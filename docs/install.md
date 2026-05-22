# Installation Guide

## Option 1: Flash ThirtyOS Image (recommended)

```bash
# Download image from Releases
gunzip ThirtyOS_v1.0.0_HG680P.img.gz

# Flash to SD/USB/SSD
sudo dd if=ThirtyOS_v1.0.0_HG680P.img of=/dev/sdX bs=4M status=progress conv=fsync

# Resize partition after flash
sudo parted /dev/sdX resizepart 2 100%
sudo e2fsck -f /dev/sdX2
sudo resize2fs /dev/sdX2
```

> **Warning:** This erases ALL data on the target device.

## Option 2: One-Liner Install (any Armbian/Debian)

If you already have Armbian running on your HG680P, jalankan perintah ini **sekali** untuk download `thirtyos-install`:

```bash
sudo curl -fsSL -o /usr/local/bin/thirtyos-install https://raw.githubusercontent.com/ahdikhfDev/ThirtyOS/main/thirtyos-install && sudo chmod +x /usr/local/bin/thirtyos-install
```

**Setelah itu**, update ke versi terbaru:

```bash
thirtyos-install update
```

## First Boot

1. Boot from SD/USB/SSD on HG680P
2. Login (default: `root` / `1234`)
3. Create a user when prompted

```bash
# 1. First-time setup (hostname, timezone, user)
thirtyos-install setup

# 2. Install packages (Node.js, Docker, PM2)
thirtyos-install prepare

# 3. Optimize system (ZRAM, journal, swappiness, etc)
thirtyos-install optimize

# 4. Install services you want (see command reference)
```
