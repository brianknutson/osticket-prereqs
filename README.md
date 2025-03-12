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
- Microsoft Azzure Virtual Machine (vm) 
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>



<p>
<img src="https://i.imgur.com/Ne7hBvV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 1 - In this tutorial, Microsoft Azure will be used to set up the osTicket system. A virtual machine (vm) will be created along with a resource group within Azure. The resource group will be created when creating the vm. In this case, a Microsoft Windows 10, 4 vCPUs virtual machine will be used. 
</p>
<br />

<p>
<img src="https://i.imgur.com/m4WRErw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 2 - Next, login into the virtual machine (vm) using Remote Desktop Connection. Use the public IP address for the computer. Then use the username and password you used to set up the vm to login. 
</p>
<br />

<p>
<img src="https://i.imgur.com/Wd6XcHM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3 - Install and enable IIS (Internet Information Services) in Windows with CGI. To accomplish this, go to the control panel and press "Uninstall a program". Then press "Turn Windows features on or off". Look up Interent Information Sevices and check the box to the left. Afterwards,  press on World Wide Web Services then Application Development Features to check the box for CGI. Press "OK" and wait for CGI to load. CGI is one of the dependents osTicket needs for part of the web sever.  
</p>
<br />

<p>
<img src="https://imgur.com/EyyYfyB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3.2 - To insure Step 3 was done correctly, go to a web brower and type 127.0.0.1, which is a the IP address for a computer's local network otherwise known as a loopback address. A similar image should appear if Step 3 was followed.   
</p>
<br />

<p>
<img src="https://i.imgur.com/Wd6XcHM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 4 - Install PHP Manager for IIS. PHP Manager is a tool that allows administrators and developers to manage and configure PHP installations on a Windows server running IIS. PHP Manager is needed for IIS to run properly.    
</p>
<br />

<p>
<img src="https://i.imgur.com/ufrM1A0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 5 - Install Rewrite Module, which is another tool needed for IIS to run properly.     
</p>
<br />

<p>
<img src="https://i.imgur.com/y63h6hL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 6 - Create a folder in the C drive of the computer called "PHP". Then unzip PHP 7.3.8 into the folder "PHP" that was created. 
</p>
<br />

<p>
<img src="https://i.imgur.com/4OU3UPu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 7 - Install VC_redist.x86.exe, which is another program needed for osTicket to work. 
</p>
<br />

<p>
<img src="https://i.imgur.com/76AVSm8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 8 - Install MySQL 5.5.62., which is a database that osTicket will use to store all the data in (users' accounts, ticketing information, etc.). When choosing the setup type when installing MySQL, make sure to choose the "Typical" settings. Next check the "Launch the MySQL Instance Configuration Wizard" before clicking finish. After when asked for a configuration type, choose "Standard Configuration". When asked to "Please set the Windows Options", just press "Next". Then, choose a password then press "Next". Finally, press "Execute".  
</p>
<br />

<p>
<img src="https://i.imgur.com/vI4eluC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 9 - Open IIS as an Admin. Then register PHP from within IIS, which will make the website server aware of the existence of the PHP on the computer. To register PHP, press "PHP Manager" then press "Register new PHP version". Next browse to the PHP folder in the C drive then press "php-cgi". Finally, press "OK". 
</p>
<br />

<p>
<img src="https://i.imgur.com/kGGZTRv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 10 - Reload IIS by pressing the "Stop" then "Start", which are actions on the right side. 
</p>
<br />

<p>
<img src="https://i.imgur.com/cUbcJ8e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/fgACiLf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 11 - Install osTicket v1.15.8 by first extracting the files. Go to the file "osTicket v1.15.8 then copy the “upload” folder into “c:\inetpub\wwwroot”. After rename “upload” to “osTicket” exactly. 
</p>
<br />

<p>
<img src="https://i.imgur.com/kGGZTRv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 12 - Once again reload IIS by pressing the "Stop" then "Start", which are actions on the right side. 
</p>
<br />

<p>
<img src="https://i.imgur.com/kmsnD6l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/HF4If2Q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 13 - Within the IIS Manager,  go to "Sites" then "Default" then "osTicket". On the right, click “Browse *:80” to go to the osTicket website. If the osTicket website doesn't show up, there was most likely a mistake along the way. It may be best to start all over if you cannot determine the issue. Note that some extensions are not enabled such as "php_imap.dll", "php_intl.dll", and "php_opcache.dll". These will need to be enable. 
</p>
<br />

<p>
<img src="https://i.imgur.com/qauOm5P.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/v8rpi5U.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 14 - To enable those extensions. Go back to IIS, click on "Sites" then "Default" then "osTicket" then double-click PHP Manager. Then click "Enable or disable an extension". Next, enable "php_imap.dll", "php_intl.dll", and "php_opcache.dll".  
</p>
<br />
