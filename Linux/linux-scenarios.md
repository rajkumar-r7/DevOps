# Linux Scenario-Based Interview Questions

## Server running slow
Check CPU, memory, disk, IO using top, df, iostat

## Disk usage 100%
Find large files, clear logs, extend disk

## SSH drops frequently
Check network, keepalive, firewall

## Zombie process
Kill parent process

## Emergency mode boot
Check fstab, fsck

## High CPU kworker
Check drivers, interrupts, dmesg

## Network bottleneck
iftop, sar

## Service not starting
systemctl status, journalctl

## Cron not running
Check cron service, logs

## Out of memory
Check processes, add swap

## Secure Linux
Firewall, patches, SSH keys

## File descriptor leaks
lsof

## Core dumps
ulimit, gdb

## DNS issues
resolv.conf, dig

## SELinux issues
getenforce, ausearch

## Mount filesystem
mount / umount
