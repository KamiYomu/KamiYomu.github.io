---
title: Integrations
parent: Features
---

# Integrations

KamiYomu supports integration with several external services to enhance your self-hosted environment. These integrations enable notifications, automatic library synchronization, and real-time status monitoring.

Currently supported integrations include **Gotify**, **Kavita**, and **Homepage (gethomepage.dev)**.

---

## Gotify

<img src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/gotify.svg"
     alt="Gotify"
     width="200">

[Gotify](https://gotify.net/) is a lightweight self-hosted notification server.  
KamiYomu uses Gotify to send push notifications when:

- A manga scan completes
- A chapter download finishes
- Important system events occur

### Configuration

**Required fields:**

- **Service URI**  
  The base URL of your Gotify instance  
  _Example:_ `http://gotify.local`

- **API Key**  
  The application token generated in Gotify

### Setup Guide

1. Open your Gotify instance in a web browser.
2. Go to **Applications**.
3. Click **Create Application**.
4. Name the application `KamiYomu`.
5. Copy the generated **Token**.
6. Paste the token into the **API Key** field in KamiYomu settings.
7. Save the configuration.

Once configured, notifications will be sent automatically.

---

## Kavita

<img src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/svg/kavita.svg"
     alt="Kavita"
     width="200">

[Kavita](https://www.kavitareader.com/) is a fast, feature-rich, cross-platform reading server.  
KamiYomu integrates with Kavita to automatically refresh or rescan libraries when new manga content is downloaded.

### Configuration

**Required fields:**

- **Service URI**  
  The URL of your Kavita instance  
  _Example:_ `http://kavita.local:5000`

- **API Key**  
  The API key associated with your Kavita user account

### Setup Guide

1. Open your Kavita instance.
2. Log in to your account.
3. Click your profile icon (top-right).
4. Navigate to **User Settings** → **API Key**.
5. Copy the API key.
6. Paste it into the **API Key** field in KamiYomu settings.
7. Save the configuration.

KamiYomu will now notify Kavita whenever new content is available.

---

## Homepage (gethomepage.dev)

<img src="https://cdn.jsdelivr.net/gh/homarr-labs/dashboard-icons/png/homepage.png"
     alt="Homepage"
     width="200">

[Homepage](https://gethomepage.dev/) is a highly customizable self-hosted dashboard.  
KamiYomu can expose runtime statistics that Homepage can display using the **Custom API widget**.

Displayed metrics include:

- Collection size
- Queued worker tasks
- Failed worker tasks
- Application version

---

### Docker Compose (Service Discovery)

If you are using Homepage’s Docker service discovery, add the following labels to your KamiYomu service in `docker-compose.yml`:

```yaml
labels:
  - "homepage.group=Download & Automation"
  - "homepage.name=Kamiyomu"
  - "homepage.href=http://kamiyomu:8080"
  - "homepage.description=Manga Download Platform"
  - "homepage.showStats=true"
  - "homepage.refresh=300"
  - "homepage.widget.type=customapi"
  - "homepage.widget.url=http://kamiyomu:8080/api/stats"
  - "homepage.widget.mappings.0.field=collectionSize"
  - "homepage.widget.mappings.0.label=Collection Size"
  - "homepage.widget.mappings.1.field=workerQueuedTasks"
  - "homepage.widget.mappings.1.label=Queued Tasks"
  - "homepage.widget.mappings.2.field=workerFailedTasks"
  - "homepage.widget.mappings.2.label=Failed Tasks"
```

After restarting your containers, KamiYomu will automatically appear in Homepage.

### Manual Setup


If you prefer not to use Docker discovery, you can manually configure Homepage.

Create or edit the `services.yml` file in your Homepage configuration directory and add:

```yaml
- Download & Automation:
    - Kamiyomu:
        href: http://kamiyomu:8080
        description: Manga Download Platform
        showStats: true
        refreshInterval: 300
        widget:
          type: customapi
          url: http://kamiyomu:8080/api/stats
          mappings:
            - field: collectionSize
              label: Collection Size
            - field: workerQueuedTasks
              label: Queued Tasks
            - field: workerFailedTasks
              label: Failed Tasks
```

### Homepage Layout Configuration

Ensure your `settings.yaml` includes the corresponding group layout:

```yaml
title: Dashboard
theme: dark
color: slate
headerStyle: clean
layout:
  Download & Automation:
    style: row
    columns: 3
```

## Available Statistics Fields

The `/api/stats` endpoint exposes the following fields:

- **collectionSize**  
  Total number of manga in your collection

- **workerQueuedTasks**  
  Number of tasks waiting to be processed

- **workerFailedTasks**  
  Number of tasks that failed during processing

- **version**  
  KamiYomu application version

- **coreVersion**  
  KamiYomu Core version

You can add or remove mappings in Homepage to display only the metrics you care about.
