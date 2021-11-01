# Cheat Sheet | Attack Active-Directory

This cheat sheet contains common enumeration and attack methods for Windows Active Directory with the use of powershell.

## Using PowerView:
```
. .\PowerView.ps1
```
Link: ![PowerView](https://github.com/PowerShellMafia/PowerSploit/blob/master/Recon/PowerView.ps1)
## Using AD Module
```
Import-Module .\Microsoft.ActiveDirectory.Management.dll
Import-Module .\ActiveDirectory\ActiveDirectory.psd1
```
Link: ![AD Module](https://github.com/samratashok/ADModule)

## Enumeration:

### Enumeration Users:

- **With PowerView:**
```
Get-NetUser                                           #Get the list of users
Get-NetUser -Username user01                          #Enumeration on user "user01"
Get-NetUser | select cn                               #Get the list of users from cn common-name
Get-NetUser | select name                             #Get the list of users from name
```
- **With AD Module:**
```
Get-ADUser -Filter *                                  #Get the list of users
Get-ADUser -Filter * -Properties *                    #Get the list of users with properties
Get-ADUser -Filter * -Properties * | select cn        #Get the list of users from cn common-name
Get-ADUser -Filter * -Properties * | select name      #Get the list of users from name
```
