<div align="center">
  <img src="https://img.shields.io/badge/Chromium-4285F4?style=for-the-badge&logo=google-chrome&logoColor=white">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white">
  <img src="https://img.shields.io/badge/license-MIT-blue?style=for-the-badge">
</div>

<br>

<div align="center">
  <h1>fortress</h1>
  <p><strong>Stealth Chromium Engine</strong></p>
  <p>Stops scrapers and browser agents from getting blocked, with one line of code change.</p>
  <p>
    <a href="#features">Features</a> •
    <a href="#quick-start">Quick Start</a> •
    <a href="#how-it-works">How It Works</a> •
    <a href="#contributing">Contributing</a>
  </p>
</div>

---

## Screenshot

![fortress Architecture](docs/screenshot.png)
*Stealth Chromium engine for bypassing bot detection.*

## Features

- **Bot Detection Bypass** — Evades Cloudflare, DataDome, PerimeterX, and more.
- **One-Line Integration** — Drop-in replacement for Playwright/Puppeteer.
- **Chromium Patched** — Custom-patched Chromium engine.
- **Fingerprint Randomization** — Dynamic browser fingerprint generation.
- **Human-Like Behavior** — Realistic mouse movements and timing.
- **No Detection** — Invisible to bot detection systems.
- **Playwright Compatible** — Works with existing Playwright scripts.
- **Puppeteer Compatible** — Works with existing Puppeteer scripts.

## Quick Start

### Playwright

```python
# Before
from playwright.sync_api import sync_playwright

# After (one line change)
from fortress.playwright import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=False)
    page = browser.new_page()
    page.goto("https://example.com")
```

### Puppeteer

```javascript
// Before
const puppeteer = require('puppeteer');

// After (one line change)
const puppeteer = require('fortress/puppeteer');

const browser = await puppeteer.launch();
const page = await browser.newPage();
await page.goto('https://example.com');
```

### Installation

```bash
pip install fortress
# or
npm install fortress
```

## How It Works

1. **Chromium Patching** — Replaces standard Chromium with patched version
2. **Fingerprint Masking** — Randomizes browser fingerprint per session
3. **Behavior Simulation** — Adds human-like delays and movements
4. **Detection Evasion** — Bypasses known bot detection signatures

## Supported Detectors

| Detector | Status |
|----------|--------|
| Cloudflare | ✅ Supported |
| DataDome | ✅ Supported |
| PerimeterX | ✅ Supported |
| Akamai Bot Manager | ✅ Supported |
| Imperva | ✅ Supported |
| Custom | ⚠️ Partial |

## Configuration

| Option | Default | Description |
|--------|---------|-------------|
| `headless` | `true` | Run in headless mode |
| `stealth` | `true` | Enable stealth mode |
| `fingerprint` | `random` | Fingerprint mode (random/static) |
| `human_delay` | `true` | Add human-like delays |

## Project Structure

```
fortress/
├── fortress/
│   ├── __init__.py
│   ├── playwright/         # Playwright integration
│   │   ├── __init__.py
│   │   └── sync_api.py
│   ├── puppeteer/          # Puppeteer integration
│   │   └── index.js
│   ├── chromium/           # Patched Chromium
│   ├── fingerprint/        # Fingerprint generation
│   └── behavior/           # Human behavior simulation
├── setup.py               # Python package
├── package.json           # Node.js package
└── README.md
```

## Contributing

Contributions are welcome. Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for community standards.

## Security

For security concerns, see [SECURITY.md](SECURITY.md). Please report vulnerabilities to **info@jorahone.com** — do not use public issues.

## License

MIT © Jhonattan L. Jimenez

---

<div align="center">
  <p>Stealth Chromium for bot detection bypass.</p>
  <p><a href="https://github.com/OneByJorah">@OneByJorah</a></p>
</div>
