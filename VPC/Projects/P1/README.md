### Project 1: Launch EC2 Instance in a Custom VPC

### Result:-
In this project, we create a custom VPC, attach an Internet Gateway, configure a Route Table, and launch an EC2 instance inside it.
Finally, we install Apache and host a simple webpage to confirm the setup.

🛠 Steps Performed

1️⃣ Create a Custom VPC
Created a VPC with CIDR block 10.0.0.0/16.
📸 [Screenshot:](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/VPC%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-25%20220707.png)

2️⃣ Create Subnet
Created a public subnet with CIDR 10.0.1.0/24.
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/VPC%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-25%20220726.png)


3️⃣ Create & Attach Internet Gateway
Created an Internet Gateway (IGW).
Attached it to the custom VPC.
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/VPC%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-25%20220743.png)

4️⃣ Configure Route Table
Edited the route table of VPC to allow internet access.
Added route: 0.0.0.0/0 → Internet Gateway.
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/VPC%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-25%20220807.png)

5️⃣ Launch EC2 Instance in Custom VPC
Selected the custom VPC and public subnet while launching.
Created a Security Group allowing SSH (22) and HTTP (80).
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/VPC%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-25%20220956.png)
📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/VPC%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-25%20221027.png)

6️⃣ Connect to EC2 via SSH
ssh -i key.pem ec2-user@<Public-IP>


7️⃣ Install & Start Apache Web Server

sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd

9️⃣ Host Custom Webpage

echo "<h1>EC2 instance from custom VPC</h1>" | sudo tee /var/www/html/index.html

📸 [Screenshot](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/VPC%2FProjects%2FP1%2FImages%2FScreenshot%202025-08-25%20221042.png)

### Output:-
EC2 instance is successfully running in custom VPC.
Custom webpage is accessible from the browser.

