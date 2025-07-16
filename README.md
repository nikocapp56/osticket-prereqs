<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/> </p>

<h1>osTicket - Prerequisites and Installation</h1>
This guide demonstrates how to install and configure the open-source ticketing system osTicket (v1.15.8) on a Windows machine using IIS, PHP, and MySQL.

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Prerequisites</h2>
Before starting, ensure the following environment is in place:

  - Azure Resource Group (example: osTicketRG)
  - Azure Virtual Machine (example: osticketVM)
    - Operating System: Windows 10 Pro, version 22H2 - x64 Gen2
    - Size: 4 vCPUs
  - Remote Desktop Access enabled (for connecting to the VM)
  - [osTicket Installation Files](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)

<h2>Installation Steps</h2>

<h3>0️⃣ Overview of osTicket Installation </h3>

- Enable Internet Information Services
- Install Web Platform Installer
- Install MySQL and Set Up Useranme and Password
- Install C++ Redistributable
- Congure Permissions and Install osTicket

<h3>1️⃣ Install/Enable Internet Information Services (IIS) with CGI </h3>



<h3> 2️⃣ Install PHP Manager for IIS </h3>



<h3> 3️⃣ Install IIS Rewrite Module </h3>



<h3> 4️⃣ Setup PHP </h3>



<h3> 5️⃣ Install additional prerequisites within osTicket installation Files </h3>



<h3> 6️⃣ Configure PHP in IIS </h3>



<h3> 7️⃣ Install osTicket </h3>



<h3> 8️⃣ Enable required PHP extensions </h3>



<h3> 9️⃣ Configure osTicket </h3>



<h3> 🔟 Setup the database </h3>



<h3> 1️⃣1️⃣ Finalize and cleanup </h3>


