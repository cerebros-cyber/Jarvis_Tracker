# Mitarbeit im Blick

Web-App für das iPad auf dem Lehrerpult: Die Klasse erscheint als Sitzplan mit Fotos, und du erfasst die mündliche Mitarbeit mit einem Fingertipp.

| Geste auf dem Schülerbild | Bedeutung |
|---|---|
| 1× tippen | Meldung |
| 2× tippen | guter Beitrag |
| wischen (beliebige Richtung) | schwache Mitarbeit |
| gedrückt halten | Menü: Eintrag korrigieren, abwesend markieren, Verlauf |

## Funktionen

- **Mehrere Klassen**, umschaltbar oben links.
- **Sitzplan** mit frei wählbarer Zahl an Reihen und Plätzen. Schüler antippen und dann einen Platz antippen, um sie umzusetzen oder zu tauschen. „Ansicht drehen“ wechselt zwischen Blick vom Pult und Blick von hinten.
- **Fotos** direkt mit der iPad-Kamera aufnehmen oder aus der Fotomediathek wählen. Ohne Foto erscheinen die Initialen.
- **Namensliste einfügen**: Klassenliste kopieren und einfügen, ein Name pro Zeile.
- **Stunden** beginnen automatisch mit dem ersten Eintrag. Nach 60 Minuten ohne Eintrag (einstellbar) beginnt die nächste Stunde von selbst; „Stunde beenden“ schließt sie sofort ab.
- **Rückgängig** für versehentliche Eingaben.
- **Auswertung** für die letzte Stunde, heute, 7 Tage, 30 Tage, alles oder einen frei gewählten Zeitraum:
  - Tabelle mit Meldungen, guten Beiträgen, schwacher Mitarbeit, Punkten und Punkten je anwesender Stunde (sortierbar),
  - Sitzplan-Ansicht, die zeigt, wer wie aktiv ist,
  - Stundenliste (einzelne Stunden lassen sich löschen),
  - Verlauf je Schüler.
- **Export** als CSV (für Excel/Numbers) oder „Tabelle kopieren“ zum Einfügen.
- **Punkte** pro Ereignis einstellbar (Standard: Meldung 1, guter Beitrag 2, schwach −1).
- **Datensicherung** als Datei exportieren und wieder importieren.
- Funktioniert **offline**. Der Bildschirm bleibt während der Stunde an.

## Auf dem iPad einrichten

Die App ist eine einzelne Webseite (`index.html`) und muss einmal irgendwo über HTTPS erreichbar sein. Danach läuft sie auch ohne Internet.

1. **Veröffentlichen**, zum Beispiel mit GitHub Pages: Im Repository unter *Settings → Pages* die Quelle *Deploy from a branch* wählen, den Branch und den Ordner `/ (root)` einstellen und speichern. Nach etwa einer Minute ist die App unter der angezeigten Adresse erreichbar.
   Alternativ den Ordner auf einen beliebigen Webspace laden oder per Drag-and-drop bei Netlify Drop hochladen.
2. Die Adresse auf dem iPad in **Safari** öffnen.
3. **Teilen-Symbol → „Zum Home-Bildschirm“** antippen. Die App erscheint dann mit eigenem Symbol und startet im Vollbild.

Beim ersten Start ist eine Beispielklasse mit erfundenen Namen angelegt, damit du alles ausprobieren kannst. Über das Klassen-Menü oben links (*Klassen verwalten …*) legst du deine eigenen Klassen an und löschst die Beispielklasse.

## Datenschutz

Alle Namen, Fotos und Einträge werden **nur lokal auf dem iPad** gespeichert (im Browser-Speicher der App). Es gibt keinen Server und keine Übertragung. Daraus folgt:

- Exportiere regelmäßig eine **Sicherung** (Zahnrad → *Sicherung exportieren*), zum Beispiel in die Dateien-App. Wenn die App vom Home-Bildschirm gelöscht oder der Safari-Verlauf samt Website-Daten gelöscht wird, sind die Daten sonst weg.
- Die Sicherungsdatei enthält personenbezogene Daten und Fotos. Bewahre sie entsprechend geschützt auf und beachte die Vorgaben deiner Schule zum Umgang mit Schülerdaten.
- Das iPad sollte mit Code gesperrt sein.

## Dateien

- `index.html` – die komplette App (HTML, CSS, JavaScript)
- `manifest.webmanifest`, `icons/` – App-Name und Symbol für den Home-Bildschirm
- `sw.js` – Offline-Unterstützung
