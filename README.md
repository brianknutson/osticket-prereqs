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
Step 8 - Install MySQL 5.5.62., which is a database that osTicket will use to store all the data in (users' accounts, ticketing information, etc.). When choosing the setup type when installing MySQL, make sure to choose the "Typical" settings. Next check the "Launch the MySQL Instance Configuration Wizard" before clicking finish. After when asked for a configuration type, choose "Standard Configuration". When asked to "Please set the Windows Options", just press "Next". Then, choose a password then press "Next". Finally, press "Execute". You will need this username and password for Step 18. 
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
<p>
<img src="https://i.imgur.com/tTT4itq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
Step 14 - To enable those extensions. Go back to IIS, click on "Sites" then "Default" then "osTicket" then double-click PHP Manager. Then click "Enable or disable an extension". Next, enable "php_imap.dll", "php_intl.dll", and "php_opcache.dll". Finally, refresh the osTicket site in your browser. It should look like the picture of the osTicket website above after enabling those extensions.  
</p>
<br />

<p>
<img src="https://i.imgur.com/zjWpMvp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/bOnlgQy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 15 - Go to C:\inetpub\wwwroot\osTicket\include. Then find the file ost-sampleconfig.php then rename it to ost-config.php. 
</p>
<br />

<p>
<img src="https://i.imgur.com/zgeCwN8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/3hq3jCV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 16 - Permissions need to be assigned to file "ost-config.php", so osTicket can make changes to that file. First, go to "properties" then "Security" then "Advance". Within the "Advance Security Settings", click "Disable inhertitance" then click "Remove all inherited permissions from this object". After, click "Add" then click "Select a principal". For the purposes of this tutorial, type "Everyone" under "Enter the object's name to select" then click "Check Names" then "OK". Under normal circumstances, this would be bad practice because it can pose a security risk. Next, under "Basic Permissions", click "Full Controll". After press "OK". Finally, click "Apply" then "OK".   
</p>
<br />

<p>
<img src="https://i.imgur.com/hfnUyf7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 17 - Go back to the osTicket website to continue setting up osTicket in the browser. Click "Continue". Now fill out the information until "Database Settings". Note that the Default email must be different from the admin email. 
</p>
<br />

<p>
<img src="https://i.imgur.com/ZvcTnDk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/wffgZi5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/JrSEyLI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
Step 18 - Before clicking on "Install Now", we still need to login into the database to create another database specific for osTicket. Afterwards, we need to provide the credentials for it. Install HeidiSQL, which will allow us to make a connection to our database. From the “osTicket-Installation-Files” folder, install HeidiSQL. Keep pressing "Next" until you see "Install". Then click "Install." Make sure there is a check mark next to "Launch HeidiSQL" then click "Finish". After HeidiSQL opens, click on "New" then fill out the username and password you used for in Step 8. Then press "Open", which will open a connection to our database. Next right-click on "Unnamed" then "Create new" then "Database". The name of the database must be osTicket. Finally click "OK". Now "osticket" should be under "Unnamed".  
</p>
<br />

<p>
<img src="https://i.imgur.com/fMF4kmg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/dNT0yVq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 19 - Go back to the osTicket webiste to continue Setting up osTicket in the browser. Fill out the "Database Settings" portion. Afterwards, click "Install Now". If you go back to HeidiSQL to the database "osticket", "osticket" should be filled with content like the picture above. Congrats! osTicket should be installed  with no errors.  
</p>
<br />

<p>
<img src="https://i.imgur.com/oaibl2q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/z7krNCP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 20 - Finally, go to http://localhost/osTicket/scp/login.php to see if you can login. If you login successfully, the page should look similar to the picture above.
</p>
<br />
