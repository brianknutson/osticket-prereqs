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
- Item 2
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
<img src="https://i.imgur.com/N4bOKV7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3 - Install and enable IIS (Internet Information Services) in Windows with CGI. To accomplish this, go to the control panel and press "Uninstall a program". Then press "Turn Windows features on or off". Look up Interent Information Sevices and check the box to the left. Afterwards,  press on World Wide Web Services then Application Development Features to check the box for CGI. Press "OK" and wait for CGI to load. CGI is one of the dependents osTicket needs for part of the web sever.  
</p>
<br />

<p>
<img src="https://i.imgur.com/N4bOKV7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Step 3 - Install and enable IIS (Internet Information Services) in Windows with CGI. To accomplish this, go to the control panel and press "Uninstall a program". Then press "Turn Windows features on or off". Look up Interent Information Sevices and check the box to the left. Afterwards,  press on World Wide Web Services then Application Development Features to check the box for CGI. Press "OK" and wait for CGI to load. CGI is one of the dependents osTicket needs for part of the web sever.  
</p>
<br />
