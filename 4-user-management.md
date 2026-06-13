# User Management in Linux

### Introduction to User Management in Linux

Linux is a multi-user operating system, meaning multiple users can operate on a system simultaneously.

Proper user management ensures:
- Security
- Controlled access
- System integrity

---

### Important Files

| File | Purpose |
|--------|---------|
| `/etc/passwd` | Stores user account details |
| `/etc/shadow` | Stores encrypted user passwords |
| `/etc/group` | Stores group information |
| `/etc/gshadow` | Stores secure group details |

---

## Creating Users in Linux

### Using `useradd`

Create a user without a home directory:

```bash
useradd username
```

Create a user with a home directory:

```bash
useradd -m username
```

Create a user with a specific shell:

```bash
useradd -s /bin/bash username
```

---

### Using `adduser` (Debian/Ubuntu)

```bash
adduser username
```

This interactive command:
- Creates the user
- Creates a home directory
- Sets a password
- Prompts for additional information

---

## Managing User Passwords

### Set or Change Password

```bash
passwd username
```

---

### Password Expiration

Set password expiration to 90 days:

```bash
chage -M 90 username
```

---

### Lock User Account

```bash
passwd -l username
```

---

### Unlock User Account

```bash
passwd -u username
```

---

## Modifying Users

### Change Username

```bash
usermod -l new_username old_username
```

---

### Change Home Directory

```bash
usermod -d /new/home/directory -m username
```

---

### Change Default Shell

```bash
usermod -s /bin/zsh username
```

---

## Deleting Users

### Delete User Only

```bash
userdel username
```

Removes:
- User account

Keeps:
- Home directory

---

### Delete User and Home Directory

```bash
userdel -r username
```

Removes:
- User account
- User home directory

---

## Working with Groups

### Create Group

```bash
groupadd groupname
```

---

### Add User to Group

```bash
usermod -aG groupname username
```

---

### View User Groups

```bash
groups username
```

Example:

```text
sainikhil sudo docker developers
```

---

### Change Primary Group

```bash
usermod -g new_primary_group username
```

---

## Sudo Access and Privilege Escalation

### Add User to Sudo Group (Ubuntu/Debian)

```bash
usermod -aG sudo username
```

---

### Add User to Wheel Group (RHEL/CentOS)

```bash
usermod -aG wheel username
```

---

## Grant Specific Commands with Sudo

Edit sudoers file:

```bash
visudo
```

Add:

```text
username ALL=(ALL) NOPASSWD: /path/to/command
```

Example:

```text
sainikhil ALL=(ALL) NOPASSWD: /usr/bin/systemctl
```

---

## Useful User Management Commands

### Check Current User

```bash
whoami
```

---

### Check User Information

```bash
id
```

---

### Check Current Home Directory

```bash
echo $HOME
```

---

### List All Users

```bash
cat /etc/passwd
```

---

### List Usernames Only

```bash
cut -d: -f1 /etc/passwd
```

---

### Show Logged-In Users

```bash
who
```

---

### Show Login History

```bash
last
```

---

## Common User Management Workflow

### Create User

```bash
sudo adduser devuser
```

---

### Add User to Sudo Group

```bash
sudo usermod -aG sudo devuser
```

---

### Verify User Groups

```bash
groups devuser
```

---

### Switch User

```bash
su - devuser
```

---

### Return to Previous User

```bash
exit
```

---

# Summary

| Task | Command |
|--------|---------|
| Create User | `adduser username` |
| Delete User | `userdel username` |
| Delete User + Home | `userdel -r username` |
| Change Password | `passwd username` |
| Lock User | `passwd -l username` |
| Unlock User | `passwd -u username` |
| Create Group | `groupadd groupname` |
| Add User to Group | `usermod -aG groupname username` |
| Add User to Sudo | `usermod -aG sudo username` |
| Switch User | `su - username` |
| Check Current User | `whoami` |
| Show User Info | `id` |