# Dossier P6: agentic-os-Zukunft und Übertragung der Claude-Installation

Stand: 13.11.2026 · Grundlage für das Grilling zu P6 · nur gelesen, nichts geändert
Frage: Was bleibt von agentic-os, wenn commerce-os und werkzeuge in den Workspace ziehen? Und wie kommt
Markus' allgemeines Claude-Verhalten (nicht Marketing) auf einen anderen Rechner?

---

## 1. Fakten (mit Pfaden)

### 1.1 agentic-os heute (`E:\agentic-os`)

- Git: aktueller Branch `skill-format`, `main` = `origin/main` = `0601b25` (per `git ls-remote` geprüft).
  Tags bis `v0.4.0`. Kein `AGENTS.md` im Repo (nur `skills/grilling/agents/openai.yaml`).
- Selbstverständnis (`README.md`, `CLAUDE.md`): „Kern der OS-Familie“. Sortenregel Kern/Fach-OS/Instanz,
  Commit-Wächter, Geräte-Setup, Familienkatalog `os-katalog`. Spec `docs/specs/agentic-os-design.md`:
  994 Zeilen, 179 KB.
- Plugin `agentic-os` 0.4.0 (`.claude-plugin/plugin.json`): Skills `three-brain` (25 KB), `umfang` (14 KB),
  `grilling` (2 KB), `skill-anleitung` (11 KB) plus SessionStart-Hook `hooks/hooks.json` →
  `skills/skill-anleitung/hooks/neue-skills.ps1` (meldet neu installierte Skills).
- Marketplace `os-katalog` (`.claude-plugin/marketplace.json`): `agentic-os`, `werkzeuge` (`./plugins/werkzeuge`),
  `commerce-os` (GitHub-Tag `v0.7.0`).
- Kopplung der Skills an das Repo: `three-brain` liest `${CLAUDE_PLUGIN_ROOT}/routing/rollen.yaml`,
  `routing/werkzeuge.yaml` und `vorlagen/extern-auftrag.md`; `umfang` nennt als Fundament-Pfade
  `konventionen/**`, `routing/**`, `hooks/**`, `tools/validate_kern*` usw. und erwähnt commerce-os.
- Umfang der Familien-Mechanik: `geraete/setup.ps1` 792 Zeilen, `geraete/inventar.py` 613 Zeilen,
  `geraete/tests/setup.Tests.ps1` 38 KB; `hooks/resolver.py` 785 Zeilen plus 40 KB Tests;
  `tools/validate_kern.py`, `tools/build_tutorial.py` (76 KB) plus Tests; `docs/tutorial/` mit drei
  Altfassungen à 1,3 MB.
- `wiki/` ist das Werkzeugpaket fürs Firmengedächtnis (Extrakt, Prüfseite, Paket, Wiki-Wächter,
  `installieren.py`), liegt also fachlich falsch im Kern.
- `SPAETER.md`: 24 Zeilen, fast alle Wiki-Werkzeuge (Extrakt, Prüfseite, Wächter), zwei Kern-Zeilen.

### 1.2 Commit d619148 und Branch skill-format

- **d619148** („umfang: Ablauf-Wahl in Abschnitt 4“) ist **gepusht**: Er liegt auf `origin/main`
  (`git branch -a --contains d619148` zeigt `remotes/origin/main`; `ls-remote` meldet `0601b25` als HEAD).
  Die Annahme „ungepusht“ stimmt nicht.
- Er ist aber **nicht installiert**: `installed_plugins.json` führt `agentic-os@os-katalog` 0.4.0 mit
  `gitCommitSha` `ebc2bd4` (vor d619148). Die Plugin-Kopie
  `~/.claude/plugins/cache/os-katalog/agentic-os/0.4.0/skills/umfang/SKILL.md` enthält die Ablauf-Wahl
  nicht, die Repo-Fassung schon. Ursache: `version` blieb 0.4.0. Laut Doku bekommen Nutzer neue Commits
  nur, wenn sich `version` ändert; neue Commits ohne Versionssprung kommen nicht an [Q3].
