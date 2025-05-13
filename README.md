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

1. Configure Roles

- On your windows VM, open a browser and access to osTicket website (http://localhost/osTicket/scp/login.php).
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

- On the Permissions tab, give permissionn to all Tickets, Tasks and Knowledgebase for that role.
- Click 'Add Role'.

![image](https://github.com/user-attachments/assets/b59d1e0c-fded-47ea-b9fc-285c6ea60e3d)

![image](https://github.com/user-attachments/assets/c8cbcd98-ea13-4580-8bbe-fa9aef733161)

![image](https://github.com/user-attachments/assets/2c80aa7e-4483-4bde-9949-02bc26aff17a)

![image](https://github.com/user-attachments/assets/7eda7026-2b53-4d00-8d3f-e5b66b7195cd)


2. Configure Departments


3. Configure Teams


4. Allow anyone to create tickets


5. Configure Agents


6. Configure Users


7. Configure SLA


8. Configure Help Topics

   


----------------------------------------------------
----------------------------------------------------

Admin/Analyst Login Page:
http://localhost/osTicket/scp/login.php 

End Users osTicket URL:
http://localhost/osTicket 

Acknowledge Agent Panel vs Admin Panel

Configure Roles (for grouping permissions)
Admin Panel -> Agents -> Roles
- Supreme Admin

Configure Departments (Ticket Visibility, Help Desk vs SysAdmins, vs Networking)
Admin Panel -> Agents -> Departments
- SysAdmins

Configure Teams
Admin Panel -> Agents -> Teams (Pull Agents from different Departments)
- Online Banking

Allow anyone to create tickets
Admin Panel -> Settings -> User Settings (UNCHECK: unregistered users can create tickets)
- Registration Required: Require registration and login to create tickets 

Configure Agents (workers)
Admin Panel -> Agents -> Add New
- Jane (Dept: SysAdmins)
- John (Dept: Support)

Configure Users (customers)
Agent Panel -> Users -> Add New
- Karen
- Ken

Configure SLA
Admin Panel -> Manage -> SLA
- Sev-A (Grace Period: 1 hour, Schedule: 24/7)
- Sev-B (Grace Period: 4 hours, Schedule: 24/7)
- Sev-C (Grace Period: 8 hours, Business Hours)

Configure Help Topics (For when users create a ticket)
Admin Panel -> Manage -> Help Topics
- Business Critical Outage
- Personal Computer Issues
- Equipment Request
- Password Reset
- Other




