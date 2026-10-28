# Robholdings | Web & Domain Infrastructure

Documentation of the domains, DNS configuration, websites, email services, and development infrastructure associated with `robholdings.com`.

## Domain & Hosting

- **Primary domain:** `robholdings.com`
- **Registrar:** GoDaddy
- **DNS management:** GoDaddy
- **Website hosting:** GitHub Pages
- **Source control:** GitHub
- **Primary website:** `www.robholdings.com`

The main website is intentionally lightweight. Independent projects generally use subdomains rather than adding numerous pages to the primary website.

GitHub Pages hosts the main website and applicable subdomains. Other services use DNS records pointing to external tunnels or self-hosted infrastructure.

## Subdomains

| Subdomain | Purpose | Status |
|---|---|---|
| `www.robholdings.com` | Main personal website | Active |
| `cat.robholdings.com` | Personal web project | Active |
| `status.robholdings.com` | Service status monitoring | Active |
| `mc.robholdings.com` | Minecraft server via Playit | Active |
| `media.robholdings.com` | External Jellyfin access | Planned |
| `music.robholdings.com` | YouTube music analytics dashboard | Planned |

Subdomains are used to keep projects independent and avoid unnecessary complexity on the main website.

## Email Infrastructure

**Primary domain email:** `rob@robholdings.com`

| Service | Purpose |
|---|---|
| ImprovMX | Incoming email forwarding |
| SMTP2GO | Outbound SMTP delivery |
| Gmail | Primary email interface |

### Incoming Email

Messages sent to `rob@robholdings.com` are forwarded through ImprovMX to Gmail.

### Outgoing Email

Gmail is configured to send as `rob@robholdings.com` using SMTP2GO.

This provides custom-domain email without operating a dedicated mail server or purchasing a separate mailbox hosting service.

### Email Authentication

DNS records support:

- **MX:** Incoming email routing
- **SPF:** Authorized email senders
- **DKIM:** Outgoing message authentication
- **DMARC:** Email authentication policy

Exact DNS values and credentials are not stored in this documentation.

## Website Development

Websites and related projects are maintained through GitHub repositories.

**Development tools:**

- GitHub — remote repositories, version history, and pull requests
- Git — local version control and synchronization
- Visual Studio Code — local development and editing
- GitHub Pages — static website hosting and deployment

### Development Workflow

1. Edit project files locally using VS Code.
2. Review changes with Git.
3. Commit and push changes to GitHub.
4. Use branches and pull requests for larger or experimental changes.
5. Deploy applicable website changes through GitHub Pages.

GitHub provides a central location for synchronizing work across the desktop, personal laptop, and work laptop.

The GitHub website can also be used for smaller edits when local development tools are unavailable.

## Project Organization

The repository contains website source files and project documentation.

Documentation is maintained separately from public-facing website content where practical.

Examples include:

- `projects/home-server/README.md` — BobbyOs hardware, networking, services, and remote access
- `infrastructure.md` — domain, DNS, hosting, email, and development workflow

Individual projects may eventually have dedicated repositories or documentation as they become more complex.

## Planned Improvements

- **Music analytics:** Build `music.robholdings.com` using exported YouTube play history, including artist rankings, genre analysis, listening trends, and date-range filters.
- **Media access:** Configure external Jellyfin access through `media.robholdings.com`.
- **Development workflow:** Continue improving Git, VS Code, and multi-device development practices.
- **Documentation:** Maintain accurate references for DNS, hosting, email, and deployment configurations.

## Related Documentation

See `projects/home-server/README.md` for BobbyOs hardware, locally hosted services, Sunshine/Moonlight streaming, VPNs, and remote administration.