- Dieselbe Regel steht schon in `~/.claude/CLAUDE.md` (Abschnitt „Bau-Aufgaben“). Im Alltag wirkt sie also
  bereits, nur über die globale Datei, nicht über den Skill.
- **Branch `skill-format`**: zwei lokale, **ungepushte** Commits `96aec14`, `ecb9e65`
  (`konventionen/skill-format.md`, 13 KB; Plan `docs/plans/2026-11-13-skill-format.md` plus Entwurf).
  Der Plan will acht Skills umbauen (vier aus agentic-os, vier aus werkzeuge), ein Prüfskript
  `tools/skill_format.py` bauen und Codex-Reviews fahren. Vorlage war der Skill `amm-hausformat`.
  Laut `STAND.md` pausiert bis P6.

### 1.3 Markus' Claude-Setup auf Nutzerebene

| Ort | Inhalt | versioniert? |
|---|---|---|
| `~/.claude/CLAUDE.md` (2,8 KB) | Canary-Präfix, Security-Check-Satz, Tabu-Zonen, Reviews über `agentic-os:three-brain`, Modellwahl-Gate mit stehender Codex-Wahl, Bau-Aufgaben (Ablauf-Frage, `agentic-os:umfang`) | nein |
| `~/.claude/settings.json` | Schlüssel: `permissions` (3 allow, `defaultMode` auto, `additionalDirectories`), `model` (sonnet), `effortLevel` (high), `statusLine`, `enabledPlugins` (8), `extraKnownMarketplaces` (4), `pluginConfigs` (antigravity), `autoUpdatesChannel`, `theme`; **keine** `hooks` | nein |
| `~/.claude/statusline.py` (3,9 KB) | Kontext, Cache, Limits, Kosten, Branch, Modell | nein |
| `~/.claude/output-styles/Short and Simple.md` | eigener Ausgabestil | nein |
| `~/.claude/skills/` | nur `synced/` (vom claude.ai-Konto synchronisierte Anthropic-Skills), keine eigenen | – |
| `~/.claude/agents`, `commands`, `hooks`, `rules` | nicht vorhanden | – |
| `~/.claude/skill-anleitung/` | leerer Ordner | – |
| `~/.codex/config.toml` | `model = "gpt-6-astra"`, `model_reasoning_effort = "medium"` | nein |

Installierte Plugins (`~/.claude/plugins/installed_plugins.json`, alle user-Scope): superpowers 7.0.2,
codex 1.0.6, antigravity 0.25.2, claude-security 0.12.0, frontend-design 1.1.1 (offizielle bzw.
Fremd-Marketplaces); agentic-os 0.4.0 und werkzeuge 0.4.0 (`os-katalog` = GitHub `TEGARDS/agentic-os`);
commerce-os 0.7.0 (`commerce-os-local` = GitHub `TEGARDS/commerce-os`) zusätzlich zweimal im
Projekt-Scope für `E:\tegards\marketing` und `E:\Tegards\marketing` (nur Groß-/Kleinschreibung verschieden).

Doppelt oder auseinandergelaufen:
1. Review-/Modellwahl-Regel steht fünfmal: `~/.claude/CLAUDE.md`, `E:\agentic-os\CLAUDE.md`,
   `skills/three-brain/SKILL.md`, `routing/rollen.yaml` (R0, R1), `protokoll/session-protokoll.md`.
2. Ablauf-Wahl: in `~/.claude/CLAUDE.md` und in `umfang` (Repo), nicht in der installierten Fassung.
3. Codex-Denkstufe: `CLAUDE.md` sagt „`~/.codex/config.toml` trägt dieselbe Wahl als Rückfall“ (xhigh),
   die Datei hat `medium`.
4. Claude-Modell: `settings.json` sonnet/high, `routing/rollen.yaml` Orchestrator opus-5-5/medium.
5. commerce-os ist in zwei Marketplaces gelistet (`os-katalog` und `commerce-os-local`);
   `geraete/soll-inventar.yaml` erwartet `commerce-os-local` als Verzeichnis `E:\commerce-os`, registriert
   ist GitHub.
