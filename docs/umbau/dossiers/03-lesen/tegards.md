---
thema: P3 – Lesebericht Tegards-Seite (commerce-os + Instanz tegards + TG-Design-Seitenvorlagen)
art: Faktenbericht, keine Empfehlungen
erstellt: 2026-11-16
stand_quellen: commerce-os v0.7.0 (Commit 3fbebab, 2026-11-01); tegards-Instanz Dateistand 2026-11-16; TG Design Dateistand 2026-11-08
---

# P3 – Tegards-Logik: SERP-geführte Kette bis zum Seitenschema

## 0. Lesart, Abkürzungen, Herkunft der Belege

**Pfad-Abkürzungen** (jede steht für genau einen absoluten Präfix):

| Kürzel | absoluter Pfad |
|---|---|
| `CO\` | `E:\commerce-os\` |
| `SK-LP`, `SK-KS`, `SK-PS`, `SK-BL`, `SK-PB`, `SK-KR`, `SK-PO` | `E:\commerce-os\skills\{landingpage,kategorieseite,produktseite,blog-beitrag,projekt-beitrag,keyword-recherche,positionierung}\SKILL.md` |
| `KON` | `E:\commerce-os\kontrakte.md` |
| `BST` | `E:\commerce-os\references\querschnitt\bausteine-content-skills.md` |
| `ZEB` | `E:\commerce-os\references\zielseiten-entscheidungsbaum.md` |
| `R-LP\`, `R-KS\`, `R-PS\`, `R-KR\`, `R-PO\`, `R-QS\`, `R-BL\`, `R-PB\` | `E:\commerce-os\references\{landingpage,kategorieseite,produktseite,keyword-recherche,positionierung,querschnitt,blog-beitrag,projekt-beitrag}\` |
| `T\` | `E:\commerce-os\templates\` |
| `A\` | `E:\commerce-os\agents\` |
| `INV\` | `E:\commerce-os\docs\invarianten\` |
| `SG\` | `E:\tegards\marketing\marketing-wissen\seo-geo\` |
| `PB`, `KL`, `WA`, `VS`, `RS`, `OG`, `KI` | `SG\seo-geo-playbook.md`, `SG\keyword-landkarte.md`, `SG\website-architektur.md`, `SG\verlinkungsstrategie.md`, `SG\referenzseiten.md`, `SG\offpage-geo.md`, `SG\ki-sichtbarkeit-log.md` |
| `PY` | `E:\tegards\marketing\projekt.yaml` |
| `SERP-GSW` | `E:\tegards\knowledge\wiki\wettbewerber\serp-analysen\2026-08-glasschiebewand.md` |
| `SV` | `E:\TG Design\ausgelagert\seitenvorlagen.md` |

**Wer hat was gelesen (ehrlich):** Selbst vollständig gelesen: die 7 SKILL.md, `ZEB`, `SERP-GSW`, `SV`, `PY` Z. 27–45, Köpfe der 5 Inventardateien, `E:\TG Design\ausgelagert\inhaltliche-grundsaetze.md` Z. 1–24. Alles übrige (Templates, schema-org, rankmath, woocommerce, alle References, `KON`, 8 Agenten, Manifest/Hook, Invarianten, 7 seo-geo-Dateien) wurde von 9 parallelen Lese-Unteragenten **vollständig** mit Read gelesen; Zeilenangaben stammen aus deren Read-Ausgabe. Stichproben gegen das Original habe ich selbst gemacht und bestätigt: `KON:85-101,137-167`, `PB:1-8,150-154,291-310`, `A\geo-validator.md:71-90`.

**Kernbefund vorab:** Die Tegards-Kette ist **SERP-first**: „ZUERST die ranking-optimale Variante … DANN gegen die eigenen Quellen abgleichen“ (`BST:21-24`, B1) und für alle 5 Content-Skills „Aus `## SERP-ERGEBNIS` ZUERST … Struktur, Argumentation und Value Proposition“ (`BST:131-135`, B8). Die Gliederung selbst ist aber je Seitentyp ein **festes Template** (14/12/12/12/14/13 Module, `CO\tests\test_templates.py:5-6`); aus der SERP werden Belegung, Keyword, FAQ-Quelle, Paritäts-Checkliste und Vergleichs-Marktstandard abgeleitet, nicht die Modulfolge.

---

## 1. Die Kette Ende-zu-Ende

### 1.0 Vorstufe je Produktlinie (optional): Positionierung
- **Skill** `positionierung`: „Einmal je Produktlinie, bevor Content entsteht“ (`SK-PO:9`).
- **Eingaben**: Linienseite + Personas laut Ladevertrag, Landkarte (nur Zeilen der Linie), `markenversprechen-usps.md`, Wettbewerber-Seiten (`SK-PO:30`); Marktsicht per `serp-analyst` (kurz) / `wettbewerbs-analyst` „Nur wenn der Approver es wünscht“ (`SK-PO:31`).
- **Ablauf**: Linie+Personas wählen (Gate, `SK-PO:29`) → JTBD + Einwand-Modell (`SK-PO:32`) → Value Props `verkauft`/`Floskel-Risiko` (`SK-PO:33`) → Angebot + Message Map (`SK-PO:34`) → `persona-anwalt` MODUS positionierung (`SK-PO:35`) → **Gate „Value-Props freigeben“** (`SK-PO:36`) → Schreiben (`SK-PO:37`).
- **Ausgabe**: `E:\tegards\marketing\marketing-wissen\positionierung\<linie>.md` (`PY:29`, Template `T\positionierung.md`, Block `KON:463-509`). **Instanzstand: Ordner enthält nur `.gitkeep` – keine Positionierungsdatei vorhanden.**

### 1.1 Keyword-Recherche
- **Skill** `keyword-recherche`, kein `serp-analyst`: „Schritt 4 extrahiert Title/H1/H2/Meta selbst per WebSearch/WebFetch“ (`SK-KR:30-31`).
- **Eingaben**: `PRODUKT` (Pflicht), `REGION` (Default 1. Markt), `SPRACHE` (`SK-KR:49-51`); `sitemap_lesen` + `inventar-sync` (`SK-KR:55-57`); `ZEB`, Landkarte inkl. KONFLIKT, `landingpages.md` + `kategorieseiten.md` (`SK-KR:59-64`); Linienseite für Modellnamen-Seeds (`SK-KR:68`).
- **Erhebung**: Suggest Google/Bing/DDG, Gewicht 3 (`SK-KR:66-72`); SERP Query A/B Top-10, Gewicht 2/1 (`SK-KR:74-76`; `R-KR\suggest-serp-erhebung.md:116-126`); 33 Pflicht-Modifikatoren (`R-KR\suggest-serp-erhebung.md:71-92`).
- **Score** wörtlich: „Score = (Vorkommen in Suggest * 3) + (Vorkommen in SERP-Titeln/ Headlines * 2) + (Vorkommen in Meta/Fließtext * 1)“ (`R-KR\scoring-und-intent.md:12-13`).
- **Ausgabe**: `## KEYWORD-ERGEBNIS` im Chat – 18-Zeilen-Tabelle (je Intent 1 Haupt- + 5 Nebenkeywords), Score-Anhang, Fremdmarken, Zielseiten-Vorschlag mit Status `geplant` (`KON:371-461`). Ohne Erhebungsdatum + Methodik-Vorbehalt „ungültig“ (`SK-KR:115-116`).
- **Zielseiten-Zuordnung**: Je Keyword genau eine Zielseite; Baum laut `ZEB` (`SK-KR:89-97`).
- **Gate**: **Freigabe-Gate** – „Erst nach explizitem OK die Landkarte ändern (`generated` aktualisieren, `verified` **nicht** setzen)“ (`SK-KR:99-104`).
- **Schreibt**: `KL` (= `E:\tegards\marketing\marketing-wissen\seo-geo\keyword-landkarte.md`, `PY:31`). Einziger Skill, der die Landkarte direkt schreibt.

### 1.2 Keyword-Landkarte
- Spalten `Keyword | Intent | Zielseite (genau eine) | Status`, **keine Datumsspalte** (`KL:25`, `KL:75`). 39 Zeilen: 16 `ist`, 2 `KONFLIKT`, 21 `geplant` (`KL:77-115`). Ist-Intents „Hypothese aus Inhalt, nicht verifiziert“ (`KL:36-39`).
- Gelesen als Keyword-Gate von LP/KS/PS (siehe 1.4), als Kannibalisierungs-Referenz von allen Content-Skills (`KL:17-23`), von `A\verlinkungs-stratege.md:39` (Keyword-Anker) und `A\inventar-sync.md:11,67`.

### 1.3 Zielseiten-Entscheidung
- Plugin-Kopie `ZEB` (Stand 2026-09-08): Landingpage „NUR wenn … ≥ 3 sinnvolle Blog-Themen + ≥ 2 erwartbare Projekte/Jahr UND kommerzielles Kern-Keyword“ (`ZEB:11-13`); sonst Kategorie (`ZEB:14-15`); Produktseite nur Long-Tail (`ZEB:16-17`); Blog auch für kommerzielle/transaktionale Keywords mit Erklärbedarf (`ZEB:18-27`); „Je Keyword genau EINE Zielseite“ (`ZEB:28-29`).
- Rollen: `zielseite` vs. `shop-seite` (`ZEB:33-37`); Kategorie-Zielseite = Kaufbegriff + ≥3 Produkte (`ZEB:38-41`); Produkt-Zielseite = Modell/Maß/Variante oder Ein-Produkt-Kategorie (`ZEB:42-44`); Familien-Varianten nie Zielseite (`ZEB:45-48`).
- Instanz-Fassung desselben Baums: `WA:125-176` (inkl. Rollen, freigegeben 2026-09-06, `WA:159-176`). `keyword-recherche` liest die Plugin-Kopie, nicht `architektur_pfad`; KS/PS lesen Rollenkriterien aus `inhalte.architektur_pfad` (`SK-KS:42`, `SK-PS:42`).

