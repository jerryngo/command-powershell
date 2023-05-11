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

  
