---
title: Public API & OPDS Catalog
parent: Features
---

# Public API & OPDS Catalog

KamiYomu provides external access to your collection via a public API and the OPDS (Open Publication Distribution System) standard.

### 📚 OPDS Catalog
To access your library on mobile devices, e-readers, or third-party apps (like Moon+ Reader or KyBook), use the following endpoint:

`http://localhost:8080/public/api/v1/opds`

**Note:** If accessing from a different device, replace `localhost` with your server's local IP address (e.g., `192.168.1.50`).

---

### 🛠 Interactive API Documentation (Swagger)

For developers or users wishing to interact with the system programmatically, a full Swagger UI is available to explore all endpoints:

`http://localhost:8080/public/api/swagger/index.html`


---

### ⚠️ Network Configuration
To access these services from outside the host machine:
* **Firewall:** Ensure that port `8080` (or your custom mapped port) is open in your system's firewall.
* **Remote Access:** If accessing over the internet, ensure you have configured port forwarding or a reverse proxy. 
* **Security:** It is highly recommended to use a VPN or a reverse proxy with SSL (HTTPS) if exposing these endpoints publicly.

> [!NOTE]
> Map volumes to local paths as needed. Check [releases](https://github.com/KamiYomu/KamiYomu/releases) for available versions.
