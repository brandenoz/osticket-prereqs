<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>Microsoft Azure</h1>
Microsoft Azure is a cloud computing platform offering various services to help users build, run, and manage applications. In our case, we will be using it to launch a virtual machine. 

<h2>Requirements</h2>

- Computer and good internet connection. 
- Credit or debit card to use Azure's free $200 credit in the first month. 

<h2>Configuration Steps</h2>


<h3>Step 1: Subscription</h3>

Create an Azure account [here](https://azure.microsoft.com/en-us/free "target='_blank'").
- Name the subscription.
- “Subscription Group 1” for example unless you have a better name for your purposes. This is what I will name mine but the name will not affect function. 


<h3>Step 2: Resource Group</h3>

- Navigate to resource groups from the Azure portal (portal.azure.com) by searching for “research groups” in the upper search bar. 
- Click on “Create”. <br>

![1](https://github.com/user-attachments/assets/bfd94b7e-8b32-4787-8fec-ed26968f55b1)
- It is a good idea to create a resource group specifically for this project. 
- Later, if you want to delete the virtual machine, it will be easier to delete the resource group which will delete the virtual machine automatically. 
- Resource groups keep things clean. 
- I will name my resource group “Virtual-Machine-Example”. 
- Click “Review + create” then “Create”. You will have a chance to add tags to the resource group, but there is no need to do this if this is your first resource group in Azure. 
- Ensure your resource group is ready by navigating to it. You can go to “Resource Groups” by searching in the search bar, then click on the one you just made to open it. <br>

![2](https://github.com/user-attachments/assets/3ddc9993-1599-4f44-917c-d1ec5ae5b114)

<h3>Step 3: Virtual Machine</h3>

- You will not need to make the virtual machine from the resource group because you will have to assign the virtual machine to a resource group to make it. 
- Navigate to virtual machines by searching “Virtual Machines” in the search bar. 
- Click on “New”, then “Azure Virtual Machine”. Continue to click “Create” until your VM is being prepared. <br>

![3](https://github.com/user-attachments/assets/b9656186-0674-4523-8317-fe0638051ad8)
- For the subscription and resource groups settings, you should have only one option for each and it should look like the screenshot below. Note that the resource group is housed beneath the subscription. 
- It may take some time to be ready. In the meantime, navigate to Virtual Machines and refresh from time to time until your VM pops up. <br>

![4](https://github.com/user-attachments/assets/89c140c9-db2e-47f4-876c-b7f267a4af70)
- For the virtual machine name, choose something that makes sense. I will use Virtual-Machine-1. 
- For the image, which is like the operating system, you have many options. I will be choosing the Windows 10 option. 
- For the size, which is like the virtual hardware, you also have many options, but I would pick at least 2 VCPUs. (virtual CPU) I have gone with 1 VCPU before and had a difficult time with the speed of the machine. <br>

![5](https://github.com/user-attachments/assets/388db483-1aa2-44bd-ad55-0b1d617a8146)
- Next, you will create your administrative login. Simply pick a username and password that you can remember. If you don’t intend to use the VM for very long, the password does not need to be anything crazy. But if you intend to use the VM beyond the experiment, I would advise using something that will be secure. Either way, you will need to remember it to log in to the VM later. <br>

![6](https://github.com/user-attachments/assets/d8fa1ba1-ae44-4f25-9d56-ab6ba4e9fd40)
- Click on “Review + Create”. 

<h3>Step 4: Login</h3>

- You have created a virtual machine and will need to login to it virtually using Remote Desktop. 
- Navigate to Remote Desktop on your Windows computer by clicking on the “start” windows icon on your keyboard. Type “remote” and you should see “Remote Desktop Connection” appear as an app, click on it. <br>

![7](https://github.com/user-attachments/assets/17e522c1-f7eb-4b40-b6a8-70d37fa684d9)
- For the “Computer:” part, you will want to get the Public IP Address for the VM from Azure like below. Copy and paste this into the Remote Desktop Connection window. Click connect. <br>

![8](https://github.com/user-attachments/assets/ca359522-5267-4cfe-ba05-56a9517f7580)
- It is important that when you continue to login, you click “More choice” and then “Use a different account” because this is where you will use the user credentials created in a previous step rather than your default computer ones. It will otherwise not let you in. <br>

![9](https://github.com/user-attachments/assets/02b8d33d-9f43-4613-a7ea-93177d33b365)
- This is the fun part, logging in, you will see the same view you would if you were logging into the physical computer. 
- You can do anything you like after this with the computer to test out the virtual machine. You can see that you are logged in as the administrative user that you made earlier. <br>

![10](https://github.com/user-attachments/assets/b2994386-98e0-4c83-9ef6-af5bce690b1b)
- Whenever you are ready to leave the VM, navigate to the top Remote Desktop bar and click the “x” to exit. 

<h3>Step 5: Cleaning Up</h3>

- Once you are done with the VM, delete the resource group. This will automatically delete the virtual machine and any other resources created within the resource group. This is why resource groups are convenient. 
- If you are not done with the VM and want to use it again in the future for another lab or purpose, in the meantime, stop the virtual machine so that it does not cost you credit while it is on. 
It is said that VMs can be good options rather than buying a bunch of computers, but they can be very expensive over time if using them full time. <br>

![11](https://github.com/user-attachments/assets/ae805f09-a45e-4f53-81df-2c1b9a5133d8)
- If you are deleting the VM and therefore resource group, you will want to find the resource group by searching “Resource Group”, clicking on the resource group, then “Delete”. To delete the RG, you will have to type the name or copy and paste the name to be able to click “Delete”. <br>

![12](https://github.com/user-attachments/assets/ae0875de-5a70-469a-8dc4-01de4d973fb8)
- As with stopping the VM to use it later without incurring cost, you will want to click on notifications and not consider your task done until you see a successfully completed notification of your action. 

<h3>The End</h3>
Thank you for following this tutorial. At this point, you will have: 
- Created a subscription to a cloud platform, Microsoft Azure, 
- Created and logged into a Virtual Machine or Virtual Computer. 
- Professionally closed or cleaned up your cloud resource. 
Go back to my projects to use your new virtual machine to use the VM: https://github.com/brandenoz/.

