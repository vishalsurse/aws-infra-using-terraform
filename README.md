# aws-infra-using-terraform
In aws ec2 creating multiple instance using terafform  
# 🚀 Terraform AWS EC2 Project

This project demonstrates how to provision multiple Amazon EC2 instances on AWS using Terraform Infrastructure as Code (IaC).

## 📌 Project Overview

This project creates:

- Multiple EC2 Instances
- AWS Infrastructure using Terraform
- Configurable variables
- Output values for Instance IDs and Public IPs

---

## 🛠️ Technologies Used

- Terraform
- AWS EC2
- Amazon Linux 2023
- AWS CLI
- Git & GitHub

---

## 📂 Project Structure

```
terraform-project/
│── main.tf
│── variables.tf
│── terraform.tfvars
│── outputs.tf
│── .gitignore
└── README.md
```

---

## 📋 Prerequisites

Before running this project, make sure you have:

- AWS Account
- IAM User with EC2 permissions
- AWS CLI installed
- Terraform installed
- Git installed

Verify installations:

```bash
terraform version
aws --version
git --version
```

---

## ⚙️ Configure AWS CLI

```bash
aws configure
```

Provide:

```
AWS Access Key ID
AWS Secret Access Key
Region: ap-south-1
Output: json
```

Verify:

```bash
aws sts get-caller-identity
```

---

## 🚀 Initialize Terraform

```bash
terraform init
```

---

## ✅ Validate Configuration

```bash
terraform validate
```

---

## 📄 Format Terraform Files

```bash
terraform fmt
```

---

## 📋 View Execution Plan

```bash
terraform plan
```

---

## ☁️ Create EC2 Instances

```bash
terraform apply
```

Type:

```
yes
```

---

## 📤 View Outputs

```bash
terraform output
```

Example:

```
instance_ids
public_ips
```

---

## 🗑️ Destroy Infrastructure

```bash
terraform destroy
```

Type:

```
yes
```

---

## 📁 Files Description

| File | Purpose |
|------|---------|
| main.tf | Creates EC2 instances |
| variables.tf | Input variables |
| terraform.tfvars | Variable values |
| outputs.tf | Displays instance IDs and public IPs |
| README.md | Project documentation |

---

## 🔒 Best Practices

- Never upload `.tfstate` files to GitHub.
- Never upload `.pem` key files.
- Never upload AWS credentials.
- Use `.gitignore` to exclude sensitive files.

Example `.gitignore`

```
.terraform/
*.tfstate
*.tfstate.*
terraform.tfvars
*.pem
```

---

## 📸 Project Output

After successful execution, Terraform creates multiple EC2 instances.

Example:

```
Terraform-EC2-1
Terraform-EC2-2
```

Outputs:

```
Instance IDs
Public IP Addresses
```

---

## 📚 Useful Terraform Commands

```bash
terraform init
terraform validate
terraform fmt
terraform plan
terraform apply
terraform output
terraform destroy
```

---

## 👨‍💻 Author

**Vishal Surse**

AWS Cloud & DevOps Engineer

- AWS Solution Architect Associate Certified
- Learning Terraform, Docker, Jenkins, Kubernetes, and CI/CD

GitHub:
https://github.com/vishalsurse

---

## ⭐ If you found this project useful, don't forget to star the repository.
