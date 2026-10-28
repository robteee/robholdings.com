# BobbyOs | Home Server

BobbyOs is my Windows 11 desktop, used for gaming, self-hosting, remote access, and experimenting with networking and web infrastructure.

## Hardware

- **CPU:** Intel Core i9-12900K
- **GPU:** NVIDIA RTX 5080
- **Motherboard:** ASUS PRIME Z790-V WIFI
- **RAM:** 32 GB DDR5-6000
- **OS:** Windows 11
- **PSU:** MSI 850W Gold
- **Case:** Fractal Pop Air
- **Network:** Ethernet, TP-Link Archer AXE95 router
- **Displays:** LG C1 4K/120Hz OLED and ASUS 27" 1440p/165Hz monitor

### Storage

| Drive | Type | Capacity | Usage |
|---|---|---|---|
| C: | NVMe SSD | 2 TB | Windows / primary applications |
| D: | NVMe SSD | 2 TB | Games / secondary storage |
| E: | SATA SSD | 2 TB | Movies |
| F: | SATA SSD | 2 TB | Music / TV Shows |
| **Total** | | **8 TB** | |

All four drives are internal SSDs. Future expansion may include a 20 TB+ HDD for bulk storage and increased media hosting.

## Services

| Service | Purpose |
|---|---|
| Jellyfin | Self-hosted media streaming |
| Caddy | Reverse proxy and web routing |
| Playit | Public tunnels through ISP CGNAT |
| Minecraft Java Server | Local and remote multiplayer |
| Tailscale | Private remote network access |
| Sunshine | Remote desktop and game-streaming host |
| Moonlight | Streaming client on phones, tablets, and laptops |
| Chrome Remote Desktop | Backup remote desktop access |
| OpenSSH | Remote commands and administration |
| PIA VPN | Split tunneling for selected traffic |
| qBittorrent | Downloads routed through PIA |

## Networking & Access

My ISP uses CGNAT, preventing conventional inbound IPv4 port forwarding.

Different services use different access methods:
- Playit: Public Minecraft access at mc.robholdings.com
- Tailscale: Private connectivity between BobbyOs and remote devices
- Sunshine/Moonlight: Low-latency gaming and desktop streaming over LAN or private remote connections
- Chrome Remote Desktop: Alternative remote desktop access
- SSH: Remote system management, including HDR commands
- PIA: VPN-isolated download traffic through split tunneling
- Caddy: Reverse proxy for applicable self-hosted web services

## Remote Streaming
### The setup supports remote gaming with an Xbox controller, keyboard/mouse input, and portable displays.

Sunshine runs on BobbyOs, with Moonlight clients on:

- iPhone 17 Pro, including external-monitor output
- Windows laptops
- iPad 6th generation

A sideloaded Moonlight fork supports additional external-monitor resolutions on iPhone.

**Current configuration and limitations:**

- The LG C1 is usually powered off during remote access.
- No virtual display driver is currently installed.
- HDRTray is not installed.
- HDRCmd.exe is used for remote HDR switching through SSH.
- Windows HDR can cause Chrome Remote Desktop to display a gray screen.
- Headless streaming can fail when no physical display is detected.
- VPN routing and display configuration can affect remote connectivity.

## Current Projects

- **Virtual display:** Install and configure a virtual display driver for reliable headless Sunshine streaming.
- **Remote workstation:** Use BobbyOs remotely from a laptop with dual-monitor support.
- **Streaming improvements:** Improve resolution, aspect ratio, and HDR switching across Moonlight clients; evaluate HDRTray.
- **Remote administration:** Improve SSH reliability, remote recovery, and connectivity.
- **Jellyfin external access:** Enable access through `media.robholdings.com` without requiring Tailscale.
- **Automated media management:** Explore automated downloads and Jellyfin library organization.
- **YouTube music analytics dashboard:** Build `music.robholdings.com` using exported YouTube play history to visualize listening trends, artists, genres, and date ranges.
- **Virtualization & sandboxing:** Configure Hyper-V and isolated Windows environments, including the planned DaveCube sandbox. Resolve existing virtualization startup issues.
## Documentation
This file covers the physical server, locally running services, and remote access.

Domain management, DNS, websites, and email infrastructure are documented separately in infrastructure.md.
