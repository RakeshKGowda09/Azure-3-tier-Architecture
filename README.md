# Azure-3-tier-Architecture
Building a 3-tier architecture in Azure

![1662126774141-transformed](https://github.com/user-attachments/assets/4365f12f-fde3-4f7e-b25a-0bfe36c1272a)

The architecture depicted in the image is a comprehensive setup involving multiple environments (production and development), including Azure services like Virtual Networks, Virtual Machines, Load Balancers, Application Gateways, SQL Databases, Key Vault, and others. Below are the steps to create this architecture in Azure:

**Step 1: Create Resource Groups**
1)	Navigate to the Azure Portal.
2)	Create Resource Groups:
3)	Go to "Resource groups" from the left-hand menu.
4)	Click "Add".
5)	Enter the resource group name: "ManagementResourceGroup".
6)	Select the region (e.g., East US).
7)	Click "Review + Create" and then "Create".
8)	Repeat to create "ProductionResourceGroup" and "DevelopmentResourceGroup".

[<img width="957" alt="image" src="https://github.com/user-attachments/assets/2ca5f843-91f7-418a-80ae-cbaa0bf4721d">]

[<img width="950" alt="image" src="https://github.com/user-attachments/assets/b943adcb-942e-446d-a9a0-8fe626fcd419">]

**Step 2: Set Up the Virtual Networks**
1)	Create Virtual Network for Management Environment:
2)	Go to "Virtual networks".
3)	Click "Add".
4)	Enter the following details:
5)	Name: ManagementVNet
6)	Address space: 10.0.0.0/16
7)	Subnet name: ManagementSubnet
8)	Subnet address range: 10.0.0.0/24
9)	Resource group: ManagementResourceGroup
10)	Location: (e.g., East US)
11)	Click "Review + Create" and then "Create".



