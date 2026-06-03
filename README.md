# CyberArk PAM Lifecycle Lab — Privileged Account Onboarding & Session Security

## Overview

This project demonstrates a CyberArk Privileged Access Management workflow, including:

- Creating and managing CyberArk Safes
- Onboarding privileged accounts into the Vault
- Assigning user access to Safes
- Managing privileged sessions through PSM
- Simulating password rotation and account offboarding
- Supporting audit visibility for privileged access activity

## Tools Used

- CyberArk PVWA
- CyberArk Vault
- CPM
- PSM
- Active Directory
- Windows Server
- PowerShell
- CyberArk REST API

## Project Goals

The goal of this lab is to show how privileged accounts can be secured, monitored, and managed using CyberArk PAM.

## Architecture / Workflow

1. Create privileged account in Active Directory
2. Create Safe in CyberArk PVWA
3. Add privileged account to the Safe
4. Assign user permissions and Safe membership
5. Configure CPM for password management
6. Connect to target server through PSM
7. Monitor and record privileged session activity
8. Perform password rotation and verification
9. Offboard account and remove privileged access

Administrator
      |
      v
    PVWA
      |
      v
    Vault
   /     \
 CPM     PSM
  |        |
  v        v
Password  Target
Rotation  Server


## Key Tasks Completed

- Created CyberArk Safe for privileged accounts
- Onboarded Windows/AD privileged account
- Configured Safe member access
- Tested privileged session through PSM
- Reviewed CyberArk audit/session activity
- Documented onboarding and offboarding workflow

## PowerShell / API Examples

### Create CyberArk Safe

```powershell
Invoke-RestMethod -Method POST `
-Uri "$PVWAURL/API/Safes" `
-Headers $Headers `
-Body $SafeBody

### Retrieve Accounts

Invoke-RestMethod -Method GET `
-Uri "$PVWAURL/API/Accounts" `
-Headers $Headers

### Add Accounts to CyberArk
Invoke-RestMethod -Method POST `
-Uri "$PVWAURL/API/Accounts" `
-Headers $Headers `
-Body $AccountBody


## Challenges & Fixes

### 1. Safe Permission Configuration

- Issue: Users could not view or access privileged accounts stored in the Safe.
- Fix: Reviewed Safe membership and assigned the required permissions through PVWA.

---

### 2. Platform Assignment During Onboarding

- Issue: Account onboarding failed due to incorrect platform selection.
- Fix: Selected the appropriate Windows platform and validated account properties.

---

### 3. Privileged Session Connection (PSM)

- Issue: Unable to launch an RDP session through PSM.
- Fix: Verified PSM connectivity and confirmed account permissions before reconnecting.

---

### 4. Password Verification & Reconciliation

- Issue: Credential verification failed during account management testing.
- Fix: Reviewed account configuration and corrected credential settings.

---

### 5. Account Offboarding

- Issue: Privileged account remained assigned after deprovisioning.
- Fix: Removed account dependencies and deleted the account from the Safe following least-privilege practices.

---

### 6. CyberArk API Authentication

- Issue: API requests returned authentication errors.
- Fix: Validated API endpoint configuration and authentication headers before retrying requests.



The following screenshots demonstrate the end-to-end CyberArk PAM lifecycle from account
onboarding to secure privileged access and deprovisioning.

### 1. Safe Creation & Management
<img src="https://github.com/user-attachments/assets/5e20a6c9-c733-424d-ae91-a4f14766dd1f"width="800"  />

Shows Safe configuration (Lex1) with assigned CPM and member permissions.


### 2. Account Onboarding

<img src="https://github.com/user-attachments/assets/6d5186d5-9485-4f32-a2a1-61755bf70f70"width="600"  />

Demonstrates onboarding of a Windows local account into CyberArk, including platform assignment
 and credential configuration.


### 3. Account Management View
<img src="https://github.com/user-attachments/assets/335ca974-87ce-49fb-a533-2884a0f6c415"width="800" />

### 4. Privileged Access via PSM
<img src="https://github.com/user-attachments/assets/d9de66d6-88cc-4f08-a6e3-0a61521db201"width="800" />


### 5. Active Session (RDP)
<img src="https://github.com/user-attachments/assets/2ced8664-c761-4b2d-972b-a19532f85ad1"width="800" />


### 6. Account Deletion
<img src="https://github.com/user-attachments/assets/8c7f08a3-b940-4c95-a6f0-1b0e3cb41052"width="700" />

Demonstrates secure offboarding of a privileged account in CyberArk, enforcing least privilege by
 removing dependencies, access links, and group memberships to prevent unauthorized access.

What I Learned

* How CyberArk secures privileged credentials
* How Safes control privileged account access
* How CPM supports password rotation
* How PSM provides session monitoring
* How PAM supports least privilege and audit readiness

Outcome

Successfully simulated a CyberArk PAM lifecycle workflow for privileged account onboarding, secure access, session monitoring, and offboarding.

## Recommendations

- Enforce MFA for privileged users
- Implement regular password rotation through CPM
- Review Safe permissions quarterly
- Monitor privileged sessions through PSM
- Apply least privilege to all privileged accounts

## Reflection

This lab strengthened my understanding of privileged access management, account lifecycle operations, secure session management, and CyberArk administrative workflows. It also reinforced the importance of least privilege and credential protection in enterprise environments.


