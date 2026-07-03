# Question 2 - Commands, Outputs, and Observations

## Command 1

```bash
mkdir -p project_workspace
```

Output:

```text
No output
```

Observation: This command created the project workspace directory. There was no error, so the directory was created successfully.

## Command 2

```bash
touch project_workspace/plan.txt project_workspace/notes.txt
```

Output:

```text
No output
```

Observation: This command created two project documentation files inside the workspace.

## Command 3

```bash
vi project_workspace/plan.txt
```

Output:

```text
No terminal output
```

Observation: I opened `plan.txt` in the vi editor and added the project plan details.

## Command 4

```bash
vi project_workspace/notes.txt
```

Output:

```text
No terminal output
```

Observation: I opened `notes.txt` in the vi editor and added notes about the workspace permission setup.

## Command 5

```bash
cat project_workspace/plan.txt
```

Output:

```text
Project Plan

1. Create a secure project workspace.
2. Create project documentation files.
3. Check the default file and directory permissions.
4. Change the workspace directory permission using chmod 750.
5. Verify ownership details using id and directory listing commands.
6. Check the umask value used for default permissions.
7. Confirm that the workspace protects project files from unauthorized users.
```

Observation: This command displayed the content of `plan.txt`. It confirmed that the project plan file was created and documented.

## Command 6

```bash
cat project_workspace/notes.txt
```

Output:

```text
Project Notes

The project_workspace directory was created to store project files securely.
The files plan.txt and notes.txt were created as sample project documentation files.

The workspace permission was changed to 750:
- Owner has read, write, and execute permission.
- Group has read and execute permission.
- Other users have no permission.

This permission setting protects project data by preventing unauthorized users from accessing the directory.
```

Observation: This command displayed the content of `notes.txt`. It confirmed that notes about the secure workspace setup were recorded.

## Command 7

```bash
ls -l project_workspace
```

Output:

```text
total 16
-rw-r--r-- 1 root root 457 Jun 22 21:32 notes.txt
-rw-r--r-- 1 root root 408 Jun 22 21:32 plan.txt
```

Observation: This command displayed the files inside the workspace. The output shows `plan.txt` and `notes.txt` with their file sizes and default file permissions.

## Command 8

```bash
ls -ld project_workspace
```

Output:

```text
drwxr-xr-x 2 root root 4096 Jun 22 21:32 project_workspace
```

Observation: This command displayed the directory permissions before modification. The original permissions allowed access for owner, group, and others.

## Command 9

```bash
chmod 750 project_workspace
```

Output:

```text
No output
```

Observation: This command changed the workspace permission to 750. This gives full access to the owner, limited access to the group, and no access to others.

## Command 10

```bash
ls -ld project_workspace
```

Output:

```text
drwxr-x--- 2 root root 4096 Jun 22 21:32 project_workspace
```

Observation: This command confirmed the changed permission. The output shows `drwxr-x---`, which means others cannot access the directory.

## Command 11

```bash
id
```

Output:

```text
uid=0(root) gid=0(root) groups=0(root)
```

Observation: This command displayed ownership identity information. The output shows the UID, GID, and group details of the user.

## Command 12

```bash
umask
```

Output:

```text
0022
```

Observation: This command displayed the default permission mask. The output `0022` explains why new files are not created with write permission for group and others.

## Command 13

```bash
find project_workspace -maxdepth 2 -ls
```

Output:

```text
3966710      4 drwxr-x---   2 root     root         4096 Jun 22 21:32 project_workspace
3966738      4 -rw-r--r--   1 root     root          457 Jun 22 21:32 project_workspace/notes.txt
3966737      4 -rw-r--r--   1 root     root          408 Jun 22 21:32 project_workspace/plan.txt
```

Observation: This command displayed the workspace structure with permissions, ownership, and file sizes. It confirmed the created directory and documentation files.
