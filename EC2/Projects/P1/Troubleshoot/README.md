
Troubleshooting – EC2 Project 1

This  covers common issues and solutions encountered while deploying an Apache web server on AWS EC2 

-> 1. Instance Won’t Start / Status Check Failed
Cause: Insufficient permissions, AMI issues, or exceeded free tier.
- **Solution:**  
  - Check instance type and ensure it’s within free tier limits.
  - Verify IAM role permissions.

->2. SSH Connection Fails
 Common Errors
  - Connection timed out 
  - Permission denied (publickey)
- **Solution:**  
  - Ensure Security Group allows inbound SSH (port 22) from your IP.
  - Confirm `.pem` key matches instance at launch.
  - Use:  
    ssh -i mykey.pem ec2-user@<public-ip>


-> 3. HTTP/HTTPS Page Not Loading
- **Cause:** Security Group rules missing for HTTP (port 80) or HTTPS (port 443).
- **Solution:**  
  - Edit inbound rules; allow HTTP/HTTPS from 0.0.0.0/0 (for demo), restrict in production.

-> 4. Apache Not Installed or Not Running
**Solution:**  
   Run installation commands:  
   
    sudo yum install httpd -y
    sudo systemctl start httpd
    sudo systemctl enable httpd
  
  Check Apache status:  
    
    sudo systemctl status httpd
    ```

-> 5. Public IP Changed After Restart
- **Cause:** EC2 public IP changes when re-stopped/started if not using Elastic IP.
- **Solution:**  
  - Check new public IP.
  - Update DNS mapping if you use it.


-> Tips
- Always download and keep your `.pem` key safe.
- Regularly check instance limits and billing in AWS Free Tier.
- For persistent IP, allocate an Elastic IP.
