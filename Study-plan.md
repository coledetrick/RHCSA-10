I took v10.

For study materials, primarily I used Sander's materials on O'Reilly. Outside of Sanders, I used old v9 materials.

- Sander's course: https://learning.oreilly.com/course/red-hat-rhcsa/9780135493137/
- Asghar's Book: https://learning.oreilly.com/library/view/rhcsa-red-hat/9781835887325/
- KodeKloud: RHCSA course (this course I went through to get familiar with Linux - months before even thinking of taking this exam) - I recommend using Sander's course over these guys for the actual exam.
- Git repo: https://github.com/ive663/RHCSA
I was a pretty casual Linux user for awhile, but got fairly comfortable with bash scripting and odd things via kodekloud & their labs.
- In terms of study prep for the exam, I took about 2 months and some change to study until I felt comfortable. (I booked while still feeling uncertain! But just had to give it a try)
- I have a small home lab with proxmox I used to spin up some RHEL vm's and follow long Sander's course. I would say once you can finish Sander's practice exam with just man pages, book it and polish on parts you feel 'slow' on. Know how to find the information you need with man pages! Get a little familiar with vim (deleting, copying, pasting, jumping around etc..).
- Their environment is a little janky, for example I couldn't use multiple tmux windows within their environment. But honestly I didn't end up needing it and crushed the tasks within an hour, taking another hour to double check things.

WEEK 1 — Core Linux & System Basics

Goal: Absolute comfort with the shell, files, permissions, help system

Day 1 – Environment & Exam Familiarity
Install RHEL 10 (2 VMs if possible)
Snapshot baseline system
Review RHCSA exam objectives
Learn to use:
man
info
/usr/share/doc


📘 Ghori: Intro + Exam Overview
🎥 Sander: Course intro + shell basics

Day 2 – Files & Directories

Navigate filesystem efficiently

Create, copy, move, delete files

Hard vs soft links

Commands to drill:

ls find locate
cp mv rm
ln ln -s


Lab

Recreate directory trees from memory

Find files by size, owner, permissions

Day 3 – Permissions & Ownership

Standard permissions

Numeric vs symbolic modes

Default permissions (umask)

chmod chown chgrp umask


Lab

Create shared directories with correct permissions

Fix broken access issues

Day 4 – ACLs & Special Permissions

ACLs (getfacl, setfacl)

SUID, SGID, sticky bit

Lab

Give users temporary access without changing ownership

Test inheritance behavior

Day 5 – Users & Groups

Create users/groups

Password policies

Account expiration

useradd usermod groupadd
passwd chage


Lab

Lock/unlock users

Enforce password aging

Day 6 – Sudo & Environment Profiles

Configure sudo safely

/etc/profile, .bashrc

visudo


Lab

Give limited sudo access

Verify security boundaries

Day 7 – Review + Mini Mock

Rebuild:

Users

Permissions

ACLs

Timed practice (90 minutes)

No notes

WEEK 2 — Storage, LVM, and Boot

Goal: Storage tasks become automatic

Day 8 – Disk & Partitioning

Identify disks

Create partitions

lsblk blkid parted

Day 9 – LVM (Core Exam Topic)

PV → VG → LV workflow

pvcreate vgcreate lvcreate


Lab

Create LVM

Format & mount it

Day 10 – Filesystems & Mounting

xfs vs ext4

Persistent mounts

mkfs mount umount
/etc/fstab


Lab

Break /etc/fstab

Fix system boot

Day 11 – LVM Resizing & Swap

Extend LVs

Create swap

lvextend resize2fs xfs_growfs
mkswap swapon

Day 12 – Boot Process & GRUB

Understand boot stages

Reset root password

Lab

Break root password

Recover via GRUB

Day 13 – Rescue & Emergency Mode

Fix boot failures

Recover from bad configs

Day 14 – Storage Review

Timed lab:

Create LVM

Resize it

Persist mounts

Reboot to verify

WEEK 3 — Services, Networking, SELinux

Goal: Troubleshooting confidence

Day 15 – Systemd & Services

Start/stop/enable services

Analyze failures

systemctl journalctl

Day 16 – Networking

Static IPs

Hostnames

Ports

nmcli ip ss hostnamectl


Lab

Configure networking without reboot

Day 17 – Package Management

Install/remove packages

Work with repos

dnf repolist provides

Day 18 – SELinux (High Value Topic)

Modes & contexts

Boolean management

getenforce setenforce
semanage restorecon


Lab

Fix SELinux-blocked service without disabling it

Day 19 – Scheduled Tasks

Cron & at

crontab at

Day 20 – Logging & Troubleshooting

System logs

Service failures

journalctl /var/log

Day 21 – Full Mock Lab

2.5–3 hours

No notes

Reboot at end

WEEK 4 — Exam Conditioning

Goal: Speed, accuracy, confidence

Day 22 – Weak Area Review

Identify slow topics

Repeat labs

Day 23 – Full Practice Exam

Simulate exam conditions

Score yourself honestly

Day 24 – Fix What You Missed

Re-do failed tasks twice

Day 25 – Speed Drills

LVM creation in under 10 minutes

Network config in under 5 minutes

User + sudo setup in under 5 minutes

Day 26 – SELinux & Boot Drill

3 SELinux issues back-to-back

2 boot recovery scenarios

Day 27 – Final Mock Exam

Treat it like the real thing

Minimal stress, maximum focus

Day 28 – Light Review

Read notes only

No heavy labs

Day 29 – Rest & Confidence

Very light practice

Sleep well

Day 30 – Exam Day

Calm

Methodical

Verify everything

Reboot when safe

Pro Exam Tips (Critical)

Persistence > correctness

Always verify:

systemctl status
mount -a
getenforce


Don’t panic — partial credit saves passes
