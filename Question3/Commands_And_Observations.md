# Question 3 - Commands, Outputs, and Observations

## Command 1

```bash
echo "This file is used to test hard links and symbolic links." > original.txt
```

Output:

```text
No output
```

Observation: This command created the original file with sample text. It was used to test hard links and symbolic links.

## Command 2

```bash
ln original.txt hardlink.txt
```

Output:

```text
No output
```

Observation: This command created a hard link. The hard link shared the same inode as the original file.

## Command 3

```bash
ln -s original.txt symlink.txt
```

Output:

```text
No output
```

Observation: This command created a symbolic link. The symbolic link pointed to the original filename.

## Command 4

```bash
ls -li
```

Output:

```text
total 8
3966740 -rw-r--r-- 2 root root 57 Jun 22 21:32 hardlink.txt
3966740 -rw-r--r-- 2 root root 57 Jun 22 21:32 original.txt
3966741 lrwxrwxrwx 1 root root 12 Jun 22 21:32 symlink.txt -> original.txt
```

Observation: This command displayed inode numbers. The original file and hard link had the same inode, while the symbolic link had a different inode.

## Command 5

```bash
stat original.txt
```

Output:

```text
File: original.txt
  Size: 57        	Blocks: 8          IO Block: 4096   regular file
Device: 0,42	Inode: 3966740     Links: 2
Access: (0644/-rw-r--r--)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2026-06-22 21:32:01.122929822 +0000
Modify: 2026-06-22 21:32:01.122929822 +0000
Change: 2026-06-22 21:32:01.123929818 +0000
 Birth: 2026-06-22 21:32:01.122929822 +0000
```

Observation: This command displayed metadata for the original file. It showed inode number, permissions, size, owner, and timestamps.

## Command 6

```bash
stat hardlink.txt
```

Output:

```text
File: hardlink.txt
  Size: 57        	Blocks: 8          IO Block: 4096   regular file
Device: 0,42	Inode: 3966740     Links: 2
Access: (0644/-rw-r--r--)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2026-06-22 21:32:01.122929822 +0000
Modify: 2026-06-22 21:32:01.122929822 +0000
Change: 2026-06-22 21:32:01.123929818 +0000
 Birth: 2026-06-22 21:32:01.122929822 +0000
```

Observation: This command displayed metadata for the hard link. It showed the same inode as the original file and a link count of 2.

## Command 7

```bash
stat symlink.txt
```

Output:

```text
File: symlink.txt -> original.txt
  Size: 12        	Blocks: 0          IO Block: 4096   symbolic link
Device: 0,42	Inode: 3966741     Links: 1
Access: (0777/lrwxrwxrwx)  Uid: (    0/    root)   Gid: (    0/    root)
Access: 2026-06-22 21:32:01.125929810 +0000
Modify: 2026-06-22 21:32:01.123929818 +0000
Change: 2026-06-22 21:32:01.123929818 +0000
 Birth: 2026-06-22 21:32:01.123929818 +0000
```

Observation: This command displayed metadata for the symbolic link. It showed that the symbolic link had a separate inode and pointed to original.txt.

## Command 8

```bash
cat original.txt
```

Output:

```text
This file is used to test hard links and symbolic links.
```

Observation: This command displayed the contents of the original file. It confirmed that the file contained the sample text.

## Command 9

```bash
rm original.txt
```

Output:

```text
No output
```

Observation: This command removed the original filename. The file data still remained available through the hard link.

## Command 10

```bash
ls -li
```

Output:

```text
total 4
3966740 -rw-r--r-- 1 root root 57 Jun 22 21:32 hardlink.txt
3966741 lrwxrwxrwx 1 root root 12 Jun 22 21:32 symlink.txt -> original.txt
```

Observation: This command showed the files after deleting the original file. The hard link remained, but the symbolic link pointed to a missing target.

## Command 11

```bash
cat hardlink.txt
```

Output:

```text
This file is used to test hard links and symbolic links.
```

Observation: This command displayed the hard link content after deleting the original file. It confirmed that hard links continue to work as long as one link remains.

## Command 12

```bash
cat symlink.txt
```

Output:

```text
cat: symlink.txt: No such file or directory
```

Observation: This command failed after deleting the original file. It showed that symbolic links depend on the target path.

Final note: The submitted `symlink.txt` file is intentionally broken because the experiment required deleting `original.txt` and observing the result. The submitted `hardlink.txt` remains readable, which proves the difference between hard links and symbolic links.
