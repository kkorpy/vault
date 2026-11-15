# VAULT

<p align="center">
  <strong>Discord Game Activity Utility</strong>
  <br />
  A streamlined Python application for managing simulated game activity sessions.
  <br /><br />
  <img src="https://img.shields.io/badge/Python-3.10%2B-7B68EE?style=flat-square" />
  <img src="https://img.shields.io/badge/Platform-Windows-7B68EE?style=flat-square" />
  <img src="https://img.shields.io/badge/License-MIT-7B68EE?style=flat-square" />
</p>

---

## Overview

VAULT is a lightweight, terminal-based utility built with Python. It automates Discord game activity event submission through an interactive interface.

## Features

- **Game Discovery** — Retrieves Discord's detectable game database.
- **Batch Processing** — Processes game activity events in batches.
- **Session Management** — Configurable activity durations.
- **Authentication** — Token and cookie-based authentication.
- **Fingerprint Generation** — Windows executable fingerprint support.
- **Local Persistence** — Saves configuration and usage statistics.

## Installation

```bash
git clone <repository-url>
cd <repository-name>
python vault.py
```

Alternatively, download the standalone executable from [Releases](../../releases).

## Security

Authentication credentials are stored locally in `vault.json`. Never share this file or commit it to version control.

## Disclaimer

Unofficial third-party project. Use responsibly and at your own risk. Simulated activity may violate Discord's Terms of Service.

---

<p align="center">
  <sub>VAULT · Built with Python</sub>
</p>
