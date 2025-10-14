# AWS IAM Project – S3 Access Guard

## Project Objective :-
To create a custom IAM policy that allows an IAM user to **list and view S3 buckets**, but **restricts uploading and deleting** files or buckets.

## IAM Setup Overview
Main Admin User: varun-admin  
New IAM User Created : s3-limited-user

varun-admin created a new IAM user with limited access permissions using a custom S3 policy.

## Step-by-Step Implementation
### **Step 1: Create IAM User**
Created a new IAM user named **`s3-limited-user`** from the `varun-admin` account.  
[Screenshot-1](./Images/ss1.png) :-** IAM user creation screen showing `s3-limited-user`.

### **Step 2: Create Custom IAM Policy**
A custom policy was created in the **IAM Policy Console** to deny delete/upload and allow list/view.
  --json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": [
        "s3:DeleteBucket",
        "s3:PutObject"
      ],
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:ListAllMyBuckets",
        "s3:ListBucket",
        "s3:GetObject"
      ],
      "Resource": "*"
    }
  ]
}
[Screenshot-2](./Images/ss2.png): Policy JSON editor screen.

Step 3: Attach Policy to User
The newly created policy S3-ListOnly-NoUploadDelete was attached directly to the s3-limited-user.

[Screenshot-3](./Images/ss3.png) Attaching policy to user.
[Screenshot-3](./Images/ss4.png) Policy successfully attached (visible under user permissions).

Step 4: Log in as Limited User
Logged into the AWS Management Console using s3-limited-user credentials.
[Screenshot-5](./Images/ss5.png) Console home page showing s3-limited-user login.

Step 5: Validate Permissions
✅ Able to list and view all S3 buckets.
[Screenshot-6](./Images/ss6.png) S3 buckets listed successfully.

❌ Access denied when deleting a bucket.
[Screenshot-7](./Images/ss7.png) “Access Denied” message during bucket deletion.

❌ Access denied when uploading a file.
[Screenshot-8](./Images/ss8.png) “Access Denied” message during upload attempt.