6. Globale `CLAUDE.md` verweist auf `E:\agentic-os\routing\werkzeuge.yaml` (harte Repo-Kopplung).
7. Das Wichtigste für einen neuen Rechner (CLAUDE.md, statusline, Ausgabestil, settings) ist **nirgends
   versioniert**; versioniert ist dagegen die schwere Familien-Mechanik.

### 1.4 Wie Everlast global und Workspace trennt

- Alles liegt im Repo: `AGENTS.md` (Hauptregeln; `CLAUDE.md` verweist nur darauf), `.claude/rules/`
  (eine Datei je Regel), `.claude/skills/`, `.claude/agents/`, `.claude/commands/`, `.claude/references/`,
  `.claude/settings.json` mit fünf SessionStart-Hooks (u. a. `cat .claude/head-of-marketing.md` nur in die
  Hauptsession, Update-Prüfung).
- Updates: Skill `/everlastpull` (`.claude/skills/everlastpull/scripts/everlastpull.mjs`, mit persönlichem
  Update-Schlüssel); selbst geänderte Skills bekommen die neue Fassung als Kopie daneben (`START-HIER.md`).
- `~/.claude` wird nicht angefasst, aber mitgedacht: `amm-konflikt-scan` scannt globale CLAUDE.md, Rules,
  Skills, Agents auf Konflikte. `references/vorrang.md`: Projekt vor global; ein globales Gate darf der
  Workspace nur schärfen, nie lockern; **bei gleichem Skill-Namen gewinnt die globale Fassung**.
- Everlast ist für macOS gebaut, Windows „nur über WSL“ (`START-HIER.md`). Der Umbau will Windows nativ.

### 1.5 Was die Claude-Code-Doku 2026 dazu sagt

- Scopes: User `~/.claude/settings.json`, Projekt `.claude/settings.json`, lokal `.claude/settings.local.json`,
  Managed (Organisation per MDM/Server/Datei). Vorrang: Managed > Kommandozeile > lokal > Projekt > User;
  Listen wie `permissions.allow` werden zusammengeführt [Q1].
- `CLAUDE_CONFIG_DIR` verlegt das ganze `~/.claude` samt Verlauf und Plugins [Q1] (zu grob für Markus).
- Plugins können Skills, Agents, Hooks, MCP, LSP, Ausgabestile, Themes, Monitore, `bin/` liefern, aber
  **keine CLAUDE.md**: „Claude Code doesn't load a CLAUDE.md at the plugin root“ [Q4]. Statusline und
  User-Settings liefert ein Plugin ebenfalls nicht.
- Marketplace-Updates: Auto-Update für Fremd-Marketplaces ist standardmäßig aus; Update nur bei geänderter
  `version`, oder `version` weglassen, dann folgen Nutzer den Commits [Q3].
- Ein Projekt kann Marketplace und Plugins über `extraKnownMarketplaces`/`enabledPlugins` in der
  committeten `.claude/settings.json` vorgeben; wirkt erst nach Ordner-Vertrauen [Q1][Q3].
- `~/.claude/CLAUDE.md` darf andere Dateien per `@pfad` importieren (auch absolute Pfade, bis vier Ebenen);
  Imports aus User-Dateien laden ohne Rückfrage. `~/.claude/rules/` gilt für alle Projekte auf dem Rechner [Q5].
- Managed Settings sind für Organisationen (Admin, MDM, Konsole) gedacht [Q1]; für einen Einzelnutzer
  mit zwei Rechnern ist das kein passender Weg.

---

## 2. Klassifizierung

(a) allgemeine Arbeitsregel für jede Claude-Arbeit · (b) Marketing/Wiki → Workspace ·
(c) nur wegen der Mehr-Repo-Familie nötig → nach dem Umbau überflüssig

