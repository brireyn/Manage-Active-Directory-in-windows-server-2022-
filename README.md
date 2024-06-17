# Manage-Active-Directory-in-windows-server-2022-
Create users, groups, and OUs (Organizational Units) in Active Directory Server 2022.

<h1>Managing Active Directory in Windows Server 2022 </h1>

<h2>Description</h2>
In this academic lab, new OUs, groups, and users are created in the previously created Globomantics domain controller. 
The group is then assigned to local file share to grant permissions for users. The computer is then removed from the domain. 

<h2>Lab walk-through:</h2>

Step 1 Creating the OU:
First connect to the Active Directory Domain controller.
![step1](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/ea929121-e01b-4202-9acc-951b33e00aa3)

Open Active Directory users and computers which shows the top of the AD Tree as the Globomantics.co Domain Controller.
![1b](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/9fee3cb6-e4f5-4240-9544-568ed0a80dfd)
There are three ways to create an OU in Active Directory:

A new Organizational unit is created in the existing AD Globomantics domain Controller by right-clicking on the domain controller and selecting create a new Organizational Unit.
![1c](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/7477115d-0dff-46d1-8962-186073327985)
![1f](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/c024e58e-0f0b-4dbe-b8e6-3afba36d1134)

OR 
Another way to create an OU in Active Directory is by selecting the Domain Controllers then right-click for the menu popup window - New - Organizational Unit. 
![1d](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/fd685d22-4d62-4c4a-997e-de418d3e06e0)

OR 
Click the OU container folder located in Active Directory Users and Computers:
![1e](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/cd383c10-4b87-4332-8131-dc58ac612237)

![1g](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/e5af1797-5ed7-4db3-8c26-de48f8a885f4)
It is always recommended to create a new top-level OU for new user objects, since can not apply Group Policy Objects to the default Computers and Users Containers. 

Step 2: Create a new User in the Globoticket Organizational Unit:
![2a](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/a424dc82-206a-4179-8c9a-bbe5d6b5a97c)
A temporary password is create a new user object in the Globoticket OU. The check box ensures the user changes the temporary password at the next logon for security purposes.
![2b](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/5dd6c707-36ef-4cbc-8273-02e5eb7a9442)

Here the user is created and showing under the Globoticket OU. 
![2c](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/54fe833c-b349-4fb1-a31d-f902fca22032)

Step 3: Create a file share access group 
A file share access group is created by right-clicking the Globoticket OU, select New - Group. This will allow local user access to a file share folder. 

![2d](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/f388c399-a46e-458f-b80f-d5f9fd1a79fc)


![2e](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/3720d29f-641c-4f8d-8327-f83fdb7df653)

Add the user to the group under File Share Access properties - Members tab:
![2f](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/6b65c762-f579-47e7-9213-129b968ec0ff)

Click add and then select the object name.
![3a](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/fa87c8d8-9008-41cf-baf1-d29ad14b23a9)

![3b](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/3dacd5c1-d667-44ec-835e-84cdec3f6b43)

![3c](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/04f2bee3-d130-44b4-8bb0-6f2d20c5ac11)
Create a new folder under the Network file share.

![3d](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/6b6affff-7072-4213-96cc-7f9660db0dd3)

Right click the folder and go to Edit under the folder security properties. 

![3e](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/5d69d900-3297-493b-90d8-bfef63250c38)
Permission list of the objects 
![3f](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/1762f54b-e215-4feb-a71f-3cf6d472a216)

Enter the object name of the shared folder “File Share Access”
![3g](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/6bf4ca3e-514f-4c80-81ec-7ace3d5154a6)
This process allows you to control access to a folder on a file share using membership in an Active Directory group. This is an easy way to implement Role Based Access Control (RBAC), as well as allowing a network administrator to grant or remove permissions on a file server without actually needing access to the data itself.

![3h](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/24d82465-c5f4-4599-9f3b-8e4e890c4530)

Step 4: Join a New Server to the Active Directory Domain:
Open a Windows desktop in a new tab. PS WIN1,, join the globomantics.co domain 
Currently the computer is not connected to the internet - connect to the internet Ethernet Adapter under Advanced Network Settings (Change Adapter Options).