### 1.4 Start eines Content-Skills, Gates
| Gate | LP | KS | PS | Blog | Projekt |
|---|---|---|---|---|---|
| `validate_projekt` | `SK-LP:34` | `SK-KS:38` | `SK-PS:38` | `SK-BL:39` | `SK-PB:38` |
| Keyword-Gate (STOPP) | ja, `SK-LP:38` | nur `zielseite`, `SK-KS:42` | nur `zielseite`, `SK-PS:42` | – | – |
| V-L1 (Intent≠Seitentyp ⇒ Frage) | `SK-LP:38` | `SK-KS:42` | `SK-PS:42` | – | – |
| Dossier-/Wissens-Gate | Dossier fehlt ⇒ **STOPP** (`SK-LP:38`) | fehlt ⇒ kein STOPP (`SK-KS:42`) | fehlt ⇒ kein STOPP (`SK-PS:42`) | – | – |
| Rollen-Gate | – | – | ja (b), `SK-PS:42` | – | – |
| Frische-Warnung 6 Mon. | `SK-LP:38` | `SK-KS:42` | `SK-PS:42` | nur Playbook, `SK-BL:49` | nur Playbook, `SK-PB:52` |
| Kannibalisierung (nur melden) | `SK-LP:38` | `SK-KS:42` | `SK-PS:42` | Vorentscheidung `SK-BL:53` | `SK-PB:57` |

### 1.5 SERP-Analyse
- **Agent** `serp-analyst` (sonnet; WebSearch, WebFetch, Read; `A\serp-analyst.md:1-6`). Läuft je Markt aus `projekt.maerkte` (Tegards: `AT, DE`, `PY:11`), Märkte „nie zu einem Ergebnis vermischt“ (`R-LP\hintergrund-analysen.md:37-40`).
- **Modus**: LP immer `voll` (`SK-LP:18`); KS/PS `voll|kurz` nach `ANALYSE-TIEFE: voll | kurz | keine` (`R-KS\intake-und-gates.md:34-40`; `SK-KS:19`); Blog/Projekt `kurz` (`SK-BL:17`, `SK-PB:16`); Positionierung `kurz` optional (`SK-PO:17`).
- **Ausgabe** `## SERP-ERGEBNIS` (`KON:85-168`): Pflicht Erhebungsdatum, Keyword|Markt, Methodik-Vorbehalt (`KON:91-95`). *kurz*: Top-5 (4 Spalten), 3 Bullets „Was die Konkurrenz zeigt“, „Empfehlung: eigener Blickwinkel“ (`KON:96-98`). *voll*: Top-10 mit 9 Spalten `# | URL | Typ | Intent | Tiefe | Struktur | Trust | UX | Rankinggrund (Hypothese)`, SERP-DNA ≤10 Bullets, „Mindestanforderungen für SERP-Parität“ (`KON:99-101`, `KON:150-167`).
- **Nicht erhoben**: Title, H1/H2-Liste, Featured Snippet, PAA, AI Overview, Wortzahl kommen im Agenten nicht vor; nur „Intent“ als Spalte (Grep-Befund Unteragent über `A\serp-analyst.md`, Z. 107, 132).
- **Ablage**: keine. Der Agent schreibt nie (`A\serp-analyst.md:13,144-145`); Ergebnis lebt nur im Chat bzw. Kommentar-Layer des Entwurfs.
- **Wiederverwendung**: verboten – „Keine SERP-Daten aus Altbeständen — jeder Durchgang erhebt frisch“ (`SK-LP:78`, `SK-KS:73`, `SK-PS:73`; `R-LP\hintergrund-analysen.md:50-54`). Einzige Ausnahme: **`SERP-VORBILD`** = Text einer vorhandenen Wiki-SERP-Analyse als Struktur-/Tiefe-Vorbild (`R-LP\hintergrund-analysen.md:49`; `R-KS\intake-und-gates.md:130`; `R-PS\intake-und-gates.md:147`; Agent `A\serp-analyst.md:47`). Blog/Projekt übergeben kein SERP-VORBILD (`SK-BL:17`, `SK-PB:16`).
- **Seitentyp-Befund**: KS „mindestens 6 der Top-10 … keine Kategorie-/Listing-Seiten“ ⇒ Approver-Entscheid (`R-KS\intake-und-gates.md:143-147`); PS nur qualitativ (`R-PS\intake-und-gates.md:156-157`).
- **Re-Run**: Hauptkeyword verschoben ⇒ alle SERP- und Wettbewerbsläufe neu (`SK-LP:40`, `SK-KS:27`, `SK-PS:27`).

### 1.6 Wettbewerbsanalyse
- **Agent** `wettbewerbs-analyst` (sonnet): LP immer, nach allen SERP-Läufen (`SK-LP:19`); KS/PS nur `voll` (`SK-KS:26`, `SK-PS:26`); Blog/Projekt nie.
- URLs: Top-2–3 organisch über alle Märkte, keine Marktplätze/Baumärkte, Betreiber-Dedupe (V-L5), <2 wird ausgewiesen (V-K3) (`R-LP\hintergrund-analysen.md:70-81`). FOKUS: Rankinggrund, tragende Value Props, Kaufpsychologie-Trigger (`R-LP\hintergrund-analysen.md:64`).
- Liest vorhandene Wettbewerber-Dossiers aus `WISSEN-AUSZUG` und ergänzt; übernommene Angaben behalten `erhoben_am` (`A\wettbewerbs-analyst.md:42-49`).
- **Ausgabe** `## WETTBEWERBS-DOSSIER`: je URL 6 Zeilen (Content-Typ, Struktur, Trust, Conversion mit `[extern:] (Fundstelle:)`, Rankinggrund-Hypothese, Schwächen/Lücken), „Muster“ ≤7 Bullets, „Gegenstrategie“ (`KON:170-218`).
- **Persistenz**: nur als Wettbewerbs-Eingangspaket nach `<wiki>/eingang/…_webseite_…` nach Gate 3 (`R-QS\wissen-laden.md:85-95`; `R-LP\pruefung-und-ablage.md:86-95`; `SK-LP:62`).

### 1.7 Analyse / Content-Gap
- LP Schritt 5: aus allen SERP-Läufen + Dossier Markt-Abgleich, Pflichtthemen = „Fragen, die ALLE Top-Treffer beantworten“, Gap-Liste High/Medium/Low (`R-LP\content-gap-und-personas.md:11-43`).
- KS/PS Schritt 6: „Ranking-optimale Variante aus SERP (+ Dossier) ableiten, dann gegen eigene Quellen abgleichen“ (`R-KS\analyse.md:9-10`); Top-Produkte aus `## SORTIMENTS-ERGEBNIS` (`R-KS\analyse.md:15-17`); Bundles (`R-PS\analyse.md:15-26`). Sortiment-Scan (`A\sortiment-scan.md`, haiku, nie Preise) nur KS/PS (`SK-KS:18`, `SK-PS:18`).

### 1.8 Positionierung / Personas / USP-Matrix
- **Weiche B9** (`BST:138-146`): `weiche_pruefen projekt.yaml <linie>`; nur `WEICHE: AKTIV` zählt; aktiv ⇒ freigegebene Value Props gesetzt, Personas/Message Map/Einwände Vorgabe, `persona-anwalt` vor Lektor. Ausgewertet in `SK-LP:46`, `SK-KS:48`, `SK-PS:48`, `SK-BL:46`, `SK-PB:48`. Da keine Positionierungsdatei existiert (1.0), ist die Weiche in Tegards derzeit nicht aktivierbar (Schluss aus Dateibestand).
- Ohne Weiche: Personas aus Wiki „AUSGEWÄHLT“, „keine neuen Personas erfinden“ (`R-LP\content-gap-und-personas.md:51-56`); Message Map `Persona | Hauptversprechen | 3 Nutzenargumente | Proof-Points | CTA` (`R-LP\content-gap-und-personas.md:64-65`).
- **USP-Matrix** (nur LP, Schritt 7): Quellen SERP-DNA, Content-Gaps, Dossier, Linienseite („USPs vs Marktstandard“, „Trust-Faktenliste“), `markenversprechen-usps.md`; Einordnung Marktstandard/teilweise/Opportunity/USP (`R-LP\usp-matrix.md:13-23`); Tabelle 2 = Modul 8 Vergleich (`R-LP\usp-matrix.md:30-34`).
- **GEO-Block** (nur LP, Schritt 8): Eingaben SERP-DNA, Gaps, USP-Matrix, Message Map ⇒ 3–5 `[GEO-SNIPPET]`, Entitäten-Cloud 10 Begriffe, SGE-Snippet ≤300 Zeichen = Modul 3 (`R-LP\geo-block.md:9-31`).

