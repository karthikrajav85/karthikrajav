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

The results of the review were documented in a structured Access Review Sheet, capturing user details, access validation (Right/Wrong), risk levels, and justification for each case.

📄 File: [Access Review Sheet](02-analysis/04_User_Access_Review_Sheet.xlsx)
(Click to download and view in Excel)

---

## Audit Findings

Based on the access review, multiple access control issues were identified and documented as audit findings. Each finding includes observation, risk, business impact, and recommended actions.

The key findings identified are:

- Inactive user accounts with active access to critical systems
- Excessive privileges granted beyond job requirements
- Unauthorized access to customer database by non-relevant roles
- Role-based access control (RBAC) violations
- Weak user lifecycle management (onboarding/offboarding)
- Lack of periodic access review process

These findings highlight gaps in access governance and increase the risk of unauthorized access, data breaches, and compliance violations.

Each finding was analyzed in detail with associated risks and remediation recommendations to strengthen access control mechanisms.

📄 File: [Audit Findings](02-analysis/05_Audit_Findings.xlsx)
(Click to download and view in Excel)

---

## Risk Assessment & Risk Register

Following the identification of audit findings, a risk assessment was performed to evaluate the potential impact of access control weaknesses on the organization.

The identified issues were consolidated into key risk areas such as inactive user access, excessive privileges, unauthorized database access, RBAC violations, weak user lifecycle management, and lack of periodic access review.

Each risk was assessed based on:
- **Likelihood**: Probability of occurrence
- **Impact**: Potential effect on business operations, data security, and compliance

Based on this assessment, risk levels were assigned (High, Medium, Low), and target risk levels were defined after implementing recommended controls.

A structured risk register was developed, including risk description, ownership, existing controls, recommended controls, and risk ratings.

📄 File: [Risk Register](03-risk/06_Risk_Register.xlsx)
(Click to download and view in Excel)

---

## Security Controls

Based on the identified risks, appropriate security controls were defined to mitigate access control weaknesses and strengthen access governance.

The controls were categorized into:

- **Preventive Controls**: To prevent unauthorized access (e.g., RBAC enforcement, least privilege, automated de-provisioning)
- **Detective Controls**: To identify issues (e.g., periodic access reviews, audit logging, access validation)
- **Corrective Controls**: To remediate issues (e.g., removal of unauthorized access, access correction)

Key controls implemented include:

- Role-Based Access Control (RBAC) enforcement
- Privileged Access Management (PAM)
- Automated user provisioning and de-provisioning
- Periodic access review and certification
- Access approval workflows
- Data masking for sensitive information
- Audit logging and monitoring

These controls were designed to ensure proper access management, reduce security risks, and improve compliance with organizational and regulatory requirements.

📄 File: [Security Controls](04-controls/07_Security_Controls.xlsx)
(Click to download and view in Excel)

---

## Governance Model (RACI)

To ensure effective implementation of access controls, a governance model was defined using the RACI (Responsible, Accountable, Consulted, Informed) framework.

This model establishes clear roles and responsibilities across the access management lifecycle, including access request, approval, provisioning, review, and de-provisioning.

Key responsibilities were assigned as follows:

- **Responsible (R)**: Executes the activity (e.g., IT Team for provisioning and de-provisioning)
- **Accountable (A)**: Owns the outcome and ensures completion (e.g., Business Owner, IT Manager)
- **Consulted (C)**: Provides input or approval (e.g., Security Team, HR)
- **Informed (I)**: Kept updated on activities (e.g., Compliance, Management)

This governance structure ensures accountability, reduces ambiguity, and helps in effective enforcement of access control policies.

📄 File: [Governance RACI Model](05-governance/08_Governance_RACI_Model.xlsx)
(Click to download and view in Excel)

---

## Risk Treatment & Action Plan

Based on the identified risks and recommended controls, a structured risk treatment plan was developed to ensure effective implementation of remediation actions.

