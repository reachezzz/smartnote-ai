# SmartNote AI 3.0 🧠

Kostenlose, mobilfreundliche Open-Source-Notiz-App. Läuft als statische Website auf GitHub Pages.

## Funktionen
- Notizen lokal erstellen, bearbeiten, löschen, durchsuchen und favorisieren
- Regelbasierte Kategorien, kurze Zusammenfassung und Schlagwortvorschläge ohne API
- JSON-Backup und -Import
- Optionaler API-Modus über einen **eigenen HTTPS-Backend-Proxy**

## KI-Anbindung
Im API-Modus sendet die App `{ "text": "..." }` per POST an den vom Nutzer eingegebenen HTTPS-Endpunkt und erwartet JSON mit `{ "result": "Analyse..." }`. Der Endpunkt muss CORS, Authentifizierung, Rate Limits und sichere Schlüsselverwaltung selbst implementieren. **Niemals einen Anbieter-API-Schlüssel in dieser statischen Website oder im Repository speichern.** Der optionale Proxy ist nicht Bestandteil dieses Repositories. API-Nutzung kann Kosten verursachen.

## Datenschutz
Ohne API-Modus bleiben Notizen im `localStorage` des jeweiligen Browsers. Kein Login, kein Cloud-Sync. Im API-Modus wird der eingegebene Text nach ausdrücklicher Bestätigung an den ausgewählten Server übertragen. Backups regelmäßig exportieren.

## Installation
`index.html` im Browser öffnen oder GitHub Pages für den `main`-Branch im Repository aktivieren.

## Upgrade von 2.0
Diese Version verwendet einen eigenen lokalen Speicherschlüssel. Vorhandene V2-Notizen werden **nicht automatisch übernommen**. Bitte Daten vorher sichern, falls erforderlich.

## Lizenz
MIT – siehe LICENSE im bestehenden Repository.
