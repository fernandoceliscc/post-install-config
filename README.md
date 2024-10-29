<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket - Post-Install Configuration

This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

## Operating Systems Used

- Windows 10 (21H2)

## Post-Install Configuration Objectives

- Installation of osTicket
- Configure Roles
- Configure Departments
- Configure Teams
- Configure Agents
- Configure Users
- Configure SLA
- Configure Help Topics

## Configuration Steps

<p align="center">
  <img src="https://imgur.com/UNDO5Wp.png"/>
</p>

This is a follow-up to my [osTicket- Prerequisites and Installation](https://github.com/GGeeto/osticket-prereqs). Begin by navigating to the 'Admin Panel'. Click on the 'Agents' tab and then access the 'Roles' sub-tab. This section allows you to create roles and customize permissions based on specific needs. While you'll find preinstalled roles listed, we'll be crafting a new one for our project.


Select 'Add New Role' and label it as 'Admin'. Proceed to the 'Permissions' section and ensure that every box across all three tabs, from tickets to tasks to the knowledge base, is checked. This role grants the assigned user full access to interact with, modify, or view any aspect of the site.

<p align="center">
  <img src="https://imgur.com/Zrj2Qj5.png"/>
</p>

Now you can click on the 'Departments' sub-tab. Departments are used to organize teams into their specific expertise, such as networking, technical support, sales, etc. This helps determine the most suitable place for a ticket to be sent. By default, the Maintenance and Support departments should be present.


Same as before, we are going to ignore this and create a new one. Click 'Add new department' and name it Administrators. Click on the circled question marks next to the text to get an idea of what can be configured. For this project, we are going to set our own account as the Manager and leave everything else at its default.

<p align="center">
  <img src="https://imgur.com/40lL0P8.png"/>
</p>

Now we are going to click on the 'Teams' sub-tab. Teams are used to group agents together to specialize in specific skills within the department, such as a Customer Service department containing billing, quality assurance, and technical support teams. These all have different tasks but can all be categorized under customer service. Additionally, teams can be separated by the level of experience users have. By default, Level 1 support should be present.


We are going to ignore this as well and create a new team. Click 'Add new team' and name it Level 2 Support. We are going to leave everything else at its default but once again click the tooltips for understanding.

<p align="center">
  <img src="https://imgur.com/40lL0P8.png"/>
</p>

Now, navigate to the 'Agents' sub-tab, where users within the teams are managed. Agents should ideally possess moderately similar skill sets for completing tasks assigned to their respective teams. Differences in experience can lead to tickets being assigned based on their difficulty level, such as someone with many years of experience being assigned a Sev-A ticket, while someone newer to the position might be assigned a Sev-C ticket. By default, your user account should be present.


We are going to create two more agents. Click 'Add new agent,' and all of the account information is at your discretion. If you are conducting the project as an experiment, I would recommend using fabricated information for the account details. Similarly, for the username, ensure it is memorable. Click 'Set password,' uncheck the box, and then create a password that you will remember. Uncheck the box that says 'Require password change next login' and click 'Set.' Now, click on 'Access' and assign the agent to the Administrators Department with the admin role. Proceed to the permissions tab and ensure that everything is checked. Then, click 'Create.' Now, add a different user but set their department to Maintenance and their role as limited access. Skip permissions and assign them to the Level 2 Support team.

<p align="center">
  <img src="https://imgur.com/AniRtGq.png"/>
</p>

Next, we are going to add users. Users are the individuals creating the tickets, so basically, the people that need a problem solved. This could be customers, employees, students, etc.


We are going to switch from the admin panel to the agent panel. Click the orange 'Agent Panel' text in the top right, and the page should reload, displaying 'Admin Panel' instead. Then, click on the 'Users' tab. By default, 'osTicket Support' should be listed as a user. We are going to add two more users. Click 'Add user,' and the information entered should also be fabricated but memorable or written down. Only write down information in a lab/experiment setting, as it is insecure to record any sort of real personal information. Click 'Add user,' and their account should appear. You can click on 'Register' with the smiley face next to it, and then 'Create account.' Next, click on 'More,' and then 'Manage account access.' From here, you can create the username and password. This will unlock the user's account.

<p align="center">
  <img src="https://imgur.com/xdp3AdT.png"/>
</p>

Next, we are going to create SLAs or Service Level Agreements. These are expectations and agreements on how efficient tickets are handled as well as the priority degrees of tickets. Priority is commonly Sev method or severity. For example, Sev C would be considered a lower priority than Sev A commonly. They are also used to measure the performance of employees handling the tickets, similar to the way a fast-food place measures the amount of food sold in a certain period of time to gauge speed.


Return to the Admin Panel, then navigate to the manage tab and access the SLA sub-tab. You'll see a 'default SLA' listed. Let's create 3 additional SLAs. Click 'Add new SLA plan' and name it Sev-A. Set the Grace period to 1 hour, indicating the ticket must be addressed/resolved within an hour. Choose a 24/7 schedule, extending beyond regular business hours. Then, click 'Add plan.' Name the next SLA Sev-B, with a 4-hour grace period and a 24/7 schedule, requiring resolution within 4 hours, even outside business hours. Finally, add Sev-C with an 8-hour grace period and a 24/5 schedule, meaning it's resolved within business hours only. For instance, if a ticket is created at 6 pm on Friday, closing at 10 pm and reopening at 12 pm, it must be resolved by 4 pm on Saturday.

<p align="center">
  <img src="https://imgur.com/o73ePg8.png"/>
</p>

Lastly, we are going to create help topics for the users to categorize their tickets with. These will have different priorities and Departments assigned to them depending on the topic. For example, a Feedback topic is going to have less priority than something like a technical problem. And a feedback topic would be set to the customer service department whereas a technical issue would be assigned to technical support.


To proceed, navigate to the Help Topics sub-tab where you'll encounter four default help topics. Click on 'Add new help topic' to create four additional topics. Name the first one 'Business Critical Outage.' Within the 'New ticket options' section, set the SLA plan to Sev-A for the 'Business Critical Outage' topic, then save the changes. Take a moment to review the configurations of the existing topics to better understand their setup. Proceed to create three more help topics: the second, named 'Personal Computer Issues,' with an SLA of Sev-B; the third, 'Password Resets,' with an SLA of Sev-C; and the fourth, 'Equipment Reset,' with an SLA of Sev-B.


Note that most organizations have methods to identify the severity of help topics, though it can also be self-explanatory. Differentiating between issues like a Business Critical outage, such as a website being down, and an employee needing a password reset is crucial due to the disparity in priority. By establishing such categories and assigning corresponding SLAs, organizations can effectively prioritize and address issues, ensuring timely resolutions and minimal disruption to operations.


This project concludes with a comprehensive guide for configuring osTicket post-installation. It covers various aspects such as roles, departments, teams, agents, users, SLAs (Service Level Agreements), and help topics. Ensure to verify instructions against the latest osTicket documentation for accuracy, and exercise caution regarding the use of personal information in lab environments.

This project will have a continuation that goes over the creation and resolution of tickets.
