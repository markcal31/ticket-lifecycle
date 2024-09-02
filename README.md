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
- Enable Internet Information Services
- Install PHP Manager for IIS
- Install Rewrite Module
- Install VC Redist
- Install MYSQL
- Install osTicket
- Install HeidiSQL
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
- Cleanup

<h2>Installation Steps</h2>

Create an Azure Virtual Machine 
<br>- Windows 10, 4 vCPUs </b>
<br>- Name: Vm-osticket </b>
<br>- Username: labuser </b> 
<br>- Password: osTicketPassword1! </b>
</p>

![image](https://github.com/user-attachments/assets/2f7296cc-0980-4720-a4ed-d0c9b1ab0f1e)

<p>
Install / Enable IIS in Windows WITH
CGI and Common HTTP Features 
<br>-  World Wide Web Services -> Application Development Features -> </b>
<br>- [X] CGI </b>
<br>- [X] Common HTTP Features </b> 
</p>

![image](https://github.com/user-attachments/assets/eed8329b-7d02-4c45-a6e8-e3e42461b92e)

<p>
AND IIS Management Console
<br>-  Internet Information Services -> Web Management Tools -> IIS Management Console </b>
<br>- [X]  IIS Management Console </b>
</p>

![image](https://github.com/user-attachments/assets/a029807d-ea01-4d3b-8d90-6fa33395a37f)

<p>
<br>-  From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) </b>
</p>
<p>
<br>-  From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi) </b>
</p>
<p>
<br>-  Create the directory C:\PHP </b>
</p>

![image](https://github.com/user-attachments/assets/0afc0eff-e3dd-4e6b-b9d1-5819d5dc9a18)

<p>
<br>-  From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP </b>
</p>

![image](https://github.com/user-attachments/assets/bcc2fe17-9fd0-4d8e-a0c3-05893a10afac)

<p>
<br>-  from the installation files, download and install VC_redist.x86.exe</b>
</p>

![image](https://github.com/user-attachments/assets/80c7dfad-ed05-4040-b25c-e1b17f85cceb)

<p>
From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
<br>- Typical Setup -> </b>
<br>- Standard Configuration -> </b>
<br>- Password1 </b>
</p>

![image](https://github.com/user-attachments/assets/4ce4a453-adbb-4b8b-af93-a2b47ad3423c)

<p>
<br>- Open IIS as an Admin</b>
</p>

![image](https://github.com/user-attachments/assets/9d2de22b-5048-46e9-adb2-5d9e18633709)

<p>
<br>- Register PHP from within IIS</b>
</p>

![image](https://github.com/user-attachments/assets/5858a740-2070-418e-821d-f20c1304897f)

<p>
<br>- Reload IIS (Open IIS, Stop and Start the server)</b>
</p>

![image](https://github.com/user-attachments/assets/050280bf-5901-417f-b9e8-de1dd6f2681e)

<p>
Install osTicket v1.15.8
<br>- Download osTicket from the Installation Files Folder </b>
<br>- Extract and copy “upload” folder to c:\inetpub\wwwroot </b>
<br>- Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” </b>
</p>

![image](https://github.com/user-attachments/assets/b77b7973-9cc0-40fd-a261-c31a40cf1726)

<p>
<br>- Reload IIS (Open IIS, Stop and Start the server)</b>
</p>

<p>
Go to sites -> Default -> osTicket
<br>- On the right, click “Browse *:80” </b>
</p>

![image](https://github.com/user-attachments/assets/78351c29-383b-46f5-9f16-15fe68a7164a)

<p>
enable extensions
<br>- Go back to IIS, sites -> Default -> osTicket </b>
<br>- Double-click PHP Manager </b>
<br>- Click “Enable or disable an extension” </b>
  <br>- Enable: php_imap.dll </b>
  <br>- Enable: php_intl.dll </b>
  <br>- Enable: php_opcache.dll </b>
<br>- Refresh the osTicket site in your browse, observe the changes </b>
</p>

![image](https://github.com/user-attachments/assets/01e9bc4a-fa45-4786-8c5d-96ad67b90f9b)

<p>
Rename: ost-config.php
<br>- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php </b>
<br>- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php </b>
</p>

![image](https://github.com/user-attachments/assets/8b929bc1-2531-403e-ad86-b9dd41e13506)

<p>
Assign Permissions: ost-config.php
<br>- Disable inheritance -> Remove All </b>
<br>- New Permissions -> Everyone -> All </b>
</p>

![image](https://github.com/user-attachments/assets/4a34a2fe-919a-406b-96c8-04029b19b9bf)

![image](https://github.com/user-attachments/assets/d08e4183-088e-465b-81d6-ed525f07d024)

![image](https://github.com/user-attachments/assets/9835f7e6-d6c3-4194-a7c7-53f1965275b0)

<p>
Continue Setting up osTicket in the browser (click Continue)
</p>

![image](https://github.com/user-attachments/assets/cc4331f0-09a9-4eb4-a21f-fd485ade136a)

<p>
From the Installation Files, download and install HeidiSQL
<br>- Open Heidi SQL </b>
<br>- Create a new session, root/Password1 </b>
<br>- Connect to the session </b>
<br>- Create a database called “osTicket” </b>
</p>

![image](https://github.com/user-attachments/assets/84108d2e-c04c-4a83-8fe4-6d8e4eb527e5)

![image](https://github.com/user-attachments/assets/8c7ad445-35d6-41ca-a1f2-f742315a3e18)

<p>
Continue Setting up osticket in the browser
<br>- MySQL Database: osTicket </b>
<br>- Click “Install Now!” </b>
</p>

![image](https://github.com/user-attachments/assets/699bde32-de7e-446b-b4b2-1241a663ee9a)

<p>
Browse to the help desk login page: http://localhost/osTicket/scp/login.php
</p>

<p>
Continue Setting up osticket in the browser
<br>- Delete: C:\inetpub\wwwroot\osTicket\setup </b>
<br>- Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php </b>
</p>

Congradulations! osTicket is now ready for use!
