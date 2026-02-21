<div align="center">

# 🔥 GoxTool — FB REG OTP Sender V1.6

**Automated Facebook Registration & SMS Verification**

[![Python](https://img.shields.io/badge/Python-3.8+-green?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![Platform](https://img.shields.io/badge/Termux_|_Linux-orange?style=flat-square)](.)
[![License](https://img.shields.io/badge/Private-red?style=flat-square)](.)

> Bulk FB registration with real SMS delivery — multi-threaded, proxy-aware, 30+ countries.

[Features](#-features) · [Install](#-installation) · [Usage](#-usage) · [Contact](#-contact)

---

</div>

## ✨ Features

- 📱 **Bulk Registration** — Process hundreds of numbers from file
- 📩 **Real SMS Delivery** — Actual Facebook verification codes
- ⚡ **GoxBrutal Mode** — Up to 50 parallel threads
- 🌍 **30+ Countries** — Region-specific names & language headers
- 🔄 **Smart Proxy** — Auto region routing + sticky sessions + IP rotation
- 🖥️ **4 Device Modes** — Android, PC, Mac, iPhone fingerprints
- 📊 **Live Dashboard** — Real-time IP, status & progress tracking
- 🧹 **Auto Cleanup** — Processed numbers removed from queue

## 📦 Installation

### Termux (Android)

```bash
pkg update
```
```bash
pkg install python git
```
```bash
rm main.py
```
```bash
git clone https://github.com/Shadhink412/fb-new-account-otp-bluster.git
```
```bash
cd fb-new-account-otp-bluster
```
```bash
pip install requests
```
```bash
pip install pycryptodome
```
```bash
python main.py
```

### Linux / VPS

```bash
sudo apt install python3 python3-pip git
```
```bash
rm main.py
```
```bash
git clone https://github.com/Shadhink412/fb-new-account-otp-bluster.git
```
```bash
cd fb-new-account-otp-bluster
```
```bash
pip3 install requests
```
```bash
pip3 install pycryptodome
```
```bash
python3 main.py
```

### Windows

> ⚠️ Windows version is not publicly available. Contact for access.
>
> Telegram: [@HyperGox](https://t.me/HyperGox) · WhatsApp: 01315076545

## 🚀 Usage

```
1. Run: python main.py
2. Add numbers: [3] Number → [1] Add
3. Set proxy:   [2] Proxy → [1] Add
4. Start:       [1] Start
```

**Number format** — one per line with country code in `number.txt`:
```
8801712345678
919876543210
2250701234567
```

## 📁 Files

```
main.py        → Run this
number.txt     → Phone numbers (one per line)
success.txt    → Sent numbers
failed.txt     → Failed numbers
gox.session    → Saved settings
```

## 📞 Contact

<div align="center">

[![Telegram](https://img.shields.io/badge/Telegram-@HyperGox-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/HyperGox)
[![Channel](https://img.shields.io/badge/Channel-GoxToolz-0088CC?style=for-the-badge&logo=telegram&logoColor=white)](https://t.me/GoxToolz)

**Built with ❤️ by HyperGox**

</div>
