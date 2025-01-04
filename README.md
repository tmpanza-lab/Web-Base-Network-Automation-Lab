# Web Base Network Automation Lab

## Objective

The objective of this project is to develop a web-based network automation lab that allows network engineers to manage and automate network devices efficiently. This lab will leverage modern network automation tools like Netmiko, enabling users to execute network configuration tasks, monitor network performance, and streamline administrative processes through a user-friendly web interface. The project aims to provide a practical, interactive platform for learning and implementing network automation, reducing manual intervention, and improving the accuracy and speed of network operations.

### Skills Learned

- Network Automation Fundamentals: Understanding the principles and practices of automating network configurations and management tasks. 
- Netmiko & Paramiko Usage: Gaining proficiency in using Netmiko & Paramiko for automating SSH connections to network devices and executing configuration commands.
- Python Scripting: Developing and enhancing Python programming skills, particularly in writing scripts for network automation tasks.
- Web Development: Learning to build and integrate a web interface for interacting with network automation scripts, including basic front-end and back-end development.
- GNS3 Lab Setup: Setting up and managing virtual network environments using GNS3 to simulate real-world network scenarios for testing automation scripts.
- Security Practices: Implementing secure coding practices to protect network devices and data from unauthorized access during automation processes.
- Documentation: Developing skills in documenting automation scripts, network configurations, and lab setup for future reference and learning.


### Tools Used

- Netmiko: A Python library that simplifies SSH connections to network devices for automation purposes.
- Paramiko: A Python implementation of the SSHv2 protocol used for handling SSH connections and secure file transfers
- Django: Web frameworks used to create the backend of the web application for interacting with network devices through a user-friendly interface.
- GNS3: A network simulation tool that allows the creation of virtual network environments for testing and practicing network automation.
- Postman: A tool for testing and interacting with RESTful APIs, which may be used to facilitate communication between the web interface and automation scripts.
- VS Code/PyCharm: Integrated Development Environments (IDEs) used for writing, debugging, and managing Python scripts and web application code.
- Cisco IOSvL2 Switch (image)
- Cisco IOSvL2 Router (image)

## Steps

Example below.

