---
date created: 2022-01-02 21:32
date updated: 2022-01-02 21:56
---

## Module 1: Introduction

- Amazon Elastic Compute Cloud (Amazon EC2)
  A server

- What is Cloud?
  The on-demand delivery of IT resources over the internet with pay-as-you-go pricing

## Module 2: Compute in the Cloud

- EC2

  - On-Demand

  You only pay for the duration that your instance runs for. This can be per hour or per second, depending on the instance type and operating system you choose to run

  - Savings Plans

  Offers low prices on EC2 usage in exchange for a commitment to a consistent amount of usage measured in dollars per hour for a one or three-year term

  - Reserved Instances

  These are suited for steady-state workloads or ones with predictable usage and offer you up to a 75% discount versus On-Demand pricing

  - Spot Instances

  They allow you to request spare Amazon EC2 computing capacity for up to 90% off of the On-Demand price. The catch here is that AWS can reclaim the instance at any time they need it, giving you a two-minute warning to finish up work and save state. You can always resume later if needed.

  - Dedicated Hosts

  Physical hosts dedicated for your use for EC2. These are usually for meeting certain compliance requirements and nobody else will share tenancy of that host.

### Scaling

![Bar graph depicting demand and unused capacity over a 7-day period|500](https://assets.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1641189600/wbQZuTSOvXqIzUQK_6AeQg/tincan/31d9c0cca79c54bdceaf3e938fd424e97c98c7e8/assets/wYruGjMW9n2aXlH7_EVco4LYrtdoEY2Je.png)
_Bar graph depicting demand and unused capacity over a 7-day period_

![Diagram of an Amazon EC2 instances scaling in and out as part of an Auto Scaling group|500](https://assets.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1641189600/wbQZuTSOvXqIzUQK_6AeQg/tincan/31d9c0cca79c54bdceaf3e938fd424e97c98c7e8/assets/12wfvrLI1e79hjMb_f8VZ-ZFC2TOC7k5B.png)
_Diagram of an Amazon EC2 instances scaling in and out as part of an Auto Scaling group_

### Elastic Load Balancing (ELB)

![Diagram of Elastic Load Balancing during a low-demand period|500](https://assets.skillbuilder.aws/files/a/w/aws_prod1_docebosaas_com/1641189600/wbQZuTSOvXqIzUQK_6AeQg/tincan/31d9c0cca79c54bdceaf3e938fd424e97c98c7e8/assets/Mhs-brNLrz0idxgI_gxyNgUGrmnijDl62.png)
_Diagram of Elastic Load Balancing during a low-demand period_

### Messages Queues

- Amazon Simple Queue Service (SQS)
- Amazon Simple Notification Service (SNS)

---

Related: [[Amazon Apps]]
