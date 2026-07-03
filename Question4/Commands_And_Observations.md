# Question 4 - Commands, Outputs, and Observations

## Command 1

```bash
lsof -p $$
```

Output:

```text
COMMAND PID USER  FD   TYPE DEVICE SIZE/OFF    NODE NAME
bash    458 root cwd    DIR   0,42     4096 3966665 /work
bash    458 root rtd    DIR   0,42     4096 3966661 /
bash    458 root txt    REG   0,42  1412096 3952946 /usr/bin/bash
bash    458 root mem    REG   0,42   367708 3955178 /usr/lib/locale/C.utf8/LC_CTYPE
bash    458 root mem    REG   0,42  1716616 3953620 /usr/lib/aarch64-linux-gnu/libc.so.6
bash    458 root mem    REG   0,42   265504 3954341 /usr/lib/aarch64-linux-gnu/libtinfo.so.6.5
bash    458 root mem    REG   0,42       50 3955185 /usr/lib/locale/C.utf8/LC_NUMERIC
bash    458 root mem    REG   0,42     3360 3955188 /usr/lib/locale/C.utf8/LC_TIME
bash    458 root mem    REG   0,42     1406 3955177 /usr/lib/locale/C.utf8/LC_COLLATE
bash    458 root mem    REG   0,42   201344 3953600 /usr/lib/aarch64-linux-gnu/ld-linux-aarch64.so.1
bash    458 root mem    REG   0,42      270 3955183 /usr/lib/locale/C.utf8/LC_MONETARY
bash    458 root mem    REG   0,42       48 3955182 /usr/lib/locale/C.utf8/LC_MESSAGES/SYS_LC_MESSAGES
bash    458 root mem    REG   0,42       34 3955186 /usr/lib/locale/C.utf8/LC_PAPER
bash    458 root mem    REG   0,42       62 3955184 /usr/lib/locale/C.utf8/LC_NAME
bash    458 root mem    REG   0,42      127 3955176 /usr/lib/locale/C.utf8/LC_ADDRESS
bash    458 root mem    REG   0,42       47 3955187 /usr/lib/locale/C.utf8/LC_TELEPHONE
bash    458 root mem    REG   0,42    27028 3953562 /usr/lib/aarch64-linux-gnu/gconv/gconv-modules.cache
bash    458 root mem    REG   0,42       23 3955180 /usr/lib/locale/C.utf8/LC_MEASUREMENT
bash    458 root mem    REG   0,42      258 3955179 /usr/lib/locale/C.utf8/LC_IDENTIFICATION
bash    458 root   0r   CHR    1,3      0t0       5 /dev/null
bash    458 root   1w   REG   0,42       68 3966753 /work/Question4/coursera_command_output.txt
bash    458 root   2w   REG   0,42       68 3966753 /work/Question4/coursera_command_output.txt
bash    458 root  10w  FIFO   0,14      0t0   13215 pipe
bash    458 root  11w  FIFO   0,14      0t0   13216 pipe
```

Observation: This command listed open files for the current shell process. The output showed files, libraries, pipes, and the command output file opened by the process.

## Command 2

```bash
ls -l /proc/$$/fd
```

Output:

```text
total 0
lr-x------ 1 root root 64 Jun 22 21:32 0 -> /dev/null
l-wx------ 1 root root 64 Jun 22 21:32 1 -> /work/Question4/coursera_command_output.txt
l-wx------ 1 root root 64 Jun 22 21:32 10 -> pipe:[13215]
l-wx------ 1 root root 64 Jun 22 21:32 11 -> pipe:[13216]
l-wx------ 1 root root 64 Jun 22 21:32 2 -> /work/Question4/coursera_command_output.txt
```

Observation: This command listed file descriptors for the shell process. File descriptors 0, 1, and 2 represented standard input, standard output, and standard error.

## Command 3

```bash
echo "Application log entry created successfully" > Question4/output.txt
```

Output:

```text
No output
```

Observation: This command redirected standard output into output.txt. No output appeared on the terminal because it was written to the file.

## Command 4

```bash
cat Question4/output.txt
```

Output:

```text
Application log entry created successfully
```

Observation: This command displayed output.txt. It confirmed that normal output redirection worked correctly.

## Command 5

```bash
ls missing_file.txt 2> Question4/error.txt
```

Output:

```text
No output
```

Observation: This command redirected an error message into error.txt. The terminal did not show the error because stderr was redirected.

## Command 6

```bash
cat Question4/error.txt
```

Output:

```text
ls: cannot access 'missing_file.txt': No such file or directory
```

Observation: This command displayed the saved error message. It confirmed that error redirection using 2> worked correctly.

## Command 7

```bash
ulimit -a
```

Output:

```text
real-time non-blocking time  (microseconds, -R) unlimited
core file size              (blocks, -c) unlimited
data seg size               (kbytes, -d) unlimited
scheduling priority                 (-e) 0
file size                   (blocks, -f) unlimited
pending signals                     (-i) 7660
max locked memory           (kbytes, -l) 8192
max memory size             (kbytes, -m) unlimited
open files                          (-n) 1024
pipe size                (512 bytes, -p) 8
POSIX message queues         (bytes, -q) 819200
real-time priority                  (-r) 0
stack size                  (kbytes, -s) 8192
cpu time                   (seconds, -t) unlimited
max user processes                  (-u) unlimited
virtual memory              (kbytes, -v) unlimited
file locks                          (-x) unlimited
```

Observation: This command displayed shell resource limits. The output included limits such as open files, stack size, memory, and process limits.
