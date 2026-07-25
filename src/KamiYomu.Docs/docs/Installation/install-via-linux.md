---
title: Install via Linux
parent: Getting Started
nav_order: 1
---

# Install via Linux (Shell)

Follow the steps below to install **KamiYomu** on Linux.

## Update packages and install required tools

Before proceeding with the installation, update your package manager and install `jq`, which is required by the installer.

**For Debian/Ubuntu/Mint/Pop!_OS:**

```sh
sudo apt-get update
sudo apt-get install -y jq
```

**For Fedora/RHEL/CentOS:**

```sh
sudo dnf update
sudo dnf install -y jq
```

If `jq` is already installed, you can skip the installation step.

## Download the installer script

Download the Bash installation script from the repository:

[Linux Install Script](https://raw.githubusercontent.com/KamiYomu/KamiYomu/refs/heads/main/installation/linux/install.sh)

You can download it manually or with `curl`:

```sh
curl -o install.sh https://raw.githubusercontent.com/KamiYomu/KamiYomu/refs/heads/main/installation/linux/install.sh
```

<img src="{{ '/assets/images/install/linux/install-script-downloaded.png' | relative_url }}" height="300"/>

## Open a terminal

Open your preferred terminal application.

## Navigate to the script location

Change to the directory where you downloaded `install.sh`.

For example, if the file is in your **Downloads** folder:

```bash
cd ~/Downloads
```

<img src="{{ '/assets/images/install/linux/shell-navigate-download.png' | relative_url }}" height="300"/>

## Make the script executable

Grant execution permissions to the installer:

```bash
chmod +x ./install.sh
```

<img src="{{ '/assets/images/install/linux/shell-makes-executable.png' | relative_url }}" height="300"/>

## Run the installer

Execute the installation script:

```bash
sudo ./install.sh
```

## Select the version

When prompted, enter the version you want to install.

- Press **Enter** to install the latest available version.

<img src="{{ '/assets/images/install/linux/shell-install-kamiyomu-select-version.png' | relative_url }}" height="300"/>

## Select the package

Choose the package that matches your Linux system.

For most modern 64-bit Linux distributions, **linux-x64** is the correct choice.

<img src="{{ '/assets/images/install/linux/shell-install-kamiyomu-select-package.png' | relative_url }}" height="300"/>

## Wait for the installation to complete

The installer will download the required files and configure KamiYomu automatically.

## Open KamiYomu

Once the installation finishes, open your browser and navigate to:

`http://localhost:8080`

If the installation completed successfully, the KamiYomu web interface should be available.

<img src="{{ '/assets/images/install/linux/kamiyomu-home-page.png' | relative_url }}" height="300"/>

<img src="{{ '/assets/images/install/linux/kamiyomu-system-page.png' | relative_url }}" height="300"/>

## Manage the KamiYomu service

If KamiYomu is running as a systemd service, you can stop, restart, or check its status.

Stop the service:

```sh
sudo systemctl stop kamiyomu.service
```

Restart the service after making changes:

```sh
sudo systemctl restart kamiyomu.service
```

Check service status:

```sh
sudo systemctl status kamiyomu.service
```

## Edit appsettings.json

If you need to update application settings, edit the file at:

`/opt/KamiYomu/linux-x64/appsettings.json`

{% capture appsettings_note %}
{% include note-appsettings-example.md %}
{% endcapture %}
{{ appsettings_note | markdownify }}

