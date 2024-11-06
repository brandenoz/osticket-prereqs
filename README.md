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

<img src="https://i." alt="Screenshot 127.0.0.4 aka Web Server page in browswer"/>
<img src="https://imgur.com/a/3ZlgbbE" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/a/CE6HO8N" alt="asdfasdfasdf"/>
<img src="https://imgur.com/a/S8nxsk8" alt="asdfasdfasdf"/>
<img src="https://imgur.com/a/aJAYGIZ" alt="asdfasdfasdf"/>
<img src="https://imgur.com/t5tjJli" alt="asdfasdfasdf"/>

<h2>Installation Steps</h2>

<p>
First, you must create a Windows 10 virtual machine in Microsoft Azure. I'd recommend choosing the size of at least 4 VCPUs as less could make it operate very slow. Using the public IP address, log in to the VM. Create a folder on the desktop called, "osTicket-Installation-Files". Navigate to https://osticket.com/download/ to choose the right open-source software for your needs. Download the zip file and extract the files into your created folder on the desktop called "osTicket-Installation-Files". You can now delete the zipped file as you will not need it anymore. </p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In a browser window, search 127.0.0.1. This will serve as the loopback address for the computer’s IP address. It should come up as “refused to connect” because we haven’t installed the web server yet. When this page comes up correctly, this will serve as confirmation of having installed the web server. 
</p>
<p>Open the control panel, and click on “Uninstall Programs” under “Programs”. Click on Turn Windows Features On or Off. Click on Internet Information Services, under Internet Information Services, under World Wide Web Services, under Application Development Features, click CGI, then ‘Okay’. It will install the web server. Refresh the 127.0.0.1 to see the default web server to see the page. 
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the "osTicket-Installation-Files" folder, you will download the following programs: PHPManagerForIIS_V1.5.0.msi and rewrite_amd64_en-US.msi. In the C drive, create a folder called PHP, and you can unzip the php-7.3.8-nts-Win32-VC15-x86.zip file into this C:\PHP folder. Next from the "osTicket-Installation-Files" download VC_redist.x86.exe and MySQL 5.5.62. For installing MySQL, select 'Typical Setup', choose to launch the Configuration Wizard after the install, then 'Standard Configuration.' For both the username and password, set to 'root'. This would'nt normally be the best option for cybersecurity, but for simplicity and preventing problems later. I recommend you put this in a saved txt file on your desktop rather than trying to remember. If you will be using osTicket in a permenant way, you can choose a more secure username and password, just make sure you save it somewhere so it doesn't become an issue later. 
</p>
<p>Open IIS as an Admin by searching for it and right-clicking open as Admin. If you are not able to do this, you will need admin access to continue. In IIS, register PHP from within IIS by going to PHP Manager > C:\PHP\php-cgi.exe. Once again, stop IIS and start IIS again to take the new configuration. 
</p>
<br />
