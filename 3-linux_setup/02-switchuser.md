# Switching Between Normal User and Root User

## Current Normal User

When logged in normally:

```bash
sainikhil@SaiNikhil:~$
```

Meaning:
- `sainikhil` → Normal Linux user
- `$` → Normal user shell

---

## Switch to Root User

Run:

```bash
sudo su
```

Now prompt becomes:

```bash
root@SaiNikhil:/home/sainikhil#
```

Meaning:
- `root` → Administrator user
- `#` → Root shell

At this point, you are still standing inside:

```text
/home/sainikhil
```

which is the normal user's home directory.

---

## Move to Root Home Directory

Run:

```bash
cd ~
```

For root user:

```text
~
```

means:

```text
/root
```

Now prompt becomes:

```bash
root@SaiNikhil:~#
```

---

## Verify Current Directory

Run:

```bash
pwd
```

Output:

```text
/root
```

---

## Switch Back to Normal User

Run:

```bash
exit
```

Prompt becomes:

```bash
sainikhil@SaiNikhil:/home/sainikhil$
```

---

## Return to Normal User Home Directory

Run:

```bash
cd ~
```

Now prompt becomes:

```bash
sainikhil@SaiNikhil:~$
```

For normal user:

```text
~
```

means:

```text
/home/sainikhil
```

---

## Important Symbols

| Symbol | Meaning |
|---|---|
| `$` | Normal user |
| `#` | Root user |

---

## Home Directories

| User | Home Directory |
|---|---|
| `sainikhil` | `/home/sainikhil` |
| `root` | `/root` |



# Linux User Home Directories

## Linux Directory Structure

```text
/home
   ├── sainikhil
   ├── devuser
   └── testuser

/root
```

---

## Explanation

| Directory | Purpose |
|---|---|
| `/home` | Contains home directories for normal users |
| `/home/sainikhil` | Home directory of user `sainikhil` |
| `/home/devuser` | Home directory of user `devuser` |
| `/root` | Home directory of root user |

---

## Create New User

```bash
sudo adduser devuser
```

Linux automatically creates:

```text
/home/devuser
```

---

## Check All Normal Users

```bash
ls /home
```

Example Output:

```text
sainikhil
devuser
testuser
```

---

## Check Current User

```bash
whoami
```

---

## Check Current Home Directory

```bash
echo $HOME
```

Example Output:

```text
/home/sainikhil
```

For root user:

```text
/root
```

---

## Important Difference

| User Type | Home Directory |
|---|---|
| Normal User | `/home/username` |
| Root User | `/root` |

---

## Home Directory Shortcut

```bash
~
```

Represents the current user's home directory.

Examples:

| User | `~` Means |
|---|---|
| `sainikhil` | `/home/sainikhil` |
| `root` | `/root` |


# Why cant we use ```sudo su``` to switch from root to normal user?

## Return From Root to Normal User

Run:

```bash
exit
```

Prompt changes back:

```bash
sainikhil@SaiNikhil:~$
```

---

## Why `exit`?

When you run:

```bash
sudo su
```

Linux opens a new root shell/session on top of your current user session.

Visual understanding:

```text
Normal User Shell
    ↓
sudo su
    ↓
Root Shell Opened
```

To close the root shell and return to previous shell:

```bash
exit
```

---

## Can We Use `sudo su` Again to Return?

No.

Because:

```bash
sudo su
```

always means:

```text
"Become root user"
```

It does NOT mean:
```text
"Go back to previous user"
```

So inside root, running:

```bash
sudo su
```

simply keeps you as root.

---

## Quick Summary

| Action | Command |
|---|---|
| User → Root | `sudo su` |
| Root → User | `exit` |

---

## Alternative Root Command

Instead of:

```bash
sudo su
```

You can also use:

```bash
sudo -i
```

Both open root shell.

# Difference Between `echo $HOME` and `pwd`

| Command | Meaning | Purpose |
|---|---|---|
| `echo $HOME` | Shows user's home directory | Displays default home path |
| `pwd` | Print Working Directory | Shows current directory |
