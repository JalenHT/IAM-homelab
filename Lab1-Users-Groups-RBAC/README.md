\# Lab 1 — Users, Groups \& RBAC in Entra ID



\## Objective

Practice creating and managing user identities, 

groups, and role assignments in Microsoft Entra ID 

to simulate a real enterprise IAM environment.



\## Environment

\- Microsoft Entra ID Free tier

\- Personal lab tenant: yourname.onmicrosoft.com



\## What I did



\### Users created

\- Created 5 test users across IT, HR, Finance, 

&#x20; and Security departments

\- Set Department and Job Title attributes on each user



\### Groups created

\- IT-Staff (Security group, manual membership)

\- HR-Finance-Collab (Microsoft 365 group)



\### RBAC assignments

\- Assigned Helpdesk Administrator directly to Alex Turner

\- Assigned Security Reader to IT-Staff group

\- Tested access by logging in as each user 

&#x20; in a private browser window



\## What I observed

\- Direct role assignment gives immediate access

\- Group-based role assignment — removing a user 

&#x20; from the group instantly revokes the inherited role

\- Helpdesk Administrator could reset passwords 

&#x20; but could not modify roles or access security settings

\- Department/Job Title attributes are critical 

&#x20; for dynamic group rules



\## Skills demonstrated

\- User lifecycle management

\- Group-based access control

\- RBAC role assignment (direct and group-based)

\- Principle of least privilege

\- Identity attribute management



\## Tools used

\- Microsoft Entra ID

\- Microsoft 365 Admin Center



\## Screenshots

!\[Users List](users-list.png)

!\[IT-Staff Group](it-staff-group.png)

!\[Helpdesk Role](helpdesk-role.png)



