## User Objects
includes
- username
- password
- group memberships

can also include info like job title, department, company, email, etc.

can manage user objects in AD DS with
- AD admin center
- AD users and computers
- Windows Admin Center
- Windows PowerShell
- dsadd command line tool

### Service Accounts
for a service to start up and authenticate, a service account is needed 
- can used a domain based account to run services

AD DS has a managed service account object which is used for service account management
- simplifies pass and SPN management

group managed service accounts allow managing service accounts on more than one server in domain

