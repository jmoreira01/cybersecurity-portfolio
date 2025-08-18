# Linux File Permissions Management

## Project Description
The research team at my organization needed to update file and directory permissions within the `projects` directory, as the existing settings did not reflect the appropriate authorization levels. 
Adjusting these permissions was critical to maintaining system security. I performed the following tasks:

## Task 1 : Check File and Directory Details

The lab starts with `/home/researcher2` as the current working directory

```bash
researcher2@04ff106a5cf4:~$ cd projects
researcher2@04ff106a5cf4:~/projects$
```

### List the contents and permissions of the projects directory.
I used `ls -l` command to determine the existing permissions for the `projects` directory. The following command and its output illustrate this process:

```bash
researcher2@04ff106a5cf4:~/projects$ ls -l 
total 20
drwx--x--- 2 researcher2 research_team 4096 Aug 18 12:21 drafts
-rw-rw-rw- 1 researcher2 research_team   46 Aug 18 12:21 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Aug 18 12:21 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_t.txt
```

### Check whether any hidden files exist in the projects directory.

```bash
researcher2@04ff106a5cf4:~/projects$ ls -la
total 32
drwxr-xr-x 3 researcher2 research_team 4096 Aug 18 12:21 .
drwxr-xr-x 3 researcher2 research_team 4096 Aug 18 12:41 ..
-rw--w---- 1 researcher2 research_team   46 Aug 18 12:21 .project_x.txt <=====
drwx--x--- 2 researcher2 research_team 4096 Aug 18 12:21 drafts
-rw-rw-rw- 1 researcher2 research_team   46 Aug 18 12:21 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Aug 18 12:21 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_t.txt
```


## Task 2 : Change File Permissions

###Check whether any files in the projects directory have write permissions for the owner type of `other`:

```bash
-rw-rw-rw- 1 researcher2 research_team   46 Aug 18 12:21 project_k.txt
```

changed to:

```bash 
-rw-rw-r-- 1 researcher2 research_team  46 Aug 18 12:21 project_k.txt
```

### The file project_m.txt is a restricted file and should not be readable or writable by the group or other; only the user should have these permissions on this file. 
List the contents and permissions of the current directory and check if the group has read or write permissions.

```bash 
researcher2@04ff106a5cf4:~/projects$ ls -l
total 20
drwx--x--- 2 researcher2 research_team 4096 Aug 18 12:21 drafts
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_k.txt
-rw-r----- 1 researcher2 research_team   46 Aug 18 12:21 project_m.txt <===== (Group has Read Only permission)
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_t.txt
```

### Use the chmod command to change permissions of the project_m.txt file so that the group doesn’t have read or write permissions.

```bash 
researcher2@04ff106a5cf4:~/projects$ chmod g-r project_m.txt
```

changed to: 

```bash 
-rw------- 1 researcher2 research_team   46 Aug 18 12:21 project_m.txt
```

### Change the permissions of the file identified in the previous step so that the owner type of other doesn’t have write permissions.

```bash 
researcher2@04ff106a5cf4:~/projects$ chmod o-w project_k.txt
```

## Task 3 : Change file permissions on a hidden file
The file .project_x.txt is a hidden file that has been archived and should not be written to by anyone. (The user and group should still be able to read this file.)

### Which owner type has the incorrect write permissions?

```bash 
researcher2@0e5013bff7d9:~/projects$ ls -la
(...)
-rw--w---- 1 researcher2 research_team   46 Aug 18 13:25 .project_x.txt <===== (User and Group with Write permission)
(...)
```

### Change the permissions of the file .project_x.txt so that both the user and the group can read, but not write to, the file.


```bash 
researcher2@0e5013bff7d9:~/projects$ chmod u-w,g-w,g+r .project_x.txt
researcher2@0e5013bff7d9:~/projects$ ls -la
(...)
-r--r----- 1 researcher2 research_team   46 Aug 18 13:25 .project_x.txt
(...)
```



## Task 4 : Change directory permissions
Only the researcher2 user should be allowed to access the drafts directory and its contents. (This means that only researcher2 should have execute privileges.)

### Does the group have permissions set to access the drafts directory and its contents?

```bash 
researcher2@04ff106a5cf4:~/projects$ ls -l
total 20
drwx--x--- 2 researcher2 research_team 4096 Aug 18 12:21 drafts         <===== (User and Group has Execute Permission)
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_k.txt
-rw------- 1 researcher2 research_team   46 Aug 18 12:21 project_m.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_r.txt
-rw-rw-r-- 1 researcher2 research_team   46 Aug 18 12:21 project_t.txt
```

### Remove the execute permission for the group from the drafts directory.

```bash 
researcher2@04ff106a5cf4:~/projects$ chmod g-x drafts
```

changed to: 

```bash 
drwx------ 2 researcher2 research_team 4096 Aug 18 12:21 drafts
```


### Summary
I successfully updated permissions to align with the organization’s authorization requirements. The process began with `ls` and `ls -la` to assess existing permissions, followed by targeted `chmod` commands to modify file and directory access rights, enhancing system security.

## Reflection
This activity strengthened my skills in Linux file permission management, a fundamental aspect of cybersecurity. Understanding permission strings and using `chmod` effectively taught me how to secure sensitive data, a key practice for protecting organizational systems. This experience builds my capability to maintain secure environments in future roles.

---
[Back to Cybersecurity Portfolio](README.md)
