# 🔐 AWS Cloud Security Audit – Jupyter Notebook Project

This project is a **Jupyter-based security auditing tool** that uses Python and `boto3` to automatically scan your AWS account for misconfigurations, weak policies, and potential security risks.

---

## ✅ Features

This script performs the following **cloud security checks**:

### S3 Bucket Checks
- Detects all S3 buckets in your account
- Flags **publicly accessible** buckets
- Separates **private** vs **public** buckets

### EC2 Security Group Checks
- Audits all security groups
- Flags groups with **inbound rules open to the internet** (e.g., `0.0.0.0/0`, `::/0`)
- Classifies groups as **open** or **restricted**

### IAM Policy Checks
- Scans all IAM roles and attached policies
- Flags **over-permissive IAM policies** with `"Action": "*"` or `"Resource": "*"`

### Root Account Checks
- Detects if the **root user has been used recently**
- Checks whether **MFA is enabled** on the root account

---

## 📊 Output Summary Table

The tool displays a summary report with:

| Check                              | Description                                 |
|-----------------------------------|---------------------------------------------|
| Total S3 Buckets                  | All buckets in the account                  |
| Public/Private Buckets            | Based on ACL/public access                  |
| Open/Restricted Security Groups   | Based on CIDR range in inbound rules        |
| Over-Permissive IAM Policies      | `"*":"*"` privilege detection               |
| Root User Usage                   | Whether root access keys or use is detected |
| Root MFA Status                   | MFA enabled or not                          |

---

## 🚀 Getting Started

### 1. Set up environment
Install Python dependencies:

**pip install boto3 pandas**

### 2. Launch the Jupyter Notebook

**Optional: Use creation.ipynb to create s3 buckets and security groups.
Open main.ipynb and run all cells.**

## 🔐 Authentication
The notebook uses manual AWS credentials for easier setup in test environments.
At the top of the notebook, provide your credentials:

aws_access_key = 'YOUR_ACCESS_KEY'
aws_secret_key = 'YOUR_SECRET_KEY'
region = 'us-east-1'
⚠️ Do not commit credentials to GitHub!


## 💡 Why This Project?
This tool is great for:

1. Students learning AWS security

2. DevSecOps and Cloud Engineers doing audits

3. Showcasing real-world Python + AWS + cybersecurity skills
