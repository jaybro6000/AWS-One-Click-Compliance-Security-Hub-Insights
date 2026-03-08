## AWS One-Click Compliance & Security Hub Insights
An Automated Cloud Governance project focused on eliminating misconfigured S3 buckets and enforcing real-time security guardrails. By integrating AWS Security Hub, IAM Access Analyzer, and Amazon EventBridge, this system provides an "always-on" monitoring pipeline that catches and alerts on public exposure within seconds of a policy change.

## Project Workflow
## 1. Centralized Security Governance
Deploying AWS Security Hub to aggregate security findings and benchmarks across the account, providing a single pane of glass for compliance posture.
<img width="1920" height="808" alt="One_Click_Compliance_Security_Hub_Insights_1" src="https://github.com/user-attachments/assets/7b11caf5-f5f4-433d-a912-3a8a02df3e02" />


## 2. Identifying the Vulnerability (S3 Public Access)
The "Before" state: An S3 bucket (compliance-test-unencrypted) with a wide-open policy allowing s3:GetObject to Principal: a critical data leak risk.
<img width="1920" height="831" alt="One_Click_Compliance_Security_Hub_Insights_12" src="https://github.com/user-attachments/assets/290d6db8-5be2-40ee-9dcb-c6c5df692c6b" />

## 3. Automated Detection via Access Analyzer
Leveraging IAM Access Analyzer to automatically flag the bucket as "Public" or "Accessible from outside the account" without manual scanning.
<img width="1920" height="808" alt="One_Click_Compliance_Security_Hub_Insights_14" src="https://github.com/user-attachments/assets/ee799e59-fa2f-4d0f-a8ef-6f949a8addcd" />

## 4. Orchestrating the Alerting Pipeline
Crafting an EventBridge Rule using a JSON pattern to listen specifically for Access Analyzer Findings and instantly route them to an Amazon SNS topic.
<img width="1920" height="819" alt="One_Click_Compliance_Security_Hub_Insights_11" src="https://github.com/user-attachments/assets/0607322c-6cd2-4418-8bbd-bfaca73dd9f6" />

## 5. Verified Incident Response (Email Alert)
The "Proof of Concept": An automated email notification delivered via SNS, providing the security team with the exact Bucket ARN and account details for immediate remediation.
<img width="956" height="399" alt="One_Click_Compliance_Security_Hub_Insights_15" src="https://github.com/user-attachments/assets/bdd7ad82-9987-4a80-9d34-e38a15a520e4" />


## Tech Stack
Monitoring: AWS Security Hub, IAM Access Analyzer

Automation: Amazon EventBridge (CloudWatch Events)

Alerting: Amazon SNS (Simple Notification Service)

Governance: Amazon S3 (Policy Compliance)

Security Principle: Automated Incident Response & Continuous Compliance Architecture

## Key Takeaways
Reduced MTTD: This architecture minimizes the Mean Time to Detect (MTTD) misconfigurations from hours to seconds.

Scalability: This solution is "One-Click" ready and can be scaled across multiple AWS Regions using Security Hub aggregation.

Hands-on Experience: Demonstrated proficiency in JSON event patterns, IAM policy auditing, and AWS notification services.
