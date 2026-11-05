# 🧠 SmartNote AI 4.0

Kostenlose, mobilfreundliche Open-Source-Notiz-App mit lokaler Textanalyse und optionaler Anbindung an einen **eigenen** KI-Proxy.

## Funktionen
- Notizen erstellen, bearbeiten, löschen, durchsuchen und favorisieren
- Kategorien, lokale regelbasierte Zusammenfassung und Schlagwörter (keine echte KI im kostenlosen Modus)
- JSON-Export und Import
- Optionale Auswahl von Claude, OpenAI oder Gemini über einen selbst betriebenen HTTPS-Proxy
- Keine Registrierung, kein Tracking, keine externen Abhängigkeiten im Frontend

## Nutzung
`index.html` öffnen oder per GitHub Pages bereitstellen. Daten werden unter dem bestehenden LocalStorage-Schlüssel `smartnote-v3` gespeichert, sodass Notizen aus Version 3.0 im selben Browser und unter derselben Domain weiter sichtbar bleiben sollten. **Vor einem Update bitte ein JSON-Backup erstellen.** Daten werden nicht zwischen Browsern synchronisiert.

## Optionaler KI-Proxy
Der Browser sendet nur nach Bestätigung einen POST an die eingegebene HTTPS-URL:

```json
{"provider":"anthropic","text":"Beispielnotiz"}
```

Der eigene Proxy soll mit JSON antworten:

```json
{"result":"Zusammenfassung und Analyse ..."}
```

Er muss API-Schlüssel **serverseitig** verwahren, Authentifizierung, Missbrauchsschutz, geeignete CORS-Regeln und HTTPS unterstützen. **Keinen geheimen Schlüssel in GitHub, HTML, JavaScript oder einer öffentlich erreichbaren Proxy-URL speichern.** Eine Server-Implementierung ist nicht enthalten. KI-API-Anfragen können Kosten verursachen. Claude Max beinhaltet nicht automatisch API-Guthaben.

## Datenschutz und Grenzen
- Lokal gespeicherte Notizen sind nicht verschlüsselt und können bei gelöschten Browserdaten verloren gehen.
- Im kostenlosen Modus erfolgt keine Übertragung der Notizen.
- Bei Proxy-Nutzung wird der analysierte Text an den gewählten Proxy übertragen.
- Die lokale Zusammenfassung ist regelbasiert und nicht mit einem Sprachmodell vergleichbar.

## Lizenz
MIT, siehe `LICENSE` im bestehenden Repository.
