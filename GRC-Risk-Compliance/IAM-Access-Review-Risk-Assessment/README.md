# User Access Review & Access Control Risk Assessment (IAM Perspective)

## Project Overview

This project demonstrates a complete User Access Review and Access Control Risk Assessment from an Identity and Access Management (IAM) perspective for a mid-sized organization, KR Shopping Pvt Ltd.

The objective of this project is to identify access control weaknesses, evaluate associated risks, and recommend appropriate security controls to improve access governance.

The project covers key activities such as asset identification, role-based access definition, user access validation, audit findings, risk assessment, control recommendations, and governance design.

This project is designed to simulate a real-world internal audit and risk assessment scenario, aligning with industry frameworks such as ISO 27001, NIST, and regulatory requirements like the Digital Personal Data Protection Act (DPDPA), India.

---

## Business Scenario

KR Shopping Pvt Ltd is a mid-sized retail and e-commerce company operating across major cities in Tamil Nadu, India. The organization manages both online and offline sales channels, including an e-commerce web application, mobile application, and physical retail outlets.

The company has approximately 400–450 employees, with around 50–60 users having access to critical IT systems such as customer databases, payment systems, admin panels, and cloud infrastructure.

Due to business expansion and increasing reliance on digital platforms, the organization faces challenges in managing user access effectively. Issues such as excessive access privileges, inactive user accounts, and lack of periodic access review can lead to security risks and compliance violations.

To address these challenges, the organization initiated an internal access review and risk assessment to evaluate current access controls and strengthen its Identity and Access Management (IAM) practices.

---

## Objectives

The key objectives of this project are:

- To identify and classify critical systems and assets used within the organization
- To define role-based access control (RBAC) aligned with business functions
- To review existing user access and identify access control issues
- To detect risks such as excessive access, inactive accounts, and unauthorized access
- To document audit findings in a structured and professional manner
- To perform risk assessment based on likelihood and impact
- To recommend appropriate security controls to mitigate identified risks
- To establish governance and accountability for access management
- To develop a risk treatment plan with defined actions, owners, and timelines
- To evaluate business impact and compliance risks related to access control issues
- To align the overall approach with industry standards such as ISO 27001, NIST, and DPDPA

---

## Scope of the Project

This project focuses on performing a User Access Review and Access Control Risk Assessment for selected critical systems within the organization.

The scope includes:

- Review of approximately 50 users who have access to key business systems
- Analysis of critical systems such as Customer Database, Payment Processing System, Admin Panel, IAM System, and POS System
- Evaluation of user access against defined role-based access control (RBAC)
- Identification of access control issues such as excessive access, inactive users, and role mismatches
- Documentation of audit findings and risk assessment
- Recommendation of security controls and governance mechanisms

The scope excludes:

- Detailed technical implementation of security tools
- Infrastructure-level security configurations
- Network security and application security testing

This project is focused on access governance and risk assessment from a Cyber GRC perspective.

---

## Critical Systems & Asset Classification

As part of the assessment, critical business systems were identified and classified based on their impact on business operations, data sensitivity, and risk exposure.

The systems were categorized into High, Medium, and Low based on factors such as customer data handling, financial transactions, and operational dependency.

High critical systems include Customer Database, Payment Processing System, Admin Panel, IAM System, and E-commerce Applications, as they handle sensitive data and core business operations.

Medium critical systems include POS System, Inventory Management System, and Email System, which support business operations but have relatively lower risk compared to core systems.

Low critical systems include infrastructure components with limited direct business impact.

📄 File: [Asset Classification Table](01-data/01_Asset_Classification_Table.xlsx)
(Click to download and view in Excel)

---

## Role-Based Access Control (RBAC)

As part of the assessment, a Role-Based Access Control (RBAC) model was defined to establish the expected access levels for different user roles within the organization.

Roles such as Customer Support Executive, Finance Executive, Database Administrator, Application Developer, DevOps Engineer, and Store Manager were identified based on business functions.

Access permissions were assigned based on the principle of least privilege, ensuring that users are granted only the minimum level of access required to perform their job responsibilities.

This RBAC model was used as a baseline to compare against actual user access in order to identify deviations, excessive privileges, and unauthorized access.

📄 File: [Role Access Mapping](01-data/02_Role_Access_Mapping.xlsx)
(Click to download and view in Excel)

---

## User Access Dataset

A realistic user access dataset was created to simulate actual organizational access scenarios. The dataset consists of 50 users across different business roles such as Customer Support, Finance, IT, Development, and Operations.

Each user was assigned access to specific systems along with defined access levels (Read, Write, Admin) and account status (Active/Inactive).

The dataset was intentionally designed to include both correct and incorrect access configurations, such as excessive privileges, inactive users with access, and role mismatches. This approach helped in performing a meaningful access review and identifying real-world security gaps.

This dataset served as the foundation for conducting access validation, audit findings, and risk assessment.

📄 File: [User Access Dataset](01-data/03_User_Access_Dataset.xlsx)
(Click to download and view in Excel)

---

## Access Review Process

The user access review was performed by comparing actual user access against the defined Role-Based Access Control (RBAC) model.

Each user’s access was evaluated based on their role, assigned system, access level (Read, Write, Admin), and account status (Active/Inactive).

Access was classified as:
- **Right**: When access aligns with the user’s role and business requirement
- **Wrong**: When access is excessive, inappropriate, or assigned to inactive users

Risk levels (High, Medium, Low, Nil) were assigned based on the potential impact of the identified issue, such as exposure of sensitive data, unauthorized modifications, or misuse of privileged access.

This structured approach helped in identifying key access control gaps, including inactive users with access, excessive privileges, and role mismatches.

📄 File: [Access Review Sheet](02-analysis/04_User_Access_Review_Sheet.xlsx)
(Click to download and view in Excel)

---


