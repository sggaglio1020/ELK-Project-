## Week 5 Homework Submission File: Archiving and Logging Data

Please edit this file by adding the solution commands on the line below the prompt.

Save and submit the completed file for your homework submission.

---

### Step 1: Create, Extract, Compress, and Manage tar Backup Archives

1. Command to **extract** the `TarDocs.tar` archive to the current directory:tar -zxvf TarDocs.tar.gz

2. Command to **create** the `Javaless_Doc.tar` archive from the `TarDocs/` directory, while excluding the `TarDocs/Documents/Java` directory:tar -cvzf archive.tar Javaless_Doc.tar

3. Command to ensure `Java/` is not in the new `Javaless_Docs.tar` archive:tar -xvf Javaless_Doc.tar

**Bonus** 
- Command to create an incremental archive called `logs_backup_tar.gz` with only changed files to `snapshot.file` for the `/var/log` directory:tar -cvpf logs_backup_tar.gz -g snapshot.file

#### Critical Analysis Question

- Why wouldn't you use the options `-x` and `-c` at the same with `tar`? -x and -c are used to produce a file. 

---

### Step 2: Create, Manage, and Automate Cron Jobs

1. Cron job for backing up the `/var/log/auth.log` file:

---crontab -e 0 6 * * 4 tar gzip -pcf/home/username

### Step 3: Write Basic Bash Scripts

1. Brace expansion command to create the four subdirectories: mkdir -p work {F1,F2,F3,F4}

2. Paste your `system.sh` script edits below:

    ```bash
    #!/bin/bash
    [Your solution script contents here]
    ```free -m awk {print -f "Memory Usa"
    ```df -h awk {print -f "Disk Usage}"
    ```top -bnl |grep|u ad| awk print {CPU Load}
    
3. Command to make the `system.sh` script executable: chmod vtx system.sh 

**Optional**
- Commands to test the script and confirm its execution: sudo apt update {apt upgrade -y}

**Bonus**
- Command to copy `system` to system-wide cron directory: /etc/cron.d/

---

### Step 4. Manage Log File Sizes
 
1. Run `sudo nano /etc/logrotate.conf` to edit the `logrotate` configuration file. 

    Configure a log rotation scheme that backs up authentication messages to the `/var/log/auth.log`.

    - Add your config file edits below:

    ```bash
    [Your logrotate scheme edits here]
    ``` /var/log/etc/log rotate. conf {
        rotate 7
        weekly
        no compress
        no error messages
    }
---

### Bonus: Check for Policy and File Violations

1. Command to verify `auditd` is active: #systemctl is-enabled auditd

2. Command to set number of retained logs and maximum log file size: cat vars/log/etc/audit/auditd.conf {size #
logs #}

    - Add the edits made to the configuration file below:

    ```bash
    [Your solution edits here]
    ```cat vars/log/etc/audit/auditd.conf {
        size:35
        log:7
    }

3. Command using `auditd` to set rules for `/etc/shadow`, `/etc/passwd` and `/var/log/auth.log`: -w /etc/shadow -p wa -k shadow
                                                                                                 -w var/log/auth.log -pa wa -k auth.log
                                                                                                 -w /etc/passwd -p wa -k passwd


    - Add the edits made to the `rules` file below:

    ```bash
    [Your solution edits here]
    ```cat rules.txt

4. Command to restart `auditd`: /user/bin/dockerd -k docker
                                 service auditd restart 

5. Command to list all `auditd` rules: auditctl -l

6. Command to produce an audit report: aureport -au 

7. Create a user with `sudo useradd attacker` and produce an audit report that lists account modifications: sudo useradd -m -s/bin/bash -c

8. Command to use `auditd` to watch `/var/log/cron`: auditctl -w /etc/passwd -p war -k password file

9. Command to verify `auditd` rules: ausearch -k shadow 

---

### Bonus (Research Activity): Perform Various Log Filtering Techniques

1. Command to return `journalctl` messages with priorities from emergency to error: journalctl -p err -b

1. Command to check the disk usage of the system journal unit since the most recent boot:[root@tecmint ~] # df

1. Comand to remove all archived journal files except the most recent two: journalctl-rotate 
                                                                           journalctl-vacuum-time=ls 


1. Command to filter all log messages with priority levels between zero and two, and save output to `/home/sysadmin/Priority_High.txt`: jouranlctl -po

1. Command to automate the last command in a daily cronjob. Add the edits made to the crontab file below:

    ```bash
    [Your solution cron edits here]
    ```@daily curl http:// www.google.com

---
Â© 2020 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
