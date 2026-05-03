# CyberArk PAM Lifecycle Lab

## Overview
This project demonstrates hands-on experience with CyberArk Privileged Access Management (PAM), focusing on managing privileged accounts across their full lifecycle.

I implemented account onboarding, safe management, credential verification, reconciliation, privileged session access (PSM), and secure account deprovisioning in a controlled lab environment.

## What I Did
- Managed privileged accounts using CyberArk PVWA
- Created and managed Safes to securely store credentials
- Onboarded Windows Server local accounts into CyberArk
- Performed account lifecycle operations:
  - Account onboarding (adding accounts to safes)
  - Credential verification
  - Password reconciliation
  - Secure account deletion
- Established secure privileged sessions via CyberArk PSM, using brokered RDP connections without exposing credentials
- Validated access control and account security states

  
## Key Concepts Demonstrated
- Privileged Access Management (PAM)
- Safe management
- Account lifecycle (Create → Manage → Delete)
- Security and access control

The following screenshots demonstrate the end-to-end CyberArk PAM lifecycle from account onboarding to secure privileged access and deprovisioning.

### 1. Safe Creation & Management
<img src="https://github.com/user-attachments/assets/5e20a6c9-c733-424d-ae91-a4f14766dd1f"  width="800"  />

Shows Safe configuration (Lex1) with assigned CPM and member permissions.


### 2. Account Onboarding

<img src="https://github.com/user-attachments/assets/6d5186d5-9485-4f32-a2a1-61755bf70f70"  width="600"  />

Demonstrates onboarding of a Windows local account into CyberArk, including platform assignment and credential configuration.


### 3. Account Management View
<img src="https://github.com/user-attachments/assets/335ca974-87ce-49fb-a533-2884a0f6c415" width="800" />

### 4. Privileged Access via PSM
<img src="https://github.com/user-attachments/assets/d9de66d6-88cc-4f08-a6e3-0a61521db201" width="800" />


### 5. Active Session (RDP)
<img src="https://github.com/user-attachments/assets/2ced8664-c761-4b2d-972b-a19532f85ad1" width="800" />


### 6. Account Deletion
<img src="https://github.com/user-attachments/assets/8c7f08a3-b940-4c95-a6f0-1b0e3cb41052" width="700" />

Demonstrates secure offboarding of a privileged account in CyberArk, enforcing least privilege by removing dependencies, access links, and group memberships to prevent unauthorized access.
