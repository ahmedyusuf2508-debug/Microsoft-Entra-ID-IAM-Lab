# Microsoft Entra ID | Identity and Access Management (IAM) Lab

## Project Overview

This project demonstrates how I built and managed an Identity and Access Management (IAM) environment using Microsoft Entra ID and Microsoft Graph PowerShell.

I created a fictional company called **SecureTech Solutions** to simulate real-world IAM responsibilities, including employee onboarding, role-based access control, multifactor authentication, security monitoring, and employee offboarding.

The goal was to gain hands-on experience managing user identities, controlling access, investigating sign-in activity, and securely removing employee access.

## Technologies Usedd

- Microsoft Entra ID
- Microsoft Azure Portal
- Microsoft Graph PowerShell
- Role-Based Access Control (RBAC)
- Multifactor Authentication (MFA)
- Microsoft Entra Audit Logs
- Microsoft Entra Sign-in Logs
- PowerShell

## Lab 1: Employee Onboarding

Created fictional employee accounts for different departments within SecureTech Solutions.

Departments included IT, Human Resources, Finance, and Security.

Created security groups to organize employees and manage access based on department.

**Skills demonstrated:** User provisioning, identity management, and security group administration.

## Lab 2: Role-Based Access Control (RBAC)

Configured administrative roles based on job responsibilities.

- Assigned Helpdesk Administrator to an IT support employee.
- Assigned Security Reader to a security analyst.
- Kept other employees as standard users.
- Tested administrative permissions to understand least-privilege access.

**Skills demonstrated:** RBAC, least privilege, and access management.

## Lab 3: Multifactor Authentication (MFA)

Configured Microsoft Authenticator for a test employee and verified MFA registration.

Explored how Microsoft Entra ID Security Defaults helps protect organizational accounts.

**Skills demonstrated:** Authentication security and MFA management.

## Lab 4: Sign-in Monitoring and Investigation

Generated controlled failed sign-in attempts and investigated them using Microsoft Entra sign-in logs.

Reviewed error code 50126, which indicates invalid credentials.

Used the logs to understand how IAM administrators investigate authentication failures.

**Skills demonstrated:** Security monitoring, log analysis, and identity threat investigation.

## Lab 5: Employee Offboarding with PowerShell

Simulated the departure of David Wilson, a fictional IT Support Specialist.

Performed the following actions:

1. Located the employee account using Microsoft Graph PowerShell.
2. Verified the account was enabled.
3. Disabled the account using `Update-MgUser`.
4. Confirmed the account status changed from `True` to `False`.
5. Verified the successful operation in Microsoft Entra audit logs.
6. Revoked the employee's sign-in sessions.
7. Removed the employee from the IT security group.

**Skills demonstrated:** User lifecycle management, PowerShell administration, session revocation, access removal, and audit verification.

## PowerShell Commands Used

```powershell
# Find a fictional employee
Get-MgUser -Filter "displayName eq 'David Wilson'"

# Disable the employee account
Update-MgUser -UserId "<test-user-UPN>" -AccountEnabled:$false

# Verify account status
Get-MgUser -UserId "<test-user-UPN>" -Property DisplayName,AccountEnabled |
    Select-Object DisplayName,AccountEnabled

# Revoke sign-in sessions
Revoke-MgUserSignInSession -UserId "<test-user-UPN>"
```

## Security Principles Demonstrated

- Least Privilege
- Role-Based Access Control
- Identity Lifecycle Management
- Multifactor Authentication
- Access Revocation
- Audit Logging and Monitoring
- Account Security

## Project Results

Successfully built a Microsoft Entra ID lab environment, created and managed employee identities, configured administrative permissions, investigated failed sign-ins, and completed an employee offboarding scenario using PowerShell.

This project helped me understand how IAM teams manage access and protect organizational identities in a real-world environment.

## Future Improvements

- Automate employee onboarding and offboarding.
- Create reusable PowerShell scripts.
- Expand access review testing.
- Explore Conditional Access policies in a properly licensed test environment.

## Disclaimer

All employee accounts and company information used in this project are fictional. This lab was created for educational and cybersecurity portfolio purposes.
