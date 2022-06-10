# pwsh-enum
Enumeration is the most important step when we perform a pentest or we want to audit our systems.
Using powershell commands instead of a external tools will help us to avoid triggering alerts on defense systems (AV,SIEM etc). As we say communicate with a Dog in his language and he won't bite you (okay nobody said that but you got the idea).

So here is a list of powershell commands for enumeration in Windows Active Directory environment. 

IMPORTANT : most of those commands are integrated to Active Directory module , you need to import first the module


```text
# Get Users in a specific Domain 
Get-ADUser -server Domaincontroller -Filter * -Properties *

#Get Users that can receive null password
Get-ADUser -server Domaincontroller -Filter {PasswordNotRequired -eq $true}

# Get Computers in a specific Domain 
Get-ADComputer -server Domaincontroller -Filter * -Properties *

# Get all active computer list in domain
# Get-ADComputer -Filter {enabled -eq $true} -properties *

# Get the default domain password policy from a specified domain
Get-ADDefaultDomainPasswordPolicy -Identity corp.local.com
```

