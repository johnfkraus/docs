https://unix.stackexchange.com/questions/104821/how-to-terminate-a-background-process

### ps

Use the `ps` command to find the process ID for this process and then use the PID to kill the process.

```bash
$ ps -eaf | grep [w]get 
saml      1713  1709  0 Dec10 pts/0    00:00:00 wget 
...
$ kill 1713
```

### pgrep

Find the process ID using `pgrep`.

```bash
$ pgrep wget
1234

$ kill 1234
```

### pkill

If you're sure it's the only wget you've run you can use the command `pkill` to kill the job by name.

```bash
$ pkill wget
```

### jobs

If you're in the same shell from where you ran the job that's now backgrounded you can check if the job is still running using the jobs command, and kill the job using its job number.

```bash
$ sleep 100 &
[1] 4542
```

Find the job number.

```bash
$ jobs
[1]+  Running                 sleep 100 &

$ kill %1
[1]+  Terminated              sleep 100
```

### fg

Bring a backgrounded job back to the foreground using the `fg` command.

```bash
$ sleep 100 &
[1] 4650

# Get the job's number.

$ jobs
[1]+  Running                 sleep 100 &

# Bring job #1 back to the foreground, and then use Ctrl+C.

$ fg 1
sleep 100
^C
```
