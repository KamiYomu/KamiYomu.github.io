---
title: Install via Linux
parent: Getting Started
nav_order: 1
---

# Install via Linux (Shell)

Follow the steps below to install **KamiYomu** on Linux.

## 0. Update packages and index and install additional packages

Before proceeding with the installation, update your package manager and packages. Use the appropriate command for your Linux distribution:

**For Debian/Ubuntu/Mint/PopOs:**

```sh
sudo apt-get update
```

**For Fedora/RHEL/CentOS:**

```sh
sudo dnf update
```

Now, install the `jq` service into your system

```sh
sudo apt-get install -y jq 
```



## 1. Download the Installer Script

Download the Bash installation script:

https://raw.githubusercontent.com/KamiYomu/KamiYomu/refs/heads/main/installation/linux/install.sh

Alternatively, save the file from:

`installation/linux/install.sh`

<img src="{{ '/assets/images/install/linux/install-script-downloaded.png' | relative_url }}" height="300"/>

## 2. Open a Terminal

Open your preferred terminal application.

## 3. Navigate to the Script Location

Change to the directory where you downloaded `install.sh`.

For example, if the file is in your **Downloads** folder:

```bash
cd ~/Downloads
```

<img src="{{ '/assets/images/install/linux/shell-navigate-download.png' | relative_url }}" height="300"/>

## 4. Make the Script Executable

Grant execution permissions to the installer:

```bash
chmod +x ./install.sh
```

<img src="{{ '/assets/images/install/linux/shell-makes-executable.png' | relative_url }}" height="300"/>

## 5. Run the Installer

Execute the installation script:

```bash
sudo ./install.sh
```

## 6. Select the Version

When prompted, enter the version you want to install.

- Press **Enter** to install the latest available version.

<img src="{{ '/assets/images/install/linux/shell-install-kamiyomu-select-version.png' | relative_url }}" height="300"/>

## 7. Select the Package

Choose the package that matches your Linux system.

For most modern 64-bit Linux distributions, **linux-x64** is the correct choice.

<img src="{{ '/assets/images/install/linux/shell-install-kamiyomu-select-package.png' | relative_url }}" height="300"/>

## 8. Wait for the Installation to Complete

The installer will download the required files and configure KamiYomu automatically.

## 9. Open KamiYomu

Once the installation finishes, open your browser and navigate to:

`http://localhost:8080`

If the installation completed successfully, the KamiYomu web interface should be available.

<img src="{{ '/assets/images/install/linux/kamiyomu-home-page.png' | relative_url }}" height="300"/>

<img src="{{ '/assets/images/install/linux/kamiyomu-system-page.png' | relative_url }}" height="300"/>