# Managing Authorization

## Objective
In this project, I use Linux commands to manage authorization.

Authorization involves granting access to specific resources within a system, which is crucial for security. Without proper authorization, any user could potentially access and alter files that belong to other users or the system itself, posing a significant security threat. Linux manages access to files and directories through permissions, determining who can access and modify them. During this lab, I delve into these permissions and adjust the ownership of a file and a directory to restrict access appropriately.
As a security analyst, it's vital to set correct access permissions to safeguard sensitive data and ensure the system's overall security.
This Qwiklabs project provisions resources and is hosted on Google Cloud. 

### Skills Learned

- managing authorization using Linux Bash shell commands
- Adjusting directory permissions to control access for different user types, ensuring security and restricting unauthorized access.
- the importance setting appropriate permissions to protect sensitive information and maintain system security.

### Tools and Environments Used

- Linux / Bash shell
'

## Scenario
In this scenario, I needed to examine and manage the permissions for the files located in the `/home/researcher2/projects` directory, specifically for the `researcher2` user.

The `researcher2` user is part of the `research_team` group.

First, I checked the permissions for all files in the directory, including hidden files, to ensure they matched the required authorization levels. If any files had incorrect permissions, I adjusted them accordingly. Finally, I reviewed the permissions of the `/home/researcher2/projects/drafts` directory and modified them to prevent any unauthorized access.

**This has-on project is broken down to 4 tasks in the order shown below:**
'

 ### Task 1: Check file and directory details

In this task, I explored the permissions of the projects directory and its files starting from the current working directory at `/home/researcher2`.

First, I navigated to the projects directory.

Then, I listed the contents of the projects directory along with their respective permissions.
Here are the permissions for the files in the projects directory:

![Z1](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/d0991645-5dd6-48c8-9cee-fb4a639b2807)

Listing the file permissions shows that `research_team` owns the files in the projects directory.

Querying the shell command `ls -la` also reveals that we have a hidden files `.project_x.txt` as shown on the termal below:

![Z2](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/c0df1d44-9ee3-4c20-b701-f1efbdfd0add)
'

 ### Task 2: Change file permissions
In this task, I needed to identify any files with incorrect permissions in the projects directory and adjust them as necessary. This action aimed to eliminate unauthorized access and enhance system security.

I checked whether any files in the projects directory granted write permissions to users other than the owner.
From the previous terminal window we notice that `project_k.txt` file has write permissions for other users. I then modified the permissions of the file identified earlier to ensure that users other than the owner do not have write permissions. To adjust the permissions of the file so that the owner type of `other` no longer had write access, I used the command `chmod o-w project_k.txt` as shown on the terminal window below:

![Z3](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/14ad6ccc-44c1-4e03-89f9-3c9cf0d374f8)

I used the `chmod` command to adjust the permissions of the `project_m.txt` file. Originally, the group had read-only permissions on the file. However, since `project_m.txt` is a restricted file, it should not be readable or writable by the group or any other users except the owner.

Therefore, I modified the permissions of `project_m.txt` to remove both read and write permissions for the group.

![Z4](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/50430ee2-bdd2-47ac-87ac-21f0547ef541)
'

### Task 3. Change file permissions on a hidden file
In this task, I needed to verify if the hidden file `.project_x.txt` had incorrect permissions and then adjust them as necessary. It was crucial that this file, which had been archived, should not permit any write operations by any user. However, both the user and the group should retain the ability to read the file.

I checked and modified the permissions of `.project_x.txt` to ensure that no users could write to it, while maintaining read permissions for both the user and the group.
The output is shown on the terminal window below:

![Z5](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/772c9bed-8136-42ad-8a45-48163332124d)
'

### Task 4. Change directory permissions
In this task, I needed to adjust the permissions of a directory. Initially, I checked the group permissions of the `/home/researcher2/projects/drafts` directory and then made modifications as necessary. I ensured that while managing permissions within the `projects` directory, specifically its subdirectory `drafts`, only the researcher2 user retained access. This meant granting execute privileges solely to researcher2 for the `drafts` directory and its contents.

I removed the execute permission for the group from the drafts directory because the `projects` group had access to it. I used the shell command `chmod g-x drafts` to accomplish this task.

![Z6](https://github.com/godfreyndlovu/Managing-Authorization/assets/102636518/265a3ec5-a31b-4e99-a4a1-b9eacd551d2b)
'

## Conclusion

This project highlights my ability to actively manage file and directory permissions in Linux using Bash shell commands. By effectively controlling permissions, mitigating security risks, and safeguarding the integrity of organizational systems, I demonstrate comprehensive skills in ensuring system security and operational reliability.
