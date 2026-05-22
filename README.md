# ThirtyOS — Custom Armbian for HG680P STB

**ThirtyOS** is a customized Armbian-based OS for the **HG680P** Android TV box (Amlogic S905X), built for lightweight home server use: bots, AI coding assistant, media server, retro gaming, Cloudflare tunnel, and more.

> Created by [@ahdikhfDev](https://github.com/ahdikhfDev)

---

## Features

- **Lightweight** — stripped of bloat, optimized for 1.8 GB RAM
- **ZRAM swap** (lz4, 50% of RAM) — no swap file needed
- **tmpfs /tmp** — logs & temp in RAM, reduces SSD wear
- **System optimizations** — disables unused services (bluetooth, avahi, ModemManager, apt-daily)
- **Auto-update** — `thirtyos-install` updates itself from GitHub, no re-flash needed
- **AI stack** — 9Router + OpenCode headless with free AI providers ($0/month)
- **One CLI tool** — `thirtyos-install` manages everything

---

## Quick Start

```bash
# Flash image to SD/USB/SSD
sudo dd if=ThirtyOS_v1.0.0_HG680P.img of=/dev/sdX bs=4M status=progress conv=fsync

# Boot → login (root / 1234) → set up
thirtyos-install setup
thirtyos-install prepare
thirtyos-install optimize
```

Already running Armbian? Just download the tool:

```bash
sudo curl -fsSL -o /usr/local/bin/thirtyos-install https://raw.githubusercontent.com/ahdikhfDev/ThirtyOS-tools/main/thirtyos-install
sudo chmod +x /usr/local/bin/thirtyos-install
thirtyos-install update
```

---

## Documentation

| Topic | Link |
|-------|------|
| Installation & first boot | [docs/install.md](docs/install.md) |
| Full command reference | [docs/commands.md](docs/commands.md) |
| AI stack setup & usage | [docs/ai-stack.md](docs/ai-stack.md) |
| Build your own image | [docs/build.md](docs/build.md) |

---

## Repository Structure

```
ThirtyOS-tools/
├── docs/                 # Documentation
├── customize-image.sh    # Build script (run on laptop/PC)
├── thirtyos-install      # CLI tool (runs on STB, bundled in image)
└── README.md             # This file
```

---

## License

MIT License — see [LICENSE](LICENSE) for details.

## Credits

- [Armbian](https://www.armbian.com/) — base OS
- [Homeflix](https://github.com/xebadir/homeflix) — media server
- [RetroArch](https://www.retroarch.com/) — emulator
- [Cloudflare Tunnel](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/) — secure tunneling
- [9Router](https://www.npmjs.com/package/9router) — AI gateway
- [OpenCode](https://opencode.ai/) — AI coding agent

## Issues & Feedback

Report issues at: https://github.com/ahdikhfDev/ThirtyOS-tools/issues
