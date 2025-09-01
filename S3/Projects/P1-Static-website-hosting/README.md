
# Project 1: Static Website Hosting on S3 
This project demonstrates how to host a simple static website on **Amazon S3** using **bucket ACLs** to make it publicly accessible.

##  Steps Performed

### 1️⃣ Create an S3 Bucket
- Open the **AWS Management Console** → S3 service.  
- Click **Create bucket** and give it a unique name (example: `my-static-site-p1`).  
- Select your region and keep other settings default.  
- ✅ Uncheck **Block all public access** (since we are using ACL for public access).  

👉 [Screenshot 1](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/S3/Projects/P1/Images/Screenshot%202025-08-25%20010307.png)

### 2️⃣ Upload Website Files
- Open your bucket.  
- Click **Upload** → Add files (HTML, CSS, JS, images).  
- Click **Upload** to store them in the bucket.  

👉 [Screenshot 2](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/S3/Projects/P1/Images/Screenshot%202025-08-25%20010330.png)

### 3️⃣ Make Files Public (ACL)
- Select the uploaded files.  
- Go to **Actions → Make public using ACL**.  
- Confirm to make the objects accessible.  

👉 [Screenshot 3](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/S3/Projects/P1/Images/Screenshot%202025-08-25%20010351.png)

### 4️⃣ Enable Static Website Hosting
- Go to **Bucket Properties** → **Static website hosting**.  
- Choose **Use this bucket to host a website**.  
- Set **index.html** as the index document.  
- Copy the **Bucket Website Endpoint** → Open in your browser. 🎉  

👉 [Screenshot 4](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/S3/Projects/P1/Images/Screenshot%202025-08-25%20010425.png)

##  Final Output
- Your static website is now hosted on **S3** using public ACLs.  
- Accessible via the **Website Endpoint URL**.  
