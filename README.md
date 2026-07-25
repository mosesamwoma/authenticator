# Authenticator

A simple desktop TOTP (Time-based One-Time Password) authenticator app built with [Kivy](https://kivy.org/). Generate 2FA codes for your services locally, without needing your phone.

## Download

Prebuilt apps for Windows, Linux, and Android are available on the [downloads page](https://felixmokayabeatz.online/beatzlock-apps/downloads/) — pick your platform there:

| Platform | Format |
|---|---|
| Windows | `.exe` |
| Linux | `.deb` (Ubuntu/Debian) or `.rpm` (Fedora) |
| Android | `.apk` |

## Features

- Generate TOTP codes from a Base32 secret
- Save multiple service/secret pairs locally (`secrets.json`)
- Auto-refreshing code with a countdown timer
- Loads your last used service on startup

## Note

- Python 3.9–3.11 (Kivy has known compatibility issues on 3.12+; 3.10 is the safest bet)

## Installation

```bash
git clone https://github.com/mosesamwoma/authenticator.git
cd authenticator
python3.10 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

## Usage

```bash
python authenticator.py
```

1. Enter a service name (e.g., `Google`, `GitHub`)
2. Enter the Base32 TOTP secret provided by that service
3. Click **Generate OTP**
4. The 6-digit code will refresh automatically every 30 seconds

## Building a Standalone Executable


```bash
pyinstaller authenticator.spec
```

The compiled app will be in `dist/`.