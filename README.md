# 🚀 AWS 3-Tier Architecture using Terraform

![Architecture Diagram](./3_tier_architecture.png)

This project provisions a **highly available and scalable 3-tier architecture on AWS using Terraform**.
The infrastructure is designed using modular Terraform code and follows standard cloud architecture practices.

---

## 🧠 Architecture Overview

The system is divided into three layers:

* **Web Tier** – Handles incoming traffic
* **Application Tier** – Processes backend logic
* **Database Tier** – Stores application data

The setup is deployed across **multiple Availability Zones** to ensure high availability and fault tolerance.

---

## 🌐 Architecture Flow

User → Route 53 → Public Load Balancer → Web Tier → Application Tier → RDS Database

---

## ⚙️ AWS Services Provisioned

* Amazon VPC (Public & Private Subnets)
* Application Load Balancer (Public & Internal)
* Amazon EC2 (Web & Application servers)
* Auto Scaling Groups
* Amazon RDS (Multi-AZ)
* NAT Gateway
* Route 53
* ACM (SSL Certificates)
* Security Groups

---

## 📁 Project Structure

```
.
├── main.tf
├── README.md
├── 3_tier_architecture.png
├── .gitignore
├── modules/
│   ├── network/
│   ├── security/
│   ├── bastion/
│   ├── launch_templates/
│   ├── asg/
│   ├── load_balancers/
│   ├── rds/
│   ├── route53/
│   └── acm/
```

---

## ⚙️ Modules Overview

* **network** → VPC, subnets, routing
* **security** → Security groups and access rules
* **bastion** → Bastion host for SSH access
* **launch_templates** → EC2 launch templates
* **asg** → Auto Scaling Groups
* **load_balancers** → Public & internal ALBs
* **rds** → Database setup (Multi-AZ)
* **route53** → DNS configuration
* **acm** → SSL certificate setup

---

## 🚀 Deployment Steps

1. Initialize Terraform

```
terraform init
```

2. Validate configuration

```
terraform validate
```

3. Plan infrastructure

```
terraform plan
```

4. Apply configuration

```
terraform apply
```

---

## 🔐 Security Design

* Public subnets for Load Balancer and Bastion host
* Private subnets for Application and Database layers
* No direct internet access to backend resources
* Security groups control communication between layers
* NAT Gateway for secure outbound access

---

## 📊 Key Features

* Multi-AZ deployment for high availability
* Auto Scaling for dynamic workload handling
* Modular Terraform structure
* Load-balanced architecture
* Secure network design

---

## 📌 Notes

* Infrastructure is fully provisioned using Terraform
* Modular design improves reusability and maintainability
* Follows standard AWS architecture best practices

---
