<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
<br>This project was part of a course career module lab, its a tutorial that outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Virtual machine running HTTP server running Microsoft® IIS or Apache
- PHP version 8.2 - 8.4
- PHP Manager for IIs
- IIS URL Rewrite Module 2
- The latest VC_redist
- mysqli extension for PHP
- MySQL database version 5.5
- HeidiSQL

<h2>Installation Steps</h2>

![image](https://github.com/user-attachments/assets/ad688968-5cce-4e05-923d-d656881ccb0e)
<p>
The first step is to create and deploy a Windows 10 virtual enviroment where the software is going to be installed. The VM should at least have 2 vCPUs and should be accessible via Remote Desktop.
</p>
<br />

![image](https://github.com/user-attachments/assets/23ea6989-7324-4554-a2e8-e075862824ef)
<p>
The next step is to prepare the enviroment by installing all prerequisites as per their instructions. The best practice is to collect all downloads into a single folder before actually installing anything.
</p>
<br />

![image](https://github.com/user-attachments/assets/ee7ac98a-c859-430e-8f61-e12c95027502)
<p>
With all the prerequisites downloaded, prepping can begin with Internet Information Service (IIS). Make sure it is enabled on Windows.
</p>
<br />

![image](https://github.com/user-attachments/assets/8d7eebbf-0901-400d-8f82-da966a054008)
<p>
Continue prepping by creating a 'PHP folder' on the 'C: drive', this folder is where the PHP files from your download should be unzipped. 
</p>
<br />

<p>
Continue prepping by installing the prerequisites. 'PHP manager for IIS', 'IIS URL Rewrite Module 2', MySQL database and MicroSoft Visuals C++ can be installed via their installation wizards. For this installation, make sure your MySQL username and passwords are 'root'. Once all these softwares are installed they now need to be conifgured.
</p>

![image](https://github.com/user-attachments/assets/82ceca46-10a2-4e96-acf8-9642b1b3817e)
<p>
While running IIS as an admin, ensure PHP Manager is configured up by clicking: PHP Manager >> Register new PHP Version >> Provide the file path to php-cgi.exe. Restart the sever to apply changes.
</p>

![image](https://github.com/user-attachments/assets/10c988ef-ec59-42e1-8fb3-6d4a0dd1e54f)
<p>
At this point, osTicket itself can be installed. Unzip the osTicket installation files. Take the 'upload' folder. Drag and drop the 'upload' folder into the directory "c:\inetpub\wwwroot". Rename the folder to "osTicket". 
osTicket should be reachable from the internet browser. Restart the IIS sever to apply changes. Then from IIS: Sites >> Defult Web Sites >> osTicket >> Browse.
</p>

![image](https://github.com/user-attachments/assets/542e7570-f289-480d-84f2-b1cab1ba6ef3)
<P>
Back at the IIS, ensure all required PHP extensions are activated by going to: Sites >> Default Webt Site >> osTicket. Ensure that php_imap.dll, php_intl.dll and php_opcache.dll are enabled.
</P>

![image](https://github.com/user-attachments/assets/4b003619-0fca-4a36-bde8-b82d38759109)
<p>
Now, to make sure that osTicket's optional features are usable, head over to the directory: "C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php"
and rename the file "ost-sampleconfig.php" to "ost-config.php". Edit the properties of the renamed file: Security >> Advanced >> change access control to 'Everyone'. The renamed file is now accessble by any extensions and software.
</p>

![image](https://github.com/user-attachments/assets/a9784034-ebb0-466e-82ef-578815c09584)
<p>
From the internet browser, continue with the osTicket installtion on the browser to register the adminstration account. This is also the point in time where osTicket is going to be connected to the SQL database. To make sure osTicket can access the SQL database, first make sure HeidiSQL is installed. Make sure to create a new connection session in HeidiSQL by naming the data base "osTicket".
</p>

![image](https://github.com/user-attachments/assets/bcfd6a9d-bca3-46d6-901f-ebcf4f28eb62)
Now, osTicket has been installed!

![image](https://github.com/user-attachments/assets/0f16279e-3d15-437d-a5e1-fae3cd5030a5)
Login to your first session to ensure no errors. You are now done installing osTicket.
