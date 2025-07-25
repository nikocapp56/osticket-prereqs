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

Control Panel -> Uninstall a program -> Turn Windows features on or off
<img width="800" alt="1" src="https://github.com/user-attachments/assets/ffa12e4f-c91e-4a67-aa51-c4381efbd171" />
<img width="800" alt="2" src="https://github.com/user-attachments/assets/bbe1c8fd-b5ce-494e-9222-9524c530cab4" />
<img width="560" alt="3" src="https://github.com/user-attachments/assets/eb10e072-41ca-4cd8-82d8-1955a2989f25" />

<h3> 2️⃣ Install PHP Manager for IIS </h3>

From the osTicket Installation Files folder, run PHPMAnagerForIIS_V1.5.0

osTicket is a PHP-based application. This GUI tool allows you to register PHP executables and manage PHP settings easily via the IIS Manager interface.

<img width="400" alt="5" src="https://github.com/user-attachments/assets/f182dfc6-29e4-4dcd-bcc9-c4ff66a6afe2" />
<img width="400" alt="6" src="https://github.com/user-attachments/assets/3ef74934-528d-48f3-b8ef-a8549d753ec2" />

<h3> 3️⃣ Install IIS Rewrite Module </h3>

From the osTicket Installation Files folder, run rewrite_amd64_en-US

This module allows IIS to rewrite URLs so that links like example.com/ticket/123 work correctly without .php extensions or query strings.

<img width="400" alt="7" src="https://github.com/user-attachments/assets/21aa4883-3001-4873-9b01-8a9ff726b07c" />

<h3> 4️⃣ Setup PHP </h3>

Create the directory C:\PHP

<img width="400" alt="8" src="https://github.com/user-attachments/assets/c8e0551b-90cd-4ca6-8fb1-bc71c420c9d7" />
<img width="400" alt="8 5" src="https://github.com/user-attachments/assets/82780713-e9ee-4649-bdb7-5a1fbb2b59c0" />

From the osTicket Installation Files folder, unzip php-7.3.8-nts-Win32-VC15-x86.zip into the C:\PHP folder

This provides the actual language interpreter needed for osTicket to run.

<img width="284" alt="8 75" src="https://github.com/user-attachments/assets/e8e0cb7f-d39c-4179-9e70-89ce04eabc2c" />
<img width="500" alt="9" src="https://github.com/user-attachments/assets/d8181fc2-29d5-463f-8f2c-c787ab3f76a5" />

<h3> 5️⃣ Install Microsoft Visual C++ Redistributable </h3>

From the osTicket Installation Files folder, run VC_redist.x86 

Some PHP extensions and MySQL components depend on the runtime libraries provided by this package. 

<img width="400" alt="10" src="https://github.com/user-attachments/assets/49bf66e4-241e-4067-8519-48d5fd919919" />

<h3> 6️⃣ Install MySQL </h3>

From the osTicket Installation Files folder, run mysql-5.5.62-win32

osTicket requires a database to store tickets, users, system settings, etc. MySQL is the backend database engine that stores all osTicket data.

<img width="400" alt="11" src="https://github.com/user-attachments/assets/814beaad-8306-4d12-a1f3-aa97f938f629" />
<img width="400" alt="12" src="https://github.com/user-attachments/assets/3f333137-6745-4474-9c87-ffa08d89bea3" />

Choose Typical Setup

<img width="400" alt="13" src="https://github.com/user-attachments/assets/bae5991a-bee6-4af9-98d5-b6f9354060da" />
<img width="400" alt="14" src="https://github.com/user-attachments/assets/44ba7e43-8af3-4e9a-b073-bb2568b5e8a9" />

Launch Configuration Wizard

<img width="400" alt="15" src="https://github.com/user-attachments/assets/5f0f754f-405f-4a50-9cc4-c18e7d4d0d4a" />
<img width="400" alt="16" src="https://github.com/user-attachments/assets/8605c1e2-8ff0-44a9-a9d1-98644e4a868e" />

Standard Configuration

<img width="400" alt="17" src="https://github.com/user-attachments/assets/1946ad30-c9e0-493a-b93b-e9c35fe48664" />
<img width="400" alt="18" src="https://github.com/user-attachments/assets/72cb55c1-5958-437b-adc9-264c3575c41b" />

Set root password: root 

<img width="400" alt="19" src="https://github.com/user-attachments/assets/57ab892f-b36d-490d-b65f-ba2ac2329159" />
<img width="400" alt="20" src="https://github.com/user-attachments/assets/d3795190-07b0-4d32-86dd-bc350d34b958" />
<img width="400" alt="21" src="https://github.com/user-attachments/assets/f3ff0f5c-71ac-473a-ab0f-e1392b027546" />

