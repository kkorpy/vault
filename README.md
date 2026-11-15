<div align="center">

# `vault`
### Discord Game Activity Utility

A Windows-focused Python CLI project for constructing and submitting Discord game-activity event payloads, managing local configuration, and tracking application-side counters.

<p>
  <img alt="Python" src="https://img.shields.io/badge/Python-3.12%2B-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img alt="Platform" src="https://img.shields.io/badge/Platform-Windows-0078D4?style=for-the-badge&logo=windows&logoColor=white">
  <img alt="License" src="https://img.shields.io/badge/License-MIT-8A63D2?style=for-the-badge">
</p>

**A terminal-based project for exploring Discord game-activity event formats and client-related metadata.**

</div>

---

> [!WARNING]
> **Read before running:** This project submits generated game-activity events to Discord. These events do not prove that a game was actually played, and the tool should not be represented as a genuine gameplay tracker. It interacts with undocumented/internal Discord endpoints and may violate Discord's Terms of Service or result in account restrictions. These endpoints can change or stop working without notice. Review the source and understand the risks before running it.

## Table of Contents

- [Overview](#-overview)
- [Project Features](#-project-features)
- [Project Structure](#-project-structure)
- [Technology](#-technology)
- [Local Data and Privacy](#-local-data-and-privacy)
- [Build and Release](#-build-and-release)
- [Known Limitations](#-known-limitations)
- [License](#-license)

## Overview

`vault` is a Python command-line application organized around a local state container, a game-catalog loader, event data structures, a batch-processing layer, and a colored terminal interface.

The project reads Discord's detectable-games catalog, maintains local configuration in `vault.json`, and includes a Windows-specific executable metadata/fingerprint routine. It can also be packaged as a standalone Windows executable with PyInstaller.

## Project Features

| Component | Description |
|:--|:--|
| **Game catalog** | Loads and parses the detectable-games catalog, filtering for entries with Windows executables. |
| **Session event models** | Represents launch and heartbeat-style game activity events. |
| **Batch processor** | Groups generated event payloads and reports request outcomes in the terminal. |
| **Authentication state** | Stores configured account credentials and analytics-token refresh information locally. |
| **Local counters** | Tracks submitted game entries and the duration recorded by the application. |
| **Terminal interface** | Provides timestamped, color-coded status messages and a numbered menu. |
| **Windows packaging** | Includes a PyInstaller spec and a GitHub Actions workflow for producing a Windows executable. |

##  Project Structure

```text
.
├── vault.py          # Main application
├── vault.json        # Local state (created/updated at runtime; ignored by Git)
├── vault.spec        # PyInstaller build configuration
├── release.yml       # GitHub Actions build/release workflow
├── LICENSE           # MIT License
├── .gitignore        # Excludes local and generated files
└── data/
    └── games.json    # Cached game catalog (created when fetched)
```

### Main application sections

- **Terminal output** — formatting, timestamps, colors, and status messages.
- **Vault state** — loading and saving local configuration and counters.
- **Game catalog** — downloading, parsing, filtering, and caching game entries.
- **Identity metadata** — creating session identifiers and client-property data.
- **Event construction** — building launch and heartbeat event objects.
- **Batch processing** — submitting event batches and interpreting HTTP status codes.
- **Application flow** — startup checks, menu handling, and local statistics.

## Technology

- **Python** — application logic and command-line interface
- **PowerShell** — Windows-specific executable metadata routine
- **JSON** — local state and game-catalog data
- **PyInstaller** — standalone executable packaging
- **GitHub Actions** — automated Windows build and release workflow

## Local Data and Privacy

The application writes local state to `vault.json`. The current implementation stores sensitive values such as the Discord account token and cookie as **plain text**.

- Never commit `vault.json` or share it in screenshots, logs, support requests, or public archives.
- Keep the file on a device and account you control.
- Do not paste account tokens or browser cookies into issues or pull requests.
- If a token or cookie is exposed, treat it as compromised and take appropriate account-security steps.
- Review the source before running it. The application sends authentication-related values in requests to Discord endpoints.

The `.gitignore` file excludes `vault.json`, Python cache files, and the local game-data directory. This is a safeguard, not encryption.

## Build and Release

The repository includes:

- `vault.spec` for PyInstaller configuration;
- `release.yml` for a GitHub Actions workflow that builds on a Windows runner; and
- a release artifact named `vault.exe`.

The workflow is configured to run on pushes and manual dispatches. Review its permissions and release behavior before enabling it on a public repository.

## Known Limitations

- The application relies on undocumented/internal Discord endpoints, which are not stable public APIs.
- Discord may change request formats, authentication requirements, or endpoint behavior at any time.
- The executable fingerprint routine is Windows-only.
- Local state is stored as readable JSON and is not encrypted.
- A successful HTTP response indicates request acceptance; it does not establish that the represented gameplay occurred.

## License

This project is distributed under the [MIT License](LICENSE).

---

<div align="center">

**Independent project · Not affiliated with, endorsed by, or supported by Discord Inc.**

</div>
