# PirateFlix 🏴‍☠️

A complete self-hosted Docker environment to automatically download, manage, and stream your movies and TV shows — all in one place. Secure, modular, and easy to deploy.

---

## 🧰 Included Services

| Service     | Description |
|-------------|-------------|
| **Gluetun** | Secure VPN tunnel (e.g., Mullvad, StrongVPN) |
| **qBittorrent** | Torrent client with web interface |
| **Radarr** | Automated movie downloader |
| **Sonarr** | Automated TV show downloader |
| **Bazarr** | Subtitles manager and downloader |
| **Prowlarr** | Indexer manager for Radarr/Sonarr |
| **Jellyfin** | Media server for local streaming |
| **SWAG** | Secure Web Application Gateway (HTTPS with DuckDNS) |
| **DuckDNS** | Dynamic DNS service to update your public IP |

---

## 🗂️ Project Structure

```
PirateFlix/
├── appdata/         # Service configurations (not versioned)
├── cache/           # Jellyfin cache
├── downloads/       # Downloaded torrents
├── movies/          # Movie library
├── series/          # TV show library
├── docker-compose.yml
├── .env             # Sensitive credentials (DO NOT commit)
├── .env.example     # Template for .env file
└── README.md
```

---

## ⚙️ Requirements

- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/)
- A VPN provider with OpenVPN config files
- A DuckDNS account for public access (optional)

---

## 🚀 Quick Start

1. Clone the repo:
   ```bash
   git clone https://github.com/your-username/PirateFlix.git
   cd PirateFlix
   ```

2. Copy and edit the environment variables file:
   ```bash
   cp .env.example .env
   nano .env
   ```

3. Start all services:
   ```bash
   docker compose up -d
   ```

---

## 🔐 Security Tips

- **Never commit `.env`** — it contains VPN and DuckDNS credentials.
- The `.env` file is excluded via `.gitignore` for safety.
- Ensure only necessary ports are exposed (e.g., 443, 80, 8080).

---

## 📍 Access URLs

| Service    | Default URL |
|------------|-------------|
| qBittorrent | http://localhost:8080 |
| Radarr      | http://localhost:7878 |
| Sonarr      | http://localhost:8989 |
| Bazarr      | http://localhost:6767 |
| Prowlarr    | http://localhost:9696 |
| Jellyfin    | http://localhost:8096 |
| SWAG (HTTPS) | https://shlx.duckdns.org |

---

## 🧠 Notes

- No GPU required for Jellyfin in this setup (CPU-based transcoding)
- Port forwarding is no longer supported with Mullvad (may affect torrenting)
- SWAG uses Let's Encrypt for free SSL certificates via DuckDNS

---

## 🙋‍♂️ Support

This is a personal project. For help, open a GitHub issue or visit [r/selfhosted](https://www.reddit.com/r/selfhosted/).

---