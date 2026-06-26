# ❗ Errors Encountered & Solutions

During this project, I encountered several real-world Terraform and AWS issues. Below are the errors and how I resolved them.

---

<img width="1366" height="768" alt="image" src="https://github.com/user-attachments/assets/7040e691-f9d6-494a-8835-4614cbd27377" />


## Error 1: No Subnets Found for Default VPC

### Error Message

```
Error: creating EC2 Instance

MissingInput: No subnets found for the default VPC.
Please specify a subnet.
```

### Cause

The AWS account did not have a usable subnet in the default VPC.

### Solution

- Created a new VPC using **VPC and More**
- Created public subnets
- Added the subnet ID in `terraform.tfvars`

```hcl
subnet_id = "subnet-xxxxxxxxxxxxxxxxx"
```

### Screenshot

![No Subnet Error](screenshots/no-subnet-error.png)

---

## Error 2: InvalidSubnetID.NotFound

### Error Message

```
InvalidSubnetID.NotFound:
The subnet ID does not exist.
```

### Cause

A wrong subnet ID was configured in `terraform.tfvars`.

### Solution

Verified available subnets:

```bash
aws ec2 describe-subnets --output table
```

Updated:

```hcl
subnet_id = "subnet-0a6da9abe43539db8"
```

### Screenshot

![Invalid Subnet](screenshots/invalid-subnet-error.png)

---

## Error 3: Terraform Validation

### Command

```bash
terraform validate
```

### Output

```
Success! The configuration is valid.
```

### Screenshot

![Terraform Validate](screenshots/terraform-validate.png)

---

## Error 4: Terraform Plan

### Command

```bash
terraform plan
```

### Output

```
Plan: 2 to add, 0 to change, 0 to destroy.
```

### Screenshot

![Terraform Plan](screenshots/terraform-plan.png)

---

## Error 5: Terraform Apply

### Command

```bash
terraform apply
```

### Output

```
Apply complete!
Resources: 2 added.
```

### Screenshot

![Terraform Apply](screenshots/terraform-apply.png)

---

## Error 6: EC2 Instances Created

### Verification

AWS Console → EC2

Successfully created multiple EC2 instances using Terraform.

### Screenshot

![EC2 Instances](screenshots/ec2-created.png)

---

# Troubleshooting Commands

Useful commands used while debugging:

```bash
aws sts get-caller-identity

aws ec2 describe-subnets --output table

terraform validate

terraform plan

terraform apply

terraform destroy

terraform output

terraform fmt
```

---

# Lessons Learned

- Always verify the AWS region.
- Verify the subnet ID before creating EC2 instances.
- Never hardcode invalid resource IDs.
- Use `terraform validate` before `terraform apply`.
- Use `.gitignore` to protect state files and credentials.
- Follow Infrastructure as Code (IaC) best practices.
