\# Lab 5 — Bulk User Creation via PowerShell \& CSV



\## Objective

Automate the creation of multiple users in Microsoft 

Entra ID using a CSV file and PowerShell, simulating 

real enterprise employee onboarding workflows.



\## Environment

\- Microsoft Entra ID Free tier

\- PowerShell 7.6.0

\- Microsoft Graph PowerShell SDK

\- Visual Studio Code



\## What I did

\- Created a CSV file with 5 users including Department 

&#x20; and Job Title attributes

\- Wrote a PowerShell script to read the CSV and create 

&#x20; each user automatically

\- Used try/catch error handling to log successes and failures

\- Confirmed all 5 users were created in Entra ID portal



\## What I observed

\- CSV-based onboarding eliminates manual portal work

\- Try/catch blocks allow the script to continue even 

&#x20; if one user fails

\- Department and Job Title are set automatically 

&#x20; from the CSV — no extra steps needed

\- This is how IAM teams onboard entire departments 

&#x20; at once during mergers or large hiring events



\## Script used

```powershell

Connect-MgGraph -Scopes "User.ReadWrite.All"



Import-Csv -Path "$env:USERPROFILE\\Desktop\\users.csv" | ForEach-Object {

&#x20;   $pp = @{ 

&#x20;       Password = "TempPass123!"

&#x20;       ForceChangePasswordNextSignIn = $true 

&#x20;   }

&#x20;   try {

&#x20;       New-MgUser `

&#x20;           -DisplayName $\_.DisplayName `

&#x20;           -UserPrincipalName $\_.UserPrincipalName `

&#x20;           -Department $\_.Department `

&#x20;           -JobTitle $\_.JobTitle `

&#x20;           -MailNickname $\_.MailNickname `

&#x20;           -AccountEnabled `

&#x20;           -PasswordProfile $pp

&#x20;       Write-Host "Created: $($\_.DisplayName)" -ForegroundColor Green

&#x20;   } catch {

&#x20;       Write-Host "Failed: $($\_.DisplayName)" -ForegroundColor Red

&#x20;   }

}

```



\## Skills demonstrated

\- PowerShell scripting

\- CSV data processing

\- Bulk user provisioning automation

\- Error handling in PowerShell

\- Microsoft Graph API user management

\- Enterprise onboarding simulation



\## Tools used

\- PowerShell 7.6.0

\- Microsoft Graph PowerShell SDK

\- Visual Studio Code

\- Microsoft Entra ID



\## Screenshots

!\[Bulk User Creation Output](bulk-create-output.png)

!\[Users in Entra Portal](users-portal.png)

