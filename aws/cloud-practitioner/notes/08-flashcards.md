# AWS Cloud Practitioner Flashcards

## What are Flashcards? & Why They Matter

Flashcards are for active recall, not passive reading. If you can answer these quickly without looking, your chance of recognizing correct options in the real exam goes up sharply.

---

## Core Concepts

### Cloud and infrastructure

1. Q: What does elasticity mean in AWS?
   A: The ability to scale resources up or down based on demand.

2. Q: What is a Region?
   A: A separate geographic area where AWS has infrastructure.

3. Q: What is an Availability Zone?
   A: An isolated location within a Region used for high availability.

4. Q: What is an edge location used for?
   A: Low-latency content delivery and DNS-related services.

5. Q: What AWS framework has six pillars for good design?
   A: The AWS Well-Architected Framework.

6. Q: Name the six Well-Architected pillars.
   A: Operational Excellence, Security, Reliability, Performance Efficiency, Cost Optimization, Sustainability.

7. Q: What cost model shift is common when moving to AWS?
   A: CapEx to OpEx.

8. Q: What is rightsizing?
   A: Matching resources to actual workload needs to avoid over- or under-provisioning.

9. Q: What is BYOL?
   A: Bring Your Own License.

10. Q: Which migration device family is used to move large amounts of data physically?
    A: AWS Snow Family.

### Shared responsibility and IAM

11. Q: AWS is responsible for what?
    A: Security of the cloud.

12. Q: Customers are responsible for what?
    A: Security in the cloud.

13. Q: Who patches the guest OS on EC2?
    A: The customer.

14. Q: Who manages physical data center security?
    A: AWS.

15. Q: What is the AWS best practice for daily administration instead of using the root user?
    A: Use IAM identities with least privilege and MFA.

16. Q: What does least privilege mean?
    A: Grant only the permissions required to perform the task.

17. Q: What is an IAM role?
    A: An assumable identity that provides temporary permissions.

18. Q: What is MFA?
    A: Multi-factor authentication.

19. Q: Which service provides centralized workforce access to multiple AWS accounts and applications?
    A: AWS IAM Identity Center.

20. Q: Which service stores and rotates secrets?
    A: AWS Secrets Manager.

### Audit, governance, and security services

21. Q: Which service records AWS API activity?
    A: AWS CloudTrail.

22. Q: Which service provides metrics, logs, and alarms?
    A: Amazon CloudWatch.

23. Q: Which service tracks resource configuration and compliance state?
    A: AWS Config.

24. Q: Which service gives access to AWS compliance reports?
    A: AWS Artifact.

25. Q: Which service helps detect threats from AWS signals and logs?
    A: Amazon GuardDuty.

26. Q: Which service helps inspect workloads for vulnerabilities?
    A: Amazon Inspector.

27. Q: Which service helps protect web apps from common web exploits?
    A: AWS WAF.

28. Q: Which service provides DDoS protection?
    A: AWS Shield.

29. Q: Which service is commonly used to manage encryption keys?
    A: AWS KMS.

30. Q: What are the two basic encryption states you should know?
    A: Encryption at rest and encryption in transit.

### Compute

31. Q: Which AWS service provides virtual machines?
    A: Amazon EC2.

32. Q: Which service runs code without managing servers?
    A: AWS Lambda.

33. Q: Which service is a container orchestration service from AWS?
    A: Amazon ECS.

34. Q: Which service is managed Kubernetes on AWS?
    A: Amazon EKS.

35. Q: Which serverless compute option is used with containers?
    A: AWS Fargate.

36. Q: Which service helps deploy applications with managed environment handling?
    A: AWS Elastic Beanstalk.

37. Q: Which simpler service is often used for small workloads or quick starters?
    A: Amazon Lightsail.

38. Q: What provides elasticity for EC2 fleets?
    A: Auto Scaling.

39. Q: What is the main purpose of a load balancer?
    A: To distribute traffic across multiple targets.

40. Q: Which EC2 family phrase should you recognize at a high level: compute optimized, memory optimized, or storage optimized?
    A: All three.

### Storage

41. Q: Which service provides object storage?
    A: Amazon S3.

42. Q: Which service provides block storage for EC2?
    A: Amazon EBS.

43. Q: Which service provides a shared managed file system for Linux workloads?
    A: Amazon EFS.

44. Q: Which family provides managed file systems for specialized use cases like Windows?
    A: Amazon FSx.

45. Q: Which service class is used for long-term archival in S3?
    A: Amazon S3 Glacier.

46. Q: What is an S3 lifecycle policy used for?
    A: Automating movement or expiration of objects based on rules.

47. Q: What is instance store?
    A: Temporary storage physically attached to the host, lost if the instance stops or terminates.

48. Q: Which service provides cached access between on-premises environments and AWS storage?
    A: AWS Storage Gateway.

49. Q: Which AWS service provides centralized backup management?
    A: AWS Backup.

50. Q: What is the simplest pairing to memorize for storage types?
    A: S3 object, EBS block, EFS file.

### Databases and analytics

51. Q: Which service is a managed relational database platform?
    A: Amazon RDS.

