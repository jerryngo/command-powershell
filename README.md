# PowerShell: Connect to Office 365 (Step by Step Guide)
## _Step 1: Install Required PowerShell Modules_

Before you can connect to Office 365 you first need to install the required modules. Unfortunately, Microsoft is now recommending you install two modules to manage Office 365. Here are the two modules we will be installing.

- Installing Module 1 (Microsoft Azure Active Directory Module for Windows PowerShell)
1. Open PowerShell as administrator. To do this right-click on PowerShell and choose “run as administrator”
2. Type the following command and press enter

    ```s
    Install-module -name MSOnline
    ```
   > **Note:** If you get a message about NuGet version ***2.8.5.201*** or newer click yes or type ***Y***.
               If you get a message about installing the module from an untrusted repository click yes or type ***Y***.
   
3. Type the command below to list the installed modules

    ```s
    Get-Module -ListAvailable
    ```
   Link a ***PIC***

- Installing Module 2 (Azure Active Directory PowerShell for Graph)

1. Open PowerShell as Administrator

2. Type the following command and press enter

    ```s
    Install-Module -Name AzureAD
    ```

3. Verify the module is installed

    ```s
    get-module -ListAvailable
    ```

## _Step 2: Connect to Office 365 with PowerShell_

Each module has different commands for connecting to office 365. You don’t have to use both, you can pick which module you want to use.
- Connect with Module 1 (Microsoft Azure Active Directory Module for Windows PowerShell… AKA MSOnline)
1. Type the following command and press enter

    ```s
    Connect-MsolService
    ```

> **Note:** You will get prompted to sign in.

   Link a ***PIC***

 2. Verify connection
    ```s
    Get-MsolCompanyInformation
    ```
the command below to verify I’m connected to Office 365.

- Connect with Module 2 (Azure Active Directory PowerShell for Graph)

1. Type the following command and press enter

    ```s
    Connect-AzureAD
    ```
The AzureAD module will automatically display some company information when it connects.

Link a ***PIC***

## Example Office 365 Powershell commands
Here are a few examples of using PowerShell to manage office 365

- Get all Office 365 Users
    ```s
    Get-MsolUser -All | select-object *
    ```
- Get all licensed users
    ```s
    Get-MsolUser -All | Where-Object { $_.isLicensed -eq "TRUE" }
    ```
- Get Azure devices
    ```s
    Get-AzureADDevice
    ```
- Set a users password
    ```s
    Set-MsolUserPassword-UserPrincipalName “<email address>” -NewPassword “New Password”
    ```
- Assign a license to a user
    ```s
    Set-MsolUserLicense -UserPrincipalName “user name” -AddLicenses “<licensed name>”
    ```

  
