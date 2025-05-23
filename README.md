<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Configure Roles (for grouping permissions)
- Configure Departments (Ticket Visibility, Help Desk vs SysAdmins, vs Networking)
- Configure Teams
- Allow anyone to create tickets
- Configure Agents (workers)
- Configure Users (customers)
- Configure SLA (Service Level Agreement)
- Configure Help Topics (For when users create a ticket)

<h2>Configuration Steps</h2>

In this lab exercise, we will alternate between the Admin Panel and the Agent Panel within the osTicket system. The Admin Panel is utilized for configuring system settings and managing backend operations, whereas the Agent Panel is designed for help desk personnel to access, manage, and respond to support tickets.

<b>1. Configure Roles</b> <br />
- On your Windows VM, open a browser and access to osTicket website (http://localhost/osTicket/scp/login.php).
- Login to the Help Desk login page with credentials created previously:
- Username: adminuser
- Password: Password1

![image](https://github.com/user-attachments/assets/ffa6bb24-8379-48e3-abdb-5554f0357532)

- Select Admin Panel (Top right).

![Screenshot 2025-05-13 121013](https://github.com/user-attachments/assets/ce458901-fc1c-4264-8afb-fdac347a6121)

- Admin Panel -> Agents -> Roles.

![image](https://github.com/user-attachments/assets/e2d384af-362e-4994-8d4c-08dd9e031056)

- To create a new role click on 'Add New Role'.

![image](https://github.com/user-attachments/assets/cfc23e56-143d-477d-b7a1-5f5f651d4927)

- Name: Supreme Admin

![image](https://github.com/user-attachments/assets/7a737702-d23a-473e-8f05-89907d5179d0)

- On the Permissions tab, permit all Tickets, Tasks, and Knowledgebase for that role.
- Click 'Add Role'.

![image](https://github.com/user-attachments/assets/b59d1e0c-fded-47ea-b9fc-285c6ea60e3d)

![image](https://github.com/user-attachments/assets/c8cbcd98-ea13-4580-8bbe-fa9aef733161)

![image](https://github.com/user-attachments/assets/2c80aa7e-4483-4bde-9949-02bc26aff17a)

![image](https://github.com/user-attachments/assets/7eda7026-2b53-4d00-8d3f-e5b66b7195cd)

<b>2. Configure Departments</b> <br />

- We are going to create a new department called "SysAdmins". To do this go to Departments Under Agents.
- Click on 'Add New Department'.

![image](https://github.com/user-attachments/assets/6b40722a-bddb-47f5-a18f-2ea827aa9c59)

- In the Setting Tab, Make sure Parent = TopLevelDepartment. We can configure things like SLAs (Service Level Agreements) here but not required for this lab.
- Name: SysAdmins
- We can also add "Agents" to departments here but we can come back and configure this later.
- Click "Create Department". 

![image](https://github.com/user-attachments/assets/db3dc9b6-f5e2-42ea-97d3-e52c65ed8db2)

![image](https://github.com/user-attachments/assets/5bcbc881-60e0-4f2d-90a9-aa98dc0b28ac)

<b>3. Configure Teams</b> <br />

- Teams allow us to create a group of people from different departments. Create a team within our simulated organization named 'Online Banking,' which will include members of the online banking team as well as help desk agents
- To do this go to Yeams Under Agents.
- Click 'Add a New Team'.

![image](https://github.com/user-attachments/assets/99181406-1717-4ba4-bb20-6deac530c5cd)

- Name: Online Banking
- Click 'Create'.
- In this lab, we will create more members later.

![image](https://github.com/user-attachments/assets/57c43f7f-b618-4049-a8f2-4fcd878eed05)

![image](https://github.com/user-attachments/assets/2a4c045c-d19a-4113-bde8-db7d2d353302)

<b>4. Allow anyone to create tickets</b> <br />

- We'll now check ticket creation for all users that registration is not required. In the Admin Panel, click on Settings -> Users. Uncheck: "Require registration and login to create tickets."

![image](https://github.com/user-attachments/assets/18f1775e-44f5-4e0d-9a89-280b77d69e43)

<b>5. Configure Agents</b> <br />

- We are going to create a couple of help desk agents to do tickets with. One will be Jane (Assigned to SysAdmins Department) and the other John (Assigned to the Support Department).
- In the Admin Panel go to Agents then click 'Add New Agent'.

![image](https://github.com/user-attachments/assets/859a617a-2ec4-4414-abd9-943d0285e10f)

osTicket Agent 1
- Name: Jane Doe
- Email Address: Jane@lognpacific.com
- Username: jane

![image](https://github.com/user-attachments/assets/10c346cf-8808-46a4-8c20-91a9d241482f)

- Click Set Password -> Uncheck "Send the agent a password reset email". Enter the password and make sure "Require Password change at next login" is set to off.
- Password: Password1

![image](https://github.com/user-attachments/assets/612ba88f-d3b7-4e86-87ea-deaa029b8b1c)

- Select the "Access" tab. Under "Primary Department" select "SysAdmins" and then choose the "Supreme Admin" role. Next is optional, under "Extended Access" choose "Support".

![image](https://github.com/user-attachments/assets/b7c77aee-50b6-4f27-abbe-fdce50e30b04)

- Select the "Teams" tab and assign her to the "Online Banking" team.
- Click 'Create'

![image](https://github.com/user-attachments/assets/b642f89b-83e9-4ccc-97be-b7e3a6db25bf)

![image](https://github.com/user-attachments/assets/b53e742a-c753-4bae-9c69-0a4cf09a4ea6)

- We are going to create another Agent. In the Admin Panel go to Agents then click 'Add New Agent'.

![image](https://github.com/user-attachments/assets/7642188e-aece-4c21-ac82-35785c954067)

osTicket Agent 2
- Name: John Doe
- Email Address: John@lognpacific.com
- Username: john

![image](https://github.com/user-attachments/assets/ccfd04eb-d8d7-459f-be7d-e505f43b4ccc)

- Click Set Password -> Uncheck "Send the agent a password reset email". Enter the password and make sure "Require Password change at next login" is set to off.
- Password: Password1

![image](https://github.com/user-attachments/assets/4c9e7488-9d16-445b-a12e-694a7c5be4aa)

- Select the "Access" tab. Under "Primary Department" select "Support" and then choose the "Supreme Admin" role. We don't need to add John to a team.
- Click 'Create'.

![image](https://github.com/user-attachments/assets/e7e24ec6-b2f9-4f01-b589-91234c2f369c)

![image](https://github.com/user-attachments/assets/5475f003-6bf5-4a8c-853f-84a614435973)

<b>6. Configure Users</b> <br />

- Next, we will create a customer's who will be used to submit tickets to the help desk. Our customer name will be "Karen".
- To start, go to Agent Panel -> Users -> Click "Add New User".

![image](https://github.com/user-attachments/assets/e1b47588-8528-43ae-b5ac-8fec5d58db61)

- Insert the following information
- Email: karen@lognpacific.com
- Full Name: Karen
- Click 'Add User'.

![image](https://github.com/user-attachments/assets/732ac44c-f80c-4b95-a584-98dc308b0888)

![image](https://github.com/user-attachments/assets/0d7a99b7-5db8-4f46-a089-c02f29d94e37)

<b>7. Configure SLA</b> <br />
The purpose of SLAs (Service Level Agreements) is to clearly define the expected level of service between a provider and a customer, including performance standards, responsibilities, and consequences if those standards aren’t met. We are going to create 3 SLAs:
- Sev-A (Severity A - Highest Priority) - (Grace Period: 1 hour, Schedule: 24/7)
- Sev-B (Severity B - Mid Priority) - (Grace Period: 4 hours, Schedule: 24/7)
- Sev-C (Severity C - Lowest Priority) - (Grace Period: 8 hours, [Business Hours])

- Go to Admin Panel -> Manage -> SLA -> Add New SLA Plan.

![image](https://github.com/user-attachments/assets/a90248d5-c93c-4085-a1ea-399ec4dba1fb)

- Insert the following information
- Name: Sev-A
- Grace Period: 1 hour
- Schedule: 24/7
- Click 'Add plan'

![image](https://github.com/user-attachments/assets/8051bc48-3fe8-47b4-9453-4663b960a2c9)

![image](https://github.com/user-attachments/assets/7648b81e-3bdb-4f82-a5c7-4edea6715df5)

- Click 'Add New SLA Plan'.
- Insert the following information
- Name: Sev-B
- Grace Period: 4 hours
- Schedule: 24/7
- Click 'Add plan'

![image](https://github.com/user-attachments/assets/805bd63c-214b-4e3e-97d2-5195e1505588)

![image](https://github.com/user-attachments/assets/68e6d3eb-ccf1-4019-9d77-ddd075e20e63)

- Click 'Add New SLA Plan'.
Insert the following information
- Name: Sev-C
- Grace Period: 8 hours
- Schedule: Monday - Friday 8 am - 5 pm with U.S. Holidays (Business Hours)
- Click 'Add plan'

![image](https://github.com/user-attachments/assets/ea25aad1-96a8-4089-b624-52b3be443e84)

![image](https://github.com/user-attachments/assets/ecf3f3a3-09f8-4cff-aab8-75b1a72929cd)

<b>8. Configure Help Topics</b> <br />

Configuring Help Topics lets you organize and route support requests by category (like "Technical Support"). This helps users pick the right type of issue, so tickets go to the right department or staff.
- Admin Panel -> Manage -> Help Topics.
- You will notice that 4 default Help Topics have already been created in the database. For this part, we are going to create 5 Help Topics
- Click 'Add New Help Topic'.

![image](https://github.com/user-attachments/assets/d1242942-9fc4-460c-a54b-920b3a80ffbe)

Topic: Business Critical Outage
Parent Topic: Report a Problem
- Click 'Add Topic'.

![image](https://github.com/user-attachments/assets/02ad8828-6177-4170-bd33-e2575fba0837)

- Help Topics -> Add New Help Topic
Topic: Personal Computer Issues
Parent Topic: Report a Problem
- Click 'Add Topic'.

![image](https://github.com/user-attachments/assets/6ab1f154-d0e2-48a9-85ed-a4d53d049505)

- Help Topics -> Add New Help Topic
Topic: Equipment Request
Parent Topic: General Inquiry
- Click 'Add Topic'.

![image](https://github.com/user-attachments/assets/0d2ab7c5-4dda-4f52-b264-52a107670556)

- Help Topics -> Add New Help Topic
Topic: Password Reset
Parent Topic: Report a Problem
- Click 'Add Topic'.

![image](https://github.com/user-attachments/assets/ecda6837-dae9-4f00-89e1-e5174e0b6703)

- Help Topics -> Add New Help Topic
Topic: Other
Parent Topic: General Inquiry
- Click 'Add Topic'.

![image](https://github.com/user-attachments/assets/9960c9b6-a806-4470-a103-a2f2c52075ca)

![image](https://github.com/user-attachments/assets/4840b6fc-8b21-4c40-b85d-5a613443dc1c)








