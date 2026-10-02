# Mitarbeit im Blick

Web-App für das iPad auf dem Lehrerpult: Die Klasse erscheint als Sitzplan mit Fotos, und du erfasst die mündliche Mitarbeit mit einem Fingertipp. Das Design folgt der NGG-Präsentationsvorlage „Start-A-Klar“: Farbschema „NGG Klar“ (Rot #DC3545, Dunkelrot #A82834, Dunkel #1D1D1B, Grau #5A5A5A/#9B9B9B, Blaugrau #6E7C83, Zartrosa #FDF3F4), Schrift Segoe UI Light (auf dem iPad SF Light), rote Kopfzeile, Titel mit roter Akzentlinie, Fußzeile mit Haarlinie und Campus-Glienicke-Logo.

| Geste auf dem Schülerbild | Bedeutung |
|---|---|
| 1× tippen | Meldung |
| 2× tippen | guter Beitrag |
| wischen (beliebige Richtung) | schwache Mitarbeit |
| gedrückt halten | Menü: Eintrag korrigieren, abwesend markieren, Verlauf |

## Funktionen

- **Mehrere Klassen**, umschaltbar oben links.
- **Sitzplan** mit frei wählbarer Zahl an Reihen und Plätzen. Schüler antippen und dann einen Platz antippen, um sie umzusetzen oder zu tauschen. „Ansicht drehen“ wechselt zwischen Blick vom Pult und Blick von hinten.
- **Fotos** einzeln beim Schüler (Kamera oder Fotomediathek) oder **gesammelt hochladen** (siehe unten). Ohne Foto erscheinen die Initialen.
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
- **Vollbild-Knopf** oben rechts: blendet die Fußzeile aus und schaltet, wo der Browser es erlaubt, in den Vollbildmodus. Die Gesten-Leiste und der Hinweis zur Beispielklasse lassen sich ausblenden, damit der Sitzplan möglichst groß ist.
- Funktioniert **offline**. Der Bildschirm bleibt während der Stunde an.

## Schülerfotos hochladen

Im Reiter **Sitzplan → „Fotos hochladen“** kannst du viele Fotos auf einmal auswählen (auf dem iPad aus der Fotomediathek oder der Dateien-App).

- **Automatische Zuordnung über den Dateinamen:** Heißt eine Datei wie der Schüler, wird sie direkt zugeordnet. Groß-/Kleinschreibung, Reihenfolge und Umlaute spielen keine Rolle: `Lena Albrecht.jpg`, `albrecht_lena.png`, `Becker, Jonas.jpg` oder `krueger-noah.jpg` werden erkannt. Ein eindeutiger Vorname reicht ebenfalls.
- **Der Reihe nach zuordnen:** Fotos ohne passenden Namen (z. B. `IMG_1234`) werden den Schülern ohne Foto in Sitzplan-Reihenfolge zugeteilt, von vorne links nach hinten rechts. Fotografierst du die Klasse in Sitzreihenfolge, passt das sofort.
- Jede Zuordnung lässt sich vor dem Übernehmen per Auswahlliste ändern. Zu Fotos mit Namen kannst du auch **neue Schüler anlegen** lassen.
- Am Mac oder PC kannst du Fotos auch per Drag-and-drop auf die Seite ziehen, ein einzelnes Foto direkt auf einen Schüler.

Die Fotos werden quadratisch zugeschnitten und verkleinert gespeichert (ca. 20–30 KB pro Bild).

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
