<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This demonstration shows the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine 
- Microsoft Azzure Virtual Machine (vm)
  

<h2>Installation Steps</h2>


Step 1 - Microsoft Azure will be used in this demonstration to set up the osTicket system. A virtual machine (VM) was created along with a resource group within Azure. The resource group was made when creating the VM. In this case, a Microsoft Windows 10 Pro virtual machine was used.

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/919387f5146c86c6fe536071f3170d44c52246e7/Screenshot%202025-07-13%20142742.png)



Step 2 - Next, I logged into the virtual machine (VM) using Remote Desktop Connection. Used the computer's public IP address. Then, use the username and password I used to set up the VM to log in. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/716f013cde383dfb603b53cb3258684fb48989f3/Step2.png)



Step 3 - I installed and enabled IIS (Internet Information Services) in Windows with CGI. To accomplish this, I went to the control panel and press "Uninstall a program". Then press "Turn Windows features on or off". I looked up Internet Information Services and check the box to the left. Afterward, I press on "World Wide Web Services" and then "Application Development Features" to check the box for CGI. Finally, I pressed "OK" and waited for CGI to load. 

CGI is one of the dependents osTicket needs for part of the web server.  

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/7aa0767f48d6c4497d0e259ffcd24d1dbbbaf213/3.PNG)



Step 3.2 - To ensure 'Step 3' was done correctly, I went to a web browser and type 127.0.0.1, which is an IP address for a computer's local network otherwise known as a loopback address. With the following image, I know 'Step 3' was done correctly. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/c993144cc35e89945b010320ad81bcfce3d8dbd6/4.PNG)



Step 4 - I installed PHP Manager for IIS. PHP Manager is a tool that allows administrators and developers to manage and configure PHP installations on a Windows server running IIS. PHP Manager is needed for IIS to run properly.    

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/0d01e14343753edc07333266d939ad7a15c5c846/5.PNG)



Step 5 - I installed Rewrite Module, which is another tool needed for IIS to run properly.     
![image alt](https://github.com/brianknutson/osticket-prereqs/blob/1c4226490f3f55906238ccb700af4512ae0304fe/5.5.PNG)



Step 6 - I created a folder in the C: Drive of the computer called "PHP". Next, I unziped PHP 7.3.8 into the folder "C:\PHP folder" that was created. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/ce7e40a294a130671d8d95ce8cd604f7cb3a9aaf/6.PNG)



Step 7 - I installed VC_redist.x86.exe, which is another program needed for osTicket to work. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/b1a4c9a05887bbf6b098a8152520be3e46e0e2c1/7.PNG) 



Step 8 - I installed MySQL 5.5.62., which is a database that osTicket will use to store all the data (users' accounts, ticketing information, etc.). When choosing the setup type when installing MySQL, I made sure to choose the "Typical" settings. Next, I checked the "Launch the MySQL Instance Configuration Wizard" before clicking finish. After when asked for a configuration type, I chose "Standard Configuration". When asked to "Please set the Windows Options", again I pressed "Next". Then, I chose a password and afterward pressed "Next". Finally, I pressed "Execute". I will use this username and password for Step 18. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/b5e58ec9abdaf520187554d0d1bddd07fdec5d4b/8.PNG)



Step 9 - Opening IIS as an Admin. I registered PHP from within IIS, which will make the website server aware of the existence of the PHP on the computer. To registered PHP, I pressed "PHP Manager" then pressed "Register new PHP version". Next, I browsed to "C:\PHP folder" then pressed "php-cgi". Finally, I pressed "OK". 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/81db5ae96a687308cb7e4e71041f939f538e473d/9.PNG)

Step 10 - I reloaded IIS by pressing the "Stop" and then "Start", which are actions on the right side. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/81db5ae96a687308cb7e4e71041f939f538e473d/10.PNG)

Step 11 - I installed osTicket v1.15.8 by first extracting the files. Then I went to the file "osTicket v1.15.8" then copy the "upload" folder into "c:\inetpub\wwwroot". Afterwards, I renamed "upload" to "osTicket". 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/81db5ae96a687308cb7e4e71041f939f538e473d/11.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/81db5ae96a687308cb7e4e71041f939f538e473d/11.5.PNG)

Step 12 - Once again reload IIS by pressing the "Stop" and then "Start", which are actions on the right side. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/81db5ae96a687308cb7e4e71041f939f538e473d/10.PNG)

