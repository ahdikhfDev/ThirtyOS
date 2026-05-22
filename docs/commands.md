# Command Reference

## `thirtyos-install setup`
First-run wizard. Sets hostname, timezone, creates user.
```bash
thirtyos-install setup
```

## `thirtyos-install prepare`
Installs core packages: Node.js 20, Docker, PM2, build tools.
```bash
thirtyos-install prepare
```

## `thirtyos-install optimize`
8-step system optimization for low-RAM devices:
1. Fix & enable ZRAM swap (lz4, 50% RAM)
2. Move journal to RAM (volatile, 50 MB max)
3. Set swappiness to 10
4. Set IO scheduler to `none` (SSD)
5. Set CPU governor to `schedutil`
6. Optionally disable NetworkManager
7. Clean apt cache & orphan packages
8. Disable unused services (bluetooth, cups, avahi, etc)
```bash
thirtyos-install optimize
```

## `thirtyos-install ai`
AI coding assistant stack — **$0/month**. Installs 9Router (AI gateway) + OpenCode (headless AI agent).

Architecture:
```
Laptop/Phone
    ↓ SSH tunnel or Cloudflare
STB ThirtyOS
    ├── OpenCode (headless)
    │       ↓ localhost:20128/v1
    └── 9Router (AI Gateway)
            ↓ auto-fallback
    ┌──────────────────────────┐
    │ Kiro AI (Claude 4.5)     │ ← unlimited free
    │ OpenCode Free            │ ← no auth
    │ iFlow                    │ ← no auth
    │ Qwen                     │ ← no auth
    └──────────────────────────┘
```

**Subcommands:**

| Subcommand | Description |
|------------|-------------|
| `ai setup` | Install & configure 9Router + OpenCode + systemd service |
| `ai status` | Show AI services status |
| `ai update` | Update 9Router & OpenCode to latest |
| `ai tunnel` | Expose AI dashboard via Cloudflare Tunnel |

See [docs/ai-stack.md](ai-stack.md) for detailed usage.

## `thirtyos-install bot-wa`
Install or update WhatsApp bot (Baileys-based).
```bash
thirtyos-install bot-wa
```

## `thirtyos-install tunnel`
Setup Cloudflare Tunnel for remote access.
```bash
thirtyos-install tunnel
```

## `thirtyos-install panel`
Install web panel: CasaOS or Portainer.
```bash
thirtyos-install panel
```

## `thirtyos-install media`
Install Homeflix media server (stream movies/series).
```bash
thirtyos-install media
```

## `thirtyos-install retro`
Install RetroArch with emulator cores (NES, SNES, PS1, N64, etc).
```bash
thirtyos-install retro
```

## `thirtyos-install wifi`
Scan and connect to WiFi networks (uses NMCLI).
```bash
thirtyos-install wifi
```

## `thirtyos-install update`
Update everything — APT packages, NPM globals, thirtyos-install itself.
```bash
thirtyos-install update
```
No re-flash needed. `thirtyos-install` auto-downloads the latest version from GitHub.

## `thirtyos-install status`
Show system & service status overview.
```bash
thirtyos-install status
```

## `thirtyos-install uninstall`
Remove installed services (bot-wa, panel, media, etc).
```bash
thirtyos-install uninstall
```

## `thirtyos-install version`
Show ThirtyOS version info.
```bash
thirtyos-install version
```