### 1.9 Seitenkonzept + ZWISCHENFREIGABE + Value-Prop-Gate
- LP Schritt 9: Konzept „BEVOR der Volltext entsteht“, Value-Prop-Gate ist „Pflichtteil dieser ZWISCHENFREIGABE“; „Ohne Freigabe entsteht **kein** Volltext“ (`SK-LP:52`). Inhalt: Intention aus Landkarte + allen SERP-Läufen, Modul-Belegung je Modul, Konditionale, Meta, Schema-Felder, **SERP-Paritäts-Vorschau je Mindestanforderung** (`R-LP\seitenkonzept.md:14-64`).
- KS/PS Schritt 7: dito + Referenz-Abgleich gegen `RS` (`SK-KS:50-51`, `SK-PS:50-51`; `R-KS\konzept.md:11-18`; `R-PS\konzept.md:11-29`).
- Blog/Projekt: **keine** Zwischenfreigabe; nur Value-Prop-Gate (`SK-BL:58`, `SK-PB:59`); Blog zusätzlich VORENTSCHEIDUNG Integration vs. neuer Artikel (`SK-BL:53`).
- Value-Prop-Gate = Baustein B3, Tabelle `| # | Value Proposition | Herkunft | Einschätzung | Empfehlung (rein/raus) |`, „Ohne diese Abstimmung entsteht kein Volltext.“ (`BST:79-87`).

### 1.10 Volltext
- LP: Conversion Pack + Volltext, 14 Module, 10 FAQ (`SK-LP:54`; `R-LP\conversion-pack-und-volltext.md:13-33`); V-K8 Abgleich REIN/RAUS (`R-LP\conversion-pack-und-volltext.md:81-82`).
- KS/PS: 12 Module (`SK-KS:53`, `SK-PS:53`); PS Familienmodus mit `{SLOT}` (`R-PS\volltext-und-familie.md:24-26`).
- Blog: `T\blog-ratgeber.md` / `T\blog-anleitung.md` (`SK-BL:60`); Projekt: `T\projekt-beitrag.md` 13 Module + JSON-LD-Anlage (`SK-PB:61`).

### 1.11 Prüfkette
Reihenfolge: `verlinkungs-stratege` (LP Schritt 11, KS/PS 9; Blog/Projekt bereits beim Start, `SK-BL:48`, `SK-PB:46`) → `persona-anwalt` nur bei aktiver Weiche → `redaktions-lektor` max. 2 Runden → `zeichen_zaehlen` + `geo-validator` „immer zuletzt“, max. 2 Runden, dann Eskalation → Checkliste (19/22/21/16 Zeilen) (`SK-LP:56-60`, `SK-KS:55-59`, `SK-PS:55-59`, `SK-BL:62-64`, `SK-PB:63-65`). Nachkorrektur-Regel: jede Änderung an Zahlen/Fakten/Struktur/Meta/Schema ⇒ erneuter Prüferlauf (`SK-LP:60`).

### 1.12 Schema / JSON-LD / RankMath / WooCommerce
Als Anlage zum Entwurf, Einfügen durch Webmaster per Copy-Paste (`T\schema-org\landingpage-jsonld.md:12`; `T\rankmath\meta-felder.md:8-10`). Details Abschnitt 7.

### 1.13 Ablage und Inventar-Update
- Ablage: `E:\tegards\marketing\content\<typ>\<slug>\entwurf.md` + `webdesign.docx` (Launcher `export_webdesign_docx`) + `medien.md` (`PY:33`; `T\content-ablage.md:19-29`; `SK-LP:62`). Inventar-/Landkarten-Update nur als Vorschlag, „Ungeschrieben ohne Freigabe“ (`SK-LP:62`).
- Nach „publiziert“ + URL: Gate 3 (Inventar `E:\tegards\marketing\marketing-wissen\content-inventar\*.md`) + Freigabe-Gate (Landkarte `geplant`→`ist`), gebatcht; `verified` nie setzen; `validate_frontmatter` PASS, dann Commit (`SK-LP:64`, `SK-KS:63`, `SK-PS:63` nur `zielseite`, `SK-BL:68-74`, `SK-PB:69-74`).
- `inventar-sync` liefert bei jedem Start den Sitemap-Diff (5 Inventardateien) und Vorschläge `geplant → ist`; schreibt nie (`A\inventar-sync.md:12-13,53-84,130-133`). Sitemap-Zuordnung RankMath: `CO\references\adapter\rankmath\sitemaps.md:7-18`.
- SessionStart-Hook meldet Entwürfe ≥7 Tage ohne Inventar-Eintrag (`CO\README.md:84`; `CO\hooks\hooks.json:1-3`; `CO\tools\hook_start.py:58-59`).

---

## 2. Elemente: Zweck – wer schreibt – wer liest

