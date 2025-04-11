
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the steps I used to set up a ticketing system and how you could do it aswell..<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure Virtual Machine
- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (RDP)
- Internet Information Services (IIS)

<h2>Environments Used </h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
  
<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2> VM Set up  </h2>

1.	Open Azure and navigate to Virtual Machines.

	2-	Click create a virtual machine 

	3-	Choose or create a Resource Group (name it what you want)

	4-	Pick your Region

	5-	Under Image  choose Windows 10 Pro.

	6-	Select an appropriate size of memory 

	7-	Create a Username and Password (example: labuser and Cyberlab123!).

	8-	Complete the remaining settings as needed, then click Create to deploy the virtual machine.

	9-	Once the VM is up and running, go to its home screen and locate the Public IP Address.

 10-	Use Remote Desktop (RDP) to connect to the virtual machine using the public IP along with the username and password you created.

---


 ![Create a VM ](https://github.com/user-attachments/assets/8530eeeb-64a0-408e-9ba7-864f7973344b)

![VM name ](https://github.com/user-attachments/assets/eefc8bd5-6dea-49fb-9cda-1dce61ad6d38)
![Labuser photo](https://github.com/user-attachments/assets/0c24f9e2-0075-473d-a079-2dbb3b1b336c)
![Create vm screen](https://github.com/user-attachments/assets/7d488446-79f2-4198-9aff-3f6cd89ff6a9)


![VM ipaddress](https://github.com/user-attachments/assets/55a7b0be-a0e7-4333-912f-0ea0feea8a64)




---

<h2> OSTicket Installation </h2>

Step 1.	Download and Extract osTicket

	- Open Windows Explorer and copy this link into the address bar:
osTicket zip

	- Download and extract the files to the Desktop
---

![ade6](https://github.com/user-attachments/assets/26d615d1-f899-4432-bafa-0bd76f8f80f9)
![ade6 (1)](https://github.com/user-attachments/assets/de7f3a89-dd50-4527-b187-e0b8c4bc872a)

---

Step 2.	Install IIS with CGI

	- Click Start, then open the Control Panel
	- Go to Programs, then click Turn Windows features on or off
	- Navigate to
Internet Information Services (IIS) > World Wide Web Services > Application and Development Features

	- Check the box for CGI, then click OK
---

![ade9](https://github.com/user-attachments/assets/8c73396f-63af-4535-9a69-0c8b041ae979)
![ade10](https://github.com/user-attachments/assets/2c7da748-63d7-49ea-8882-5c7a4eeae58c)
![ade11](https://github.com/user-attachments/assets/6d4ee13f-838e-4a11-bef3-9d1a9c19bfe3)

---

Step 3.	Install PHP Manager and Rewrite

	- Inside the osTicket folder, download PHP Manager and URL Rewrite
	- Follow the installation prompts and accept all terms

---

![ade12](https://github.com/user-attachments/assets/ed13d3c1-cee8-494b-95b2-36945b7ef696)

---

Step 4.	Set Up PHP
   
	- Navigate to the C:\ drive and create a new folder named PHP
	- Go back to the downloaded zip file, extract its contents, and find the PHP folder
	- Move the extracted PHP files into C:\PHP

Step 5.	Install Required Dependencies
   
	-	Install VC_redist.x86.
	- Install MySQL using the Typical Setup option
	- Launch the MySQL Configuration Wizard and select Standard Configuration
	- Important Use the same Username and Password for MySQL (ROOT in all caps).
	- Click Next then Execute to complete the setup.

---

![a15](https://github.com/user-attachments/assets/9609f915-8e98-4b72-97f0-61c6fba8e239)
![a16](https://github.com/user-attachments/assets/8ab6b478-9a95-4c34-bb4a-7db6d3b2c854)

---


Step 6.	Configure IIS for PHP
   
	- Open IIS as Admin
	- Click PHP Manager, then select Register New PHP Version
	- Locate the PHP folder on the C:\ drive, open it, and select the php-cgi.exe file
	- Click OK, then restart IIS

---

![ade13](https://github.com/user-attachments/assets/324e4773-3f9a-4128-bdca-f91a2ad8b29e)
![ade14](https://github.com/user-attachments/assets/9acf49ef-33d3-443f-a5eb-ca3281de93e6)
![ade15](https://github.com/user-attachments/assets/06ad3091-f990-42d4-9d33-2b72a2811321)
![ade16](https://github.com/user-attachments/assets/2a23b13b-b6a8-4392-91d6-5cacddb3937e)

---

Step 7.	Configure osTicket in IIS
   
	- Go back to the osTicket installation folder and extract all files.
	- Open the extracted folder and copy the upload folder to: C:\inetpub\wwwroot
	- Rename the folder to osTicket (exact spelling, including capitalization).
	- Restart IIS.

---
![ade16](https://github.com/user-attachments/assets/2a23b13b-b6a8-4392-91d6-5cacddb3937e)
![ade17](https://github.com/user-attachments/assets/8679b806-a1e0-4c9c-8d73-37b7329f8836)
![ade18](https://github.com/user-attachments/assets/4ee9906a-88cd-416d-9c59-ae99587ab691)

---
Step 8.	Launch osTicket
   
	- In IIS, open Sites, then select Default Web Site.
	- Click Browse osTicket, and it should open successfully.

---

![ade19](https://github.com/user-attachments/assets/49b376de-8ee2-4c60-9a86-196e72d18268)

---

<h2>OsTicket Configuration</h2>

- Enable Missing PHP Extensions
  
	- Open IIS and navigate to PHP Manager.
	- Enable the following extensions:
		- php_imap.dll
		- php_intl.dll
		- php_opcache.dll

---

![a29](https://github.com/user-attachments/assets/917f6e13-c503-408e-aeb1-362b1a1b235f)
![ade20](https://github.com/user-attachments/assets/af017cee-2a22-4036-9df8-fe68f70d2dae)
![ade21](https://github.com/user-attachments/assets/0abbf225-8994-4211-9743-d94b1ed5caa9)

---
    
- Rename and Configure ost-config.php

	- Navigate to: C:\inetpub\wwwroot\osTicket\include.
   ---
  ![ade22](https://github.com/user-attachments/assets/d4586b30-ffe6-4f49-b19f-056dba724116)
  
  ---

	- Find ost-sampleconfig.php and rename it to ost-config.php (exact spelling).
   ---
  ![a35](https://github.com/user-attachments/assets/40138abd-e1e7-4a4f-bfc7-3b3297031842)
  
  ---
  
	- Right-click the file and select Properties.
---
![ade23](https://github.com/user-attachments/assets/ba9d74b4-dce1-43cb-916f-f15da22db145)
![ade24](https://github.com/user-attachments/assets/c9cac959-9527-415e-82bf-f01be1dcee89)
![a24](https://github.com/user-attachments/assets/6445e3b5-7fcb-4ab1-bdb1-5bc291417df0)
![ade25](https://github.com/user-attachments/assets/60a8db73-7990-4f61-b0f8-7af09b7d89fe)

---
	- Go to Security > Advanced.
	- Click Disable Inheritance, then Remove all entries.
	- Click Select a Principal, type Everyone, then check Full Control.
	- Click OK to apply the changes.

- Complete osTicket Installation

	- 	On the osTicket setup screen, enter a Help Desk Name and Admin Username of your choice.

- Install HeidiSQL

    - Open the osTicket installation folder and install HeidiSQL.
    - Follow the installation steps and ensure Launch when done is checked.
    - Open HeidiSQL and create a new session.
      
	 - Enter:
	   - Username: root
	   - Password: ROOT (all caps)
    - If it does not connect, restart the lab and try again.
      
---

![a40](https://github.com/user-attachments/assets/530e6e4c-ae9e-4ad6-b8e9-d29336bd2d58)
![ade26](https://github.com/user-attachments/assets/e3a567ee-c895-47d7-95c0-856b77190e2f)
![a42](https://github.com/user-attachments/assets/b6839f55-df83-4f38-ba2e-7d7321d84546)

---



- Create the osTicket Database

	-	Once connected, right-click Unnamed and select Create New > Database.
	- Name it osTicket (exact spelling).
---

![ade27](https://github.com/user-attachments/assets/0229ac6f-8371-407b-b327-7a4f0bfb9527)
![ade28](https://github.com/user-attachments/assets/5c1a57bd-8fc5-4a61-a942-6288fe300bc0)

---

-	Finalize osTicket Setup

	- Go back to the osTicket setup tab.
	- In the SQL Database field, enter osTicket.
	- For SQL Username, enter root.
	- For Password, enter ROOT (all caps).
	- Click Install.
	- If successful, you should see a Congratulations screen.

---

![image](https://github.com/user-attachments/assets/5646f022-6546-448d-9414-630b482f7555)

---

- Access osTicket Admin Panel

	- Use the Staff Control Panel link to log in as an admin.
	- Regular users can access osTicket via the main URL.
---

![ade29](https://github.com/user-attachments/assets/785e3831-02ce-4426-bce4-df0e789887df)
![a47](https://github.com/user-attachments/assets/6df54d2e-4812-4ba0-8922-4a2cbc048506)

---





