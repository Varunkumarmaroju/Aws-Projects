 EC2 Project – Deploy a Web Server (Free Tier)

 Objective :- Launch an EC2 instance, configure security, install Apache, and serve a sample web page.

Result:- Public web server running on EC2 (t2.micro, Free Tier), reachable over HTTP.

 Architecture
**EC2**: Amazon Linux 2, t2.micro
 **Security Group**: SSH (22) from your IP, HTTP (80) from Anywhere
 **Storage**: 8–10 GB GP2
 **Key Pair**: RSA, .pem file

 Steps Performed

1. **Launch instance** (Amazon Linux 2, t2.micro).  
   Step 1 - Launch Instance

   [Screenshot1](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/EC2%2FProjects%2FP1%2Fimages%2Fss2.png)

2. **Configure Security Group**  
   Inbound: SSH 22 (My IP), HTTP 80 (0.0.0.0/0).  
   Step 2 - Security Group

    [Screenshot2](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/EC2%2FProjects%2FP1%2Fimages%2Fss3.png)

4. **Connect via SSH
    ssh -i mykey.pem ec2-user@<52.91.214.224>

5. **Install Apache web server**
   sudo yum install httpd -y
   sudo systemctl start httpd
   sudo systemctl enable httpd


6. **Upload website content**

7. **Access the website via public IP**  
Step 3 - Website Running

     [Screenshot3](https://github.com/Varunkumarmaroju/Aws-Projects/raw/main/EC2%2FProjects%2FP1%2Fimages%2Fss1.png)


  Verification  
- EC2 instance running status verified on AWS Console.
- Web page output verified by accessing public IPv4 address in browser.




