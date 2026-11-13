# Dossier P1: Reviewer, Designsystem, Medien

Stand 13.11.2026 · Vorbereitung für das Grilling zu P1 · nur gelesen, nichts geändert (einzige Schreibung: diese Datei).
Quellen: `E:\Everlast Learning\marketing-workspace-0.5.0\` (kurz: Everlast), `E:\agentic-os\skills\three-brain\`,
`E:\agentic-os\routing\`, `C:\Users\marku\.claude\CLAUDE.md`, Codex-Plugin unter
`C:\Users\marku\.claude\plugins\cache\openai-codex\codex\1.0.6\`, `E:\TG Design\`, `E:\commerce-os\`,
`E:\offene_Konzepte\asset footage bibliothek\`, Web (URLs in Abschnitt A.3 und C.1).
Nicht gelesen: `~/.codex/config.toml`, Zugangsdaten, `.env*`.

---

## Teil A: Reviewer über Codex

### A.1 Everlast: der fremde Juror

**`tools/juror.ts`** (111 Zeilen, Bun):
- Ruft `codex exec -s read-only --ephemeral --skip-git-repo-check --color never -C <leerer Temp-Ordner> -o urteil.md [-m <modell>] [-i <bild>…] -` auf. Prompt kommt über stdin.
- Der leere Temp-Ordner als Arbeitsverzeichnis hält `AGENTS.md` und den Workspace aus dem Kontext des Jurors: Er sieht nur, was ihm übergeben wird ("kalter Read").
- Rubrik: bei Texten die sechs Fragen aus `.claude/agents/references/content-marketer-pruefung.md`, Abschnitt "Der Skeptiker-Pass" (Wettbewerber würde unterschreiben? Zahl mit Quelle? genau ein Insight? Format passt zur Awareness-Stufe? CTA weich? Earned Secret?). Bei Bildern eine eingebaute 6-Punkte-Bildrubrik (Absicht in 1 s, Hierarchie, Text fehlerfrei, Komposition, KI-Artefakte, Unterscheidbarkeit). Eigene Rubrik per `--rubrik <datei>`.
- Festes Ausgabeformat: je Rubrikzeile "hält / hält nicht" mit wörtlichem Zitat, dann `GESAMT: n von m` und `SCHWERSTE SCHWÄCHE`. Kein Lob, keine Umschrift.
- `bun tools/juror.ts check` prüft Installation und Login. Exit 3 = nicht verfügbar, dann prüft Sonnet 5 als Rückfall.
- Kein Effort-Flag: die Denkstufe kommt aus der Codex-Konfiguration.

**Einsatz** (`.claude/head-of-marketing.md`, Abschnitt 5 "Modell-Politik"): Zeile "Prüfer | GPT, sonst Sonnet 5 | medium | `tools/juror.ts`". Regel: "Der Prüfer ist nie das Modell des Erzeugers". Zusätzlich Zeile 54: Varianten-Läufe mit "Prüfer mit fester Rubrik vor der Wahl".
**`amm-challenge`** (`.claude/skills/amm-challenge/SKILL.md`, Schritt 8): drei Juroren auf verschiedenen Modellen, einer davon über `juror.ts`, Ergebnis `jury.md`. Läuft bei jedem neuen Creative (Rule `challenge-vor-handwerk`).

**Charakter:** Der Juror prüft **Inhalte** (Text, Bild) gegen eine Marketing-Rubrik. Er prüft keinen Code und keine Bauentscheidungen.

### A.2 Markus heute: three-brain plus Codex-Plugin

**Skill `three-brain`** (`E:\agentic-os\skills\three-brain\SKILL.md`, 454 Zeilen) plus `E:\agentic-os\routing\` (`rollen.yaml` 91 Z., `werkzeuge.yaml` 27 Z., zwei Schemas, `pruefe_routing.py`, Fixtures):
- No-Self-Review-Gesetz: jede Prüfung eigener Arbeit geht an Codex.
- Fehlerzähler (2 gleiche Fehler → Codex-Rescue), Risikopfade (`src/auth/**`, `**/migrations/**`, `**/Stripe*` …), Vollständigkeits-Verfahren, Konsens-Modus mit drei Modellen, Break-even-Lehre.
- Modellwahl-Gate R0': vor jedem CLI-Aufruf Optionen zeigen, Ledger-Zeilen, Auftragsdatei mit fünf Kopfzeilen (`vorlagen/extern-auftrag.md`).
- Umfangsblock im Review-Auftrag: Befunde klassifiziert als Fehler / Ergänzung / Begründung trägt nicht; Ergänzungen nach `SPAETER.md`.
- Ausführung über Companion: `codex-companion.mjs task --background --model <m> --effort <e> "$(cat <auftrag>)"`.
- **agy-Teil** (Gemini): Delegation mit `--dir`, Zustimmungs-Gate, Schreib-Grants in `~/.gemini/…`, Tiers, Medienanalyse. `rollen.yaml` besetzt `bulk-mechanisch` und `handwerkskritiker-design` mit agy. Laut Markus **nie im Skill genutzt**.

**Globale Regel** (`C:\Users\marku\.claude\CLAUDE.md`): Reviews macht Codex über three-brain. Stehende Wahl `--model gpt-6-astra --effort xhigh`, ohne Nachfrage. Rückfall in `~/.codex/config.toml`.

**Tatsächliche Nutzung** (Beleg `E:\TG Design\three-brain-out\log.md`, 13 Zeilen): drei Codex-Reviews am 08.11.2026 zum Designsystem (11, 14 und 18 Befunde, fast alle "Fehler"), Fix-Runden, ein Fehlaufruf (`task --help` wurde als Auftrag gesendet). Andere `three-brain-out`-Ledger fand ich unter `E:\*\` und `E:\*\*\` nicht. Genutzt wird also genau ein Pfad: **Codex-Review mit Umfangsblock und fester Befundliste.**

**Codex-Plugin** (`codex@openai-codex` 1.0.6, installiert 31.08.2026; `codex-cli 0.153.4` unter `%APPDATA%\npm\codex`):
- Befehle: `/codex:review` (native Review, braucht Git-Stand, kein Fokustext), `/codex:adversarial-review` (mit Fokustext), `/codex:rescue` (`--model`, `--effort` bis `xhigh`), `/codex:transfer`, `status/result/cancel`, `/codex:setup`.
- Skills `codex-cli-runtime`, `codex-result-handling`, `gpt-5-4-prompting`; Agent `codex-rescue`.
- Hooks (`hooks/hooks.json`): SessionStart/SessionEnd immer aktiv; **Stop-Hook `stop-review-gate-hook.mjs`** (Timeout 900 s). Das Gate ist je Workspace in der Plugin-State-Datei gespeichert, Standard `stopReviewGate: false`, umschaltbar mit `/codex:setup --enable-review-gate`.
- Der Gate-Prompt (`prompts/stop-review-gate.md`) prüft **nur Codeänderungen** des letzten Turns ("Only review it if Claude actually did code changes"). Bei Texten und Strategie-Dateien gibt er praktisch immer ALLOW.

### A.3 Stand der Technik 2026 (Web)

- OpenAI hat `codex-plugin-cc` Ende März 2026 veröffentlicht. Es bietet Review, Adversarial-Review, Rescue und das optionale Stop-Gate. Die README warnt, das Gate könne eine lange Claude/Codex-Schleife erzeugen und Limits schnell aufbrauchen. Ohne `--model`/`--effort` wählt Codex selbst, Vorgaben stehen in `~/.codex/config.toml`. https://cdn.jsdelivr.net/gh/openai/codex-plugin-cc@main/README.md · Berichte: https://the-decoder.com/openai-launches-a-codex-plugin-that-runs-inside-anthropics-claude-code/ , https://codex.danielvaughan.com/2026/03/31/codex-plugin-cc-cross-model-bridge/
- `codex exec`: Standard-Sandbox ist read-only. `-o/--output-last-message` schreibt nur die Schlussantwort, `--ephemeral` speichert keine Session, `codex exec -` liest den Prompt aus stdin. https://learn.chatgpt.com/docs/non-interactive-mode (Weiterleitung von developers.openai.com/codex/noninteractive)
- Einordnung: Das Gate gilt in Berichten als experimentell und riskant. Für gezielte Prüfungen ist `codex exec` read-only mit festem Prompt das schlichteste Muster. Genau das macht `juror.ts`.

### A.4 Vergleich

| Kriterium | Everlast `juror.ts` | three-brain (Companion) | Plugin-Befehle | Stop-Gate |
|---|---|---|---|---|
| Einfachheit | 1 Datei, 1 Aufruf | 454 Z. Skill + 6 Routing-Dateien + Ledger | Slash-Befehl | 1 Schalter |
| Prüfgegenstand | Text, Bild gegen Rubrik | Code, Konzept, Plan mit Umfangsblock | Git-Diff (Code) | nur Codeänderungen |
| Kalter Read | ja (leerer cwd) | nein (läuft im Repo) | nein | nein |
| Modell/Effort explizit | nur `-m`, Effort aus config | ja, Pflicht | optional | aus config |
| Windows | Bun fehlt hier (`which bun`: nicht gefunden); Pfad-Ersetzung mit `/` ist kosmetisch falsch; ob `Bun.spawnSync(["codex"])` den npm-Shim `codex.cmd` findet, ist **ungeprüft** | läuft (Beleg 08.11.) | läuft (Node) | läuft, aber Schleifen- und Kostenrisiko |
| Kosten | 1 Codex-Lauf je Prüfung (ChatGPT-Plan) | 1 Lauf je Review; xhigh ist langsam | wie links | potenziell jeder Turn |
| Was er fängt | Marketing-Schwächen: Floskel, fehlende Quelle, kein Insight, Bildfehler | Logik- und Konzeptfehler, ausgelassene Begründungen | Code-Bugs | Code-Bugs vor "fertig" |
| Pflege | Rubrik-Datei pflegen | Modelllisten, Datumsfelder `pruefen_bis`, Schemas, Gate-Regeln | Plugin-Updates | keine |

**Ehrliche Bewertung:**
- three-brain ist für Markus' reale Nutzung **überbaut**. Gebraucht wird ein einziger Pfad: Codex-Review mit Umfangsklassifikation. Fehlerzähler, Risikopfade (Code-Pfade, die es im Marketing-Workspace nicht gibt), Vollständigkeits-Verfahren, Konsens-Modus, Break-even-Lehre und der ganze agy-Teil decken keinen heutigen Fall ab.
- Das Modellwahl-Gate ist durch die stehende Wahl faktisch erledigt, kostet aber weiter Ledger-Zeilen und Pflege von `werkzeuge.yaml`.
- `juror.ts` kann wiederum keine Bau-Reviews: keine Umfangsklassifikation, kein Effort.
- Der stärkste Teil von three-brain ist der **Umfangsblock** (Fehler / Ergänzung / Begründung trägt nicht). Er passt direkt zur No-Overengineering-Regel.
- Das Stop-Gate passt nicht: Es prüft nur Code und riskiert Schleifen.

### A.5 Optionen

- **A-1: Everlast 1:1** (`juror.ts` für Inhalte, sonst nichts). + schlank, Everlast-treu. − Bau-Reviews des Workspace (Skills, Hooks) haben keinen Weg. − Bun muss unter Windows laufen.
- **A-2: three-brain weiterführen.** + bewährt, globale Regel bleibt gültig. − schwer, agy-Ballast, zweite Routing-Quelle neben dem Head-Abschnitt 5.
- **A-3: Ein Juror, zwei Rubriken (Empfehlung).** `juror.ts` übernehmen. Unter Windows lauffähig machen: Bun installieren oder als Node/Python portieren, Entscheidung in P7. Ergänzen um festes `-m gpt-6-astra -c model_reasoning_effort=xhigh` (stehende Wahl) und eine zweite Rubrik `bau-review.md` mit dem Umfangsblock aus three-brain. Inhalte prüft der kalte Read (Skeptiker- und Bildrubrik), Bauarbeit die Bau-Rubrik. Dazu das Codex-Plugin installiert lassen für `/codex:adversarial-review` an Code bei Bedarf; Stop-Gate aus.
- **A-4: Nur Codex-Plugin.** + gepflegt von OpenAI. − Review braucht Git-Diff und ist codezentriert. Rubrik und kalter Read fehlen.

### A.6 Empfehlung A

A-3: ein Prüfweg (`codex exec` read-only, leerer cwd, feste Rubrik, festes Ausgabeformat), zwei Rubrik-Dateien, Modell und Effort im Aufruf fest. three-brain wandert **nicht** in den Workspace. Der agy-Teil kommt auf `SPAETER.md`. Rückfall bleibt Sonnet nach Everlast-Regel, aber nur mit Hinweis "Juror nicht verfügbar". Folge: Die globale CLAUDE.md-Regel ("über den Skill `agentic-os:three-brain`") muss angepasst werden. Das gehört zu P6 (agentic-os-Zukunft).

---

## Teil B: Designsystem

### B.1 Fakten

**Tegards (Markus):**
- Live-Artefakt in claude.ai, laut `E:\TG Design\designsystem\ANLEITUNG.md` (23 Zeilen) Version 25, 52 Bausteine. Beschreibt seit der Bereinigung am 08.11. **nur Design**.
- Seitenaufbau, Texte, Sortiment und WordPress liegen in `E:\TG Design\ausgelagert\` (`inhaltliche-grundsaetze.md`, `seitenvorlagen.md`, `sortiment.md`, `wordpress.md`). Das ist Futter für den Content-Agenten bzw. P3/P4.
- Lokale Kopie `ds\project\` (826 KB): `README.md` (Visuelle Grundlagen, Ikonografie, Logo, Grenzen), `tokens.json`, `design-system.json`, `components\` (55 Einträge), `assets\` (Blog-Elemente, Icons, Kategorie-Icons, Logos, Produkt-Icons, Siegel), `fonts\`.
- Generator `tools\` (Python: `components_def.py`, `components_verdeca.py`, `build_components.py`, `scope.py`, `mktest.py`), Originale in `quellen\` (205 KB).
- **Heutige Sync-Praxis** (ANLEITUNG): manuell über das Artifact-Werkzeug. `publish` mit `root = E:\TG Design\designsystem\ds` und geänderten Dateien. Vorher `read` mit `path` auf die Live-Fassung, weil die Seite selbst speichert (`design-system.json`, generierter README-Teil, `tokens.css`, `api/`).
- `tokens.css` und `api/` fehlen lokal noch. Offen: "Seite einmal speichern".
- Zielplattform: WordPress/WooCommerce mit WoodMart + WPBakery. Komponenten sind HTML-Snippets in Wrapper `.tg-ds` mit `bundle.css`.
- "DesignSync": In Plugins, Skills und `E:\TG Design` fand ich keinen Eintrag dazu. Ob das eine Fähigkeit der Artefakt-Typen in claude.ai ist, habe ich **nicht geprüft**. Der belegte Weg ist Artifact `read`/`publish`.

**Everlast:**
- `strategie/brand-identity/brand-design/design-tokens.md` ist im Paket ein **Stub** (9 Zeilen, "Noch nicht ausgefüllt").
- `/prime-design` (`.claude/commands/prime-design.md`) liest alles unter `brand-design/`, die harten Regeln der Brand Voice und die kreative Leitidee.
- Leser: `ux-ui-designer` ("Jeder Farb-, Schrift- und Radiuswert kommt aus `design-tokens.md`"), `webdesigner`, `grafik-designer` (zusätzlich `bildsprache.md` und `brand-design/assets/`), `video-cutter`, `content-marketer` (Karussell-Layouts).
- `bildsprache.md` wird referenziert, liegt im Paket aber nicht.
- Skills `design-system` (generischer Token-/Slide-Werkzeugkasten mit Node/Python-Skripten) und `ui-styling` (shadcn/Tailwind). Für eine WPBakery-Seite mit eigenem `bundle.css` passt `ui-styling` kaum. `design-system` ist ein Werkzeug zum Erzeugen von Tokens, keine Markenwahrheit.

### B.2 Reicht nur Cloud?

Eher nein:
- Agenten müssten jede Komponente über das Artifact-Werkzeug laden. Ob Subagenten dieses Werkzeug haben, ist ungeprüft, `grep` geht nicht, und jeder Lauf hängt am Netz.
- Das Brennen von HTML für WordPress braucht die Snippets und Assets als Dateien.
- Cloud bleibt aber die **Wahrheit für Menschen** (Ansicht, Freigabe, Teilen).

### B.3 Optionen für den Ort

- **B-1: Ganzes Designsystem in den Workspace** (z. B. `strategie/brand-identity/brand-design/designsystem/`). + alles an einem Ort, Agenten greppen direkt. − 1 MB Snippets im Strategie-Ordner, `prime-design` würde alles laden (Kontextkosten). − Der Generator ist Bau-Werkzeug, kein Strategie-Inhalt.
- **B-2: Eigenes Design-Repo bleibt (`E:\TG Design\designsystem\`), im Workspace nur ein Destillat (Empfehlung).** `brand-design/design-tokens.md` (Farben, Schriften, Abstände, Radien aus `tokens.json`/README, ca. 60 Zeilen) plus `bildsprache.md` (Abschnitt Bildsprache, Ikonografie, Logo). Kopfzeilen: Artefakt-Link, Version, lokaler Pfad zu `components\<Name>\README.md`. `prime-design` lädt nur das Destillat. Der `webdesigner` liest einzelne Komponenten-READMEs gezielt aus dem lokalen Pfad. + Everlast-Struktur bleibt, kleiner Kontext. − Zwei Orte, das Destillat kann veralten.
- **B-3: Design-Repo als Unterordner `design/` des Workspace** (wie im commerce-os-Spec `design.system_pfad: design/`). + ein Repo, Generator lebt mit. − Der Workspace wird zum Bau-Repo für das Designsystem. Publish-Root ändert sich, ANLEITUNG muss umziehen.

**Sync (für B-2/B-3):** manuell, kein Sync-Werkzeug bauen. Regel: Nach jedem Publish einer neuen Version wird im selben Schritt das Destillat nachgezogen. Die Versionsnummer steht im Frontmatter des Destillats (`source: Artefakt v25`). Prüfen lässt sich das mit einem Blick: Version im Destillat = Version in der ANLEITUNG.

### B.4 Empfehlung B

B-2. Begründung: Everlast-Struktur bleibt unverändert, `prime-design` bleibt klein, und das funktionierende Publish-Verfahren in `E:\TG Design` wird nicht umgebaut. Leser: `webdesigner` und `ux-ui-designer` (Tokens + Komponenten-READMEs), `grafik-designer` und `video-cutter` (Tokens + Bildsprache + Assets/Logos). `ui-styling` (shadcn) nicht übernehmen oder nur behalten, wenn ein heutiger Fall es braucht. Die Inhalte aus `ausgelagert\` gehen in P3/P4, nicht in das Design.

---

## Teil C: Mediengenerierung und Medienbibliothek

### C.1 Fakten Everlast: Higgsfield

**Skill `amm-higgsfield`** (94 Zeilen + 4 Referenzen):
- Pflichtweg CLI `higgsfield`, keine MCP-Bild-Tools.
- Zyklus: `account status`, dann `generate list` ("Bestand zuerst"), dann `model list`/`model get`, dann `generate cost`, dann `generate create --wait --json`, dann Download per `curl`.
- Edit statt Neuwurf (Inpaint, Outpaint, Upscale). Hausmodell `seedream_v4_5`, kein Seed, Konsistenz über Referenzbilder. Kein `auth token` (druckt das Token).

**Weitere Bausteine:**
- Rule `credits`: kein Lauf über 30 Credits ohne Bestätigung, Läufe eines Auftrags zählen zusammen, Kosten vor jedem Lauf zeigen, billig zuerst.
- `tools/bildgen/bg` (Python): zwei Anbieter (Higgsfield-CLI, Gemini mit eigenem Schlüssel), Bremse bei 30 Bildern, Ablage `daten/creatives/JJMMTT-<zweck>/` mit `lauf.json` (Modell, Prompt, Referenzen, Kosten). Die Anmeldung hält laut README 24 h.
- Agenten: `grafik-designer` (Sonnet 5, lädt `amm-higgsfield` vor, liest Bildsprache und Tokens) und `video-cutter` (Clips aus Higgsfield, Schnitt mit `ffmpeg`, optionale HyperFrames-Skills).

**Windows-Probleme:**
1. `higgsfield` ist auf diesem Rechner **nicht installiert** (`which higgsfield`: nicht gefunden).
2. Offizielle Installation per `npm install -g @higgsfield/cli`. Offenes Issue #5 (seit 06.05.2026): Die Installation scheitert, wenn Git für Windows installiert ist, weil das falsche `tar` greift. Markus hat Git Bash. Umgehung laut Issue: Windows-`tar.exe`. https://github.com/higgsfield-ai/cli/issues/5 · https://github.com/higgsfield-ai/cli
3. `bg` erzeugt PNG über `sips`, das es nur auf macOS gibt. Unter Windows entsteht nur WebP, und Gate und Wahrnehmungshash lesen ausschließlich PNG.
4. `video-cutter-werkzeuge.md` nennt `/opt/homebrew/bin/higgsfield`. `ffmpeg` ist hier nicht im PATH.
5. Credentials liegen unter `~/.config/higgsfield/credentials.json`. Unter Windows ist der Pfad ungeprüft.
6. Bun-Werkzeuge (`juror.ts`, `varianten.ts`): Bun fehlt.

### C.2 Fakten Markus: OpenArt

- **OpenArt-CLI ist installiert**: `C:\Users\marku\AppData\Local\Programs\openart\bin\openart.exe` (im PATH, Go-Binary vom 31.08.).
  - Befehle: `account` (Plan, Credits), `creation` (frühere Generierungen = Bestand), `generate`, `model`, `project`, `upload` (Referenzmedien), `workspace`.
  - Flags: `--json`, `--compact` ("token-minimal for agents"), `--dry-run`. Login per OAuth oder `OPENART_TOKEN`.
  - Ein eigener Kostenbefehl wie `generate cost` steht **nicht** in der Hilfe. Ob `model`/`--dry-run` Credits nennen, ist ungeprüft.
- Zusätzlich der claude.ai-Connector "OpenArt" (Eintrag in `~/.claude.json`).
- `E:\agentic-os\routing\werkzeuge.yaml`: Higgsfield "Bild- und Bewegtbild-Veredelung", OpenArt "Bildgenerierung mit Referenz", beide mit Abo.
- `E:\commerce-os\docs\specs\commerce-os-design.md` (Z. 244–305):
  - Rohdateien beider Werkzeuge liegen in `quellen\…\generiert\` mit `prompt.md`, in Git nur die Web-Kopie per LFS.
  - IPTC-KI-Kennzeichnung.
  - Faktenklasse 1: kein generiertes Produktbild zeigt Maße oder Funktionen, die das Produkt nicht hat.
  - Ein Projektbeitrag ohne echtes Foto wird nicht publiziert.

### C.3 OpenArt neben Higgsfield, ohne doppelte Logik

- **O-1: Nur Higgsfield, OpenArt auf `SPAETER.md`.** + Everlast 1:1, eine Logik. − Higgsfield läuft unter Windows noch nicht (Installation, PNG), OpenArt schon. Markus zahlt beide Abos.
- **O-2: Gemeinsamer Zyklus, Anbieter als Referenzdatei (Empfehlung, falls beide genutzt werden).**
  - Der Zyklus (Bestand, Kosten/Freigabe, Erzeugen, Ablage mit `lauf.json`) und die Rule `credits` gelten anbieterneutral.
  - Je Anbieter eine Referenzdatei mit Befehlen, Modellen und Fallen: `amm-higgsfield/references/…` bzw. eine neue `references/openart.md`.
  - `bg` hat bereits zwei Anbieter. Gemini wird durch OpenArt ersetzt, die PNG-Wandlung unter Windows z. B. mit Pillow (P7).
  - Wann welcher Anbieter: eine Zeile in der Rolle des `grafik-designer`, entschieden im Grilling.
- **O-3: OpenArt nur interaktiv über den MCP-Connector in claude.ai.** + null Bau. − Agenten im Workspace sehen keinen Bestand, keine Ablage und keine Kostenbremse. Das widerspricht Everlasts "CLI statt MCP".

### C.4 Medienbibliothek

**Ausgangslage:**
- Die Bibliothek ist fertig, hat aber keine MCP- und keine API-Anbindung. Suche und Download macht Markus manuell in einen Zielordner.
- Das alte Asset-OS (`Asset-Bibliothek_Konzept_und_Bauauftrag.md`, 816 Zeilen) ist abgesagt. Wiederverwendbar daraus sind nur Regeln:
  - Identität ≠ Dateiname.
  - Benennung in Kleinbuchstaben mit Bindestrichen, ohne Umlaute, keine `final_neu_final2`.
  - Prompt bleibt beim generierten Bild.
  - "Bestand zuerst".
  - Wiederverwendungsarten: direkt verwendbar / anpassbare Vorlage / Stilreferenz.
  - Exporte je Projekt getrennt.
  - Nicht übernehmen: Katalog-Datenbank, Dashboard, Embeddings, OneDrive-Beobachtung, Asset-API.
- Commerce-os-Vorlage `E:\commerce-os\templates\medien.md`: je Content-Stück eine `medien.md` neben `entwurf.md`. Eine Zeile je `[BILD: … | ALT: …]`-Anker mit Spalten Datei (SEO-Name), Herkunft (foto/bearbeitet/generiert), Quelle, Werkzeug/Modell, Prompt-Datei, Alt-Text, KI-Kennzeichnung.

**Drei schlanke Abläufe:**

- **M-1: Medien-Brief → Markus lädt → Agent verdrahtet.**
  1. Agent schreibt `medien.md` mit zusätzlicher Spalte "Suchbegriffe / Motiv" je Anker.
  2. Markus sucht in der Bibliothek und lädt in `<workspace>/assets/<stück>/`.
  3. Agent prüft, ob jede Zeile eine Datei hat, benennt auf den SEO-Namen um und setzt die Pfade.

  \+ minimal, nutzt die bewährte Vorlage. − Markus muss je Stück suchen. Umbenennen verliert den Bezug zur Bibliothek, außer die Spalte "Quelle" trägt den Bibliotheksnamen oder die Bibliotheks-ID.
- **M-2: Ein Eingangsordner.**
  1. Markus lädt alles Gefundene in `assets/eingang/` (ein fester Zielordner, im Browser als Download-Ziel einstellbar).
  2. Agent sortiert per Brief-Abgleich in `assets/<stück>/`, benennt um und füllt `medien.md`.

  \+ Markus muss nur einen Ordner kennen. − Bei mehreren Stücken gleichzeitig ist die Zuordnung unsicher, deshalb Rückfrage bei unklaren Dateien.
- **M-3: Workspace-Bestand zuerst** (Ergänzung zu M-1 oder M-2). Vor jedem Brief und vor jeder Generierung sucht der Agent in `assets/**` und in allen `medien.md` (grep über Motiv und Alt-Text). Erst bei Lücken schreibt er einen Brief oder schlägt eine Generierung vor.

  \+ verhindert Doppel-Downloads und Neuwürfe, analog zu Higgsfield. − wirkt erst, wenn sich Bestand ansammelt.

**Empfehlung C:** M-1 + M-3. Generierte Bilder landen im selben `assets/<stück>/`, ihre `lauf.json` und ihren Prompt verweist `medien.md`. Offen für P7: Binärdateien in Git (LFS wie commerce-os) oder außerhalb von Git.

---

## Fragen für das Grilling

1. Reviewer: Einverstanden mit **einem** Prüfweg (`codex exec` read-only, kalter Read) mit zwei Rubriken (Inhalt, Bau), statt three-brain im Workspace?
2. Soll der Umfangsblock (Fehler / Ergänzung / Begründung trägt nicht) Pflicht für jede Bau-Prüfung im neuen Workspace sein?
3. Bleibt die stehende Wahl `gpt-6-astra, xhigh` auch für den Inhalts-Juror? Everlast fährt den Prüfer auf `medium`, und xhigh ist bei vielen Text-Prüfungen langsam.
4. Rückfall, wenn Codex nicht verfügbar ist: Sonnet prüfen lassen (Everlast) oder Prüfung als offen markieren (deine Regel "kein Selbst-Review")?
5. Darf three-brain als Skill für die anderen Projekte weiterleben, bis P6 entscheidet, oder ziehen wir die globale CLAUDE.md-Regel gleich mit um?
6. agy/Antigravity: komplett auf `SPAETER.md` (inkl. `handwerkskritiker-design` in `rollen.yaml`)? Oder gibt es einen heutigen Fall, z. B. Videoanalyse?
7. Codex-Plugin: installiert lassen für gelegentliche Code-Reviews, Stop-Gate dauerhaft aus?
8. Bun unter Windows installieren (Everlast-Werkzeuge 1:1) oder `juror.ts` und `varianten.ts` nach Node/Python portieren? (Querbezug P7)
9. Designsystem: Bleibt `E:\TG Design\designsystem\` der Bau- und Publish-Ort, und der Workspace bekommt nur das Destillat (B-2)? Oder soll alles in den Workspace (B-1/B-3)?
10. Wer zieht das Destillat nach einem Publish nach: du per Auftrag oder fest als letzter Schritt im Publish-Ablauf der ANLEITUNG?
11. Meinst du mit "DesignSync" eine konkrete Funktion in claude.ai, die ich prüfen soll, oder den heutigen Artifact-read/publish-Weg?
12. Braucht der Workspace `ui-styling` (shadcn/Tailwind) überhaupt, wenn die Zielplattform WPBakery mit `bundle.css` ist?
13. Wofür nutzt du heute Higgsfield und wofür OpenArt? Gibt es eine klare Aufteilung (z. B. Produktbild mit Referenz → OpenArt, Video/Veredelung → Higgsfield)?
14. Soll Higgsfield unter Windows jetzt installiert werden (npm-Bug mit Git-`tar` umgehen), oder startet der Workspace nur mit OpenArt?
15. Gilt die Credits-Grenze von 30 je Auftrag auch für dich, und für beide Anbieter gemeinsam?
16. Medienbibliothek: Wie heißt sie, und wie suchst du darin (Stichwort, Ordner, visuell)?
17. Wohin lädst du heute herunter (Standard-Downloads, fester Ordner)? Darf der Zielordner `<workspace>/assets/eingang/` bzw. `assets/<stück>/` sein?
18. Welche Formate kommen aus der Bibliothek (JPG, PNG, WebP, Video, SVG), und wer erzeugt die Web-Fassung (Größe, WebP, IPTC-KI-Kennzeichnung)?
19. Bleibt die Bibliotheks-ID oder der Originalname in `medien.md` stehen (Spalte "Quelle"), damit ein Bild später wiederauffindbar ist?
20. Bilder in Git: LFS wie in commerce-os, nur Web-Kopien, oder Medien ganz außerhalb des Repos?
21. Gilt die commerce-os-Regel "kein Projektbeitrag ohne echtes Foto" und "kein generiertes Produktbild mit erfundenen Merkmalen" auch im neuen Workspace?
