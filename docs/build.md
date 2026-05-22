# Build Your Own Image

## Prerequisites (on Kali/Ubuntu/Debian)

```bash
sudo apt update
sudo apt install -y qemu-user-static parted e2fsprogs curl
```

## Build

```bash
git clone https://github.com/ahdikhfDev/ThirtyOS.git
cd ThirtyOS

# Download Armbian base image:
# https://www.armbian.com/amlogic-s905x/

sudo bash customize-image.sh Armbian_*.img.gz
```

Output: `ThirtyOS_v1.0.0_HG680P.img.gz`

## Customize the Build

Edit `customize-image.sh` to add/remove packages or change configs, then rebuild.
