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
6)	Select the region (e.g., Central India).
7)	Click "Review + Create" and then "Create".
8)	Repeat to create "ProductionResourceGroup" and "DevelopmentResourceGroup".

<img width="957" alt="image" src="https://github.com/user-attachments/assets/2ca5f843-91f7-418a-80ae-cbaa0bf4721d">

<img width="947" alt="image" src="https://github.com/user-attachments/assets/91aa3d9a-becc-4cc3-ae31-391a03fbc830">


**Step 2: Set Up the Virtual Networks**

****Create Virtual Network for Management Environment:**
1)	Go to "Virtual networks".
2)	Click "Add".
3)	Enter the following details:
4)	Name: ManagementVNet
5)	Address space: 10.0.0.0/16
6)	Subnet name: ManagementSubnet
7)	Subnet address range: 10.0.0.0/24
8)	Resource group: ManagementResourceGroup
9)	Location: (e.g., Central India)
10)	Click "Review + Create" and then "Create".

<img width="873" alt="image" src="https://github.com/user-attachments/assets/b8fcf7fd-38b5-4e88-b549-e66381179eb1">


**Create Virtual Network for Production Environment:**

****Repeat the steps for creating ProductionVNet:**
1.	Name: ProductionVNet
2.	Address space: 10.1.0.0/16
3.	Subnets:
i.	WebSubnet: 10.1.1.0/24
ii.	AppSubnet: 10.1.2.0/24
iii. DBSubnet: 10.1.3.0/24
4.	Resource group: ProductionResourceGroup

<img width="757" alt="image" src="https://github.com/user-attachments/assets/b360fe37-6d03-4581-aa65-81ec00769789">


**Create Virtual Network for Development Environment:**

****Repeat the steps for creating DevelopmentVNet:**
1)	Name: DevelopmentVNet
2)	Address space: 10.2.0.0/16
3)	Subnets:
I.	WebSubnet: 10.2.1.0/24
II.	AppSubnet: 10.2.2.0/24
III.	DBSubnet: 10.2.3.0/24
4)	Resource group: DevelopmentResourceGroup

<img width="664" alt="image" src="https://github.com/user-attachments/assets/062095d3-a433-4b5b-824b-a2c7d1b98d53">


**Step 3: Deploy Virtual Machines (VMs)**

****Create Bastion Host for Management Environment:**
1)	Go to "Virtual machines".
2)	Click "Add".
3)	Enter the following details:
i.	Subscription: Your subscription
ii.	Resource group: ManagementResourceGroup
iii.	Name: ManagementBastion
iv.	Region: (e.g., Central India)
v.	Image: Choose an appropriate OS (e.g., Windows Server 2019)
vi.	Size: Select an appropriate size (e.g., Standard_B2s)
vii.	Authentication type: Password
viii.	Username: AzureAdmin
ix.	Password: Enter a strong password
x.	Public inbound ports: None
xi.	NIC network: ManagementVNet -> ManagementSubnet
4)	Click "Next: Disks" -> "Next: Networking" -> "Review + Create" -> "Create".

<img width="689" alt="image" src="https://github.com/user-attachments/assets/eb45ed3f-14e9-446b-8ac9-f2d06ad5f396">


**Create VMs for Production Environment:**

****Repeat the VM creation process for Production VMs:**
1)	WebTier VM:
i.	Resource group: ProductionResourceGroup
ii.	Name: ProdWebVM
iii.	Region: (e.g., Central India)
iv.	NIC network: ProductionVNet -> WebSubnet
2)	AppTier VM:
i.	Resource group: ProductionResourceGroup
ii.	Name: ProdAppVM
iii.	NIC network: ProductionVNet -> AppSubnet
3)	DBTier VM:
i.	Resource group: ProductionResourceGroup
ii.	Name: ProdDBVM
iii.	NIC network: ProductionVNet -> DBSubnet





