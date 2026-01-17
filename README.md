# Azure IAM & RBAC Lab (Microsoft Entra ID)

This project demonstrates a real-world implementation of **Identity and Access Management (IAM)** using **Microsoft Entra ID (Azure Active Directory)** and **Azure Role-Based Access Control (RBAC)**.

The lab focuses on **secure access design**, **least privilege principles**, **group-based role assignments**, **Multi-Factor Authentication (MFA)**, and **audit & sign-in monitoring**, all implemented using the **Azure Free Tier**.

---

## Project Objectives

- Implement centralized identity management using Microsoft Entra ID
- Enforce least-privilege access using Azure RBAC
- Assign permissions using **security groups**, not individual users
- Secure identities with **Multi-Factor Authentication (MFA)**
- Validate access using real sign-in scenarios
- Monitor identity and access activity using audit and sign-in logs

---

## Architecture Overview

The architecture follows Microsoft-recommended best practices:

- Users are created in Microsoft Entra ID
- Users are added to security groups based on job roles
- RBAC roles are assigned to groups at the **Resource Group** scope
- MFA is enforced using Security Defaults
- Access is validated by logging in as different users
- All actions are monitored using Azure logs

 Detailed architecture explanation is available here:  
 [Architecture Documentation](architecture/README.md)

---

## Identity Design

### Users
- **Admin User** – Full control (Owner)
- **Developer User** – Contributor access
- **Read-only User** – Reader access
- **Guest User** – Limited vendor-style access

### Security Groups
- `grp-az-devs` → Contributor
- `grp-az-readonly` → Reader
- `grp-az-vendor-guest` → Reader (restricted)

Users receive permissions **only through group 

---

## Security Configuration

- **Security Defaults enabled**
- **MFA enforced** for all users
- Password-only access is blocked
- Guest user access is restricted

---

## Access Validation

Access was tested by logging in as:
- Developer → Access granted to resources
- Read-only user → View-only access
- Guest user → Limited access
- Unauthorized actions → Blocked

Screenshots of each scenario are documented.

View all validation screenshots here:  
[Screenshots](screenshots/README.md)

---

## Monitoring & Auditing

The following logs were reviewed:
- **Audit Logs** – Group membership changes
- **Sign-in Logs** – Login success and failure events

These logs confirm:
- RBAC enforcement
- MFA enforcement
- Unauthorized access attempts

---

## Skills Demonstrated

- Microsoft Entra ID (Azure AD)
- Azure RBAC & least privilege design
- Group-based access management
- Identity security & MFA
- Azure Monitor (Audit & Sign-in logs)
- Real-world IAM troubleshooting
- Azure Portal navigation & administration

---

## Real-World Use Case

This setup mirrors enterprise scenarios such as:
- Onboarding developers with controlled access
- Providing auditors with read-only permissions
- Granting vendors temporary, restricted access
- Enforcing security compliance with MFA
- Auditing identity changes for security reviews

---

## Cost & Subscription

- Built entirely using **Azure Free Tier**
- No paid services user


