# Active-Directory-Setup

![download](https://github.com/user-attachments/assets/bbe0457f-3947-4a8b-92d8-f83c828ff609)


Step-by-step guide to installing and configuring Active Directory on Windows Server 2022.

Introduction
Brief overview of Active Directory and its purpose.
Mention prerequisites and target audience.
Outline the tutorial structure.

## Prerequisites

- VMware Workstation Pro (can also be completed with VirtualBox)
- Windows Server 2022 ISO file
    - https://info.microsoft.com/ww-landing-windows-server-2022.html

### Step 1: Install Windows Server

Open VMware and create a new virtual machine.

![image](https://github.com/user-attachments/assets/77602b97-2a04-488c-bebd-fc0e99c9dd63)

Keep configuration as "Typical" and click next.

---
![image](https://github.com/user-attachments/assets/dad07bb3-e42f-4f4d-9ea7-0a4c1522a09c)

Select "Browse..." and choose your downloaded Windows Server 2022 ISO file. 
(Note: below the file path, the OS should be detected) <br /> 
Click next.

---
![image](https://github.com/user-attachments/assets/bcd34f60-c396-4dfc-a544-24dd4d929f71)

Add a name and password to log into the server initially. (This will change later on) <br />
Click next.

---
![image](https://github.com/user-attachments/assets/0f2c21ab-7bbb-4e03-b81f-ffcc989f65f5)

Set a name for the VM and choose a file location on your PC for it to be stored. <br />
Click next.

---

Follow the steps to configure the initial setup (date/time, network settings, etc.).
Activate the Windows Server license (if applicable).
Step 2: Assign a Static IP Address
Open the Network and Sharing Center.
Configure the static IP address:
IP Address: 192.168.x.x
Subnet Mask: 255.255.255.0
Default Gateway: 192.168.x.1
DNS: Leave as the same as the IP address.
Save the configuration and test connectivity.
Step 3: Install Active Directory Domain Services (AD DS)
Launch Server Manager.
Click on Add Roles and Features.
Follow the wizard and select the Active Directory Domain Services role.
Accept required features and continue through the wizard.
Click Install and wait for completion.
Step 4: Promote Server to Domain Controller
In Server Manager, click the notification flag and select Promote this server to a domain controller.
Choose:
Add a new forest (if starting from scratch).
Specify a root domain name (e.g., example.com).
Configure the domain controller options:
Functional level: Windows Server 2016 or higher.
DNS server: Check the box.
Set a strong Directory Services Restore Mode (DSRM) password.
Confirm selections and complete the configuration wizard.
Restart the server.
Step 5: Verify Active Directory Installation
Log in to the server using the domain administrator account.
Open Active Directory Users and Computers (ADUC) to confirm domain setup.
Verify DNS configuration:
Open DNS Manager.
Check for forward and reverse lookup zones.
Step 6: Add Users and Groups
Open ADUC.
Create an organizational unit (OU):
Right-click on the domain > New > Organizational Unit.
Name the OU (e.g., IT Department).
Add users:
Right-click on the OU > New > User.
Fill in user details and set passwords.
Create groups:
Right-click on the OU > New > Group.
Assign members to the group.
Step 7: Additional Configuration (Optional)
Configure Group Policies:
Open Group Policy Management.
Create and link a Group Policy Object (GPO).
Set up file sharing.
Enable security settings as per organizational needs.
Step 8: Test the Configuration
Join a client machine to the domain:
Open System Properties > Change settings > Domain.
Enter the domain name and provide credentials.
Verify login with the new domain account.
Conclusion
Summarize the process and provide next steps for further configurations.
Include links to official Microsoft documentation or helpful resources.
</p>
