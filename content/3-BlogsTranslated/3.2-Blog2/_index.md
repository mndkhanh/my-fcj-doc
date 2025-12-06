---
title: "Minimize risk through defense in depth: Building a comprehensive AWS control framework"
date: "2025-09-09T14:41:44+07:00"
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---

_Authors: Luis Pastor, Rodolfo Brenes, and George’son Tib_  
_Published At: September 23, 2025_  
_Categories: AWS CloudFormation, AWS Config, AWS Control Tower, AWS Organizations, AWS Security Hub, Security, Identity & Compliance_

---

## Challenges Faced by Security and Governance Teams

Security and governance teams across all environments face a common challenge: translating abstract security and governance requirements into a concrete, integrated control framework. AWS services provide capabilities that organizations can use to implement controls across multiple architectural layers—from provisioning infrastructure to continuous operational monitoring.

Many organizations deploy multi-account environments using **AWS Control Tower** or **Landing Zone Accelerator** as the foundational layer for governance and security architecture. Once the environment is set up, organizations typically add **detective controls** from services such as **AWS Security Hub** and **AWS Config**, based on security, compliance, and operational needs. While this progression is a strong starting point, there remains significant opportunity to implement **defense-in-depth** strategies that strengthen the overall security posture.

Highly regulated industries such as fintech and financial services often serve as the gold standard for governance and security controls. While these sectors have developed robust frameworks, continuous improvement and cross-industry learning remain valuable for organizations seeking to enhance their control environments. However, many organizations struggle to move beyond a baseline compliance mindset. Based on our experience with customers across industries, this limited perspective often stems from factors such as:

- Immediate compliance pressure
- Limited resources
- Lack of understanding of control maturity roadmaps
- Overemphasis on detection vs. prevention
- Preference for technology-agnostic controls instead of leveraging AWS-integrated capabilities—leading to unnecessary complexity

**The good news:**  
A more holistic approach—using AWS preventive, proactive, detective, and responsive controls—can dramatically reduce risk while enabling operational efficiency through automation.

This article presents a practical framework to help you develop a strong security and governance control strategy. We explore how your organization can advance from a detection-centric posture to a multilayered control framework, including real-world examples across the resource lifecycle—such as infrastructure-as-code testing and preventative controls like:

- **Service Control Policies (SCPs)**
- **Resource Control Policies (RCPs)**
- **Declarative Policies (DPs)**

Grounded in best practices from highly regulated industries and enhanced by modern cloud capabilities such as **AWS Organizations** and **AWS Control Tower**, we provide a structured approach for elevating your organization’s control environment beyond basic compliance.

---

## Customer Challenges in Control Implementation

Organizations encounter many obstacles when attempting to implement a comprehensive AWS control framework. Below are key challenges:

### 1. Limited Resources and Skill Gaps

Security teams often face expanding responsibilities while operating with constrained resources. They commonly adopt **detective controls** first because they appear easier to implement and provide immediate visibility—but this can create critical gaps in security posture.

Teams may also lack expertise across all control types, especially **preventative**, **proactive**, and **responsive** controls. Pressure to demonstrate fast improvements often leads to tactical fixes instead of strategic, multi-layered security design.

### 2. Analysis Paralysis

Choosing which tools to prioritize is difficult. The vast array of AWS security services and third-party tooling can overwhelm teams. Converting compliance requirements into cloud-focused capabilities while maintaining visibility of emerging threats adds further complexity.

These challenges may delay important improvements while teams search for a “perfect solution.”

### 3. Misunderstanding Defense in Depth

Defense in depth is often misunderstood. Some believe that a single strong control—such as strict IAM roles or least-privilege policies—is sufficient.

This overlooks the importance of multiple coordinated controls across different layers. Many teams also underestimate the role of organizational-level controls like SCPs, which complement workload-level controls to create a stronger overall posture.

### 4. Security Maturity Journey Challenges

Many organizations remain stuck at early maturity stages, relying heavily on detection without advancing toward prevention. Controls are often applied inconsistently and lack alignment to a broader security strategy.

Measuring progress over time is also difficult—contributing to stalled maturity.

### 5. Scale and Consistency Issues

As AWS environments grow, consistent governance becomes harder. Managing exceptions and special cases across growing infrastructure introduces operational complexity. Controls may be partially implemented or implemented incorrectly—reducing their intended impact.

---

## Strategic Investment in Security

Implementing comprehensive controls requires initial investment, but long-term benefits can significantly transform organizational operations.

The transformation begins with establishing **baseline controls** using proven starting points like:

- **AWS Control Tower**
- **Customizations for AWS Control Tower**

These tools provide hundreds of built-in controls and guardrails for secure multi-account architectures.

Rather than manually constructing all account-level and resource-level controls, you can accelerate by using AWS-native governance frameworks and automation.

Once baseline controls are in place, benefits extend beyond the security team:

- Development and operations teams deploy faster and more confidently
- Security becomes an enabler, not a blocker
- Guardrails ensure strong posture without slowing innovation

As your organization evolves, automation and layered controls reduce operational burden and help shift security teams from reactive firefighting to proactive risk management.

---

## Understanding the Types of Security Controls and How They Work Together

AWS defines four major categories of controls, all of which work together to form a comprehensive security framework. Let’s examine each type using a common requirement: **preventing data leakage from public Amazon S3 buckets.**

---

## Preventative Controls

Preventative controls establish the foundational security requirements by defining policies, standards, and expectations before resources are deployed.

An example S3 requirement:

> **All S3 buckets must be private by default, and public access may only be granted through an approved exception process.**

Preventative controls apply across organizational and resource levels:

### Organization Level

- **SCPs** to block creation of publicly accessible S3 buckets
- **SCPs** to prevent unsafe S3 object uploads, such as blocking SSE-C encryption unless explicitly approved

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "DenySSECEncryption",
      "Effect": "Deny",
      "Action": "s3:PutObject",
      "Resource": "*",
      "Condition": {
        "Null": {
          "s3:x-amz-server-side-encryption-customer-algorithm": "false"
        }
      }
    }
  ]
}
```

### Resource Level
