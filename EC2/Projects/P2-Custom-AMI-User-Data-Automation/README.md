📌 Project Overview :-

In this project, I created a Custom AMI (Amazon Machine Image) from a manually configured EC2 instance and then launched a new EC2 instance from that AMI using User Data automation.
This approach allows launching fully configured servers quickly and consistently, without repeating manual setup steps.

Steps Performed :-

1️⃣ Security Group Creation
Created a Security Group named varun-web-ec2
Added two inbound rules:
SSH (22) – Restricted to My IP
HTTP (80) – Open to 0.0.0.0/0
Purpose: To allow secure SSH access and allow public web traffic
📸  [Image1](Images/ss1.png): SG creation (SSH & HTTP rules)

2️⃣ Key Pair Creation
Created a key pair named pwrd
Key type: RSA
Downloaded the .pem file securely
📸  [Image2](Images/ss2.png): Key pair creation (pwrd)

3️⃣ Launching the Base EC2 Instance
Instance Name: Base-Instance
AMI: Amazon Linux 2
Type: t2.micro (Free Tier)
Attached SG: varun-web-ec2
Attached key: pwrd
Public IPv4 allocated
📸 [Image3](Images/ss3.png)t: Base-Instance created with Public IP

4️⃣ Installing Apache Web Server
Connected via SSH and executed:
sudo yum update -y
sudo yum install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
echo "<h1>Varun EC2 Base Server</h1>" | sudo tee /var/www/html/index.html
Verified that the webpage loaded successfully in browser
This is the final configuration we want inside the AMI
📸  [Image4](Images/ss4.png): Webpage loaded via Base-Instance Public IP

5️⃣ Creating a Custom AMI
Created AMI from Base-Instance
AMI Name: webserver-ami-v1
AWS captured the system state + Apache setup
📸  [Image5](Images/ss5.png): AMI creation screen (webserver-ami-v1)

6️⃣ Launching a New Instance from AMI
Instance Name: Test-Instance
Launched directly from webserver-ami-v1
Same Security Group & Key Pair reused
Added User Data for auto configuration:
#!/bin/bash
yum update -y
systemctl enable httpd
systemctl start httpd
echo "<h1>Varun EC2-p2: AMI + User Data Success!</h1>" > /var/www/html/index.html
📸  [Image6](Images/ss6.png): Test-Instance launched from AMI

7️⃣ Validating the New Instance
Opened Test-Instance’s Public IP in browser
Page loaded successfully with the automated User Data message
This confirms:
AMI creation successful
User Data executed correctly
Server auto-configured on first boot
📸 [Image7](Images/ss7.png): Test-Instance webpage loaded successfully

🎯 Key Learnings :-
How to configure a Linux EC2 from scratch
How to install and run Apache web server
Understanding inbound rules in Security Groups
Creating reusable Custom AMIs
Launching EC2 instances from AMI
Using User Data for automated provisioning
Real-world cloud engineer workflow for reproducible deployments

🧹 Cleanup Performed
To avoid unnecessary charges:
Terminated both EC2 instances
Deregistered AMI
Deleted associated snapshots
