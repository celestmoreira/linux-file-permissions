# **Project Description**

In this lab activity, I was required to audit and correct file and directory permissions in the `projects` directory. Some permissions were misconfigured, allowing more access than intended. To strengthen security, I reviewed the ecisting settings and updated them as needed. Below is an overview of the steps I performed:

# **Check file and Directory Details** 

The following code demonstrates how I used Linux commands to determine the existing permissions set for a specific directory in the file system.

![Task 1 Terminal Output](screenshots\screenshot-task1.png)

When I first checked the contents of the `projects` directory, I started with the `ls -l` command. The first line in the screenshot shows the exact command I ran, and everything below it is the output. The `ls -l` command gives a detailed listing of all _visible_ files and directories, including their permissions, the file owner, thr group owner, file sizes, and timestamps. 

# **Describe the Permission Strings**

Right after running `ls -l`, I took a closer look at the permission strings. Each item begins with a 10 character string (for example: `-rw-rw-r--` or `drwx--x---`). These characters represent permissions for three categories of users: 

- **User** - the owner of the file (in this lab, the user is `researcher2`)
- **Group** - the group the file belongs to (`research_team`)
- **Other** - anyone else on the system who is not the user or in the group

Understanding this breakdown helped me interpret who currently has read, write, or execute access for each file. It's important to analyze this before making any permission changes later in the lab.

After reviewing the visible files, I needed to check whether any hidden files were present. To do that, I used `ls -la`. The `-a` option reveals hidden files, these are files that begin with a dot (`.`) and don't appear with a regular `ls` command. Using `ls -la` showed me a hidden file named `.project_x.txt` that wasn't visible earlier. 

From the full output of `ls -la`, I identified: 

- One directory: `drafts/`
- One hidden file: `.project_x.txt`
- Five regular project files 

# **Change File Permissions
 