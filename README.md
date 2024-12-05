<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/watch?v=K7T_JjvEamg)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Files
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>
To install osTicket on Virtual Machine you need to create one from Azure
<p>
<img width="1276" alt="image" src="https://github.com/user-attachments/assets/dbca973f-85b9-479a-bcfb-40e3e587a3d2">
<img width="292" alt="image" src="https://github.com/user-attachments/assets/9612bca2-4287-401b-a533-15f917cad20e">
</p>
<p>
Once you log in to Azure, you simply click on virtual machine then hit create and click on Azure virtual machine.
</p>
<br />
<img width="614" alt="image" src="https://github.com/user-attachments/assets/e29a5d50-78dd-4b5e-bf54-283d136278c1">
</p>
Next you need to create new resource group (which is a container that hold resources in Azure or "Folder").
</p>
<img width="608" alt="image" src="https://github.com/user-attachments/assets/3eeb22ab-60a7-41c4-9224-3898e4d7efc6">
</p>
Create your virtual machine name. Then pick your time zone and region, and make sure image is windows 10 Pro. Size can be whatever you want, but remember it will cost money if you leave it running all day.
</p>
<img width="633" alt="image" src="https://github.com/user-attachments/assets/b12adfde-31dc-4995-9861-2d63976e634e">
</p>
<img width="620" alt="image" src="https://github.com/user-attachments/assets/7c534a0f-8421-4a98-a33b-5b0ded0f009f">
</p>
Next create your username and password and check on Licensing. Make sure that on the Networking page, virtual network need to be the same as your virtual name. Then review + create. 
</p>
<img width="370" alt="image" src="https://github.com/user-attachments/assets/80be9f8b-371c-4db4-8d6e-3e9cda4b8b42">
</p>
<img width="1274" alt="image" src="https://github.com/user-attachments/assets/4cd53c15-160e-437a-aacc-2c2bb7324ee7">
</p>
<img width="295" alt="image" src="https://github.com/user-attachments/assets/35879dd8-f00b-4545-952c-2fa4a870e263">
</p>
After it complete go to virtual machine and copy the Public IP address and open up remote desktop connection in your computer and put in the ip address in and log in with username and password you just created.
</p>
After log into VM with remote desktop download this in Virtual Machine (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD) and extract everything on the desktop.
</p>
<img width="602" alt="image" src="https://github.com/user-attachments/assets/1c373e60-3a08-432e-a019-df5a643f8e2f">
</p>
Next Install / Enable IIS in windows with CGI by going to control and programs then click on Turn Windows features on or off.
</p>
<img width="337" alt="image" src="https://github.com/user-attachments/assets/15456c14-9c29-4c38-9e6b-c1ed86836a32">
</p>
Then Internet Information Services > World Wide Web Services > Application Development Feature > Check on CGI and press OK.
</p>
Install PHP Manager for IIS and Rewrite Module from the folder. Create the directory C:\PHP from C: then extract PHP 7.3.8 to PHP you just created. Then install VCredist. 
</p>
<img width="607" alt="image" src="https://github.com/user-attachments/assets/4961ee71-8223-42aa-bb4f-5ab74075cc84">
</p>
Install MySQL with these setting Typical Setup > Lanuch Configuration Wizard > Standard COnfiguration.
new root password: root and confirm: root. Then execute.
</p>
<img width="359" alt="image" src="https://github.com/user-attachments/assets/54552fdc-1c03-41da-a2eb-d29fa4406082">
</p>
Open up IIS (Internet Information Services) as admin from window. Click on PHP version and register on PHP folder in C: we installed and select php-cgi.
</p>
<img width="782" alt="image" src="https://github.com/user-attachments/assets/3cc89acd-d0a6-42ac-a021-17c9ffb33dce">
</p>
Next unzip osTicket, then copy "upload" folder into “c:\inetpub\wwwroot” and rename it to "osTicket"
</p>
<img width="640" alt="image" src="https://github.com/user-attachments/assets/6db5a8a8-5e9d-4265-b976-cf8dbcb547a7">
</p>
Reload IIS (Open IIS, Stop and Start the server). </p>
Got to Sites > osTicket > Browse *.80"</p>
It will load an osTicket sites.</p>
<img width="914" alt="image" src="https://github.com/user-attachments/assets/d13fcab0-484e-4675-a379-b125b3019720">
</p>
<img width="503" alt="image" src="https://github.com/user-attachments/assets/24fec2a7-927f-40d4-9da1-7654539e4958">
</p>
Note that some extensions are not enabled</p>
Go back to IIS, sites -> Default -> osTicket</p>
Double-click PHP Manager</p>
Click “Enable or disable an extension”</p>
Enable: php_imap.dll</p>
Enable: php_intl.dll</p>
Enable: php_opcache.dll</p>
Refresh the osTicket site in your browser, observe the changes</p>
<img width="725" alt="image" src="https://github.com/user-attachments/assets/6e32541c-f3b1-4073-8e9b-6c1752af5f02">
</p>
Rename: ost-config.php</p>
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php</p>
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php </p>
<img width="680" alt="image" src="https://github.com/user-attachments/assets/69911b12-b2d6-4077-8dee-d7aade7e298e">
</p>
Install HeidiSQL from downloaded folder</p>
Open Heidi SQL</p>
Create a new session, user:root password:root</p>
Connect to the session</p>
Create a database from unnamed called “osTicket” </p>
<img width="692" alt="image" src="https://github.com/user-attachments/assets/aba1b33b-b7ad-46ab-92f3-6c3af9cd0e7e">
</p>
Then go back to osTicket website and click continue </p>
Continue Setting up osTicket in the browser </p>
MySQL Database: osTicket</p>
MySQL Username: root</p>
MySQL Password: root</p>
Click “Install Now!”</p>
<img width="695" alt="image" src="https://github.com/user-attachments/assets/f92af108-df8d-4bb2-b9d5-fe5a732a2fb2">
</p>