*Ref 1: Network Diagram*
![image](https://github.com/user-attachments/assets/f02fdd68-f2c0-467c-a4af-953745e06714)
![image](https://github.com/user-attachments/assets/43f8dd60-091e-43e7-91d2-567d578d1996)
 
 


# 1. Installing Python, Paramiko, & Django


To download python, you can go to python.org/downloads/

Here we can download the latest version, in this case the latest version is version 3.13.1
![image](https://github.com/user-attachments/assets/30275af8-950b-4eb1-995a-434848994873)
![image](https://github.com/user-attachments/assets/3bc2ed86-f90b-451f-965e-8c2068783903)
![image](https://github.com/user-attachments/assets/8205c872-daab-491b-8c4c-f743334f6723)

To ensure that Python is installed on our computer, we can open a command prompt, then type python --version.

Here we can see that we have python version 3.12.1.
This is means that we have successfully installed Python on our computer.
![image](https://github.com/user-attachments/assets/02a15c6b-ca75-42bf-9dc4-5c9236d63ef5)


Next we will learn how to install paramiko if you don't know about paramiko yet, you can see the paramiko documentation at paramiko.org here we can see that paramiko is a python library, it supports python version 2.7 or 3.4 and above, the goal of paramiko is to be able to implement ssh version 2, both as a client and as a server.
![image](https://github.com/user-attachments/assets/6d0a86e3-e3c4-4011-8c33-760061173142)

 










In this LAB, we will use paramiko as a ssh client, the paramiko will act as a library that will do SSH to Cisco routers and mikrotik routers.

Okay let’s install paramiko, open a command prompt, then type pip install paramiko.
 ![image](https://github.com/user-attachments/assets/2e3005ee-cf7a-477e-ae7d-4ac303ea8f98)
![image](https://github.com/user-attachments/assets/fd76e958-c3b9-4735-9ade-206cc3713d8e)

 




Okay we have finished installing paramiko and upgrading pip, to prove that paramiko has been installed correctly on our computer, we can enter the python interpreter by typing python, then here we can try to import paramiko.

Okay here we don't get an error, meaning the paramiko has been successfully installed on our computer. We can exit from this python interpreter by typing exit.
![image](https://github.com/user-attachments/assets/ec78344a-91db-4c62-8514-375a83c0786b)


 

Next we will learn how to install Django.

If you don't know about Django yet, you can see the Django documentation in djangproject.com, here we can see that Django is a python web framework, so we can use Django to build a website with python.

Okay, let's install Django, it's similar to how to install paramiko, we only need to open the command prompt and type pip install Django.

To prove that Django is installed properly or not, we can enter the Python interpreter, then type import django.

Okay here we also don't get an error, meaning that Django is successfully installed on our computer.

 ![image](https://github.com/user-attachments/assets/4249823a-d785-4cec-b07f-ba172cfe9cf8)
![image](https://github.com/user-attachments/assets/3b367c9d-b3f9-40a8-8e29-076369bc9f9e)

Here I will use a visual studio code, you are free to use your favorite code editor, but if you want to, you can download visual studio code for free at code.visualstudio.com.
![image](https://github.com/user-attachments/assets/8bf4fd8e-2997-4b05-b79c-8f6f4fe687cd)
![image](https://github.com/user-attachments/assets/f334b5c6-d490-4448-b250-8dfa8d706472)
 
 
# 2. Writing hello world code in python


Okey, now let’s start writing a simple python script, first create a new file, then save the file.

Don't forget to use .py extension, because this is a python script.

To display a simple word in python, we can use print keywords, for example we want to display a “hello world”.

With a very simple script like this, we can display the “hello world”, okay now save the file, and then open the command prompt and go to the directory where we saved the python script, in this case I save it in the document, try to dir to make sure that the python script is in this directory, okay we can see the python script here.

We can run the python script by typing python script.py, script.py is the name of our file.

When we enter, we will get hello world like this.

![image](https://github.com/user-attachments/assets/c5b0ee27-8ef9-4974-b848-d2da7b9aa4b0)

 
Now let’s try to manipulate the script, let’s add hello python.

Save the file, open the command prompt and run the script again, here we get hello world and hello python Okay, we have successfully written a simple script using python.
![image](https://github.com/user-attachments/assets/af717f71-7d8a-4cbd-8673-428cda435f40)


 
# 3. Importing cisco and mikrotik router to gns3

If you don't have GNS3 installed on your computer yet, you can download from gns3.com, you can download it for FREE, You just need to create an account first, don’t worry, you don't have to pay anything to create an account, After creating free account you will be able to download gns3 installer for FREE.

I assume that you already have GNS3 installed on your computer
![image](https://github.com/user-attachments/assets/3cf37f79-c49c-4606-8894-33cdfdc2c4de)
 

Open the GNS3, create a new project, in this case, I create project1.

To import a mikrotik router and cisco, you must download the image first.

I have uploaded a mikrotik and cisco image in my resource section
![image](https://github.com/user-attachments/assets/7d7850cc-8bca-40c5-822c-2e25c9c592f7)

 

Now I have those two image in my computer.

Let’s start importing mikrotik & cisco router to gns3. Go to edit and preference, we will try to import the Cisco router first, you can go to IOS router, then choose new, here we can browse to the image that we have downloaded before.

Then next, We don't need to set anything, we will use default configuration, so we just stay next, next, next, until finish.

Okay, now we have successfully import cisco router to gns3.
![image](https://github.com/user-attachments/assets/e476532f-7c30-4932-89f0-48fd4015d522)
![image](https://github.com/user-attachments/assets/cf09b87a-8c58-490d-ac2f-c259ba7b2664)

 
 

Next let’s try to import mikrotik router to gns3, we have to enter the qemu vms menu, then click new, we get a warning here, but we can ignore it, enter the name here, i use mikrotik, for RAM, we use default, which is 256MB, next, next, here we must select new image, then browse to the mikrotik image that we have downloaded before.

yes, then finish.
![image](https://github.com/user-attachments/assets/e3731456-f660-4ad9-b95b-da4f145686a4)
![image](https://github.com/user-attachments/assets/ed5f84c0-049f-4709-b9a5-1746d373bd8c)
![image](https://github.com/user-attachments/assets/9e2be0d6-ce6c-4394-ac87-823d1bcfd23c)
 

 

 



If you want to change the mikrotik logo, you can enter the edit menu, then there is a symbol, select browse, then you can choose as you like.

Here I will use the router firewall icon
 ![image](https://github.com/user-attachments/assets/0d9d8668-473e-41c3-a247-796f26f7db1e)
![image](https://github.com/user-attachments/assets/657172b4-f44d-4f50-92d8-d68e7c25c1f9)


 




If we see here, we will see mikrotik and cisco, we can import our router to the project by drag and drop, we also import a Cisco, to turn on the router, we can right-click and choose start, here we can see the green icon, which means both of routers are running.
![image](https://github.com/user-attachments/assets/d92f4871-b4a6-4345-8841-dde81c6e8021)

 
And if we look here, notice that the CPU load is 100%.

To decrease the cpu usage, we can do it by right-click on cisco router and then select auto idle pc.
![image](https://github.com/user-attachments/assets/e5937b50-0cb7-4422-8e27-3ae656ec40b4)
![image](https://github.com/user-attachments/assets/2f36068d-6ff9-4069-979a-e1c4e296c523)
 

 
To console the router, we can just double click on the router.

Here the terminal will open automatically, the username for mikrotik is admin, and the

password is blank.

Ok, now we have entered the mikrotik router.
![image](https://github.com/user-attachments/assets/b9dc224a-8c48-407c-a215-95e828b1f695)
 
let’s try to enter cisco, here we can also see that we have entered the Cisco router.
 
 ![image](https://github.com/user-attachments/assets/41e89acc-1b13-4216-bf37-d6d54ef7de48)
![image](https://github.com/user-attachments/assets/56cdc765-110c-4779-a003-5ae0ddc02528)

# 4. Connecting router to host OS
![image](https://github.com/user-attachments/assets/99c16b4d-9b07-457a-a67a-adcb470e3006)

 
To create a virtual interface, you can enter start, then type hdwwiz, this stands for hardware
![image](https://github.com/user-attachments/assets/a39b297e-8f46-48d6-a073-bc9a6846b8f3)

wizard. next, here, chose recommended, next, next, choose network adapters, select Microsoft on the left, and on the right, choose loopback adapter, next, next, and finish.
![image](https://github.com/user-attachments/assets/bba7a99c-df1e-400f-9307-7cd6d0bc69de)
 ![image](https://github.com/user-attachments/assets/4c542ebd-0d5e-4b16-9a4f-608d50ac5a80)
![image](https://github.com/user-attachments/assets/33fe51a9-2092-4002-887a-2f404f3c8d77)
![image](https://github.com/user-attachments/assets/bac1dc92-3a45-4d96-ad5d-a750ca5c1b6e)
![image](https://github.com/user-attachments/assets/63070bee-8ccf-4764-b9df-7e86d1f68ad2)


 
 
After create a virtual interface, we need to restart our computer. But before that let’s

save our project on gns3 first Okay, I'm done restarting my computer. To prove that our virtual interface is already up we can enter the open network and sharing center. 

Then change adapter settings here we can see that we have Microsoft loopback adapter, which is the Loopback Adapter Now let’s configure the ip address for this interface. According to our topology, the IP Address is 192.168.1.1.
![image](https://github.com/user-attachments/assets/f14da461-4696-47f5-ae49-42111029d477)



 
Next, let’s open our project on gns3. enter the project library, select our project, then ok
![image](https://github.com/user-attachments/assets/d7f0a4cd-55dd-4c78-befb-08bbdf325545)


 
 

Okay here we see mikrotik and cisco router. Next we need to import a cloud the cloud will act as our computer. 
![image](https://github.com/user-attachments/assets/e2a82403-6742-4622-bafd-b0f69df85114)

 
 We also need to import an Ethernet switch next we need to configure this cloud to act as our computer.
![image](https://github.com/user-attachments/assets/7327cfa2-6755-4ee5-a83e-79871b2048fb)

 
Finally, let’s connect the cable from our computer to the switch from the switch to the mikrotik, from Cisco to the switch. Now let’s turn on the mikrotik & cisco router
![image](https://github.com/user-attachments/assets/3eaab6d2-c1f2-4f88-ae42-6a8170506a28)

 

If we look at this topology, note that the computer is connected to a switch, then the mikrotik and Cisco router are also connected to the switch. Later we will configure the ip address 192.168.1.1 on the computer, 192.168.1.2 on the mikrotik, and 192.168.1.3 on cisco. Here we know that mikrotik and cisco are on gns3, meaning we need to create a virtual interface on our computer, why? Because gns3 is virtual, so we must make a virtual interface on our computer to connecting our computer with router on gns3.
 ![image](https://github.com/user-attachments/assets/7d6e701c-5087-49be-941b-dfa3399f7276)

Now let’s try to configure the IP address on the mikrotik and Cisco router, but before that it is strongly recommended to look at the interface that is installed on the mikrotik and Cisco, by clicking this icon, here we can see that the mikrotik is in Ether 0 but the interface naming on mikrotik router is started from ethernet1, so ether 0 here means ether1, then on the cisco, the interface is fa0 / 0.

Ok, let’s configure the ip address on the mikrotik router first.

The mikrotik ip address will be 192.168.1.2.
![image](https://github.com/user-attachments/assets/6119a5b3-0524-49ac-9b52-d4f499bf5d63)
 
Next let’s configure the ip address on the Cisco router.

The ip address of cisco router will be 192.168.1.3.
![image](https://github.com/user-attachments/assets/7bca6f21-d8c3-4726-9539-609fe143ef57)
 
Now, let’s try to ping from our computer to the Mikrotik and Cisco router.

Open the command prompt, let’s ping the mikrotik first, which is 192.168.1.2, okay it works,

then let’s try ping to the Cisco router. Okay, it also works. Now we have successfully
 ![image](https://github.com/user-attachments/assets/e904cefa-b26e-49de-9589-f160c53b5a48)
![image](https://github.com/user-attachments/assets/f6210f0f-4ae0-43c9-8f26-21e365c17481)



 
 # 5. Configure ssh on the router


Okay, now let’s configure SSH on Cisco router first. To configure SSH on Cisco first we must create a username, in this case we will create a username and password.

Also, we need to set the user privileges to 15  then we have to set a domain name, for example, I will set the domain name to sky29.co.za

Next we need to create a key by typing crypto key generate RSA, use 1024 modulus last, go to line vty 0 15, then type Login local and Exit, login local mean that we need to use local username & password database to login to the router by ssh

Until now, we have finished configuring SSH on the Cisco router.
![image](https://github.com/user-attachments/assets/2ee756b9-639e-428a-bebe-77e1523ec789)

 
Now let’s try to remote the cisco router using SSH, Open a putty. Type the cisco router address, then select SSH and Open . Yes, login as userame, and the password.

Ok, now we have successfully remote the cisco router using ssh,  now let’s take a look to mikrotik. In the mikrotik, SSH is active by default, so we don't need to configure anything.
Just open a new putty, then type mikrotik address, choose ssh and open. Yes login as admin, and the password is blank. Okey, we have successfully remote the mikrotik router using SSH.


# 6. Simple Network Automation on Cisco Routers
![image](https://github.com/user-attachments/assets/3970bd03-e9ac-4815-bcec-d0c753a18ad1)

 
Let’s understand the code, in the first line, we import paramiko, paramiko is python library that we are going to use as a ssh client.

We also need to import time, I will explain later why we need to import time.

Here we define the ip address, username and password of the cisco router we call SSH Client function from paramiko.

Then we connect to the router using the ip address, username, and password that we have defined before here, we print that we have successfully connected to the router, and then do invoke shell.
Here we can see that we send the cisco command to the router.

In this example I just send a command to configure loopback interface 0 with ip address 10.1.1.1.
![image](https://github.com/user-attachments/assets/dbdd2954-11dd-469b-8ba2-53827b09521e)

 
Okay Now let’s run the code open the command prompt, and go to the directory where we save the code.

Let’s try to dir to make sure that we are in the right directory here we can see that we have script.py.

Let’s run the code by command python script.py Here we can see that we have successfully login to 192.168.1.3, which is the IP Address of Cisco Router.

And then we also see that we have successfully send command to configure loopback interface 0 with ip address 10.1.1.1 to the cisco router.

Let’s go to the cisco router and type show ip interface brief here we can see that now we have loopback 0 with ip address 10.1.1.1.


Congratulation ! now you are able to write a simple script for network automation on cisco router
![image](https://github.com/user-attachments/assets/6c098b81-a267-4d2c-b2ab-6023c86dac7e)


 # 7. Simple Network Automation on Mikrotik Routers


In the cisco code, we need to import time, I already explained about time in the previous video

But now, for mikrotik code, we don’t need to import time here we define the ip address, username, and password of the mikrotik router. We call SSH Client function from paramiko and then we connect to the mikrotik router using the ip address, username, and password that we have defined before.

The different between this two script is, that we need to invoke shell in the cisco router but we don’t in the mikrotik router. Also the keyword to send the command to the cisco router is send, but in mikrotik we use exec_command. And we don’t need to delay the program in mikrotik, but in cisco, we must sleep the program or the command will not send to the router successfully.

Don’t forget to always close the ssh session save the code, open a command prompt, see that we are in the right directory here we can see that we have script2.py. Let’s run the code.
![image](https://github.com/user-attachments/assets/9d8b6fca-7aee-45f9-ab93-efd03d8bd379)

 
Okay, we have successfully run the code, In this example code, we will create a bridge interface in mikrotik and configure the ip address 10.2.2.1 to that bridge interface.

Let’s go to mikrotik terminal and see if the script is work you can see that now we have bridge interface and new ip address in the mikrotik Okay, now we are able to doing Network Automation on Cisco & Mikrotik routers.
![image](https://github.com/user-attachments/assets/99d0118b-561b-4675-bfe9-25e9574e0e6d)
![image](https://github.com/user-attachments/assets/0575d407-a41d-4664-97b5-8bd9f33069df)
![image](https://github.com/user-attachments/assets/917c32a0-a552-406d-b7e2-b69830ebfcc4)

 
Thank you for watching, and see you on the LAB!







