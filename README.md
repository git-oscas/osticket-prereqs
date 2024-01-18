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
- Create directory C:\PHP, Download PHP 7.3.8 unzip contents into C:\PHP
- Download VC_redist.x86.exe
- Download MySQL 5.5.62
- Download osTicket v1.15.8
- Download HeidiSQL

<h2>Installation Steps</h2>

Install / Enable IIS in Windows with CGI and Common HTTPS Features and IIS Management Console (in Web Management Tools)

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/54911f13-3a72-4cdb-a084-f2db5adf800e)

osTicket runs out of a website which is why it is important to setup and configure IIS in order to run osTicket

- Install PHP Manager for IIS
- Install Rewrite Module
- Create directory C:\PHP, install PHP 7.3.8 unzip contents into C:\PHP
- Install VC_redist.x86.exe
- Install MySQL 5.5.62 and configure during setup

Open IIS as an Admin and register PHP from within IIS

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/7c00b5a8-be62-40a9-9dae-aac5555ef6a2)

Register a new PHP version to enable PHP via FastCGI (which we installed during the setup of IIS)

Restart IIS

Install osTicket v1.15.8
- Download osTicket from the Installation Files Folder
- Extract and copy “upload” folder to c:\inetpub\wwwroot
- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”

Restart IIS

Go to sites -> Default -> osTicket
- On the right, click “Browse *:80”

Note that some extensions are not enabled
- Go back to IIS, sites -> Default -> osTicket
- Double-click PHP Manager
- Click “Enable or disable an extension”

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/1642f2da-1880-447b-8e4b-117b1c492b8c)

Enable the extensions highlighted in the picture above for improvements recommended by osTicket

Refresh the osTicket site in your browser and observe the changes

Rename: ostconfig.php
- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions: ost-config-php
- Disable inheritance -> Remove All
- New Permissions -> Everyone -> All

Continue setting osTicket up in the browser (click continue)

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/2c85c112-2930-4a39-b2cb-8bfddec547bd)

Install HeidiSQL, create and connect to the session, then create a database called "osTicket" (as seen in picture above)

Continue setting up osTicket in the browser and click "Install Now!"

![image](https://github.com/git-oscas/osticket-prereqs/assets/156957308/dbb46ab2-0b7a-43e3-a1b3-c1f8dc101c9d)

If done correctly, the page above will be displayed soon after.
