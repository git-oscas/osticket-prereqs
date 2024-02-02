<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Install IIS with CGI
- Download PHP Manager for IIS
- Download Rewrite Module
- Download PHP 7.3.8
- Download VC_redist.x86.exe
- Download MySQL 5.5.62
- Download osTicket v1.15.8
- Download HeidiSQL

<h2>Installation Steps</h2>

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/e6c29e3d-a252-47f2-99e2-80485bc31049)

Create an Azure VM using Windows 10

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/1e330bc0-db9a-4979-85d5-9d4580160d3b)
![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/74620a11-fdef-4a2d-a3bd-da43d16e89d7)
![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/43faf803-6443-41f3-99aa-20017608bf62)

Within the Azure VM, right click on the windows icon and click "run" and type "control" to run control panel.

Within the control panel click "Programs" then click "Turn Windows features on or off"

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/1758d703-7478-40b1-9534-cc60d70762e3)

Install/Enable IIS in Windows with "CGI" and "Common HTTP Features" & "IIS Management Console"

Click "Ok" after enabling the folders

Install "PHP Manager" for IIS

Install "Rewrite Module"

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/feea9a40-d9a4-48b4-b56c-8b466cfacc2c)

Create directory "C:\PHP"

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/3b40550c-8d2f-4fa8-9ac7-909e0b5047dd)

Download "PHP 7.3.8" and unzip the contents into "C:\PHP"

Install "VC_redist.x86.exe

Install "MySQL 5.5.62" and configure it as seen in the pictures below

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/e5c7688c-45db-4357-a76f-e232837b2d17)
![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/dc50c6ce-3f18-476f-889d-958b67d576c8)
![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/07143c92-e12e-41a3-915b-57396eeb4ccb)

 - Typical Setup
 - Launch Configuration Wizard (after install)
 - Standard Configuration
 - (any password)

Open IIS as an Admin

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/0586248e-e425-46a6-9457-0d4235eec59e)

Register PHP from within IIS by selecting the PHP exectutable file as seen below

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/9b3657fb-5956-4dde-a1d4-3e7008c43952)

Restart IIS

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/3a3ac9ea-8a38-4bfd-8454-457466a34f13)

Install osTicket v1.15.8
- Download osTicket
- Extract and copy "upload" folder to "c:\inetpub\wwwroot"
- Within "c:\inetpub\wwwroot", rename "upload" to "osTicket"

Restart IIS

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/533b71c6-1a67-4521-85cf-d5a551797453)

Go to sites -> Default -> osTicket
- On the right, click "Browse *.80"


Note some extensions are not enabled
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/16029f26-e518-4626-8449-c784c9bc92ce)
![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/cd2e70f6-82a3-4a6e-9b24-62a14118d9d6)

- Click “Enable or disable an extension”
  - Enable: php_imap.dll
  - Enable: php_intl.dll
  - Enable: php_opcache.dll
- Refresh the osTicket site in your browse, observe the changes

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/07c5469d-5475-4080-993b-c4b84d75e19b)
![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/dd28bdea-f58c-456a-9ea0-965846c536e3)

Rename: ost-config.php
- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config.php

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/d8311939-e10c-440b-bb0f-e19fadc833f6)

- Disable inheritance -> Remove All

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/467d8d72-0815-4d06-ba85-a94336ba3522)
![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/fa81ecd4-13ad-4eec-99b6-771411441619)

- New Permissions -> Everyone -> All

Continue Setting up osTicket in the browser (click Continue)
 - Name Helpdesk
 - Default email (receives email from customers)

Download and install HeidiSQL
 - Open Heidi SQL
 - Create a new session, root/(password you made)
 - Connect to the session
 
![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/dd0e3304-f724-4743-9ea0-62d1f0b56711)
![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/1b615be9-fe18-41cd-8685-890ff164884e)

 - Create a database called “osTicket”

Continue Setting up osticket in the browser

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/182a1949-92ad-4dcc-ae03-6d84709dc056)

 - MySQL Database: osTicket
 - MySQL Username: root
 - MySQL Password: Password1
 - Click “Install Now!”

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/8daf38c4-76f6-4274-8d4c-c0eba9959a17)

If done correctly this image should automatically appear after clicking continue

Clean up
 - Delete: C:\inetpub\wwwroot\osTicket\setup
 - Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
