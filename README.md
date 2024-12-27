<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This guide provides an overview of the required components and a step-by-step walkthrough for installing osTicket, an open-source help desk ticketing system.<br />





<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute) *minimum of 4vCPUS
- Remote Desktop Protocol
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Enable Internet Information Services(IIS)
- Install PHP Manager for IIS
- Install VC Redist.x86.exe
- Install MySQL 5.5.62
- Install Rewrite Module
- Unzip PHP 7.3.8 into C\:PHP Folder
- Register PHP Manager within IIS
- Install osTicket
- Install HeidiSQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enable Internet Information Services (IIS)
  
What it does:
IIS is Microsoft’s built-in web server for Windows. Enabling IIS lets you host web applications (like osTicket) on your machine.

How to enable IIS:

-Open Control Panel: Go to Start → Control Panel (or Settings → Apps & Features in newer Windows versions).

-Turn Windows Features On or Off: Locate and click Programs → Turn Windows features on or off.

-Enable IIS: Check the box labeled Internet Information Services. Make sure you also expand World Wide Web Services → Application Development Features and select what you need (e.g., CGI).

-Click OK: Windows will install and enable IIS.
</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  Install PHP Manager for IIS

What it does:
PHP Manager simplifies the management of one or more PHP installations on IIS. It provides a GUI for tasks like configuring php.ini settings and switching between PHP versions.

How to install:

-Download PHP Manager: Go to the official Microsoft IIS site or search “PHP Manager for IIS” and download the installer (e.g., PHPManagerForIIS-1.2.0.msi).

-Run the Installer: Double-click the MSI file and follow the prompts.

-Open IIS Manager: After installation, you’ll see PHP Manager as an option under IIS in the Internet Information Services (IIS) Manager tool.
  
</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Install VC Redist.x86.exe

What it does:
The Microsoft Visual C++ Redistributable (VC Redist) provides the runtime libraries needed by PHP to function. PHP compiled on Windows often depends on these libraries to run properly.

How to install:

-Download VC Redist: Go to Microsoft’s download page for the correct Visual C++ Redistributable (commonly 2010, 2012, or 2015–2019 versions, depending on your PHP build).

-Run the Installer: Double-click the .exe file and follow the setup wizard.

-Restart (If Needed): Some systems require a restart for changes to take effect.

</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Install MySQL 5.5.62

What it does:
MySQL is the database server where osTicket will store all its data—tickets, user information, and application settings.

How to install:

-Download MySQL Installer: Get the MySQL Community Server installer (version 5.5.62) from MySQL’s official website or archives.

-Run the Installer: Choose a “Typical” or “Custom” setup.

Configure MySQL:
-Root Password: Set a strong root password.
-Create a Database (Optional at this point): You can create a separate database for osTicket later.

Service Settings: Accept defaults (e.g., MySQL running as a service).

Finish Installation: Make sure MySQL is running, and note your root credentials for later.

</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Install Rewrite Module

What it does:
The URL Rewrite module for IIS allows you to create user-friendly URLs or redirect rules. Many web apps (including osTicket) rely on rewrite rules for clean URLs and proper routing.

How to install:

-Download URL Rewrite: Visit Microsoft’s IIS website and download URL Rewrite Module for your IIS version.

-Run the Installer: Follow the prompts. IIS will automatically add the Rewrite Module once installed.

-Verify Installation: Open IIS Manager → Sites → URL Rewrite should now appear under IIS in the feature list.

</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Unzip PHP 7.3.8 in C:\PHP
  
What it does:
PHP is the scripting engine that osTicket uses. Unzipping the PHP files in a dedicated folder keeps your web server organized and makes it easier to configure in IIS.

How to do it:

-Download PHP 7.3.8 (Non-thread safe preferred for IIS): Get the .zip package from windows.php.net.

-Create Folder: Create a folder in C:\ named PHP.

-Unzip Contents: Extract all files from the downloaded .zip into C:\PHP.


</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Register PHP Manager Within IIS
  
What it does:
Tells IIS where PHP is located and ensures your server processes PHP files correctly.

How to register PHP in IIS:

-Open IIS Manager: Press Win + R, type inetmgr, and press Enter.

-Select Your Server: In the left pane, click on your server name.

-Open PHP Manager: Under IIS, click PHP Manager.

-Register New PHP Version: Click Register new PHP version and browse to C:\PHP\php-cgi.exe.

-Validate Configuration: After registering, you should see PHP 7.3.8 listed under the PHP Manager screen

</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Install osTicket
  
What it does:
osTicket is the main helpdesk application that provides ticket management, user support, and customer service functionalities.

How to install:

-Download osTicket: From osTicket.com, get the latest stable release (or your preferred version).

-Extract Files: Unzip the osTicket files into a folder under your IIS web root (e.g., C:\inetpub\wwwroot\osticket).

-Set Permissions: Ensure C:\inetpub\wwwroot\osticket\include\ost-config.php is writable by IIS.

-Open Browser & Run Setup: Go to http://localhost/osticket and follow the on-screen installer.

-Database Info: Enter the MySQL hostname (often localhost), database name, username, and password.

-Admin Details: Provide an admin email, name, and password for the helpdesk.

-Finalize Installation: Once done, rename or remove setup directory as per instructions for security.

</p>
<br />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 Install HeidiSQL
  
What it does:
HeidiSQL is a user-friendly graphical tool to manage MySQL databases. It allows you to run queries, import/export data, and modify database structures without using the command line.

How to install:

-Download HeidiSQL: Visit heidisql.com and get the latest installer.

-Run the Installer: Accept defaults or customize the installation path.

-Launch HeidiSQL: Connect to MySQL using your root credentials (or a specific osTicket user you set up).

-Explore Databases: You can create, edit, or back up the osTicket database as needed

</p>
<br />
