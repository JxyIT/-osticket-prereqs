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

1. Log into the VM with Remote Desktop

Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. 
![image](https://github.com/user-attachments/assets/360eeee5-7241-4557-b94a-2c8334370f85)

2. Install / Enable IIS in Windows WITH CGI
World Wide Web Services -> Application Development Features -> [X] CGI

![image](https://github.com/user-attachments/assets/15994c0f-7bfa-49e1-8805-13500b879ae7)

3. From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

![image](https://github.com/user-attachments/assets/ee16984c-6da1-400a-883e-7129300729f6)

4.From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

![image](https://github.com/user-attachments/assets/eaf17a6e-a3f3-4a04-83ae-87e0d80db3d5)

  5.Create the directory C:\PHP

![image](https://github.com/user-attachments/assets/a79ee310-a7f3-467b-b603-3eb78a965ea5)

6.From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

![image](https://github.com/user-attachments/assets/26158537-1578-42ef-bb61-d83ff1ea7eab)

![image](https://github.com/user-attachments/assets/a567e2ca-1160-490a-8e1b-8de2d6cc412f)

7.From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

![image](https://github.com/user-attachments/assets/786bfb57-994c-4e00-b49f-4ee990724911)

8.From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)



![image](https://github.com/user-attachments/assets/06f16b5e-0948-429e-9506-b91db01e456c) ![image](https://github.com/user-attachments/assets/f10dea8d-ada9-4dd2-b8b3-88e989d769ca) ![image](https://github.com/user-attachments/assets/57e0a5f9-b661-4554-859d-914c80eef5ed)



Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Username: ex.root
Password:ex.root

9. Open IIS as an Admin

![image](https://github.com/user-attachments/assets/69587026-8208-408f-9ded-192c1834b7d6)

10. Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

![image](https://github.com/user-attachments/assets/4b2a0a38-32c3-4e65-8119-29536f251319)

11. Reload IIS (Open IIS, Stop and Start the server)

12. Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”



![image](https://github.com/user-attachments/assets/3cc82a0a-6e14-4079-ad80-5a5f40410662) ![image](https://github.com/user-attachments/assets/5981dae2-2186-4737-bc31-1127d35bfb05) ![image](https://github.com/user-attachments/assets/8215d83c-d7ec-46a4-8622-8ffc8ed4f920)



13. Reload IIS (Open IIS, Stop, and Start the server)

14. Go to sites -> Default -> osTicket
On the right, click “Browse *:80”
Note that some extensions are not enabled

![image](https://github.com/user-attachments/assets/b8922957-f526-45ed-b55f-b87d0b1b7a01)

15. Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”

![image](https://github.com/user-attachments/assets/35d1c90b-7a61-40f4-85ad-c338fcad8c80)

Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll

![image](https://github.com/user-attachments/assets/f883b434-ac59-4c46-a2b7-d2eb01393eb2)

Refresh the osTicket site in your browser, and observe the changes

![image](https://github.com/user-attachments/assets/ab1ba805-cb64-4ad3-ad8b-8350de5922cd)

16. Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![image](https://github.com/user-attachments/assets/148b726b-2c35-4de4-8609-cd822503a59c)

17. Assign Permissions: ost-config.php
Disable inheritance -> Remove All

![image](https://github.com/user-attachments/assets/8a318fcb-91f2-4696-b7d8-a1fbb1a26471)

New Permissions -> Everyone -> All

![image](https://github.com/user-attachments/assets/a369cfd9-80d6-4e88-ba91-d9da86b4eff9)


19. Continue setting up osTicket in the browser (click Continue)
Name Helpdesk
The default email (receives email from customers)

![image](https://github.com/user-attachments/assets/75f7b66d-e347-4a93-9667-5d7418969795)


21. From the “osTicket-Installation-Files” folder, install HeidiSQL.
Open Heidi SQL
Create a new session, root/root
Connect to the session
Create a database called “osTicket”



![image](https://github.com/user-attachments/assets/8f13f240-bedc-4aec-bac3-64c24cb676cc) ![image](https://github.com/user-attachments/assets/aa468196-7f31-4a2e-a061-a1fe404766eb) ![image](https://github.com/user-attachments/assets/c9d1f9fd-d4c5-4fa2-b988-e0403856101d)



23. Continue Setting up osTicket in the browser
MySQL Database: osTicket
MySQL Username: root
MySQL Password: root
Click “Install Now!”

![image](https://github.com/user-attachments/assets/0eb6c2d9-4d88-4171-b888-08093f7d6442) 


![image](https://github.com/user-attachments/assets/20d44b2a-2826-4e46-bb69-55e415344350)
