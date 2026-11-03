# 02 — AWS Lambda Basics

## What Is AWS Lambda?

**AWS Lambda** is a serverless compute service that lets you run code without provisioning or managing servers. AWS handles the underlying infrastructure and scales execution based on demand.

## Types of Lambda Functions

### Lambda Event Functions

Event-driven Lambda functions run code in response to **events** or **API calls**. You can connect a function to triggers such as:

- **Amazon API Gateway** — invoke a function from an API request.
- **Amazon S3** — invoke a function when an object is created or changed.
- **Amazon SQS** — process messages from a queue.
- **Amazon EventBridge** — respond to events or scheduled rules.

Each invocation is handled in an execution environment that is isolated from other *concurrent* environments. Lambda can scale horizontally by creating more environments as demand increases.

> **Important:** Execution environments can be reused across invocations, so temporary in-memory state may persist between *sequential* invocations in the same environment. Do not rely on that state being available. Store persistent state externally, such as in DynamoDB or S3.

### Lambda Web Functions

Lambda can also power web applications and API backends.

- With **Lambda Web Adapter** or a compatible framework, a web application (for example, a Node.js app) can handle HTTP requests while running on Lambda.
- Traditional event-based API integrations commonly use **API Gateway** or **Lambda Function URLs** to receive HTTP requests and pass them to the Lambda handler.

## Lambda Execution Environments and MicroVMs

AWS Lambda uses isolated execution environments backed by **Firecracker microVMs**.

- Execution environments are designed for fast startup and secure isolation.
- A single invocation can run for a **maximum of 15 minutes** (900 seconds).
- A warm environment may be reused for subsequent invocations.

## Execution Role (IAM)

A Lambda **execution role** is an AWS Identity and Access Management (**IAM**) role that grants the function permission to access AWS services and resources.

For example, a function may need permission to write logs to **Amazon CloudWatch Logs** or read objects from an **S3 bucket**.

> The execution role grants permissions **to the running function**, not to the IAM user who creates or deploys it. The user deploying the function needs their own permissions, such as `lambda:CreateFunction` and `iam:PassRole` where applicable.

## Event Function Code (Python)

A Lambda function written in Python may contain **multiple Python functions**, but the configured handler is the entry point for an invocation.

By default, a common handler name is `lambda_handler` (though you can configure another name). The handler accepts two arguments:

- **`event`** — input data for the invocation, typically represented as a Python dictionary decoded from a JSON event payload. The structure depends on the event source.
- **`context`** — an object containing runtime and invocation information, such as the request ID and remaining execution time.

```python
import json
import logging

logger = logging.getLogger()
logger.setLevel(logging.INFO)


def format_message(name):
    return f"Hello, {name}!"


def lambda_handler(event, context):
    name = event.get("name", "World")
    message = format_message(name)

    logger.info("Request ID: %s", context.aws_request_id)
    logger.info("Message: %s", message)

    return {
        "statusCode": 200,
        "body": json.dumps({"message": message}),
    }
```

The `format_message()` helper shows how a Lambda handler can call other Python functions.

## Logging in Lambda

You can log information from a Python Lambda function using:

- **`print()`** — simple output for quick debugging.
- **Python's `logging` module** — structured levels such as `INFO`, `WARNING`, and `ERROR` for more controlled logging.

Lambda normally sends standard output and logging output to **Amazon CloudWatch Logs** when its execution role has the required permissions (commonly granted via the `AWSLambdaBasicExecutionRole` managed policy).

The default CloudWatch log group is:

```text
/aws/lambda/<function-name>
```

### View Lambda Logs with the AWS CLI

```bash
# List recent log streams for a function
aws logs describe-log-streams \
  --log-group-name /aws/lambda/<function-name> \
  --order-by LastEventTime \
  --descending

# Follow log events as they arrive
aws logs tail /aws/lambda/<function-name> --follow
```

Replace `<function-name>` with the actual Lambda function name. Add `--region <region>` if your AWS CLI default region differs from the function's region.

## Key Takeaways

- Lambda runs code without you managing servers.
- Event functions respond to triggers such as API Gateway, S3, SQS, and EventBridge.
- Lambda scales by running invocations in isolated execution environments; don't assume local state persists.
- Web apps and HTTP APIs can run on Lambda using suitable integrations or adapters.
- An invocation can run for up to **15 minutes**.
- A Lambda execution role controls **what the function can access**.
- In Python, the configured handler is the entry point and receives `event` and `context`.
- Use `print()` or `logging` to write logs that can be viewed in CloudWatch Logs.
