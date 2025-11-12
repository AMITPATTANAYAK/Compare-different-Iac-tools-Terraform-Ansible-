# 🌩️ Infrastructure as Code (IaC) Validation  
### *Comparison of Terraform and Ansible for Automated VM Provisioning on AWS Free Tier*

---

## 📘 Overview

This project explores **Infrastructure as Code (IaC)** — a core DevOps practice that automates infrastructure provisioning and management using code rather than manual configuration.  
It compares two leading IaC tools, **Terraform** and **Ansible**, to evaluate their performance in **automating the creation and configuration of virtual machines (VMs) on AWS Free Tier**.

By combining Terraform’s **declarative provisioning** with Ansible’s **configuration automation**, this project demonstrates an efficient, scalable, and repeatable DevOps workflow.

---

## 🎯 Objectives

- Understand the concept and workflow of **Infrastructure as Code (IaC)**.  
- Automate cloud infrastructure provisioning using **Terraform** and **Ansible**.  
- Compare both tools based on **deployment time**, **ease of configuration**, and **success rate**.  
- Validate the effectiveness of IaC in achieving **automated, consistent, and repeatable deployments**.

---

## 🧰 Tools and Technologies Used

| Category | Tool / Technology | Description |
|-----------|-------------------|--------------|
| IaC Tool 1 | **Terraform** | Declarative infrastructure provisioning tool. |
| IaC Tool 2 | **Ansible** | Configuration management and automation tool. |
| Cloud Platform | **AWS Free Tier** | Used to host and test infrastructure deployments. |
| Languages | **HCL**, **YAML** | For writing IaC scripts and playbooks. |
| OS Environment | **Ubuntu / Windows (WSL)** | Local testing and development. |
| Additional Tools | **AWS CLI**, **SSH** | For authentication and connectivity. |

---

## ⚙️ Methodology

### 1. **Setup and Workflow**

A typical pattern is:
1. Use **Terraform** to create base infrastructure (EC2 instances, networking, etc.).
2. Use **Ansible** to configure those instances (install packages, manage services, deploy apps).

This project provisions multiple EC2 instances using Terraform, retrieves their IPs, and then configures them with Ansible using a dynamic inventory.

### 2. **Workflow Summary**
```bash
# Step 1: Initialize and Apply Terraform Configuration
terraform init
terraform apply -auto-approve

# Step 2: Generate Dynamic Inventory for Ansible
terraform output > inventory.ini

# Step 3: Run Ansible Playbook
ansible-playbook -i inventory.ini playbook.yml