| Teil | Klasse | Begründung / was davon bleibt |
|---|---|---|
| `CLAUDE.md` (Arbeit am Kern) | c | Regeln für den Kern selbst; Commit-Sprache/Trailer sind schon global geregelt |
| `README.md`, `docs/specs/agentic-os-design.md` | c | beschreiben die Familie; Archiv |
| `skills/umfang` | **a** | Kern der Anti-Overengineering-Bremse; Fundament-Pfadliste und commerce-os-Bezug kürzen |
| `skills/three-brain` | **a** | Codex-Review und Modellwahl-Gate; heute 25 KB und an `routing/`, `vorlagen/`, Ledger gekoppelt; braucht eine schlanke Fassung |
| `skills/grilling` | **a** | klein, allgemein |
| `skills/skill-anleitung` + Hook `neue-skills.ps1` | a (optional) | allgemein, aber Komfort; Nutzung klären (Frage 9) |
| `routing/rollen.yaml`, `werkzeuge.yaml` (Inhalt) | a (Kern) | nur „Reviewer = Codex, Modell, Stufe“ ist allgemein; passt in wenige Zeilen |
| `routing/` Schemas, Fixtures, `pruefe_routing.py`, `README.md` | c | Prüfapparat für Datumsfelder und Rangfolgen |
| `routing/werkzeuge.yaml` → Higgsfield, OpenArt | b | Medienwerkzeuge des Marketings (P1) |
| `protokoll/session-protokoll.md` | a (Kern) / c | Wechsel-Signale und Ledger-Zeile sind allgemein; Phasen und Orte sind Familie |
| `protokoll/git-strategie.md`, `headless.md` | a (klein) | Trunk + Tags, Headless-Regeln; auf je einen Absatz kürzbar |
| `vorlagen/extern-auftrag.md` | a | von three-brain gebraucht |
| `vorlagen/startpunkt`, `startprompt`, `uebergabeblock`, `abschluss-checkliste` | c (teils a) | der Umbau nutzt schon die kürzere Handoff-Vorlage in `STAND.md`; Everlast hat `entscheidungen.md`/`arbeitslog.md` |
| `hooks/` (Commit-Wächter `pre-commit`, `resolver.py`, Abnahmematrix) | c | löst `os-bindung.json` je Repo auf; im Ein-Workspace-Modell ohne Gegenstück |
| `.githooks/`, `tools/validate_kern*`, `kern_umgebung.py`, `cache_groesse.py`, `pyproject.toml`, `uv.lock` | c | Kern-Wächter für den Kern selbst |
| `tools/build_tutorial.py`, `docs/tutorial/` | c | Familien-Release-Tutorial |
| `geraete/` (setup.ps1, inventar.py, soll-inventar, Tests) | c | Idee „Rechner übertragen“ ist a, diese Umsetzung ist Familien-Bootstrap (Repos, Instanz-Bindung) |
| `konventionen/os-plugin.md`, `os*.schema.json`, `host-adapter.md`, `glossar.md`, `zustand-als-datei.md` | c | Fach-OS-Konvention |
| `konventionen/skill-format.md` (Branch) | offen (a oder b) | Hausformat für Skills; gehört dorthin, wo künftig Skills gebaut werden |
| `wiki/` (Werkzeugpaket) | b | Firmengedächtnis → Workspace (P2) |
| `plugins/werkzeuge` | b (entschieden) | Hinweis: `video-wissen` ist inhaltlich allgemein |
| `.claude-plugin/plugin.json`, `marketplace.json` | c in heutiger Form | bei Option A auf ein Plugin ohne commerce-os/werkzeuge schrumpfen |
| `SPAETER.md` | b / c | Wiki-Zeilen → Workspace; Kern-Zeilen entfallen |
| `docs/berichte`, `docs/migration`, `docs/quellen`, `docs/CHANGELOG.md` | c | Archiv |
| `~/.claude/CLAUDE.md` | **a** | bleibt global; Kopplungen an `agentic-os:`-Namen und `E:\agentic-os\routing\…` lösen |
| `~/.claude/statusline.py`, `output-styles/`, `settings.json` | **a** | gehören zum Rechner, nicht zu einem Repo |

Ergebnis in einem Satz: Von agentic-os sind rund vier Dateien Kern (umfang, three-brain schlank, grilling,
extern-auftrag) plus ein paar Zeilen Routing; der große Rest ist Familien-Mechanik (c) oder Wiki (b).

