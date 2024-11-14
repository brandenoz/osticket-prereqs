<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This ticketing system is a widely used and trusted open-source support ticketing system. osTicket has 5+ million users worldwide and is used by 15,000+ businesses. Setting up a help desk ticketing system from scratch is a great way to learn the potential lifecycle of a ticket in a ticketing system and gain experience that will likely be transferable to other ticketing systems. 

<h2>Requirements</h2>

- Computer or VM Windows 10, 4 VCPUs.
- Good internet connection.

<h2>Configuration Steps</h2>

<h3>Step 1: Make a VM</h3>

You can use a VM from my previous project on Building a Virtual Machine, or you can create one now: https://github.com/brandenoz/virtual-machine. It is recommended that you choose Windows 10 for the image and 4 VCPUs for the size. You won’t want the VM to be slow. Remember, you will want a resource group made first to keep everything tidy. Set the username and password for the administrator account as something you will remember. Also, make sure to click the box under licensing on the first page of the virtual machine creation. 

<h3>Step 2: Download Files</h3>

For this lab, I will be using the Open Source edition of osTicket but other options have more support. I am choosing the Open Source option because it will have more flexibility for this lab and it will involve a heavier technical side of the software than the Cloud-hosted option would have. 
- Create a folder on the desktop called, “osTicket-Installation-Files”. 
- Download files for the installation from this link (https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)  or the osTicket website based on your needs and plugin selections. 
- Extract the files into the “osTicket-Installation-Files” folder on your desktop and delete the file from downloads. 

<h3>Step 3: Install the Web Server</h3>

In a web browser, search 127.0.0.1. This is the loopback address that will load a page once the web server is installed. If you want to see this step in depth, go to this page before installing the web server to see that it will refuse to connect. 
- A web server is a computer system and software that stores and delivers web content to users over the Internet. After this, your VM or local computer will be one. 
Hit the Windows start button and search control to bring up the Control Panel. 
Under Programs, click Uninstall a program. <br>

