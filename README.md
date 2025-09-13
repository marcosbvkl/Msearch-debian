# Msearch (SerpAPI CLI)

Msearch is a simple command‑line tool that fetches Google results using SerpAPI and prints a readable summary. It prefers the AI Overview when available; otherwise falls back to common fields (answer box, knowledge graph, or top organic snippet). It can also print sources when present.

## Requirements
- Linux with `dpkg` (Debian/Ubuntu and derivatives)
- `python3` (3.8+)
- A SerpAPI key (paid beyond free/trial)

## Install
1. Open a terminal in this folder (Desktop/Msearch).
2. Install the package:
   sudo dpkg -i msearch_1.0.0_all.deb

> If `dpkg` reports missing dependencies, run: `sudo apt -f install` and re-run the install.

## Configure API key
Set your SerpAPI key in your shell environment. Two options:

- One‑time for current terminal:
  export SERPAPI_API_KEY=YOUR_KEY

- Persist for all terminals (recommended):
  echo 'SERPAPI_API_KEY=YOUR_KEY' >> ~/.api_keys
  echo 'source ~/.api_keys' >> ~/.bashrc
  # restart the terminal or: source ~/.bashrc

Msearch also auto‑loads `SERPAPI_API_KEY` from `~/.api_keys` if present.

## Usage
- Basic:
  msearch "your query"

- Locale:
  msearch --hl en --gl US "your query"

- Show sources when available:
  msearch --sources "your query"

- Raw JSON (debugging):
  msearch --json "your query"

Examples:
- msearch "what is api"
- msearch --sources --hl en --gl US "vitamin d deficiency symptoms"

## Uninstall
sudo apt remove msearch

## Notes
- AI Overview is not guaranteed for all queries/locales. When it’s missing, Msearch prints a reasonable fallback.
- This package installs the `msearch` command to `/usr/bin/msearch`.
