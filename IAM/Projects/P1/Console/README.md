📘 IAM Project 1 – Restricting Access with IAM Groups & Users

Project Objective:-
The goal of this project is to understand how IAM Groups, Users, and Policies work in AWS.
We will create a group with S3 permissions only, add a user to it, and then test access restrictions.

🛠 Steps Performed:-
1️⃣ Create IAM Group – S3ADMINS
Created a new IAM Group named S3ADMINS.
Attached the AmazonS3FullAccess policy to the group.
📸 [Screenshot](./Images/ss1.png)

2️⃣ Create IAM User – s3-user
Created a new IAM User named s3-user.
Added s3-user to the S3ADMINS group.
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/IAM%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-29%20183339.png)

3️⃣ Verify User Creation
Confirmed that s3-user was successfully created and assigned to the S3ADMINS group.
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/IAM%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-29%20183502.png)

4️⃣ Login as s3-user
Logged into the AWS Console as the s3-user.
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/IAM%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-29%20183720.png)

5️⃣ Test Access Restriction (EC2)
Tried to launch an EC2 instance using s3-user.
Access was denied (as expected) because s3-user only has S3 permissions.
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/IAM%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-29%20183844.png)

6️⃣ Test S3 Access
Created an S3 bucket successfully using s3-user.
This confirms that permissions were applied correctly.
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/IAM%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-29%20184024.png)


✅ Learning Outcome
IAM Groups help centralize permissions for multiple users.
The s3-user could access only S3 services but was restricted from EC2.
This demonstrates least privilege principle in IAM.

 Project Completed Successfully!
