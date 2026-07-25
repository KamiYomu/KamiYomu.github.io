---
title: Advanced Configurations
parent: Getting Started
nav_order: 3
---

This section provides a set of configuration options you can enable or customize for your KamiYomu instance using your Docker Compose setup.

{% capture docker_full_example_note %}
{% include note-docker-full-example.md %}
{% endcapture %}
{{ docker_full_example_note | markdownify }}

If you run KamiYomu as a standalone application on Windows or Linux, edit the appsettings.json file directly.

- Windows: `%ProgramFiles%\KamiYomu\win-x64\appsettings.json`
- Linux: `/opt/KamiYomu/linux-x64/appsettings.json`

{% capture appsettings_note %}
{% include note-appsettings-example.md %}
{% endcapture %}
{{ appsettings_note | markdownify }}