- [1. Understand and use essential tools \[\]](#1-understand-and-use-essential-tools-)
  - [1.1. Registering a System](#11-registering-a-system)
  - [1.2. Access a shell prompt and issue commands with correct syntax](#12-access-a-shell-prompt-and-issue-commands-with-correct-syntax)
  - [1.3. Use input-output redirection (\>, \>\>, |, 2\>, etc.)](#13-use-input-output-redirection----2-etc)
  - [1.4. Use grep and regular expressions to analyze text](#14-use-grep-and-regular-expressions-to-analyze-text)
  - [1.5. Access remote systems using SSH](#15-access-remote-systems-using-ssh)
  - [1.6. Log in and switch users in multiuser targets](#16-log-in-and-switch-users-in-multiuser-targets)
  - [1.7. Archive, compress, unpack, and uncompress files using tar, gzip, and bzip2](#17-archive-compress-unpack-and-uncompress-files-using-tar-gzip-and-bzip2)
  - [1.8. Create and edit text files](#18-create-and-edit-text-files)
  - [1.9. Create, delete, copy, and move files and directories](#19-create-delete-copy-and-move-files-and-directories)
  - [1.10. Create hard and soft links](#110-create-hard-and-soft-links)
  - [1.11. List, set, and change standard ugo/rwx permissions](#111-list-set-and-change-standard-ugorwx-permissions)
  - [1.12. Locate, read, and use system documentation including man, info, and files in /usr/share/doc](#112-locate-read-and-use-system-documentation-including-man-info-and-files-in-usrsharedoc)
- [2. Manage software](#2-manage-software)
  - [2.1. Configure access to RPM repositories](#21-configure-access-to-rpm-repositories)
  - [2.2. Install and remove RPM software packages](#22-install-and-remove-rpm-software-packages)
  - [2.3. Configure access to Flatpak repositories](#23-configure-access-to-flatpak-repositories)
  - [2.4. Install and remove Flatpak software packages](#24-install-and-remove-flatpak-software-packages)
- [3. Create simple shell scripts](#3-create-simple-shell-scripts)
  - [3.1. Conditionally execute code (use of: if, test, \[\], etc.)](#31-conditionally-execute-code-use-of-if-test--etc)
  - [3.2. Use Looping constructs (for, etc.) to process file, command line input](#32-use-looping-constructs-for-etc-to-process-file-command-line-input)
  - [3.3. Process script inputs ($1, $2, etc.)](#33-process-script-inputs-1-2-etc)
  - [3.4. Processing output of shell commands within a script](#34-processing-output-of-shell-commands-within-a-script)
- [4. Operate running systems](#4-operate-running-systems)
  - [4.1. Boot, reboot, and shut down a system normally](#41-boot-reboot-and-shut-down-a-system-normally)
  - [4.2. Boot systems into different targets manually](#42-boot-systems-into-different-targets-manually)
  - [4.3. Interrupt the boot process in order to gain access to a system](#43-interrupt-the-boot-process-in-order-to-gain-access-to-a-system)
  - [4.4. Identify CPU/memory intensive processes and kill processes](#44-identify-cpumemory-intensive-processes-and-kill-processes)
  - [4.5. Adjust process scheduling](#45-adjust-process-scheduling)
  - [4.6. Manage tuning profiles](#46-manage-tuning-profiles)
  - [4.7. Locate and interpret system log files and journals](#47-locate-and-interpret-system-log-files-and-journals)
  - [4.8. Rsyslog](#48-rsyslog)
  - [4.9. Preserve system journals](#49-preserve-system-journals)
  - [4.10. Start, stop, and check the status of network services](#410-start-stop-and-check-the-status-of-network-services)
  - [4.11. Securely transfer files between systems](#411-securely-transfer-files-between-systems)
- [5. Configure local storage](#5-configure-local-storage)
  - [5.1. List, create, delete partitions on MBR and GPT disks](#51-list-create-delete-partitions-on-mbr-and-gpt-disks)
  - [5.2. Create and remove physical volumes](#52-create-and-remove-physical-volumes)
  - [5.3. Assign physical volumes to volume groups](#53-assign-physical-volumes-to-volume-groups)
  - [5.4. Create and delete logical volumes](#54-create-and-delete-logical-volumes)
  - [5.5. Configure systems to mount file systems at boot by universally unique ID (UUID) or label](#55-configure-systems-to-mount-file-systems-at-boot-by-universally-unique-id-uuid-or-label)
  - [5.6. Add new partitions and logical volumes, and swap to a system non-destructively](#56-add-new-partitions-and-logical-volumes-and-swap-to-a-system-non-destructively)
- [6. Create and configure file systems](#6-create-and-configure-file-systems)
  - [6.1. Create, mount, unmount, and use VFAT, ext4, and xfs file systems](#61-create-mount-unmount-and-use-vfat-ext4-and-xfs-file-systems)
  - [6.2. Mount and unmount network file systems using NFS](#62-mount-and-unmount-network-file-systems-using-nfs)
  - [6.3. Configure autofs](#63-configure-autofs)
  - [6.4. Extend existing logical volumes](#64-extend-existing-logical-volumes)
  - [6.5. Diagnose and correct file permission problems](#65-diagnose-and-correct-file-permission-problems)
- [7. Deploy, configure, and maintain systems](#7-deploy-configure-and-maintain-systems)
  - [7.1. Schedule tasks using at and cron](#71-schedule-tasks-using-at-and-cron)
  - [7.2. Start and stop services and configure services to start automatically at boot](#72-start-and-stop-services-and-configure-services-to-start-automatically-at-boot)
  - [7.3. Configure systems to boot into a specific target automatically](#73-configure-systems-to-boot-into-a-specific-target-automatically)
  - [7.4. Configure time service clients](#74-configure-time-service-clients)
  - [7.5. Install and update software packages from Red Hat Content Delivery Network, a remote repository, or from the local file system](#75-install-and-update-software-packages-from-red-hat-content-delivery-network-a-remote-repository-or-from-the-local-file-system)
  - [7.6. Modify the system bootloader](#76-modify-the-system-bootloader)
- [8. Manage basic networking](#8-manage-basic-networking)
  - [8.1. Configure IPv4 and IPv6 addresses](#81-configure-ipv4-and-ipv6-addresses)
  - [8.2. Configure hostname resolution](#82-configure-hostname-resolution)
  - [8.3. Configure network services to start automatically at boot](#83-configure-network-services-to-start-automatically-at-boot)
  - [8.4. Restrict network access using firewalld and firewall-cmd](#84-restrict-network-access-using-firewalld-and-firewall-cmd)
- [9. Manage users and groups](#9-manage-users-and-groups)
  - [9.1. Create, delete, and modify local user accounts](#91-create-delete-and-modify-local-user-accounts)
  - [9.2. Change passwords and adjust password aging for local user accounts](#92-change-passwords-and-adjust-password-aging-for-local-user-accounts)
  - [9.3. Create, delete, and modify local groups and group memberships](#93-create-delete-and-modify-local-groups-and-group-memberships)
  - [9.4. Configure superuser access](#94-configure-superuser-access)
  - [9.5. Change default user settings](#95-change-default-user-settings)
- [10. Manage security](#10-manage-security)
  - [10.1. Configure firewall settings using firewall-cmd/firewalld](#101-configure-firewall-settings-using-firewall-cmdfirewalld)
  - [10.2. Manage default file permissions](#102-manage-default-file-permissions)
  - [10.3. Configure key-based authentication for SSH](#103-configure-key-based-authentication-for-ssh)
  - [10.4. Troubleshoot Selinx](#104-troubleshoot-selinx)
  - [10.5. Set enforcing and permissive modes for SELinux](#105-set-enforcing-and-permissive-modes-for-selinux)
  - [10.6. List and identify SELinux file and process context](#106-list-and-identify-selinux-file-and-process-context)
  - [10.7. Restore default file contexts](#107-restore-default-file-contexts)
  - [10.8. Manage SELinux port labels](#108-manage-selinux-port-labels)
  - [10.9. Use boolean settings to modify system SELinux settings](#109-use-boolean-settings-to-modify-system-selinux-settings)

RHCSA EX200 RHEL10

## 1. Understand and use essential tools []

### 1.1. Registering a System

   ```bash
   rhc connect
   subscription-manager register|status|syspurpose|unregister
   insights-client --register

   # certificates 
   ls /etc/pki/product-default # identify RH product installed on system
   ls /etc/pki/consumer # identify system
   ls /etc/pki/entitlement # authenticate system to repositories
   ```

### 1.2. Access a shell prompt and issue commands with correct syntax  

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

### 1.3. Use input-output redirection (>, >>, |, 2>, etc.)  

   ```bash
   grep "fail" /var/log/messages | tee failed.log  ### |: pipe output; tee: write to file and stdout
   ls /nonexistent 2>&1 | tee errors.txt  ### 2>&1: redirect stderr to stdout
   ls /nonexistent &> errors.txt  ### redirect stderr and stdout to errors.txt
   ls /nonexistent > errors.txt 2>&1  ### redirect stderr and stdout to errors.txt
   ls /nonexistent > errors.txt 2> /dev/null  ### redirect discard errors and stdout to errors.txt
   cat file1.txt file2.txt > combined.txt  ### >: overwrite output file
   ```

### 1.4. Use grep and regular expressions to analyze text  

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

### 1.5. Access remote systems using SSH  

   ```bash
   ssh -X user@host "firefox"  ### -X: enable X11 forwarding
   ssh user@host "tar czf /tmp/home.tar.gz /home/user"  ### run remote command via SSH
   ```

### 1.6. Log in and switch users in multiuser targets  

   ```bash
   sudo -i # switch to root
   sudo su - username # switch to user
   sudo su - username -c "whoami" # run command as other user
   su -l username -c "whoami"  ### su: switch user; -l: login shell; -c: run command
   sudo -u username bash -c 'id'  ### sudo: run as another user; -u: specify user
   ```

### 1.7. Archive, compress, unpack, and uncompress files using tar, gzip, and bzip2  

   ```bash
   tar --exclude='*.tmp' -czvf backup.tar.gz /home/user  ### --exclude: skip files; -c: create; -z: gzip; -v: verbose; -f: file
   tar -cvf test.tar.gz /home/user # compress directory 
   tar -xvf test.tar.gz . # uncompress file
   tar -tvf archive.tar | grep '.sh'  ### -t: list; -v: verbose; -f: file
   ```

### 1.8. Create and edit text files  

   ```bash
   touch file{1..5}
   touch file{a,b}
   touch file{a{b,c},d}
   echo -e "Line1\nLine2" > file.txt  ### -e: interpret escapes; >: overwrite
   sed -i 's/foo/bar/g' file.txt  ### sed: stream editor; -i: in-place; s/foo/bar/g: replace all
   ```

### 1.9. Create, delete, copy, and move files and directories  

   ```bash
   find . -name "*.bak" -exec rm {} \;  ### find: search; -exec: run command on results
   find . -name "*.bak" -delete
   cp -av dir1/ dir2/  ### cp: copy; -a: archive - keep permissions; -v: verbose
   mkdir -p dir/subdir ### -p: make parent directory
   ls -R dir ### -R: recursive list directories
   tree -L 5 dir ### show tree of directory -L <number>: deep of tree 
   ```

### 1.10. Create hard and soft links  

   ```bash
   ln -s /var/log/messages /tmp/messages_link  ### ln -s: create symbolic (soft) link
   ln /etc/hosts /tmp/hosts_hardlink  ### ln: create hard link
   ```

### 1.11. List, set, and change standard ugo/rwx permissions  

   ```bash
   chmod go+w,o-r file.txt      # Add write for group, remove read for others on file.txt
   chmod a+x script.sh          # Add execute permission for all users on script.sh
   chown :developers file.txt   # Change group ownership of file.txt to 'developers'
   find /var/www -type f -exec chmod 644 {} \;  # Set permissions to 644 for all files under /var/www
   chmod -R g+rwX dir           # Recursively add read/write for group and execute for directories/files with any execute bit set; this adds execute bit only to directories and files that already have at least one execute bit set 
   chmod 00770 example # to remove special permission additional 0 is necessary. 
   ```

| Mode | Description                                                                                                                       |
| ---- | --------------------------------------------------------------------------------------------------------------------------------- |
| `r`  | Read access to the file. Listing access to the directory.                                                                         |
| `w`  | Write permissions to the file or directory.                                                                                       |
| `x`  | Execute permissions to the file. Allows entering the directory and accessing files and subdirectories inside the directory.       |
| `X`  | Special execute: Execute permissions to a directory, or execute permissions to a file if at least one of the execute bits is set. |

| Permission     | Bit Notation | Effect on Files                                                                  | Effect on Directories                                                                                                                     |
| -------------- | ------------ | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `u+s` (suid)   | `4000`       | File executes as the user that owns the file, not as the user that ran the file. | No effect.                                                                                                                                |
| `g+s` (sgid)   | `2000`       | File executes as the group that owns the file.                                   | Files created in the directory have a group owner matching the group owner of the directory.                                              |
| `o+t` (sticky) | `1000`       | No effect.                                                                       | Users with write access to the directory can remove only files that they own; they cannot remove or force saves to files owned by others. |

### 1.12. Locate, read, and use system documentation including man, info, and files in /usr/share/doc  

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

## 2. Manage software

### 2.1. Configure access to RPM repositories  

   ```bash
   dnf config-manager --enable codeready-builder-for-rhel-10-x86_64-rpms  ### enable repo
   dnf repolist all  ### list all repos
   dnf config-manager --addrepo="https://example.com" 
   dnf config-manager --addrepo="/mnt/cd" # add repository 
   vi /etc/yum.repos.d/example.repo
   rpm --import GPG_KEY
   dnf install example.rpm
   ```

### 2.2. Install and remove RPM software packages  

   ```bash
   dnf install --downloadonly --downloaddir=/tmp vim  # --downloadonly: only download; --downloaddir: target dir
   rpm -q --scripts httpd  # -q: query package; --scripts: show package scripts
   rpm -q dnf              # -q: query if 'dnf' is installed
   rpm -ql dnf             # -q: query; -l: list files in 'dnf' package
   rpm -qc openssh-clients # -q: query; -c: list config files in 'openssh-clients'
   rpm -qf /etc/yum.repos.d # -q: query; -f: find which package owns file/dir
   rpm -ivh podman-5.4.0-1.el10.x86_64.rpm # -i: install; -v: verbose; -h: hash progress
   rpm -qlp podman-5.4.0-1.el10.x86_64.rpm # -q: query; -l: list files; -p: query package file (not installed)
   rpm -qip podman-5.4.0-1.el10.x86_64.rpm # -q: query; -p: package file; -i: show package info
   rpm2cpio httpd-2.4.63-1.el10.x86_64.rpm | cpio -idv # extract rpm contents; -i: extract; -d: create dirs; -v: verbose
   rpm2cpio httpd-2.4.63-1.el10.x86_64.rpm | cpio -tv  # list rpm contents; -t: list; -v: verbose
   dnf search all package_name         # search all packages for 'package_name'
   dnf provides command|file           # find which package provides command/file
   dnf info package_name               # show info about 'package_name'
   dnf list kernel                     # list installed/available 'kernel' packages
   dnf group list --hidden             # list all package groups, including hidden
   dnf group info 'group_name'         # show info about group 'group_name'
   dnf history                         # show transaction history
   dnf history info history_number     # show details for transaction 'history_number'
   dnf list package_name               # list installed/available 'package_name'
   uname -r                            # show running kernel version
   uname -a                            # show all system info
   ```

### 2.3. Configure access to Flatpak repositories  

```bash
flatpak remote-list --show-details  ### list Flatpak repos with details
podman login registry.redhat.io  # Authenticate to Red Hat registry for OCI images
cp $XDG_RUNTIME_DIR/containers/auth.json $HOME/.config/flatpak/oci-auth.json  # Copy OCI authentication to user Flatpak config
cp $XDG_RUNTIME_DIR/containers/auth.json /etc/flatpak/oci-auth.json  # Copy OCI authentication to system-wide Flatpak config

flatpak remotes -d  # List configured Flatpak repositories with details
flatpak remote-ls --app  # List available Flatpak applications from all remotes
flatpak remotes --user  # List Flatpak remotes for current user
flatpak remotes --system  # List system-wide Flatpak remotes

flatpak remote-add --system --if-not-exists name https://example.com/repo.flatpakrepo  # Add a new system-wide Flatpak remote if not already present
flatpak remote-ls remote_name --app  # List applications from a specific remote
flatpak remote-delete remote_name  # Remove a Flatpak remote
flatpak remote-modify --disable remote_name  # Disable a Flatpak remote
flatpak remote-modify --enable remote_name  # Enable a Flatpak remote

cat /etc/flatpak/remotes.d/remote_name.flatpakrepo  # View configuration file for a Flatpak remote
```

### 2.4. Install and remove Flatpak software packages  

   ```bash
   dnf install flatpak  # Install Flatpak package manager

   flatpak install --user flathub org.mozilla.firefox  # Install Firefox from Flathub for current user
   flatpak uninstall --delete-data org.mozilla.firefox  # Uninstall Firefox and remove its data
   flatpak mask thunderbird  # Prevent updates or installation of Thunderbird Flatpak
   flatpak info thunderbird  # Show information about the Thunderbird Flatpak package
   ```

## 3. Create simple shell scripts

   ```bash
   help for
   help if
   help test # information about test statements []
   help while
   ```

### 3.1. Conditionally execute code (use of: if, test, [], etc.)  

   ```bash
   if grep -q "ERROR" /var/log/messages; then  ### -q: quiet (no output)
     echo "Errors found"
   else
     echo "No errors"
   fi
   ```

### 3.2. Use Looping constructs (for, etc.) to process file, command line input  

   ```bash
   for user in $(cut -d: -f1 /etc/passwd); do  ### cut: split by ':'; -f1: first field
     echo "Checking $user"
     id $user  ### id: show user info
   done
   ```

### 3.3. Process script inputs ($1, $2, etc.)  

   ```bash
   if [ $# -lt 2 ]; then  ### $# number of args; -lt: less than
     echo "Usage: $0 arg1 arg2"  ### $0: script name
     exit 1
   fi
   echo "Arg1: $1, Arg2: $2"  ### $1/$2: first/second arg
   ```

### 3.4. Processing output of shell commands within a script  

   ```bash
   files=$(find /var/log -name "*.log")  ### $(...): command substitution
   for f in $files; do
     echo "$f: $(wc -l < $f) lines"  ### wc -l: count lines
   done
   ```

## 4. Operate running systems

### 4.1. Boot, reboot, and shut down a system normally  

   ```bash
   systemctl reboot --force  ### --force: force reboot
   systemctl poweroff --no-wall  ### --no-wall: don't notify users
   ```

### 4.2. Boot systems into different targets manually  

   ```bash
   systemctl list-units --type=target --all  ### list systemd targets
   systemctl isolate rescue.target  ### switch to rescue mode
   ```

To change the GRUB boot target, add `systemd.unit=emergency.target` or `systemd.unit=rescue.target` to the GRUB command line.

### 4.3. Interrupt the boot process in order to gain access to a system  

   *(GRUB: add `init=/bin/bash` and remove all `console=` entries then mount for password reset)*

   ```bash
   mount -o remount,rw /  ### remount as read-write
   passwd root  ### reset root password
   touch /.autorelabel # if selinux is on the /etc/passwd have to be relabelled on boot.
   exec /sbin/init
   ```

### 4.4. Identify CPU/memory intensive processes and kill processes  

   ```bash
   ps aux --sort=-%cpu | head        ### sort by CPU usage
   ps aux --sort=-%mem | head        ### sort by memory usage
   kill PID
   kill -SIGKILL PID
   pkill -u user                     ### kill all processes for user
   ```

### 4.5. Adjust process scheduling  

   ```bash
   nice -n -5 tar czf backup.tar.gz /home  ### -n: set nice value
   renice -n 15 -p $(pgrep httpd)  ### renice: change nice value; -p: process id
   ```

### 4.6. Manage tuning profiles  

   ```bash
   tuned-adm recommend  ### recommend best profile
   tuned-adm profile virtual-guest  ### set profile
   ```

### 4.7. Locate and interpret system log files and journals  

   ```bash
   journalctl --since "1 hour ago"  ### logs from last hour
   journalctl --since today # show today logs
   journalctl -u sshd --no-pager  ### logs for sshd; --no-pager: no paging
   journalctl -n 5 # list all 5 logs
   journalctl -f # follow journalctl
   journalctl -p err # show only error facility
   journalctl -u sshd.service # show logs of specific unit
   journalctl -b 1 # get journal logs  form first boot
   journalctl --list-boots # show available boot entries in journal.
   tail -f /var/log/secure # monitor /var/log/secure
   sealert -a /var/log/audit/audit.log # search for selinux alerts in audit.log
   ```

### 4.8. Rsyslog

   ```bash
   man logger # check list of domain and warning priority 
   man rsyslog.conf # check how to configure rsyslog
   cat /etc/rsyslog.conf # check rsyslog config
   echo "authpriv.warning /var/log/secure" >> /etc/rsyslog.d/custom.conf # custom rsyslog conf to log all logs from authpriv domain and warning priority
   logger -p authpriv.waring "test"  # test rsyslog using logger.
   ```

### 4.9. Preserve system journals  

   ```bash
   mkdir /var/log/journal
   journalctl --flush # after creation of /var/log/journal use this command to flush current journal to storage
   journalctl --vacuum-size=500M  ### reduce journal size
   journalctl --output=export > /root/journal-backup.bin  ### export journal
   man journald.conf # how to modify journal behavior
   systemctl restart systemd-journald
   ```

### 4.10. Start, stop, and check the status of network services  

   ```bash
   systemctl restart NetworkManager  ### restart service
   systemctl is-enabled firewalld  ### check if enabled
   ```

### 4.11. Securely transfer files between systems  

   ```bash
   rsync -avz --progress /etc user@host:/backup/etc  ### rsync: sync files; -a: archive; -v: verbose; -z: compress
   scp -r /var/www user@host:/var/www  ### scp: secure copy; -r: recursive
   ```

## 5. Configure local storage

### 5.1. List, create, delete partitions on MBR and GPT disks  

   ```bash
   parted /dev/sdb print  ### print partition table
   parted /dev/sdb mklabel msdos|gpt ### create partition table msdos or gpt type.
   parted /dev/sdb mkpart primary backup ext4 1MiB 100MiB  ### create primary partition on msdos labeled disk, named backup with partition type ext4. Name, partition type are optional options, primary option is necessary only for msdos labeled disk, don't use when disk is gpt labelled.
   parted /dev/sdb mkpart swap1 linux-swap 1MiB 100MiB ### create swap partition named swap1
   parted /dev/sdb rm 1 ### remove partition 1 on /dev/sdb
   parted /dev/sdb set 1 lvm on # set lmv flag on partition.
   udevadm settle # register new partitions with kernel.
   ```

### 5.2. Create and remove physical volumes  

   ```bash
   pvcreate /dev/sdb1 /dev/sdc1  ### create PVs
   pvs  ### list PVs
   pvmove -A y /dev/sdc1 # free /dev/sdb1 parttition
   vgreduce vg01 /dev/sdc1 # remove physical volume from volume group
   pvremove /dev/sdc1  ### remove PV
   ```

### 5.3. Assign physical volumes to volume groups  

   ```bash
   vgcreate vgdata /dev/sdb1 /dev/sdc1  ### create VG
   vgextend vgdata /dev/sdd1  ### add PV to VG
   vgs  ### list VGs
   ```

### 5.4. Create and delete logical volumes  

   ```bash
   lvcreate -L 5G -n lvbackup vgdata  ### create LV
   lvremove /dev/vgdata/lvbackup  ### remove LV
   lvs  ### list LVs
   ```

### 5.5. Configure systems to mount file systems at boot by universally unique ID (UUID) or label  

   ```bash
   lsblk -fp
   blkid /dev/sdb1  ### get UUID
   echo "UUID=$(blkid -s UUID -o value /dev/sdb1) /mnt/data ext4 defaults 0 2" >> /etc/fstab  ### add to fstab

   ```

### 5.6. Add new partitions and logical volumes, and swap to a system non-destructively  

   ```bash
   lvextend -r -L +2G /dev/vgdata/lvdata  ### -r: resize filesystem
   mkswap /dev/vgdata/lvswap  ### create swap
   swapon /dev/vgdata/lvswap  ### enable swap
   echo 'UUID=xxxxxx swap swap defaults 0 0' >> /etc/fstab
   echo 'UUID=xxxxxx swap swap pri=4 0 0' >> /etc/fstab # setup swap priority, default -2, max 32767, higher number higher priority.
   swapon -a # mount all swap disks in fstab.
   swapoff # turnoff swap
   ```

## 6. Create and configure file systems

### 6.1. Create, mount, unmount, and use VFAT, ext4, and xfs file systems  

   ```bash
   mkfs.xfs /dev/vgdata/lvdata  ### create xfs filesystem
   mount -o noatime /dev/vgdata/lvdata /mnt/data  ### mount with noatime
   umount /mnt/data  ### unmount
   echo '/dev/vgdata/lvdata /mnt/data xfs default 0 0' >> /etc/fstab ### add fstab entry to mount volume.
   ```

### 6.2. Mount and unmount network file systems using NFS  

   ```bash
   showmount --exports server # show mount points on remove server or moutn root directory / to list all mounts.
   mount -t nfs server:/export/home /mnt/home  ### mount NFSv4
   echo "server:/export/home /mnt/home nfs4 rw,sync 0 0" >> /etc/fstab  ### add NFS to fstab
   ```

### 6.3. Configure autofs  

   ```bash
   ### direct autofs
   echo "/- /etc/auto.home" >> /etc/auto.master.d/home.autofs  ### add autofs map
   echo "/home/user -rw,sync server:/export/user" > /etc/auto.home  ### map user dir
   ### indirect autofs
   echo "/home /etc/auto.home" >> /etc/auto.master.d/home.autofs  ### add autofs map
   echo "user -rw,sync server:/export/user" > /etc/auto.home  ### map user dir
   echo "* -rw,sync server:/export/&" > /etc/auto.home  ### map all dirs in /export/ dir
   echo "* -rw,sync server:/export/homes/&" > /etc/auto.home  ### map all dirs in /export/ dir

   systemctl restart autofs  ### restart autofs
   ```

When mounting home dircetory from network share set selinux boolean `setsebool -P use_nfs_home_dirs on`.

### 6.4. Extend existing logical volumes  

   ```bash
   lvextend -L +5G /dev/vgdata/lvdata  ### extend LV
   xfs_growfs /mnt/data  ### grow xfs filesystem
   resize2fs /dev/vg01/lv01 ## grow ext4 filesystem
   swapoff -v /dev/vg01/swap ## unmount swap
   lvextedn -L +1G /dev/vg01/swap ## extend swap partition
   mkswap /dev/vg01/swap ## repartition swap
   swapon /dev/vg01/swap ## mount swap
   ```

### 6.5. Diagnose and correct file permission problems  

   ```bash
   find /var/www -type f -exec chmod 644 {} \;  ### set permissions
   restorecon -Rv /var/www  ### restore SELinux context
   ```

## 7. Deploy, configure, and maintain systems  

### 7.1. Schedule tasks using at and cron

   ```bash
   # Example of job definition:
   # .---------------- minute (0 - 59)
   # |  .------------- hour (0 - 23)
   # |  |  .---------- day of month (1 - 31)
   # |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
   # |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
   # |  |  |  |  |
   # *  *  *  *  * user-name  command to be executed
   # 0/2 * * * * bob echo "evry two minut job"
   # 0/5 15-18 * * * 
   at 23:30 # interactive job, enter script then ctrl+D
   echo "test interactive job" | at 23:30
   crontab -e # edit cron of user running command
   crontab -l -u bob # show crontab of user bob
   crontab -e -u bob # as root edit bob crontab
   ls /etc/cron.d/ # custom cron jobs directory
   cat /etc/crontab > /etc/cron.d/custom # cat content of default crontab, then edit for your needs.
   echo "* * * * * command" | crontab - -u bob # overvrite crontab of user bob with pipline.
   ```

### 7.2. Start and stop services and configure services to start automatically at boot  

   ```bash
   systemctl enable --now crond  ### enable/start cron
   systemctl disable --now crond ### stop and disable cron
   systemctl disable firewalld  ### disable firewalld
   systemctl list-units --type=service|timer|socket --all # list all units of provided type
   systemctl list-unit-files --type=service|timer|socket # list all unit files of provided type
   systemctl status firewalld # show service status
   systemctl cat firewalld # show service file
   systemctl edit firewalld # edit service file
   systemctl reload sshd # reload service without stopping
   systemctl mask service_name # prevent starting or enabling service.
   systemctl list-dependencies --reverse NetworkManager.service
   ```

### 7.3. Configure systems to boot into a specific target automatically  

   ```bash
   systemctl set-default graphical.target  ### set default target
   systemctl get-default  ### show default target
   ```

### 7.4. Configure time service clients  

   ```bash
   tzselect # help select specific timezone.
   timedatectl list-timezones # list all available time zones
   timedatectl set-timezone America/New_York  ### set timezone
   timedatectl set-ntp true|false # on|off ntp, reqirements: chrony instaled.
   chronyc tracking  ### show chrony status
   chronyc sources -v # show chrony sync status
   ```

### 7.5. Install and update software packages from Red Hat Content Delivery Network, a remote repository, or from the local file system  

   ```bash
   dnf update --security  ### update security packages
   dnf install /tmp/package.rpm  ### install local rpm
   ```

### 7.6. Modify the system bootloader  

   ```bash
   man bootparam | man kernel-command-line # list of kernel arguments
   grubby --info ALL # list all avaible grub options
   grubby --default-index # get default grub index
   grubby --set-default-index 0 # set grub to use kernel form index
   grubby --update-kernel /boot/vmlinuz-6.12.0-55.9.1.el10_0.x86_64 --args="rhgb quiet" ## add  argument to kernel 
   grubby --update-kernel /boot/vmlinuz-6.12.0-55.9.1.el10_0.x86_64 --remove-args="rhgb quiet" ## remove argument from kernel 
   ```

## 8. Manage basic networking

### 8.1. Configure IPv4 and IPv6 addresses  

Always check autoconnect of connection profiles, new and old to preserver configuration during reboot.

   ```bash
   nmcli con show # show connection status 
   nmcli con show --active # show active connection status
   nmcli dev show # how network device status
   nmcli con add type ethernet con-name eth1 ifname eth1 ipv4.addresses 192.168.2.10/24 ipv4.dns 8.8.8.8 ipv4.gateway 192.168.2.1 ipv4.method manual  ### add connection
   nmcli con up eth1  ### bring up connection
   nmcli con mod eth1 +ipv4.addresses 192.168.2.11/24 connection.autoconnect yes ## modify connection, after modify run nmcli con up autoconnect is necessary to make setting persistent during reboot.
   nmcli con reload # reload network configuration.
   nmcli con reload eth1 # reload specific network configuration
   nmcli con del eth1 # remove specific network configuration
   nmcli gen permissions # show permissiong to setup network interfaces for command invoking user.
   ```

### 8.2. Configure hostname resolution  

   ```bash
   echo "192.168.2.100 server2" >> /etc/hosts  ### add host entry
   hostnamectl hostname server2.example.com  ### set hostname
   dig example.com # query DNS servers.
   host example.com # query DNS servers
   getent hosts example.com # query also /etc/hosts
   ```

### 8.3. Configure network services to start automatically at boot  

   ```bash
   systemctl enable --now NetworkManager  ### enable/start NetworkManager
   systemctl enable --now sshd  ### enable/start sshd
   ```

### 8.4. Restrict network access using firewalld and firewall-cmd  

   ```bash
   firewall-cmd --get-default-zone
   firewall-cmd --set-default-zone=dmz
   firewall-cmd --permanent --zone=internal --add-source=192.168.0.0./24 # allow trafic from network in zone 
   firewall-cmd --permament --zone=pubic --add-source=192.168.12.11/32 # allow trafic from single address.
   firewall-cmd --permament --zone=block --add-source=192.168.12.11/32 # block trafic from single address.
   firewall-cmd --permanent --zone=public --add-service=https  ### add https service
   firewall-cmd --permanent --zone=public --remove-service=ftp  ### remove ftp service
   firewall-cmd --reload  ### reload firewall, neccessary when using --permanent option.
   ```

## 9. Manage users and groups

### 9.1. Create, delete, and modify local user accounts  

   ```bash
   useradd -m -s /bin/bash alice  ### -m: create home; -s: shell
   usermod -L bob  ### -L: lock account
   userdel -r charlie  ### -r: remove home
   usermod -U
   usermod -aG group username 
   usermod -c "comment" username
   ```

### 9.2. Change passwords and adjust password aging for local user accounts  

   ```bash
   passwd --expire alice                # Force user 'alice' to change password at next login
   chage -d 0 alice                     # Set last password change date to 0 (forces password change at next login)
   chage -E 2025-12-31 bob              # Set account expiry date for 'bob' to December 31, 2025
   chage -m 0 -M 90 -W 7 -I 14 bob      # Set min days=0, max days=90, warn=7 days, inactive=14 days for 'bob'
   chage -E $(date -d "+30 days" +%F) bob # Set 'bob' account to expire in 30 days from today
   chage -l bob                         # List password aging and account expiry info for 'bob'
   usermod -L -e 2025-06-01 bob         # Lock 'bob' account and set expiry date to June 1, 2025
   passwd -l bob                        # Lock 'bob' account (disable password)
   cat /etc/login.defs                  # View default user account settings (UID ranges, password aging, etc.)
   cat /etc/security/pwquality.conf     # View password quality requirements (length, complexity, etc.)
   ```

### 9.3. Create, delete, and modify local groups and group memberships  

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

### 9.4. Configure superuser access  

   ```bash
   echo "alice ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers.d/alice  ### Allow user 'alice' to run any command as any user without password
   echo "%admin ALL=(ALL) ALL" > /etc/sudoers.d/admin           ### Allow all users in 'admin' group to run any command as any user (password required)
   user_name|%group_name HOSTS=(AS_USERS:AS_GROUPS) COMMANDS ### Sudoers syntax: specify user/group, hosts, run-as users/groups, and allowed commands
   ```

### 9.5. Change default user settings

   ```bash
   /etc/skel                # Directory containing default files for new user home directories files should have 644 perm
   /etc/login.defs          # Configuration file for user account creation defaults (UID ranges, password aging, etc.)
   /etc/secure/pwquality.conf # Password quality requirements (minimum length, complexity, etc.)
   ```

## 10. Manage security

### 10.1. Configure firewall settings using firewall-cmd/firewalld  

   ```bash
   firewall-cmd --permanent --add-rich-rule='rule family="ipv4" source address="192.168.1.0/24" service name="ssh" accept'  ### rich rule for ssh
   firewall-cmd --reload  ### reload firewall
   ```

### 10.2. Manage default file permissions  

```bash
umask 027  ### set default permissions
chmod -R o-rwx /home/alice  ### remove other access
```

| Umask Value | Default File Permissions | Default Directory Permissions | Description           |
| ----------- | ------------------------ | ----------------------------- | --------------------- |
| `0000`      | 666 (rw-rw-rw-)          | 777 (rwxrwxrwx)               | No restrictions       |
| `0022`      | 644 (rw-r--r--)          | 755 (rwxr-xr-x)               | Others cannot write   |
| `0027`      | 640 (rw-r-----)          | 750 (rwxr-x---)               | Others have no access |
| `0077`      | 600 (rw-------)          | 700 (rwx------)               | Only owner has access |

*Umask subtracts permissions from the default (666 for files, 777 for directories).*

**Set default umask for all users:**  

- Edit `/etc/profile` and add or modify the line:  

   ```bash
   umask 027
   ```

   This sets the default umask for all users on login.

**Set default umask for a specific user:**  

- Add or modify the `umask` line in the user's shell startup file (e.g., `~/.bashrc`, `~/.bash_profile`, or `~/.profile`):  

   ```bash
   umask 027
   ```

   This sets the default umask only for that user.

### 10.3. Configure key-based authentication for SSH  

   ```bash
   ssh-keygen -t ed25519 -C "alice@server"  ### generate key; -t: type; -C: comment
   ssh-copy-id -i ~/.ssh/id_ed25519.pub user@host  ### copy key to host
   ```

### 10.4. Troubleshoot Selinx

   ```bash
   tail /var/log/messages | grep -C 3 -i selinux
   tail /var/log/audit/audit.log | grep -C 3 -i selinux
   sealert -f /var/log/audit/audit.log
   ausearch -m AVC -ts recent
   ```

### 10.5. Set enforcing and permissive modes for SELinux  

   ```bash
   setenforce 0  ### set permissive mode --temporary
   getenforce
   sed -i 's/^SELINUX=.*/SELINUX=permissive/' /etc/selinux/config  ### change config
   ```

### 10.6. List and identify SELinux file and process context  

   ```bash
   ls -lZ /var/www/html  ### show SELinux context
   ps -eZ | grep httpd  ### show process context
   semanage fcontext -l # list all file labels
   semanage fcontext -a -t httpd_sys_content_t '/virtual(/.*)?'
   restorecon -RFvv /virtual # restore contest recursiviely on directory
   semanage fcontext -l -C # list changes to default policy
   ```

### 10.7. Restore default file contexts  

   ```bash
   restorecon -Rv /var/www/html  ### restore context; -R: recursive; -v: verbose
   ```

### 10.8. Manage SELinux port labels  

   ```bash
   semanage port -l # list all port labels
   semanage port -a -t ssh_port_t -p tcp 2222  ### -a: append (add); -t: type; -p: protocol
   semanage port -d -t http_port_t -p tcp 8080  ### -d: delete; -t: type; -p: protocol
   semanage port -m -t http_port_t -p tcp 71 # we have to use this command if port 71 is assigned to other policy.
   semanage port -l -C # list changes to default policy
   ```

### 10.9. Use boolean settings to modify system SELinux settings  

   ```bash
   getsebool -a # list all avaible boolean policies
   setsebool -P httpd_can_sendmail on  ### -P: persistent; set boolean
   getsebool httpd_can_sendmail  ### get boolean value
   ```