„Liest“ = lesende Stellen in `E:\commerce-os` und Live-Dateien in `E:\tegards`. Treffer in `E:\tegards\marketing\.superpowers\`, `…\marketing\docs\`, `E:\tegards\knowledge\.pakete\`, `.journal\`, `.zustand\`, `register\identitaeten.json` sind reine historische bzw. Register-Einträge (Pfad + Hash) und **keine Leselogik**; sie sind nur gezählt (Anzahlen im Unteragenten-Grep: z. B. `serp-analyst` 2224 Zeilen in `.superpowers`, 155 in `docs`).

### 2.1 Skills (alle von Mensch/Approver gestartet; kein Skill ruft einen anderen Skill auf)
| Skill | Zweck | schreibt (nach Gate) | ruft Agenten | Kernbeleg |
|---|---|---|---|---|
| keyword-recherche | Keywords je Intent, Zielseite, Landkarte | `KL` | inventar-sync | `SK-KR:8-15,99-104` |
| positionierung | Positionierung je Linie | `…\positionierung\<linie>.md` | persona-anwalt, (serp-analyst kurz, wettbewerbs-analyst) | `SK-PO:9,36-37` |
| landingpage | Produkt-Landingpage | Entwurf; Inventar/Landkarte/Wettbewerbs-Eingangspaket nach Freigabe | inventar-sync, serp-analyst voll, wettbewerbs-analyst, verlinkungs-stratege, persona-anwalt, redaktions-lektor, geo-validator | `SK-LP:17-23` |
| kategorieseite | Kategorie als Zielseite/Shop-Seite | dito | + sortiment-scan | `SK-KS:17-26` |
| produktseite | Produkt/Familie | dito (Landkarte nur `zielseite`) | + sortiment-scan | `SK-PS:17-26` |
| blog-beitrag | Ratgeber/Anleitung | dito | inventar-sync, serp-analyst kurz, verlinkungs-stratege, persona-anwalt, redaktions-lektor, geo-validator | `SK-BL:16-23` |
| projekt-beitrag | Kundenprojekt | dito | wie Blog | `SK-PB:15-22` |

### 2.2 Agenten (schreiben alle **nie** Dateien; „Verhaltensregel, keine technische Sperre“, z. B. `A\serp-analyst.md:13`)
| Agent | Modell | Ausgabe (KON) | Liest | Aufgerufen von |
|---|---|---|---|---|
| serp-analyst | sonnet | SERP-ERGEBNIS `KON:85-168` | nur Kontrakt, `projektkonstanten.md`, WISSEN-AUSZUG, SERP-VORBILD-Text | `SK-LP:18`, `SK-KS:19`, `SK-PS:19`, `SK-BL:17`, `SK-PB:16`, `SK-PO:17`; Templates `T\landingpage.md:74,298,385,467`, `T\kategorieseite.md:92,313,363`, `T\produktseite.md:121,394,448`, `T\rankmath\meta-felder.md:19` |
| wettbewerbs-analyst | sonnet | WETTBEWERBS-DOSSIER `KON:170-218` | WISSEN-AUSZUG (Dossiers) | `SK-LP:19`, `SK-KS:20`, `SK-PS:20`, `SK-PO:18` |
| geo-validator | sonnet | GEO-PRUEFBERICHT `KON:321-369` | `inhalte.playbook_pfad`, `no_gos`, `snippet_limits`, Templates (`A\geo-validator.md:33-40`) | alle 5 Content-Skills |
| verlinkungs-stratege | sonnet | LINK-PLAN `KON:257-296` | `VS`, Inventar, `WA` §2, `KL` (`A\verlinkungs-stratege.md:35-41`) | alle 5 Content-Skills |
| inventar-sync | haiku | INVENTAR-SYNC-ERGEBNIS `KON:28-83` | Sitemap, Inventar, Entwürfe, `KL` | alle Content-Skills + keyword-recherche |
| sortiment-scan | haiku | SORTIMENTS-ERGEBNIS `KON:220-255` | Live-Shopseite | KS, PS |
| persona-anwalt | sonnet | PERSONA-BEFUND `KON:511-551` | `positionierung_pfad` (`A\persona-anwalt.md:39`) | positionierung; Content-Skills nur bei Weiche |
| redaktions-lektor | sonnet | STIL-PRUEFBERICHT `KON:298-319` | `stil_pfad`, Instanz-CLAUDE.md (`A\redaktions-lektor.md:55-65`) | alle 5 Content-Skills |
Kein Agent wird aus Hook, `os.json` oder einem Command gerufen; `commands/` existiert nicht (Unteragent-Glob).

### 2.3 Gemeinsame References
| Datei | Zweck | gelesen von |
|---|---|---|
| `ZEB` | Zielseiten-Baum, Rollen | `SK-KR:59-60,89-90`, `SK-BL:53` |
| `R-QS\bausteine-content-skills.md` | B1 Grounding, B2 Briefing, B3 Value-Prop-Gate, B5/B6 Platzhalter, B7 Ablage, B8 SERP-first, B9 Weiche (B4 fehlt in der Nummerierung) | `SK-LP:36`, `SK-KS:40`, `SK-PS:40`, `SK-BL:45,55`, `SK-PB:42,54,59`; Templates (Grounding-Kopf) |
| `R-QS\frische-und-wiederverwendung.md` | 6-Monats-Warnung, Wiederverwendung nur INVENTAR-SYNC (`:7-23`) | `SK-LP:40`, `SK-KS:44`, `SK-PS:44`, `SK-BL:45`, `SK-PB:42,52`, `SK-KR:54`, `SK-PO:30` |
| `R-QS\wissen-laden.md` | Ladevertrag Wiki, WISSEN-AUSZUG ≤16 000 Bytes, Eingangspaket | alle 7 Skills (z. B. `SK-LP:38`, `SK-KR:68`) |
| `R-QS\referenzseiten-methode.md` | Struktur-Benchmark, 8+8 Abgleichsfragen (`:102-135`), Refresh 6 Monate (`:89-92`) | nur `SK-KS:48`, `SK-PS:48` |
| `R-QS\projektkonstanten.md` | alle `inhalte.*`-Standards (`:38-52`); **kein Feld für SERP-Analysen** | alle Skills, alle Agenten |
| `KON` | alle Ausgabekontrakte | alle Skills und Agenten (`KONTRAKT-PFAD`) |

Skill-eigene References (LP 10, KS 8, PS 8, KR 3, PO 3, Blog 5, Projekt 5) werden ausschließlich vom jeweiligen SKILL.md mit „Vor … lesen“ geladen (Fundstellen je Datei: `CO\docs\regeln\referenztabellen.md`, generiert von `CO\tools\skill_struktur.py`). In `E:\tegards` liest keine Live-Datei diese References inhaltlich.

### 2.4 Templates
| Template | Module/Checkliste | befüllt von | geprüft von |
|---|---|---|---|
| `T\landingpage.md` | 14 / 19 | landingpage (`SK-LP:50,52,54,60`) | geo-validator (`A\geo-validator.md:135`) |
| `T\kategorieseite.md` | 12 / 22 | kategorieseite (`SK-KS:50,53,59`) | geo-validator |
| `T\produktseite.md` | 12 / 21 | produktseite (`SK-PS:50,53,59`) | geo-validator |
| `T\blog-ratgeber.md`, `T\blog-anleitung.md` | 12 bzw. 14 / 16 | blog-beitrag (`SK-BL:55,60`) | geo-validator |
| `T\projekt-beitrag.md` | 13 / 16 | projekt-beitrag (`SK-PB:55,61,65`) | geo-validator |
| `T\content-ablage.md`, `T\medien.md` | Ablageformat | alle 5 Content-Skills (z. B. `SK-LP:62`) | `export_webdesign_docx` |
| `T\positionierung.md` | Positionierungsdatei | positionierung (`SK-PO:37`) | persona-anwalt, Weiche B9 |
| `T\schema-org\*-jsonld.md` (4) | JSON-LD-Bausteine | LP/KS/Blog/Projekt | geo-validator Kriterium 7 |
| `T\rankmath\meta-felder.md`, `T\woocommerce\felder.md`, `T\woocommerce\produkt-schema-kontrolle.md` | Stack-Adapter | KS/PS/alle (über `templates/<stack.*>/…`) | geo-validator (PS „inkl. Schema-Kontrollliste“, `SK-PS:23`) |
| `T\wpbakery\README.md` | „heute leer bis auf diese Datei“, Füllung „folgt in Etappe M5/M6“ (`:7`) | – | – |
Alle Templates tragen „Stand: 2026-10-03, Nächste Prüfung: 2027-04-03“ (Z. 1–2), `T\content-ablage.md` 2026-10-28, `T\positionierung.md` ohne Stand.

### 2.5 Gates
| Gate | definiert | Wirkung |
|---|---|---|
| Gate 1 Publikation | `CO\docs\specs\commerce-os-design.md:388` | nie publizieren (`SK-LP:68`) |
| Gate 2 Methodik | `CO\CLAUDE.md:74-76` | Regeländerungen nur mit Approver + Versionssprung |
| Gate 3 Wissen/Inventar | `CO\CLAUDE.md:36`; `R-QS\wissen-laden.md:82` | schreiben nur nach OK |
| Freigabe-Gate | `SK-KR:99-104` | Landkarte nur nach OK |
| Keyword-Gate | `SK-LP:38`, `SK-KS:42`, `SK-PS:42`; Details `R-LP\voraussetzungen-und-gates.md:57-73` | STOPP + `/keyword-recherche` |
| Wissens-/Dossier-Gate | `SK-KS:42`, `SK-PS:42` (kein STOPP); `SK-LP:38` (STOPP) | |
| ZWISCHENFREIGABE | `SK-LP:52`, `SK-KS:50`, `SK-PS:50`; Regel `CO\docs\regeln\skill-aufteilung.md:16` | kein Volltext ohne Freigabe |
| Value-Prop-Gate (B3) | `BST:79-87` | aufgerufen `SK-LP:52`, `SK-KS:51`, `SK-PS:51`, `SK-BL:58`, `SK-PB:59` |
| Gate „Value-Props freigeben“ | `SK-PO:36` | Positionierungsdatei nur nach OK |

### 2.6 Invarianten (`INV\`)
Je Skill eine YAML mit maschinenlesbaren Ankern (Schritte, Gates, Agentenparameter, Limits, Verbote); geprüft von `CO\tests\test_invarianten.py` gegen Alt-Skill und `SKILL.md` (`INV\README.md:11-20`); Gate-Wortlaut darf nur im Schritttext stehen (`INV\README.md:149-154`). SERP-relevant: „Keine SERP-Liste aus Altmaterial“ / „Mindestanforderungen für SERP-Parität“ (`INV\landingpage.yaml:87-95`), „Keine SERP-Altbestände“ (`INV\kategorieseite.yaml:200`), Keyword-Kontrakt mit Erhebungsdatum (`INV\keyword-recherche.yaml:110-127`). Gelesen nur von Tests (`CO\tests\test_invarianten*.py`, `test_skilltexte_umbau.py`, `test_templates.py:55-57`, `test_testmodus.py:212-213`); kein Skill/Agent liest sie zur Laufzeit. Kennungen V-L/V-K/V-P/L-K stammen aus Praxistest-Triage (`E:\tegards\marketing\docs\berichte\gate2-triage.md:43-56,102-112`).

### 2.7 seo-geo-Dateien der Instanz
| Datei | Zweck | schreibt | liest |
|---|---|---|---|
| `PB` (310 Z.) | „**die** SEO/GEO-Strategie-Referenz aller Skills und Subagents“ (`PB:16-17`); 9 Grundsätze | Mensch nach 4-Schritt-Prozess (`PB:293-303`) | `A\geo-validator.md:34,54,156,202`; Frische-Prüfung `SK-BL:49`, `SK-PB:52`, Gates LP/KS/PS; `T\produktseite.md:90`; `R-KS\aufbau.md:168`. **Nicht** von keyword-recherche/positionierung |
| `KL` (162 Z.) | Keyword → genau eine Zielseite | nur keyword-recherche nach Freigabe-Gate; andere nur Vorschlag `geplant→ist` | alle 7 Skills (`CO\os.json:48-84`), `A\inventar-sync.md:11,67`, `A\verlinkungs-stratege.md:39,318` |
| `WA` (198 Z.) | Ist-Zustand, Entscheidungsbaum §2, Bewertung | Mensch (generated 2026-09-06) | `A\verlinkungs-stratege.md:38`, KS/PS (Rollen), Blog-Vorentscheidung (`R-BL\zweig-und-vorentscheidung.md:41`) |
| `VS` (225 Z.) | Link-Regeln §1–§8 | Mensch | `A\verlinkungs-stratege.md:36-41` („Regeln IMMER frisch lesen“, `:64-73`), `T\produktseite.md:32,325,361` |
| `RS` (496 Z.) | „Struktur-Benchmark, kein Text-Vorbild“ (`RS:13`), nur Kategorie/Produkt | Mensch nach Methode | nur KS/PS (`SK-KS:48`, `SK-PS:48`; `R-KS\konzept.md:18`; `R-PS\konzept.md:25`) |
| `OG` (145 Z.) | Off-Page-GEO-Strategie | Mensch | **niemand**: kein Treffer in `E:\commerce-os`, kein Pfadfeld in `PY` |
| `KI` (87 Z.) | KI-Sichtbarkeits-Log | soll „laufend durch `/seo-audit` Modul (d)“ (`KI:59-61`) – Skill existiert nicht | **niemand** (kein Treffer in `E:\commerce-os`) |

### 2.8 Nachbarordner in `E:\tegards\marketing\marketing-wissen\` (Inventar)
- `content-inventar\blogartikel.md` (32 Z.): 4 Blogartikel per Sitemap-Crawl mit Keyword-/Persona-Hypothese, verified 2026-08-16.
- `content-inventar\kategorieseiten.md` (61 Z.): 16 Kategorieseiten, dito.
- `content-inventar\landingpages.md` (36 Z.): 2 Landingpages, dito.
- `content-inventar\produktseiten.md` (746 Z.): 700 Produktseiten mit Kategorie-Heuristik aus Slug.
- `content-inventar\projekte.md` (35 Z.): 6 Projektseiten mit Ort.
- `redaktion\redaktionsstil.md` (185 Z.): 4 Stilprofile, Prüfgrundlage des redaktions-lektor; `status: draft`, kein `verified` (Unteragent, Z. 1–40 gelesen).
- `positionierung\`, `produktlinien\`, `sortiment\`, `unternehmen\`, `zielgruppen\`, `wettbewerber\serp-analysen\`, `seo-geo\`: jeweils nur `.gitkeep` (Wissen liegt im Wiki `E:\tegards\knowledge\wiki\…`, `PY:28,38-41`).

### 2.9 SERP-Analysen im Bestand
- **Genau eine** Live-Analyse: `SERP-GSW` (145 Z.). Weitere Kopien nur in `E:\tegards\knowledge\.pakete\2026-10-27-umzug-wettbewerber\…` und `E:\tegards\marketing\.superpowers\sdd\2026-10-18-umbau-wissensarchitektur\pakete-eingaben\…`. `E:\tegards\marketing\marketing-wissen\wettbewerber\serp-analysen\` leer. `E:\marketing-os` enthält nur `README.md`, kein SERP-Treffer; `E:\werkzeuge` existiert nicht.
- **Aufbau**: Frontmatter `id`, `type: thema`, `status: stable`, `generated: claude/claude-sonnet-5 2026-08-16T19:11:37Z`, `verified: human:mm 2026-08-16T20:55:32Z`, `produktlinien: ["glasschiebewaende-deluxe"]`, `herkunft_alt: /wissensbasis/seo-geo/seo-geo-playbook.md` (`SERP-GSW:1-16`); Erhebungsdatum + „SERPs sind flüchtig“ (`SERP-GSW:18-24`); Methodik-Vorbehalt (`:26-34`); Top-10 mit genau den 9 Kontrakt-Spalten (`:43-54`); SERP-DNA 10 Bullets (`:60-119`); Mindestanforderungen 5 Punkte (`:121-144`). Format = Kontrakt Modus voll (`KON:150-167`).
- **Wer schrieb**: generated-Feld nennt nur das Modell; Format entspricht `serp-analyst` Modus voll (Agent schreibt nie selbst ⇒ Ablage durch Menschen/Session). Umzug ins Wiki per Paket 2026-10-27 (`E:\tegards\knowledge\log.md:32`).
- **Wer liest**: als Beleg zitiert in `E:\tegards\knowledge\wiki\wettbewerber\foravida.md:136`, `luxbach.md:43`, `terrawin.md:144`, `tuinmaximaal.md:46`. Im Ablauf nur als `SERP-VORBILD`-Text (1.5). Sie enthält noch den Altpfad `[intern: /wissensbasis/seo-geo/seo-geo-playbook.md]` (`SERP-GSW:133`).

### 2.10 TG-Design-Seitenvorlagen
- Ordner `E:\TG Design\ausgelagert\seitenvorlagen` existiert **nicht**; es gibt die Datei `SV` (100 Z., Dateidatum 2026-11-08, kein Stand-Kopf). Nachbarn: `inhaltliche-grundsaetze.md` (24 Z., „ausgelagert am 2026-11-08“, „Übergabe an das Content-Tool“, Z. 1–3), `sortiment.md` (48 Z.), `wordpress.md` (75 Z.) – letztere zwei nicht gelesen.
- Inhalt: Reihenfolge der Designsystem-Bausteine je Seitenart; „Theme“ vs. „WPBakery“ (`SV:3`). Seitenarten: Blogartikel Anleitung/Ratgeber (`SV:5-26`), Landingpage Produkt (`SV:28-45`), **Produkt-Landingpage einzelnes Produkt/Modellreihe** (`SV:47-63`, „Muster für neue Produktwelten wie Lamellendächer, Carports“), Projekt (`SV:65-76`), Kategorieseite WooCommerce (`SV:78-85`), Produktbeschreibung WooCommerce (`SV:87-93`), Marketing (`SV:95-100`).
- **Bezug zu commerce-os: keiner im Text.** Grep über `E:\TG Design` nach `commerce-os|landingpage.md|kategorieseite.md`: kein Treffer. `SV` wird gelesen von `inhaltliche-grundsaetze.md:7` und gelistet in `E:\TG Design\designsystem\ds\filelist.txt:80`. Inhaltliche Überschneidungen (Fakt, Vergleich der Texte):

| Seitenart | SV (Layout-Bausteine) | commerce-os-Template (Textmodule) |
|---|---|---|
| Blog | `TipBox` „💡 Das Wichtigste vorab“ (`SV:10`); `Faq` nur „bei Ratgebern“ (`SV:24`) | Answer-First Modul 3 (`T\blog-ratgeber.md:98-123`); FAQ Pflicht auch bei Anleitung (`T\blog-anleitung.md:260-279`) |
| Landingpage | 14 Bausteine inkl. Video, Farbvarianten, `FeatureTable` „Deluxe vs. Marktstandard“, `Faq --2col` (`SV:32-45`) | 14 Module inkl. Vergleichstabelle Modul 8, genau 10 FAQ (`T\landingpage.md:270,348`) |
| Kategorie | `CategoryIntro` 2–3 Sätze; unter Raster Kaufberatung 300–600 Wörter (`SV:83-85`) | Intro 50–100 Wörter; SEO-Block 200–300+ (`T\kategorieseite.md:113-130,215-225`) |
| Produkt | Kurzbeschreibung + Checklist; Tab: ProductDescription → SpecTable → TipBox → Anleitungs-Link (`SV:91-93`) | 12 Module, Kurzbeschreibung ≤~50 Wörter, Langbeschreibung 250–600 (`T\produktseite.md:138-240`) |
| Projekt | `ProjectFacts` „Auf einen Blick“, Problem/Lösung/Challenge, Faq, Besichtigungsformular (`SV:69-76`) | 13 Module inkl. Technische Matrix, Storytelling, DIY-Proof, GEO-Snippet + FAQ (`T\projekt-beitrag.md:30-331`) |
| Produkt-Landingpage | eigene Seitenart (`SV:47-63`) | **kein** Gegenstück in commerce-os |

---

## 3. Wie das Seitenschema je Seitentyp entsteht

Allgemein: Feste Modulfolge im Template („verbindliche 14-Modul-Folge“, `T\landingpage.md:12`; „12-Modul-Folge“ `T\kategorieseite.md:12`, `T\produktseite.md:12`). Grounding-Kopf in allen Templates: SERP/Wettbewerb liefern die ranking-optimale Variante, Quellen nur auf Widersprüche abgleichen (`R-KS\rolle-und-grundhaltung.md:16-18`; `R-LP\rolle-und-grundhaltung.md:21-24`). Spannung (Fakt): B8 verlangt „optimale Struktur“ aus Top-Rankern (`BST:131-132`), das Gerüst ist aber fest.

### 3.1 Landingpage
- **Fest**: 14 Module H1 → Hero-Bild → Answer-First → Hero 3 VP + Trust + CTA → Problem/Lösung je Persona → USPs → Deep-Dive → Vergleich → Social Proof → FAQ (genau 10) → CTA → Layout-Anker → Meta → JSON-LD (`T\landingpage.md:62-475`). Keine Länge aus der SERP-Spalte „Tiefe“ abgeleitet.
- **Aus SERP/Wettbewerb**: Hauptkeyword „aus dem `serp-analyst`-Ergebnis der Produktlinie übernehmen“ (`T\landingpage.md:74-75`); Marktstandard-Spalte Modul 8 „aus SERP-Erwartung“ (`:280-281,289`); FAQ-Priorität 3 = PAA aus serp-analyst (`:385`); Fokus-Keyword (`:467`); Intention aus Landkarte + SERP (`R-LP\seitenkonzept.md:15-17`); SERP-DNA → USP-Matrix, GEO-Block (`R-LP\usp-matrix.md:13`; `R-LP\geo-block.md:9`); Mindestanforderungen → Paritäts-Vorschau im Konzept und Paritäts-Abgleich in Prüfung (`R-LP\seitenkonzept.md:55-58`; `R-LP\pruefung-und-ablage.md:47-51`); Top-10-URLs → Wettbewerber-Auswahl.
- **Aus Positionierung/Personas/Dossier**: Modul 4 VP aus USP-Matrix bzw. `markenversprechen-usps.md` (`T\landingpage.md:158-163`); Modul 5 Pain „wörtlich oder sinngemäß aus den „Pains“-Abschnitten der Persona-Seiten“ (`:194,201-207`); FAQ-Priorität 1 Dossier „FAQ-Rohstoff“, 2 Personas (`:381-384`); Trust-Zeile aus „Trust-Faktenliste“ (`:163-165`). Wort „Positionierung“ kommt im Template nicht vor.
- **Konditional**: Modul 8 nur mit belegtem Marktstandard, Modul 9 nur mit Referenzprojekt (`R-LP\seitenkonzept.md:35-37`).

### 3.2 Kategorieseite
- **Fest**: 12 Module (H1, Intro 50–100 W. mit `[GEO-SNIPPET]`, Bild, Unterkategorien/Filter, Produktraster, SEO-Block 200–300+ W. mit 3 H3, Top-Produkte, Ratgeber-Links, FAQ 5–8, CTA, Meta, JSON-LD) (`T\kategorieseite.md:78-375`); Aufbauregeln + 15-Punkte-Baymard-Checkliste (`R-KS\aufbau.md:24-125`); Rollen-Tiefe `shop-seite`: SEO-Block optional ≤150 W., FAQ ≥3 (`R-KS\aufbau.md:185-198`).
- **Aus SERP**: H1/Meta-Keyword bei `zielseite` (`T\kategorieseite.md:91-93,362-363`); FAQ-Priorität 3 (`:313`); Gap-Liste Pflichtthemen (`R-KS\analyse.md:11-12`); Seitentyp-Befund ≥6/10; Paritäts-Abgleich nur `voll` (`R-KS\link-plan-und-pruefung.md:40-42`). Wettbewerbs-Dossier wird im Template nicht erwähnt.
- **Aus Sortiment/Landkarte/Referenzseiten**: Rolle aus Landkarte (`T\kategorieseite.md:42-47`); Modul 4 nur wenn Sortiment Unterkategorien/Filter hat (`:171-181`); Raster-Reihenfolge aus `## SORTIMENTS-ERGEBNIS` (`:199-200`); Referenz-Abgleich Checklistenzeile 17 (`:441`).
- **Personas**: H3 „Einsatz/Anwendungsfall je Persona“ (`:218-219`), FAQ-Priorität 2 (`:312-313`).

