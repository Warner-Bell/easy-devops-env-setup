# Setting Up a Basic Dev Environment on a Windows\Linux Machine
---

# 🚀 Set Up Your Dev Environment

Welcome to your step-by-step guide for setting up a **powerful development environment** using **Windows Subsystem for Linux (WSL)**, **Visual Studio Code (VSCode)**, and essential tools like **Git** and **Node Version Manager (NVM)**.

---

## 📑 **Table of Contents**

1. [💻 IDE - Install Visual Studio Code (VSCode)](#ide---install-visual-studio-code-vscode)
2. [🔧 Configure VSCode for Development](#configure-vscode-for-development)
3. [🐧 WSL - Setting Up Ubuntu and Updating Linux Kernel](#wsl---setting-up-ubuntu-and-updating-linux-kernel)
4. [🛠️ Essential Dev Tools](#essential-dev-tools)
5. [🐍 Python and pip](#python-and-pip)
6. [⚡ Git - Installation and Configuration](#git---installation-and-configuration)
7. [🔑 Git Credential Manager (GCM)](#git-credential-manager-gcm)
8. [🔒 Configure Security Settings](#configure-security-settings)
9. [🎉 Final Congratulations](#final-congratulations)

---

## 💻 IDE - Install Visual Studio Code (VSCode)

VSCode is a **crucial tool** for development. Let's get it installed and ready!

### 🔽 **Steps to Install VSCode:**

1. **Download VSCode:** Visit [Visual Studio Code](https://code.visualstudio.com/Download) and download the Windows installer.
2. **Run the Installer:** Double-click the downloaded file and follow the instructions. Check the options to:
    - Add VSCode to the PATH.
    - Create a desktop icon for quick access.
  
### 🚀 **Install VSCode Using PowerShell CLI:**

```
$InstallerUrl = "https://code.visualstudio.com/sha/download?build=stable&os=win32-x64-user"
$InstallerPath = "$env:TEMP\VSCodeInstaller.exe"
Invoke-WebRequest -Uri $InstallerUrl -OutFile $InstallerPath
Start-Process -FilePath $InstallerPath -ArgumentList "/verysilent" -NoNewWindow -Wait
Remove-Item $InstallerPath
```

### 🚀 **Install VSCode Using Linux CLI:**

```bash
sudo apt install curl gpg
curl -fsSL https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o /usr/share/keyrings/ms.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/ms.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
sudo apt update
sudo apt install code
```

> After installing, launch VSCode by typing `code` in your terminal.

---

## 🔧 Configure VSCode for Development

### 🛠️ **Steps to Configure VSCode:**

1. **Open VSCode:** Launch VSCode from your **Start Menu** or **Desktop Icon**.
2. **Install Extensions:** Go to the Extensions Marketplace by pressing `Ctrl+Shift+X`. Recommended extensions:
   - 🔗 **Remote Development** – for remote development within WSL.
   - 🐍 **Python** – for Python development.
   - 🧩 **GitLens** – enhances Git capabilities.
   - 🐳 **Docker** – for containerization.
   - ✨ **ESLint** – for JavaScript development.
   - 📜 **YAML** – for YAML language support.
   - 💻 **Live Share** – for collaborative coding.
   - 🔐 **Remote - SSH** – to connect via SSH to remote servers.

---

## 🐧 WSL - Setting Up Ubuntu

Build a **robust foundation** by setting up **WSL** and **Ubuntu** on your Windows machine.

### 🛠️ **Steps to Install WSL & Ubuntu:**

1. **Install WSL Ubuntu:**
   - In VSCode Open a **PowerShell** terminal and enter:
     ```bash
     wsl --install -d Ubuntu
     ```
   - Click Yes if prompted to allow program to make changes, view install progress in terminal.
   - Wait for the installation to complete, 
   - Reboot your machine. (a terminal window will open upon reboot)
   - In the terminal window type a username when prompted (all lowercase), enter a password wait for the process to complete then close the window.

2. **Update Linux Packages:**
   - Now that WSL is up and running, we need to ensure our Linux packages are up-to-date. 
   - Open VSCode open your Ubuntu(WSL) terminal and run:
     ```bash
     sudo apt update && sudo apt upgrade -y
     ```
---

## 🛠️ Essential Dev Tools

To build high-quality software, install these **essential tools**:

```
sudo apt-get install wget ca-certificates curl
```

### 🚀 **Node Version Manager (NVM):**

Manage your Node.js versions efficiently with NVM:

```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/master/install.sh | bash
```

---

## 🐍 Python and pip

Python is an essential tool for cloud development. Install **Python** and **pip** with:

```
sudo apt install python3-pip -y
```

### ✅ **CFN-Lint (CloudFormation Linter):**

Ensure quality in your CloudFormation templates:

```
pip3 install cfn-lint
```

> Don't forget to install the **CloudFormation Linter** extension in VSCode!

### 🔧 jq (Command-line JSON processor):
jq is a lightweight command-line JSON processor, essential for parsing and manipulating JSON data:

```
sudo apt-get install jq
```
---

## 💽 Install Database Tools (if needed)
If your development requires a database, install the appropriate database. For example, for MySQL:
1.	Download MySQL: Go to the MySQL Downloads page and select the Windows version.
2.	Install MySQL: Follow the setup wizard, set up your root password, and configure the server.

---

## ⚡ Git - Installation and Configuration

Git is essential for **version control**. Install and configure Git with the following:

### 🛠️ **Install Git:**

```
sudo apt-get install git
```

### 🧑‍💻 **Configure Git Identity:**

```
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

### 🔍 **View Git Configuration:**

```
git config --list
```

### Install Git CLI

```
sudo apt install gh
```

---

## 🔑 Git Credential Manager (GCM)

**Git Credential Manager (GCM)** simplifies authentication for Git services like **GitHub** and **Azure DevOps**.

### 💡 **Setting Up GCM in WSL:**

Set up GCM within WSL:
   ```
   git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/bin/git-credential-manager.exe"
   ```

---

## 🔒 Configure Security Settings

### 🔧 **Steps to Secure Your System:** ### (Optional)

1. **Windows Security:** Ensure **Windows Defender** or your preferred antivirus is active and updated.
2. **Firewall Settings:** Configure your **Windows Firewall** to allow development tools while blocking unauthorized access.
3. **Secure Browsers:** Install security extensions like **HTTPS Everywhere** and ensure your browsers are up to date.
4. **Regular Updates:** Keep **Windows OS**, **VSCode**, and all installed packages/extensions updated.

---

## 🎉 Final Congratulations

You now have a **fully configured, secure development environment** on your Windows machine using **WSL**, **VSCode**, **Git**, and other standard development tools. You're ready for cloud development and ensuring your **CloudFormation templates** are linted before merging into the main branch.

**Happy Coding!** 💻🌐

