### Summary of Key AWS Services Explained

### Core AWS Services Overview

|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| Category                                      | Service                                         | Key Features & Use Cases                                                                                         |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **DNS & Traffic Management**                  | **Route 53**                                    | Domain registration, DNS management, health checks, geographic & latency-based routing, failover configuration.  |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Storage**                                   | **S3 (Simple Storage Service)**                 | Object/blob storage for static content such as images, HTML, files; event triggers integration with Lambda.      |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **EFS (Elastic File System)**                   | Shared file storage mountable by multiple EC2 instances for static content sharing.                              |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **EBS (Elastic Block Store)**                   | Block storage attached to single EC2 instances, suited for databases and transactional workloads.                |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Content Delivery**                          | **CloudFront**                                  | CDN service for caching and replicating S3 content globally to reduce latency and improve user experience.       |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Compute**                                   | **EC2 (Elastic Compute Cloud)**                 | Flexible virtual servers with OS choice; requires manual management (patching, scaling, teardown, avalibility).  |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Lightsail**                                   | Simplified virtual server hosting with predefined templates; ideal for beginners or small apps.                  |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **ECS (Elastic Container Service)**             | Container orchestration with lifecycle management; supports serverless via Fargate for simpler deployment.       |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **EKS (Elastic Kubernetes Service)**            | Managed Kubernetes service; supports container orchestration for Kubernetes users.                               |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Lambda**                                      | Serverless compute for running code functions on demand; auto-scaling; integrates with many AWS services.        |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **API & Load Balancing**                      | **Elastic Load Balancer (ELB)**                 | Distributes incoming API traffic to multiple compute instances; supports auto-scaling and sticky sessions.       |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **API Gateway**                                 | Managed API endpoints; supports REST and WebSocket; integrates with various AWS services; rate limiting & auth.  |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Security**                                  | **WAF (Web Application Firewall)**              | Protects APIs/websites from bot attacks, SQL injection, IP banning.                                              |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Shield**                                      | DDoS protection; free basic tier; paid Shield Advanced for mission-critical apps with 24/7 monitoring & support. |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Certificate Manager**                         | Manages SSL/TLS certificates for HTTPS encryption across AWS endpoints.                                          |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Cognito**                                     | User authentication and authorisation via user pools; token-based access control for APIs.                       |
|                                               |                                                 | User registers -> login to Cognito -> cognito returns a token -> call API endpoint with security token           |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Databases**                                 | **RDS (Relational Database Service)**           | Managed relational DB supporting MySQL, Oracle, SQL Server, multi-AZ availability, auto-scaling, monitoring.     |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Aurora**                                      | AWS-developed relational DB compatible with MySQL/Postgres; supports serverless scaling to zero.                 |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **DynamoDB**                                    | Fully managed NoSQL key-value store with predictable performance; widely used internally by AWS.                 |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **DocumentDB**                                  | Managed MongoDB-compatible document database.                                                                    |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Keyspaces**                                   | Managed Apache Cassandra-compatible NoSQL database.                                                              |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Neptune**                                     | Graph database for relationship queries, e.g., social networks.                                                  |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **OpenSearch**                                  | Managed Elasticsearch fork for search and log analytics; supports Kibana dashboards.                             |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **DMS (Database Migration Service)**            | Migrates on-premise databases to AWS managed databases.                                                          |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Caching**                                   | **ElastiCache**                                 | Managed Redis or Memcached caching; volatile cache that loses data on node failure.                              |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **MemoryDB**                                    | Redis-compatible caching with durability via replication logs; cache data persists through failures.             |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **AI & Machine Learning**                     | **Bedrock**                                     | Facilitates integration with multiple foundational AI models for chatbots, image/voice generation.               |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Sagemaker**                                   | Platform for building, training, deploying machine learning models; aimed at data scientists.                    |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Recognition**                                 | Image and video analysis for face detection, emotion, text, scene context.                                       |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Polly**                                       | Text-to-speech synthesis with multiple voices.                                                                   |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Transcribe**                                  | Speech-to-text conversion with speaker identification; useful for transcription of meetings/interviews.          |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Application Coordination & Messaging**      | **SNS (Simple Notification Service)**           | Pub/sub messaging for broadcasting notifications to multiple subscribers asynchronously.                         |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **SQS (Simple Queue Service)**                  | Message queue for decoupling components; supports FIFO and standard queues for event processing.                 |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **EventBridge**                                 | Event bus supporting AWS service events, custom events, schema discovery, rules for scheduled triggers.          |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Step Functions**                              | Workflow orchestration with conditional logic, parallel tasks, failure handling, and task sequencing.            |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **MWAA (Managed Workflows for Apache Airflow)** | Managed open-source workflow orchestration alternative to Step Functions.                                        |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Data Processing & Analytics**               | **EMR (Elastic MapReduce)**                     | Managed Hadoop/Spark clusters for big data processing.                                                           |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Athena**                                      | Serverless SQL querying directly on data stored in S3.                                                           |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Glue**                                        | Serverless ETL and data catalog with Glue Studio for data preparation and transformation.                        |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Redshift**                                    | Fully managed, scalable columnar data warehouse for large-scale analytics; expensive, suited for large orgs.     |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **QuickSight**                                  | BI and data visualisation service similar to Power BI; integrates with Redshift and S3.                          |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Kinesis**                                     | Real-time streaming data ingestion and processing; supports Firehose for batch delivery to S3.                   |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Monitoring & Logging**                      | **CloudWatch**                                  | Logs, metrics, dashboards, alarms, and CloudWatch Insights for querying logs.                                    |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **CloudTrail**                                  | Audit logs for AWS account activity and API calls.                                                               |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Config**                                      | Configuration monitoring and compliance enforcement with policy checks.                                          |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **X-Ray**                                       | Distributed tracing and profiling for debugging and performance analysis.                                        |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **CI/CD (Continuous Integration & Delivery)** | **CodeBuild**                                   | Builds and tests source code; runs unit tests and builds artifacts.                                              |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **CodeDeploy**                                  | Automates deployment to EC2, Lambda, or on-premise instances.                                                    |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **CodePipeline**                                | Orchestrates build, test, deployment pipeline stages.                                                            |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Infrastructure as Code (IaC)**              | **CloudFormation**                              | Declarative JSON/YAML templates for provisioning AWS infrastructure.                                             |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **CDK (Cloud Development Kit)**                 | Allows writing IaC using familiar programming languages (Python, Java, Ruby, etc.) with constructs & logic.      |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Developer Productivity**                    | **Amplify**                                     | Simplified framework for full-stack app deployment with built-in auth, storage, hosting; good for prototyping.   |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **AppSync**                                     | Managed GraphQL service for building APIs with resolvers without managing backend infrastructure.                |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **WorkSpaces**                                  | Managed virtual desktop infrastructure for remote user environments.                                             |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Amazon Q**                                    | AI-powered developer assistant integrated into IDE for code completion and AWS resource queries.                 |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **MCP (Model Context Protocol)**                | Experimental AI-driven natural language interface for querying AWS resources; potential security risks.          |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Identity & Access Management**              | **IAM (Identity and Access Management)**        | Defines users, roles, and policies to control resource access and permissions.                                   |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **Identity Center**                             | Integrates external identity providers for user and permission management across AWS accounts.                   |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
| **Networking**                                | **VPC (Virtual Private Cloud)**                 | Isolated virtual networks within AWS cloud for resource segregation and security.                                |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **VPN**                                         | Secure tunnels from external networks to access VPC resources.                                                   |
|                                               |-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|
|                                               | **PrivateLink**                                 | Private communication between VPCs and AWS services without public internet exposure.                            |
|-----------------------------------------------|-------------------------------------------------|------------------------------------------------------------------------------------------------------------------|