52. Q: Which service is AWS’s high-performance managed relational engine family?
    A: Amazon Aurora.

53. Q: Which service is a NoSQL key-value/document database?
    A: Amazon DynamoDB.

54. Q: Which service is an in-memory cache?
    A: Amazon ElastiCache.

55. Q: Which service is used for data warehousing?
    A: Amazon Redshift.

56. Q: Which service migrates databases to AWS?
    A: AWS Database Migration Service.

57. Q: Which tool helps convert database schemas during migration?
    A: AWS Schema Conversion Tool.

58. Q: Which service queries data in S3 using SQL?
    A: Amazon Athena.

59. Q: Which service is used for data integration and ETL?
    A: AWS Glue.

60. Q: Which service creates BI dashboards and visualizations?
    A: Amazon QuickSight.

### Networking and delivery

61. Q: Which service defines a private network boundary in AWS?
    A: Amazon VPC.

62. Q: What is a subnet?
    A: A segmented network range inside a VPC.

63. Q: What is the difference between a security group and a NACL?
    A: Security groups are stateful resource-level firewalls; NACLs are stateless subnet-level filters.

64. Q: Which service is AWS DNS?
    A: Amazon Route 53.

65. Q: Which service is AWS CDN?
    A: Amazon CloudFront.

66. Q: Which service is commonly used to expose and manage APIs?
    A: Amazon API Gateway.

67. Q: Which service provides dedicated private connectivity from on-premises to AWS?
    A: AWS Direct Connect.

68. Q: Which service provides encrypted connectivity over the public internet to AWS?
    A: AWS VPN.

69. Q: What is the main benefit of CloudFront?
    A: Low-latency content delivery using edge locations.

70. Q: Why use multiple AZs?
    A: To improve availability and reduce single points of failure.

### Messaging, integration, developer, frontend, and IoT

71. Q: Which service is pub/sub notifications?
    A: Amazon SNS.

72. Q: Which service is managed queuing?
    A: Amazon SQS.

73. Q: Which service is event bus and event routing?
    A: Amazon EventBridge.

74. Q: Which service sends email?
    A: Amazon SES.

75. Q: Which service is cloud contact center?
    A: Amazon Connect.

76. Q: Which service is for CI build steps?
    A: AWS CodeBuild.

77. Q: Which service is for release pipeline orchestration?
    A: AWS CodePipeline.

78. Q: Which service helps trace requests across applications?
    A: AWS X-Ray.

79. Q: Which service helps build and host frontend web and mobile apps?
    A: AWS Amplify.

80. Q: Which service manages IoT devices and messaging?
    A: AWS IoT Core.

### AI/ML service recognition

81. Q: Which AWS service is the main managed ML platform?
    A: Amazon SageMaker AI.

82. Q: Which service builds conversational interfaces?
    A: Amazon Lex.

83. Q: Which service extracts text and data from documents?
    A: Amazon Textract.

84. Q: Which service converts speech to text?
    A: Amazon Transcribe.

85. Q: Which service translates text?
    A: Amazon Translate.

86. Q: Which service analyzes sentiment and text?
    A: Amazon Comprehend.

87. Q: Which service is often used for intelligent enterprise search?
    A: Amazon Kendra.

88. Q: Which service can analyze images and video?
    A: Amazon Rekognition.

89. Q: Which service converts text to lifelike speech?
    A: Amazon Polly.

90. Q: For CLF-C02, how deep do you need to know AI/ML services?
    A: At high-level use-case matching depth.

### Billing, support, and governance

91. Q: Which pricing model has no long-term commitment?
    A: On-Demand.

92. Q: Which pricing model fits interruptible workloads?
    A: Spot Instances.

93. Q: Which pricing option fits steady predictable use with commitment?
    A: Reserved Instances or Savings Plans.

94. Q: Which service alerts on budget thresholds?
    A: AWS Budgets.

95. Q: Which service analyzes historical spend?
    A: AWS Cost Explorer.

96. Q: Which tool estimates the cost of a planned design?
    A: AWS Pricing Calculator.

97. Q: Which service helps manage multiple accounts and consolidated billing?
    A: AWS Organizations.

98. Q: Which service provides best-practice checks, including cost optimization guidance?
    A: AWS Trusted Advisor.

99. Q: Which dashboard shows AWS service and account health events?
    A: AWS Health Dashboard.

100. Q: Which support plan is the safer choice for production-critical workloads than Developer Support?
     A: Business Support.

### Cloud concepts and models

101. Q: Name the six advantages of cloud computing (AWS).
     A: 1) Trade capital expense for variable expense, 2) Benefit from massive economies of scale, 3) Stop guessing capacity, 4) Increase speed and agility, 5) Stop spending money running/maintaining data centers, 6) Go global in minutes.

102. Q: What is the difference between IaaS, PaaS, and SaaS?
     A: IaaS = you manage OS/apps on AWS infrastructure (EC2); PaaS = AWS manages the platform, you deploy code (Elastic Beanstalk); SaaS = ready-to-use software (e.g., Amazon WorkMail).

