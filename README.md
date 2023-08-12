<p align="center">
<img src="https://github.com/Jayjohn1337/azure-nsg/assets/67848718/fa470bca-8947-459a-a142-5fba3e63bc51)"/>
</p>

<h1>Network Security Groups (NSGs) in Azure Virtual Machines</h1>
In this tutorial, we utilize Azure Virtual Machines to experiment with Network Security Groups. <br />


<!--<h2>Video Demonstration</h2>-->

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Windows Server 2022

<h2>High-Level Steps</h2>

- Step 1: Create some sample file shares with various permissions
- Step 2: Attempt to access file shares as a normal User
- Step 3: Create an "ACCOUNTANTS" Security Group, assign permissions and test access

<h2>Actions and Observations</h2>

<h3>Create some sample file shares with various permissions</h3>

<p>
1a. Log into DC-1 with a domain admin account and log into Client-1 with a domain user account.<br>

1b. On DC-1, on the C:\ drive, create 4 folders; 1 with 'read access', 1 w/ 'write access', 1 w/ 'no access', and 1 named "accounting".<br>
<img src="https://github.com/Jayjohn1337/azure-network-protocols/assets/67848718/c25778ca-23fb-4021-a2e7-5b6f08e5d750"/><br>

1c. To set the permissions to read-only for the first folder, right-click the folder-- select Properties-- Sharing-- Share...-- type in 'domain users'-- Add-- under permission level select 'Read'-- Share-- Done.<br>
<img src="https://github.com/Jayjohn1337/azure-network-protocols/assets/67848718/5381b27d-c881-4720-904d-c9dc6ec6e217"/><br>

1d. For the 'write access' folder, repeat the process from '1c', except select 'Read/Write' under permission level.<br>

1e. For the 'no access' folder, repeat '1c' process, but instead of typing 'domain users' type 'domain admins' and select 'Read/Write'. By selecting Domain Admin and not selecting domain users, effectively domain users do not have access to the folder because it is not being shared with users who only have access as the group.<br>

</p>

<h3>Attempt to access file shares as a normal User</h3>

<p>
2a. Back on Client-1, open File Explorer. Then to find the shared folders, type '\\dc-1' in the middle input field.   
<img src="https://github.com/Jayjohn1337/azure-nsg/assets/67848718/e4fd6607-6654-4f1d-bf16-d28de8b3e6f9"/>    

2b. When attempting to open the folder that has no access to domain users, an error will produce.   
<img src="https://github.com/Jayjohn1337/azure-nsg/assets/67848718/8e71ad2b-590f-4fe1-9210-5f5d9feeafcc"/>    

2c. When accessing the 'read only' folder and attempting to create anything in the folder produce a different error.    
<img src="https://github.com/Jayjohn1337/azure-nsg/assets/67848718/cd93cc55-fdae-4a07-9d1f-88bb85ab8c99"/>   

2d. The folder with Read/Write access will not have any errors when utilizing the folder.   

</p>

<br />

<h3>Create an "ACCOUNTANTS" Security Group, assign permissions and test access</h3>

<p>
3a. Return to DC-1, in Active Directory, and create a security group called "ACCOUNTANTS". It's good practice to create an Organizational Unit (OU) called Security Group and create the "ACCOUNTANTS" group inside the Security Group, but for the lab, we'll create a OU ACCOUNTANTS and create the security group ACCOUNTANTS inside of it. Right-click ACCOUNTANTS OU-- New-- Groups-- type ACCOUNTANTS in Group name field-- make sure Security is selected under Group Type-- OK.   
<img src="https://github.com/Jayjohn1337/azure-nsg/assets/67848718/9b1e17fd-930b-44f3-b289-be7064849273"/>    

3B. On the "accounting" folder created earlier; set the permissions to the "ACCOUNTANTS" group and under the permission level set to "Read/Write".      

3c. Switching back to Client-1, when attempting to access the folder named "accounting", the error produced from '2b' will present itself.     

3d. Log out of Client-1. (One method: Open Command Prompt, type logoff, and press Enter.)     

3e. Add the domain user that was logged in to Client-1 to the ACCOUNTANTS Security Group to access the folder. In DC-1, Active Directory Users and Computers-- mydomain-- ACCOUNTANTS-- ACCOUNTANTS-- Members-- Add-- type in the domain user login name-- Check Names-- OK-- Apply-- Ok.    
<img src="https://github.com/Jayjohn1337/azure-nsg/assets/67848718/30c7ebbf-4f9a-4058-99a2-e9578b437957"/>

3f. Log back into Client-1 with domain user account. When accessing the 'accounting' folder the domain user will now have access.

</p>
<br />
