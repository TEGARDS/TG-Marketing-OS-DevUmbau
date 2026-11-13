# Entscheidungen P1: Reviewer, Designsystem, Medien

Stand 14.11.2026 · Grilling abgeschlossen, Codex-Review (gpt-6-astra, xhigh, 9 Befunde) eingearbeitet · Grundlage: `docs/umbau/dossiers/01-reviewer-design-medien.md`
Teile wurden in der Nebensession (btw-Session) entschieden und per Nachricht übernommen. Q-Nummern folgen dem Grilling, nicht der Fragenliste im Dossier.

---

## Teil A: Reviewer

### A1 Ein Prüfweg mit zwei Rubriken (Q1)
- **Ergebnis:** Der Workspace prüft über **einen** Weg: Everlast `tools/juror.ts` (`codex exec -s read-only --ephemeral`,
  leerer Temp-Ordner als Arbeitsverzeichnis = kalter Read, festes Ausgabeformat, Urteil per `-o` als Datei).
  Es gibt zwei Rubriken: **Inhalt** (Everlast-Skeptiker-Pass und eingebaute 6-Punkte-Bildrubrik) und **Bau** (neue Rubrik-Datei mit Umfangsblock, siehe A2).
  three-brain kommt **nicht** in den Workspace.
- **Geltungsbereich (Codex-Befund #3):** A1 regelt den **externen Codex-Prüfweg**, also wie Codex aufgerufen wird. Ob die Everlast-Challenge
  (`/amm-challenge`, Rule `challenge-vor-handwerk`: drei Teams, drei Juroren auf verschiedenen Modellen, einer davon über `juror.ts`)
  übernommen wird, entscheidet die Inventur in P9. Wird sie übernommen, ist `juror.ts` dort der Codex-Juror.
- **Inhaltsrubrik je Auftragsart (Codex-Befund #2):** Der Skeptiker-Pass gilt bei Everlast nur für große Stücke des `content-marketer`
  (`content-marketer-pruefung.md`). Er verlangt einen weichen CTA und würde Verkaufstexte des `copywriter` fälschlich beanstanden.
  Die Rubrik wird daher je Auftragsart gewählt. Die Zuordnung Rubrik ↔ Content-Fähigkeit entscheidet P4.
- **Urteil dauerhaft (Codex-Befund #4):** `juror.ts` löscht seinen Temp-Ordner, das Urteil bleibt nur mit `--out` erhalten.
  Der Juror läuft deshalb immer mit `--out`, das Urteil liegt neben dem Prüfgegenstand (Dateiname P7). Kein Ledger.
- **Begründung:** Real genutzt wird von three-brain nur ein Pfad: Codex-Review mit Umfangsblock und fester Befundliste
  (Beleg `E:\TG Design\three-brain-out\log.md`). Fehlerzähler, Risikopfade, Konsens-Modus und Vollständigkeits-Verfahren decken
  keinen heutigen Fall des Marketing-Workspace ab. `juror.ts` ist eine Datei mit einem Aufruf und Everlast-treu.
- **Verworfen:** Everlast 1:1 ohne Bau-Rubrik (Bau-Reviews hätten keinen Weg), three-brain weiterführen (454 Zeilen Skill +
  6 Routing-Dateien, zweite Routing-Quelle neben Head-Abschnitt 5), nur Codex-Plugin (Git-Diff-zentriert, keine Rubrik, kein kalter Read).

### A2 Umfangsblock Pflicht in der Bau-Rubrik (Q2)
- **Ergebnis:** Jede Bau-Prüfung ordnet Befunde ein als *Fehler / Ergänzung / Begründung trägt nicht*. Ergänzungen gehen nach `SPAETER.md`.
  Die Inhalts-Rubrik bleibt bei „hält / hält nicht“ mit Zitat.
- **Begründung:** Wertvollster Teil von three-brain, setzt die Regel gegen Overengineering direkt um.

### A3 Modell und Denkstufe fest im Aufruf (Q14, Q15)
- **Ergebnis:** Bau-Rubrik `gpt-6-astra`, `xhigh`; Inhalts-Rubrik `gpt-6-astra`, `medium`. Beides steht fest im Juror-Aufruf
  (`-m …`, `-c model_reasoning_effort=…`). Kein Modellwahl-Gate, keine Ledger-Zeilen, keine Auftragsdatei mit Kopfzeilen im Workspace.
- **Begründung:** Bauentscheidungen lohnen die Tiefe. Inhaltsprüfungen sind häufig, Everlast fährt sie auf `medium`.
  Mit der Wahl an genau einer Stelle wird ein Gate überflüssig, das Urteil liegt per `--out` als Datei vor (A1).
  Beleg für `xhigh` bei Bau: 08.11.2026 lieferten drei Reviews 11/14/18 Befunde, fast alle echt. Bei Inhalten kommt die Qualität aus Rubrik und kaltem Read.
- **Startphase:** Die ersten 5–10 Inhaltsprüfungen laufen doppelt (`medium` und `xhigh`). Findet `xhigh` regelmäßig etwas, das `medium` übersieht, wird hochgestellt.
  Grund: Es gibt keinen eigenen Vergleich.
- **Verworfen:** überall `xhigh` (langsam bei vielen Text-Prüfungen), überall `medium` (zu flach für Bau).

### A4 Rückfall ohne Codex (Q3)
- **Ergebnis:** Inhalte prüft ein Claude-Modell, das **nicht** das Modell des Erzeugers ist (Texte von Opus → Sonnet, Bilder/Videos von
  `grafik-designer`/`video-cutter` auf Sonnet → Opus), mit sichtbarem Hinweis „Juror nicht verfügbar, Rückfall <Modell>“ (Everlast `juror.ts check`, Exit 3).
  Bau-Prüfungen bleiben „offen“, kein „fertig“, bis Codex wieder verfügbar ist.
- **Begründung:** Everlast: „Der Prüfer ist nie das Modell des Erzeugers“ (`head-of-marketing.md`, Abschnitt 5). Ein pauschaler Sonnet-Rückfall
  wäre bei `grafik-designer` und `video-cutter` (beide Sonnet) ein Selbst-Review (Codex-Befund #1). Content soll nicht blockieren.
  Für Bau gilt „kein Selbst-Review“: Claude prüft nicht Claude.
- **Verworfen:** pauschal Sonnet als Rückfall.

### A5 agy/Antigravity (Q4)
- **Ergebnis:** Der agy-Teil kommt nicht in den Workspace (inkl. Rollen `handwerkskritiker-design`, `bulk-mechanisch`). → `SPAETER.md`.
- **Begründung:** Nie genutzt. Falls Videoanalyse real gebraucht wird, reicht das vorhandene antigravity-Plugin ohne Routing-Schicht.

### A6 Codex-Plugin (Q5)
- **Ergebnis:** Bleibt installiert für gelegentliche Code-Reviews (`/codex:adversarial-review`, `/codex:rescue`). Stop-Gate dauerhaft aus.
  Der Workspace baut nichts darauf auf.
- **Begründung:** Das Gate prüft nur Codeänderungen und kann lange Claude/Codex-Schleifen erzeugen.

### A7 Laufzeit Bun (Q17)
- **Ergebnis:** Bun wird installiert, `juror.ts` und die übrigen Everlast-TS-Werkzeuge bleiben 1:1.
  Bedingung ist ein Test in P7: (1) startet `Bun.spawnSync(["codex"])` den npm-Starter `codex.cmd` korrekt, (2) läuft der Steuerstand
  mit `Bun.serve` unter Windows. Scheitert der Test, wird auf Node 24 portiert (führt TS direkt aus; ca. 60 Bun-Aufrufe in 43 Dateien umstellen).
- **Begründung:** Code bleibt identisch mit dem erprobten Everlast-Code, kein Fehlerrisiko durch Umschreiben, Vergleiche mit neuen
  Everlast-Versionen bleiben lesbar. Eine zweite Laufzeit stört nicht. Mac-spezifische Teile (`sips`, `which`, `/opt/homebrew`, `/`)
  müssen in beiden Fällen angepasst werden.
- **Verworfen:** Python-Portierung (Neuschreiben), Node-Portierung vorab ohne Test.

### A8 three-brain und globale CLAUDE.md bis P6 (Q16)
- **Ergebnis:** three-brain und die globale Regel „Reviews über `agentic-os:three-brain`“ bleiben für alle anderen Projekte bis P6 unverändert.
- **Offen P6:** Globale Regel auf den Juror-Weg umstellen oder auf „außerhalb des Workspace“ beschränken.
  Stehende Wahl `gpt-6-astra, xhigh` mit A3 abgleichen (Inhalt `medium`). `~/.codex/config.toml` steht auf `medium` (Querbefund STAND.md).

---

## Teil B: Designsystem

### B1 Ort = B-2 + Vorschau-Fix (Q6)
- **Ergebnis:** `E:\TG Design\designsystem\` bleibt Bau- und Publish-Ort. Der Workspace bekommt nur ein Destillat
  (`brand-design/design-tokens.md`, `bildsprache.md`; Kopf: Artefakt-Link, Version, Pfad zu `components\`).
  Der Generator in `E:\TG Design\tools` macht die `preview.html` eigenständig (`bundle.css`, `@font-face ../../fonts`,
  `/_blob/<hash>` → lokale `assets`-Pfade). Abnahme: 3–4 Komponenten online vs. lokal in gleicher Breite (aus `@dsCard`),
  Schrift, Farben, Kanten und Logos gleich. Bis dahin lesen Agenten lokal nur Code, Sichtreferenz ist nur das Online-Artefakt.
- **Leser:** `webdesigner` und `ux-ui-designer` (Tokens + Komponenten-READMEs), `grafik-designer` und `video-cutter` (Tokens, Bildsprache, Logos/Assets).
- **Begründung:** Everlast-Struktur bleibt, `prime-design` bleibt klein, das bewährte Publish-Verfahren wird nicht umgebaut.
  Befund: Die 55 lokalen `preview.html` sind „nackt“ (kein `bundle.css`, kein `@font-face`, Bilder als `/_blob/`, nur auf claude.ai auflösbar).
  Graue data-SVG-Platzhalter sind absichtlich.
- **Verworfen:** B-1 (alles in den Strategieordner: Kontextkosten, Generator ist kein Strategie-Inhalt), B-3 (Workspace wird Bau-Repo des Designsystems),
  nur Cloud (Agenten können nicht greppen, WordPress-HTML braucht Dateien).
- **DesignSync:** Werkzeug für claude.ai/design-Projekte (eigenständiges Claude Design schließt am 14.12.2026). Betrifft das Artefakt nicht,
  der Weg bleibt Artifact `read`/`publish`.
- **Offen P7:** Bau der Generator-Änderung, Zuordnung `_blob`-Kennungen → Dateien in `assets\`.

### B2 Destillat aktuell halten (Q18)
- **Ergebnis:** Fester letzter Schritt im Publish-Ablauf der `ANLEITUNG.md` in `E:\TG Design\designsystem\`: Destillat nachziehen und die
  Version im Destillat-Kopf anheben. Prüfung mit einem Blick: Version im Destillat = Version in der ANLEITUNG. Kein Sync-Werkzeug.
- **Verworfen:** Nachziehen per Einzelauftrag (wird vergessen).
- **Offen P7:** Zeile in der ANLEITUNG ergänzen (liegt außerhalb dieses Repos).

### B3 `ui-styling` und Skill `design-system` (Q7)
- **Ergebnis:** Beide nicht übernehmen, → `SPAETER.md` mit Auslöser.
- **Begründung:** Everlast führt `ui-styling` selbst unter „Nicht benutzen“ (`webdesigner-werkzeuge.md`), `design-system` nur situativ bei
  echtem Token-Neubau. Kein Agent lädt sie vor. Der `webdesigner` baut nur aus TG-Komponenten als Raw-HTML (`.tg-ds` + `bundle.css`, WPBakery oder Gutenberg).
- **Offen P4:** Andere Formate (Social, Ads, Plakat, Motion, Slides) laufen über die Content-Skills, die `design-tokens.md` lesen, Entscheidung je Skill.
  Newsletter hat bei Everlast keinen Design-Skill. **Offen P3/P4/P7:** Wie `bundle.css` auf die Website kommt.
  Inhalte aus `E:\TG Design\ausgelagert\` gehen in P3/P4, nicht ins Design.

---

## Teil C: Medien

### C1 Generierung nur mit OpenArt (Q8)
- **Ergebnis:** Der Medien-Zyklus (Bestand zuerst, Kosten und Freigabe, Erzeugen, Ablage mit `lauf.json`) läuft nur mit der OpenArt-CLI
  (`openart.exe` 0.1.1, angemeldet, Plan Plus, 12.000 Credits/Monat). `amm-higgsfield` wird als `tg-openart` umgeschrieben:
  Referenzdatei, kein eigenes Programm. `tools/bildgen/bg` wird nicht übernommen.
- **Korrekturen am Dossier:** OpenArt hat eine kostenlose Kostenschätzung (`openart model cost`) und kann Video (`openart generate video`, image2video).
- **Bausteine `tg-openart`:** Kosten `model cost` + Guthaben `account`; `--dry-run` vor jedem echten Lauf; Modelle nie aus dem Gedächtnis
  (`model list`, `model form <id> <mode>`); Referenzbild `--image`, einmal `upload add`, URL wiederverwenden; Bestand zuerst `creation list`;
  Ablage `-o <stück>/generiert/` + `lauf.json` (Job-ID, Prompt, Modell, Credits, Referenz); Video image2video; Agent-Flags `--json --compact --no-input --quiet`.
- **Verworfen:** Higgsfield (heute nicht genutzt, Installationsfehler unter Windows), beide Anbieter (doppelte Logik ohne heutigen Fall).
- **Offen P4:** Qualität von OpenArt-Video für den `video-cutter`. **Offen P7:** Skillname endgültig, Bau.

### C2 CLI statt MCP
- **Ergebnis:** Im Workspace nur die OpenArt-CLI. Markus schaltet den OpenArt-Connector für Claude Code selbst ab (evtl. nur im claude.ai-Chat behalten).
- **Begründung:** Der Connector lädt Werkzeugschemas in jede Session und liefert große JSON-Antworten. Die CLI hat keine Grundlast,
  kleine Ausgaben, Dateien direkt auf Platte. Everlast-treu.

### C3 Credits-Regel (Q9)
- **Ergebnis:** Grenze 400 Credits je Auftrag, alle Läufe zusammengezählt. Darunter ohne Rückfrage, darüber Bestätigung.
  Video immer mit Bestätigung. Vor jedem Lauf `openart model cost` und Restguthaben zeigen. Billig zuerst.
- **Begründung:** Everlasts 30 Higgsfield-Credits ≈ 1,20 $. OpenArt Plus ≈ 0,3 ct/Credit → 400 Credits ≈ gleicher Geldwert
  ≈ 7–10 Bilder (40–60 Cr) oder 1 Video (300–600 Cr). Planpreise aus Sekundärquellen, nicht offiziell geprüft.
- **Verworfen:** 30 Credits 1:1 (weniger als ein Bild).

### C4 Medienbibliothek TGMB (Q10)
- **Fakten:** „Tegards Medienbibliothek“ (TGMB): Vektordatenbank mit Stichwort-, semantischer und Ähnlichkeitssuche.
  Manuelle Auswahl, Download-Button, Zielordner frei wählbar, stabile Namen bzw. UUIDs, liefert auch Video. Kein MCP/API geplant.
- **Ergebnis:** Variante 1 ist Standard: Der Agent schreibt `medien.md` als Brief (je Bildstelle fertige semantische Suchtexte,
  1–2 Stichworte, optional „ähnlich wie“, genauer Zielpfad für den Download-Dialog). Markus lädt herunter. Der Agent sieht sich
  die Bilder an, ordnet zu, prüft Vollständigkeit, benennt auf SEO-Namen um, erzeugt Web-Fassung und Alt-Text, trägt `TGMB:<uuid>` ein.
  Variante 2 ist als Abkürzung erlaubt: Sammel-Download in einen Eingangsordner unter `inbox/`, der Agent sortiert durch Ansehen und fragt bei Unklarheit.
  Bestand zuerst, in dieser Reihenfolge: Workspace → TGMB → erst dann generieren.
- **Verworfen:** Bibliothek als MCP (Token-Grundlast). Aus dem abgesagten Asset-OS nur die Regeln (Identität ≠ Dateiname, Benennung
  klein mit Bindestrichen ohne Umlaute, Prompt bleibt beim Bild), keine Datenbank, kein Dashboard.

### C5 Ablageort: Medien beim Stück, Stück mit Medien als Ordner (bewusste Anpassung, Codex-Befund #8)
- **Ergebnis:** Kein Sammelordner `assets/<stück>/`. Nach Everlast (`grafik-designer-workflows.md`, „Ablage“) liegt jedes Bild neben
  seinem Stück, stückfreie Motive in `pipelines/assets/{bilder,videos}/<spalte>/<slug>/`.
  **Anpassung gegenüber Everlast:** Ein Stück mit Medien ist ein Ordner `pipelines/<kanal>/<spalte>/JJMMTT-<slug>/` mit der Stück-Datei
  (z. B. `artikel.md`), `medien.md`, `quelle/` (TGMB-Originale), `generiert/` (+ `lauf.json` je Lauf) und `web/` (Web-Fassungen).
  Herkunftskette in `medien.md`: `TGMB:<uuid>` bzw. `openart:<job-id> aus TGMB:<uuid1>, <uuid2>`.
- **Begründung:** Bei Everlast ist ein Blogartikel eine Einzeldatei `JJMMTT-<slug>.md`, weil die Astro-Website den Ordner direkt als
  Content-Collection liest (`pipelines/blog/README.md`, „Ein Ordner, zwei Leser“). Bei Tegards gibt es diesen zweiten Leser nicht (WordPress, Raw-HTML).
  Die Ordnerform ist bei Everlast schon Muster (Karussell mit `folien/`, `cover/`).
- **Verworfen:** Medien flach neben die Datei (unübersichtlich, kein Platz für `lauf.json` je Lauf, beim Spaltenwechsel wandern viele Einzeldateien).
- **Offen P9/P4:** Abgleich mit den Frontmatter-Verträgen je Pipeline-README und mit der Steuerstand-Karte (Kartenbild nur aus `web/`,
  Assets-Reiter „Bei ihrem Stück“ muss `quelle/` und `generiert/` richtig behandeln). **Offen P7:** Umsetzung, genauer Pfad von `inbox/`.

### C6 Formate und Web-Fassung (Q11)
- **Ergebnis:** TGMB-Downloads sind Originale in voller Größe. Der Agent erzeugt die Web-Fassung, das Original bleibt unverändert.
- **Offen P7:** Werkzeug für die Bild-Web-Fassung (inkl. IPTC-KI-Kennzeichnung generierter Bilder), `ffmpeg` für Video (fehlt unter Windows).

### C7 Medien in Git (Q12)
- **Ergebnis:** Keine Binärdateien in Git. In Git liegen `medien.md` und `lauf.json`, Bilder und Videos sind per `.gitignore` ausgenommen.
- **Begründung:** Alles ist wiederherstellbar: TGMB-Originale über die UUID, OpenArt-Ergebnisse über die Job-ID (`creation`), Web-Fassungen per Skript.
- **Verworfen:** LFS (Pflegeaufwand ohne heutigen Fall), nur Web-Fassungen in Git (doppelte Megabytes).
- **Offen P7:** `.gitignore`-Muster.

### C8 OpenArt-Fälle (an CLI 0.1.1 geprüft)
1. TGMB-Foto überarbeiten: `generate image "<Änderung>" --image quelle/<uuid>.jpg -o generiert/`. Ein Rückspielen in die TGMB ist kein Thema.
2. Neue Perspektive aus mehreren TGMB-Referenzen: `--image` mehrfach. Risiko Produktgeometrie → `referenz-diff` (C9).
3. Video aus Start- und Stop-Bild: Das Modell kann es (kling-3-omni `endFrame`), die CLI 0.1.1 nur das Startbild. Heute Start+Stop manuell
   in der OpenArt-Web-App, kein API-Aufruf an der CLI vorbei. **Offen P7:** Unterstützt eine neuere CLI `endFrame`?

### C9 Bildprüfung und Wahrheitsregeln (Q13)
- **Ergebnis:** Harte Regeln: (1) Kein generiertes Produktbild zeigt Maße oder Funktionen, die das Produkt nicht hat.
  (2) Kein Projektbeitrag ohne echtes Foto.
- **Prüfstelle (1):** Everlast-Rule `referenz-diff.md` (Produktgeometrie und Objektzahl gegen ein Vorbild, Slop-Gate vor einer Quote) mit
  TGMB-Referenzen als Vorbild, dazu die 6-Punkte-Bildrubrik des Jurors. **Neu (Codex-Befund #6):** Beide prüfen keine erfundenen Funktionen
  oder Maße. Die Bildrubrik bekommt deshalb eine Zeile „Das Bild zeigt nur Merkmale, die in den Produktdaten belegt sind“, und der Juror
  erhält die Produktdaten als Text. Unbelegbare Darstellungen bleiben bis zur Klärung offen. **Offen P3/P4:** welche Produktdatenquelle.
- **Prüfstelle (2) (Codex-Befund #7):** Der `content-marketer` weist vor dem Ergebnis-Checkpoint in `medien.md` mindestens ein echtes Foto nach
  (Herkunft `TGMB:<uuid>` oder eigenes Foto). Ohne Nachweis bleibt der Beitrag offen.
- **Begründung:** Kostet wenig, schützt vor dem teuersten Fehler, baut auf Everlast-Bestand auf.
- **Hinweis:** Everlast hat keine Medienbibliothek. `steuerstand/medien.ts` baut nur Vorschaubilder (`sips` + `ffmpeg`, Windows-Problem P7).
  Bildstil-Konstanz prüft Everlast per Kontaktbogen (`amm-bildstil`).

### C10 Datenfreigabe an externe Dienste (Codex-Befund #5)
- **Ergebnis:** Einmalige Freigabe. **Dürfen raus:** TGMB-Medien und Workspace-Texte (Entwürfe, Strategie, Planung) an OpenArt
  (`upload add`, `--image`) bzw. Codex (Juror). **Bleiben drin:** Zugangsdaten, `.env*`, Kunden- und Personendaten mit Klarnamen
  (Everlast-Rule `geheimnisse-und-daten.md`). **Rückfrage vorher:** jedes andere Material, z. B. fremde Fotos oder Kundenprojekte mit Personen.
- **Begründung:** Die Credits-Grenze (C3) regelt Kosten, nicht Datenabfluss. Ohne Abgrenzung würde ein Upload unter der Grenze ohne Rückfrage laufen.

---

## Querschnitt

### Q-1 Saubere Abspaltung von Everlast
- **Ergebnis:** `everlastpull` samt SessionStart-Hook wird nicht übernommen, nichts schreibt mehr von außen ins System.
  Everlast ist nur Ideenquelle. Neue Versionen lädt Markus manuell in einen eigenen Ordner neben `E:\Everlast Learning\marketing-workspace-0.5.0`,
  eine Session vergleicht und listet Neuerungen, Markus entscheidet Punkt für Punkt.
- **Begründung:** Bei einem umbenannten, portierten System würde `everlastpull` eine Flut von `*.everlast-neu` und doppelte Skills erzeugen.
- **Verworfen:** `everlastpull` behalten.

### Q-2 Namensregel
- **Ergebnis:** `amm-<name>` → `tg-<name>` (`amm-` = Kursname „Agentic Marketing Masterclass“). Fremd-Skills ohne `amm-` behalten ihren Namen.
  Keine Zuordnungstabelle, die Zuordnung folgt aus dem Namen.
- **Offen P7:** Querverweise in Agenten, Rules, Commands und Head in einem Durchgang umbenennen.

### Q-3 Neues Planungsthema P9
„Everlast-Inventur und Durchspielen“: alle Workflows, Pipelines (inkl. Spaltenlogik), Swipefile, Steuerstand, Skills, Rules, Commands und
Prozesse erfassen und durchspielen. Ergebnis: Inventarliste mit Status je Baustein (1:1 / anpassen / weglassen → SPAETER) und Durchspiel-Protokoll.
Hängt an P0, ist Voraussetzung für P7 und für das Planungsaudit (Codex-Befund #9), überschneidet sich mit P8. Rohlesen über Subagenten.
Eingetragen in `STAND.md`.

---

## Offene Punkte nach Thema

- **P3/P4:** Produktdatenquelle für die Produktwahrheits-Zeile der Bildrubrik (C9).
- **P4:** Content-Skills und `design-tokens.md` je Skill; Zuordnung Inhaltsrubrik ↔ Content-Fähigkeit (A1); Newsletter-Design;
  Qualität OpenArt-Video; Weg von `bundle.css` auf die Website (auch P3/P7); Kanalverträge für Stück-Ordner (C5, mit P9).
- **P6:** Globale CLAUDE.md-Regel zu three-brain; stehende Wahl vs. A3; `~/.codex/config.toml` auf `medium`; Bun in die Rechner-Übertragungsliste.
- **P7:** Bun-Test (A7); Bau-Rubrik-Datei; Juror-Effort je Rubrik und `--out`-Dateiname (A1/A3); Produktwahrheits-Zeile der Bildrubrik (C9); Generator-Änderung und `_blob`-Zuordnung (B1); ANLEITUNG-Zeile (B2); `tg-openart` bauen und benennen (C1);
  `inbox/`-Pfad (C5); Web-Fassungs-Werkzeug, IPTC, `ffmpeg` (C6); `.gitignore` (C7); CLI-`endFrame` (C8); Umbenennung `amm-`→`tg-` (Q-2).
- **P9:** neu, siehe Q-3; dazu: Challenge-Jury übernehmen ja/nein (A1), Stück-Ordner gegen Kanalverträge und Steuerstand-Karte (C5).
