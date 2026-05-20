# postmarketOS — Realme 9 Pro 5G (oscar)

Downstream port using LineageOS 23.2 kernel (SM6375 / Snapdragon 695).

## Device
| | |
|---|---|
| Codename | oscar (RMX3471 / RMX3472) |
| SoC | Qualcomm Snapdragon 695 (SM6375) |
| Kernel | 5.4.x downstream GKI |
| Base | LineageOS 23.2 |

## Status
| Component | Status |
|---|---|
| Boot | 🔧 Testing |
| USB SSH | 🔧 Testing |
| Display | 🔧 Testing |
| WiFi | ❌ Needs firmware blobs |
| Camera | ❌ Not planned (no open ISP) |

## Build
Push to main → GitHub Actions builds automatically.
Download from the **Actions** tab → latest run → Artifacts.

# Disable AVB (required!)
fastboot flash vbmeta --disable-verity --disable-verification vbmeta.img

# Keep vendor_boot and dtbo from LineageOS
fastboot flash vendor_boot vendor_boot.img
fastboot flash dtbo dtbo.img

# Flash pmOS
fastboot flash boot boot.img
fastboot flash userdata rootfs-realme-oscar.img

fastboot reboot

sudo ip addr add 172.16.42.2/24 dev usb0
ssh user@172.16.42.1