Each risk was addressed through specific actions with clearly defined ownership, priority, and timelines. The action plan includes both immediate remediation steps and long-term control improvements.

Key actions include:

- Removal of inactive user access from critical systems
- Review and reduction of excessive privileges
- Implementation of automated user provisioning and de-provisioning
- Enforcement of Role-Based Access Control (RBAC)
- Introduction of periodic access review and certification process
- Implementation of Privileged Access Management (PAM)

High-risk issues were prioritized for immediate action, while medium-risk issues were planned for phased implementation.

This approach ensures that risks are not only identified but also effectively mitigated through actionable and trackable steps.

📄 File: [Action Plan](03-risk/09_Action_Plan.xlsx)
(Click to download and view in Excel)

---

## Business Impact & Compliance

The identified access control risks were further analyzed to understand their impact on business operations and regulatory compliance.

Business impact was evaluated in terms of data security, financial loss, operational disruption, and reputational damage. Risks such as unauthorized access to customer data and excessive privileges can lead to data breaches, fraud, and loss of customer trust.

From a compliance perspective, these risks may result in violations of applicable data protection regulations, particularly the Digital Personal Data Protection Act (DPDPA), India.

Key compliance risks include:

- Unauthorized access to personal data
- Failure to restrict access based on business need
- Lack of proper access control and monitoring mechanisms

Addressing these risks is critical to ensure regulatory compliance, protect sensitive data, and maintain business integrity.

📄 File: [Business Impact & Compliance](06-business-impact/10_Business_Impact_Compliance.xlsx)
(Click to download and view in Excel)

---

## Framework Mapping

To ensure alignment with industry standards and regulatory requirements, the identified security controls were mapped to globally recognized frameworks and standards.

The controls implemented in this project were aligned with:

- **ISO/IEC 27001:2022** – for information security management and access control practices
- **NIST SP 800-53** – for detailed security control guidelines, particularly in access control and audit mechanisms
- **Digital Personal Data Protection Act (DPDPA), India** – for compliance with data protection and privacy requirements

Key areas of alignment include:

- Access Control and Least Privilege (ISO 27001 A.5.15, NIST AC-6)
- Identity and Access Management (ISO 27001 A.5.16, NIST AC-2)
- Access Rights Management and Review (ISO 27001 A.5.18, NIST AC-2)
- Audit Logging and Monitoring (ISO 27001 A.8.15, NIST AU-2)
- Data Protection and Masking (ISO 27001 A.8.11)

This mapping ensures that the recommended controls are not only effective but also compliant with industry best practices and regulatory expectations.

📄 File: [Framework Mapping](04-controls/11_Framework_Mapping.xlsx)
(Click to download and view in Excel)

---

## Key Learnings

Through this project, I gained a practical understanding of access control review and risk assessment from a Cyber GRC perspective.

Key learnings include:

- Understanding how to define and implement Role-Based Access Control (RBAC) aligned with business needs
- Performing structured user access review to identify access control gaps
- Converting audit findings into meaningful risk scenarios
- Assessing risks based on likelihood and impact
- Designing preventive, detective, and corrective security controls
- Establishing governance through clear roles and responsibilities (RACI model)
- Developing risk treatment plans with defined actions, ownership, and timelines
- Mapping controls to industry frameworks such as ISO 27001 and NIST
- Evaluating business impact and compliance risks, including data protection requirements

This project helped in developing a risk-based and governance-oriented mindset required for Cyber GRC roles.

---

## Conclusion

This project demonstrates a complete end-to-end approach to User Access Review and Access Control Risk Assessment from an IAM perspective.

Starting from asset identification and role definition, the project progressed through access validation, audit findings, risk assessment, control design, governance implementation, and risk treatment planning.

By aligning the approach with industry frameworks and regulatory requirements, this project reflects a real-world Cyber GRC scenario focused on improving access governance and reducing security risks.

Overall, the project highlights the importance of structured access management, clear accountability, and continuous monitoring to ensure secure and compliant business operations.

---
