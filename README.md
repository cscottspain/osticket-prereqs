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
<p>
<img src="https://i.imgur.com/1NvBOtA.png" alt="Azure Virtual Machine Window"/>
</p>
<p>

- Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPU's 
- When creating the VM, allow it to create a new Virtual Network a.k.a. VNET



<p>
<img src="https://i.imgur.com/QpqqamL.png" alt="Azure Virtual Machine Window"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/iUKdfks.png" alt="Azure Virtual Machine Details Window"/>
</p>
<p>
<img src="https://i.imgur.com/Rz130YK.png" alt="Azure Virtual Machine Details Window 2"/>
</p>
<p>
Part 2: Installation
  
  
- Connect to your Virtual Machine with Remote Desktop
- Install / Enable IIS in Windows
<p>
<img src="https://i.imgur.com/70QjWeh.png" alt="IIS Enable Window"/>
</p>
<ul>
    <li>
        <p>Install Web Platform Installer (download from within lab files:&nbsp;<a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">link</a>)</p>
        <ul>
          <p>
<img src="https://i.imgur.com/0n9Lt3g.png" alt="Web Platform Installer Icon"/>
</p>
            <li>
                <p>Open after installation</p>
            </li>
            <li>
                <p>Add MySQL 5.5 (it will ask for credentials to be created later)</p>
                <ol>
                  <a href="https://imgur.com/RBSA200"><img src="https://i.imgur.com/RBSA200.png" title="source: imgur.com" /></a>
                    <li>
                        <p>Name: root</p>
                    </li>
                    <li>
                        <p>Password: Password1</p>
                    </li>
                </ol>
            </li>
            <li>
                <p>Add All simple versions of x86 PHP up until 7.3</p>
            </li>
<a href="https://imgur.com/VxkybZd"><img src="https://i.imgur.com/VxkybZd.png" title="source: imgur.com" /></a>            <li>
                <p>Fix any failures if required (download from within lab files:&nbsp;<a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">link</a>)</p>
                <ul>
                    <li>
                        <p>Install PHP Version 7.3.8 (or any other version if necessary,&nbsp;<a href="https://windows.php.net/downloads/releases/archives/">archives</a>)</p>
                    </li>
                    <li>
                        <p>Install PHP Manager 1.5.0 for IIS 10 (folder you unzipped on the desktop)</p>
                    </li>
                    <li>
                        <p>Install Microsoft Visual C++ 2009 Redistributable Package</p>
                    </li>
                </ul>
            </li>
        </ul>
    </li>
    <li>
        <p>Install osTicket v1.15.8</p>
        <ul>
            <li>
                <p>Download osTicket (download from within lab files:&nbsp;<a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">link</a>)</p>
            </li>
            <li>
                <p>Extract and copy the &ldquo;upload&rdquo; folder INTO c:\inetpub\wwwroot</p>
            </li>
            <li>
                <p>Within c:\inetpub\wwwroot, Rename &ldquo;upload&rdquo; to &ldquo;osTicket&rdquo;</p>
            </li>
        </ul>
    </li>
    <li>
        <p>Reload IIS (Open IIS, Stop and Start the server)</p>
        <ul>
            <li>
                <p>Go to sites -&gt; Default -&gt; osTicket</p>
            </li>
            <li>
                <p>On the right, click &ldquo;Browse *:80&rdquo;</p>
            </li>
        </ul>
    </li>
    <li>
        <p>Enable Extensions in IIS: Note that some extensions are not enabled</p>
        <ul>
            <li>
                <p>Go back to IIS, sites -&gt; Default -&gt; osTicket</p>
            </li>
            <li>
                <p>Double-click PHP Manager</p>
            </li>
            <li>
                <p>Click &ldquo;Enable or disable an extension&rdquo;</p>
                <ul>
                    <li>
                        <p>Enable: php_imap.dll</p>
                    </li>
                    <li>
                        <p>Enable: php_intl.dll</p>
                    </li>
                    <li>
                        <p>Enable: php_opcache.dll</p>
                    </li>
                </ul>
            </li>
        </ul>
    </li>
    <li>
        <p>Refresh the osTicket site in your browse, observe the changes</p>
    </li>
    <li>
        <p>Rename:<br>&nbsp; &nbsp;&nbsp;From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php<br>&nbsp; &nbsp;&nbsp;To: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
    </li>
    <li>
        <p>Assign Permissions: ost-config.php</p>
        <ul>
            <li>
                <p>Disable inheritance -&gt; Remove All</p>
            </li>
            <li>
                <p>New Permissions -&gt; Everyone -&gt; All</p>
            </li>
        </ul>
    </li>
    <li>
        <p>Continue Setting up osTicket in the browser (click Continue)</p>
        <ul>
            <li>
                <p>Name Helpdesk</p>
            </li>
            <li>
                <p>Default email (receives email from customers)</p>
            </li>
        </ul>
    </li>
    <li>
        <p>Download and Install HeidiSQL (download from within lab files:&nbsp;<a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">link</a>)</p>
        <ul>
            <li>
                <p>Create a new session, root/Password1</p>
            </li>
            <li>
                <p>Connect to the session</p>
            </li>
            <li>
                <p>Create a database called &ldquo;osTicket&rdquo;</p>
            </li>
        </ul>
    </li>
    <li>
        <p>Continue Setting up osticket in the browser</p>
    </li>
    <li>
        <p>MySQL Database: osTicket</p>
        <ul>
            <li>
                <p>MySQL Username: root</p>
            </li>
            <li>
                <p>MySQL Password: Password1</p>
            </li>
        </ul>
    </li>
    <li>
        <p>Click &ldquo;Install Now!&rdquo;</p>
    </li>
    <li>
        <p>Congratulations, hopefully it is installed with no errors!</p>
    </li>
    <li>
        <p>Clean up</p>
        <ul>
            <li>
                <p>Delete: C:\inetpub\wwwroot\osTicket\setup</p>
            </li>
            <li>
                <p>Set Permissions to &ldquo;Read&rdquo; only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
            </li>
        </ul>
    </li>
    <li>
        <p>Login to the osTicket Admin Panel&nbsp;(<a href="http://localhost/osTicket/scp/login.php">http://localhost/osTicket/scp/login.php</a>)</p>
    </li>
</ul>
<p><br></p>
<p>Notes:</p>
<ul>
    <li>
        <p>Browse to your help desk login page:&nbsp;<a href="http://localhost/osTicket/scp/login.php">http://localhost/osTicket/scp/login.php</a> &nbsp;</p>
    </li>
    <li>End Users osTicket URL:&nbsp;<a href="http://localhost/osTicket/">http://localhost/osTicket/</a>&nbsp;</li>
</ul>
