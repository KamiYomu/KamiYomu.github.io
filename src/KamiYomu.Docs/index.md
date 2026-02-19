---
title: Getting Started
layout: home
nav_order: 1
---

# KamiYomu

<img src="{{ '/assets/images/logo.png' | relative_url }}" height="50"/>


# 📖 KamiYomu

**KamiYomu** is a high-performance, extensible manga manager designed for enthusiasts who demand total control. 

By leveraging a modular **Crawler Agent** architecture, KamiYomu empowers you to discover, download, reading, and archive manga from any supported source into a private, self-hosted library.

> {: .highlight }
> **Total Extensibility:** If a site isn't supported yet, you can build your own Crawler Agent in C# and integrate it instantly.
> {: .highlight }

### 🚀 Core Capabilities
* **Modular Crawling:** Support for any website via community-driven **Crawler Agents**.
* **Local Archival:** Download and store high-quality images in a structured local library.
* **Private Hosting:** A built-in web reader to access your collection from any device, anywhere.
* **Developer Friendly:** Comprehensive SDK and Validator tools for building custom agents.


[![GitHub Release](https://img.shields.io/github/v/release/kamiyomu/kamiyomu)]({{ '/docs/changelogs' | relative_url }})
[![GitHub contributors](https://img.shields.io/github/contributors/kamiyomu/kamiyomu)](https://github.com/kamiyomu/kamiyomu/graphs/contributors)
[![GitHub License](https://img.shields.io/github/license/kamiyomu/kamiyomu)](https://github.com/kamiyomu/kamiyomu/blob/main/LICENSE)

---

## 🤝 Join the KamiYomu Community

KamiYomu is built by people who care about great tooling for managing manga. Get involved — your feedback, bug reports, and contributions help shape the project.

| Action | Link |
| :--- | :--- |
| **Discuss** | [![Join the community](https://img.shields.io/github/discussions/kamiyomu/kamiyomu?logo=github&label=Discussions)](https://github.com/KamiYomu/KamiYomu/discussions) |
| **Report** | [![GitHub issues](https://img.shields.io/github/issues/kamiyomu/kamiyomu?logo=github&label=Issues)](https://github.com/kamiyomu/kamiyomu/issues) |
| **Contribute** | [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?logo=github)](https://github.com/KamiYomu/KamiYomu/pulls) |

---

### 🛠️ How You Can Help

Every contribution matters. Whether you are fixing a typo or building a new feature, we appreciate the help!

* **Build & Extend**: [Create a **Crawler Agent**]({{ '/docs/crawler-agents/create/' | relative_url }}) using the [Core library](https://github.com/KamiYomu/KamiYomu.CrawlerAgents.Core). Check the [Development Guide]({{ '/docs/development/visual-studio/' | relative_url }}) for specs.
* **Test & Report**: Found a bug? Open an issue with clear steps to reproduce and include your logs.
* **Improve Docs**: Help us make the documentation clearer or contribute translations for wider reach.
* **Review**: Help triage issues or provide feedback on open Pull Requests.

> {: .note }
> New to the project? Start by looking for issues to get your feet wet!
> {: .note }

### 📢 Help KamiYomu Grow

If KamiYomu has made your manga management easier, consider sharing it with others who might benefit. 

Growth happens best through word of mouth. Whether you share the project on your favorite social platforms, mention it in developer circles, or talk about it within your community, your voice helps us find new contributors and users. 

Even a small gesture goes a long way in helping the project thrive:

| Support Us | Link |
| :--- | :--- |
| **Star the Project** | [![GitHub stars](https://img.shields.io/github/stars/kamiyomu/kamiyomu?style=social)](https://github.com/kamiyomu/kamiyomu/stargazers) |
| **Follow the Org** | [![GitHub followers](https://img.shields.io/github/followers/kamiyomu?style=social)](https://github.com/orgs/KamiYomu) |


---

### ❤️ Support the Project

If KamiYomu makes your manga management easier, consider supporting the ongoing development:

<a href="https://github.com/sponsors/MarcosCostaDev">
  <img src="https://img.shields.io/badge/Sponsor-GitHub-ea4aaa?style=for-the-badge&logo=github-sponsors" alt="Sponsor MarcosCostaDev" />
</a>

---

## ⚠️ Capabilities & Limitations

### ✅ What KamiYomu Does

* **Complete Manga Reader:** Features a full suite of tools including advanced filtering, reading history, "Chapters of the Week," and dedicated views for new chapters and fresh manga releases.
* **Browser-Based Crawling:** Operates crawler agents that act like a standard web browser to navigate sites, execute JavaScript, and interact with content naturally.
* **Task Orchestration:** Schedules and manages agent tasks such as searching, listing, and fetching metadata.
* **Image Acquisition:** Downloads images directly from sources identified by the crawler agents.
* **Local Archiving:** Automatically organizes downloaded images into structured archives within your specified directories.
* **Flexible Exporting:** Allows you to export your collection as PDF, CBZ, or ZIP files for offline use.
* **Library Management:** Provides a sleek, self-hosted web interface optimized for both desktop and mobile browsing.

---

### ❌ What KamiYomu Does Not

**Security & Data Integrity**
* **Exploit or Invade:** Never bypasses security measures, exploits vulnerabilities, or circumvents paywalls/access controls.
* **Extract Private Data:** Does not scrape databases, protected information, login credentials, or API keys.
* **Data Collection:** Does not collect, monitor, or store any personal data, metadata, or activity on central servers.

**Content & Distribution**
* **Provide Content:** Does not include, host, or serve any built-in manga content. Users must source their own material.
* **Peer-to-Peer Sharing:** Does not support P2P sharing, inter-instance communication, or commercial redistribution.
* **Content Persistence:** Does not cache or retain content on KamiYomu servers; all data exists strictly on the user's local storage.

**Legal & Liability**
* **Endorsement:** Does not support, condone, or assist in bypassing legal restrictions or copyright infringement.
* **Compliance Guarantee:** Does not ensure compliance with third-party Terms of Service or local laws; this is the sole responsibility of the user.
* **Professional Services:** Does not offer legal advice, official support for third-party sites, or warranties regarding software reliability.

---

### ⚖️ User Responsibility & Disclaimer

**KamiYomu is provided "as-is" for local, personal use only.** By using this software, you acknowledge that you are solely responsible for the content you access and how you manage it. The developers and maintainers of KamiYomu assume **no liability** for:
1. User compliance with copyright laws or licensing agreements.
2. Violations of the Terms of Service of any source websites.
3. Any legal consequences arising from the use or misuse of this tool.

Users are encouraged to use KamiYomu only with content they have the legal right to access.

## 📃 License


The KamiYomu project is licensed under the **AGPL-3.0 (Affero General Public License version 3.0)**. This license allows users to freely use, modify, and distribute the software, provided that any modified versions are also distributed under the same license. 

### Key Points of AGPL-3.0:
- **Freedom to Use**: Users can run the software for any purpose.
- **Freedom to Study and Modify**: Users can access the source code and modify it to suit their needs.
- **Freedom to Distribute Copies**: Users can share the original software with others.
- **Freedom to Distribute Modified Versions**: Users can distribute modified versions of the software, but they must also be licensed under AGPL-3.0, ensuring that the same freedoms are preserved for all users.

For more detailed information, please refer to the official AGPL-3.0 [license text](https://github.com/kamiyomu/kamiyomu/blob/main/LICENSE).
