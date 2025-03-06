![68747470733a2f2f692e696d6775722e636f6d2f436c7a6a3758732e706e67](https://github.com/user-attachments/assets/7a6cd4ef-0ab5-4609-80b8-b0377f3bbafd)


# osTicket - Prerequisites and Installation

Welcome to my detailed tutorial on how to successfully install the osTicketing Help Desk system.

## Environments and Technologies Used 

* Microsoft Azure
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

In the Azure portal, create a virtual machine (create a new resource group)
Remotely log into the newly created virtual machine with its IP address. 

### Step 2: Install and Enable IIS in Windows with CGI
![3  turn on IIS](https://github.com/user-attachments/assets/88b6946e-4b4a-43a5-9168-a97e3adcf3b6)

This will help bridge the gap to allow applications to host on to the browser. 
> Open the control panel > programs > turn windows features on/off > find Internet Information Services > open Application Development Features tab > check CGI > ok












