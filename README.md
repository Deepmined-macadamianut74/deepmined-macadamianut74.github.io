# Webseite Tobias Rothmund

Zweisprachige Wissenschaftler-Webseite (Deutsch/Englisch) mit Blog, gebaut mit [Hugo](https://gohugo.io).
Keine Datenbank, keine Plugins, keine Cookies, keine Drittanbieter – alle Inhalte sind einfache Textdateien.

---

## 1. Einmalig: Seite online stellen (ca. 15 Minuten)

1. **GitHub-Konto** anlegen: <https://github.com/signup>
2. **Neues Repository** erstellen: <https://github.com/new>
   - Name: `<ihr-nutzername>.github.io` (dann läuft die Seite direkt unter `https://<ihr-nutzername>.github.io`)
   - Sichtbarkeit: *Public*
3. **Dateien hochladen**: Im neuen Repository auf *uploading an existing file* klicken und den gesamten Inhalt dieses Ordners hineinziehen (inkl. des versteckten Ordners `.github`). Tipp: Mit [GitHub Desktop](https://desktop.github.com) geht das bequemer.
4. **Veröffentlichen einschalten**: *Settings → Pages → Build and deployment → Source:* **GitHub Actions** wählen.
5. Nach 1–2 Minuten ist die Seite online. Den Fortschritt sehen Sie unter dem Reiter *Actions*.

**Eigene Domain** (z. B. `tobiasrothmund.de`): Unter *Settings → Pages → Custom domain* eintragen und beim Domain-Anbieter die dort angezeigten DNS-Einträge setzen.

---

## 2. Einen Blogbeitrag schreiben

**Im Browser (am einfachsten):**

1. Im Repository zu `content/de/blog/` gehen → *Add file → Create new file*
2. Dateiname, z. B. `vertrauen-in-wissenschaft.md` (klein, ohne Leerzeichen – wird zur Adresse)
3. Diesen Kopf einfügen und darunter schreiben:

```markdown
---
title: "Titel des Beitrags"
date: 2026-10-01
tags: ["Desinformation", "Medien"]
summary: "Ein bis zwei Sätze, die in der Übersicht erscheinen."
---

Hier beginnt der Text. Absätze durch Leerzeilen trennen.

## Zwischenüberschrift

Text mit **Fettdruck**, *Kursivschrift* und [Links](https://example.org).
```

4. Unten auf **Commit changes** klicken. Nach ca. einer Minute ist der Beitrag online.

**Nützliches:**

| Wunsch | So geht's |
|---|---|
| Entwurf, noch nicht veröffentlichen | `draft: true` in den Kopf schreiben |
| Beitrag zu einem späteren Termin veröffentlichen | Zukünftiges Datum eintragen – die Seite wird täglich um 7 Uhr neu gebaut |
| Englische Fassung | Gleichen Dateinamen in `content/en/blog/` anlegen. Der Sprachumschalter verknüpft beide automatisch (oder `translationKey: gleicher-name` in beide Köpfe schreiben) |
| Inhaltsverzeichnis am Rand | `toc: true` in den Kopf |
| Bild einfügen | Bild nach `static/images/` hochladen, im Text: `![Beschreibung](/images/bild.jpg)` |
| Fußnote | `Text.[^1]` und am Ende `[^1]: Quelle.` |

Alle Gestaltungsmöglichkeiten zeigt der Beispielbeitrag `content/de/blog/formatierung.md` (kann danach gelöscht werden).

---

## 3. Publikationen, Vorträge & Interviews pflegen

Diese stehen **nicht** in einzelnen Seiten, sondern in zwei Listen – einmal gepflegt, erscheinen sie automatisch auf Deutsch und Englisch:

- `data/publications.yaml` – Publikationen (Filter & Suche entstehen automatisch)
- `data/talks.yaml` – Vorträge, Keynotes, Interviews, Podcasts, TV, Presse

Einfach einen vorhandenen Eintrag kopieren und anpassen. Auf **Einrückung** achten (zwei Leerzeichen). Mit `selected: true` erscheint eine Publikation auf der Startseite. Zukünftige Vorträge werden automatisch als „demnächst“ markiert.

⚠️ **Alle Einträge mit „[Beispiel]“ sind Platzhalter** und müssen ersetzt werden.

---

## 4. Wo steht was?

| Inhalt | Datei |
|---|---|
| Name, E-Mail, Profil-Links, Porträtfoto | `hugo.toml` (Abschnitt `[params]`) |
| Titel/Rolle je Sprache, Menüpunkte | `hugo.toml` (Abschnitt `[languages]`) |
| Startseite: Einleitungssatz & Forschungsschwerpunkte | `content/de/_index.md`, `content/en/_index.md` |
| Forschungsprojekte (je Projekt eine Datei) | `content/de/forschung/`, `content/en/research/` |
| Über mich / Lebenslauf | `content/de/about.md`, `content/en/about.md` |
| Impressum & Datenschutz | `content/de/impressum.md`, `content/de/datenschutz.md` |
| PDFs zum Download | `static/pdf/` (Link: `/pdf/datei.pdf`) |
| Farben & Gestaltung | `assets/css/main.css` (ganz oben) |

**Porträtfoto:** Bild (Hochformat, ca. 4:5) nach `static/images/portrait.jpg` hochladen und in `hugo.toml` `portrait = "/images/portrait.jpg"` eintragen.

**Adresse der Seite:** In `hugo.toml` `baseURL` auf die endgültige Adresse setzen (bei GitHub Pages wird sie automatisch gesetzt).

---

## 5. Lokal ansehen (optional)

Wer Änderungen vor dem Veröffentlichen ansehen möchte: [Hugo installieren](https://gohugo.io/installation/) (Version ≥ 0.146, „extended“), dann im Ordner:

```
hugo server
```

und <http://localhost:1313> im Browser öffnen. Änderungen erscheinen sofort.

---

## Hinweise

- **Impressum & Datenschutz** sind Vorlagen und müssen mit echten Angaben ergänzt und ggf. geprüft werden.
- Die Schrift *Inter* wird lokal ausgeliefert (kein Google-Fonts-Aufruf, DSGVO-freundlich). Lizenz: SIL Open Font License, siehe `static/fonts/Inter-LICENSE.txt`.
- Die Seite unterstützt automatisch Hell-/Dunkelmodus, Mobilgeräte, RSS-Feed (`/blog/index.xml`), Sitemap und Suchmaschinen-Metadaten.
