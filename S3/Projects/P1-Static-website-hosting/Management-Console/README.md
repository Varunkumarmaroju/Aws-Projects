
# Project 1: Static Website Hosting on S3 
This project demonstrates how to host a simple static website on **Amazon S3** using **bucket ACLs** to make it publicly accessible.

##  Steps Performed

### 1️⃣ Create an S3 Bucket
- Open the **AWS Management Console** → S3 service.  
- Click **Create bucket** and give it a unique name (example: `my-static-site-p1`).  
- Select your region and keep other settings default.  
- ✅ Uncheck **Block all public access** (since we are using ACL for public access).  
👉 [Screenshot 1](./Images/ss1.png)

### 2️⃣ Upload Website Files
- Open your bucket.  
- Click **Upload** → Add files (HTML, CSS, JS, images).  
- Click **Upload** to store them in the bucket.  


### 3️⃣ Make Files Public (ACL)
- Select the uploaded files.  
- Go to **Actions → Make public using ACL**.  
- Confirm to make the objects accessible.  


### 4️⃣ Enable Static Website Hosting
- Go to **Bucket Properties** → **Static website hosting**.  
- Choose **Use this bucket to host a website**.  
- Set **index.html** as the index document.  
- Copy the **Bucket Website Endpoint** → Open in your browser. 🎉  
 👉 [Screenshot 3](./Images/ss2.png)


##  Final Output
- Your static website is now hosted on **S3** using public ACLs.  
- Accessible via the **Website Endpoint URL**.
- 👉 [Screenshot 4](./Images/ss3.png)