<h3> 7️⃣ Configure PHP in IIS </h3>

Run IIS as administrator.

<img width="158" height="310" alt="22" src="https://github.com/user-attachments/assets/e12ee1df-a33f-4315-94ac-071ccce71be9" />

Open PHP Manager

<img width="600" alt="23" src="https://github.com/user-attachments/assets/a273a437-617f-4a6e-aebc-59f1af11bc7b" />

Click "Register new PHP version"

<img width="450" alt="24" src="https://github.com/user-attachments/assets/7488eaf8-e19d-4ae8-9212-c6365d92bc4d" />
<img width="500" alt="25" src="https://github.com/user-attachments/assets/b41a6deb-38b0-45fa-9ea1-2af2fc979e0a" />

Navigate to This PC \ C: \ PHP \ php-cgi.exe

<img width="450" alt="26" src="https://github.com/user-attachments/assets/06de5d63-eaa9-437a-b533-04513910a3dc" />
<img width="500" alt="27" src="https://github.com/user-attachments/assets/936394d5-00b6-4c09-88f6-bbe785f2d20f" />

Reload IIS (Stop and Start the server)

<img width="470" alt="28" src="https://github.com/user-attachments/assets/1d341125-5a4d-44f8-ac00-15e20d06dd88" />
<img width="475" alt="29" src="https://github.com/user-attachments/assets/6a1bb8a1-ff86-415f-ae85-8870eac0beaf" />

<h3> 8️⃣ Install osTicket </h3>

From the osTicket Installation Files folder, unzip osTicket-v1.15.8.zip

<img width="470" alt="30" src="https://github.com/user-attachments/assets/68d438c4-0b24-40a5-9b66-adf48edf2be3" />
<img width="475" alt="30 5" src="https://github.com/user-attachments/assets/c408e90f-4273-40ae-a8c3-0cbfa8093c60" />

Copy the upload folder into C: \ inetpub \ wwwroot

<img width="330" alt="31" src="https://github.com/user-attachments/assets/1de8c956-5d49-48e9-9751-e4e6d3567b08" />
<img width="330" alt="32" src="https://github.com/user-attachments/assets/5ee3118e-5cf0-4e14-8425-236a36de6a82" />
<img width="330" alt="33" src="https://github.com/user-attachments/assets/7e4d715c-4b45-4d58-ba0f-5456c4a2fe9c" />

Rename upload to osTicket

<img width="460" alt="34" src="https://github.com/user-attachments/assets/e9b8c799-82f1-4616-9dc9-c3901f3772f6" />
<img width="465" alt="35" src="https://github.com/user-attachments/assets/481cbcff-8e33-4ad1-a400-fc058498332d" />

Reload IIS (Run IIS as administrator, Stop and Start the server)

<img width="470" alt="28" src="https://github.com/user-attachments/assets/fc087cbe-8da9-42cf-90a6-8ddc98b1e40d" />
<img width="475" alt="29" src="https://github.com/user-attachments/assets/c1ae5a5f-6edd-4dd6-b3f7-d23f37a38061" />

<h3> 9️⃣ Enable required PHP extensions </h3>

<img width="750" alt="36" src="https://github.com/user-attachments/assets/15217027-d67e-4e49-8814-ee43806d5412" />
<img width="600" alt="37" src="https://github.com/user-attachments/assets/de20cb0d-2040-43d4-a9a6-358b6a93a344" />

Some extensions aren’t enabled yet, so go back into IIS -> Sites -> Default -> osTicket -> PHP Manager -> Enable or disable an extension

<img width="750" alt="38" src="https://github.com/user-attachments/assets/bca59f03-e788-43e8-ba7a-21cbca1fc0f3" />
<img width="657" alt="39" src="https://github.com/user-attachments/assets/353750f7-6409-40a9-a62e-1965640b5f79" />
<img width="240" alt="40" src="https://github.com/user-attachments/assets/1d53d06a-4db9-498b-bb7b-99026bffbb8d" />

Enable the following:

- php_imap.dll
- php_intl.dll
- php_opcache.dll

<img width="300" alt="41" src="https://github.com/user-attachments/assets/86a463ce-7357-49c0-af78-a439d4f5a14a" />
<img width="290" alt="42" src="https://github.com/user-attachments/assets/8f75c98d-9ed4-400d-9a0c-7c7821e2a97c" />
<img width="300" alt="43" src="https://github.com/user-attachments/assets/6a9090b9-fd24-4a30-bac5-f89eb79b59e8" />

