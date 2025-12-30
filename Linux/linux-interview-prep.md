# Linux Interview Preparation Guide 🐧

This document is designed for **DevOps and Linux interview preparation**.  
Each answer is written in a **descriptive, interview-friendly manner**, explaining not just *what* to do, but *why*.

---

## 1. How do you print the current date and time in a shell script?

In Linux, the `date` command is used to display the current system date and time.

```bash
date
```

You can also format the output, which is very common in shell scripts and log files:

```bash
date "+%Y-%m-%d %H:%M:%S"
```

**Interview Insight:**  
The `date` command is frequently used in cron jobs, monitoring scripts, and application logs to timestamp events.

---

## 2. How do you view the contents of a ZIP file without extracting it?

To list the contents of a ZIP file without extracting it, use:

```bash
unzip -l file.zip
```

This helps verify files before extraction and is useful in automation scripts.

---

## 3. What does Linux permission 755 mean?

Linux permissions are represented by three digits:
- **Owner**
- **Group**
- **Others**

Permission `755` means:
- Owner → read, write, execute (7)
- Group → read, execute (5)
- Others → read, execute (5)

This permission is commonly used for executable scripts and directories.

---

## 4. Which command is used to change file or directory permissions?

The `chmod` command is used to modify permissions.

```bash
chmod 755 script.sh
```

This ensures the owner can modify the file, while others can only read and execute it.

---

## 5. Which command is used to create a new Linux user?

To create a user:

```bash
useradd username
passwd username
```

On some distributions, `adduser` provides an interactive way:

```bash
adduser username
```

---

## 6. How do you check all active network ports on a Linux system?

Modern Linux systems use the `ss` command:

```bash
ss -tuln
```

This shows TCP/UDP ports that are listening on the system.

---

## 7. Linux is a CLI-based OS — what type of shell does it use?

Most Linux systems use **Bash (Bourne Again Shell)** by default.

Other shells include:
- sh
- zsh
- fish
- csh

---

## 8. Where should environment variables be stored?

- User-specific variables → `~/.bashrc`, `~/.bash_profile`
- System-wide variables → `/etc/environment`, `/etc/profile`

System-wide variables apply to all users and services.

---

## 9. What command is used to list all listening ports in Linux?

```bash
ss -tulnp
```

This shows listening ports along with the owning process.

---

## 10. How do you check which process is using the most CPU or memory?

The `top` command provides a real-time view:

```bash
top
```

A more user-friendly alternative is:

```bash
htop
```

---

## 11. What command is used to generate an SSH key?

```bash
ssh-keygen
```

Common secure option:

```bash
ssh-keygen -t rsa -b 4096
```

SSH keys are widely used for passwordless authentication.

---

## 12. Name some popular Linux distributions.

- Ubuntu
- CentOS
- RHEL
- Debian
- Fedora
- Amazon Linux
- SUSE

---

## 13. How do you print the last 15 lines of a file in Linux?

```bash
tail -n 15 filename
```

Very useful for checking logs.

---

## 14. How do you enable passwordless authentication between two servers?

1. Generate SSH key:
```bash
ssh-keygen
```

2. Copy the public key:
```bash
ssh-copy-id user@server-ip
```

This is essential for automation and CI/CD pipelines.

---

## 15. A Linux server is running slow. How do you diagnose it?

Step-by-step approach:
- Check CPU and memory usage using `top`
- Check disk usage using `df -h`
- Check disk I/O using `iostat`
- Check load average using `uptime`

**Interview Tip:**  
Always explain your troubleshooting sequence logically.

---

## 16. Disk usage hits 100%. How do you resolve it?

- Identify large directories:
```bash
du -sh /*
```
- Clear old logs
- Remove unused files
- Extend disk if required

---

## 17. SSH connection frequently drops. How do you debug?

- Check network stability
- Review SSH configuration
- Enable keepalive settings
- Check firewall and MTU issues

---

## 18. A process is stuck in zombie state. What do you do?

Zombie processes cannot be killed directly.
You must terminate the **parent process** that spawned it.

---

## 19. System boots into emergency mode. How do you troubleshoot?

- Check `/etc/fstab`
- Verify UUIDs
- Run filesystem checks using `fsck`

---

## 20. High CPU usage from `kworker`. What do you check?

- Hardware interrupts
- Driver issues
- Disk or network I/O
- Kernel logs using `dmesg`

---

## 21. How do you detect network bottlenecks?

```bash
iftop
nload
sar -n DEV
```

---

## 22. Service won’t start. What steps do you follow?

- Check service status using `systemctl status`
- Review logs with `journalctl`
- Validate configuration files

---

## 23. Cron job not running. How do you troubleshoot?

- Check cron service
- Verify crontab entries
- Use absolute paths
- Check cron logs

---

## 24. Server is out of memory. What do you do?

- Identify memory-heavy processes
- Check swap usage
- Restart or optimize application
- Increase RAM if required

---

## 25. How do you secure a Linux server?

- Disable root login
- Use SSH keys
- Configure firewall
- Apply patches
- Enable SELinux/AppArmor
- Follow least privilege

---

## 26. How do you inspect file descriptor leaks?

```bash
lsof -p <pid>
```

---

## 27. How do you analyze core dumps?

- Enable core dumps using `ulimit`
- Analyze with `gdb`

---

## 28. How do you troubleshoot DNS resolution failures?

- Check `/etc/resolv.conf`
- Test with `nslookup` and `dig`
- Verify network connectivity

---

## 29. Explain debugging SELinux issues.

- Check enforcement mode
- Review AVC denials
- Temporarily set permissive mode for debugging

---

## 30. In Linux, how do you attach and detach a filesystem?

Attach:
```bash
mount /dev/sdb1 /mnt
```

Detach:
```bash
umount /mnt
```

---

📌 **Tip:** Practice explaining answers clearly — interviews focus on *reasoning*, not memorization.
