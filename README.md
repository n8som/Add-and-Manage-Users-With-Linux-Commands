# Add-and-Manage-Users-With-Linux-Commands

<h2>Activity Overview</h2>

Previously, I focused on authorization, the concept of granting access to specific resources in a system. Another important concept in security is authentication. Authentication is the process of a user proving that they are who they say they are in the system.

When managing this, security analysts need to ensure

- not all users get access to the system,
- new users (those who are new to the organization or a group) are added to the system, and
- current users who change groups or leave the organization are deleted from the system.

In this lab activity, I’ll use the ```useradd```, ```usermod```, ```userdel```, and ```chown``` commands to manage user access in the Linux Bash shell.

Important: I must use ```sudo``` at the beginning of all the commands I use in this lab. Adding or removing users and groups are tasks that require root (super user) privileges, and I’ll need to use ```sudo``` with the commands that are used to perform these tasks.

<h2>Scenario</h2>

In this scenario, a new employee with the username ```researcher9``` joins an organization. I have to add them to the system and continue to manage their access during their time with the organization.

Here’s how I’ll do this task: First, I’ll add a new employee to the system and then to their primary group. Second, I’ll make this employee the owner of a file related to a particular project. Third, I’ll add the new employee to a supplementary group. Finally, I’ll delete the employee from the system.

<h2>Task 1. Add a new user</h2>

A new employee has joined the Research department. In this task, I must add them to the system. The username assigned to them is ```researcher9```.

1. Write a command to add a user called ```researcher9``` to the system.

Next, I need to add the new user to the ```research_team``` group.

2. Use the ```usermod``` command and ```-g``` option to add ```researcher9``` to the ```research_team``` group as their primary group.

![image](https://github.com/n8som/Add-and-Manage-Users-With-Linux-Commands/assets/110139109/0f8a3d3f-4a83-490c-a220-fa76b92fc09f)

<h2>Task 2. Assign file ownership</h2>

The new employee, ```researcher9```, will take responsibility for ```project_r```. In this task, I must make them the owner of the ```project_r.txt``` file.

The ```project_r.txt``` file is located in the ```/home/researcher2/projects``` directory, and owned by the ```researcher2``` user.

- Use the ```chown``` command to make ```researcher9``` the owner of ```/home/researcher2/projects/project_r.txt```.

![image](https://github.com/n8som/Add-and-Manage-Users-With-Linux-Commands/assets/110139109/3385b447-7ef9-4948-a707-096998b038fc)

<h2>Task 3. Add the user to a secondary group</h2>

A couple of months later, this employee's role at the organization has changed, and they are working in both the Research and the Sales departments.

In this task, I must add ```researcher9``` to a secondary group (```sales_team```). Their primary group is still ```research_team```.

- Use the ```usermod``` command with the ```-a``` and ```-G``` options to add ```researcher9``` to the ```sales_team``` group as a secondary group.

Note: Options for Linux commands are case-sensitive, so make sure I use a lowercase ```-a``` and an uppercase ```-G```.

![image](https://github.com/n8som/Add-and-Manage-Users-With-Linux-Commands/assets/110139109/4639654e-9842-4619-a881-732add227d9a)

<h2>Task 4. Delete a user</h2>

A year later, ```researcher9```, decided to leave the company. In this task, I must remove them from the system.

1. Run the command, ```sudo userdel researcher9``` to delete ```researcher9``` from the system:

This command will output the following message:

![image](https://github.com/n8som/Add-and-Manage-Users-With-Linux-Commands/assets/110139109/60eb457f-cb84-43c7-9242-a4838194f548)

This is expected.

Note: When I create a new user in Linux, a group with the same name as the user is automatically created and the user is the only member of that group. After removing users, it is good practice to clean up any such empty groups that may remain behind.

2. Run the following command, ```sudo groupdel researcher9``` to delete the ```researcher9``` group that is no longer required:

![image](https://github.com/n8som/Add-and-Manage-Users-With-Linux-Commands/assets/110139109/56d26148-4805-450d-84f1-2e5107caa438)

<h2>Conclusion</h2>

I now have practical experience in using basic Linux Bash shell commands to

- add a new user,
- add a user to a group,
- change user permissions on files, and
- delete a user.

This is an important milestone on my journey toward managing users in Linux!

