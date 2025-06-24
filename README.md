# InsightIQ-Analytics-Platform-AWS-EC2-Deployment
InsightIQ Analytics is a modern, responsive analytics platform website built with HTML5, CSS3, and JavaScript. The project demonstrates deploying a web application on AWS EC2 Free Tier using Apache Web Server, showcasing cloud hosting, Linux server management, and web development skills.


🛠️ Technologies Used
Amazon EC2 (AWS Free Tier) – Cloud compute instance for hosting
Amazon Linux 2 – Operating system for the instance
Apache HTTP Server – Web server for serving static content
HTML5, CSS3, JavaScript – Frontend website technologies
SSH – Secure connection to EC2 instance

📋 Steps to Deploy the Website
1. Launch EC2 Instance

Log in to AWS Management Console.
Navigate to EC2 service and launch a new instance.
Choose Amazon Linux 2 AMI (Free Tier eligible).
Select t2.micro instance type.
Configure security group to allow:
SSH (port 22) from your IP
HTTP (port 80) from anywhere (0.0.0.0/0)
Launch instance with a new or existing key pair.

2. Connect to EC2 via SSH

bash
ssh -i /path/to/your-key.pem ec2-user@<EC2-Public-IP>
(Replace /path/to/your-key.pem and <EC2-Public-IP> with your actual key and instance IP).

3. Install Apache Web Server

bash
sudo yum update -y
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl enable httpd

4. Deploy the Website

Copy your single-file website (e.g., index.html) to the Apache web root:

bash
sudo mv index.html /var/www/html/
Set permissions if needed:

bash
sudo chmod 644 /var/www/html/index.html

5. Test Your Deployment

Open a browser and navigate to http://<EC2-Public-IP> to view your website.

📈 Key Features
Responsive Design: Adapts to desktop and mobile screens
Interactive UI: FAQ accordion, smooth navigation, contact form feedback
Single-File Deployment: Easy to manage and portable
Secure Cloud Hosting: Hosted on AWS with firewall and SSH access

💡 Best Practices & Tips
Always update your server before installing new packages.
Use security groups to restrict access to only necessary ports.
Regularly backup your website files.
Monitor your EC2 instance usage to stay within Free Tier limits.
