# lab-ansible-aws-config-mgmt
Ansible on AWS lab: Terraform EC2 provisioning + Ansible configuration management (transferable to Puppet/Chef)
Terraform + AWS S3 Lab: Secure Bucket Provisioning with Versioning and Lifecycle Management
📌 Aim & Objectives
The aim of this lab was to design, implement, and validate an AWS S3 bucket infrastructure using Terraform, focusing on security best practices and lifecycle management.

Objectives:
- Automate provisioning of an S3 bucket with Terraform.
- Enforce bucket ownership controls and block all public access.
- Enable bucket versioning for recovery and resilience.
- Apply lifecycle management policies (automatic expiration of non-current versions).
- Document the process step-by-step with screenshots (46 images total).
📌 Scope
- Infrastructure as Code (IaC) using Terraform.
- AWS S3 bucket creation in eu-west-1 (Ireland) region.
- Focus on security, cost optimization, and lifecycle management.
- Repository includes all Terraform configuration files (main.tf, providers.tf, variables.tf) and 46 supporting screenshots for evidence.
📌 Methodology & Approach
1. Terraform Setup
   - Installed Terraform CLI.
   - Configured providers and variables.

2. Code Structure
   - main.tf: Resources (S3 bucket, access block, ownership, versioning, lifecycle).
   - providers.tf: AWS provider configuration.
   - variables.tf: Variable declarations.

3. Execution Strategy
   - Initialized backend (terraform init).
   - Validated code (terraform validate).
   - Previewed execution plan (terraform plan).
   - Applied changes (terraform apply).

4. Verification
   - Checked bucket creation in AWS Management Console.
   - Confirmed block public access, ownership control, versioning, and lifecycle policies were enabled.
📌 Challenges Encountered
- File path errors when creating .tf files inside C:\Windows\System32. Resolved by creating a dedicated working directory in C:\Users\IME-PC\terraform-lab.
- File extensions issue (.tf.txt instead of .tf). Fixed by renaming files properly.
- Lifecycle policy warnings (missing prefix/filter). Adjusted Terraform config for compliance.
- Multiple re-initializations due to misplacement of files.
📌 Limitations
- Lab used a single AWS region (eu-west-1); multi-region replication not tested.
- Only basic lifecycle rules were applied (non-current version expiration after 30 days).
- Did not integrate with CloudFront, Lambda, or EventBridge.
📌 Must-Do Best Practices (Learned)
- Always create a dedicated project folder for Terraform instead of using System32.
- Double-check file extensions before running Terraform commands.
- Use terraform fmt to maintain consistent formatting.
- Validate (terraform validate) before applying changes.
- Capture and document outputs (terraform show, terraform state list).
📌 Importance & Significance
- Client Perspective: Ensures data stored in S3 is secure, resilient, and cost-efficient.
- Cloud Engineer Perspective: Demonstrates ability to apply AWS security best practices using IaC.
- Enterprise Value: Automating S3 infrastructure with Terraform reduces human error, enforces compliance, and provides a repeatable blueprint for future deployments.
📌 Adoption & Implementation Strategy
- Can be adopted by enterprises migrating workloads to AWS for secure storage.
- Lifecycle rules reduce storage costs by automatically expiring old object versions.
- Public access block and ownership controls ensure compliance with data protection standards (GDPR, HIPAA, SOC2).
- Scales easily: the same configuration can be extended to multiple environments (dev, test, prod) using workspaces and modules.
📌 Why This Lab Matters for AWS Cloud Solutions
This lab directly solves real client needs:
- Prevents data leaks by enforcing strict access policies.
- Ensures business continuity through versioning and recovery.
- Reduces operational costs with lifecycle management.
- Demonstrates Infrastructure as Code (IaC) as a core AWS competency.
📸 Screenshots (46 Total)
All screenshots are stored in the screenshots/ directory.
Some key highlights:
1. Terraform file creation (main.tf, providers.tf, variables.tf)
2. Initialization and validation (terraform init, terraform validate)
3. Execution plan (terraform plan)
4. Apply results (terraform apply)
5. AWS Console verification (S3 bucket created, settings applied)
6. Final success screenshot → terraform-lab-s3-bucket-versioning-lifecycle-success.png
📂 Repository Structure
terraform-lab/
│── main.tf
│── providers.tf
│── variables.tf
│── README.md
│── LICENSE
│── .gitignore
│── screenshots/
│    ├── step1-init.png
│    ├── step2-validate.png
│    ├── step3-plan.png
│    ├── step4-apply.png
│    └── terraform-lab-s3-bucket-versioning-lifecycle-success.png
