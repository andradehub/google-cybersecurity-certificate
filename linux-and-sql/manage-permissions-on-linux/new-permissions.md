# File Permissions in Linux

## Project Description
As a security professional, part of my responsibilities  
include managing file system permissions to ensure  
that only authorized users can access sensitive  
research files. In this project, I examined existing  
permissions on the /home/researcher2/projects   
directory, identified unauthorized access, and used  
Linux commands to modify permissions to match the  
organization's authorization policies.  

---

## Check File and Directory Details  

The following command was used to check the current  
permissions of files and subdirectories in the  
projects directory, including hidden files:  
```bash  
ls -la /home/researcher2/projects  
```  

Output:
```  
drwx--x--- researcher2 research_team drafts  
-rw-rw-rw- researcher2 research_team project_k.txt  
-rw-r----- researcher2 research_team project_m.txt  
-rw-rw-r-- researcher2 research_team project_r.txt  
-rw-rw-r-- researcher2 research_team project_t.txt  
-rw--w---- researcher2 research_team .project_x.txt  
```

---

## Describe the Permissions String  

Using project_k.txt as an example:  
Permission string: -rw-rw-rw-  

| Position | Character | Meaning |  
|---|---|---|  
| 1 | - | Regular file |  
| 2-4 | rw- | User: read and write |  
| 5-7 | rw- | Group: read and write |  
| 8-10 | rw- | Other: read and write |  
  
This means the file is a regular file where the  
user (owner), group, and others all have read and  
write permissions. Execute permission is not granted  
to any of them.  

---

## Change File Permissions

The organization does not allow others to have write  
access to any files. The file project_k.txt was  
found to have write permissions for others, which  
violates this policy.  

The following command was used to remove write  
permissions from others:  
```bash  
chmod o-w project_k.txt
```

After the change, the permission string became:  
-rw-rw-r--  

This ensures that others can only read the file,  
while the user and group retain their read and  
write permissions.  

---

## Change File Permissions on a Hidden File  

The file .project_x.txt is a hidden archived file.  
The organization requires that no one has write  
access to this file, but both the user and group  
should be able to read it.  

The current permissions were:  
-rw--w----

The following command was used to set the correct  
permissions:  
```bash  
chmod u-w,g-w,g+r .project_x.txt
```

After the change, the permission string became:  
-r--r-----

This ensures that both the user and group can read  
the file, but no one has write access, which matches  
the organization's requirements for archived files.  

---

## Change Directory Permissions  

The drafts directory belongs to researcher2, and  
only researcher2 should be allowed to access it  
and its contents. The group currently has execute  
permission on the directory, which allows them  
to access its contents.  

The following command was used to remove the group's  
execute permission:  
```bash  
chmod g-x drafts
```

After the change, the permission string became:  
drwx------  

This ensures that only researcher2 can access the  
drafts directory and its contents, removing any  
unauthorized group access.  

---

## Summary  
In this project, I examined and modified file  
permissions in the /home/researcher2/projects    
directory to align with the organization's  
authorization policies. Using the ls -la command,  
I identified files and directories with incorrect  
permissions. I then used chmod to remove  
unauthorized write access from others on  
project_k.txt, restrict write access on the hidden  
file .project_x.txt, and limit access to the drafts  
directory to researcher2 only. These changes ensure  
that sensitive research files are protected from  
unauthorized access.  
