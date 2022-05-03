# pwsh-enum
Powershell commands for enumeration in Windows Active Directory environment. 

```text
# Get Users in a specific Domain 
Get-ADUser -server Domaincontroller -Filter * -Properties *
```

```text
# Get the default domain password policy from a specified domain
Get-ADDefaultDomainPasswordPolicy -Identity corp.local.com
```