Step 13 - Within the IIS Manager,  I went to "Sites" then "Default" then "osTicket". On the right, I clicked “Browse *:80” to go to the osTicket website. Some extensions are not enabled such as "php_imap.dll", "php_intl.dll", and "php_opcache.dll". These will be enabled in the following steps. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/ecbb4e2371dd88ef5bcec70b9c11a9747863f619/12.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/ecbb4e2371dd88ef5bcec70b9c11a9747863f619/12.5.PNG)

Step 14 - To enable those extensions. I went back to IIS, clicked on "Sites" then "Default" then "osTicket" and then double-clicked PHP Manager. Then I clicked "Enable or disable an extension". 

Next, I enabled "php_imap.dll", "php_intl.dll", and "php_opcache.dll". 

Finally, I refreshed the osTicket site in my browser to ensure that those extensions were enabled.  

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/3324a3887a7619fc657b1b81852939e88adeeeac/14.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/3324a3887a7619fc657b1b81852939e88adeeeac/14.2.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/3324a3887a7619fc657b1b81852939e88adeeeac/14.3.PNG)

Step 15 - I went to C:\inetpub\wwwroot\osTicket\include. Next, I found the file ost-sampleconfig.php then renamed it to ost-config.php. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/39248810311c805a932b3b9b3b39a871f5eff335/15.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/39248810311c805a932b3b9b3b39a871f5eff335/15.5.PNG)

Step 16 - Permissions need to be assigned to file "ost-config.php", so osTicket can make changes to that file. First, I went to "Properties" then "Security" then "Advance". Within the "Advance Security Settings", I clicked "Disable Inheritance" then clicked "Remove all inherited permissions from this object". 

After, I clicked "Add" and then clicked on "Select a principal". For this demonstration, I typed "Everyone" under "Enter the object's name to select" then clicked "Check Names" then "OK". Under normal circumstances, this would be considered bad practice because it can pose a security risk. Next, under "Basic Permissions", I clicked "Full Control". After, I pressed "OK". Finally, I clicked "Apply" then "OK".   

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/c22ca761f35dc4f28224c32ea5ca972fbc6642d2/16.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/c22ca761f35dc4f28224c32ea5ca972fbc6642d2/16.5.PNG)

Step 17 - I went back to the osTicket website to continue setting up osTicket in the browser. I clicked "Continue". Then I filled out the information until "Database Settings". Note that the Default email must be different from the admin email. 

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/5bf2bf5227b9719494d7b7375a8732396a31ed0b/17.PNG)

Step 18 - Before clicking on "Install Now", I still need to log into the database to create another database specific to osTicket. Afterwards, I need to provide the credentials for it. I installed HeidiSQL, which will allow me to make a connection to the database. From the “osTicket-Installation-Files” folder, I installed HeidiSQL. I kept pressing "Next" until I saw "Install". Then I clicked "Install." I made sure there is a checkmark next to "Launch HeidiSQL" then I clicked "Finish". 

After HeidiSQL opens, I clicked on "New" then fill out the username and password I used in Step 8. 

Then I pressed "Open", which will open a connection to our database. Next, I right-clicked on "Unnamed" then "Create new" then "Database". The name of the database must be osTicket. Finally, I clicked "OK". Now "osticket" will be under "Unnamed".  

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/7f1e3f30b12145f3c5dfdecaac27cf639ad6163d/18.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/7f1e3f30b12145f3c5dfdecaac27cf639ad6163d/18.5.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/7f1e3f30b12145f3c5dfdecaac27cf639ad6163d/18.8.PNG)

Step 19 - I went back to the osTicket website to continued setting up osTicket in the browser. I filled out the "Database Settings" portion. Afterward, I clicked "Install Now".

When I went to go back to HeidiSQL to the database "osticket", "osticket" was filled with content like the picture below. Now osTicket is installed with no errors.  

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/96712a03fcf5852a67d91c3f799af6d361833f3b/19.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/96712a03fcf5852a67d91c3f799af6d361833f3b/19.5.PNG)

Step 20 - Finally, I went to http://localhost/osTicket/scp/login.php to see if you can log in. 

When I logged in successfully, the page looked like the picture below.

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/71f8c5898c6e1e25007402b19b4f6d380386aba8/20.PNG)

![image alt](https://github.com/brianknutson/osticket-prereqs/blob/71f8c5898c6e1e25007402b19b4f6d380386aba8/20.5.PNG)
