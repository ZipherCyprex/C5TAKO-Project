<div align="center">

# C5TAKO™

### Open-Source Wi-Fi & Bluetooth Testing Device

[![License](https://img.shields.io/badge/License-Custom-blue.svg)](LICENSE)
[![Firmware Release](https://img.shields.io/badge/Firmware-Latest-green.svg)](https://github.com/ZipherCyprex/C5TAKO-Project/releases)
[![Documentation](https://img.shields.io/badge/Docs-Online-orange.svg)](https://c5tako.ziphers.space)
[![Discord](https://img.shields.io/badge/Discord-Join%20Us-7289da.svg)](https://discord.gg/UXV38s6wAc)

<img src="docs/images/Zipher_c5tako.png" alt="C5TAKO Device" width="400"/>

**Firmware releases and documentation for DIY builders and developers**

</div>

<br>

## 📋 Table of Contents

- [About](#-about)
- [Downloads & Flashing](#-downloads--flashing)
- [Hardware Pinout](#-hardware-pinout)
- [Documentation](#-documentation)
- [Community & Support](#-community--support)
- [Legal Notice](#️-legal-notice)

<br>

## 🎯 About

This repository provides **firmware releases** and **installation tools** for the C5TAKO™ device. 

C5TAKO™ is a portable Wi-Fi (2.4/5 GHz) and Bluetooth LE testing device for security research and penetration testing. This repo is primarily for DIY builders and developers who want to flash firmware or contribute to the project.

> **For end-users**: Full user guides, feature documentation, and tutorials are available at **[c5tako.ziphers.space](https://c5tako.ziphers.space)**

<br>
<br>

## 📦 Downloads & Flashing

### Latest Firmware

Download the latest firmware `.bin` file from the [Releases](https://github.com/ZipherCyprex/C5TAKO-Project/releases) page.

<br>

### Flashing Methods

<br>

### 🌐 Option 1: Firmware Flasher (Easiest)

Use the official web-based flasher - no installation required:

**👉 [Firmware Flasher - Ziphers](https://flash.ziphers.space)**

**Steps:**
1. Visit the flasher website
2. Connect your ESP32-C5 via USB-C
3. Click "Connect" and select your device port
4. The firmware will be flashed automatically

> **Recommended** - This is the fastest and most user-friendly method.

<br>

### 🔧 Option 2: ESP Web Tool

Use [ESP Web Tool](https://espressif.github.io/esptool-js/) for manual flashing:

**Steps:**
1. Download the `.bin` file from releases
2. Open ESP Web Tool in a Chromium-based browser (Chrome, Edge, etc.)
3. Connect your ESP32-C5 via USB-C
4. Click "Connect" and select your device
5. Set flash offset to `0x0`
6. Select the downloaded `.bin` file
7. Click "Program" to flash

<br>

### ⚙️ Option 3: Command Line (esptool)

For advanced users who prefer terminal:

```bash
esptool.py --chip esp32c5 --port COM3 write_flash 0x0 firmware.bin
```

Replace `COM3` with your device's serial port (`/dev/ttyUSB0` on Linux/Mac).

<br>

**Troubleshooting:** If flashing fails, see the [Firmware Update Guide](https://c5tako.ziphers.space/getting-started/update-firmware) or ask for help in our [Discord](https://discord.gg/UXV38s6wAc).

<br>
<br>

## 🔌 Hardware Pinout

### Required MCU: ESP32-C5 Development Board

**Recommended**: XIAO ESP32-C5 or any ESP32-C5 dev board

> **Important**: This firmware is designed specifically for ESP32-C5. Other ESP32 variants are not supported.

<br>

| Component | GPIO Pin | Notes |
|-----------|----------|-------|
| **TFT Display (SPI)** | | |
| - MOSI | TBD | SPI Data |
| - MISO | TBD | SPI Data |
| - SCK | TBD | SPI Clock |
| - CS | TBD | Chip Select |
| - DC | TBD | Data/Command |
| - RST | TBD | Reset |
| - BL | TBD | Backlight PWM |
| **5-Way Button** | | Active LOW |
| - UP | TBD | Pull-up |
| - DOWN | TBD | Pull-up |
| - LEFT | TBD | Pull-up |
| - RIGHT | TBD | Pull-up |
| - CENTER | TBD | Pull-up |
| **Power (Optional)** | | |
| - Battery | TBD | ADC for voltage monitoring |

> **Note**: Pin assignments are being finalized and will be updated soon.

<br>

### Physical Components

- **Display**: 240x240 ST7789 TFT LCD
- **USB-C**: Charging & firmware flashing
- **Power Switch**: ON/OFF toggle
- **5-Way Button**: Navigation control

<br>

> **Warning**: C5TAKO™ is **NOT waterproof**. Avoid moisture and handle with care during assembly.

<br>
<br>

## 📚 Documentation

Complete user guides, feature documentation, and DIY assembly instructions:

### 👉 **[c5tako.ziphers.space](https://c5tako.ziphers.space)**

<br>

**For DIY Builders:**
- [Serial Protocol Specification](https://c5tako.ziphers.space/developer/serial-protocol)
- [Firmware Update Guide](https://c5tako.ziphers.space/getting-started/update-firmware)
- [Troubleshooting](https://c5tako.ziphers.space/help/troubleshooting)

**For End Users:**
- [Getting Started](https://c5tako.ziphers.space/getting-started/unboxing-and-power)
- [Feature Overview](https://c5tako.ziphers.space/features/menu-overview)
- [WiFi & Bluetooth Guides](https://c5tako.ziphers.space/features/wifi-overview)

<br>
<br>

## 💬 Community & Support

<div align="center">

[![Discord](https://img.shields.io/badge/Discord-7289DA?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/UXV38s6wAc)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://instagram.com/ziphers)
[![YouTube](https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white)](https://youtube.com/@ziphers)
[![Facebook](https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white)](https://facebook.com/ziphers)

</div>

<br>

### Get Help

- **Technical Support** - Join our [Discord Server](https://discord.gg/UXV38s6wAc) (11:00–00:00 GMT+7)
- **Bug Reports** - Open an issue in this repository
- **General Questions** - Visit [ziphers.space](https://www.ziphers.space/)

<br>
<br>

## ⚠️ Legal Notice

C5TAKO™ is designed for **educational purposes, security research, and authorized penetration testing only**.

<br>

### Allowed Usage

✅ Testing on your own devices and networks  
✅ Authorized security assessments with written permission  
✅ Educational research in controlled environments

### Prohibited Usage

❌ Unauthorized access to networks or devices  
❌ Malicious attacks or data theft  
❌ Interference with public infrastructure

<br>

> **Warning**: Unauthorized network testing may violate local laws. Users are solely responsible for compliance with applicable regulations. The developers of C5TAKO™ are not liable for misuse of this device.

<br>

**Legal Compliance:**
- Check local laws before testing any wireless network
- Obtain written permission before testing third-party systems
- Use only on networks and devices you own or have authorization to test
- Follow responsible disclosure practices for discovered vulnerabilities

<br>
<br>

<br>
<br>

<div align="center">

### Made with ❤️ by [zipher](https://ziphers.space)

**Other Projects**: [Zipher HID](https://hid.ziphers.space/) • [HERTZ](https://hertz.ziphers.space/)

[🌐 Website](https://www.ziphers.space/) • [📖 Docs](https://c5tako.ziphers.space) • [🔗 Linktree](https://linktr.ee/zipherqr)

<br>

**Star ⭐ this repository if you find it useful!**

</div>
