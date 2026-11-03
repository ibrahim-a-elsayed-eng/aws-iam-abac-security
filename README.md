# 🛡️ AWS Cloud Security with IAM: Managing Access and Least Privilege

## 🚀 What I Built and What It Does
I spent over 3 hours of hands-on work managing access and security in AWS using Identity and Access Management (IAM). I built a custom IAM policy, set up an AWS account alias for a custom sign-in URL, created an IAM user group, added an IAM user, and tested access rules using the IAM Policy Simulator.

## 🛠️ Tech Stack
- **AWS IAM:** Used for managing users, groups, permissions, custom policies, account aliases, and secure access control.
- **Amazon EC2:** Used for launching instances, managing compute capacity, and testing policy tags and permission rules.

## ✨ Project Highlights
- Completed a knowledge check quiz on EC2 instances, IAM policies, account aliases, users, and groups.
- Switched to the Ohio (`us-east-2`) region and navigated to the EC2 service.
- Entered a custom JSON policy defining allow and deny statements for EC2 actions based on resource tags (`NextWorkDevEnvironmentPolicy`).
- Created an AWS account alias (`nextwork-alias-ibrahim`) to generate a custom sign-in URL.
- Created an IAM user group and assigned the custom `NextWorkDevEnvironmentPolicy` to the group.
- Created the IAM user `nextwork-dev-ibrahim-ahmed`, downloaded credentials, and tested access using the **IAM Policy Simulator** to verify `Allowed` and `Denied` states with resource tags (`Env = development`).

## 🧩 The Hardest Problem I Solved
When I created a new IAM user to test custom permissions, the initial creation failed due to an invalid user name containing a space. I identified the error from the system output stating that the specified value for `userName` was invalid (must contain only alphanumeric characters and allowed special symbols). I fixed this by editing the user name to replace the space with a hyphen, which resolved the error and allowed me to complete user creation and save credentials successfully.

## 🎯 Skills Showed
- **IAM Policy Configuration:** Wrote and applied custom JSON policies with allow and deny rules for EC2 resource tags.
- **Access Management:** Created IAM user groups and assigned specific managed policies for efficient permission control.
- **AWS Account Customization:** Generated a custom account alias to provide a user-friendly console sign-in URL.
- **User Troubleshooting:** Fixed invalid user name formatting errors during IAM user creation to successfully generate console access and credentials.

- * ## 🎓 NextWork Verification
* **Project Badge/Certificate:** [https://nextwork.ai/hemaa/docs/51a5fd24-7458-58a6-8653-9b90119a0e4a)

