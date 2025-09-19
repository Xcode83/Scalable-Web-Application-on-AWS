# Scalable-Web-Application-on-AWS

This project demonstrates how to deploy a highly available and scalable web application using AWS EC2 Auto Scaling, Application Load Balancer, and CloudWatch Monitoring.

It ensures that the application can handle traffic spikes by automatically scaling instances based on CPU utilization, while CloudWatch provides monitoring and alerting.

📌 Architecture Overview

EC2 Auto Scaling Group (ASG) → Automatically adjusts the number of instances.

Application Load Balancer (ALB) → Distributes traffic evenly across instances.

Launch Template → Defines how new EC2 instances are created.

CloudWatch Monitoring → Tracks CPU utilization and triggers alarms.

SNS Notifications (optional) → Sends email alerts when alarms are triggered.

⚙️ Steps Implemented
1️⃣ Prepare EC2 Instance

Installed Apache Web Server.

Configured a basic HTML page displaying server details.

Created an AMI from this instance for Auto Scaling.

2️⃣ Launch Template

Defined instance type, key pair, and security groups.

Used the custom AMI for uniform instance setup.

3️⃣ Target Group

Created to allow ALB to route traffic to healthy instances.

4️⃣ Application Load Balancer (ALB)

Configured as Internet-facing.

Linked to target group for traffic distribution.

5️⃣ Auto Scaling Group (ASG)

Desired: 2 | Min: 1 | Max: 3.

Scaling Policy: Target Tracking → CPU Utilization at 50%.

6️⃣ CloudWatch Alarms

Set CPU utilization threshold (>70%).

Triggered scaling actions and optional SNS notifications.

🖥️ Testing

Generated load using stress tool.

Observed Auto Scaling automatically launch new EC2 instances.

Verified traffic distribution via ALB DNS name.

CloudWatch alarms triggered & notifications sent.

📷 Project Workflow

Deploy EC2 instance → Configure Web Server → Create AMI.

Launch Template → Auto Scaling Group → Application Load Balancer.

Attach CloudWatch Monitoring & Alarms.

Test scaling by simulating high CPU load.

🛠️ Tools & Services Used

Amazon EC2 – Compute service.

Amazon EC2 Auto Scaling – Automatic scaling of instances.

Elastic Load Balancing (ALB) – Distributes incoming traffic.

Amazon CloudWatch – Monitoring & alarms.

Amazon SNS (optional) – Notifications.

Apache Web Server – Hosting simple web app.
