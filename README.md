# Powershell Active Directory Enumeration
Enumeration is the most important step when we want to perform a pentest or we want to audit our AD system.
Using powershell instead of external tools will help us to avoid triggering alerts on defense systems (AV,SIEM etc). As we say communicate with a Dog in his language and he won't bite you (okay nobody said that but you got the idea).

So here is a list of powershell commands for enumeration in Windows Active Directory environment. 

IMPORTANT : most of those commands are integrated to Active Directory module , you need to import it.

Get Users in a specific Domain 
```text
Get-ADUser -server Domaincontroller -Filter * -Properties *
```
Get Users that can receive null password
```text
Get-ADUser -server Domaincontroller -Filter {PasswordNotRequired -eq $true}
```
Get all users that do not Require Preauthentication
```text
Get-ADUser -Filter 'useraccountcontrol -band 4194304' -Properties useraccountcontrol | Format-Table name
```
Get the list of all trusts within the current domain
```text
Get-ADTrust -Filter *               
```
Get the list of all trusts within the indicated domain
```text
Get-ADTrust -Identity us.domain.corporation.local   
```
Get Computers in a specific Domain 
```text
Get-ADComputer -server Domaincontroller -Filter * -Properties *
```
Get all active computer list in domain
```text
Get-ADComputer -Filter {enabled -eq $true} -properties *
```
Get the default domain password policy from a specified domain
```text
Get-ADDefaultDomainPasswordPolicy -Identity corp.local.com
```
Get all groups that contain the word "admin" in the group name
```text
Get-ADGroup -Filter 'Name -like "*admin*"' | select Name     
```
Get all members of the "Domain Admins" group
```text
Get-ADGroupMember -Identity "Domain Admins" -Recursive       
```
Get group membership for a specific user
```text
Get-ADPrincipalGroupMembership -Identity login001     
```

![My Image](commands.png)

