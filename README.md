```
# 🛡️ AWS IAM Cloud Security &amp; ABAC Access Control

## 📌 Project Overview
This project demonstrates how to implement **Attribute-Based Access Control (ABAC)** and the **Principle of Least Privilege** using AWS IAM and Resource Tagging. As a Cloud/DevOps Engineer, I configured fine-grained security policies to grant a new intern full control over development resources while protecting critical production infrastructure from unauthorized actions.

---

## 🏛️ Architecture &amp; Key Components
* **Amazon EC2**: Deployed two virtual servers labeled with environment tags (`Env: development` and `Env: production`).
* **AWS IAM Policy**: Authored a custom JSON access policy utilizing conditional statements (`ec2:ResourceTag/Env`).
* **IAM User Group**: Created `nextwork-dev-group` to enable scalable, group-based permission management.
* **IAM User**: Onboarded `nextwork-dev-ibrahim-ahmed` and assigned them to the group.
* **AWS Account Alias**: Configured a customized sign-in URL for streamlined identity management.
* **IAM Policy Simulator**: Tested permission boundaries in a non-disruptive sandbox environment.

---

## ⚙️ Custom JSON Policy (`NextWorkDevEnvironmentPolicy`)

```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Action": "ec2:*",
            "Resource": "*",
            "Condition": {
                "StringEquals": {
                    "ec2:ResourceTag/Env": "development"
                }
            }
        },
        {
            "Effect": "Allow",
            "Action": "ec2:Describe*",
            "Resource": "*"
        },
        {
            "Effect": "Deny",
            "Action": [
                "ec2:DeleteTags",
                "ec2:CreateTags"
            ],
            "Resource": "*"
        }
    ]
}

```

---

## 🧪 Security Validation &amp; Testing

### 1\. Live Access Testing (Incognito Session)

* **Development Server (** **nextwork-dev** **)**: Successfully stopped the instance (`Stopping` state).
* **Production Server (** **nextwork-prod** **)**: Attempted to stop the instance ➡️ Triggered explicit **Access Denied** error.

### 2\. IAM Policy Simulator Evaluation

* Simulated `StopInstances` with condition `ec2:ResourceTag/Env = development` ➡️ **Allowed**.
* Simulated `DeleteTags` ➡️ **Denied** (enforcing tag preservation).

---

## 🧹 Resource Cleanup

To strictly follow AWS Free Tier &amp; Cloud Security best practices:

* Terminated both EC2 instances (`nextwork-dev` &amp; `nextwork-prod`).
* Cleaned up the test IAM User Group and IAM User.

- * ## 🎓 NextWork Verification
* **Project Badge/Certificate:** [https://nextwork.ai/hemaa/docs/51a5fd24-7458-58a6-8653-9b90119a0e4a)

