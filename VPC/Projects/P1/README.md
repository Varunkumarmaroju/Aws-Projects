### Project 1: Launch EC2 Instance in a Custom VPC

### Result:-
In this project, we create a custom VPC, attach an Internet Gateway, configure a Route Table, and launch an EC2 instance inside it.
Finally, we install Apache and host a simple webpage to confirm the setup.

🛠 Steps Performed

1️⃣ Create a Custom VPC
Created a VPC with CIDR block 10.0.0.0/16.
📸 Screenshot:

2️⃣ Create Subnet
Created a public subnet with CIDR 10.0.1.0/24.
📸 Screenshot:


3️⃣ Create & Attach Internet Gateway
Created an Internet Gateway (IGW).
Attached it to the custom VPC.
📸 Screenshot:

4️⃣ Configure Route Table
Edited the route table of VPC to allow internet access.
Added route: 0.0.0.0/0 → Internet Gateway.
📸 Screenshot:

5️⃣ Launch EC2 Instance in Custom VPC
Selected the custom VPC and public subnet while launching.
Created a Security Group allowing SSH (22) and HTTP (80).
📸 Screenshot:

6️⃣ Connect to EC2 via SSH
ssh -i key.pem ec2-user@<Public-IP>
📸 Screenshot:

7️⃣ Install & Start Apache Web Server

sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd

9️⃣ Host Custom Webpage

echo "<h1>EC2 instance from custom VPC</h1>" | sudo tee /var/www/html/index.html

📸 Screenshot:

### Output:-
EC2 instance is successfully running in custom VPC.
Custom webpage is accessible from the browser.

