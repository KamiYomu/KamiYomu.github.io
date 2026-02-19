---
title: Development
nav_order: 5
---

## 🚀 Setting Up .NET 8 & Global Tools

This guide covers the installation of the **.NET 8 SDK (LTS)** and **LibMan**, the lightweight library manager used for KamiYomu's client-side assets.

### 1. Install the .NET 8 SDK
The SDK (Software Development Kit) is required to build, run, and publish .NET applications.

* **Official Download**: Visit the [Download .NET 8.0](https://dotnet.microsoft.com/en-us/download/dotnet/8.0) page.
* **Platform Instructions**: 
    * **Windows**: Download the **x64** or **Arm64** installer.
    * **macOS**: Choose **Arm64** (Apple Silicon) or **x64** (Intel).
    * **Linux**: Use your package manager (e.g., `sudo apt-get install -y dotnet-sdk-8.0`).
* **Verify**: Open your terminal (PowerShell, CMD, or Bash) and run:
    ```bash
    dotnet --version
    ```
    *You should see a version starting with `8.0.x` (e.g., `8.0.400`).*

---

### 2. Install LibMan (Library Manager)
KamiYomu uses **LibMan** to handle frontend dependencies. It must be installed as a global tool to be accessible via the command line.

* **Install Command**:
    ```bash
    dotnet tool install -g Microsoft.Web.LibraryManager.Cli
    ```
* **Verify Installation**:
    ```bash
    libman --version
    ```

> { .Important } 
> If the `libman` command is not recognized after installation, restart your terminal. If the issue persists, ensure your .NET tools directory is in your system's `PATH`:
> * **Windows**: `%USERPROFILE%\.dotnet\tools`
> * **macOS/Linux**: `$HOME/.dotnet/tools`
> { .Important } 

---

### 3. Basic LibMan Usage in KamiYomu
Once installed, you can manage the project's client-side dependencies from the root directory:

* **Restore libraries**: `libman restore` (Downloads everything listed in `libman.json`).
* **Add a new library**: `libman install <library-name> --provider cdnjs`.
* **Clean files**: `libman clean`.

---

### 4. Useful Diagnostics
If you need to check your environment setup, use these commands:

| Command | Purpose |
| :--- | :--- |
| `dotnet --list-sdks` | Shows all installed SDK versions. |
| `dotnet --info` | Displays detailed info about your OS and .NET environment. |
| `dotnet tool list -g` | Lists all globally installed .NET tools. |



### 5. [LiteDB Studio](https://github.com/litedb-org/LiteDB.Studio)
A powerful Graphical User Interface (GUI) designed for viewing, querying, and editing **LiteDB v5** documents. 

* **Why use it?**: It provides a SQL-like console to run commands, explore collections, and manage your local data storage visually.
* **Compatibility**: Native support for the LiteDB storage engine used in the project.
* **License**: Free and Open Source.

### 6. [Thorium Reader](https://github.com/edrlab/thorium-reader)

A modern, highly accessible desktop reading application for Windows, macOS, and Linux. It is the recommended tool for testing and consuming the **KamiYomu OPDS feed**.
* **License**: Free and Open Source.

---