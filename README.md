# VAULT

<p align="center">
  <strong>Discord game/hour spoofer</strong>
  <br />
  
  <br /><br />
  <img src="https://img.shields.io/badge/Python-3.10%2B-7B68EE?style=flat-square" />
  <img src="https://img.shields.io/badge/Platform-Windows-7B68EE?style=flat-square" />
  <img src="https://img.shields.io/badge/License-MIT-7B68EE?style=flat-square" />
</p>

---

## Overview

VAULT is a lightweight, terminal based utility built with Python. It automates Discord game activity event submission through the terminal.

## Features

- **Game Discovery** — Retrieves Discords detectable game database.
- **Batch Processing** — Processes game activity events in batches.
- **Session Management** — Configurable activity durations.
- **Authentication** — Token and cookie-based authentication.
- **Fingerprint Generation** — Windows executable fingerprint support.
- **Local Persistence** — Saves configuration and usage statistics.

## Installation

```bash
git clone https://github.com/kkorpy/vault.git
cd vault
python vault.py
```

Alternatively, download the standalone executable from [Releases](../../releases).

## Security

Authentication credentials are stored locally in `vault.json`. Never share this file or commit it to version control.

## Disclaimer

unofficial third party project. use responsibly and at your own risk. This violates Discords Terms of Service.

## Here is how to get your cookie and token (never share these with anyone)
<img width="1633" height="855" alt="token" src="https://github.com/user-attachments/assets/bc844a7c-ed9e-4c24-af83-d20f01b2600c" />

Go to dev tools ctrl + shift + i then navigate to Storage -> Local Storage -> filter "token" make sure you have the thing in the red box on.

<img width="1619" height="586" alt="cf_clearance" src="https://github.com/user-attachments/assets/70571149-7132-4ea5-9ae4-2108dbd4f442" />

Go to dev tools ctrl + shift + i then navigate to Storage -> Cookies after, find "cf_clearance" then copy the value.
---

<p align="center">
  <sub>VAULT · Built with Python</sub>
</p>