---

## 3. Optionen zur Übertragung auf einen anderen Rechner

Zu übertragen ist in jedem Fall: globale CLAUDE.md, 3 bis 4 Skills, statusline.py, Ausgabestil,
settings.json (ohne Geheimnisse), Codex-Modellzeile. Fremd-Plugins (superpowers, codex, antigravity …)
kommen über `enabledPlugins` + Marketplaces wieder; ob ein frischer Rechner sie aus der User-Settings
allein nachinstalliert, ist **nicht geprüft** (einmal testen, sonst eine Zeile je Plugin im Skript).

### A: kleines agentic-os-Plugin über den bestehenden Marketplace `TEGARDS/agentic-os`

- Pro: läuft heute schon; Skills haben Namensraum (`agentic-os:umfang`), keine Kollision mit Workspace-Skills;
  Update per `/plugin marketplace update`; Plugin-Hook ist möglich.
- Contra: trägt **keine** CLAUDE.md, statusline, settings [Q4], A allein löst die Übertragung also nicht,
  es braucht zusätzlich B oder D. Versionsdisziplin nötig (d619148 zeigt das Problem schon jetzt), oder
  `version` weglassen. Repo muss erst ausgemistet werden (Spec, Wächter, Tutorial), sonst bleibt der
  Pflegeballast. Zwei Mechanismen statt einem.
- Aufwand: mittel (Repo entkernen, Marketplace auf ein Plugin reduzieren, three-brain kürzen).
  Pflege: Version heben je Änderung.

### B: Dotfiles-Repo für `~/.claude` plus kleines Installationsskript

- Inhalt: `CLAUDE.md`, `settings.json` (Vorlage), `statusline.py`, `output-styles/`, `skills/umfang`,
  `skills/three-brain`, `skills/grilling`, `codex-modell.txt` o. ä.; `installieren.ps1` kopiert nach `~/.claude`.
- Pro: ein Ort für alles, was wirklich wandern muss; deckt CLAUDE.md und statusline ab; Windows-nativ
  ohne Symlinks (Kopieren genügt); Backup als Nebeneffekt. Alternativ statt Kopie eine Import-Zeile
  `@E:/claude-setup/CLAUDE.md` in `~/.claude/CLAUDE.md`, dann reicht `git pull` [Q5].
- Contra: Skills verlieren den Präfix `agentic-os:`; alle Verweise (globale CLAUDE.md, umfang, three-brain,
  Workspace-Regeln) einmal umbenennen. Globale Skills schlagen gleichnamige Workspace-Skills (Everlast
  `vorrang.md`), also eindeutige Namen wählen. Kopie heißt: nach Änderungen Skript erneut laufen lassen.
- Aufwand: klein (ein Repo, ein Skript mit etwa 30 Zeilen). Pflege: Änderungen im Repo statt in `~/.claude`.
- Variante B': dafür das bestehende Repo `agentic-os` nehmen und auf genau diesen Inhalt schrumpfen
  (Historie und GitHub-Remote bleiben, Name passt dann nicht mehr ganz).

### C: Allgemeine Regeln in jedes Workspace-Repo (Everlast-Stil)

- Pro: ein geklontes Repo ist sofort komplett; passt zum Everlast-Muster; Regeln nah an der Arbeit.
- Contra: Markus arbeitet nicht nur im Marketing-Workspace (`E:\agentic-os`, `TG Design`, `tegards`,
  `E:\codex-setup` …); jede Regel stünde n-mal und läuft auseinander (das Problem von 1.3 Nr. 1 wieder).
  statusline, Ausgabestil, Modell und Plugins sind ohnehin Rechner-Sache. Ein `everlastpull`-artiges
  Update kann eigene Regeldateien berühren.
- Aufwand: klein für das erste Repo, wächst mit jedem weiteren. Pflege: hoch.
- Sinnvoll nur für das, was ohnehin marketing-spezifisch ist (b) und schon entschieden ist.

### D: Manuell kopieren

