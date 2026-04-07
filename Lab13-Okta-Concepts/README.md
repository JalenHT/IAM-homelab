# Lab 13 — Okta Concepts & Architecture

## Objective
Document Okta Identity and Access Management concepts,
architecture, and compare Okta to Microsoft Entra ID
to demonstrate knowledge of third-party IAM platforms
used in enterprise environments.

## Why Okta matters
Okta is the most widely deployed third-party IAM platform
in enterprise environments. Many Houston employers including
financial services, energy, and healthcare companies use
Okta alongside or instead of Microsoft Entra ID. Understanding
Okta concepts is essential for any IAM analyst role.

## Okta vs Microsoft Entra ID

| Feature | Okta | Microsoft Entra ID |
|---------|------|--------------------|
| Type | Third-party IAM | Microsoft native IAM |
| Best for | Multi-cloud, vendor neutral | Microsoft 365 environments |
| SSO | Universal Directory | Azure AD SSO |
| MFA | Okta Verify, push, TOTP | Microsoft Authenticator |
| Provisioning | Okta Lifecycle Management | Entra ID Provisioning |
| On-prem sync | Okta AD Agent | Entra Connect |
| Pricing | Per user per month | Included with M365 |
| Free tier | Developer tenant (limited) | Entra ID Free |

## Core Okta concepts

### Universal Directory
Okta's central user store — similar to Active Directory
or Entra ID. Stores all user profiles, attributes, and
group memberships in one place regardless of where the
user was originally created.

### Okta Lifecycle Management
Automates user provisioning and deprovisioning across
connected applications. When a user is created in Okta
they are automatically provisioned in all assigned apps.
When deprovisioned all access is revoked simultaneously.

### Okta Integration Network (OIN)
A catalog of 7000+ pre-built app integrations. IAM
analysts use OIN to connect SaaS applications to Okta
for SSO and provisioning without custom development.

### Authentication Policies
Rules that define how users must authenticate to access
applications. Similar to Conditional Access in Entra ID.
Policies can require MFA based on user, group, network
location, device trust, and risk level.

### Okta Verify
Okta's native MFA authenticator app — equivalent to
Microsoft Authenticator. Supports push notifications,
TOTP codes, and biometric authentication.

## How Okta SSO works (SAML 2.0 flow)
```
User → clicks app → Okta checks policy → 
prompts MFA if required → generates SAML assertion → 
sends assertion to app → app grants access
```

**Key terms:**
- **IdP (Identity Provider)** — Okta — issues the SAML assertion
- **SP (Service Provider)** — the application — trusts the assertion
- **SAML assertion** — a signed XML token proving the user's identity
- **SSO URL** — where the SP sends authentication requests
- **Entity ID** — unique identifier for the IdP or SP

## How Okta MFA policies work

Okta MFA policies are configured at two levels:

**Org-level policy** — applies to all users signing into Okta
**App-level policy** — applies to specific applications

Policy factors available:
- Okta Verify push notification
- TOTP authenticator apps (Google Authenticator etc)
- SMS/Voice (legacy — not recommended)
- Hardware security keys (FIDO2/WebAuthn)
- Email magic link
- Biometrics

## Okta vs Entra ID — MFA comparison

| Feature | Okta | Entra ID |
|---------|------|----------|
| Push notifications | Okta Verify | Microsoft Authenticator |
| TOTP | Any TOTP app | Microsoft Authenticator |
| FIDO2/Passkeys | Yes | Yes |
| SMS (legacy) | Yes (not recommended) | Yes (not recommended) |
| Conditional policy | Authentication Policies | Conditional Access |
| Risk-based MFA | Okta ThreatInsight | Entra ID Protection |

## Okta AD Agent vs Microsoft Entra Connect

Both tools sync on-premises Active Directory users
to the cloud IAM platform:

| Feature | Okta AD Agent | Entra Connect |
|---------|---------------|---------------|
| Syncs to | Okta Universal Directory | Microsoft Entra ID |
| Install on | Domain-joined Windows server | Domain Controller |
| Sync direction | One-way (AD to Okta) | One-way (AD to Entra) |
| Password sync | Yes | Yes |
| Real-time sync | Near real-time | Every 30 minutes |

## Common Okta interview questions

**Q: What is the difference between Okta and Active Directory?**
Active Directory is an on-premises directory service for
managing users and computers in a Windows domain. Okta is
a cloud-based IAM platform that provides SSO, MFA, and
lifecycle management for SaaS applications. Okta can sync
with Active Directory using the Okta AD Agent.

**Q: What is the difference between SP-initiated and IdP-initiated SSO?**
SP-initiated: user goes to the application first, gets
redirected to Okta to authenticate, then redirected back.
IdP-initiated: user goes to Okta dashboard first, clicks
the app tile, and is sent directly to the app with a
SAML assertion.

**Q: What is Okta Lifecycle Management?**
It automates user provisioning and deprovisioning across
connected applications using SCIM or API connectors. When
HR creates a user in the source system Okta automatically
provisions access to all assigned applications. When the
user is terminated Okta deprovisioning revokes all access.

**Q: How does Okta handle MFA?**
Okta uses Authentication Policies to define when MFA is
required. Policies can be applied at the org level or per
application. Factors include Okta Verify push, TOTP, FIDO2,
and biometrics. Risk-based MFA using ThreatInsight can
require step-up authentication based on suspicious signals.

## What I would practice with an Okta tenant
- Create users and groups in Universal Directory
- Configure an Authentication Policy requiring MFA
- Add a SAML 2.0 app integration from the OIN
- Test SP-initiated and IdP-initiated SSO flows
- Configure the Okta AD Agent to sync lab.local users
- Review system logs for authentication events

## Skills demonstrated
- Okta architecture and core concepts
- SAML 2.0 SSO flow understanding
- Okta vs Entra ID comparison
- MFA policy concepts
- Lifecycle management concepts
- Okta AD Agent vs Entra Connect comparison
- IAM platform evaluation skills

## Note on hands-on access
Okta Developer tenant requires a business email address
for signup. Personal Gmail accounts are not accepted.
This lab documents Okta concepts and architecture based
on official Okta documentation and industry knowledge.
Hands-on labs will be added when business email access
is available.

## Resources used
- Okta Developer Documentation: developer.okta.com
- Okta Identity 101: help.okta.com
- SAML 2.0 specification
- Okta vs Microsoft Entra ID comparison guides
