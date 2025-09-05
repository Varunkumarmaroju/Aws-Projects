### IAM Project 2 – Access S3 from EC2 using IAM Role
Project Objective:-
The goal of this project is to understand how IAM Roles work in AWS and how they allow an EC2 instance to access S3 without using static IAM user keys.

Key learning points:
->Create an IAM role with S3 permissions.
->Attach the role to an EC2 instance.
->Access S3 buckets from the EC2 terminal using the role.
->Observe the effect of permissions (ReadOnly vs. FullAccess).

Screenshots & Steps
1️⃣ Role Creation
[Screenshot:](./Images/ss1.png)
Created a role named Role-task.
Trusted entity: EC2.
Purpose: To allow EC2 instances to access S3 using this role.

2️⃣ Role Permissions
[Screenshot:](./Images/ss2.png)
Attached AmazonS3ReadOnlyAccess policy.
This allows the EC2 instance to list buckets and read objects but cannot create or delete buckets/objects.

3️⃣ EC2 Instance Creation
[Screenshot:](./Images/ss3.png)
Launched an EC2 instance and attached Role-task under Advanced Details → IAM Role.
Verified IAM role in the console and terminal.

4️⃣ S3 Bucket Creation
[Screenshot:](./Images/ss4.png)
Created a bucket named buck-for-ec2-role in the S3 console.
Purpose: To test EC2 role access to S3.

5️⃣ Accessing S3 from EC2
[Screenshot:](./Images/ss5.png)
Connected to EC2 using EC2 Instance Connect.
Commands executed:
aws s3 ls
Output: Lists buck-for-ec2-role → confirms the EC2 instance can read S3 using the role.

Attempting to create a bucket:
aws s3 mb s3://aws-bck-rle
Result: AccessDenied → shows that the role has ReadOnly permissions, as expected.

Summary:-
Successfully created Role-task and attached it to an EC2 instance.
Verified EC2 can list existing S3 buckets.
Attempt to create a bucket failed → demonstrates role-based permissions in action.
This project highlights secure, keyless access for EC2 instances to AWS services.
