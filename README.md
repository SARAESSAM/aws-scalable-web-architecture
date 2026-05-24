# Scalable and Secure AWS Web Architecture


 - A highly available and scalable AWS architecture designed using core AWS networking, security, monitoring, and compute services.


   .  AWS Architecture Diagram

   .  Project Overview
   
   . AWS Services Used

   .  Architecture flow
   
1.  AWS Architecture Diagram

   <img width="1620" height="971" alt="Diagram (2)" src="https://github.com/user-attachments/assets/5e63e009-2721-4485-9a28-2bea77ae2ea1" />

2. Project Overview

     This project demonstrates the design of a scalable and secure web application architecture on AWS.

      The architecture follows AWS best practices for:
   
        - High Availability
        - Scalability
        - Security
        - Monitoring
        - Network Isolation

The solution distributes traffic through an Application Load Balancer and automatically scales EC2 instances across multiple Availability Zones.

3. AWS Services Used
   
     • VPC for Network Isolation
   
     • Public & Private Subnets for Secure workload segmentation
    
     •	Application Load Balancer (ALB) for traffic distribution
   
     •	Auto Scaling Group (ASG) for elasticity
      
     • Ec2 for Application Hosting ( Configure Launch Template)
    
     •	CloudFront CDN for caching and latency reduction
   
     •	RDS Multi-AZ for resilient database services.
   
     •	AWS WAF for application-layer protection.
   
     •	Systems Manager Session Manager for secure administration.
   
     •	CloudWatch + SNS for observability and alerting.
   
     • Nat Gateway for outbound Internat access for Web and DB servers.
   
     • IAM role for Access Managment instead of hardcoded credentials to allow EC2 access SSM and cloud watch.
   
   The design follows AWS Well-Architected Framework principles:

     . Operational Excellence 
     . Security 
     . Reliability 
     . Performance Efficiency 
     . Cost Optimization 
     
5. Architecture Flow
 
    1.	Users access application through: 
        o	Route 53 DNS, CloudFront CDN 
    2.	CloudFront forwards dynamic requests to: 
        o	AWS WAF 
        o	Application Load Balancer 
    3.	ALB distributes traffic to: 
        o	EC2 instances in private subnets 
    4.	EC2 instances communicate with: 
        o	RDS Multi-AZ Database 
    5.	EC2 outbound internet access uses: 
        o	NAT Gateway 
    6.	Monitoring and alerts handled by: 
      o	CloudWatch + SNS 
    7.	Administration handled securely through: 
      o	Systems Manager Session Manager
    8.  AWS WAF filters malicious requests

Summary of Flow

   - Users → Route 53 → CloudFront → AWS WAF → ALB → EC2 Auto Scaling (Multi-AZ Private Subnets) → Amazon RDS Multi-AZ
   - Internet Access → Internet Gateway → NAT Gateways → Private Subnets
   - Monitoring → CloudWatch → SNS Alerts
   - Operations → Systems Manager → IAM Roles
  
