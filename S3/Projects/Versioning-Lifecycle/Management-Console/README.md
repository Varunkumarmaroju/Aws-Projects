S3 Project-2: Versioning & Lifecycle 
Project Overview :-
This project demonstrates Amazon S3 Versioning and Lifecycle Management using the AWS Management Console.
We created a bucket, enabled versioning, uploaded files with multiple versions, configured lifecycle rules, and reviewed object versions in the browser.

Steps Performed:-
1. Create S3 Bucket
Open AWS Management Console → S3.
Create bucket with name s3-proj-2-ver.
Region: us-east-1.
Other settings left default.
📸 [Screenshot:](./Images/ss1.png)

2. Enable Versioning
Go to bucket → Properties tab.
Enable Bucket Versioning.
📸 [Screenshot:](./Images/ss2.png)


3. Upload Files & View Versions
Uploaded file: details.txt.
Re-uploaded with modifications → new versions created.
Turned on Show versions inside bucket.
📸[Screenshot:](./Images/ss3.png)


4. Check Object Versions in Browser
Accessed the file in browser to confirm multiple versions.
📸 [Screenshot:](./Images/ss4.png)


5. Create Lifecycle Rule
Navigate to Management tab → Lifecycle rules.
Created rule: Expire-old-versions.
📸 [Screenshot](./Images/ss5.png)

6. Configure Transitions & Expiration
Transition noncurrent versions to Standard-IA after X days.
Permanently delete noncurrent versions after Y days.
📸 [Screenshot:](./Images/ss6.png)

✅ Key Learnings:-
Versioning keeps multiple object versions safe.
Lifecycle rules automate cost optimization & cleanup.
Buckets must be emptied (all versions) before deletion.
