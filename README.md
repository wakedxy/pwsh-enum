# pwsh-enum
Powershell commands for enumeration in Windows Active Directory environment. 

```text
# Get Users in a specific Domain 
Get-ADUser -server Domaincontroller -Filter * -Properties *

#Get Users that can receive null password
Get-ADUser -server Domaincontroller -Filter {PasswordNotRequired -eq $true}

# Get Computers in a specific Domain 
Get-ADComputer -server Domaincontroller -Filter * -Properties *

#
```

```text
# Get the default domain password policy from a specified domain
Get-ADDefaultDomainPasswordPolicy -Identity corp.local.com
```
