<div align="center">

# 🔥 GoxTool — FB Registration OTP Sender

### Automated Facebook Registration & SMS Verification System

[![Version](https://img.shields.io/badge/Version-1.6_Beta-blue?style=for-the-badge)](.)
[![Python](https://img.shields.io/badge/Python-3.8+-green?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Platform](https://img.shields.io/badge/Platform-Termux_|_Linux-orange?style=for-the-badge)](.)
[![License](https://img.shields.io/badge/License-Private-red?style=for-the-badge)](.)

<br/>

> **Bulk Facebook registration with real SMS delivery — fully automated, multi-threaded, proxy-aware.**

<br/>

[Features](#-features) · [Installation](#-installation) · [Usage](#-usage) · [Modes](#-modes) · [Proxy](#-proxy-system) · [Contact](#-contact)

---

</div>

<br/>

## ✨ Features

<table>
<tr>
<td width="50%">

### 🎯 Core Capabilities
- **Bulk Registration** — Process hundreds of numbers from file
- **Real SMS Delivery** — Actual Facebook verification codes sent
- **Auto Number Cleanup** — Processed numbers removed from queue
- **Success/Fail Tracking** — Separate logs for results

</td>
<td width="50%">

### ⚡ Performance
- **Pipeline Architecture** — Pre-fetches sessions while submitting
- **GoxBrutal Mode** — Up to 50 parallel threads
- **Zero Downtime** — Background session preparation
- **Smart Retry** — Handles rate limits gracefully

</td>
</tr>
<tr>
<td width="50%">

### 🌍 Multi-Region Intelligence
- **30+ Country Support** — Region-specific name generation
- **Auto Language Matching** — Accept-Language headers match phone country
- **Dynamic Proxy Routing** — Auto-inject region codes per number
- **Sticky Sessions** — Same IP for entire registration flow

</td>
<td width="50%">

### 🖥️ Device Emulation
- **Android** — Samsung, Pixel, Xiaomi fingerprints
- **Mac** — macOS Catalina → Sequoia, Retina DPR
- **PC** — Windows 10/11, multiple Chrome versions
- **iPhone** — iOS 16-17, Safari with WebKit

</td>
</tr>
</table>

<br/>

## 📦 Installation

### Termux (Android)

```bash
# Install Python
pkg update && pkg install python

# Install dependencies (auto-installed on first run)
pip install requests pycryptodome

# Run
python main.py
```

### Linux / VPS

```bash
# Install Python 3.8+
sudo apt install python3 python3-pip

# Install dependencies
pip3 install requests pycryptodome

# Run
python3 main.py
```

<br/>

## 🚀 Usage

### Quick Start

```
1. Run: python main.py
2. Add numbers: Menu → [3] Number → [1] Add
3. Set proxy:   Menu → [2] Proxy → [1] Add
4. Start:       Menu → [1] Start
```

### Number Format

Add phone numbers in `number.txt` — one per line, with country code:

```
8801712345678
919876543210
2250701234567
```

> 💡 Numbers are auto-removed after processing (success or fail)

<br/>

## ⚙️ Modes

### 🟢 Normal Mode (Serial)

```
Pipeline architecture — sequential processing with background session prefetch.
Best for: Low proxy bandwidth, single proxy, careful processing.
```

- Pre-fetches next 10 sessions in background
- Each number gets unique device fingerprint + IP
- Shows real-time IP for each request

### 🔴 GoxBrutal Mode (Parallel)

```
Multi-threaded processing — up to 50 workers simultaneously.
Best for: High bandwidth proxy, bulk processing, speed.
```

- Configurable thread count (1-50)
- Staggered thread starts to prevent proxy overload
- Real-time counter: done/total per thread

```
Menu → [4] Mode → Select Normal or Brutal
Menu → [4] Mode → [3] Set thread count
```

<br/>

## 🌐 Proxy System

### Supported Format

```
host:port:username:password
```

### Smart Features

| Feature | Description |
|---------|-------------|
| **Region Auto-Detect** | Phone number → country code → proxy region injection |
| **Sticky Sessions** | Same exit IP for entire registration flow per number |
| **IP Rotation** | Each number gets a fresh IP via session ID |
| **Region Code Injection** | Auto-replaces `-region-XX` in proxy username |

### Example Proxy Setup

```
proxy.example.com:8080:user-region-BD:password
```

> When processing a **+225** (Ivory Coast) number, the proxy username automatically changes to `user-region-CI`, routing through a Côte d'Ivoire IP address.

<br/>

## 🌎 Supported Countries

<details>
<summary><b>Click to expand — 30+ countries with region-specific names</b></summary>

<br/>

| Region | Countries |
|--------|-----------|
| **South Asia** | 🇧🇩 Bangladesh, 🇮🇳 India, 🇵🇰 Pakistan |
| **Southeast Asia** | 🇮🇩 Indonesia, 🇵🇭 Philippines, 🇻🇳 Vietnam, 🇹🇭 Thailand, 🇲🇾 Malaysia |
| **Middle East** | 🇸🇦 Saudi Arabia, 🇪🇬 Egypt, 🇦🇪 UAE |
| **Africa** | 🇨🇮 Côte d'Ivoire, 🇧🇯 Benin, 🇳🇬 Nigeria, 🇿🇦 South Africa |
| **Europe** | 🇫🇷 France, 🇩🇪 Germany, 🇮🇹 Italy, 🇪🇸 Spain, 🇹🇷 Turkey, 🇷🇺 Russia, 🇺🇦 Ukraine |
| **Americas** | 🇺🇸 USA, 🇧🇷 Brazil, 🇲🇽 Mexico |
| **East Asia** | 🇯🇵 Japan, 🇰🇷 South Korea, 🇨🇳 China |

Each country has **culturally accurate name pools** for realistic registration profiles.

</details>

<br/>

## 🖥️ Device Emulation

Switch device profiles from the menu:

```
Menu → [5] Device
  [1] Android  — Samsung Galaxy, Google Pixel, Xiaomi
  [2] PC       — Windows 10/11, Chrome 130-145
  [3] Mac      — macOS 10.15-15.1, Retina displays
  [4] iPhone   — iOS 16-17, Safari
```

Each session generates a **completely unique fingerprint**:
- Randomized Chrome build numbers
- Consistent Client Hints (sec-ch-ua, platform, model, DPR)
- Viewport matching real screen resolutions
- Accept-Language matching phone country

<br/>

## 📊 Dashboard

```
 IP:103.45.xx.xx LOC:BD
 PRX:ON  DEV:MAC  MOD:Normal
 NUM:number.txt [150]
 ─────────────────
 [1] Start  [2] Proxy  [3] Number
 [4] Mode   [5] Device [6] TG
 [0] Exit
```

### Live Results

```
 ┌──────────────────────────────┐
 │ ✓ CODE SENT (SMS) │ 880171*** │
 │ REG  │  +8801*****678  │     │
 └──────────────────────────────┘
```

<br/>

## 📁 File Structure

```
├── main.py          # Main executable (run this)
├── number.txt       # Phone numbers (one per line)
├── success.txt      # Successfully sent numbers
├── failed.txt       # Failed numbers with reasons
└── gox.session      # Saved settings (proxy, mode, threads)
```

<br/>

## ⚠️ Requirements

| Requirement | Minimum |
|-------------|---------|
| Python | 3.8+ |
| RAM | 512 MB |
| Internet | Required |
| Platform | Termux / Linux |

### Auto-installed Dependencies
- `requests` — HTTP client
- `pycryptodome` — Cryptographic operations

<br/>

## 📞 Contact

<div align="center">

| Channel | Link |
|---------|------|
| **Telegram** | [@HyperGox](https://t.me/HyperGox) |
| **Channel** | [t.me/GoxToolz](https://t.me/GoxToolz) |
| **WhatsApp** | 01315076545 |

<br/>

**Built with ❤️ by HyperGox**

</div>
