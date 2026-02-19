---
title: Setup
parent: Development
nav_order: 1
---

We recommend using Visual Studio 2022 or later with the .NET 8 SDK installed. 
However, you can also run KamiYomu using VsCode.

- Fork the repository
- Select the develop branch (`git checkout develop`)
- Create your feature branch (`git checkout -b feature/AmazingFeature`)
- Commit your changes (`git commit -m 'Add some AmazingFeature'`)
- Push to the branch (`git push origin feature/AmazingFeature`)
- Open a Pull Request against the `develop` branch


## 🛠️ Main Development Environments

We support development in both the full Visual Studio IDE and the lightweight VS Code. Choose the environment that best fits your workflow:

| IDE / Editor | Best For... | Documentation |
| :--- | :--- | :--- |
| **Visual Studio** | Full .NET features, integrated debugging, and heavy refactoring. | [View Guide]({{ '/docs/development/visual-studio/' | relative_url }}) |
| **VS Code** | Cross-platform development, lightweight editing, and extension flexibility. | [View Guide]({{ '/docs/development/visual-studio-code/' | relative_url }}) |

> {: .note }
> Regardless of your choice, ensure you have the latest .NET SDK installed as specified in our [Getting Started]({{ 'http://localhost:4000/docs/development/development/' | relative_url }}) guide.
> {: .note }


---