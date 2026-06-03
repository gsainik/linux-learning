# WSL Ubuntu Installation and Usage

## Install WSL Ubuntu

Open:
- Command Prompt
- PowerShell

Run:

```powershell
wsl --install
```

This installs:
- WSL
- Ubuntu Linux

---

## First Login

After installation, Ubuntu opens like:

```bash
sainikhil@SaiNikhil:~$
```

This means:
- `sainikhil` → Linux username
- `SaiNikhil` → Machine name
- `$` → Normal user

---

## Switch to Root User

Run:

```bash
sudo su
```

Now prompt becomes:

```bash
root@SaiNikhil:~#
```

Meaning:
- `root` → Administrator user
- `#` → Root/admin prompt

---

## Return Back to Normal User

Run:

```bash
exit
```

Prompt changes back to:

```bash
sainikhil@SaiNikhil:~$
```

---

# Open Linux in Another Terminal Tab

## Method 1

In Windows Terminal:
- Click dropdown arrow (`▼`)
- Select:

```text
Ubuntu
```

---

## Method 2

Open Windows Search and search:

```text
Ubuntu
```

Open the installed Ubuntu application.

---

# Install Packages

If you are normal user:

```bash
apt install python3
```

will fail with permission denied.

Use:

```bash
sudo apt install python3
```

OR switch to root user first:

```bash
sudo su
apt install python3
```

---

# Common Commands

## Update Package List

```bash
sudo apt update
```

## Upgrade Packages

```bash
sudo apt upgrade
```

## Install Package

```bash
sudo apt install git
```

---

