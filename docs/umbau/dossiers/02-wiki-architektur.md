# Dossier P2: Wiki-Architektur Best-of

Stand 13.11.2026 · Vorbereitung für das Grilling zu P2 · nur gelesen, nichts geändert.
Quellen: Artefakte „Tegards-Wiki erklärt“ (Stand 12.11.) und „LLM Wiki im Faktencheck“ (Stand 12.11.), `E:\tegards\knowledge\`,
`E:\agentic-os\wiki\`, `E:\agentic-os\plugins\werkzeuge\`, `E:\commerce-os\references\querschnitt\wissen-laden.md`,
`E:\tegards\marketing\docs\plans\commerce-os-session-15-startpunkt.md`, `E:\Everlast Learning\marketing-workspace-0.5.0\`.
Token-Angaben sind Schätzungen aus Dateigrößen (Faustregel 3,5 bis 4 Byte je Token bei deutschem Markdown), nicht gemessen.

---

## 1. Fakten

### 1.1 Tegards-Wiki (`E:\tegards\knowledge\`)

**Aufbau, drei Schichten plus Verwaltung**
- `eingang/`: Briefkasten, nicht in Git. Liegen heute: 12 Ordner mit Namen wie die schon übernommenen Quellen plus 12 Rohdateien (PDFs, eine `.md`).
- `quellen/<bereich>/<jjjj-mm>_<art>_<gegenstand>_<sprache>[_v<nr>]/` mit `original.<ext>` (Binärdateien nicht in Git), `extrakt.md` (1:1 per Skript, Seitenmarken), `karte.md` (Steckbrief, sha256, Prüfstellen-Tabelle). Heute zwei Bereiche: `produkte/`, `technik/`; 12 Quellenkarten.
- `wiki/`: 26 Seiten laut Artefakt, Ordner `unternehmen/` (kern, profil, ziele-und-strategie, markenversprechen-usps), `produktlinien/` (2), `zielgruppen/` (4 Personas), `wettbewerber/` (6 plus `serp-analysen/`), `sortiment/` (1), `technik/` (1), `synthesen/` (leer).
- Verwaltung: `_SCHEMA.md` (136 Zeilen, einzige Regelquelle, mit Block `wiki-konfig`), `INDEX.md` (generiert, 3,7 KB), `wiki/_verzeichnis.md` (5 KB), `log.md` (26 Einträge, nur Anhängen), `pruefungen.md` (3 offene Prüffälle `ungepruefte_erweiterung` seit 27.10.), `register/identitaeten.json`, `indexer.yaml` (Bereiche, Sperrliste).
- Maschinenzustand: `.pakete/` (33 Paketordner), `.journal/` (`funde.jsonl`, `register-neu.json`), `.zustand/` (`abgleich.lock`, `graph.json`, `zustand.json`, `gesundheit.md`, `fehler.log`).

**Regeln (`_SCHEMA.md`)**
- Nur die KI schreibt Seiten, ein Freigeber (`human:mm`, `human:bs`) gibt jede Änderung frei; Freigabe hängt am Fingerabdruck des Pakets. „Ein Paket = ein Diff = eine Freigabe = ein Commit.“
- Harte Produktfakten nur mit Beleg auf Quellenstelle (`[intern: quelle:/<ordner>/r<n>#seite-<n>]`); Wiki-Seite ist kein Rohbeleg.
- Widersprüche markieren, nie auflösen (Warnblock auf jeder Seite + Prüffall). Ungeklärte Werte nur mit Warnblock.
- Quellfassungen unveränderlich, neue Fassung = `_v<nr>`, alte bekommt `ersetzt_durch`.
- Frontmatter OKF-nah: `id`, `type` (quelle/entitaet/thema/synthese), `art`, `description` (1 Satz), `status`, `generated`, `verified`, `produktlinien`, `sources`, `beziehungen`.
- Pflichtabschnitte Produktlinie: „Technische Fakten“, „Trust-Faktenliste“, „No-Gos“, „Offene Fragen“.
- Wettbewerber: `## Profil` (zeitlos) + `## Beobachtungen` (datiert, nur ergänzen, Kopf mit `erhoben_am`, `url`, `methodik`); `profil_geprueft_am` älter 6 Monate ⇒ Warnung.

**Werkzeuge und Skills**
- `E:\agentic-os\wiki\werkzeuge\`: 23 Python-Module, 11 123 Zeilen (größte: `paketkern.py` 1 409, `abgleich.py` 1 138, `sperre.py` 975, `waechter.py` 947, `wiki_cli.py` 924, `paket.py` 819, `pruefstellen.py` 737), 24 Testdateien, `hooks/pre-commit`. Kopie in `E:\tegards\knowledge\werkzeuge\`.
- Skill `wiki-ingest` (119 Zeilen + 5 References, 355 Zeilen): Duplikatprüfung per sha256, Extrakt, Prüfstellen, Prüfseite, Karte, Paket, Freigabe, Commit.
- Skill `wiki-pruefen` (49 + 46 Zeilen): Duplikate, Widersprüche, Persona-Abdeckung, Prüffälle; Ergebnis ist Paket der Art `pruefen`.
- Agent `pruefstellen-klaerer` (59 Zeilen, immer Sonnet, nur Read): Status je Prüfstelle (KI bestätigt / ergänzt / gelesen / offen / nicht lesbar / verworfen). Prüfseite als lokale HTML mit Stichprobe 5, bei Fehler 10, dann alle.
- Nach Ordnernamen betreffen rund 14 der 33 Pakete Werkzeuge, Wartung, Schema oder Leseweg, nicht Fachwissen.

**Lesen und Kontext**
- `E:\tegards\CLAUDE.md` importiert `@AGENTS.md` und `@knowledge/wiki/unternehmen/kern.md` (3,7 KB ≈ 1 k Token) in jede Session unter `E:\tegards`.
- Leseregel (`E:\tegards\knowledge\AGENTS.md`, `wissen-laden.md`): `INDEX.md` → passende Seite ganz lesen (inkl. Frontmatter, No-Gos, Warnblöcke) → bei Quellen Karte und zitierte Revision. Grep nur zum Finden. Seit 31.10. kein Such-Werkzeug und kein `wiki-leser`-Agent mehr.
- Ladevertrag `E:\commerce-os\references\querschnitt\wissen-laden.md` (95 Zeilen): Kern → Linienseite → gezielt weitere Seiten → Personas der Linie. Agenten lesen das Wiki nie selbst, sie bekommen `WISSEN-AUSZUG:` ≤ 16 000 Byte mit Pflichtteil (No-Gos, Warnblöcke).
- Rückweg heute: Skill legt Eingangspaket `eingang/<datum>_<art>_<gegenstand>_de/original.md` mit `herkunft` ab, dann `wiki-ingest`.
- Seitengrößen: `lamellendaecher.md` 52,6 KB (≈ 14 k Token), `glasschiebewaende-deluxe.md` 32,7 KB (≈ 9 k), Personas je ≈ 7 KB (≈ 2 k), Wettbewerber 6 bis 12 KB, SERP-Analyse 16 KB.

**Synthese-Rückweg (Entwurf, nicht entschieden)** – `commerce-os-session-15-startpunkt.md` Zeilen 44–50:
Claude schlägt nach einer Wiki-Antwort in einem Satz die Ablage vor; Ja = Gate-3-Freigabe, dann Paket über `wiki-ingest`;
Pflichtfeld `stuetzt_sich_auf` (Seiten-id + Freigabestand), Wächter meldet Veraltung; Kriterien: ≥ 3 Seiten oder eigene
Auswertung, vorher `wiki/synthesen/` durchsuchen, höchstens ein Vorschlag je Thema und Session, headless keiner.
Faktencheck-Artefakt bewertet „Antworten zurückschreiben“ als größten Hebel und Variante „Claude schlägt vor“ als empfohlen.

### 1.2 Everlast (`E:\Everlast Learning\marketing-workspace-0.5.0\`)

**Feste Fächer mit Stubs**
- `stammdaten/` (`unternehmen.md`, `personal-data.md`), `strategie/` (`positionierung/` 10 Dateien, `brand-identity/`, `umwelt/` mit `makroanalyse/`, `mikroanalyse/competitor.md`, `porters-five.md`, `reviews-mining.md`, `swot.md`, `ziele/`), `produkte/<produkt>/` (`offer.md`, `ziele.md`, `casestudies.md`, `competitor.md`, `zielgruppe/icp.md`, `persona.md`, `voice-of-customer.md`), `kanaele/` (6 Dateien), `swipefile/` (13 Fächer mit README), `wissen/` (38 Kursblätter, flach, Feld `lektion`).
- Stub-Frontmatter: `status: stub`, `last_updated:`, `source:`; Rumpf „Noch nicht ausgefüllt. Hier gehört hinein: …“ (≈ 170 Byte je Datei).
- `amm-workspace-setup`: „Die Stubs bleiben Stubs. Die Analyse-Skills erkennen daran ihren Ablageort“; Fortschritt = Datei ohne `status: stub`. „Nie überschreiben“.
- Ordnungsdateien: `AGENTS.md` (≈ 4 KB, jede Session und jeder Agent), `CLAUDE.md` ist ein Symlink (unter Windows liegt eine 9-Byte-Textdatei „AGENTS.md“, Port-Thema für P7), `.claude/references/workspace-karte.md` (2,6 KB, Dateinamen je Ordner).

**Rückfluss in den Kontext**
- `/prime` (`.claude/commands/prime.md`): genau 6 Dateien (Stammdaten, Positionierung, Produkte, Zielgruppen, Zielhierarchie), Antwort nur „✅“, keine siebte Datei.
- `/prime-content` (+8 Dateien plus Personal-Brand-Steckbriefe und Zielgruppen je Produkt), `/prime-design`, `/prime-strategie` (≈ 20 Dateien, ausdrücklich ohne Arbeitsordner `JJMMTT-` und Reports), `/prime-ads`, `/prime-daten`.
- Agenten (`.claude/agents/*.md`, Abschnitt „2. Context“): Pflichtlektüre beim Spawn = prime + prime-<fach>, Projektgedächtnis (`entscheidungen.md`, `review.md`), Kanaldateien inkl. `content-learnings.md`, Swipefile, eigenes Agent-Memory.
- SessionStart-Hook (`.claude/settings.json`) lädt `.claude/head-of-marketing.md` (153 Zeilen) nur in die Hauptsession; `.claude/rules/*.md` teils mit `paths:` (z. B. `projekte-und-namen.md`).

**Wissenspflege und Gedächtnis**
- Workflow D (`.claude/head-of-marketing.md` Z. 45–49): Wissensdateien pflegt nur der Head; jeder Agent liefert je Lauf 3–5 Zeilen Destillat; Head trägt mit Datum ein (Content → `kanaele/content-learnings.md`, Voice → Voice-Datei, Design → `brand-design/`).
- `kanaele/content-learnings.md`: „wächst nur durch Anhängen, nie durch Überschreiben“ (AGENTS.md). Keine Verdichtungsregel.
- Agent-Memory: `memory: project` in allen 6 Agenten, Ordner `.claude/agent-memory/`; Destillat geht „zusätzlich ins eigene Memory“ (z. B. `content-marketer.md` Z. 71).
- `workspace-cleanup`: Archiv-Ordner per Subagenten destillieren nach `wissen/workspace-memory/<JJMMTT>-archiv-kern.md` (6 Abschnitte, < 400 Zeilen, Quellpfad je Punkt, `quelle_commit`), dann Freigabe, dann löschen. Nutzt `osascript` (Mac), `python3`.
- `learn`: Material (Video, PDF, Kurs) → genau 1 Skill mit `references/herkunft.md`, nie eine Zusammenfassung.
- Projektgedächtnis: `projekte/JJMMTT-<slug>/` mit `entscheidungen.md`, `review.md`, `arbeitslog.md` (nur Anhängen), Fassungen `-vN`, nichts löschen, `archiv/` im Projekt; `projekte/backlog/`.

---

## 2. Unterschiede

| Merkmal | Tegards | Everlast |
|---|---|---|
| Grundgedanke | Karpathy-Wiki: Quelle → Beleg → verdichtete Seite | Strategie-Ordner: feste Ergebnisdateien je Methode |
| Struktur | Seitentypen + Entitäts-Arten, Ordner frei nach Gegenstand | feste Ordner und Dateinamen, Stubs markieren Ablageorte |
| Wer schreibt | nur KI, Freigabe je Paket durch human:mm/bs | Skills schreiben in Stubs, Head pflegt Wissensdateien |
| Belege | Pflicht für harte Fakten, mit Seitenanker im Extrakt | Feld `source:`, ohne Format und ohne Prüfung |
| Rohquellen | `quellen/` unveränderlich, Original + Extrakt + Karte | `daten/` (Rohdaten, Auswertungs-Läufe), keine Quellenkarten |
| Unsichere Werte | Prüfstellen, Warnblöcke, Prüffälle | keine eigene Mechanik („nichts wird geraten“) |
| Widersprüche | markieren, nie auflösen | `amm-konflikt-scan` (Skill), sonst keine Regel |
| Index | `INDEX.md` generiert, 1 Satz je Seite | `workspace-karte.md` (handgepflegt, Dateinamen) |
| Kontext immer | `kern.md` per `@`-Import (≈ 1 k Token) | `AGENTS.md` (≈ 1 k) + Head-Datei (≈ 2–3 k, nur Hauptsession) |
| Kontext bei Bedarf | Index → Seite → Grep, frei nach Urteil | feste `/prime*`-Leselisten |
| Agenten | lesen nie selbst, `WISSEN-AUSZUG` ≤ 16 KB | lesen selbst prime-Listen, Projekt- und Kanaldateien |
| Lernen aus Arbeit | Synthesen vorgesehen, Ordner leer, Ablauf fehlt | Destillat → `content-learnings.md` (Anhängen) + Agent-Memory |
| Verdichten | Synthese mit `stuetzt_sich_auf` (Entwurf) | `workspace-cleanup` für Archive |
| Wettbewerb | 6 Entitätsseiten, Profil + datierte Beobachtungen | `strategie/umwelt/mikroanalyse/competitor.md` + `produkte/<p>/competitor.md` |
| Personas | 4 Seiten, linienübergreifend (`produktlinien: [..]`) | je Produkt `zielgruppe/persona.md` + `strategie/positionierung/zielgruppen.md` |
| Werkzeuggewicht | 11 123 Zeilen Python, Paket/Wächter/Sperre/Journal/Locks | keine Wiki-Werkzeuge; Prüfskripte für Pfade und Format |
| Protokoll | `log.md` global, festes Präfix | `arbeitslog.md` je Projekt |
| Plattform | Windows, Python/uv | Mac-zentriert (`osascript`, Symlink, `python3`, bash-Hooks) |

---

## 3. Lücken

### 3.1 Tegards
1. **Rückweg Synthese fehlt**: Typ und Ordner da, null Seiten, nur Entwurf. Lernen aus Arbeit (was hat funktioniert) gibt es gar nicht, das Wiki kennt nur Firmenfakten.
2. **Strategie-Ebene fehlt**: Keine Fächer für Positionierung je Linie, Brand Voice, Ziele/KPIs, Kanäle, Content-Säulen (liegt verteilt in `marketing/marketing-wissen/`, eigene Regeln, eigenes `verified`).
3. **Zwei Wissensorte, zwei `verified`-Bedeutungen** (Wiki = freigegeben, Marketing = vollgeprüft): erklärungsbedürftig, Fehlerquelle.
4. **Werkzeuggewicht gegen Nutzen**: Rund 14 von 33 Paketen sind Werkzeug/Wartung. 3 Prüffälle seit 27.10. offen, Eingang nicht geleert. Das System kostet Pflege, bevor es Wissen liefert.
5. **Große Linienseiten** (52 KB) machen den Index-Weg teuer: Jede Produktfrage lädt ≈ 14 k Token, Ausschnitte sind laut Leseregel verboten.
6. **Kein Werkzeug für Lernen** aus Kursmaterial (Everlast `learn`), kein Projektgedächtnis im Wiki.

### 3.2 Everlast
1. **Keine Belegkette**: `source:` ist Freitext; ein Wert aus einem Datenblatt ist von einer Vermutung nicht unterscheidbar. Für technische Produkte (Statik, Maße) zu schwach.
2. **Kein Quellenlager**: PDFs, Datenblätter, Montageanleitungen haben keinen Ort; `daten/` ist für Auswertungen gedacht.
3. **Learnings wachsen unbegrenzt**: nur Anhängen, keine Verdichtung, kein Ablaufdatum, Widersprüche zwischen alten und neuen Zeilen bleiben stehen. Agent-Memory doppelt dieselben Zeilen, unsichtbar für andere Agenten und nicht freigegeben.
4. **Kein Index für wachsende Ordner**: Prime-Listen kennen nur feste Dateien; Wettbewerber, Synthesen oder viele Personas fallen heraus.
5. **Wettbewerb doppelt** (umwelt und je Produkt), ohne Datierung von Beobachtungen.
6. **Wiederholte Ladekosten**: Jeder Agenten-Spawn liest prime + prime-<fach> neu.
7. **Widerspruch in sich**: `wissen/README.md` verlangt flache Blätter, `workspace-cleanup` schreibt nach `wissen/workspace-memory/`.

---

## 4. Optionen

### 4.1 Feste Fächer vs. LLM-gepflegt

| Option | Inhalt | Vorteile | Nachteile |
|---|---|---|---|
| A Everlast pur | Alle Dateien fest, Stubs, Skills füllen | vorhersagbar, prime-Listen funktionieren, Setup-Stationen erkennen Fortschritt | wachsende Mengen (Wettbewerber, Quellen, Synthesen) passen nicht |
| B Tegards pur | Seitentypen, KI legt Seiten frei an, Index generiert | wächst mit, Belege | Strategie-Ebene fehlt, Struktur hängt am Werkzeug |
| **C Hybrid** | **Gerüst fest (Ordner + Kerndateien als Stubs), offene Sammelordner mit Index, die die KI befüllt** | prime bleibt deterministisch, Wachstum hat einen Ort | zwei Regeln statt einer (fest vs. offen) |

Vorschlag Abgrenzung für C:
- **Fest (Markus kuratiert Ordner und Dateinamen, Stub = Ablageort):** `stammdaten/`, `strategie/positionierung/`, `strategie/brand-identity/`, `strategie/ziele/`, `strategie/umwelt/*.md` (Übersichten, SWOT), `produkte/<linie>/` mit festen Dateien, `kanaele/`.
- **Offen (KI legt Dateien an, Index führt sie):** `strategie/umwelt/wettbewerber/<name>.md`, `strategie/zielgruppen/` bzw. Personas (siehe Frage 6), `quellen/`, Synthesen, `swipefile/<fach>/`, `projekte/`.
- Inhalt fester Dateien schreibt die KI (Skill oder Head), nie ohne Commit, den Markus sieht. Eine neue feste Datei ist eine Entscheidung, keine KI-Aktion.

### 4.2 Rückfluss in den Kontext (Kosten geschätzt)

| Weg | Wann geladen | Kosten heute / erwartet | Stärke | Schwäche |
|---|---|---|---|---|
| Always-on (`AGENTS.md`, `@`-Import Kern) | jede Session, jeder Agent | ≈ 1–2 k Token | nie vergessen | jede Zeile kostet überall |
| `/prime` (6 Dateien) | Sessionstart, Agenten-Spawn | Stubs heute ≈ 0,3 k; gefüllt geschätzt 3–6 k | deterministisch, prüfbar | lädt auch Unnötiges, wiederholt je Agent |
| `/prime-<fach>` | Fachaufgabe | gefüllt geschätzt 8–25 k (strategie am größten) | passend zum Fach | Liste muss gepflegt werden, offene Ordner fehlen |
| Index → Seite → Grep | bei Bedarf | Index ≈ 1 k + 1–3 Seiten; Tegards-Linie ≈ 9–14 k je Seite | skaliert, findet Neues | hängt am Urteil des Modells, große Seiten teuer |
| Hook SessionStart | Start/Compact | Head-Datei ≈ 2–3 k | rollenabhängig | nur ganze Dateien |
| `.claude/rules` mit `paths:` | nur bei passender Datei | 0 bis Regelgröße | billig, gezielt | nur für Regeln, nicht für Fachwissen |
| Agent liest selbst (Everlast) | je Spawn | prime + fach ≈ 10–30 k je Agent | Agent vollständig im Bild | Kosten je Spawn, keine Kürzung |
| `WISSEN-AUSZUG` (Tegards) | je Agentenauftrag | ≤ 16 KB ≈ 4–5 k je Agent, plus Hauptkontext zum Bauen | gedeckelt, Pflichtteil sicher | Hauptsession muss alles erst selbst lesen; Mehraufwand im Skill |

Folgerung: Für feste Dateien ist prime am billigsten im Denken und sicher; für offene Ordner ist Index → Seite nötig. Größter Kostentreiber ist nicht der Weg, sondern die **Seitengröße** (Tegards-Linienseiten) und das **wiederholte Laden je Agent**.

### 4.3 Learnings (Anhängen) vs. Synthese (Verdichten)

| | Learnings (Everlast) | Synthese (Tegards-Entwurf) | Cleanup (Everlast) |
|---|---|---|---|
| Auslöser | jeder Agentenlauf | Claude schlägt nach Antwort vor | Archiv leeren |
| Form | datierte Zeilen, nur anhängen | eigene Seite mit `stuetzt_sich_auf` | Kern-Datei mit Quellpfad je Punkt |
| Freigabe | keine eigene (Head trägt ein) | Ja-Satz + Paketfreigabe | Gate vor Löschen |
| Risiko | Wachstum, alte Zeilen gelten weiter, Widersprüche still | Aufwand, wird nie benutzt (heute 0) | selten, groß, Mac-Werkzeuge |
| Veraltung | keine | über Freigabestand erkennbar | `quelle_commit` als Rückweg |

**Schlankes kombiniertes Modell (Vorschlag):**
1. **Einsammeln = Anhängen.** Eine Datei je Fach (`kanaele/content-learnings.md` u. ä.), Zeile: Datum · Erkenntnis · Beleg (Projektpfad oder Zahl). Kein Agent-Memory für Fachwissen; Agent-Memory nur für Arbeitsweise (Regel aus dem Faktencheck).
2. **Verdichten = selten, mit Schwelle.** Ab z. B. 40 Zeilen oder quartalsweise: die KI schreibt oben einen Abschnitt „Gilt heute“ (≤ 15 Zeilen, je Punkt Verweis auf die Ursprungszeilen), alte Zeilen wandern in „Verlauf“ darunter. Prime/Agenten lesen nur „Gilt heute“. Markus gibt per Diff frei.
3. **Synthese aus Fragen = Vorschlag in einem Satz** (Tegards-Entwurf), aber als normale Datei im passenden Fach mit `stuetzt_sich_auf: [pfade]`, ohne Paketwerkzeug. Veraltung: später ein kleines Skript (Datum der Grundlage jünger als Synthese ⇒ Hinweis) – auf `SPAETER.md`, bis es die erste Synthese gibt.
4. **Cleanup** bleibt für Projekte-Archive, Ziel nicht `wissen/` (Kurswissen), sondern z. B. `projekte/archiv/<JJMMTT>-kern.md`.

### 4.4 Faktenweg mit Prüfstellen: schwer oder schlank?

Ehrlich: Paketkern, Fingerabdruck-Freigabe, Sperre/Sperrvererbung, Journal, Locks, Register, Abgleich und Graph sind für eine Lage gebaut, die es im Ein-Workspace nicht mehr gibt: mehrere Repos, Codex und Claude als Schreiber, zwei Freigeber, Schutz gegen Commits an den Paketen vorbei. In **einem** Git-Repo mit einer schreibenden Session ist **Git selbst das Paket**: Diff ansehen = Freigabe, Commit = Anwenden, `git revert` = Rückweg. Der Qualitätskern liegt in Regeln, nicht in den 11 000 Zeilen.

| Baustein | Behalten? | Schlanke Form |
|---|---|---|
| Quellen unveränderlich, Original + Extrakt + Karte | ja | Ordnerkonvention + kleine Prüfung im Pre-Commit (Datei unter `quellen/` geändert ⇒ Fehler) |
| Extrakt per Skript mit Seitenmarken | ja | ein Skript (docling-Aufruf aus `extrakt.py`/`pruefstellen.py` herauslösen) |
| Prüfstellen + Klärer-Agent (Sonnet) | ja, wo Bilder Werte tragen | Agent bleibt; Prüfseite optional, sonst Liste mit Bildpfaden im Chat |
| Stichprobenregel 5/10/alle | ja | als Regel im Skill, kein Werkzeug |
| Belegformat mit Seitenanker | ja | wie heute |
| Warnblock bei Widerspruch und ungeklärtem Wert | ja | wie heute |
| Prüffälle `pruefungen.md` | vereinfachen | Abschnitt „Offene Fragen“ je Seite + eine Liste, keine Kennungen |
| `log.md` | ja | Git-Log + Commit-Konvention reicht, oder eine Zeile je Ingest |
| Paket, Fingerabdruck, Journal, Locks, Register, Graph, Abgleich | nein | entfällt; Git-Diff + Commit |
| Wächter (947 Zeilen) | stark kürzen | Pre-Commit ≤ ~150 Zeilen: Frontmatter-Pflichtfelder, Quellen unverändert, Belegpfade lösen auf |
| Zwei Freigeber | offen | nur wenn human:bs wirklich freigibt (Frage 10) |

Risiko der schlanken Form: Ohne Fingerabdruck kann eine spätere Änderung unbemerkt vor dem Commit dazukommen. Gegenmittel: ein Ingest = ein Commit, Diff wird vor dem Commit gezeigt. Das deckt den Einzelplatz ab.

### 4.5 Ort im neuen Workspace

| Option | Beschreibung | Vorteile | Nachteile |
|---|---|---|---|
| W1 eigenes `wiki/` neben Everlast-Ordnern | Tegards-Wiki 1:1 als Unterordner | wenig Umbau | zwei Wissenswelten, Doppelungen (Personas, USPs, Wettbewerb), prime sieht es nicht |
| **W2 Wiki = Everlast-Fächer** | Tegards-Inhalte in die Everlast-Ordner, plus `quellen/` als Belegschicht | ein Ort je Thema, prime/Agenten passen | Umzug der Inhalte, Linienseiten zerschneiden |
| W3 Everlast-Fächer + `wissen/` als LLM-Wiki | Fakten in `wissen/` | klare Trennung | kollidiert mit Kurswissen-Logik von `wissen/` |

Zuordnung für W2 (Vorschlag):

| Tegards heute | Neuer Ort (Everlast-Logik) | Bemerkung |
|---|---|---|
| `wiki/unternehmen/kern.md` | `stammdaten/unternehmen.md` (+ Kurzfassung in `AGENTS.md`?) | Kern entspricht funktional prime |
| `wiki/unternehmen/unternehmensprofil.md` | `stammdaten/unternehmen.md` | zusammenführen |
| `wiki/unternehmen/ziele-und-strategie.md` | `strategie/marketingstrategie.md`, `strategie/ziele/zielhierarchie.md` | aufteilen |
| `wiki/unternehmen/markenversprechen-usps.md` | `strategie/positionierung/usps.md` | |
| `wiki/produktlinien/<linie>.md` | `produkte/<linie>/` (Everlast-Dateien) + neue Datei `fakten.md` (Technische Fakten, Trust, No-Gos, Offene Fragen) | Name `produkte/` behalten, Ordner = Linien-id (`lamellendaecher`, `glasschiebewaende-deluxe`); löst auch die 52-KB-Seite auf |
| `wiki/sortiment/fixverglasung.md` | `produkte/<linie>/sortiment/` oder `produkte/fixverglasung/` | Frage 7 |
| `wiki/technik/statik-…md` | `produkte/glasschiebewaende-deluxe/technik.md` | |
| `wiki/zielgruppen/persona-*.md` | `strategie/positionierung/zielgruppen/persona-*.md` (linienübergreifend), `produkte/<linie>/zielgruppe/persona.md` nur Verweis + Linienbesonderheiten | Frage 6 |
| `wiki/wettbewerber/<name>.md` | `strategie/umwelt/wettbewerber/<name>.md` (Profil + Beobachtungen) | `mikroanalyse/competitor.md` = Übersicht, `produkte/<linie>/competitor.md` = Auswahl je Linie |
| `wiki/wettbewerber/serp-analysen/` | `seo/` (Everlast hat `seo/`) oder Beobachtung | P3 |
| `quellen/` | `quellen/` (neu, Wurzel) | Binär nicht in Git |
| `eingang/` | `quellen/_eingang/` | Everlast `inbox/` ist der Briefkasten an Markus, nicht für Quellen |
| `INDEX.md` | `.claude/references/workspace-karte.md` erweitern um offene Ordner, oder je offener Ordner ein `README.md` mit 1 Zeile je Datei | |
| `log.md`, `pruefungen.md` | Git-Log; „Offene Fragen“ je Datei | |
| `wiki/synthesen/` | im Fach, z. B. `strategie/umwelt/synthesen/` oder `produkte/<linie>/` | Frage 9 |
| `marketing/marketing-wissen/*` | in dieselben Fächer (positionierung, redaktion → `brand-voice`, seo-geo → `seo/`) | P3/P4 klären Details |

---

## 5. Empfehlung Best-of

1. **Ein Wissensort, Everlast-Gerüst (W2 + Hybrid C).** Feste Fächer mit Stubs bleiben, wie sie sind; Tegards bringt drei Dinge hinein: `quellen/` als Belegschicht, offene Sammelordner (Wettbewerber, Personas) mit Index, Datei `fakten.md` je Produktlinie mit den vier Pflichtabschnitten.
2. **Tegards-Regeln übernehmen, Tegards-Werkzeuge nicht.** Belegpflicht für harte Fakten, Seitenanker, Quellen unveränderlich, Widerspruch markieren, Warnblock bei ungeklärten Werten, Wettbewerber als Profil + Beobachtungen. Diese Regeln passen in eine Rule-Datei mit `paths:` (`quellen/**`, `produkte/**`, `strategie/umwelt/**`) und kosten nur dort Kontext.
3. **Faktenweg schlank:** Skill „quelle-einpflegen“ = Extrakt-Skript + Klärer-Agent + Karte + betroffene Dateien + ein Commit nach Diff-Ansicht. Pre-Commit-Prüfung klein. Kein Paket/Journal/Lock/Register/Graph. Wenn Werte aus Bildern selten sind, Prüfseite weglassen und offen bleibende Stellen als Liste zeigen.
4. **Kontext:** prime-Listen nach Everlast für feste Dateien; offene Ordner über `README.md`-Index je Ordner; Agenten lesen selbst (Everlast), aber nur `fakten.md` und „Gilt heute“-Abschnitte, nicht ganze Verläufe. `WISSEN-AUSZUG` nur dort behalten, wo Agenten mit großen Dateien arbeiten (später prüfen).
5. **Lernen:** Learnings anhängen + seltene Verdichtung in „Gilt heute“; Synthese-Vorschlag in einem Satz nach Tegards-Entwurf, Ablage im Fach; Agent-Memory nur Arbeitsweise; `learn` für Kursmaterial übernehmen.
6. **Auf `SPAETER.md`:** Veraltungs-Skript für Synthesen, Volltextsuche (erst ab ~150–200 Seiten), zweiter Freigeber, typisierte Beziehungen, Prüfseite als HTML falls Bildstellen häufig werden.

---

## 6. Fragen für das Grilling

1. Ein Wissensort (W2, Tegards-Inhalte in Everlast-Fächer) oder Tegards-Wiki als eigener Ordner (W1)?
2. Welche Ordner sind für dich „fest“ (nur du legst Dateien an), welche darf die KI frei wachsen lassen? Reicht die Liste in 4.1?
3. Bleibt die Regel „harte Produktfakten nur mit Beleg auf Quellenstelle“ in voller Strenge, oder nur für technische Werte (Maße, Statik, Zertifikate)?
4. Reicht dir „Diff ansehen, dann ein Commit“ als Freigabe, oder brauchst du eine eigene Freigabe-Geste je Änderung (Paket, Prüfseite)?
5. Wie oft kommen Datenblätter mit Werten in Bildern vor? Davon hängt ab, ob Prüfstellen-Agent und Prüfseite mitgehen oder nur der Agent.
6. Personas: einmal linienübergreifend unter `strategie/` (Tegards) oder je Produkt unter `produkte/<linie>/zielgruppe/` (Everlast)?
7. Sortiment (Fixverglasung) und Technik: eigene Produktordner, Unterordner der Linie oder eigener Ordner?
8. Wettbewerber: `strategie/umwelt/wettbewerber/<name>.md` mit Profil + Beobachtungen, und `produkte/<linie>/competitor.md` nur als Auswahl je Linie – einverstanden?
9. Wo liegen Synthesen: im jeweiligen Fach oder in einem Sammelordner? Und gilt „Claude schlägt einmal vor, du sagst Ja/Nein“ als Ablauf?
10. Gibt human:bs künftig Wissen frei, oder bist du einziger Freigeber?
11. Learnings: Verdichtungsschwelle (Zeilenzahl oder Zeitraum) und wer verdichtet (Head auf Zuruf, fester Termin)?
12. Agent-Memory: nur Arbeitsweise erlauben und Fachwissen verbieten?
13. Linienseiten aufteilen (Everlast-Dateien + `fakten.md`) oder als eine große Seite behalten?
14. Agenten lesen selbst (Everlast) oder bekommen einen gedeckelten Auszug (Tegards)? Oder gemischt nach Agent?
15. Wohin mit `marketing/marketing-wissen/` (Positionierung, Redaktion, SEO-GEO, Content-Inventar) – hier entscheiden oder an P3/P4 übergeben?
16. Wie gehen die vorhandenen 12 Quellen samt Extrakten und Karten über: 1:1 kopieren oder neu einpflegen?
17. Wird `wissen/` nur Kurswissen (Everlast-Logik), und landet `workspace-cleanup` woanders als in `wissen/workspace-memory/`?
18. Soll `kern.md` als Always-on-Import bleiben, oder ersetzt `/prime` ihn ganz?