### 3.3 Produktseite
- **Fest**: 12 Module (Name/H1, Kurzbeschreibung ≤~50 W., Bild, Langbeschreibung 250–600 bzw. 120–250 W., Nutzen je Persona, `[ATTRIBUTE]`, Montage, Bundles 2–4, FAQ 3–5, CTA, Meta ≤149, Schema-Kontrolle) + Familien-Modus mit `{SLOT}`, Slot-Tabelle, Varianten-Matrix (`T\produktseite.md:109-539`). Regeln teils nur „[intern: Festlegung der Ursprungsinstanz]“ (`R-PS\aufbau.md:38,60,94,104,120`). Keine Baymard-Checkliste.
- **Aus SERP**: H1 (`T\produktseite.md:120-121`), FAQ-Priorität 3 (`:394`), Meta (`:447-448`); `shop-seite`: KEYWORD = Produktname (V-P3, `R-PS\intake-und-gates.md:144-146`).
- **Aus Sortiment**: Modus-Vorschlag (`T\produktseite.md:66-67`), Bundles aus Cross-Sells (`:358-359`), Slot-Quelle Shop-Attribut (`:510-512`).
- **Personas**: Modul 5 „Personas aus den Persona-Seiten der Linie“, `zielseite` ≥2 (`:262,266-267`).