- Pro: null Bau; bei einem zweiten Rechner, der selten aufgesetzt wird, völlig ausreichend.
- Contra: keine Versionierung, kein Backup (heute ist genau das der Zustand), Abweichungen merkt keiner.
- Aufwand: 10 Minuten je Rechner. Pflege: keine, bis etwas verloren geht.

### Was jede Option für d619148 und `skill-format` heißt

| | d619148 (gepusht, nicht installiert) | Branch `skill-format` (lokal, 2 Commits) |
|---|---|---|
| A | wirkt erst nach Versionssprung (0.4.1) oder ohne `version`-Feld | Plan schrumpft auf 3 bis 4 Skills; Prüfskript und `validate_kern`-Anbindung sind dann Ballast |
| B / B' | Repo-Stand von `umfang` wird kopiert, d619148 ist automatisch drin; Doppelung mit CLAUDE.md auflösen | Kern-Wächter entfällt; `skill-format.md` als kurze Regel ins Setup-Repo oder in den Workspace, ohne Prüfskript |
| C | `umfang`-Inhalt landet als Rule/Skill im Workspace | Konvention wird Workspace-Regel; Everlast hat mit `amm-hausformat` schon ein Hausformat (Abgleich in P7) |
| D | wie B, nur ohne Versionierung | Branch bleibt liegen; Inhalt nur als Notiz |

In keiner Option lohnt es sich, den Plan `2026-11-13-skill-format.md` so umzusetzen wie geschrieben
(8 Skills, 4 davon ziehen um, Prüfskript gegen den Kern-Wächter). Der Branch kann ungemergt liegen bleiben,
bis P7 klärt, wo Skills künftig gebaut werden. Löschen nur mit Freigabe.

---

## 4. Ehrliche Empfehlung (minimal)

1. **agentic-os als Familie beenden.** Die Mechanik (Wächter, Geräte-Setup, Konventionen, Spec, Tutorial)
   hat nur in der Mehr-Repo-Welt einen Zweck. Nach dem Umbau Repo auf GitHub archivieren, nicht löschen.
