# Scalable-Web-Application-Deployment-on-AWS

![image](https://github.com/user-attachments/assets/97207181-8f48-41ec-9fee-fb25ebadc11f)



Step 1: Create a VPC
Go to VPC Dashboard

Create a custom VPC

Add 2 subnets:

Public Subnet for web servers

Private Subnet for the database

Attach an Internet Gateway to the VPC

Add a Route Table and associate it with the public subnet

Step 2: Launch EC2 Instances
Go to EC2 Dashboard

Click Launch Template or Launch Instance

Choose an Amazon Linux AMI or Ubuntu

Add Web Server (Apache/Nginx) + App Code

Configure Security Group to allow:

Port 22 (SSH)

Port 80 (HTTP)

Port 443 (HTTPS)

Step 3: Create an Application Load Balancer
Go to EC2 > Load Balancers

Choose Application Load Balancer

Assign public subnets

Add listener on port 80 or 443

Create a Target Group

Register EC2 instances with the target group

Step 4: Set Up Auto Scaling
Go to Auto Scaling Groups

Create a new group linked to your EC2 launch template

Attach the Application Load Balancer

Define scaling policies (e.g., scale out at 70% CPU usage)

Set min, max, and desired number of instances

Step 5: Configure Amazon RDS
Go to RDS Dashboard

Create a new MySQL/PostgreSQL instance

Select Multi-AZ deployment for high availability

Place RDS in the private subnet

Allow EC2 access using Security Groups

Step 6: Store Static Files in S3 (Optional)
Go to S3

Create a bucket (e.g., myapp-static-files)

Upload static files (images, CSS, JS)

Enable static website hosting

(Optional) Attach CloudFront for CDN

Step 7: Monitor with CloudWatch
Go to CloudWatch Dashboard

Enable monitoring for EC2, RDS, and Load Balancer

Create Alarms (e.g., high CPU or low memory)

Enable log collection from EC2 instances

Step 8: Secure Your Application
Use AWS Certificate Manager (ACM) to create an SSL certificate

Attach it to the Load Balancer

Apply IAM Roles to EC2 for secure access to AWS services

Configure Security Groups and NACLs for network security
