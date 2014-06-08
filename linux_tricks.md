
Mount remote directory using sshfs

```
sshfs name@server:/path/to/directory /path/to/mountpoint
```

Compare remote file with a local file

```
ssh user@host cat /path/to/remotefile | diff /path/to/localfile
````

Make a partition in ram which is useful if you need a temporary working space as read/write access is fast.

```
mount -t tmpfs tmpfs /mnt -o size=1024m
```

Display the top ten running processes - sorted by memory usage

```
ps aux | sort -nk +4 | tail
```

Graph # of connections for each hosts

```
netstat -an | grep ESTABLISHED | awk '{print $5}' | awk -F: '{print $1}' | sort | uniq -c | awk '{ printf("%s\t%s\t",$2,$1) ; for (i = 0; i < $1; i++) {printf("*")}; print "" }'
```