### Key Insights

- **Route 53** is fundamental for managing domain names and traffic routing with advanced features like health checks and geo-routing.
- **Amazon S3** combined with **CloudFront** provides efficient, globally distributed static content delivery.
- **Compute options range** from full control with EC2, simplified Lightsail, container orchestration with ECS/EKS, to serverless Lambda offering zero maintenance and automatic scaling.
- **API Gateway** offers fine-grained control, security, and integration for APIs beyond what load balancers provide.
- **Security services** such as WAF and Shield protect applications from common web attacks and DDoS, while Certificate Manager ensures encrypted communications.
- **Databases cover relational, document, key-value, graph, and search use cases**, with serverless options like Aurora Serverless and fully managed NoSQL solutions like DynamoDB and DocumentDB.
- **Caching solutions** differ in persistence: ElastiCache is volatile, while MemoryDB offers state durability.
- **AI services** cater both to developers (Bedrock) and data scientists (Sagemaker), with specialised services for media analysis and speech/text conversion.
- **Messaging and event-driven architectures** leverage SNS, SQS, EventBridge, and Step Functions for decoupled, scalable workflows.
- **Data analytics stack** includes raw data storage (S3), processing (EMR, Glue), querying (Athena, Redshift), visualisation (QuickSight), and real-time ingestion (Kinesis).
- **Monitoring tools** like CloudWatch and CloudTrail provide operational and security visibility; X-Ray delivers deep application profiling.
- **CI/CD tools** automate building, testing, and deployment pipelines, improving development velocity and reliability.
- **Infrastructure as Code** is supported via CloudFormation and the more user-friendly CDK, enabling repeatable, auditable deployments.
- **Developer tools** like Amplify and AppSync simplify app development but may limit flexibility at scale.
- **IAM and Identity Center** underpin secure access management across AWS resources.
- **VPCs and related networking services** ensure secure, isolated cloud environments with controlled access.

Video: https://www.youtube.com/watch?v=OGYEXGy8ca4