### 3.4 Blog (Ratgeber / Anleitung)
- **Fest**: Ratgeber 12 Module, Anleitung 14 (5a Voraussetzungen, 5b Schritte, 5c Endkontrolle, Sicherheitshinweis wortgleich, Häufige Fehler) (`T\blog-ratgeber.md:44-316`; `T\blog-anleitung.md:47-345`). Struktur-Vorbild: Stilbibel + Live-Referenzen (`T\blog-ratgeber.md:18-28`).
- **Aus SERP (kurz)**: nur „Fokus-Keyword aus dem `serp-analyst`-Ergebnis übernehmen“ (`T\blog-ratgeber.md:314-315`); Vorentscheidung „eigener Intent laut `## SERP-ERGEBNIS`“ (`R-BL\zweig-und-vorentscheidung.md:27-44`); B8 allgemein.
- **Aus Interview/Personas**: Schritte „ausschließlich aus dem Interview, den Fotos oder internen Quellen“ (`SK-BL:81`); FAQ-Priorität Recherche/Interview, dann Personas (`T\blog-ratgeber.md:235-239`). Landkarte, Positionierung, Wettbewerb kommen im Template nicht vor.

### 3.5 Projekt-Beitrag
- **Fest**: 13 Module (H1 `<Produkt/Nutzen> für <Anwendungsfall> in <Ort>`, Titelbild 2:3, Answer-First, Technische Matrix mit Quelle-Spalte, Storytelling ≤200 W., Kundenzitat nur nach Ja, DIY-Proof, Bilder Vorher→Montage→Ergebnis, GEO-Snippet 3–5 Sätze + FAQ 3–5, 3 CTA-Varianten) (`T\projekt-beitrag.md:30-331`).
- **Aus SERP (kurz)**: lokales Haupt-Keyword „<Produkt> <Ort>“ (`SK-PB:45`), Fokus-Keyword (`T\projekt-beitrag.md:328-329`).
- **Aus Interview/Personas**: Ort „exakt wie im Interview“ (`:42`); Persona-Bezug in Modul 4 (`:108-112`); Zitat-Gate (`SK-PB:55`).

---

## 4. GEO / KI-Sichtbarkeit

### 4.1 geo-validator – vollständige Checkliste (`A\geo-validator.md:71-90`, wortgleich `KON:343-353`)
1 Answer-First-Block in den ersten 300 Zeichen · 2 Entitäten logisch verknüpft (Produkt, Norm, Ort) · 3 ≥1 belegte Zahl mit Quelle · 4 Zitat nur vom Approver oder von ihm bestimmt · 5 FAQ nach PAA-Logik · 6 Fakten maschinell extrahierbar · 7 Schema-JSON-LD vollständig/konsistent · 8 Snippet ≤155 (Limit `snippet_limits.description`, PS `description_produkt`) · 9 Title ≤ `snippet_limits.title` · 10 keine Preise · 11 kein No-Go-Verstoß.
- Skala nur ✅/❌ (`A\geo-validator.md:186`). Messkonvention Kriterium 1 je Seitentyp (`:120-144`); fehlender empfohlener Schema-Baustein kein ❌ (E9, `:146-150`). Liest Playbook-Abschnitte On-Page-GEO und Snippet-Längen (`:152-169`); Ausgabe-Abschnitt „Playbook-Abweichungen“ (`:182-194`).
- AI Overviews / LLM-Zitierung werden **nicht ausdrücklich** geprüft; nur description „KI-Zitierfähigkeit“ (`:3`).
- Ergänzende GEO-Vorgaben in Templates: Answer-First „für Google SGE, Bing Copilot und andere KI-Bots“ (`T\landingpage.md:104-106`); `WebPage` + `speakable` optional (`T\schema-org\landingpage-jsonld.md:199-222`); GEO-Passage 134–167 Wörter, Primärstudie „nicht unabhängig geprüft“ (`R-KS\aufbau.md:173-178`).

### 4.2 Playbook zu AI Overviews / LLM
- „Google AI Overviews nutzen weiterhin den normalen Googlebot-Index und bleiben aktiv“ (`PB:268-269`); Reddit-Anteil in AI Overviews 49,4 % (`PB:184-185`).
- GEO-Zitierfaktoren: Spec-Werte +26/+28/+25 % „in den geprüften Quellen wörtlich nicht auffindbar“ (`PB:141-143`); Handlung „~20–40 % Sichtbarkeitssteigerung“ (`PB:146-150`); Quellen arXiv (`PB:130,139`).
- On-Page-GEO §5: Answer-First, Entitäten, Schema-Typen, belegte Zahl, Expertenzitat, Quellen, PAA-FAQ (`PB:94-98`); E9 FAQPage „empfohlen, kein Pflichtbaustein“ (`PB:103-113`).
- Technik: Trainings-Bots blockieren, Such-Bots erlauben (`PB:242-248`); llms.txt „nicht empfohlen“ (`PB:272`). E-E-A-T als Wort fehlt im Playbook.

### 4.3 ki-sichtbarkeit-log
Spalten `Datum | Engine | Prompt | tegards zitiert? | wer stattdessen | Notiz` (`KI:63`); festes 10-Prompt-Set, Änderung nur über Playbook-Prozess (`KI:40-55`); **12 Einträge, alle 2026-08-23** (Perplexity 10× Nein, Copilot/AI Overviews „nicht messbar“) (`KI:65-76`); Führung „laufend durch `/seo-audit` Modul (d)“ (`KI:59-61`), kein Intervall, keine Folgemessung.

### 4.4 offpage-geo
Reine Strategie, operative Umsetzung „erst nach Phase 5“ (`OG:20-26`): Bewertungsmanagement (Plattformen „noch nicht mit Markus abgestimmt“, `OG:36-42`), Community r/Heimwerken (`OG:61-80`), YouTube (Kanal offen, `OG:100-106`), Brand-Mentions quartalsweise (`OG:110-117`), GSC-Backlink-Export quartalsweise (`OG:121-136`). Gelesen von keinem Skill/Agenten.

---

## 5. Frische

