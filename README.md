<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
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


</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
