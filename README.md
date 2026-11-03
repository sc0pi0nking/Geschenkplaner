# 🎄 Geschenkeplaner

Kleine Web-App zum Planen der Weihnachtsgeschenke: Personen mit Budget, Geschenkideen mit Preis, Link und Status, Kennzahlen zu Budget und Fortschritt.

Läuft komplett im Browser, ohne Server und ohne Account. Lässt sich auf dem Handy wie eine App installieren und funktioniert danach auch offline.

## Funktionen

- **Personen mit Budget** und Fortschrittsbalken (rot bei Überschreitung)
- **Geschenke** mit Preis, Link, Notiz und Status: Idee → Bestellt → Angekommen → Verpackt → Verschenkt
- **Kennzahlen**: Budget, geplant, ausgegeben, Kaufquote, versorgte Personen, verpackt, Pakete unterwegs, offene Beträge von Mitschenkern
- **Steckbrief pro Person**: Kleider- und Schuhgröße, Lieblingsfarbe, mag / mag nicht, Notizen
- **Mitschenker**: Anteile in %, Betrag wird berechnet, Häkchen für „bezahlt“. Ins Budget zählt nur dein eigener Anteil
- **Sendungsverfolgung**: erscheint bei Status „Bestellt“; Versanddienst wählen, Nummer eintragen, „Verfolgen →“
- **Ideen-Inbox**: Ideen ohne Person notieren und später per Auswahl einer Person zuordnen
- **Verpackungs-Checkliste** mit eigenen Punkten
- **Rückgängig**: nach jedem Löschen 5 Sekunden lang
- **Darstellung**: Auto / Hell / Dunkel über den Knopf oben rechts
- **Vorzeige-Modus (⛶)**: zeigt nur eine Person im Vollbild, Preise optional. Schließen nur durch Gedrückthalten, damit niemand versehentlich in die Gesamtliste kommt
- **Ausblenden (🙈)**: versteckt einzelne Personen in der Liste; wieder anzeigen nur durch Gedrückthalten
- **Schnee am 24.12.** (Vorschau: 5× schnell auf den 🎄 tippen)

## Auf GitHub veröffentlichen (ca. 5 Minuten)

1. Auf github.com ein neues Repository anlegen, z. B. `geschenkeplaner`. Sichtbarkeit **Public** (GitHub Pages ist im kostenlosen Plan nur für öffentliche Repos verfügbar).
2. Dateien hochladen: im Repo auf **Add file → Upload files**, den gesamten Inhalt dieses Ordners reinziehen (inklusive `icons/`), dann **Commit changes**.
   Alternativ per Terminal:
   ```bash
   git init
   git add .
   git commit -m "Geschenkeplaner"
   git branch -M main
   git remote add origin https://github.com/DEIN-NAME/geschenkeplaner.git
   git push -u origin main
   ```
3. Im Repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, Branch `main`, Ordner `/ (root)`, **Save**.
4. Nach ca. 1–2 Minuten ist die App erreichbar unter
   `https://DEIN-NAME.github.io/geschenkeplaner/`

## Aufs Handy holen

- **iPhone (Safari):** Link öffnen → Teilen-Symbol → **Zum Home-Bildschirm**.
- **Android (Chrome):** Link öffnen → Drei-Punkte-Menü → **App installieren** bzw. **Zum Startbildschirm hinzufügen**.

Danach startet die App im Vollbild ohne Browserleiste.

## Wichtig zu den Daten

- Die Daten liegen **nur lokal auf dem jeweiligen Gerät**. Das Repo ist zwar öffentlich, deine Geschenkliste aber nicht: Sie wird nie hochgeladen.
- Handy und Laptop teilen sich die Daten **nicht** automatisch. Übertragen geht über **Export (JSON)** auf dem einen Gerät und **Import** auf dem anderen.
- iPhone: Safari kann Daten von Web-Apps löschen, die mehrere Wochen nicht geöffnet wurden. Als Home-Bildschirm-App ist das deutlich robuster, ein gelegentlicher Export als Backup schadet trotzdem nicht.

## Updates einspielen

Nach einer Änderung an den Dateien in `sw.js` die Zeile `const VERSION = 'v1';` hochzählen (`v2`, `v3`, …) und neu pushen. Die App lädt die neue Version dann beim nächsten Öffnen mit Internet.

## Dateien

| Datei | Zweck |
| --- | --- |
| `index.html` | Die komplette App (Oberfläche + Logik) |
| `manifest.webmanifest` | Name, Farben und Icons für die Installation |
| `sw.js` | Service Worker für Offline-Betrieb |
| `icons/` | App-Icons für Android und iOS |
