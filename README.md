# aws-scalable-web-architecture
Scalable Web Application on AWS (EC2-Based)
1. Project Overview

This project designs a highly available, scalable, secure, and production-grade web application architecture on AWS using EC2 instances deployed in private subnets across multiple Availability Zones.

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


2. Solution Objectives
   

	. High availability across multiple AZs 
  . Horizontal scalability 
  . Secure private infrastructure 
  . Reduced latency using CDN caching 
  . Automated recovery and failover 
  . Monitoring and operational visibility 
  . Infrastructure ready for production workloads
     
3. High-Level Architecture
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

4. AWS Architecture Diagram
 
<img width="1620" height="971" alt="Diagram (2)" src="https://github.com/user-attachments/assets/5e63e009-2721-4485-9a28-2bea77ae2ea1" />
