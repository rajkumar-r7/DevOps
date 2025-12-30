# Linux Basics – Interview Questions & Answers 🐧

## Q1. How do you print the current date and time in a shell script?
date
date "+%Y-%m-%d %H:%M:%S"

## Q2. How do you view the contents of a ZIP file without extracting it?
unzip -l file.zip

## Q3. What does Linux permission 755 mean?
Owner: rwx, Group: r-x, Others: r-x

## Q4. Which command is used to change file or directory permissions?
chmod 755 file

## Q5. Which command is used to create a new Linux user?
useradd username
passwd username

## Q6. How do you check all active network ports?
ss -tuln

## Q7. Which shell does Linux use?
Bash

## Q8. Where should environment variables be stored?
~/.bashrc, /etc/environment

## Q9. Command to list listening ports?
ss -lntup

## Q10. Check top CPU or memory process?
top / htop

## Q11. Generate SSH key?
ssh-keygen

## Q12. Popular Linux distributions?
Ubuntu, CentOS, RHEL, Debian

## Q13. Print last 15 lines of file?
tail -n 15 file

## Q14. Enable passwordless SSH?
ssh-keygen
ssh-copy-id user@host
