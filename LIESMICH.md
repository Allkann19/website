# sachsenenergie-glasfaser.de — sauberes Website-Projekt

Eigenständiger Nachbau der Website als reines HTML/CSS — unabhängig vom Hostinger-Baukasten,
frei bearbeitbar und beliebig erweiterbar. Ersetzt die bisherigen Custom-HTML-Embed-Blöcke.

## Aufbau
```
website/
├── index.html                        → Startseite (Home)
├── termine.html → Termine
├── livestream-infoveranstaltung.html → Livestream
├── unterlagen.html                   → Unterlagen / Downloads
├── impressum.html                    → Impressum
├── livestream.html                   → Stream-Seite hinter dem Button (war passwortgeschützt)
└── assets/
    └── styles.css                    → gemeinsames Stylesheet (alle Seiten)
```

Jede Seite ist eine eigene Datei mit identischem Kopf (Logo + Navigation) und greift auf das
gemeinsame `assets/styles.css` zu. Design-Farben und Schrift sind als CSS-Variablen oben in
`styles.css` zentral hinterlegt (`--red` = SachsenEnergie-Rot, Schrift „Roboto").

## Ändern
- **Texte/Termine ändern:** in der jeweiligen `.html`-Datei den Text bearbeiten.
- **Neuen Termin hinzufügen:** in `termine.html` einen `<article class="ga-event">`-Block kopieren.
- **Neue Seite anlegen:** eine bestehende `.html` kopieren, Inhalt anpassen, in der Navigation aller Seiten verlinken.
- **Design anpassen:** Farben/Abstände zentral in `assets/styles.css`.

## Veröffentlichen (Hostinger Premium Web Hosting)
Zwei Wege:
1. **Datei-Manager (hPanel):** den Inhalt des Ordners `website/` in das Web-Verzeichnis hochladen.
2. **Git-Deployment:** Ordner als GitHub-Repo verbinden → Hostinger stellt Änderungen automatisch live.

Tipp: zuerst auf einer Test-Subdomain prüfen, dann die Domain `sachsenenergie-glasfaser.de`
auf das neue Verzeichnis zeigen lassen. Die alte Baukasten-Seite bleibt bis dahin online.

## Offene Punkte
- **Download-Dateien (Unterlagen):** alle PDF-Links sind aktuell Platzhalter (`href="#"`) —
  exakt wie auf der bisherigen Live-Seite. Sobald die PDFs vorliegen, hier verlinken.
- **Fotos der Ansprechpartner:** statt Fotos werden aktuell Monogramme (JH/JW) gezeigt.
  Echte Fotos können in `index.html` im Block `.ga-person` ergänzt werden.
- **Saubere URLs ohne `.html`:** beim Hosting via Regel (.htaccess) oder Ordnerstruktur einrichten.
- **Stream-Seite (`livestream.html`):** Der Video-Einbettungslink und der direkte Teilnahme-Link
  sind Platzhalter (`HIER_TEAMS_EMBED_URL_EINSETZEN` / `HIER_TEAMS_JOIN_LINK_EINSETZEN`) – wie im
  Original. Vor einer Veranstaltung die echten Teams-Links eintragen.
- **Passwortschutz der Stream-Seite:** Die Seite war auf Hostinger per Passwort („Glasfaser")
  geschützt. Das ist eine Server-Einstellung und muss beim neuen Hosting neu eingerichtet werden
  (hPanel: Verzeichnis-/Passwortschutz oder `.htaccess`). Statisches HTML allein bietet keinen Schutz.
