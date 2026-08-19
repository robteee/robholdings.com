# Rob Holdings Home Server Lab

A small self-hosting project built on my Windows desktop to experiment with networking, remote access, media hosting, game servers, DNS, and web infrastructure.

## The Setup

The server currently runs:

- **Minecraft Java Server** — local and remote multiplayer
- **Jellyfin** — self-hosted media streaming
- **Caddy** — reverse proxy and web-service routing
- **Playit** — public tunneling through ISP CGNAT
- **Tailscale** — private remote access
- **PIA** — split tunneling for selected traffic
- **qBittorrent** — VPN-isolated download traffic
- **Custom DNS** — services connected to `robholdings.com` subdomains

## Architecture

```text
                       INTERNET
                          |
          +---------------+---------------+
          |                               |
          v                               v
 robholdings.com DNS                 Tailscale
          |                         Private Access
          v                               |
       Playit                             |
          |                               |
          +---------------+---------------+
                          |
                          v
                  WINDOWS SERVER
                          |
        +-----------------+-----------------+
        |                 |                 |
        v                 v                 v
    Minecraft          Jellyfin           Caddy


LOCAL NETWORK                         VPN TRAFFIC

Local LAN Devices                     qBittorrent
        |                                  |
        v                                  v
   Home Router                            PIA
        |                                  |
        +--------> Windows Server          v
                                        Internet
```

## Why the Tunnels?

My ISP uses **CGNAT**, which prevents normal inbound IPv4 port forwarding from being enough for public hosting.

Instead of purchasing a dedicated public IP, I use different tools for different access needs:

- **Playit** for public Minecraft access
- **Tailscale** for private remote access
- **Direct LAN connections** while at home
- **PIA split tunneling** to isolate download traffic without routing server services through the VPN

Minecraft is currently accessible externally through `mc.robholdings.com`.

## Why Build It?

I'm an SEO professional rather than a developer or systems administrator. This project started as a practical way to learn more about the infrastructure underneath the web: DNS, networking, proxies, tunnels, server processes, remote access, and service availability.

It has also become a sandbox for future technical SEO and web experiments under Rob Holdings.

## Next

- External Jellyfin access
- `media.robholdings.com`
- `status.robholdings.com` with live service monitoring
- `lab.robholdings.com` for technical/SEO experiments
- Expanded server storage
- Private file sharing
- Better automatic startup and recovery

## Security

Public documentation intentionally excludes internal IP addresses, credentials, local file paths, tunnel identifiers, firewall details, and other unnecessary operational information.
