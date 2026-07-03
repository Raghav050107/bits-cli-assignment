# Question 1 - Commands, Outputs, and Observations

## Command 1

```bash
whoami
```

Output:

```text
root
```

Observation: This command shows the current logged-in user. The output shows that I was logged in as root in the Linux environment.

## Command 2

```bash
id
```

Output:

```text
uid=0(root) gid=0(root) groups=0(root)
```

Observation: This command displays the user ID, group ID, and group membership. The output confirms that the current user belongs to the root group.

## Command 3

```bash
groups
```

Output:

```text
root
```

Observation: This command lists the groups of the current user. The output shows root as the active group.

## Command 4

```bash
echo "$SHELL"
```

Output:

```text
/bin/bash
```

Observation: This command prints the current shell. The output shows that the shell used was /bin/bash.

## Command 5

```bash
pwd
```

Output:

```text
/work
```

Observation: This command prints the present working directory. The output shows that the commands were executed from /work.

## Command 6

```bash
ls -la
```

Output:

```text
total 36
drwxr-xr-x 8  501 root 4096 Jun 22 21:31 .
drwxr-xr-x 1 root root 4096 Jun 22 21:26 ..
drwxr-xr-x 7  501 root 4096 Jun 22 21:23 .git
drwxr-xr-x 3  501 root 4096 Jun 22 21:25 Question1
drwxr-xr-x 3  501 root 4096 Jun 22 21:26 Question2
drwxr-xr-x 4  501 root 4096 Jun 22 21:26 Question3
drwxr-xr-x 3  501 root 4096 Jun 22 21:26 Question4
drwxr-xr-x 3  501 root 4096 Jun 22 21:26 Question5
-rw-r--r-- 1  501 root 1517 Jun 22 21:23 README.md
```

Observation: This command lists all files and directories with detailed information. The output shows the question folders and project files in the workspace.

## Command 7

```bash
ping -c 4 google.com
```

Output:

```text
PING google.com (142.251.220.110) 56(84) bytes of data.
64 bytes from 142.251.220.110: icmp_seq=1 ttl=63 time=0.072 ms
64 bytes from 142.251.220.110: icmp_seq=2 ttl=63 time=0.442 ms
64 bytes from 142.251.220.110: icmp_seq=3 ttl=63 time=0.657 ms
64 bytes from 142.251.220.110: icmp_seq=4 ttl=63 time=0.569 ms

--- google.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3061ms
rtt min/avg/max/mdev = 0.072/0.435/0.657/0.223 ms
```

Observation: This command checks network connectivity. The output shows 4 packets transmitted and 4 received, so the network connection was working.
