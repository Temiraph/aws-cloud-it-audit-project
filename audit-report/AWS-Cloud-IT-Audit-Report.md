# AWS Cloud IT Audit Report

## 1. Executive Summary
This audit assessed selected AWS cloud controls related to identity and access management, storage security, and logging/monitoring.

## 2. Audit Objective
The objective of this audit was to evaluate whether key AWS controls are appropriately configured to reduce security, compliance, and operational risks.

## 3. Audit Scope
The audit covered:
- IAM users, groups, roles, and policies
- MFA configuration
- S3 bucket public access settings
- CloudTrail logging configuration
- Privileged access controls

## 4. Audit Methodology
The audit was conducted using:
- Configuration review
- Evidence inspection
- Control testing
- Risk rating
- Documentation of findings and recommendations

## 5. Detailed Findings

### Finding 1 — Excessive Privileged Access

#### Observation
An IAM user named `audit-user` was assigned the `AdministratorAccess` policy, providing unrestricted administrative privileges within the AWS environment.

#### Risk
Excessive privileges increase the risk of unauthorized system changes, privilege abuse, and potential compromise of sensitive cloud resources.

#### Risk Rating
High

#### Recommendation
Administrative privileges should be restricted based on the principle of least privilege. Users should only receive permissions necessary for their job responsibilities.

---

### Finding 2 — MFA Not Enabled

#### Observation
Multi-Factor Authentication (MFA) was not enabled for the IAM user account reviewed during the audit.

#### Risk
Without MFA, compromised credentials could allow unauthorized access to the AWS environment.

#### Risk Rating
High

#### Recommendation
Enable MFA for all privileged and standard IAM accounts to reduce the risk of unauthorized access.

---

### Finding 3 — Publicly Accessible S3 Bucket

#### Observation
The S3 bucket allowed public read access through its bucket policy configuration.

#### Risk
Public access to cloud storage may result in unauthorized disclosure of sensitive information.

#### Risk Rating
High

#### Recommendation
Public access should be blocked unless explicitly required for business purposes. Bucket policies should follow least privilege principles.

-----

### Finding 4 — Incomplete Cloud Logging Configuration

#### Observation
CloudTrail logging was not fully configured across the AWS environment during the audit review.

#### Risk
Without centralized and complete logging, security incidents and unauthorized activities may not be detected or investigated effectively.

#### Risk Rating
High

#### Recommendation
CloudTrail should be configured across all required regions and integrated with centralized monitoring and log retention controls.
