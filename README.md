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
5. Now that the IIS i s enabled, from the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi), go through the install wizard and complete the install. 
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
<br />
<p>
11. Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar. Open IIS as an administrator. The program should look like this.
</p>
<br />
<p>
12. We will now want to register PHP from within IIS. Click on PHP Manager
</p>
<br />
<p>
Register new PHP version.
</p>
<br />
<p>
You will want to provide a path to the php executable file (php-cgi.exe). Go to C drive -> PHP -> click on php-cgi file. 
</p>
<br />
<p>
Restart the IIS server.
</p>
<br />
<p>
13. Install osTicket v1.15.8 -Download osTicket from the Installation Files Folder -Extract and copy "upload" folder to c:\inetpub\wwwroot -Within c:\inetpub\root, Rename "upload" to "osTicket"

Reload IIS again.
</p>
<br />
<p>
14. On IIS go to sites -> Defualt -> osTicket -On the right, click "Browse *80."

Some extensions are not enabled on the osTicket browser.

To enable the extensions: -Go back to IIS, sites -> Default -> osTicket -Doble click PHP Manager -Click "Enable or disable an extension"
</p>
<br />
<p>
We will want to enable three extensions from here.

1. php_imap.dll
2. php_intl.dll
3. php_opcache.dll
   
</p>
<br />
<p>
15. Once we have those extensions in IIS, we are going to want to rename one of the files in our osTicket folder. Go into the file explorer and search C:\inetpub\wwwroor\osTicket\include\ost-sampleconfig.php

We are going to rename the ost-sampleconfig.php to ost-config.php

Now that we have rename the files, right click on the file and go to properties. From there click security click on advance and disable the inheritance. We will select "Remove all inherited permissions" from this object

Click Add

Select a prinicpal

Type "Everyone" in the box.

Make sure "Full Control" and all other boxes are checked. 

Click Apply and Ok

Once that is done we will contine to setup osTicket in the browser. Click Continue onn the osTicket browser page. Fill out the page as required except the Database Settings at the bottom of the page. We will get to that. 

We will want to download and install HeidiSQL from the Installation Files.

When the program is open we will create a new session in it.

Once we are conncted to the session we will go back to the browser to finish setting everything up. Under the Database Settings in the browser the username will be "root" and the password will be "Password1"

We will now create a new database within HeidiSQL. in Heidi right click on the left side where it says "Unnamed", select "create new, and then select "database. Name the new database osTicket. Once we have the new database setup, go back to the osTicket browser and under MySQL Database, type in "osTicket".

The last step is to do some clean up. We will want to delete the setupd folder in our system. -Delete: C:\inetpub\wwwroor\osTicket\setup. ONly delete the setup folder and nothing else. 

We then will want to set the permissions back to "Read" only in the ost-config.php file.

The last step after that is to login to osTicket on the browser. 

Congrats! You have now successfully installed and setup osTicket!
</p>
