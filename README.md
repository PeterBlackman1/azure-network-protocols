<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>

![Screen Shot 2023-01-30 at 11 13 07 PM (2)](https://user-images.githubusercontent.com/120864279/215671542-2c6259dc-fae5-4499-bb5c-d513689d857e.png)

Logged into my DC-1 as my domain account admin.

<p>

![Screen Shot 2023-01-30 at 11 16 05 PM (2)](https://user-images.githubusercontent.com/120864279/215671865-17a8af26-bb99-4fe4-9ebf-69344adc120d.png)


Choose an account to log into in Client-1.

<p>

![Screen Shot 2023-01-30 at 11 19 11 PM (2)](https://user-images.githubusercontent.com/120864279/215672255-549b64de-0e5f-4f49-a3b7-3329562d10e1.png)

Logging into Client-1 under this user account.

<p>

  ![Screen Shot 2023-01-30 at 11 25 24 PM (2)](https://user-images.githubusercontent.com/120864279/215673265-12f03e44-79ca-492b-a834-dbdc0f9a88fb.png)

Created four folders on DC-1 in the C:\ drive. 

<p>

![Screen Shot 2023-01-30 at 11 29 40 PM (2)](https://user-images.githubusercontent.com/120864279/215673911-8cc4452f-9a75-4ba7-a130-389a44bd6fc5.png)

Changing the permissions on the "read-access" folder to allow access to the "Domain Users" group.

<p>
 
![Screen Shot 2023-01-30 at 11 36 20 PM (2)](https://user-images.githubusercontent.com/120864279/215674763-6f54fee3-a75d-40a0-806b-42f5009560c8.png)

Added the "Domain Users" to the group and now I'm able to click share.

<p>

![Screen Shot 2023-01-30 at 11 38 16 PM (2)](https://user-images.githubusercontent.com/120864279/215675083-9aa382ea-e035-4890-b9af-d348f35829f3.png)

Going into my "write-access" properties to assign the "Domain Users" permissions to "Read/Write" 

<p>

![Screen Shot 2023-01-30 at 11 40 29 PM (2)](https://user-images.githubusercontent.com/120864279/215675460-2beecc0e-f8bb-464c-ab96-eafbf6fcc4a1.png)

Now that I've assigned permissions in the to the "Domain Users" I can share and close the window.


<p>

![Screen Shot 2023-01-30 at 11 48 55 PM (2)](https://user-images.githubusercontent.com/120864279/215676707-9776a5af-7875-4711-9af9-92cf52154f8e.png)


Assigning permissions the "no-access" folder by adding "Domain Admins" to the share group and assign permissions of "Read/Write".

<p>
  
 ![Screen Shot 2023-01-30 at 11 54 28 PM (2)](https://user-images.githubusercontent.com/120864279/215677732-d3d30c4a-0f75-42fd-a8a2-736bbc4b9c84.png)

Going to the shared folder that I created on DC-1 to test and see if I can access the folders I created.

<p>

![Screen Shot 2023-01-30 at 11 56 40 PM (2)](https://user-images.githubusercontent.com/120864279/215678019-5216295a-49b4-49f1-9550-9ed5de93cde0.png)

Trying to access the "no-access" folder and was not able to due to permissions.

<p>

![Screen Shot 2023-01-30 at 11 58 06 PM (2)](https://user-images.githubusercontent.com/120864279/215678275-11bca547-da3a-4d96-8ac1-8ec384ba3609.png)

Tried to create a file in the "read-access" folder and was denied due to permissions.

<p>

  
![Screen Shot 2023-01-31 at 12 04 04 AM (2)](https://user-images.githubusercontent.com/120864279/215679388-16dac0c1-25eb-4263-b6e6-1191215d3138.png)

Created a text file in the "read-access" folder as an admin. When I logged back into Client-1 I was able to view and open the file.

<p>

![Screen Shot 2023-01-31 at 12 07 26 AM (2)](https://user-images.githubusercontent.com/120864279/215680279-0c66f2d3-728d-436d-b221-f7ba39389057.png)

In DC-1 I'm creating a "_SECURITY_GROUPS" folder
  
<p>

![Screen Shot 2023-01-31 at 12 09 08 AM (2)](https://user-images.githubusercontent.com/120864279/215680309-647d168d-808f-4578-aa86-e14cb9fd8a2e.png)

Adding an "ACCOUNTANTS" group to the security group that I created.
  
<p>
  