**Vorhandene Mechanismen (alle reaktiv, beim Skill-Start):**
1. Marketing-Dateien: „`verified.at` (sonst `generated.at`) … älter als 6 Monate“ ⇒ Warnung; `generated` jünger als `verified` ⇒ „erweitert, aber ungeprüft“ (`R-QS\frische-und-wiederverwendung.md:7-12`; angewandt `SK-LP:38`, `SK-KS:42`, `SK-PS:42`; Blog/Projekt nur Playbook `SK-BL:49`, `SK-PB:52`). Nur Warnung, kein Abbruch, kein Auffrischungsauftrag.
2. Wiki-Seiten: `verified_at` > 6 Monate ⇒ Frische-Warnung; Wettbewerber-Profil `profil.veraltet`; Beobachtungen altern nicht (`R-QS\wissen-laden.md:43-53`).
3. SERP: immer frisch erheben, nie wiederverwenden (1.5) – Frische durch Neuerhebung je Lauf, aber ohne Ablage.
4. References/Templates: Kopf „Nächste Prüfung“ = Stand + 6 Monate; liegt sie in der Vergangenheit ⇒ Frische-Warnung (`R-QS\kommentar-layer-und-platzhalter.md:96-104`). Stand 2026-11-16 ist keine überschritten.
5. Referenzseiten: Refresh-Pflicht 6 Monate (`R-QS\referenzseiten-methode.md:89-92`; `RS:21-22` „2027-03-06“).
6. Hook: Entwürfe ≥7 Tage ohne Inventar (`CO\README.md:84`); Wiki-Teil meldet Veraltungswarnungen zu `stuetzt_sich_auf` (`CO\README.md:85`).