103. Q: What are the three cloud deployment models?
     A: Cloud (all-in), Hybrid (cloud + on-premises), and On-premises/Private (e.g., AWS Outposts for hybrid).

104. Q: Why does the cloud offer lower variable cost ("economies of scale")?
     A: AWS aggregates usage from huge numbers of customers, which lowers pay-as-you-go prices.

### Cloud Adoption Framework (CAF)

105. Q: What is the AWS Cloud Adoption Framework (CAF)?
     A: Guidance to plan and accelerate an organization's cloud adoption, organized into 6 perspectives.

106. Q: Name the 6 CAF perspectives.
     A: Business, People, Governance, Platform, Security, Operations.

107. Q: Which 3 CAF perspectives are the business (non-technical) capabilities?
     A: Business, People, Governance. (Platform, Security, Operations are technical.)

108. Q: Which CAF perspective covers skills, culture, training, and change management?
     A: The People perspective.

109. Q: Which CAF perspective covers risk, compliance, and cloud financial management?
     A: The Governance perspective.

110. Q: Name the 4 CAF transformation phases in order.
     A: Envision, Align, Launch, Scale.

111. Q: Which CAF phase identifies capability gaps across the 6 perspectives?
     A: The Align phase.

112. Q: CAF vs Well-Architected Framework?
     A: CAF = organizational cloud adoption (6 perspectives); Well-Architected = workload/architecture design (6 pillars).

### Well-Architected and review tools

113. Q: Which AWS tool reviews a workload against the 6 pillars and flags risks?
     A: The AWS Well-Architected Tool (free in the console).

114. Q: Which Well-Architected pillar covers availability, failover, and disaster recovery?
     A: Reliability.

115. Q: How many categories does Trusted Advisor check?
     A: 6 — Cost Optimization, Performance, Resilience, Security, Operational Excellence, Service Limits. (Older material lists 5 with "Fault Tolerance.")

### Migration (7 Rs)

116. Q: Name the 7 Rs of migration.
     A: Rehost, Replatform, Relocate, Repurchase, Refactor, Retire, Retain.

117. Q: Which R is "lift-and-shift" with no changes?
     A: Rehost.

118. Q: Which R means rewriting an app for cloud-native benefits?
     A: Refactor (Re-architect).

### Support plans

119. Q: Name the 5 AWS Support plans.
     A: Basic, Developer, Business, Enterprise On-Ramp, Enterprise.

120. Q: Which support plans include a Technical Account Manager (TAM)?
     A: Enterprise (designated TAM) and Enterprise On-Ramp (pool of TAMs).

121. Q: What is the minimum plan for 24/7 phone, chat, and email with Cloud Support Engineers?
     A: Business Support.

### Billing and pricing (extras)

122. Q: What does AWS Organizations consolidated billing provide?
     A: A single bill across accounts plus volume (tiered) pricing discounts.

123. Q: Which commitment-based option is most flexible across EC2, Lambda, and Fargate?
     A: Compute Savings Plans.

124. Q: What are cost allocation tags used for?
     A: Attributing and tracking AWS costs by team, project, or environment.

### Networking and global (extras)

125. Q: What does AWS Transit Gateway do?
     A: Acts as a central hub connecting many VPCs and on-premises networks with transitive routing (replaces the VPC peering mesh).

126. Q: CloudFront vs Global Accelerator?
     A: CloudFront = CDN that caches HTTP/S content at edge locations; Global Accelerator = network-layer routing with static IPs for TCP/UDP (no caching).

127. Q: What is a VPC gateway endpoint used for?
     A: Private access to S3/DynamoDB from a VPC without traffic going over the internet (and it's free).

### Security and governance (extras)

128. Q: In IAM policy evaluation, what wins — allow or explicit deny?
     A: An explicit deny always wins.

129. Q: What are Service Control Policies (SCPs) in AWS Organizations?
     A: Guardrails that set the maximum permissions for accounts/OUs (they don't grant access).

130. Q: Which service sets up a secure multi-account environment with best-practice guardrails?
     A: AWS Control Tower.

131. Q: Which service discovers sensitive data such as PII in S3?
     A: Amazon Macie.

132. Q: Which service centralizes security findings across accounts?
     A: AWS Security Hub.

---

## Practical Examples & Reference Snippets

Flashcard usage pattern:

```text
Round 1: Answer from memory
Round 2: Mark misses
Round 3: Re-answer only misses after 2 hours
Round 4: Re-answer next day
```

---

## Quick Reference

```text
Audit -> CloudTrail
Metrics -> CloudWatch
Object -> S3
Block -> EBS
File -> EFS
Managed SQL -> RDS/Aurora
NoSQL -> DynamoDB
Queue -> SQS
Pub/Sub -> SNS
Event bus -> EventBridge
Spend alert -> Budgets
Spend analysis -> Cost Explorer
CAF -> org adoption (6 perspectives: B/P/G + P/S/O)
WAF -> workload design (6 pillars: O-S-R-P-C-S)
7 Rs -> Rehost, Replatform, Relocate, Repurchase, Refactor, Retire, Retain
TAM -> Enterprise (+ Enterprise On-Ramp)
```
