# AWS Certified Developer – Associate (DVA-C03) Study Tracker

**Exam date:** Sunday, January 24, 2027  
**Study start:** October 27, 2026  
**Study window:** October 27, 2026 – January 24, 2027 (~13 weeks)  
**Study target:** 7–10 hours/week (adjust as needed)  
**Primary platform:** [AWS Skill Builder](https://skillbuilder.aws/)  
**Status:** 🟡 In progress

> **Goal:** Pass the AWS Certified Developer – Associate exam **and** learn to build, deploy, monitor, and troubleshoot production-style AWS applications. This is a *Developer* certification plan with deliberate DevOps practice.
>
> **Exam version:** Prepare for **DVA-C03**, which launches December 1, 2026. Check the exam code in your appointment confirmation and select DVA-C03-aligned Skill Builder materials; older DVA-C02 content may not cover all updates.

## Exam at a glance

| Detail | Target |
| --- | --- |
| Certification | AWS Certified Developer – Associate |
| Exam code | DVA-C03 |
| Date | **2027-01-24** |
| Duration | 130 minutes |
| Questions | 65 multiple-choice / multiple-response |
| Passing scaled score | 720 / 1,000 |
| Exam domains | Development (30%); Security (26%); Testing & Deployment (22%); Troubleshooting & Optimization (22%) |

Source: [AWS certification update for DVA-C03](https://aws.amazon.com/blogs/training-and-certification/september-2026-new-offerings/). Always use the **latest [official exam guide](https://aws.amazon.com/certification/certified-developer-associate/)** as the source of truth for detailed objectives.

## How to use this repository

1. In [AWS Skill Builder](https://skillbuilder.aws/), find the **AWS Certified Developer – Associate Exam Prep Plan** and enroll. Choose **DVA-C03** materials where available.
2. Work through the corresponding Skill Builder **digital training**, **Exam Prep review/practice**, and **hands-on labs** listed below. Course names and catalog availability can change; use the topics and search terms rather than assuming an exact course title exists.
3. Check off tasks as you complete them (`[ ]` → `[x]`). Commit your progress weekly.
4. Keep notes in `notes/`, screenshots or diagrams in `assets/` (no credentials), and code for the capstone in `labs/` or a linked separate repo.
5. Track *why* you missed practice questions; reviewing answers is more valuable than repeating memorized questions.

### Suggested weekly study routine

- **3 hours:** Skill Builder courses / Exam Prep Review
- **2–3 hours:** AWS Builder Labs or your own safe, budgeted AWS sandbox
- **1–2 hours:** notes, flashcards, AWS documentation
- **1–2 hours:** practice questions and explanation review

**Budget/security checklist (do before labs):**

- [ ] Enable MFA and use a least-privilege identity; don't use the root user for routine labs.
- [ ] Set up AWS Budgets and billing alerts. (Alerts are **not** hard spending caps.)
- [ ] Understand which resources cost money, especially NAT gateways, load balancers, RDS, Fargate, and public IPv4 addresses.
- [ ] Shut down/delete test resources after each lab; verify in the billing console.
- [ ] Never commit AWS keys, passwords, tokens, `.env` files, or real customer data.

## Progress dashboard

| Week | Dates | Focus | Done |
| --- | --- | --- | --- |
| 1 | Oct 27–Nov 1 | Essential AWS foundations + first Lambda | ⬜ |
| 2 | Nov 2–8 | Lambda deep dive: IAM, events, testing, logging | ⬜ |
| 3 | Nov 9–15 | API Gateway + Lambda deployment and integration tests | ⬜ |
| 4 | Nov 16–22 | DynamoDB and data access | ⬜ |
| 5 | Nov 23–29 | Integration, events & asynchronous workflows | ⬜ |
| 6 | Nov 30–Dec 6 | Application security | ⬜ |
| 7 | Dec 7–13 | Testing and deployment | ⬜ |
| 8 | Dec 14–20 | Containers & DevOps capstone | ⬜ |
| 9 | Dec 21–27 | Monitoring, troubleshooting & optimization | ⬜ |
| 10 | Dec 28–Jan 3 | New DVA-C03 topics and domain review | ⬜ |
| 11 | Jan 4–10 | Complete capstone; timed practice exams | ⬜ |
| 12 | Jan 11–17 | Target weak domains; final full mock | ⬜ |
| 13 | Jan 18–24 | Light review and exam day | ⬜ |

## Weekly plan

### Week 1 — Oct 27–Nov 1: Essential AWS foundations and first Lambda

**Why this order?** Keep the fundamentals **before** Lambda, but make them a short, practical prerequisite—not an entire week of theory. Lambda requires an execution role, permissions, a Region, and logging. Start Lambda as soon as these ideas make sense.

**AWS Skill Builder searches:** *AWS global infrastructure*, *AWS IAM fundamentals*, *AWS CloudShell*, *AWS Lambda foundations*. Use short introductory lessons; don't feel obligated to finish all of Cloud Practitioner Essentials.

- [x] Read the DVA-C03 exam overview and four exam domain weights.
- [x] Enroll in the relevant Skill Builder [DVA-C03 prep plan](https://skillbuilder.aws/category/exam-prep/developer-associate-DVA-C03).
- [x] Take Official Practice Question Set baseline: **6/20 (30%)**; see assessment below.
- [ ] **NEXT:** Review Regions vs. Availability Zones, shared responsibility, IAM users vs. roles vs. policies, and AWS CLI vs. CloudShell (aim for 1–2 focused sessions).
- [ ] Configure MFA, safe lab access, AWS Budgets and billing alerts before creating resources.
- [ ] **Mini-lab:** In CloudShell run `aws sts get-caller-identity` and `aws configure list`; document what identity the CLI is using. Avoid creating long-lived access keys for this lab.
- [ ] **First Lambda lab:** Follow [AWS's first Lambda function tutorial](https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html) using Python. Create, invoke with a test JSON event, inspect logs, and clean up resources when finished.
- [ ] Save `notes/01-foundations.md` and `notes/02-lambda-basics.md`; commit notes and record anything confusing.

**Week 1 checkpoint:** Explain why Lambda needs an IAM execution role, what a test event is, where its logs go, and the difference between a Region and an Availability Zone.

### Week 2 — Nov 2–8: Lambda deep dive (starting from zero)

**AWS Skill Builder searches:** *AWS Lambda*, *AWS Lambda foundations*, *AWS Lambda permissions*, *serverless testing*, *Amazon CloudWatch Logs*.

- [ ] Understand serverless, runtimes, handlers, event/context objects, and synchronous vs. asynchronous invocations.
- [ ] Learn Lambda execution roles, resource-based permissions, environment variables, memory, timeout, and deployment packages.
- [ ] Learn how CloudWatch logs work; deliberately trigger a handled error and diagnose it.
- [ ] Practice Python Lambda unit tests locally with `pytest` and mocked AWS SDK dependencies.
- [ ] **Lab:** Make a Lambda function that validates an input JSON payload, returns clear success/error responses, and logs useful debugging information.
- [ ] **Lab:** Test valid, missing, and malformed input events; document expected vs. actual results.
- [ ] Study AWS SDK for Python (Boto3) basics and credential/permission handling inside Lambda.
- [ ] Read about concurrency, throttling, retries, idempotency, cold starts, versions, and aliases; explain them in plain language.
- [ ] Commit `notes/03-lambda-deep-dive.md` and tests in `labs/lambda-basics/`.

**Week 2 checkpoint:** Explain handler vs. runtime, invocation types, execution role vs. permission to invoke, local unit testing vs. tests in AWS, and what happens if a Lambda invocation fails.

### Week 3 — Nov 9–15: API Gateway + Lambda, testing and repeatable deployment

**AWS Skill Builder searches:** *Amazon API Gateway*, *AWS SAM*, *AWS Lambda testing*, *serverless applications*, *AWS CodeBuild*.

- [ ] Learn API Gateway HTTP endpoints, routes, integrations, authorization, throttling, and stages.
- [ ] **Lab:** Expose a Lambda function via API Gateway; send requests with `curl` or Postman.
- [ ] **Lab:** Run integration tests against the deployed API; compare with local unit tests and investigate an IAM or validation error.
- [ ] Learn environment isolation: separate test/staging resources, Lambda versions and aliases, and what aliases **do not** isolate.
- [ ] Deploy the API reproducibly with AWS SAM or CloudFormation; avoid relying only on console clicks.
- [ ] Review safe deployment patterns, validation before release, and CloudWatch logs for troubleshooting.
- [ ] Commit API, test code, deployment definition, and `notes/04-api-gateway-testing.md`.

**Week 3 checkpoint:** Demonstrate an HTTP request → API Gateway → Lambda → response, and explain how to test and deploy changes safely.

### Week 4 — Nov 16–22: DynamoDB and databases

**Skill Builder searches:** *Amazon DynamoDB*, *DynamoDB developer*, *Amazon RDS basics*.

- [ ] Learn partition/sort keys, access patterns, Query vs. Scan, GSIs/LSIs.
- [ ] Study conditional writes, TTL, consistency, streams, capacity modes, and transactions.
- [ ] Compare DynamoDB vs. RDS for common use cases.
- [ ] **Lab:** Add DynamoDB CRUD to the serverless API; test a conditional update.
- [ ] Make a one-page DynamoDB decision cheat sheet.

### Week 5 — Nov 23–29: Events and application integration

**Skill Builder searches:** *Amazon SQS*, *Amazon SNS*, *Amazon EventBridge*, *AWS Step Functions*.

- [ ] Compare queues vs. pub/sub vs. event buses vs. workflows.
- [ ] Understand SQS visibility timeout, dead-letter queues, ordering, deduplication, and retries.
- [ ] Study EventBridge rules and event-driven designs.
- [ ] **Lab:** API/Lambda → SQS → worker Lambda; demonstrate a retry and DLQ.
- [ ] Sketch synchronous vs. asynchronous architectures.

### Week 6 — Nov 30–Dec 6: Security (26%)

**Skill Builder searches:** *AWS application security*, *IAM*, *AWS KMS*, *AWS Secrets Manager*, *Amazon Cognito*.

- [ ] Review IAM evaluation, role assumption, least privilege, and temporary credentials.
- [ ] Learn KMS, encryption at rest/in transit, Secrets Manager vs. Systems Manager Parameter Store.
- [ ] Understand Cognito use cases, authorizers, and application authentication patterns.
- [ ] **Lab:** Replace a hard-coded configuration secret with Secrets Manager or a secure equivalent.
- [ ] Review any newly released DVA-C03 security / AI-service integration objectives in the official guide.

### Week 7 — Dec 7–13: Testing and deployment (22%) — second pass

**Skill Builder searches:** *AWS CodePipeline*, *AWS CodeBuild*, *AWS CodeDeploy*, *AWS SAM*, *deployment strategies*.

- [ ] Revisit unit vs. integration vs. end-to-end tests, mocking AWS services, test environments, and pre-deployment validation (build on Weeks 2–3).
- [ ] Compare rolling, blue/green, canary, and all-at-once deployments.
- [ ] Review CI/CD stages, approvals, rollback, and deployment artifacts.
- [ ] **Lab:** Build a GitHub Actions workflow that runs tests and deploys your small serverless app.
- [ ] Describe when CodePipeline/CodeBuild/CodeDeploy would replace or complement GitHub Actions.

### Week 8 — Dec 14–20: Containers and the DevOps capstone

**Skill Builder searches:** *Amazon ECR*, *Amazon ECS*, *AWS Fargate*, *Amazon CloudWatch*.

- [ ] Study ECR repositories/images and ECS tasks, services, and task roles.
- [ ] Compare Lambda vs. ECS/Fargate vs. EC2 deployment choices.
- [ ] **Capstone:** Containerize a small Node.js or Python API; add tests and a Dockerfile.
- [ ] **Capstone:** Use GitHub Actions to build/push an image to ECR and deploy to ECS/Fargate (only if costs are acceptable).
- [ ] Capture a redacted architecture diagram, deployment steps, and cleanup instructions.

### Week 9 — Dec 21–27: Troubleshooting and optimization (22%)

**Skill Builder searches:** *Amazon CloudWatch*, *AWS X-Ray*, *AWS observability*, *AWS Lambda optimization*.

- [ ] Read CloudWatch logs, metrics, alarms, and dashboards.
- [ ] Trace failures across API Gateway, Lambda, and downstream services.
- [ ] Practice interpreting throttling, permissions errors, retry storms, and timeout failures.
- [ ] Study caching, performance, concurrency, and cost tradeoffs.
- [ ] **Lab:** Intentionally break a lab application, diagnose it using logs/metrics, and document root cause and fix.

### Week 10 — Dec 28–Jan 3: DVA-C03 gap review

**Skill Builder:** Use *Exam Prep Review* and *Exam Prep Practice* resources for the updated exam, where available.

- [ ] Compare your notes against **all objectives in the current DVA-C03 exam guide**.
- [ ] Cover DVA-C03 AI-assisted development and secure AI-service integration topics at the depth listed in the guide (not general ML theory).
- [ ] Review flashcards and domain question sets; log missed topics.
- [ ] Create a 1-page AWS service selection/decision matrix.
- [ ] Update your weak-topic list in the score tracker below.

### Week 11 — Jan 4–10: Integrate your learning

- [ ] Finish the capstone README and diagram; verify deployment from a clean git commit.
- [ ] Add structured logs, an alarm, and a documented rollback procedure.
- [ ] Take a **timed, unseen** full-length practice exam if available.
- [ ] Review every incorrect or guessed answer; connect each miss to a specific exam objective.
- [ ] Revisit the lowest-performing two domains in Skill Builder.

### Week 12 — Jan 11–17: Exam readiness

- [ ] Take a second timed full-length practice exam using fresh questions if available.
- [ ] Aim for **~80%+ on fresh practice questions** as a personal buffer, **not** an AWS passing-score conversion.
- [ ] Re-study IAM/KMS, Lambda/API Gateway, DynamoDB, SQS/EventBridge, CI/CD, and monitoring based on misses.
- [ ] Use AWS Skill Builder's **Official Practice Exam** if included in your subscription.
- [ ] Confirm exam appointment, name/ID requirements, time zone, and testing instructions.

### Week 13 — Jan 18–24: Final review and exam

- [ ] Review only weak areas, diagrams, service comparisons, and error log.
- [ ] Complete a few short **fresh** question sets; avoid cramming large new topics.
- [ ] Check test-center travel or online-proctor technical requirements.
- [ ] **January 23:** Rest, sleep, and prepare ID/check-in details.
- [ ] **January 24 — EXAM DAY:** Take AWS Certified Developer – Associate (DVA-C03).
- [ ] Record result and write down next steps for the Solutions Architect / DevOps path.

## Hands-on capstone: AWS deployment pipeline

**Goal:** Show real deployment and operational skills alongside certification prep.

```text
GitHub repository
       |
       v
GitHub Actions (lint + tests + Docker build)
       |
       v
Amazon ECR (container image)
       |
       v
Amazon ECS / Fargate (running API)
       |
       v
Amazon CloudWatch (logs + alarm)
```

**Definition of done**

- [ ] A small Dockerized API runs locally with a documented start command.
- [ ] CI runs tests before deployment.
- [ ] The image is versioned and pushed to ECR without hard-coded AWS secrets (prefer GitHub OIDC + an IAM role).
- [ ] A deployment to ECS/Fargate succeeds and health checks pass.
- [ ] Logs are visible in CloudWatch; one alert is configured.
- [ ] README includes architecture, tradeoffs, approximate costs, rollback, and teardown steps.
- [ ] All paid infrastructure is torn down when no longer needed.

> If Fargate/load balancer costs are inconvenient, prioritize **Skill Builder Builder Labs** and the serverless application instead. The Docker/ECS project improves DevOps skills but isn't necessary to pass every exam objective.

## Resources

- [AWS Skill Builder](https://skillbuilder.aws/)
- [AWS Certified Developer – Associate certification and exam prep](https://aws.amazon.com/certification/certified-developer-associate/)
- [AWS official certification exam guides](https://docs.aws.amazon.com/aws-certification/latest/examguides/)
- [AWS DVA-C03 announcement, exam dates, and domain weights](https://aws.amazon.com/blogs/training-and-certification/september-2026-new-offerings/)
- [AWS Certification Exam Prep offerings](https://aws.amazon.com/certification/certification-prep/)
- [AWS Skill Builder subscriptions and available features](https://skillbuilder.aws/subscriptions)
- [AWS Well-Architected Framework](https://aws.amazon.com/architecture/well-architected/)
- [AWS pricing calculator](https://calculator.aws/)

---

**Next after this exam:** AWS Solutions Architect – Associate for architecture and infrastructure depth, followed by substantial hands-on CI/CD, IaC, monitoring, and reliability practice toward AWS DevOps Engineer – Professional.
