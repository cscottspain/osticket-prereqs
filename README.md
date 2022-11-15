<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### (COMING SOON!) [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

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
          <a href="https://imgur.com/KRjgavx"><img src="https://i.imgur.com/KRjgavx.png" title="source: imgur.com" /></a>      
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
       <ul dir="auto">
    <li>
        <p dir="auto">Install osTicket v1.15.8</p>
        <ul dir="auto">
            <li>
                <p dir="auto">Download osTicket (download from within lab files: <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6" rel="nofollow">link</a>)</p>
            </li>
            <li>
                <p dir="auto">Extract and copy the &ldquo;upload&rdquo; folder INTO c:\inetpub\wwwroot</p>
            </li>
            <li>
                <p dir="auto">Within c:\inetpub\wwwroot, Rename &ldquo;upload&rdquo; to &ldquo;osTicket&rdquo;</p>
            </li>
        </ul>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668470640.png" width="660" height="455"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668470659.png" width="677" height="536"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668470685.png" width="652" height="532"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Reload IIS (Open IIS, Stop and Start the server)</p>
        <ul dir="auto">
            <li>
                <p dir="auto">Go ** sites -&gt; Default -&gt; osTicket</p>
            </li>
            <li>
                <p dir="auto">On the right, click &ldquo;Browse *:80&rdquo;</p>
            </li>
        </ul>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668470762.png" width="883" height="630"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471245.png" width="883" height="864"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Enable Extensions in IIS: Note that some extensions are not enabled</p>
        <ul dir="auto">
            <li>
                <p dir="auto">Go back to IIS, sites -&gt; Default -&gt; osTicket</p>
            </li>
            <li>
                <p dir="auto">Double-click PHP Manager</p>
            </li>
            <li>
                <p dir="auto">Click &ldquo;Enable or disable an extension&rdquo;</p>
                <ul dir="auto">
                    <li>
                        <p dir="auto">Enable: php_imap.dll</p>
                    </li>
                    <li>
                        <p dir="auto">Enable: php_intl.dll</p>
                    </li>
                    <li>
                        <p dir="auto">Enable: php_opcache.dll</p>
                    </li>
                </ul>
            </li>
        </ul>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668470961.png" width="598" height="653"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668470973.png" width="418" height="409"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Refresh the osTicket site in your browse, observe the changes</p>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471002.png" width="327" height="149"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Rename:<br>&nbsp; &nbsp; From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php<br>&nbsp; &nbsp; To: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471021.png" width="499" height="374"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471035.png" width="498" height="366"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Assign Permissions: ost-config.php</p>
        <ul dir="auto">
            <li>
                <p dir="auto">Disable inheritance -&gt; Remove All</p>
            </li>
            <li>
                <p dir="auto">New Permissions -&gt; Everyone -&gt; All</p>
            </li>
        </ul>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471138.png" width="696" height="466"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471150.png" width="604" height="408"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471161.png" width="718" height="463"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471171.png" width="361" height="201"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471181.png" width="604" height="409"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Continue Setting up osTicket in the browser (click Continue)</p>
        <ul dir="auto">
            <li>
                <p dir="auto">**** Helpdesk</p>
            </li>
            <li>
                <p dir="auto">Default email (receives email from customers)</p>
            </li>
        </ul>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471324.png" width="1536" height="864"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471346.png" width="883" height="864"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Download and install HeidiSQL (download from within lab files: <a href="https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6" rel="nofollow">link</a>)</p>
        <ul dir="auto">
            <li>
                <p dir="auto">Create a new session, root/&quot;Password&quot;</p>
            </li>
            <li>
                <p dir="auto">Connect to the session</p>
            </li>
            <li>
                <p dir="auto">Create a database called &ldquo;osTicket&rdquo;</p>
            </li>
        </ul>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471718.png" width="735" height="468"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Continue Setting up osTicket in the browser</p>
    </li>
    <li>
        <p dir="auto">MySQL Database: osTicket</p>
        <ul dir="auto">
            <li>
                <p dir="auto">MySQL Username: root</p>
            </li>
            <li>
                <p dir="auto">MySQL Password: &quot;Password&quot;</p>
            </li>
        </ul>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471825.png" width="883" height="792"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Click &ldquo;Install Now!&rdquo;</p>
    </li>
    <li>
        <p dir="auto">Congratulations, hopefully it is installed with no errors!</p>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471860.png" width="650" height="499"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Clean up</p>
        <ul dir="auto">
            <li>
                <p dir="auto">Delete: C:\inetpub\wwwroot\osTicket\setup</p>
            </li>
            <li>
                <p dir="auto">Set Permissions to &ldquo;Read&rdquo; only: C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
            </li>
        </ul>
    </li>
</ul>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668471954.png" width="603" height="618"></p>
<p><img src="https://myfiles.space/user_files/136342_a1cddde58552a220/136342_custom_files/img1668472027.png" width="883" height="864"></p>
<ul dir="auto">
    <li>
        <p dir="auto">Login to the osTicket Admin Panel&nbsp;(<a href="http://localhost/osTicket/scp/login.php" rel="nofollow">http://localhost/osTicket/scp/login.php</a>)</p>
    </li>
</ul>
<p dir="auto">Notes:</p>
<ul dir="auto">
    <li>
        <p dir="auto">Browse to your help desk login page: <a href="http://localhost/osTicket/scp/login.php" rel="nofollow">http://localhost/osTicket/scp/login.php</a> &nbsp;</p>
    </li>
    <li>End Users osTicket URL: <a href="http://localhost/osTicket/" rel="nofollow">http://localhost/osTicket/</a>&nbsp;</li>
</ul>
