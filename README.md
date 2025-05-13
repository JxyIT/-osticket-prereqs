<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system, osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com/watch?v=LOzmM5ZjKi0)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Windows 10 VM
- PHP Manager for IIS
- URL Rewrite Module
- MySQL
- Microsoft Visual C++

<h2>Installation Steps</h2>



<p> 1.Set Up Your Windows 10 VM
Begin by creating a Windows 10 VM with at least 2 virtual CPUs to ensure smooth operation. Ensure that Remote Desktop is enabled for easy access.

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p> 2. Install Internet Information Services (IIS)
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Enable IIS with CGI support:

Open Control Panel → Programs → Turn Windows features on or off.

Check Internet Information Services.

Expand World Wide Web Services → Application Development Features, then check CGI.

Click OK to install
</p>
<br />

<p>3. Download and Install Required Components
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Using the Web Platform Installer:

Search for MySQL 5.5 and install.

Search for PHP (versions up to 7.3) and install.

Install PHP Manager for IIS.

Install the URL Rewrite Module.

Install Microsoft Visual C++ Redistributable Package..

4. Configure PHP for IIS

Extract PHP (e.g., PHP 7.3.8) to C:\PHP.

In PHP Manager for IIS, register the PHP version.

Configure PHP settings as needed

5.Install osTicket

Download the latest osTicket version from the official website.

Extract the contents to a folder (e.g., C:\inetpub\wwwroot\osticket).

Rename include\ost-sampleconfig.php to include\ost-config.php.
