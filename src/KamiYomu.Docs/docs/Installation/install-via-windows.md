---
title: Install via Windows
parent: Getting Started
nav_order: 1
---

# Install via Windows (PowerShell)

## Minimal Requirements

- Windows 10

Follow the steps below to install **KamiYomu** on Windows.

## 1. Download the Installer Script

Download the PowerShell installation script:

https://raw.githubusercontent.com/KamiYomu/KamiYomu/refs/heads/main/installation/windows/install.ps1

Alternatively, save the file from:

`installation/windows/install.ps1`

<img src="{{ '/assets/images/install/windows/install-script-downloaded.png' | relative_url }}" height="300"/>

## 2. Open PowerShell as Administrator

Right-click **PowerShell** and select **Run as administrator**.

<img src="{{ '/assets/images/install/windows/powershell-as-admin.png' | relative_url }}" height="300"/>

## 3. Navigate to the Script Location

Change to the directory where you downloaded `install.ps1`.

For example, if the file is in your **Downloads** folder:

```powershell
cd ~/Downloads
```


<img src="{{ '/assets/images/install/windows/powershell-navigate-download.png' | relative_url }}" height="300"/>

## 4. Unblock the Script

Windows may block scripts downloaded from the internet. Run:

```powershell
Unblock-File .\install.ps1
```

<img src="{{ '/assets/images/install/windows/powershell-unblock-file.png' | relative_url }}" height="300"/>


## 5. Run the Installer

Enable the script policy for running on Current User

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
```

Then select `A`

<img src="{{ '/assets/images/install/windows/powershell-execution-policy.png' | relative_url }}" height="300"/>


Execute the installation script:

```powershell
.\install.ps1
```

## 6. Select the Version

When prompted, enter the version you want to install.

- Press **Enter** to install the latest available version.

<img src="{{ '/assets/images/install/windows/powershell-install-kamiyomu-select-version.png' | relative_url }}" height="300"/>

## 7. Select the Package

Choose the package that matches your Windows system.

For most modern 64-bit Windows installations, **win-x64** is the correct choice.

<img src="{{ '/assets/images/install/windows/powershell-install-kamiyomu-select-package.png' | relative_url }}" height="300"/>

## 8. Wait for the Installation to Complete

The installer will download the required files and configure KamiYomu automatically.

<img src="{{ '/assets/images/install/windows/powershell-install-kamiyomu-package-download.png' | relative_url }}" height="300"/>

## 9. Open KamiYomu

Once the installation finishes, open your browser and navigate to:

`http://localhost:8080`

If the installation completed successfully, the KamiYomu web interface should be available.

<img src="{{ '/assets/images/install/windows/powershell-installation-completed.png' | relative_url }}" height="300"/>

<img src="{{ '/assets/images/install/windows/kamiyomu-home-page.png' | relative_url }}" height="300"/>

<img src="{{ '/assets/images/install/windows/kamiyomu-system-page.png' | relative_url }}" height="300"/>

# Windows Service

After the installation, KamiYomu will be available in the program files (`C:\Program Files\KamiYomu\win-x64`) also, it is registered as Windows Service with Name 

<img src="{{ '/assets/images/install/windows/kamiyomu-windows-service.png' | relative_url }}" height="300"/>





