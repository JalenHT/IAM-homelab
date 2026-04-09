# Lab 15 — ServiceNow ITSM Concepts

## Objective
Document ServiceNow IT Service Management concepts
and IAM-specific workflows used by identity analysts
in enterprise environments.

## Why ServiceNow matters
ServiceNow is the most widely deployed ITSM platform
in enterprise environments. IAM analysts use ServiceNow
daily to process access requests, manage onboarding and
offboarding tickets, and document provisioning activities.
Most IAM job descriptions list ServiceNow as a required
or preferred skill.

## Core ServiceNow modules for IAM analysts

### Incident Management
Used to track and resolve access issues reported by users.
Common IAM incidents:
- User locked out of account
- MFA not working
- SSO login failure
- Password reset requests
- Access denied to the application

### Service Catalog
A self-service portal where users submit access requests.
IAM analysts review and fulfill these requests based on
least privilege principles and approval workflows.

Common catalog items:
- New user account request
- Application access request
- Elevated privilege request
- VPN access request
- Shared mailbox access

### Change Management
Used to document and approve changes to identity systems.
IAM changes that require change tickets:
- Adding a new application to SSO
- Modifying group membership policies
- Updating Conditional Access rules
- Deploying new MFA methods
- Changing password policy settings

### Request and Approval Workflow
ServiceNow workflows automate the approval process for
access requests. A typical IAM access request flow:

```
User submits request → Manager approval →
IT security review → IAM analyst provisions →
Ticket resolved → User notified
```

## Common IAM ticket types

### New employee onboarding ticket
When a new employee joins the organization, an onboarding
ticket is created containing all access that needs to be
provisioned:
- Active Directory account creation
- Email account setup
- Application access based on role
- MFA enrollment
- VPN access if required
- Badge access if applicable

### Employee offboarding ticket
When an employee leaves, all access must be revoked
immediately. Offboarding checklist:
- Disable AD account
- Revoke all application access
- Remove from all security groups
- Invalidate MFA tokens
- Forward email if required
- Document completion with timestamps

### Access review ticket
Periodic reviews of user access to ensure compliance
with least privilege. IAM analyst tasks:
- Pull a list of users with access
- Send review to managers
- Remove access for departed users
- Document approved access
- Close ticket with audit trail

### Privileged access request
Requests for elevated or admin-level access require
additional approval and are time-limited:
- Requires manager and security team approval
- Access granted for a specific time window
- All activity logged during the elevated access period
- Access automatically revoked when the window expires

## ServiceNow vs ticketing tools comparison

| Feature | ServiceNow | Jira | Remedy |
|---------|------------|------|--------|
| ITSM focus | Yes | No | Yes |
| IAM workflows | Built-in | Custom | Built-in |
| Self-service portal | Yes | Limited | Yes |
| Approval workflows | Yes | Yes | Yes |
| Market share | #1 enterprise | Developer focus | Legacy |
| Free tier | Developer (limited) | Cloud free | No |

## Key ServiceNow terms for IAM interviews

**RITM** — Requested Item — individual line item in a
service catalog request

**INC** — Incident ticket number prefix

**CHG** — Change ticket number prefix

**REQ** — Request ticket number prefix

**SLA** — Service Level Agreement — time limit for
resolving a ticket (e.g., access requests resolved in 4 hours)

**CMDB** — Configuration Management Database — inventory
of all IT assets and their relationships

**Assignment group** — The team responsible for a ticket
(e.g., IAM Team, Security Operations)

## What I would practice with a ServiceNow instance
- Create and resolve an incident for a locked-out user
- Submit an access request through the Service Catalog
- Build an approval workflow for privileged access
- Create an onboarding ticket with all provisioning steps
- Run an access review and document results
- Create a change ticket for an Entra ID policy update

## Common ServiceNow interview questions

**Q: Walk me through how you would handle an access request**
User submits a request through the Service Catalog. I review
the request against the user's role and least privilege
policy. I escalate for manager approval if required. Once
approved, I provision the access in the relevant system
(AD, Entra ID, application). I document all steps in the
ticket work notes and resolve the ticket, notifying the user.

**Q: What is the difference between an incident and a request?**
An incident is an unplanned interruption — something broke.
A request is a planned ask for something new — a user wants
access to an application. Incidents have stricter SLAs
because they impact productivity immediately.

**Q: How do you document access provisioning in ServiceNow?**
I use work notes to document every action taken — what
access was granted, when, in which system, and under whose
approval. This creates an audit trail that compliance teams
can review. I never close a ticket without complete
documentation of what was provisioned.

## Note on hands-on access
ServiceNow Personal Developer Instance requires a business
email address. This lab documents ServiceNow concepts and
IAM workflows based on official ServiceNow documentation
and industry knowledge. Hands-on practice will be added
when business email access is available.

## Skills demonstrated
- ITSM concepts and terminology
- IAM ticket lifecycle management
- Access request workflow design
- Onboarding and offboarding process knowledge
- Audit trail and documentation practices
- SLA and compliance awareness
- ServiceNow module knowledge

## Resources used
- ServiceNow Documentation: docs.servicenow.com
- ServiceNow Learning: nowlearning.servicenow.com
- ITSM best practices
