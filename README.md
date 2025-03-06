![68747470733a2f2f692e696d6775722e636f6d2f436c7a6a3758732e706e67](https://github.com/user-attachments/assets/7a6cd4ef-0ab5-4609-80b8-b0377f3bbafd)


# osTicket - Prerequisites and Installation

Welcome to my detailed tutorial on how to successfully install the osTicketing Help Desk system.

## Environments and Technologies Used 

* Microsoft Azure (Virtual Machines/Compute)
* Remote Desktop
* Internet Information Services (IIS)

## Operating Systems Used

* Windows 10 Pro (22H2)

## List of Prerequisites

* Virtual Machine (Windows 10 Pro)
* IIS (Internet Information Services) & CGI
* PHP 7.3.8 Manager for IIS
* IIS URL Rewrite Module
* VC.15
* MySQL 5.5.62
* osTicket v1.15.18
* HeidiSQL

## Installation Steps 
### Step 1: Create a Virtual Machine in Azure
![1  create VM](https://github.com/user-attachments/assets/fcb09ff2-9cdd-45be-9b9e-850a33164aaa)
![2  remotely log in](https://github.com/user-attachments/assets/6ff5af90-b1ab-4777-a27e-041ad99b0690)

In the Azure portal, create a virtual machine (create a new resource group).
Remotely log into the newly created virtual machine with its IP address. 

### Step 2: Install and Enable IIS in Windows with CGI
![3  turn on IIS](https://github.com/user-attachments/assets/88b6946e-4b4a-43a5-9168-a97e3adcf3b6)

This will help bridge the gap to allow applications to host on to the browser. 
> Open the control panel > programs > turn windows features on/off > find Internet Information Services > open Application Development Features tab > check CGI > ok

### Step 3: Download the Necessary Programs 
![4  install PHP manager](https://github.com/user-attachments/assets/176d901d-1b46-4b9b-abee-392a88d28056)
![5  install IIS rewrite module](https://github.com/user-attachments/assets/826154a8-3e8c-40b4-9fc7-b210f29e41b6)

The link below will give you a list of the programs you need for this installation. Once downloaded, check the browser to see if they are successfully downloaded. 
https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6 
Begin to install the PHP Manager and Rewrite Module program.

### Step 4: Create a new folder in the C: file
![6  create PHP file](https://github.com/user-attachments/assets/660bf91c-83cf-408b-a8da-08eb5af6dd4f)
![7  move extracted PHP file](https://github.com/user-attachments/assets/ad35fc63-885f-4ab3-a8e7-75b359362079)

> Open external files > create a new folder called “PHP” > go back to the browser and open the downloaded PHP folder > extract > select destination to the new PHP folder created.

### Step 5: Finish Installing the Required Programs 
![8  download vs code](https://github.com/user-attachments/assets/6bdd411a-04a8-4c2b-8232-279f8ae8eec2)
![9  download SQL](https://github.com/user-attachments/assets/22fb70e3-2db4-4006-b8ec-11809edb0a53)

> Go back to browser > download VC15 > download MySQL (standard installation) > create username and password

### Step 6: Register PHP in IIS Manager
![10  set up cgi in IIS for PHP](https://github.com/user-attachments/assets/e7d0436b-ef5f-412e-bdb9-666a26ac000f)

> Open IIS Manager > click PHP Manager > Register new PHP version > go to PHP folder > select php-cgi > ok

### Step 7: Install osTicket
![11  rename upload file to osTicket](https://github.com/user-attachments/assets/f86e10f4-d4e8-4301-99b8-41b3803dd8cf)

Go back to the web browser and download the osTicketing system 
> Open downloaded file and extract > copy “upload” file and paste into the “c:\inetpub\wwwroot” folder (Windows > inetpub > wwwroot) > rename “upload” file to “osTicket” > restart IIS Manager

### Step 8: Enable Extensions in IIS Manager for Ticketing System
![12  open osTicket in IIS](https://github.com/user-attachments/assets/1ae3c6d3-3463-4743-ac13-88987218b535)
![13  osTicket from IIS](https://github.com/user-attachments/assets/19f94f25-ae2d-49d7-9714-b8a18648e576)
![14  enable php_imap   php_intl](https://github.com/user-attachments/assets/60dff2b7-08e5-43a6-9b94-c2c3f8a1af9e)
![15  reload page](https://github.com/user-attachments/assets/5684b4d3-4d12-4aff-ba9e-18f8b7c03c3c)

> Open IIS Manager > In the Connections column, click “VM-OST” > sites > Default Web Site > osTicket > on the right column under Manage Folder, click “Browse *80 (https).
In the “osTicket” folder under the connections column, select PHP Manager > Enable or disable an extension > enable the extensions that need to be enabled  
- Enable: php_imap.dll	
- Enable: php_intl.dll
- Enable: php_opcache.dll
  
Refresh browser page to see if the recommended feature have been updated.

### Step 9: Rename “ost-config.php” and Assign Permissions: ost-config.php
![16  rename file in osTicket](https://github.com/user-attachments/assets/df433fa5-9349-424c-921b-89ccdc6965f8)
![17  disable inheritance](https://github.com/user-attachments/assets/e3432f5b-f413-463d-9596-9bec9c5ad652)
![18  set to everyone](https://github.com/user-attachments/assets/b824f335-db2a-4668-81af-83a4570a8627)
![19  allow full control](https://github.com/user-attachments/assets/951fd266-7e73-4b01-9b1e-c72caf60c485)
![19  full control updated](https://github.com/user-attachments/assets/b3232287-1460-45fc-90d3-109379117e91)

> In the file explorer, select “osTicket” (This PC > Windows (C:) > inetpub > wwwroot > osTicket > include > rename “ost-sampleconfig.php” to  “ost-config.php” > ost-config.php > Properties > Security > Advanced > Disable inheritance > remove inheritance permissions > Add > select a principal > in the empty white box type in “everyone > ok > allow full control > apply > ok > ok

### Step 10: Finish Setting up osTicket Installer
![20  install heidiSQL](https://github.com/user-attachments/assets/9a7b091b-4149-44ff-98d4-265ed6ec79b0)
![21  set up new database](https://github.com/user-attachments/assets/0edcf438-e7b5-40a5-ab68-ed2c38349486)
![22  complete installation](https://github.com/user-attachments/assets/4d11ec76-fec9-4ba3-baee-e90d51acf6ae)
![23  complete installation](https://github.com/user-attachments/assets/7734894c-9d54-467f-966f-99f94bcee053)

Go back to the web browser > complete basic installation 
Download HeidiSQL > create a new section > give a password > Open 
On the left column under “Unnamed”, select Create New > Database > name “osTicket” > ok
Fill in the Database Setting with the same into > Install Now














