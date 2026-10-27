# AWS Certified Developer – Associate (DVA-C03) Study Tracker

**Exam date:** Sunday, January 24, 2027  
**Study start:** October 27, 2026  
**Time available:** 89 days (~13 weeks)  
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
| 1 | Oct 27–Nov 1 | Setup, exam overview, IAM & fundamentals | ⬜ |
| 2 | Nov 2–8 | AWS SDK, S3, EC2 & application fundamentals | ⬜ |
| 3 | Nov 9–15 | Lambda & API Gateway | ⬜ |
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

### Week 1 — Oct 27–Nov 1: Setup and AWS fundamentals

**Skill Builder:** Search for the *Developer – Associate Exam Prep Plan*, *AWS Cloud Practitioner Essentials* (use selectively for unfamiliar topics), and IAM-related digital training.

- [X] Read the DVA-C03 exam overview and four exam domain weights.
- [X] Enroll in the relevant Skill Builder exam [prep plan](https://skillbuilder.aws/category/exam-prep/developer-associate-DVA-C03) DVA-C03.
- [ ] Complete the **Official Practice Question Set** as a baseline if an appropriate DVA-C03 set is available; record score and weak areas.
- [ ] Review AWS Regions/AZs, shared responsibility, IAM roles/policies, AWS CLI, and CloudShell.
- [ ] Configure MFA, a lab identity, budgets, and alerts.
- [ ] **Lab:** Make an AWS CLI call with a least-privilege role; explain credentials vs. roles.
- [ ] Commit setup notes (`notes/01-fundamentals.md`).

### Week 2 — Nov 2–8: Application foundations

**Skill Builder searches:** *AWS SDK*, *Amazon S3*, *Amazon EC2*, *AWS development fundamentals*.

- [ ] Study AWS SDK credential provider chain, retries, pagination, and error handling.
- [ ] Learn S3 object access, storage classes, presigned URLs, and event notifications.
- [ ] Review EC2, instance roles, basic VPC/security groups, and environment configuration.
- [ ] **Lab:** Use Python (Boto3) or Node.js AWS SDK to upload and read an S3 object with an IAM role or safe local profile.
- [ ] Write notes comparing IAM resource policies vs. identity policies.

### Week 3 — Nov 9–15: Lambda and API Gateway

**Skill Builder searches:** *AWS Lambda*, *Amazon API Gateway*, *serverless applications*, *AWS SAM*.

- [ ] Learn Lambda lifecycle, memory/timeout, concurrency, versions/aliases, layers, and environment variables.
- [ ] Study API Gateway routes, auth, stages, throttling, and integrations.
- [ ] Review SAM or CloudFormation for repeatable serverless deployment.
- [ ] **Lab:** Deploy a small API Gateway → Lambda API; add structured logging.
- [ ] Explain Lambda cold starts and idempotency.

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

### Week 7 — Dec 7–13: Testing and deployment (22%)

**Skill Builder searches:** *AWS CodePipeline*, *AWS CodeBuild*, *AWS CodeDeploy*, *AWS SAM*, *deployment strategies*.

- [ ] Understand unit vs. integration tests, mocking AWS services, and pre-deployment validation.
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
- [ ] Complete a few short question sets; avoid cramming large new topics.
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

## Practice exam & weak-area log

| Date | Resource | Score | Development | Security | Test/Deploy | Troubleshoot/Optimize | Top weaknesses |
| --- | --- | --- | --- | --- | --- | --- | --- |
| YYYY-MM-DD | Official Practice Question Set | — | — | — | — | — | — |
| YYYY-MM-DD | Full-length practice #1 | — | — | — | — | — | — |
| YYYY-MM-DD | Full-length practice #2 | — | — | — | — | — | — |

**Missed-question journal template:**

```text
Date:
Domain / objective:
Service / concept:
Why I got it wrong:
Correct rule / decision point:
Hands-on test or documentation link:
Revisit on:
```

**Avoid score inflation:** Skill Builder practice sets may repeat the same questions on retakes. Track *first attempts* separately from repeats.

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
