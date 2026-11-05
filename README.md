# 🧠 SmartNote AI — Version 2.0

A privacy-conscious, responsive, open-source notes workspace.

**Live demo:** https://reachezzz.github.io/smartnote-ai/

## Features
- Create, edit and delete notes
- Search notes and filter by category or favorites
- Offline, rule-based category suggestions and extractive previews (not generative AI)
- JSON backup export and import
- Responsive dark-mode dashboard
- Local browser storage, no account or server required

## Run
Open `index.html` in a browser or deploy this repository with GitHub Pages (`main` / root).

## Privacy and limitations
Notes are stored in the current browser's `localStorage`, **not encrypted** and **not synced**. Clearing site data removes them. Export backups regularly. Do not store sensitive secrets on shared devices.

The offline tools are deterministic heuristics; **there is no Claude API integration yet**. A future integration must use a server-side proxy with authentication, quotas, abuse protection and a server-held API key. Never put API keys in public JavaScript or GitHub commits. Claude subscriptions and API billing are separate.

## Roadmap
- Optional secure server-side AI analysis
- Automated tests and accessibility improvements
- Optional encrypted sync
- User-controlled tags

## License
MIT (see LICENSE).
