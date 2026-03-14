# 📱 FB New Account OTP Bluster

**Facebook New Account OTP Sender — Mobile (Termux) Version**

Automated tool for sending OTP verification codes to phone numbers via Facebook's registration flow.

> **Developer:** [@HyperGox](https://t.me/HyperGox) | **Channel:** [t.me/GoxToolz](https://t.me/GoxToolz)

---

## ⚡ Features

- 📨 **OTP Sender** — Send Facebook registration OTP to phone numbers
- 🔥 **Brutal Mode** — Multi-threaded parallel sending for maximum speed
- 🐢 **Normal Mode** — Serial sending, one at a time
- 🔗 **Proxy Support** — Add, test, remove rotating proxies
- 📱 **Device Modes** — Android, PC, Mac, iPhone user-agent emulation
- 📋 **Number File** — Add, view, and manage phone numbers
- 📊 **Live Progress** — Real-time success/fail counter
- 💾 **Auto Save** — Settings persist across sessions
- 🔑 **HWID License** — Hardware-locked activation system

---

## 📲 Termux Installation

Open Termux and run these commands one by one:

**1. Update packages:**
```
pkg update -y && pkg upgrade -y
```

**2. Install required tools:**
```
pkg install git wget build-essential libffi openssl zlib -y
```

**3. Remove old Python (if installed):**
```
yes | pkg remove python
```
```
apt autoremove -y
```
```
rm -rf $PREFIX/lib/python*
```

**4. Download Python 3.12:**
```
cd ~ && wget https://www.python.org/ftp/python/3.12.12/Python-3.12.12.tgz
```

**5. Extract:**
```
tar -xzf Python-3.12.12.tgz
```

**6. Build & Install (takes 5-10 mins):**
```
cd Python-3.12.12
```
```
LDFLAGS="-L$PREFIX/lib" CFLAGS="-I$PREFIX/include" ./configure --prefix=$PREFIX --with-openssl=$PREFIX
```
```
make -j4
```
```
make install
```

**7. Setup Python command:**
```
ln -sf $PREFIX/bin/python3.12 $PREFIX/bin/python
```
```
ln -sf $PREFIX/bin/pip3.12 $PREFIX/bin/pip
```

**8. Cleanup build files:**
```
cd ~ && rm -rf Python-3.12.12 Python-3.12.12.tgz
```

**9. Verify Python version:**
```
python --version
```
> ✅ Should show: `Python 3.12.12`

**10. Install required modules:**
```
pip install requests
```

**11. Clone the repository:**
```
git clone https://github.com/Shadhink412/fb-new-account-otp-bluster.git
```

**12. Enter the folder:**
```
cd fb-new-account-otp-bluster
```

**13. Run the tool:**
```
python fb_otp_sender.py
```

---

## 📖 How to Use

### Main Menu

| Option | Description |
|--------|-------------|
| `1` | ▶ Start sending OTP |
| `2` | 🔗 Proxy Settings |
| `3` | 📋 Number File management |
| `4` | ⚡ Mode Settings (Normal / Brutal) |
| `5` | 📱 Device Mode selector |
| `6` | 📢 Telegram contact |
| `0` | Exit |

### Step-by-Step

1. **Add Numbers** — Go to option `3` → Add phone numbers with country code
2. **Set Proxy** *(optional)* — Go to option `2` → Add proxy `host:port:user:pass`
3. **Choose Mode** — Go to option `4` → Normal (serial) or Brutal (multi-thread)
4. **Select Device** — Go to option `5` → Android / PC / Mac / iPhone
5. **Start** — Press `1` to begin sending

### Number Format

Add phone numbers with country code, one per line:
```
8801XXXXXXXXX
2250XXXXXXXXX
```

---

## ⚠️ Important Notes

- Requires active **HWID license** to run
- Contact [@HyperGox](https://t.me/HyperGox) on Telegram for license activation
- Your HWID will be shown when you first run the tool
- Proxy is recommended for best results

---

## 📞 Contact

- **Telegram:** [@HyperGox](https://t.me/HyperGox)
- **WhatsApp:** 01315076545
- **Channel:** [t.me/GoxToolz](https://t.me/GoxToolz)

---

> Made with ❤️ by **GoxToolz**
