# 🚀 EC2-Apache-WebServer Deployment Project

This project demonstrates how to deploy a static website hosted on an Apache Web Server using an Amazon EC2 instance. The source code for the website is pulled directly from this GitHub repository.

##  Tech Stack

- Amazon EC2  
- Apache HTTP Server  
- GitHub  
- Amazon Linux 2

  
## 02. Network Architecture

![VPC Network Diagram](Architecture.png)

---

##  Steps to Reproduce

1.  **Launch EC2**:
       -Amazon Linux 2, t2.micro (Free Tier), open ports 22 & 80.
   
3.  **Connect to Your EC2 Instance**
       -ssh -i "My_Key_Pair_2.pem" ec2-user@ec2-15-206-174-242.ap-south-1.compute.amazonaws.com

4.  **Update Packages and Install Apache & Git**
       -sudo yum update -y
       -sudo yum install -y httpd git

5.  **Start Apache and Enable it to Run on Boot**
       -sudo systemctl start httpd
       -sudo systemctl enable httpd

6.  **Pull Your Website from GitHub**
       -git clone https://github.com/your-username/your-repo-name.git

7.  **Move Your Website Files to Apache Web Directory**
      -sudo mv your-repo-name/* /var/www/html/
      -sudo mv your-repo-name/.* /var/www/html/ 2>/dev/null         # move hidden files like .htaccess

8.  **Optional cleanup**
       -rm -rf your-repo-name

9.  **Set Correct Permissions (Optional but Recommended)**
       -sudo chown -R apache:apache /var/www/html
       -sudo chmod -R 755 /var/www/html

10. **Restart Apache**
     -sudo systemctl restart httpd

---

## Output

1. **Access site**: //http://15.206.174.242/>

---

##  Files
- Architecture.png
- index.html  
- README.md

---