![1](https://github.com/user-attachments/assets/011c3cb6-2a47-4c61-90bc-95a8c6c3495b)

- Click Turn Windows features on or off. 
- Turn on (if not already on) Internet Information Services and click the drop down. 
- Turn on World Wide Web Services and open the drop down. 
- Open the drop down beneath Application Development Featurs and check CGI. <br>

![2](https://github.com/user-attachments/assets/752e1979-779b-4a5c-9281-227c1a6d359e)

- Click OK. Now go refresh or search 127.0.0.1 and you will see the web server landing page. <br>

![3](https://github.com/user-attachments/assets/c9d88641-76d7-4082-95ff-a5614c49ebe0)


<h3>Step 4: Install Files</h3>

We will be using the desktop folder we made. This is a list of resources needed for the installation per osTicket compiled by Josh Madakor. 
- Install PHPManagerforIIS_V1.5.0 by doubleclicking the file from our desktop folder on our desktop. Click: Next > I Agree > Next > Close. 
Install by doubleclicking rewrite_amd64_en-US by doubleclicking then clicking I accept > Install > Finish. 
Create a directory on the C drive, C:\PHP. Open another file explorer window for convenience. Go to the C drive and make a folder tiltled "PHP". 
Extract php-7.3.8-nts-Win32-VC15-x86 into the PHP folder on the C drive by right clicking on php-7.3.8-nts-Win32-VC15-x86 extracting to our PHP folder on the C drive. <br>

![4](https://github.com/user-attachments/assets/d96285cc-a990-40b3-a4b2-47671050e7ec)

- Install VC_redist.x86 by doubleclicking it then clicking I agree > Install > Close. 
- Install mysql-5.5.62-win32 by doubleclicking it then clicking Next > I accept > Next > Typical > Install > Click Launch the Wizard > Finish > Next > Standard Configuration > Next > Next > make username/password “root” to keep it simple. > Next > Execute > Finish. 
- In the Windows start menu, search “ISS” to see Internet Information Services (IIS) Manager. Right-click and open as administrator. In this next step we will be making the computer aware of PHP being on it. <br>

![5](https://github.com/user-attachments/assets/881b5399-9692-4550-a89c-a4bada3cb5b3)

- Doubleclick PHP Manager. Click Register new PHP version. Browse to php-cgi.exe from the C drive, PHP. Click OK. 
- Now reload ISS. To do this, stop by right clicking and selecting stop. Then after a second or so, right click and click start again. This is what we will do when we reload ISS. 
- Install osTicket-v1.15.8 by right clicking and extracting with default suggestion. When done, you will see this file extracted, doubleclick to open. 
- Copy the folder named “upload”. Paste the file into Windows (C:) > inetpub > wwwroot. Rename the file from Uplaod to osTicket. 
- Now reload IIS. To do this, stop by right clicking and selecting stop. Then after a second or so, right click and click start again. 
- Now in IIS, click on osTicket under Default Web Site under Sites. Then click Browse to open the osTicket site in a browser window. <br>

![7](https://github.com/user-attachments/assets/ce8504fb-902f-40fc-a91d-a20b76dcd89b)<br>

![8](https://github.com/user-attachments/assets/e493abd9-438f-417c-91d7-21fe6b344db7)
- In IIS, doubleclick PHP manager, click Enable or Disable an extension. Then enable the following three extensions if not already done: 1) php_imap.dll, 2) php_intl.dll, 3) php_opcache.dll. Refresh your osTicket Installer page that opened previously in your web browser and observe that most of the recommendations cleared. <br> 

![9](https://github.com/user-attachments/assets/7a282aa2-70fb-4dad-b8e2-10434b7815b2)

<h3>Step 5: Configure Web Installation</h3>

In inetpub > wwwroot > osTicket > include, find the file named ost-sampleconfig.php and rename to ost-config.php. <br>

![10](https://github.com/user-attachments/assets/9272f599-ceeb-4b9b-80b4-8dd9ed9ad25e)

- Open properties of this renamed file. Got to Security > Advanced > Disable Inheritance > Remove all inherited permissions from this object > Add > Select a principal > “Everyone” > Check Names > OK > Full Control > OK > Apply > OK > OK. <br>

![11](https://github.com/user-attachments/assets/d428bbfb-f1d3-48db-9686-9a174c43ec61)

- Now click Continue on the osTicket website that loaded previously into a browser window for us. 
- Name your help desk. Enter a default email and email address for the Admin User that is different. Use adminuser as the Username and Password1 as the password to keep it simple. You can change this later or choose something more secure now as long as you remember it later on when you need it. <br>

![12](https://github.com/user-attachments/assets/f0bb9a1c-97c6-4aa8-b34e-436a54705203)

- Go into our desktop file folder: osTicket-Installation-Files, install HeidiSQL_12.3.0.6589_Setup by doubleclicking > I accept > Next > Next > Next > Install > Ensure Launch HeidiSQL is checked > Finish. Open HeidiSQL. 
- In HeidiSQL > click New > add root as the User and Password > OK. Right-click Unamed > Create New > Database > osTicket > OK. <br>

![13](https://github.com/user-attachments/assets/188c129c-3dcd-4a96-ac5a-1b173f8bb954)

- Now in the osTicket browser page, set the MySQL Database as osTicket, set the MySQL username and password as root, click Install Now. You will see a congratulations page when this is completed. In HeidiSQL you will see files in the new database that we created. 

<h3>Step 6: Bookmark URLs</h3>

- This is the fun part. Open these URLs in your web browser and bookmark them for easy navigation later. Login with your user account. 
- http://localhost/osticket/scp/login.php (bookmark) 
- Login with admin user credentials made earlier. <br>

![14](https://github.com/user-attachments/assets/71c1990e-b608-400b-a327-0a9d6944a6f3)

- http://localhost/osTicket/ (bookmark) <br>

![15](https://github.com/user-attachments/assets/1b90a86f-6482-4a59-a653-7cdeb00bc0a6)

<h3>Step 7: Clean Up</h3>

If you are stopping for now. As shown in the virtual machine project before this one, stop your VM and ensure you get a success notification before walking away. 


See the next lab here: https://github.com/brandenoz/post-install-config. 