**Nicht vorhanden:** Kein Mechanismus, der Playbook, Landkarte, Architektur, offpage-geo, KI-Log oder SERP-Analysen **aktiv** neu erhebt oder terminiert. Der im Playbook/KI-Log/OG genannte Pflegeweg `/seo-audit` (Module a, d, g; `PB:152-153,277-278`; `KI:59-61`; `OG:144-145`) **existiert nicht** (`E:\commerce-os\skills\` enthält nur die 7 Skills; Grep `seo-audit` in `E:\commerce-os` ohne Treffer). Gesucht: alle Skills, Agenten, References, Hook, `os.json`, `PY`, seo-geo-Dateien.

**Stände der Instanzdateien:**
| Datei | generated.at | verified.at | Prüfregel in der Datei |
|---|---|---|---|
| `PB` | 2026-10-10 | 2026-08-16 | „Nächste Prüfung im Rahmen von `/seo-audit` Modul (a)“ (`PB:152-153`); je Abschnitt „Geprüft am: 2026-08-16“ |
| `KL` | 2026-10-10 | 2026-08-16 | „bei jedem Content-Refresh aktualisiert“ (nur Anbieter-Auswahl Lamelle, `KL:141-144`) |
| `WA` | 2026-09-06 | 2026-08-16 | keine |
| `VS` | 2026-09-07 | 2026-08-16 | „Nächste Prüfung: 2027-02-16 (6 Monate)“ (`VS:224`) |
| `RS` | 2026-10-06 | – (draft) | 2027-03-06 (`RS:21-22`) |
| `OG` | 2026-09-07 | 2026-08-16 | `/seo-audit` Modul (g) (`OG:144-145`) |
| `KI` | 2026-08-23 | 2026-08-16 | keine |
| `SERP-GSW` | 2026-08-16 | 2026-08-16 | „muss bei Bedarf neu erhoben werden“ (`SERP-GSW:18-19`) |
Folge laut Regel 1: PB, KL, WA, VS, OG, KI melden heute „erweitert, aber ungeprüft“ (generated > verified). Ab 2027-02-16 überschreiten die `verified`-Daten 2026-08-16 die 6-Monats-Grenze.

---

## 6. Produktlinien

- **Linien in den Dateien**: Glasschiebewände Deluxe, Lamellendächer, Faltdach-Pergolen als drei gleichrangige Linien (`WA:191`); Landkarte: Ist-Zeilen GSW/Verglasungen/Profile/Montage/Werkzeuge, geplant-Zeilen nur Lamellendächer, Faltdach **keine Zeile** (`KL:77-115`); Architektur: nur GSW-Silo existiert, Lamelle/Faltdach „im gesamten Content-Inventar nicht auffindbar“ (`WA:30-54,102-112`); KI-Prompts 1/2/5/8 GSW, 3 Lamelle, 10 Faltdach (`KI:40-49`); Referenzseiten nur GSW-Wettbewerber dreku/durchdacht (`RS:72,198`); SERP-Analyse nur GSW (`SERP-GSW:9`). Liste der Linien nicht in `PY` (nur Wiki-Pfad `PY:28`).
- **Wo die Logik je Linie unterscheidet**: Positionierungsdatei je Linie (`T\positionierung.md:4`); Linienseite/Dossier + Persona-Seiten der Linie über Ladevertrag (`R-QS\wissen-laden.md:19-27`); linienspezifische Keyword-Seeds (Modellnamen, Dossier-Abschnitt `## Keyword-Modifikatoren`, `R-KR\suggest-serp-erhebung.md:94-109`); Content-Sperrvermerke/Garantien im Dossier (`T\landingpage.md:37-48`); `manufacturer`/`brand` laut Dossier (`T\schema-org\landingpage-jsonld.md:108-120`; `T\woocommerce\produkt-schema-kontrolle.md:43`); Pillar-Sonderregel Lamellendach (Pillar `/lamellendaecher/` entschieden 2026-10-10, Links auf Platzhalter statt Kategorie, `KL:44-54`).
- **Keine Linienlogik** in Templates, Agenten, schema-org, `VS` (Linien nur Ankerbeispiele `VS:25-26`), Playbook.

---

## 7. Strukturierte Daten

| Seitentyp | Typen (Pflicht / empfohlen / optional) | Verbote | wer füllt | Beleg |
|---|---|---|---|---|
| Landingpage | `Product` Pflicht (Produktlinie, keine SKU; name, description = Snippet wortgleich, image, brand, url); `FAQPage` empfohlen; `WebPage`+`speakable` optional; Org über projekt-jsonld | kein `offers`/`price`/`priceCurrency` | Skill befüllt, Webmaster fügt ein | `T\schema-org\landingpage-jsonld.md:58-106,199-238` |
| Kategorie | `CollectionPage` Pflicht mit `ItemList` (`position`,`url`,`name`) als `mainEntity`; `FAQPage` empfohlen; max. 2 Script-Blöcke | kein `offers`; nicht doppeln, wenn RankMath CollectionPage ausgibt | Skill; RankMath ggf. | `T\schema-org\kategorieseite-jsonld.md:39-45,83-141,193-209` |
| Produkt | **kein eigenes JSON-LD**: `Product` inkl. `offers` erzeugen WooCommerce + RankMath; Kontrollliste name/description/image/brand/sku/category; `FAQPage` optional 3–5; `HowTo` nur mit Anleitungsabschnitt | kein zweites Product-Schema | Skill/Redakteur prüft | `T\woocommerce\produkt-schema-kontrolle.md:11-26,35-54,58-124`; `SK-PS:67` |
| Blog | `Article` Pflicht (author/publisher = Organization), `HowTo` nur Anleitung optional (step 1:1 aus 5b), `FAQPage` empfohlen | keine Person erfinden, kein `estimatedCost`, kein LocalBusiness | Skill | `T\schema-org\blog-jsonld.md:51-217` |
| Projekt | `Article` Pflicht; `Review` nur nach Zitat-Ja; `FAQPage` empfohlen; `LocalBusiness` immer | keine Kundenadresse, kein erfundenes `reviewRating` | Skill | `T\schema-org\projekt-jsonld.md:20-212` |
- Für alle: kein `@graph`, separate Script-Blöcke; `BreadcrumbList` „nie selbst erzeugt“, macht das SEO-Plugin (`T\schema-org\blog-jsonld.md:29-30,213-214`; `T\rankmath\meta-felder.md:25`).
- **RankMath-Felder** (`T\rankmath\meta-felder.md:17-35`): SEO Title ≤ `snippet_limits.title` (60), Description ≤155 bzw. Produkt 149, Focus Keyword aus serp-analyst (`shop-seite` keins, `:19`), Schema-Eingabe, Robots nur HUMAN-CHECK; „je Schema-Typ genau eine führende Quelle“ (`:33-35`). Tegards-Limits `{title: 60, description: 155, description_produkt: 149}` (Unteragent `PY:25`).
- **WooCommerce-Felder** (`T\woocommerce\felder.md:16-34`): Produkt – Titel, Kurzbeschreibung ~50 W., Beschreibung/Tab, Attribut-Tabelle (Shop), Cross-Sells, Slug; Kategorie – Name, Beschreibung oben 50–100 W., Feld unter Raster 200–300+ W., Slug.
- Projektkonstanten: `projekt.marke`, `projekt.rechtsname`, `projekt.domain`, `kontakt_email`, `maerkte`, `unternehmensprofil.md` (`T\schema-org\projekt-jsonld.md:144-171`).

---

## 8. Widersprüche, Lücken, Verwaistes

**Verwaist / ohne Leser**
1. `OG` und `KI`: von keinem Skill/Agenten gelesen, kein Pfadfeld in `PY`, Pflegeweg `/seo-audit` existiert nicht (Abschnitt 5).
2. `SERP-GSW`: einzige SERP-Analyse; nur noch als SERP-VORBILD-Text und Beleg in 4 Wettbewerberseiten genutzt; keine Ablage neuer SERP-Läufe vorgesehen (`R-QS\projektkonstanten.md` ohne Feld); Ordner `marketing-wissen\wettbewerber\serp-analysen\` leer.
3. Positionierungsordner leer ⇒ Weiche B9 und `persona-anwalt` im Content-Lauf derzeit ohne Gegenstand.
4. Invarianten nur von Tests gelesen; `T\wpbakery\README.md` leer bis auf Hinweis.
5. `SV` (TG Design) ohne jeden Verweis aus commerce-os und umgekehrt; Seitenart „Produkt-Landingpage“ ohne Template.

**Widersprüche**
6. SERP-Modus Produktseite: `KON:87,89` nennt Produktseite bei Modus voll, Fence-Titel „für Landingpages, Kategorieseiten“ (`KON:137`); `A\serp-analyst.md:3` „kurz für Projekt/Blog“, aber KS/PS/Positionierung sind kurz-Consumer (`KON:88`).
7. Kriterium 8 fest „≤155“ im Namen, Limit aber parametrisch (`A\geo-validator.md:85-87`; `KON:350`); Playbook-Befund PT-13 (`PB:310`).
8. FAQ-Rich-Results: „seit 2023 nur Behörden/Gesundheit“ (`T\schema-org\landingpage-jsonld.md:129-130`) vs. „eingestellt seit 7. Mai 2026“ (`T\schema-org\kategorieseite-jsonld.md:175-177`; `R-KS\aufbau.md:152-160`).
9. Landingpage-FAQ „genau 10“ (`T\landingpage.md:348`; `R-LP\conversion-pack-und-volltext.md:32-33`) vs. Playbook E9 „Regel genau 10 Fragen gilt nicht als Schema-Regel“ (`PB:103-113`) vs. SERP-GSW Mindestanforderung „6–8 Fragen“ (`SERP-GSW:132`).
10. Keyword-Gate LP: Reference „empfiehlt … endet“ (`R-LP\voraussetzungen-und-gates.md:61-63`) vs. Skill „STOPP“ (`SK-LP:38`); LP Dossier fehlt = STOPP, KS/PS = kein STOPP.
11. Checklisten-Behauptung „Zeilen 1–11 identisch mit Landingpage“ (`T\kategorieseite.md:407-408`), Zeile 11 weicht ab (`T\landingpage.md:535` vs. `T\kategorieseite.md:435`).
12. Conversion Pack: Template „kein dediziertes Conversion-Pack-Dokument“ (`T\landingpage.md:416-418`) vs. Skill „Pack und Volltext nach … landingpage.md“ (`SK-LP:54`).
13. Wettbewerber-Seiten: „das Wiki enthält dafür noch keine Wettbewerber-Seite“ (`T\landingpage.md:286-287`) – Wiki hat foravida, luxbach, terrawin, tuinmaximaal u. a. (`E:\tegards\knowledge\wiki\wettbewerber\`).
14. Pillar-Fallback Lamelle: „nicht ersatzweise auf die Shop-Kategorie“ (`KL:52-54`) vs. `VS:29-31` Kategorie als Pillar-Ersatz.
15. Kategorie-Zielseiten mit 1 Produkt in `KL:93-94` vs. ≥3-Produkte-Regel `WA:164-167`.
16. `RS` `status: draft` ohne `verified` (`RS:5`) vs. „Auswahl freigegeben“ (`RS:23`).
17. `verified.at` 2026-08-16 bei PB/VS trotz späterer Freigaben (PB v1.1 „freigegeben human:mm 2026-10-10“, `PB:310`).
18. `T\produktseite.md:90` verweist für Snippet-Werte auf Playbook §9 – seit v1.1 in §5 (`PB:280-281,310`); `R-KS\aufbau.md:165-170` verweist für Answer-First-Messkonvention aufs Playbook – dort nicht enthalten (Unteragent `PB` §5).
19. Modusname `familie` (`T\woocommerce\produkt-schema-kontrolle.md:36`) vs. `produktfamilie` (`T\produktseite.md:59`).
20. `R-QS\kommentar-layer-und-platzhalter.md:93-94` „Eine Reference verweist auf keine weitere Reference“ – mehrere tun es (z. B. `R-QS\frische-und-wiederverwendung.md:14-16`).

**Veraltete Pfade/Stände**
21. Altpfad `/wissensbasis/…` in `SERP-GSW:15,133`, `E:\tegards\knowledge\wiki\produktlinien\lamellendaecher.md:23-24,461,478`; Ordner existiert nicht.
22. `E:\tegards\marketing\content\produktseite\zip-screens\entwurf.md:218` verweist auf nicht mehr existierende `templates/schema-org/produktseite-schema-kontrolle.md`; `…\content\kategorieseite\fixverglasung\entwurf.md:352` auf `references/kategorieseite-aufbau.md`.
23. Templates „Stand: 2026-10-03“, Git-Änderung 2026-10-30 (Unteragent `git log`, Commit 7064078).
24. `PB:54-55` „künftig durch den Skill `kategorieseite`, Phase 4“ – Skill existiert; `KL:38-39` Ist-Intents weiter Hypothese; `KI:20-25` „Phase 1“ vs. tatsächlich Phase 3.
25. Bau-Reste in neutralen Templates/Seeds (Montage, Konfigurator, „bauordnung“, „motor“) neben Seifen-Beispielen (`R-KR\suggest-serp-erhebung.md:85-92`; `T\projekt-beitrag.md:214,285`).

---

## 9. Dateiinventar (Zeilen laut `wc -l`)

**commerce-os – Skills**: `SK-BL` 81, `SK-KS` 73, `SK-KR` 116, `SK-LP` 78, `SK-PO` 46, `SK-PS` 73, `SK-PB` 80.
**References gemeinsam**: `ZEB` 56; `CO\references\adapter\rankmath\sitemaps.md` 33; `R-QS\` bausteine 162, delegationsmodus 26, frische 23, kommentar-layer 104, projekt-lesen 42, projektkonstanten 82, referenzseiten-methode 172, reparatursession 40, wissen-laden 95.
**References je Skill**: `R-LP\` content-gap 72, conversion-pack 82, geo-block 32, hintergrund-analysen 123, link-plan 30, pruefung-und-ablage 123, rolle 26, seitenkonzept 64, usp-matrix 73, voraussetzungen 112 · `R-KS\` ablage 56, analyse 18, aufbau 198, intake 169, konzept 18, link-plan 44, rolle 20, volltext 19 · `R-PS\` ablage 60, analyse 26, aufbau 247, intake 179, konzept 29, link-plan 46, rolle 20, volltext-und-familie 35 · `R-KR\` scoring 72, suggest-serp 131, zielseiten 33 · `R-PO\` angebot 75, auswahl 110, einwaende 89 · `R-BL\` ablage 53, entwurf 60, interview 39, pruefung 35, zweig 63 · `R-PB\` ablage 48, entwurf 38, interview 29, kannibalisierung 13, pruefung 27.
**Templates**: blog-anleitung 390, blog-ratgeber 361, content-ablage 113, kategorieseite 462, landingpage 557, medien 31, positionierung 42, produktseite 610, projekt-beitrag 375, rankmath\meta-felder 35, schema-org\blog-jsonld 217, kategorieseite-jsonld 209, landingpage-jsonld 238, projekt-jsonld 212, woocommerce\felder 44, woocommerce\produkt-schema-kontrolle 141, wpbakery\README 7.
**Agenten**: geo-validator 209, inventar-sync 141, persona-anwalt 103, redaktions-lektor 127, serp-analyst 156, sortiment-scan 151, verlinkungs-stratege 321, wettbewerbs-analyst 145.
**Steuerung**: `KON` 571, `CO\CLAUDE.md` 94, `CO\README.md` 107, `CO\os.json` 88, `CO\.claude-plugin\plugin.json` 7, `…\marketplace.json` 13, `CO\hooks\hooks.json` 3, `CO\tools\hook_start.py` 279.
**Invarianten/Regeln**: `INV\` README 284, blog-beitrag 223, kategorieseite 229, keyword-recherche 134, landingpage 266, positionierung 35, produktseite 234, projekt-beitrag 191; `CO\docs\regeln\referenztabellen.md` 153, `skill-aufteilung.md` 41.
**tegards seo-geo**: `PB` 310, `KL` 162, `WA` 198, `VS` 225, `RS` 496, `OG` 145, `KI` 87.
**tegards sonstige**: `SERP-GSW` 145; `PY` (Z. 27–45 selbst, Rest Unteragent); `redaktionsstil.md` 185 (nur Z. 1–40); content-inventar blogartikel 32, kategorieseiten 61, landingpages 36, produktseiten 746, projekte 35 (nur Köpfe).
**TG Design**: `SV` 100; `inhaltliche-grundsaetze.md` 24 (Z. 1–24); `sortiment.md` 48 und `wordpress.md` 75 **nicht gelesen**.

**Nicht gelesen**: `CO\docs\specs\commerce-os-design.md`, `CO\docs\berichte\*`, `CO\tests\*` (nur Grep), `CO\fixtures\*`, `CO\tools\*` außer `hook_start.py`; Instanz-CLAUDE.md/AGENTS.md von tegards; Wiki-Seiten (Linien, Personas, Wettbewerber) außer `SERP-GSW`; `E:\tegards\marketing\content\*\entwurf.md` (nur Grep-Zeilen); `E:\TG Design\ausgelagert\sortiment.md`, `wordpress.md`.
