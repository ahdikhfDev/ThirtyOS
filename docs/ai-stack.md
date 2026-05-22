# AI Stack — $0/month

## Architecture

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

## Setup

```bash
# Install everything
thirtyos-install ai setup
```

## Usage on STB

```bash
# Run directly on STB
opencode
```

## From Laptop via SSH Tunnel

```bash
ssh -L 20128:localhost:20128 thirty@<ip-stb>
# Open http://localhost:20128/dashboard
```

## From Anywhere via Cloudflare

```bash
thirtyos-install ai tunnel
# Access https://ai.yourdomain.com/dashboard
```

## Commands

| Subcommand | Description |
|------------|-------------|
| `ai setup` | Install & configure 9Router + OpenCode + systemd service |
| `ai status` | Show AI services status |
| `ai update` | Update 9Router & OpenCode to latest |
| `ai tunnel` | Expose AI dashboard via Cloudflare Tunnel |
