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

- Resource Group
- Windows 10 Virtual Machine with 2-4 virtual CPUs
- PHP Manager for IIS
- Rewrite Module
- PHP 7.3.8
- VC_redist.x86.exe
- MySQL 5.5.62
- osTicket v1.15.8
- HeidiSQL

<h2>Installation Steps</h2>
<p> -Install and Enable IIS with CGI withing Windows </p>
<ul>
<p> - Go to start and search for world wide web services -> application development features -> CGI </p></ul>
<p>
<img src="https://i.imgur.com/oNtKvOQ.png" height="80%" width="80%" alt=""/>
</p>
<body>
<p>
<p> - Download and install PHP Manager for IIS </p>
<p> - Download and install Rewrite Module </p>
<p> - Create a directory C:\PHP </p>
<p> - Download PHP 7.3.8 and unzip in directory C:\PHP </p>
<p> - Download and install VC_redist.x86.exe </p>
<p> - Download and install MySQL 5.5.62 </p>
<ul>
<p> - Select Typical Setup </p>
<p> - Launch Configuration Wizard after installation </p>
<p> - Select Standard Configuration </p>
<p> - Create a Password you wouldn't forget </p>
</ul>
</p>
</body>
</br>


<p> Go back to start and search for IIS, right-click to open as an Admin. Register PHP from within IIS and refresh </p>

<p>
<img src="https://i.imgur.com/v8mVI06.png" height="80%" width="80%" alt=""/>
</p>

Install osTicket v1.15.8
	<p>- within file explorer go to files within osTicket to find upload folder </p>
	<p>- extract and copy "upload" folder to c:\inetpub/wwwroot </p>
	<p>- Within the path, rename "upload" to "osTicket" </p>
Refresh IIS
	<p>- Click sites -> default -> osTicket </p>
	<p>- On the right side select "Browse *:80"</p>
	
<p>
<img src="https://i.imgur.com/jeLschR.png" height="80%" width="80%" alt=""/>
</p>

osTicket should appear on a tab
<p>
<img src="https://i.imgur.com/vjrkSQ8.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
There'll be a few extensions that aren't enabled, to enable them
	<p> - Go to IIS click sites -> default -> osTicket </p>
	<p> - Double-click PHP Manager </p>
	<p> - Click the option below to "Enable or disable an extension" </p>
		- Find and enable the following extensions
		<ul> - php_imap.dll </ul>
		<ul> - php_intl.dll </ul>
		<ul> - php_opcache.dll </ul>
<p>
<img src="https://i.imgur.com/0oO3M7z.png" height="80%" width="80%" alt=""/>
</p>		
	<p> - Refresh the osTicket site in browser and notice the extensions are now enabled </p>
</p>
<br />

<p>
<img src="https://i.imgur.com/o6NvowX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Rename: ost-config.php
<p> - In file explorer change C:\intepub\wwwroot\osTicket\include\ost-sampleconfig.php to 		C:\intepub\wwwroot\osTicket\include\ost-config.php </p>
Assign Permissions: ost-config.php
<p> - Right-click the file and disable the inheritance -> remove all </p>
<p> - Add a new permission -> everyone -> all </p>

<p>
<img src="https://i.imgur.com/G15sQQG.png" height="80%" width="80%" alt=""/>
</p>

Continue Setting up osTicket in browser
<p> - Create a Helpdesk name </p>
<p> - Create a default email </p>

<p>
<img src="https://i.imgur.com/3Sv80kc.png" height="80%" width="80%" alt=""/>
</p>

Download and install HeidiSQL before finishing osTicket in browser
<p>	- Open HeidiSQL </p>
<p>	- Create a new session, (use the username root and password created in MySQL 5.5.62) </p>
<p>	- Connect to the session </p>
<p>	- Create a database called "osTicket" </p>

<p>
<img src="https://i.imgur.com/Yt83qFM.png" height="80%" width="80%" alt=""/>
</p>
Finish osTicket setup in browser
<p>	- Fill in the fields with the information provided in HeidiSQL </p>
<p>		- MySQL Database: osTicket </p>
<p>		- MySQL Username: root </p>
<p>		- MySQL Password: (one you provided) </p>
<p>		- Click Install Now </p>

<p>
<img src="https://i.imgur.com/RHnQNkh.png" height="80%" width="80%" alt=""/>
</p>

If there are no errors, Congratulations!!!
<p> Browse to your help desk login in page: <ul> - http://localhost/osTicket/scp/login.php </ul> </p>

<p>
<img src="https://i.imgur.com/yWnCnoU.png" height="80%" width="80%" alt=""/>
</p>


<p> For the End Users, to create tickets, this is their osTicket URL: </p>
	<ul> - http://localhost/osTicket/ </ul>

<p>
<img src="https://i.imgur.com/QNGNsar.png" height="80%" width="80%" alt=""/>
</p>

Clean up Files
<p>	- Delete the setup file in the following directory: C:\inetpup\wwwroot\osTicket\setup </p>
<p>	- Set Permissions to "Read" only by right-clicking C:\inetpub\wwwroot\osTicket\include\ost-config.php and going into the properties </p>
</p>

Click this link to go to the <a href="https://github.com/JonnishaCampbell/post-install-config"> post installation configuration</a> section 
<br />
