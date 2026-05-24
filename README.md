# Scalable and Secure AWS Web Architecture
   .  Project Overview

   .  Solution Objectives

   .  High Level Architecture

   .  AWS Architecture Diagram

1. Project Overview

     - Designed highly available AWS architecture across multiple AZs
     - Implemented Auto Scaling for application resilience
     - Protected application using AWS WAF
     - Configured CloudWatch monitoring and logging
     - Used IAM roles with SSM Session Manager access
     - Designed secure network segmentation using public/private subnets


    The architecture uses:
     •	Application Load Balancer (ALB) for traffic distribution
   
     •	Auto Scaling Group (ASG) for elasticity
   
     •	CloudFront CDN for caching and latency reduction
   
     •	RDS Multi-AZ for resilient database services
   
     •	AWS WAF for application-layer protection
   
     •	Systems Manager Session Manager for secure administration
   
     •	CloudWatch + SNS for observability and alerting 

   The design follows AWS Well-Architected Framework principles:

     . Operational Excellence 
     . Security 
     . Reliability 
     . Performance Efficiency 
     . Cost Optimization 


3. Solution Objectives
   

	. High availability across multiple AZs 
  . Horizontal scalability 
  . Secure private infrastructure 
  . Reduced latency using CDN caching 
  . Automated recovery and failover 
  . Monitoring and operational visibility 
  . Infrastructure ready for production workloads
     
4. High-Level Architecture
   User Flow
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

5. AWS Architecture Diagram
   
   - Users → Route 53 → CloudFront → AWS WAF → ALB → EC2 Auto Scaling (Multi-AZ Private Subnets) → Amazon RDS Multi-AZ
   - Internet Access → Internet Gateway → NAT Gateways → Private Subnets
   - Monitoring → CloudWatch → SNS Alerts
   - Operations → Systems Manager → IAM Roles
   - Security → Security Groups
		
<img width="1620" height="971" alt="Diagram (2)" src="https://github.com/user-attachments/assets/5e63e009-2721-4485-9a28-2bea77ae2ea1" />