![4a](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/144c9635-52ae-47d5-b74f-3650e5984a95)

![4b](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/96bdca92-c360-48fe-97a4-8ab53097d61c)

![4c](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/be5b2218-e18f-4b44-8e60-34b35471dbb9)

Connect to DNS server addresses manually and set as Preferred DNS server by clicking on Properties. 
![4d](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/6ae952fb-1d2b-45d5-82c7-5aacac69c9c4)
Then in Networking tab select Internet Protocol Version 4 (TCP/IPv4) check box. 
![4e](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/8ba4dd38-c24e-48e4-b98c-db65c879aea7)
To assign a static IPv4 address, Use the following IP address box should be filled out. DHCP is normally used for automatic IP assignment but static IP addresses are more secure. 
![4h](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/d1b619a9-55d2-4b49-ad3b-ce810760a83d)

On the Windows Settings window, type Advanced System Settings in the search box at the top, and select View advanced system settings.

Choose the Computer Name tab in the System Properties window.
![4j](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/576b498e-09c1-4ecd-8bd5-f1cc3c624f8e)

Click the Change... button to change the domain. 
![4k](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/3daf28c7-9570-48b0-b000-bb3ef5689f5a)
![4m](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/4570fdcf-0a69-4d49-8149-fab6e1d345b8)
![4n](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/43b494d4-d277-438e-bead-5e44bb7f49ec)

 Domain Name is updated and settings are applied. 
![5a](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/cccb6365-91f2-4ee1-9f1c-27ac3d6ea45b)

Changes take effect after you restart the computer when changing the computer domain. 
Back in the Active Directory Domain Controller VM - the PSWin1 computer is shown added to the domain under the file share. 
![5b](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/63dbd6c0-d302-4579-8302-0ad1430d6d7b)

Step 5: Create a new Group Policy Object in Active Directory and link it to an Organizational Unit. 
In the Domain Controller console, go to Windows Administrative tools and then Group Policy management. 

![5 c](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/5e3c0726-266e-40fc-81b2-7028ed0109e0)

In the left-hand pane, expand the item Forest: globomantics.co, then Domains, then globomantics.co.
![5d](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/875263e2-c1e9-4c8e-8641-42f33b4e98c2)
Under Group Policy Objects - create a new GPO and Name the Group Policy Object: User Settings.
![5e](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/758540f5-d04f-4640-88c0-6f9c5d7d9175)

![5f](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/dc18aa68-daec-4f71-a533-b078709a7def)
In the right-hand pane, right-click User Settings and choose Edit. This will start the Group Policy Management Editor.

![5g](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/9eae28c1-edb5-49f0-878b-92ed5bafff08)

In the right-hand pane, double-click Remove "Make Available Offline" command.
In the settings window for Remove "Make Available Offline" command, choose the Enabled option and click OK. 
![5h](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/01647f48-584c-4956-b414-730e9c2e0c3b)

Ensure "Enable" option is checked. 
![5j](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/016cdd4a-d85f-4919-bd76-c67476e9ffa8)

Verify the State for Remove “Make Available Offline” command is Enabled 
![5k](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/0231ca92-1138-42d5-8a17-5fcb3df6af70)

In the Group Policy Management window, right-click Globoticket and choose Link an Existing GPO....

![5m](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/59c52466-81a6-4cd6-8e04-48938a5bd3f2)

In the Select GPO window, choose User Settings and click OK.
![5n](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/3ad784f5-49b7-4bf8-8dcf-69ae038df02b)

Click Globoticket in the left-hand pane, and verify that User Settings is listed in the right-hand pane.
![5o](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/c8ef4a31-9001-4e70-88d9-789e334350c1)


<h3>To Remove a Windows desktop from AD </h3>
Inside of Active Directory Administrative Center console go to the domain controller and select the computer or workstation to delete

![5p](https://github.com/brireyn/Manage-Active-Directory-in-windows-server-2022-/assets/96150916/e0443937-a4e3-4e9b-bfe6-6d52879f9fc9)

Delete a computer from the domain through AD Administrative Center - then click delete to remove.



