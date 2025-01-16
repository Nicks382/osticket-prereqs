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

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VS Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
1. The first thing you are going to do is create a virtual machine by going to https://portal.azure.com/. Setup your virtual machine with Windows 10 Pro 22H2, and you'll want to create the virtual machine with at least 2VPCUs and 8 GiB of RAM.
</p>
<br /> 
<p>
2. Once you've created your virtual machine, you will want to connect to it by using the public ip address the VM is setup with. You'll connect using the remote desktop connection app. 
</p>

<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3. Once you hace connected to your virtual machine, you will want to go to your control panel. From the control panel, open up programs. Select, turn Windows features on and off. 
</p>
<p>
4. You'll want to install/enable IIS in Windows in with CGI and Common HTTP Features

  - World Wide Web Services -> Application Development Features -> [X] CGI [X] Common HTTP Features
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<i> NOTE</i> Make sure all Common Features are checked. 

To make sure the IIS is is installed/enabled, go to a browswer of your choice and search for 127.0.0.1. It should look something like this.
</p>
<br />
<p>
5. Now that the IIS i s enabled, from the Installation Files, download and install PHP Manager fro IIS (PHPManagerForIIS_V1.5.0.msi), go throught he install wizard and complete the install. 
</p>
<br />
<p>
6. Next from the Installation Flies, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<br />
<p>
7. Create a folder in the C drive called PHP.
</p>
<br />
<p>
8. From the installation Flies, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP
</p>
<br />
<p>
!! ATTENTION !! If this appears, choose to "Keep" the file:
</p>

<br />

<p>
9. Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe
</p>
<br />
<p>
10. Download and install MYSQL 5.5.62 (mysql-5.5.62-win32.msi) Run the setup wizard. Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->
</p>
<br />
<p>
Make the new root password: Password1
</p>
<br />
<p>
Execute the process on the next page. 
</p>
