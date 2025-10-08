- [1. RHCSA EX200 RHEL10](#1-rhcsa-ex200-rhel10)
  - [1.1. Understand and use essential tools \[\]](#11-understand-and-use-essential-tools-)
    - [Registering a System](#registering-a-system)
    - [1.1.1. Access a shell prompt and issue commands with correct syntax](#111-access-a-shell-prompt-and-issue-commands-with-correct-syntax)
    - [1.1.2. Use input-output redirection (\>, \>\>, |, 2\>, etc.)](#112-use-input-output-redirection----2-etc)
    - [1.1.3. Use grep and regular expressions to analyze text](#113-use-grep-and-regular-expressions-to-analyze-text)
    - [1.1.4. Access remote systems using SSH](#114-access-remote-systems-using-ssh)
    - [1.1.5. Log in and switch users in multiuser targets](#115-log-in-and-switch-users-in-multiuser-targets)
    - [1.1.6. Archive, compress, unpack, and uncompress files using tar, gzip, and bzip2](#116-archive-compress-unpack-and-uncompress-files-using-tar-gzip-and-bzip2)
    - [1.1.7. Create and edit text files](#117-create-and-edit-text-files)
    - [1.1.8. Create, delete, copy, and move files and directories](#118-create-delete-copy-and-move-files-and-directories)
    - [1.1.9. Create hard and soft links](#119-create-hard-and-soft-links)
    - [1.1.10. List, set, and change standard ugo/rwx permissions](#1110-list-set-and-change-standard-ugorwx-permissions)
    - [1.1.11. Locate, read, and use system documentation including man, info, and files in /usr/share/doc](#1111-locate-read-and-use-system-documentation-including-man-info-and-files-in-usrsharedoc)
  - [1.2. Manage software](#12-manage-software)
    - [1.2.1. Configure access to RPM repositories](#121-configure-access-to-rpm-repositories)
  - [1.3. Create simple shell scripts](#13-create-simple-shell-scripts)
  - [1.4. Operate running systems](#14-operate-running-systems)
  - [1.5. Configure local storage](#15-configure-local-storage)
  - [1.6. Create and configure file systems](#16-create-and-configure-file-systems)
  - [1.7. Schedule tasks using at and cron](#17-schedule-tasks-using-at-and-cron)
  - [1.8. Manage basic networking](#18-manage-basic-networking)
  - [1.9. Manage users and groups](#19-manage-users-and-groups)
  - [1.10. Manage security](#110-manage-security)


# 1. RHCSA EX200 RHEL10

## 1.1. Understand and use essential tools []
### Registering a System
```bash
rhc connect
subscription-manager register|status|syspurpose|unregister
insights-client --register

# certificates 
ls /etc/pki/product-default # identify RH product installed on system
ls /etc/pki/consumer # identify system
ls /etc/pki/entitlement # authenticate system to repositories
```

### 1.1.1. Access a shell prompt and issue commands with correct syntax  
   ```bash
   echo "Current user: $(whoami)"  ### whoami: print current user
   for file in $(ls *.log); do grep "ERROR" "$file"; done  ### loop through .log files and search for "ERROR"
   pwd # print working directory
   cd ~ or cd # change to home directory
   echo The value of \$HOME is your home directory. 
   $ The value of $HOME is your home directory. ## \ used as escape character 
   myhost=$(hostname -s); echo $myhost # invoke command and assign to variable
   newgrp group_name # temporary change user group from primary to secondary, all executed commands use this group.
   ```
### 1.1.2. Use input-output redirection (>, >>, |, 2>, etc.)  
   ```bash
   grep "fail" /var/log/messages | tee failed.log  ### |: pipe output; tee: write to file and stdout
   ls /nonexistent 2>&1 | tee errors.txt  ### 2>&1: redirect stderr to stdout
   cat file1.txt file2.txt > combined.txt  ### >: overwrite output file
   ```
### 1.1.3. Use grep and regular expressions to analyze text  
   ```bash
   grep -E "^(root|admin)" /etc/passwd  ### -E: extended regex; ^: start of line
   grep -r "password" /etc/  ### -r: recursive search
   grep -A2 "error" /var/log/messages  ### -A2: show 2 lines after match
   grep -B2 "fail" /var/log/messages  ### -B2: show 2 lines before match
   grep -C1 "denied" /var/log/secure  ### -C1: show 1 line before and after match
   grep -i "warning" /var/log/messages  ### -i: ignore case
   grep -v "^#" /etc/ssh/sshd_config  ### -v: invert match (exclude lines starting with #)
   grep -n "PermitRootLogin" /etc/ssh/sshd_config  ### -n: show line numbers
   grep -o "[0-9]\{3,\}" /var/log/messages  ### -o: only matching part; find numbers with 3+ digits
   grep -E "([A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,})" /etc/passwd  ### match email-like patterns
   grep -E "([0-9]{1,3}\.){3}[0-9]{1,3}" /var/log/messages  ### match IPv4 addresses
   grep -E "^[^:]+:[^:]*:[0-9]{4,}:" /etc/passwd  ### match lines with UID >= 1000
   ```
### 1.1.4. Access remote systems using SSH  
   ```bash
   ssh -X user@host "firefox"  ### -X: enable X11 forwarding
   ssh user@host "tar czf /tmp/home.tar.gz /home/user"  ### run remote command via SSH
   ```
### 1.1.5. Log in and switch users in multiuser targets  
   ```bash
   su -l username -c "whoami"  ### su: switch user; -l: login shell; -c: run command
   sudo -u username bash -c 'id'  ### sudo: run as another user; -u: specify user
   ```
### 1.1.6. Archive, compress, unpack, and uncompress files using tar, gzip, and bzip2  
   ```bash
   tar --exclude='*.tmp' -czvf backup.tar.gz /home/user  ### --exclude: skip files; -c: create; -z: gzip; -v: verbose; -f: file
   tar -tvf archive.tar | grep '.sh'  ### -t: list; -v: verbose; -f: file
   ```
### 1.1.7. Create and edit text files  
   ```bash
   touch file{1..5}
   touch file{a,b}
   touch file{a{b,c},d}
   echo -e "Line1\nLine2" > file.txt  ### -e: interpret escapes; >: overwrite
   sed -i 's/foo/bar/g' file.txt  ### sed: stream editor; -i: in-place; s/foo/bar/g: replace all
   ```
### 1.1.8. Create, delete, copy, and move files and directories  
   ```bash
   find . -name "*.bak" -exec rm {} \;  ### find: search; -exec: run command on results
   find . -name "*.bak" -delete
   cp -av dir1/ dir2/  ### cp: copy; -a: archive - keep permissions; -v: verbose
   mkdir -p dir/subdir ### -p: make parent directory
   ls -R dir ### -R: recursive list directories
   tree -L 5 dir ### show tree of directory -L <number>: deep of tree 
   ```

### 1.1.9. Create hard and soft links  
   ```bash
   ln -s /var/log/messages /tmp/messages_link  ### ln -s: create symbolic (soft) link
   ln /etc/hosts /tmp/hosts_hardlink  ### ln: create hard link
   ```
### 1.1.10. List, set, and change standard ugo/rwx permissions  
    ```bash
    chmod g+w,o-r file.txt  ### chmod: change permissions; g+w: add write for group; o-r: remove read for others
    chown :developers file.txt  ### chown: change owner; :developers: change group
    find /var/www -type f -exec chmod 644 {} \;  ### find: search; -type f: files; -exec: run command
    ```
### 1.1.11. Locate, read, and use system documentation including man, info, and files in /usr/share/doc  
```bash
man -k passwd                   ### Search man page descriptions for 'passwd'
man -w ls                      ### Show location of 'ls' man page
man -W passwd                  ### Show all locations of 'passwd' man page
man -wK passwd                 ### Show locations of man pages containing 'passwd' anywhere in their name or description
man ls                         ### View manual for 'ls'
man 5 passwd                   ### View section 5 (file formats) for 'passwd'
whatis tar                     ### Show short description for 'tar'
man -a passwd                  ### Show all man pages for 'passwd'
info coreutils 'ls invocation' ### Read info documentation for 'ls'
less /usr/share/doc/bash/README ### View documentation file
```

## 1.2. Manage software
### 1.2.1. Configure access to RPM repositories  
   ```bash
   dnf config-manager --set-enabled codeready-builder-for-rhel-10-x86_64-rpms  ### enable repo
   dnf repolist all  ### list all repos
   ```
2. Install and remove RPM software packages  
   ```bash
   dnf install --downloadonly --downloaddir=/tmp vim  ### --downloadonly: only download; --downloaddir: target dir
   rpm -q --scripts httpd  ### -q: query; --scripts: show package scripts
   ```
3. Configure access to Flatpak repositories  
   ```bash
   flatpak remote-list --show-details  ### list Flatpak repos with details
   ```
4. Install and remove Flatpak software packages  
   ```bash
   flatpak install --user flathub org.mozilla.firefox  ### --user: install for user; flathub: repo; org.mozilla.firefox: app
   flatpak uninstall --delete-data org.mozilla.firefox  ### --delete-data: remove app data
   ```

## 1.3. Create simple shell scripts
1. Conditionally execute code (use of: if, test, [], etc.)  
   ```bash
   if grep -q "ERROR" /var/log/messages; then  ### -q: quiet (no output)
     echo "Errors found"
   else
     echo "No errors"
   fi
   ```
2. Use Looping constructs (for, etc.) to process file, command line input  
   ```bash
   for user in $(cut -d: -f1 /etc/passwd); do  ### cut: split by ':'; -f1: first field
     echo "Checking $user"
     id $user  ### id: show user info
   done
   ```
3. Process script inputs ($1, $2, etc.)  
   ```bash
   if [ $# -lt 2 ]; then  ### $# number of args; -lt: less than
     echo "Usage: $0 arg1 arg2"  ### $0: script name
     exit 1
   fi
   echo "Arg1: $1, Arg2: $2"  ### $1/$2: first/second arg
   ```
4. Processing output of shell commands within a script  
   ```bash
   files=$(find /var/log -name "*.log")  ### $(...): command substitution
   for f in $files; do
     echo "$f: $(wc -l < $f) lines"  ### wc -l: count lines
   done
   ```

## 1.4. Operate running systems
1. Boot, reboot, and shut down a system normally  
   ```bash
   systemctl reboot --force  ### --force: force reboot
   systemctl poweroff --no-wall  ### --no-wall: don't notify users
   ```
2. Boot systems into different targets manually  
   ```bash
   systemctl list-units --type=target  ### list systemd targets
   systemctl isolate rescue.target  ### switch to rescue mode
   ```
3. Interrupt the boot process in order to gain access to a system  
   *(GRUB: add `rd.break` and mount sysroot for password reset)*
   ```bash
   mount -o remount,rw /sysroot  ### remount as read-write
   chroot /sysroot  ### change root to sysroot
   passwd root  ### reset root password
   ```
4. Identify CPU/memory intensive processes and kill processes  
   ```bash
   ps aux --sort=-%cpu | head  ### sort by CPU usage
   pkill -u user  ### kill all processes for user
   ```
5. Adjust process scheduling  
   ```bash
   nice -n -5 tar czf backup.tar.gz /home  ### -n: set nice value
   renice -n 15 -p $(pgrep httpd)  ### renice: change nice value; -p: process id
   ```
6. Manage tuning profiles  
   ```bash
   tuned-adm recommend  ### recommend best profile
   tuned-adm profile virtual-guest  ### set profile
   ```
7. Locate and interpret system log files and journals  
   ```bash
   journalctl --since "1 hour ago"  ### logs from last hour
   journalctl -u sshd --no-pager  ### logs for sshd; --no-pager: no paging
   ```
8. Preserve system journals  
   ```bash
   journalctl --vacuum-size=500M  ### reduce journal size
   journalctl --output=export > /root/journal-backup.bin  ### export journal
   ```
9. Start, stop, and check the status of network services  
   ```bash
   systemctl restart NetworkManager  ### restart service
   systemctl is-enabled firewalld  ### check if enabled
   ```
10. Securely transfer files between systems  
    ```bash
    rsync -avz --progress /etc user@host:/backup/etc  ### rsync: sync files; -a: archive; -v: verbose; -z: compress
    scp -r /var/www user@host:/var/www  ### scp: secure copy; -r: recursive
    ```

## 1.5. Configure local storage
1. List, create, delete partitions on MBR and GPT disks  
   ```bash
   parted /dev/sdb print  ### print partition table
   parted /dev/sdb mkpart primary ext4 1MiB 100MiB  ### create partition
   fdisk -l /dev/sdb  ### list partitions
   ```
2. Create and remove physical volumes  
   ```bash
   pvcreate /dev/sdb1 /dev/sdc1  ### create PVs
   pvs  ### list PVs
   pvremove /dev/sdc1  ### remove PV
   ```
3. Assign physical volumes to volume groups  
   ```bash
   vgcreate vgdata /dev/sdb1 /dev/sdc1  ### create VG
   vgextend vgdata /dev/sdd1  ### add PV to VG
   vgs  ### list VGs
   ```
4. Create and delete logical volumes  
   ```bash
   lvcreate -L 5G -n lvbackup vgdata  ### create LV
   lvremove /dev/vgdata/lvbackup  ### remove LV
   lvs  ### list LVs
   ```
5. Configure systems to mount file systems at boot by universally unique ID (UUID) or label  
   ```bash
   blkid /dev/sdb1  ### get UUID
   echo "UUID=$(blkid -s UUID -o value /dev/sdb1) /mnt/data ext4 defaults 0 2" >> /etc/fstab  ### add to fstab
   ```
6. Add new partitions and logical volumes, and swap to a system non-destructively  
   ```bash
   lvextend -r -L +2G /dev/vgdata/lvdata  ### -r: resize filesystem
   mkswap /dev/vgdata/lvswap  ### create swap
   swapon /dev/vgdata/lvswap  ### enable swap
   ```

## 1.6. Create and configure file systems
1. Create, mount, unmount, and use VFAT, ext4, and xfs file systems  
   ```bash
   mkfs.xfs /dev/vgdata/lvdata  ### create xfs filesystem
   mount -o noatime /dev/vgdata/lvdata /mnt/data  ### mount with noatime
   umount /mnt/data  ### unmount
   ```
2. Mount and unmount network file systems using NFS  
   ```bash
   mount -t nfs4 server:/export/home /mnt/home  ### mount NFSv4
   echo "server:/export/home /mnt/home nfs4 defaults 0 0" >> /etc/fstab  ### add NFS to fstab
   ```
3. Configure autofs  
   ```bash
   echo "/home /etc/auto.home" >> /etc/auto.master  ### add autofs map
   echo "user -rw,soft server:/export/user" > /etc/auto.home  ### map user dir
   systemctl restart autofs  ### restart autofs
   ```
4. Extend existing logical volumes  
   ```bash
   lvextend -L +5G /dev/vgdata/lvdata  ### extend LV
   xfs_growfs /mnt/data  ### grow xfs filesystem
   ```
5. Diagnose and correct file permission problems  
   ```bash
   find /var/www -type f -exec chmod 644 {} \;  ### set permissions
   restorecon -Rv /var/www  ### restore SELinux context
   ```
6. Deploy, configure, and maintain systems  
   ```bash
   dnf groupinstall "Web Server"  ### install group
   systemctl enable --now httpd  ### enable and start httpd
   ```

## 1.7. Schedule tasks using at and cron
1. Start and stop services and configure services to start automatically at boot  
   ```bash
   systemctl enable --now crond  ### enable/start cron
   systemctl disable firewalld  ### disable firewalld
   ```
2. Configure systems to boot into a specific target automatically  
   ```bash
   systemctl set-default graphical.target  ### set default target
   systemctl get-default  ### show default target
   ```
3. Configure time service clients  
   ```bash
   timedatectl set-timezone America/New_York  ### set timezone
   chronyc tracking  ### show chrony status
   ```
4. Install and update software packages from Red Hat Content Delivery Network, a remote repository, or from the local file system  
   ```bash
   dnf update --security  ### update security packages
   dnf install /tmp/package.rpm  ### install local rpm
   ```
5. Modify the system bootloader  
   ```bash
   grub2-editenv list  ### list GRUB env
   grub2-set-default 2  ### set default boot entry
   ```

## 1.8. Manage basic networking
1. Configure IPv4 and IPv6 addresses  
   ```bash
   nmcli con add type ethernet con-name eth1 ifname eth1 ipv4.addresses 192.168.2.10/24 ipv4.method manual  ### add connection
   nmcli con up eth1  ### bring up connection
   ```
2. Configure hostname resolution  
   ```bash
   echo "192.168.2.100 server2" >> /etc/hosts  ### add host entry
   hostnamectl set-hostname server2.example.com  ### set hostname
   ```
3. Configure network services to start automatically at boot  
   ```bash
   systemctl enable --now NetworkManager  ### enable/start NetworkManager
   systemctl enable --now sshd  ### enable/start sshd
   ```
4. Restrict network access using firewalld and firewall-cmd  
   ```bash
   firewall-cmd --permanent --zone=public --add-service=https  ### add https service
   firewall-cmd --permanent --zone=public --remove-service=ftp  ### remove ftp service
   firewall-cmd --reload  ### reload firewall
   ```

## 1.9. Manage users and groups
1. Create, delete, and modify local user accounts  
   ```bash
   useradd -m -s /bin/bash alice  ### -m: create home; -s: shell
   usermod -L bob  ### -L: lock account
   userdel -r charlie  ### -r: remove home
   usermod -U
   usermod -aG group username 
   usermod -c "comment" username
   ```
2. Change passwords and adjust password aging for local user accounts  
   ```bash
   passwd --expire alice  ### expire password
   chage -E 2025-12-31 bob  ### -E: set expiry date
   ```
3. Create, delete, and modify local groups and group memberships  
   ```bash
   groupadd -g GID devs  ### add group
   groupadd -r system_group_name 
   groupmod -n new_group_name old_group_name
   groupmod -g new_GID group_name
   gpasswd -a alice devs  ### add user to group
   gpasswd -d bob devs  ### remove user from group
   groupdel group_name
   groupmod -aU user_name1 user_name2
   ```
4. Configure superuser access  
   ```bash
   echo "alice ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers.d/alice  ### passwordless sudo for alice
   ```
5. Change default user settings

   ```bash
   /etc/skel                # Directory containing default files for new user home directories files should have 644 perm
   /etc/login.defs          # Configuration file for user account creation defaults (UID ranges, password aging, etc.)
   /etc/secure/pwquality.conf # Password quality requirements (minimum length, complexity, etc.)
   ```
   
## 1.10. Manage security
1. Configure firewall settings using firewall-cmd/firewalld  
   ```bash
   firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="192.168.1.0/24" service name="ssh" accept'  ### rich rule for ssh
   firewall-cmd --reload  ### reload firewall
   ```
2. Manage default file permissions  
   ```bash
   umask 027  ### set default permissions
   chmod -R o-rwx /home/alice  ### remove other access
   ```
3. Configure key-based authentication for SSH  
   ```bash
   ssh-keygen -t ed25519 -C "alice@server"  ### generate key; -t: type; -C: comment
   ssh-copy-id -i ~/.ssh/id_ed25519.pub user@host  ### copy key to host
   ```
4. Set enforcing and permissive modes for SELinux  
   ```bash
   setenforce 0  ### set permissive mode
   sed -i 's/^SELINUX=.*/SELINUX=permissive/' /etc/selinux/config  ### change config
   ```
5. List and identify SELinux file and process context  
   ```bash
   ls -lZ /var/www/html  ### show SELinux context
   ps -eZ | grep httpd  ### show process context
   ```
6. Restore default file contexts  
   ```bash
   restorecon -Rv /var/www/html  ### restore context; -R: recursive; -v: verbose
   ```
7. Manage SELinux port labels  
   ```bash
   semanage port -a -t ssh_port_t -p tcp 2222  ### -a: append (add); -t: type; -p: protocol
   semanage port -d -t http_port_t -p tcp 8080  ### -d: delete; -t: type; -p: protocol
   ```
8. Use boolean settings to modify system SELinux settings  
   ```bash
   setsebool -P httpd_can_sendmail on  ### -P: persistent; set boolean
   getsebool httpd_can_sendmail  ### get boolean value
   ```