2. **Das Allgemeine in ein kleines Setup-Repo (Option B, Variante B' oder neu).** Nur: globale CLAUDE.md,
   `umfang`, `three-brain` (gekürzt, Modell- und Reviewer-Zeile direkt im Skill statt `routing/*.yaml`),
   `grilling`, `statusline.py`, Ausgabestil, settings-Vorlage. Kein Schema, kein Wächter, keine Tests.
3. **Installationsskript nur, wenn ein zweiter Rechner wirklich regelmäßig genutzt wird.** Sonst reicht
   eine README mit den Kopierbefehlen (das ist D, aber versioniert).
4. **Kein Plugin mehr für drei Skills** (Option A), solange es nur einen Nutzer gibt: Ein Plugin löst
   CLAUDE.md und statusline nicht und bringt Versionspflege mit. Ausnahme: Markus will den Namensraum
   `agentic-os:` unbedingt behalten (Frage 4).
5. **Marketing-Teile (b) ziehen in den Workspace** (wiki/, werkzeuge, Medienzeilen aus `routing/`),
   wie schon für commerce-os entschieden.
6. Sofort und unabhängig davon: die fünf Doppelungen aus 1.3 auf **eine** Quelle zurückführen
   (globale CLAUDE.md als einzige Regelquelle, Skills verweisen nur), Codex-Denkstufe angleichen.

Was dabei bewusst wegfällt: Soll-/Ist-Inventar, `setup.ps1 -Pruefen`, Kern-Wächter, Routing-Schemas mit
`pruefen_bis`, Tutorial-Generator, Familienkatalog. Zukunftsfälle (z. B. „Team bekommt die Regeln auch“)
auf `SPAETER.md`.

---

## 5. Fragen für das Grilling

1. Wie oft wechselst du tatsächlich den Rechner? Gibt es heute einen zweiten aktiven (die VM `AI-SANDBOX`
   aus dem Bericht vom September), oder ist es Vorsorge?
2. Soll irgendwann jemand anderes (Team, Freelancer) deine allgemeinen Regeln bekommen? Nur dann lohnt
   ein Plugin/Marketplace.
3. Darf agentic-os nach dem Umbau archiviert werden (GitHub „archived“, lokal bleibt der Ordner), oder
   soll das Repo als B' weiterleben und nur schrumpfen?
4. Ist dir der Präfix `agentic-os:` an den Skills wichtig, oder dürfen sie global einfach `umfang`,
   `three-brain`, `grilling` heißen?
5. Soll `three-brain` auf das reduziert werden, was du nutzt (Codex-Review, Modellwahl-Gate), und die
   Teile Antigravity, Konsensmodus, Multimodal, Vollständigkeitssuche wegfallen? Welche davon nutzt du wirklich?
6. Wo steht künftig die Modellwahl: nur in der globalen CLAUDE.md (eine Zeile) oder weiter in einer
   eigenen Datei mit Datum und `pruefen_bis`?
7. Sollen Session-Protokoll, Ledger und Startpunkt-Vorlagen allgemein bleiben, oder ersetzt das
   Everlast-Muster (`entscheidungen.md`, `arbeitslog.md`, Handoff in `STAND.md`) sie ganz?
8. Brauchst du den Commit-Wächter in irgendeinem künftigen Repo noch, oder reicht Git ohne Hook?
9. Nutzt du `skill-anleitung` (HTML-Anleitungen zu Skills) und den Hook „neue Skills gefunden“ wirklich?
10. Branch `skill-format`: liegen lassen bis P7, Konvention als Notiz in den Workspace übernehmen, oder
    ganz verwerfen?
11. Statusline und der P0-Vorschlag (Kontext-Datei plus `UserPromptSubmit`-Hook): Gehören sie ins
    Setup-Repo (rechnerweit) oder in den Workspace (nur dort)?
12. Settings-Abweichungen: Soll das Standardmodell sonnet/high bleiben (settings.json) oder
    Opus 5.5/medium (rollen.yaml)? Und Codex `medium` oder `xhigh` als Rückfall in `config.toml`?
13. commerce-os ist zweimal im Projekt-Scope für `E:\tegards\marketing` / `E:\Tegards\marketing` installiert
    und in zwei Marketplaces gelistet: Bereinigen beim Umzug in den Workspace (P5/P7)?
14. Canary-Präfix und Security-Check-Satz: bleiben sie global, und soll der Workspace sie nur schärfen dürfen
    (Everlast-Regel „global nur schärfen“)?

---

## Quellen

- [Q1] Settings files and precedence: https://code.claude.com/docs/en/settings
- [Q2] Create a marketplace: https://code.claude.com/docs/en/plugin-marketplaces
- [Q3] Host and maintain a marketplace (Updates, Version, Auto-Update):
  https://code.claude.com/docs/en/plugins/host-marketplace.md
- [Q4] Add components to a plugin (keine CLAUDE.md im Plugin):
  https://code.claude.com/docs/en/plugins/components.md
- [Q5] Memory / CLAUDE.md, Imports, `~/.claude/rules/`: https://code.claude.com/docs/en/memory
- Lokal gelesen: `E:\agentic-os\{CLAUDE.md, README.md, SPAETER.md, .claude-plugin\*, hooks\hooks.json,
  routing\*.yaml, geraete\README.md, geraete\soll-inventar.yaml, docs\migration\claude-konfiguration.md,
  docs\plans\2026-11-13-skill-format.md, skills\*\SKILL.md (Überschriften/Kopplungen)}`;
  `C:\Users\marku\.claude\{CLAUDE.md, settings.json (nur Struktur), statusline.py (Kopf),
  plugins\installed_plugins.json, plugins\known_marketplaces.json}`; `~/.codex/config.toml` (nur Modellzeilen);
  `E:\Everlast Learning\marketing-workspace-0.5.0\{CLAUDE.md, AGENTS.md, START-HIER.md, .claude\settings.json
  (Struktur), .claude\rules\README.md, .claude\skills\amm-konflikt-scan\references\vorrang.md (per Suche)}`.
