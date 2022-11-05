<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- osTicket
- HeidiSQL
- PHPManager
- Web Platformer
- vcredist
- mysql-5.5.62
- php.7.3.8

Download them all [here](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).

<h2>Installation Steps</h2>
Part 1: Create Virtual Machine in Azure

- Create a Resource Group
- Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPU's 
- When creating the VM, allow it to create a new Virtual Network a.k.a. VNET



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Part 2: Installation
  
  
- Connect to your Virtual Machine with Remote Desktop
- Install / Enable IIS in Windows
- Install Web Platform Installer (download from within lab files: link)
  
    - Open after installation
    - Add MySQL 5.5 (it will ask for credentials to be created later)
      - Name: root
      - Password: "Your Password"
    - Add All simple versions of x86 PHP up until 7.3
    - Fix any failures if required (download from within lab files: link)
- Install PHP Version 7.3.8 (or any other version if necessary, archives)
- Install PHP Manager 1.5.0 for IIS 10 (folder you unzipped on the desktop)
- Install Microsoft Visual C++ 2009 Redistributable Package
- Install osTicket v1.15.8
    - Download osTicket (download from within lab files: link)
    - Extract and copy the “upload” folder INTO c:\inetpub\wwwroot
    - Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”
- Reload IIS (Open IIS, Stop and Start the server)
    - Go to sites -> Default -> osTicket
    - On the right, click “Browse *:80”
- Enable Extensions in IIS: Note that some extensions are not enabled
  - Go back to IIS, sites -> Default -> osTicket
  - Double-click PHP Manager
  - Click “Enable or disable an extension”
    - Enable: php_imap.dll
    - Enable: php_intl.dll
    - Enable: php_opcache.dll
- Refresh the osTicket site in your browse, observe the changes
- Rename:
	- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
	- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
- Assign Permissions: ost-config.php
    - Disable inheritance -> Remove All
    - New Permissions -> Everyone -> All
- Continue Setting up osTicket in the browser (click Continue)
    - Name Helpdesk
    - Default email (receives email from customers)
- Download and Install HeidiSQL (download from within lab files: link)
    - Create a new session, root/Password1
    - Connect to the session
    - Create a database called “osTicket”
- Continue Setting up osticket in the browser
- MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: "Your Password"
Click “Install Now!”
Congratulations, hopefully it is installed with no errors!
Part 3: Clean up
  - Delete: C:\inetpub\wwwroot\osTicket\setup
  - Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
  - Login to the osTicket Admin Panel (http://localhost/osTicket/scp/login.php)

Notes:
Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
End Users osTicket URL: http://localhost/osTicket/ 
  
  
  Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
