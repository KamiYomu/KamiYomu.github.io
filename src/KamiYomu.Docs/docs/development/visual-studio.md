---
title: Visual Studio Setup
parent: Development
nav_order: 3
---

# Visual Studio Setup

## Requirements
- Docker: [Download here](https://www.docker.com/get-started)
- Visual Studio: [Download here](https://visualstudio.microsoft.com/downloads/)
- .NET 8 SDK: [Download here](https://dotnet.microsoft.com/en-us/download/dotnet/8.0)

{% capture clone_repo_note %}
{% include note-clone-repo.md %}
{% endcapture %}
{{ clone_repo_note | markdownify }}

- Open the solution in Visual Studio in `/src/KamiYomu.sln`
- Right-Click on the `libman.json`, then click on `Restore Client-Side Libraries`
- Set `docker-compose` project as **startup project** (Right-click on `docker-compose` project, select `Set As Startup Project.`).
- Run it (press `F5`)

## 🛠️ Additional Tools

To streamline your development workflow with KamiYomu, we recommend the following utilities:

### [ResX Resource Manager](https://github.com/dotnet/ResXResourceManager)
A powerful, open-source tool for managing **Internationalization (i18n)**. It simplifies the creation and maintenance of `.resx` files by providing a centralized interface for keys and translations.

* **Key Features**: Visual translation management, easy key creation, and bulk editing.
* **Documentation**: [Read the Docs](https://github.com/dotnet/ResXResourceManager/blob/master/Documentation/Readme.md)
* **License**: Free and Open Source.