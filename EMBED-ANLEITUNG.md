# CLS Skool-Widgets — Hosting & Embed-Anleitung

16 interaktive Lektions-Widgets + Übersichtsseite. Alle Dateien sind **self-contained** (nur Google Fonts als externe Abhängigkeit), responsiv und im CLS-Brand (Schwarz/Amber).

## 1. Hosten (einmalig, ~5 Minuten)

Skool bettet URLs ein — die HTML-Dateien müssen also online liegen. Der schnellste Weg (kostenlos, mit Claude Code im Terminal):

```bash
cd ~/Claude/vsl-funnel/skool-widgets
gh repo create cls-widgets --public --source=. --push
```

Dann auf GitHub: Repo → Settings → Pages → Branch `main` aktivieren.
Deine Widgets liegen danach unter:

```
https://DEIN-GITHUB-NAME.github.io/cls-widgets/01-claude-im-terminal.html
```

Alternative: Vercel (`npx vercel --prod` im Ordner) oder Netlify Drop (Ordner in den Browser ziehen).

**Wichtig:** Öffentliches Hosting = die Inhalte sind technisch für jeden mit Link erreichbar. Für den Start okay (der Wert liegt in Videos + Community); wer es dicht will, hostet später hinter einem simplen Token-Link.

## 2. In Skool einbetten (pro Lektion)

In der Skool-Classroom-Lektion:

- **Add link / Embed** wählen und die Widget-URL einfügen — Skool rendert eine eingebettete Vorschau. Funktioniert je nach Skool-Plan/Umgebung unterschiedlich gut, deshalb:
- **Empfohlener Standard:** Im Lektions-Text einen klaren Button-Link setzen:
  `→ ÖFFNE DAS WIDGET ZU DIESER LEKTION: [URL]`
  Die Widgets sind mobiloptimiert und laufen im Browser-Tab perfekt — oft die bessere UX als ein gequetschtes Iframe.
- Wenn du volle iframe-Kontrolle hast (z. B. eigene Portal-Seite, Notion, Website):

```html
<iframe src="https://DEINE-DOMAIN/01-claude-im-terminal.html"
        width="100%" height="1100"
        style="border:0;" loading="lazy"></iframe>
```

Empfohlene iframe-Höhen: 01 → 1100 · 02 → 1400 · 03 → 1500 · 04 → 1200 · 05 → 1300 · 06 → 1800 · 07 → 1300.

## 3. Zuordnung Widget → Lektion

| # | Datei | Skool-Lektion | Typ |
|---|---|---|---|
| 01 | 01-claude-im-terminal.html | Setup: Claude ins Terminal | Checkliste mit Copy-Befehlen, Fortschritt via localStorage |
| 02 | 02-git-github-brew.html | Setup: Brew, Git & GitHub | Begriffs-Karten + Setup + Fehlerhilfe |
| 03 | 03-prompt-anatomie.html | Prompts: Das Briefing | Klickbare Prompt-Anatomie + Prompt-Builder |
| 04 | 04-lead-check.html | Leads: Qualifizieren | Score-Tool mit Gesprächs-Opener |
| 05 | 05-preis-rechner.html | Monetarisierung | Einkommens-Rechner mit Slidern |
| 06 | 06-outreach-cadence.html | Outreach: Der Fahrplan | Timeline mit kopierbaren Vorlagen |
| 07 | 07-einwand-trainer.html | Verkauf: Einwände | 8 Flip-Cards |
| 08 | 08-ziel-board.html | 10 · Setups & Tricks → Setup | Ziel-Board-Generator (3/6/12 Monate, Rechnung, Zeitstrahl) |
| 09 | 09-der-loop.html | 10 · Setups & Tricks → Bildlich erklärt | Klickbarer Loop, 8 Stationen mit Prompts |
| 10 | 10-arbeitsweg-methode.html | 10 · Setups & Tricks → Setup | Maps → Link → Notiz, gezeichnete Handy-Screens |
| 11 | 11-setup-handy.html | 10 · Setups & Tricks → Setup | Handy-Setup-Checkliste (Claude + Stitch) |
| 12 | 12-website-check.html | 10 · Setups & Tricks → Tricks | 10-Punkte-Check + Übergabe-Satz |
| 13 | 13-drei-designs.html | 10 · Setups & Tricks → Tricks | Drei-Design-Trick + Stitch-Prompt-Generator |
| 14 | 14-stitch-befehle.html | 10 · Setups & Tricks → Tricks | Stitch-Spickzettel mit Vorher/Nachher |
| 15 | 15-pflege-rechner.html | 10 · Setups & Tricks → Bildlich erklärt | Doppel-Schalter: einmalig + monatlich als Diagramm |
| 16 | 16-landkarte.html | 10 · Setups & Tricks → Bildlich erklärt | Die 9 Schalter als Landkarte mit Fortschritt |
| 17 | 17-esis-bereit.html | 00 · Überblick → „Esis, ich bin bereit“ (alle) + Dein Start | Codewort erklärt, Satz-Baukasten, WhatsApp-Vorschau, drei Wege |
| 18 | 18-dein-start.html | Dein Start (Premium, privat) | Zielkarte, Landkarte der 8 Wege mit Detail + Esis-Satz, 4-Fragen-Wahl, Start-Regeln |

`index.html` = Übersicht aller Widgets (z. B. als „Ressourcen"-Lektion ganz oben im Classroom verlinken).

## 4. Anpassen

- **Farben/Fonts:** oben in jeder Datei im `:root`-Block (`--am` = Amber-Akzent).
- **Preise im Rechner:** Slider-Grenzen in `05-preis-rechner.html` (`min`/`max` der `<input type=range>`).
- **Neue Einwände/Vorlagen:** einfach einen `card`-/`day`-Block duplizieren.