Refresh the osTicket website and all the extensions that were just enabled are now checked off.

<img width="600" alt="44" src="https://github.com/user-attachments/assets/046d6e3c-fd45-479b-8896-0c6236b82740" />

<h3> 🔟 Configure osTicket </h3>

Go to C: \ inetpub \ wwwroot \ osTicket \ include

Rename ost-sampleconfig.php to ost-config.php

<img width="400" alt="45" src="https://github.com/user-attachments/assets/9eb0f025-f411-46f6-9ed0-9bc4f3b02f46" />
<img width="398" alt="46" src="https://github.com/user-attachments/assets/a8015e1a-de6f-45e0-88cb-c5fc9e3d74ce" />
<img width="400" alt="47" src="https://github.com/user-attachments/assets/b3cab1a0-9ace-458a-b538-c790d0404e49" />
<img width="270" alt="48" src="https://github.com/user-attachments/assets/33133bd6-bc9c-409e-8828-8cc8494b5133" />

Disable inheritance -> Remove All

<img width="500" alt="49" src="https://github.com/user-attachments/assets/b6a93bd9-e477-4fac-8f08-93689ce35638" />
<img width="412" alt="50" src="https://github.com/user-attachments/assets/b96344cb-a845-4b7c-9150-cb518237ae1d" />

Add New Permissions -> Select a principal -> Everyone -> Full control

<img width="500" alt="51" src="https://github.com/user-attachments/assets/f7ffca35-52b0-48db-a46e-73188987bf4c" />
<img width="412" alt="52" src="https://github.com/user-attachments/assets/8a11460d-87df-40ee-bfa3-b89a92fc4e15" />
<img width="500" alt="54" src="https://github.com/user-attachments/assets/748629c8-aa25-4398-8324-d51758e4823a" />
<img width="422" alt="55" src="https://github.com/user-attachments/assets/846ee99a-f6a3-48c3-b7f2-ee2d50208eb6" />

Everyone has full access now.

<img width="587" alt="56" src="https://github.com/user-attachments/assets/b2609d22-ff2a-4abd-9cb9-e135ef69d0c4" />
<img width="280" alt="57" src="https://github.com/user-attachments/assets/b944985d-a482-40ea-8f1b-c16ba76e6dda" />

<h3> 1️⃣1️⃣ Install HeidiSQL </h3>

From the osTicket Installation Files folder, run HeidiSQL_12.3.0.6589_Setup

This lets you easily connect to your MySQL server, create a new database (osTicket), and inspect or modify tables. 

<img width="500" alt="59" src="https://github.com/user-attachments/assets/98372454-9f4c-4656-b071-705e8a08000a" />
<img width="450" alt="60" src="https://github.com/user-attachments/assets/e9f28e1d-1669-4431-a77b-fd5ff78b8c93" />
<img width="450" alt="61" src="https://github.com/user-attachments/assets/42700ad6-2665-4b72-9c2e-e146ea1f2d9b" />
<img width="450" alt="62" src="https://github.com/user-attachments/assets/0f84abac-9d2c-465c-8df3-ee52f3b5269f" />
<img width="450" alt="63" src="https://github.com/user-attachments/assets/b874219e-af39-482e-a78a-b05249d8dc35" />
<img width="450" alt="64" src="https://github.com/user-attachments/assets/fa00f301-5486-429c-a12b-4fbaaf50f7ad" />
<img width="452" alt="65" src="https://github.com/user-attachments/assets/f2b76b43-34de-4235-b1e3-a381ae49cfe6" />
<img width="294" alt="66" src="https://github.com/user-attachments/assets/5cba9f85-ba4e-467f-96d8-b1d0bf3b7242" />
<img width="450" alt="67" src="https://github.com/user-attachments/assets/02c21061-c47d-4b77-a403-c68cf31d57a9" />
<img width="450" alt="68" src="https://github.com/user-attachments/assets/d2264114-8d6e-4500-b7c9-2f29f309671e" />
<img width="524" alt="69" src="https://github.com/user-attachments/assets/28676a1d-ab36-453d-b3d1-df530f30d6a2" />
<img width="420" alt="70" src="https://github.com/user-attachments/assets/d0f05e86-73cb-4fa4-b8f4-00980195065b" />


<h3> 1️⃣2️⃣ Setup the database </h3>

<img width="540" alt="58" src="https://github.com/user-attachments/assets/74863475-8aca-4941-8165-73534d95c69d" />
<img width="390" alt="72" src="https://github.com/user-attachments/assets/c276a26d-4cf0-49b6-92ae-1d56536ca53a" />


<h3> 1️⃣3️⃣ Finalize and cleanup </h3>


