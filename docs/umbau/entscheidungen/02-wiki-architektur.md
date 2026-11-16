# Entscheidungen P2: Wiki-Architektur

Stand 16.11.2026 · Grilling abgeschlossen (Q1–Q19), Codex-Review (gpt-6-astra, xhigh, 20 Befunde) eingearbeitet, Streitfälle 17–20 von
Markus entschieden, Nachentscheidungen zu Frontmatter, Freigabe und Leselisten übertragen · Grundlage: `docs/umbau/dossiers/02-wiki-architektur.md`
Teile wurden in zwei Nebensessions (btw) entschieden und auf Markus' ausdrücklichen Auftrag übertragen. Q-Nummern folgen dem Grilling,
nicht der Fragenliste im Dossier. EL = `E:\Everlast Learning\marketing-workspace-0.5.0\`. Fundstellen zu Everlast sind in dieser Session
gelesen (selbst oder per Subagent); „nicht gelesen“ steht ausdrücklich dabei.

Leitsatz: **Everlast-Gerüst, Tegards-Faktensicherung.** Aus Tegards bleiben `quellen/`, `fakten.md` mit Belegpflicht, Prüfstellen mit
Klärer und Prüfseite und die Diff-Freigabe vor dem Commit bei Fakten. Die schwere Ablauf-Technik fällt weg.

---

## Teil A: Ort und Struktur

### A1 Ein Wissensort in den Everlast-Fächern (Q1)
- **Ergebnis:** W2. Tegards-Wissen geht in die Everlast-Fächer (`stammdaten/`, `strategie/`, `produkte/`, `kanaele/` …). Es gibt kein
  eigenes `wiki/` daneben. Die Inhalte werden nach Onboarding Weg 1 Station für Station neu eingearbeitet, nicht als Ordner umgezogen.
- **Begründung:** Ein Ort je Thema, keine Doppelungen (Personas, USPs, Wettbewerb). Die festen Prime-Pfade passen weiter
  (EL `.claude/commands/prime.md:5-12`, sechs feste Dateien). Die Erweiterung der Prime-Listen aus C1 ist eine bewusste Anpassung,
  kein unveränderter Everlast-Weg (Codex #7).
- **Verworfen:**
  - W1 (Tegards-Wiki als eigener Ordner): zwei Wissenswelten, `/prime` sieht es nicht.
  - W1-light (eigener Produktwissen-Bereich): kein Gewinn gegenüber `fakten.md` je Linie.
  - W3 (Fakten nach `wissen/`): stößt sich mit der Kurswissen-Logik.

### A2 Ordnerregel: fest oben, offen darunter (Nebensession, geändert durch Q14)
- **Ergebnis:**
  - Die oberste Ebene ist fest (`stammdaten/`, `strategie/`, `produkte/`, `kanaele/`, `quellen/` …). Ein neues Hauptfach legt nur Markus an,
    das LLM darf es vorschlagen.
  - In offenen Bereichen legt das LLM Dateien und bei Bedarf Unterordner frei an. Offene Bereiche sind z. B. `produkte/<linie>/technik/`,
    `strategie/umwelt/wettbewerber/`, Personas, Synthesen und `quellen/`.
  - Jeder offene Ordner führt ein Verzeichnis **`index.md`** (OKF, siehe C3), nicht `README.md`.
  - Eine neue Produktlinie ist ein Ordner nach Vorlage, den das LLM anlegen darf.
- **Begründung:** Feste Dateien halten `/prime` deterministisch, Wachstum (Wettbewerber, Quellen, Synthesen) bekommt einen Ort.
  Das deckt sich mit dem Karpathy-Muster: Die Struktur wird zwischen Nutzer und Agent ausgehandelt und im Schema festgehalten.
  `index.md` statt `README.md`, weil das OKF-Standard ist und Everlast-READMEs Erklärdateien sind (z. B. `swipefile/<fach>/README.md`).
- **Verworfen:**
  - Everlast pur: Wachsende Mengen haben keinen Ort.
  - Tegards pur: Strategie-Ebene fehlt, Struktur hängt am Werkzeug.

### A3 Produktlinie = Everlast-Dateien + `fakten.md`; `quellen/` an der Wurzel (Nebensession)
- **Ergebnis:**
  - Je Linie gibt es `produkte/<linie>/` mit den Everlast-Dateien (offer, ziele, casestudies, competitor, zielgruppe/ …) für den
    Marketing-Teil, dazu **`fakten.md`** für technische Werte mit Beleg auf `quellen/`.
  - `fakten.md` hat die Tegards-Pflichtabschnitte „Technische Fakten“, „Trust-Faktenliste“, „No-Gos“ und „Offene Fragen“.
  - `quellen/` ist die Rohschicht an der Wurzel, der Eingang ist `quellen/_eingang/`.
  - **Was unveränderlich ist (Codex #2):** In jedem Quellordner sind `original.*` und `extrakt*.md` unveränderlich. Eine neue Fassung wird
    ein neuer Ordner `_v<nr>`. `karte.md` ändert sich nur bei Prüfstellen-Status und `ersetzt_durch`, und zwar über den Faktenweg (B2).
    `quellen/index.md` und `quellen/_eingang/` sind veränderlich.
- **Begründung:** Das löst die 52-KB-Linienseite (`lamellendaecher.md`) auf. Belege bleiben prüfbar.
- **Verworfen:** Linienseite als ein großes Dokument behalten (≈ 14 k Token je Produktfrage).

### A4 `inbox/` bleibt Everlast-Briefkasten (Nebensession)
- **Ergebnis:** `inbox/` ist der Ausgangs-Briefkasten des Workspace an Markus (Brief je Lauf, `on-hold/`, `archiv/`), nicht der Quellen-Eingang.
- **Beleg:** EL `PRINZIPIEN.md:69`, `.claude/rules/inbox-brief.md:16,97`.

### A5 Vier Inhaltsarten, vier Orte (Nebensession)
- **Ergebnis:**
  - **(a) Wissen** gehört in die Fächer.
  - **(b) Rohquellen** gehören nach `quellen/`, auch Protokolle eigener Selbstversuche und Sprachnotiz-Transkripte.
  - **(c) Absichten** (Ideen, neue Kanäle und Werbemittel, Blog-Ideen, Themen aus Wettbewerber-Lücken) gehören in Backlog bzw.
    Pipeline (`projekte/backlog/`, Details P9), nicht ins Wiki.
  - **(d) Ergebnisse** (veröffentlichte Stücke) gehören in Projektordner und Content-Inventar. Die Erkenntnis daraus geht in die
    Learnings, ein neuer Fakt nach `fakten.md` mit Beleg auf das Versuchsprotokoll.
  - Eine Wettbewerber-Lückenanalyse ist eine Synthese im Fach Wettbewerb.
  - Sprachnotizen aus Google Drive landen im Eingang, der Head sortiert sie (Idee in den Backlog, Fakt nach `quellen/`).
- **Begründung:** Absichten sind keine Wahrheit und würden `/prime` und Agenten belasten.
- **Beleg:** EL `projekte/backlog/README.md:3,5`, `head-of-marketing.md:65`.

### A6 Ein Schreibort, andere Workspaces lesen nur (Nebensession)
- **Ergebnis:** Grundregel „ein Schreibort, andere Workspaces lesen nur, nicht kopieren“. Ein künftiger Vertriebs-Workspace bindet
  `stammdaten/`, `produkte/` und `quellen/` lesend ein (Pfadverweis, zusätzliches Verzeichnis oder Submodul, Bauform offen).
  Auf Markus' Wunsch steht das **nicht** auf `SPAETER.md`, sondern gilt als Grundregel.

### A7 Linienregel und die 9 Linien (Nebensession, löst P5 I-08 und Dossier-Frage 7)
- **Ergebnis:**
  - **Regel:** Eine eigene Linie hat eine eigene Zielgruppe, einen eigenen Wettbewerb oder ein eigenes Versprechen. Teilen zwei Kandidaten
    alle drei, sind sie Pakete einer Linie.
  - Modelle (Deluxe Plus, Tilt, Delight) sind Pakete in `offer.md`, ihre Werte stehen in `fakten.md`. Shop-Artikel und Varianten bekommen
    keinen Ordner, Quelle bleibt der Shop.
  - **Linien heute (9):**
    - Überdachungen & Pergolen: Lamellendach, Carport, Faltdach-Pergola-Markise, Terrassenüberdachung Glas, Terrassenüberdachung Polycarbonat.
    - Verglasungen & Sichtschutz: Glasschiebewand Deluxe, Fixverglasung, Seitenwand Alu-Polycarbonat, Keilfenster.
  - Die Ordner sind flach (`produkte/<linie>/`). Die Oberkategorie ist kein Ordner, sondern ein Kopf-Feld `oberkategorie:` und ein
    Eintrag in `produkte.md`.
- **Begründung:** Prime-Befehle nutzen feste Pfade (EL `.claude/commands/prime-content.md:13`, `produkte/<produkt>/zielgruppe/persona.md`).
  Eine zweite Ordnertiefe würde dort eine Bedingung erzwingen.
- **Beleg:** EL `.claude/skills/amm-new-product/references/ordner.md:98,101`. Quelle der Linien: `E:\tegards\sandbox\ueberdachungen-struktur.md`
  (laut Markus aktuell) und Markus' Angaben.
- **Folge P7:** Der Steuerstand kennt nur ein Produkt (EL `steuerstand/build.ts:3016-3018`, „genau ein Haupt-Angebot je Workspace“) und
  muss auf mehrere Linien umgebaut werden.

### A8 Personas in drei Ebenen (Q7)
- **Ergebnis:**
  - **A** `strategie/positionierung/zielgruppen.md`: Segmente für alle Linien.
  - **B** `strategie/positionierung/zielgruppen/<gruppe>.md`: gemeinsamer Zuschnitt, nur wenn mindestens zwei Linien ihn teilen.
    Heute `verglasungen-sichtschutz.md`, `terrassenueberdachungen.md` wird beim Anlegen geprüft.
  - **C** `produkte/<linie>/zielgruppe/persona.md`: gibt es immer, entweder mit eigenem Inhalt oder als Verweis auf B mit Abschnitt „Abweichungen“.
  - **Grundsatz:** Eine Aussage steht auf der höchsten Ebene, auf der sie noch stimmt. Der Agent liest A und C, B nur bei Verweis aus C.
  - **Wer entscheidet:** Beim Anlegen einer Linie schlägt der Skill (Everlast new-product, künftig `tg-`) „Verweis oder eigener Inhalt“ vor,
    Markus gibt frei. Spätere Unterschiede schlägt der Head vor.
- **Begründung:** Dieselben Kunden kaufen mehrere Linien. Doppelte Personas würden auseinanderlaufen. C bleibt am Everlast-Pfad.
- **Verworfen:** Everlast pur (volle Persona je Linie), Tegards pur (nur linienübergreifend, bricht die `prime-content`-Pfade).

### A9 Wettbewerber: Profil + Beobachtungen (Q8)
- **Ergebnis:**
  - Je Wettbewerber gibt es eine Datei `strategie/umwelt/wettbewerber/<name>.md` mit „Profil“ (zeitlos) und „Beobachtungen“
    (datiert, nur ergänzen).
  - `strategie/umwelt/mikroanalyse/competitor.md` ist die Übersicht, `produkte/<linie>/competitor.md` nur die Auswahl je Linie mit Verweisen.
  - SERP-Analysen gehen an P3.
- **Weggelassen:** Teilungsregel M-07 → `SPAETER.md` (größte Datei heute `terrawin.md`, 12,2 KB).

---

## Teil B: Faktenweg

### B1 Werkzeuge schlank: Frage W-00 aus P5 (Q2)
- **Ergebnis:**
  - **Bleibt (Python):**
    1. Extrakt-Skript: docling-Aufruf mit Seitenmarken und Bildausschnitten, herausgelöst aus `extrakt.py`/`pruefstellen.py`.
    2. Prüfseite (HTML): Wert aus dem Bild neben dem Bildausschnitt, Korrektur durch Markus, entkoppelt von Paket und Fingerabdruck.
    3. Pre-Commit-Prüfung, Ziel ≤ ~150 Zeilen. Sie prüft: Original und Extrakt in `quellen/` unverändert (A3), Pflicht-Frontmatter,
       Belegpfade lösen auf, jede Datei in einem offenen Ordner hat einen `index.md`-Eintrag (C3). Veraltete Dateien meldet nicht der
       Pre-Commit, sondern `tg-wissen-pruefen` (B6), weil die Frist dort an einer Stelle steht. Die frühere Warnung „Datei nach
       `verified` erweitert“ entfällt mit dem Feld `verified` (C3).
  - **Bleibt ohne Code:** Klärer-Agent `pruefstellen-klaerer` (Sonnet, nur Read), Stichprobe 5/10/alle als Skill-Regel,
    sha256-Duplikatprüfung im Skill, Belegpflicht, Warnblock, „Widerspruch markieren, nie auflösen“, Quellen unveränderlich.
  - **Entfällt:** Paket, Fingerabdruck-Freigabe, Sperre, Journal, Register, Locks, Abgleich, Graph-Werkzeug, Wächter (947 Zeilen).
    Ersatz ist Git (B2) und die Wissensprüfung auf Zuruf (B6).
- **Begründung:**
  - Prüfstellen sind der Normalfall: 10 von 12 Quellen haben welche, 421 Kennungen, davon 337 Art „bild“. Markus hat über die Prüfseite
    Werte korrigiert: **11 korrigierte Prüfstellen** (Vermerk „korrigiert (human:mm …)“, 25./26.10.), je Tabellenzeile genau eine.
    Die früher genannte Zahl 38 zählte alle Kennungen der betroffenen Sammelzeilen, die Zahl 19 zählte den Vermerk in 8 Sammelzeilen
    doppelt. Beide waren falsch (Codex #12). Die Prüfseite findet also echte Fehler und bleibt, anders als im Dossier („optional“).
  - Paket, Journal, Locks und Register schützten gegen mehrere Schreiber, Repos und Freigeber. Das ist kein heutiger Fall.
- **Folge für die 30 Zeilen mit Fußnote ¹ aus P5** (`dossiers/05-altbestand.md:15-17,24`), einzeln eingeordnet (Codex #15), weil Extrakt
  und Prüfseite bleiben:
  - **Erledigt (22), weil ihr Werkzeug entfällt:** W-01, W-03 bis W-10, W-16, W-17, W-19, W-20, W-22 bis W-26, W-30, W-31, W-34, W-35.
    W-10 deckt jetzt B6 ab, W-26 ist die Regel in A9 ohne Wächter.
  - **SPAETER (6):**
    - W-11 bis W-15: Extrakt für Audio, E-Mail, HTML, XLSX-Bilder und die PDF-Weiche (je eine Zeile, zusammengefasst).
    - W-18: Komfort der Prüfseite.
  - **P7 (2):**
    - W-21: „KI bestätigt“ nur gegen die PDF-Textebene, eine Bedeutungsregel für Klärer und Prüfseite.
    - W-32: mehrzeilige Belege im Pre-Commit prüfen.
- **Bewusste Einschränkungen:**
  - Kein Werkzeugschutz, wenn sich zwischen Diff-Ansicht und Commit etwas ändert. Regel: Commit direkt nach dem Ja.
  - Die Sperre ist nur noch Regel + Pre-Commit. Eine Änderung am Skill vorbei fällt erst im PR auf.
  - Die Graph-Prüfung ist weniger lückenlos als das Werkzeug.
- **Verworfen:**
  - Ganzen Python-Stack mitnehmen (11 123 Zeilen für eine Lage, die es nicht mehr gibt).
  - Ohne Prüfseite (würde die nachweislich wirksame Bildprüfung streichen).
  - Gar kein Python (Extrakt mit Seitenmarken braucht ein Skript).

### B2 Freigabe von Wissen und die P1-Git-Regel (Q3)
- **Ergebnis:**
  - **Belegpflichtige Fakten** laufen so: Diff im Chat zeigen, Markus sagt ausdrücklich Ja, direkt danach ein Commit (ein Einpflegen =
    ein Commit). Das gilt für Änderungen unter `quellen/**` (außer `index.md` und `_eingang/`) und für jede Änderung eines belegpflichtigen
    Werts nach B3, **egal in welcher Datei** (Codex #1). Beispiel: Die Garantie in `offer.md` ist so ein Wert, Everlast sieht sie dort vor
    (EL `amm-workspace-setup/references/struktur.md:116`).
  - Ort solcher Werte ist `fakten.md` mit Beleg. Andere Dateien übernehmen den Wert wortgleich mit Verweis auf `fakten.md`.
    `tg-wissen-pruefen` (B6, Stufe a) meldet Abweichungen.
  - Alle übrigen Wissensänderungen (Strategie, Kanäle, Learnings, Personas …) laufen im normalen `develop`-Fluss nach P1. Der PR
    `develop` → `main` ist das zweite Netz.
- **Begründung:** Die Strenge sitzt dort, wo ein falscher Wert schadet (Maße, Statik). P1 erlaubt Sessions, auf `develop` selbstständig zu
  committen. Für Fakten ist dieses Ja die Ausnahme.
- **Verworfen:** nur der PR (zu spät für Maße und Statik), Freigabe vor jedem Commit jeder Wissensdatei (bremst ohne Nutzen).

### B3 Belegpflicht für technische und rechtlich heikle Werte (Q4)
- **Belegformen (Codex #3):** Es gilt der Seitenanker im Extrakt, `[intern: quelle:/<ordner>/r<n>#seite-<n>]`. Für Textquellen ohne
  Extrakt gilt der Überschriftenanker im Original, `[intern: quelle:/<ordner>/original#<anker>]`. Beide Formen kommen unverändert aus
  Tegards (`E:\tegards\knowledge\_SCHEMA.md:72`). Die zweite Form ist nötig, weil die Statik-Notiz keinen Extrakt hat.
- **Ergebnis:** Die Belegpflicht gilt für Maße, Statik, Lasten,
  Zertifikate und Normen, Garantie und Material. Weiche Aussagen (Nutzen, Einsatzfälle) brauchen keinen Anker. Warnblock bei Widerspruch
  und ungeklärtem Wert, „markieren, nie auflösen“, Quellen unveränderlich: alles voll gültig.
- **Begründung:** Deckt das reale Risiko (Haftung) ab. Heute tragen genau drei Seiten Quellenbelege (190 Zeilen: Lamellendächer 120,
  Glasschiebewände 48, Statik 22).
- **Folge:** P5 I-07 (stellengenaue Anker) ist damit Teil der Regel.
- **Verworfen:** volle Strenge für jede Produktaussage.

### B4 Einziger Freigeber (Q9)
- **Ergebnis:** Markus (`human:mm`) ist einziger Freigeber.
- **Begründung:** `human:bs` hat nie freigegeben: 0-mal in `log.md`, in 26 Knowledge-Commits und in `verified`. Alle 16 Wiki-Dateien mit
  `verified` tragen `human:mm` (gezählt: `grep -l "^verified:" -r wiki`; die früher genannte 17 war falsch, Codex #13).
- **Weggelassen:** zweiter Freigeber → `SPAETER.md`.

### B5 Protokoll und Prüffälle: `log.md`, `pruefungen.md` entfallen (Q18)
- **Ergebnis:**
  - Das Protokoll für Quellen ist das Git-Log, ein Commit je eingepflegter Quelle. Bereich `quellen`, z. B. `feat(quellen): <ordner> eingepflegt`.
  - Prüffälle werden zum Abschnitt „Offene Fragen“ in der betroffenen Datei.
  - Die drei offenen Prüffälle vom 27.10. (`ungepruefte_erweiterung` bei Glasschiebewand Deluxe, Lamellendach, Foravida) entfallen,
    weil diese Dateien nach Weg 1 neu entworfen werden.
- **Beleg:** EL hat kein globales Protokoll (`find -iname log.md` ohne Treffer). Je Projekt gibt es `arbeitslog.md` (`AGENTS.md:24`),
  Conventional Commits ohne feste Typenliste (`.claude/rules/git-branches.md:5`).

### B6 Prüfungen: `tg-konflikt-scan` + neu `tg-wissen-pruefen` (Q19)
- **Ergebnis:**
  1. **`amm-konflikt-scan` → `tg-konflikt-scan`**, unverändert übernommen. Er findet Widersprüche zwischen Steuerdateien und zwischen
     Steuerdateien und Wissen.
  2. **`tg-wissen-pruefen` (neu, nicht Everlast)** ersetzt das Tegards-`wiki-pruefen`, das am Paketwerkzeug hängt.
     - **Er prüft:** Widersprüche zwischen Wissensdateien, Fakten ohne Beleg, fehlende Personas je Linie, veraltete Seiten
       einschließlich `profil_geprueft_am` (Frist nach C3) und fehlende `index.md`-Einträge.
     - **Diagnosekette** aus `wiki-pruefen`: Gab es das Wissen? Wurde es gefunden? Ist es aktuell und richtig gewichtet? Ist das Urteil
       richtig? Ist die Abnahme bestanden?
     - **Ausgabe:** Bericht unter `daten/<JJMMTT>-wissen-pruefen/` und ein Brief. Er korrigiert nie selbst, es gibt kein Paket.
  3. **Zwei Stufen, ohne Zeitplaner:**
     - **(a) Klein und immer:** Beim Einpflegen oder Ändern einer Wissensdatei prüft der Skill die berührten Dateien gegen ihre Nachbarn
       (gleiche Linie, gleiches Fach): Widerspruch, fehlender Beleg, fehlender `index.md`-Eintrag.
     - **(b) Vollprüfung:** fällig nach 30 Tagen oder 10 Wissens-Commits seit der letzten Prüfung, je nachdem, was zuerst eintritt.
       - Erinnerung als Inbox-Brief **und** als Steuerstand-Knopf „Wissen prüfen“ im Bereich „Wissen“ mit Erklärtext (was geprüft
         wird, Diagnosekette, keine Selbstkorrektur, Bericht zur Freigabe). Bau P7.
       - Sie läuft mit, wenn die Learnings-Verdichtung (D2) ansteht.
       - Den Zustand liefern das Datum des letzten Berichts in `daten/` und `git log`.
       - **Gegen Codex #17 beibehalten**, nichts verschlankt. Grund (Markus): Ohne Erinnerung wird die Prüfung vergessen.
- **Begründung (Codex #10 berücksichtigt):**
  - Der Konflikt-Scan liest die Wissensfächer ein (EL `konflikt-scan.ts:88`, Schicht „wissen“). Alle Wissensdateien haben aber dieselbe
    Einheit „wissen“, also schlägt die **mechanische Kandidatensuche** keine Paare Wissen gegen Wissen vor (`:183`). Drift meldet sie bei
    Wissen nie (`:190`).
  - Die Leser-Agenten lesen ihre Pakete vollständig (EL `references/rubrik.md:100-101`) und können einen Widerspruch zwischen zwei
    Wissensdateien deshalb zufällig bemerken. Gezielt gesucht wird er nicht.
  - Was dem Scan sicher fehlt: die Prüfung „Wert ohne Beleg“, Persona-Abdeckung je Linie, veraltete Dateien und der gezielte Abgleich
    `fakten.md` gegen die Marketing-Dateien derselben Linie.
  - Den Scan umzubauen hieße, in Paarlogik und Rubrik einzugreifen, die für Steuerdateien gebaut sind.
  - Heutiger Fall: In Weg 1 entstehen 9 neue `fakten.md`.
- **Befund Everlast:** EL `amm-konflikt-scan/SKILL.md:36` sagt, `--tief` nehme `wissen/` und Projektdateien dazu. Im Skript wirkt `--tief`
  nur auf die References globaler Skills (`konflikt-scan.ts:99`). Das ist ein Widerspruch in Everlast, beim Übernehmen in der Skill-Datei zu korrigieren (P7).
- **Verworfen:** den Konflikt-Scan um Wissen erweitern; nur den Konflikt-Scan ohne Wissensprüfung (dann hätte B1 keinen Lint).
- **Nicht gelesen:** ob der EL-Steuerstand (Reiter Fokus) schon Karten für fällige Aufgaben kennt (P7 vor dem Bau prüfen).

---

## Teil C: Rückfluss in den Kontext

### C1 Agenten lesen selbst (Q12)
- **Ergebnis:**
  - Wie Everlast lesen Agenten selbst (prime + prime-<fach>). Die Aufteilung folgt dem Everlast-Muster (Codex #7): Die Prime-Listen
    sind die Basis des Fachs, der Abschnitt „Context“ der Agentendatei der Zusatz des Agenten (EL `content-marketer.md:40-46`).
  - **In die Prime-Listen** (bewusste Anpassung):
    - `fakten.md` der Linie in die produktbezogenen `prime-<fach>`-Listen, neben `produkte/<produkt>/…` (wie EL `prime-content.md:13`).
      No-Gos und Warnblöcke gelten immer. Welche der fünf Fachlisten produktbezogen sind, klärt P7.
    - Persona B in `prime-content` (A8).
    - Die Regel „feste Zahl Dateien, keine weitere“ (EL `prime.md:25`, `prime-content.md:19`) bleibt. Eine neue Grunddatei wird bewusst
      aufgenommen, die Zahl im Text wird angepasst.
  - **In den Abschnitt „Context“ des Agenten:** Aus den Learnings „Gilt heute“ und dazu alle Zeilen seit der letzten Verdichtung, höchstens
    40 nach D2 (Codex #8). Gibt es noch keine Verdichtung, liest der Agent alle Zeilen. Keine älteren Verläufe.
- **Begründung:**
  - Mit dem Aufteilen der Linienseite (A3) fällt der Hauptgrund für den gedeckelten Auszug weg.
  - Everlast-Updates werden nie automatisch übernommen, nur von Hand nach dem Vergleich (E1). Die Sorge, ein Update überschreibe
    angepasste Prime-Listen, trägt deshalb nicht.
- **Verworfen:** die Zusatzlektüre nur in Agentendateien und Head (erste Fassung): Sie hätte das Everlast-Muster Basis/Zusatz verlassen.
- **Verworfen:**
  - Tegards `WISSEN-AUSZUG` ≤ 16 KB: Die Hauptsession müsste alles erst selbst lesen. → `SPAETER.md`.
  - P5 M-05 Rechercheur-Agent fürs Wiki: wurde gemessen und war schlechter als direktes Lesen. Kein SPAETER-Eintrag.

### C2 `kern.md` als Always-on-Import entfällt (Q13)
- **Ergebnis:** Der Inhalt geht nach `stammdaten/unternehmen.md` und wird über `/prime` geladen. `AGENTS.md` bekommt nur 2–3 Sätze, wer Tegards ist.
- **Begründung:** Immer Geladenes kostet in jeder Session und jedem Agentenlauf, auch dort, wo es niemand braucht (heute 3,7 KB ≈ 1 k Token
  über `@`-Import in `E:\tegards\CLAUDE.md`).

### C3 Leseweg, Verzeichnis, Frontmatter, Graph (Q14)
- **Leseweg in Stufen:**
  1. `/prime` (feste Liste)
  2. `.claude/references/workspace-karte.md` (Landkarte der Ordner, Everlast; verweist bei offenen Ordnern auf deren `index.md`)
  3. `index.md` des passenden offenen Ordners
  4. Datei ganz
  5. bei Bedarf über den Seitenanker bis `quellen/<ordner>/extrakt.md` und die Karte
- **Verzeichnis `index.md` (OKF):**
  - Format: `* [Titel](datei.md) - <Satz>. Stichworte: <…>. Linien: <…> · Stand <Datum>`
  - Je Eintrag ein Satz von höchstens ~20 Wörtern (Dokumentart und wann öffnen) und höchstens 10 Stichworte; gesamt ≤ ~40 Wörter.
  - Das LLM pflegt den Eintrag beim Anlegen oder Ändern, der Pre-Commit prüft, dass er da ist. Kein Generator-Skript.
- **Frontmatter nach Everlast, OKF-Felder gestrichen (Nachentscheidung Markus, ersetzt die erste Fassung „OKF v0.2“):**
  - **Felder je Datei wie ihre Everlast-Vorlage (Korrektur der Nebensession):** Jede Datei bekommt genau die Felder und Status-Werte
    der Vorlage ihres erzeugenden Skills (`assets/`, `references/`). Es gibt kein eigenes Einheitsschema.
    - Produkt-Stubs (`offer.md`, `persona.md` …) haben nur `status`, `last_updated`, `source` (EL `produkte/produkt-a/offer.md:1-5`,
      `zielgruppe/persona.md:1-5`). Der Steuerstand liest `last_updated` (EL `steuerstand/build.ts:89`), es gilt endgültig.
    - `titel` und `typ` stehen, wo die Vorlage sie hat: in `wissen/` (mit `block` und `lektion`, EL `wissen/README.md:8`) und in
      Vorlagen wie `amm-goal-setter/assets/`, `amm-kampagne/assets/`, `amm-leadmagnet-funnel/assets/`, `amm-youtube-radar/assets/`,
      `amm-loops/assets/branchen-update/` (8 Vorlagen, per `grep` gezählt).
    - `quelle_commit` in den Cleanup-Kern-Dateien (EL `workspace-cleanup/SKILL.md:54`).
  - **Zusatzfelder (Tegards), kommen nur dazu:** `produktlinien`, `stuetzt_sich_auf` (D3), `oberkategorie` (A7) und
    `profil_geprueft_am`, nur in Wettbewerberprofilen.
  - **Gestrichen:** `type`, `title`, `description`, `tags`, `aliases`, `generated {by, at}` (ganz, egal welche Herkunft),
    `verified {by, at}`, `sources` in Objektform (ersetzt durch Everlasts `source`), `stale_after`, `id`, `beziehungen`.
    Beziehungen sind Links im Text. `id` ist entbehrlich, weil Belege über Pfade verweisen (B3).
  - **`profil_geprueft_am`** behält die Tegards-Bedeutung (`E:\tegards\knowledge\_SCHEMA.md:80`, Codex #9): Nur eine vollständige
    Profilprüfung erneuert es, Beobachtungen und Teilkorrekturen nicht. Fehlt es, gilt das Profil als „nie geprüft“, beim Umzug kein
    Scheindatum. Die Frist steht an einer Stelle und ist einstellbar (z. B. in einer Referenz von `tg-wissen-pruefen`), vorerst 6 Monate.
    Die Fälligkeit errechnet die Prüfung selbst (B6).
- **Freigabe und Fortschritt 1:1 wie Everlast (Nachentscheidung Markus, ersetzt „Fertig heißt stable + verified“ aus Codex #6):**
  - Setup-Dateien verlieren `status: stub` erst nach Freigabe durch den Nutzer (EL `amm-content-strategie/SKILL.md:30`). Das ist
    Everlasts eigene Antwort auf Codex #6: Keine Station wird vor der Freigabe grün. Das gilt auch beim Altbestand in Weg 1.
  - Offen heißt `status: stub` oder Datei fehlt, alles andere ist fertig (EL `amm-workspace-setup/SKILL.md:47`, `steuerstand/build.ts:106`).
    Setup und Steuerstand bleiben unverändert.
  - **`status: entwurf`** heißt wie bei Everlast „noch nicht freigegeben“. Es steht in 12 Skill-Dateien, z. B. „`status: entwurf` bleibt
    stehen, bis ein Mensch freigibt“ (EL `amm-video-zu-blog/SKILL.md:254-255`) und `status: entwurf` mit `freigabe_person: offen`
    (EL `amm-personal-brand/references/steckbrief-vorlage.md:30,33`). Weitere: Vorlagen in `amm-content-strategie/assets/`
    (Säulen, Suchverhalten, Ideen), `amm-kampagne`, `amm-leadmagnet-funnel` (Mailstrecke), `amm-seo` (Befund), `amm-pillar-to-blog`.
  - Sonderform Brand Voice: `entwurf` bleibt zusätzlich stehen, wenn mehr als ein Viertel der Regeln unbelegt ist
    (EL `amm-brand-voice/references/grundlagen.md:186-188`).
  - Es gibt kein `draft` / `stable` / `deprecated` und kein `verified`.
  - Das Ja vor dem Commit für belegpflichtige Werte (B2) bleibt.
- **Suche:** Volltext- und semantische Suche (P5 M-06, qmd) gibt es heute nicht → `SPAETER.md` mit qualitativem Auslöser.
  Das Kriterium „2 MB“ ist verworfen (nur ein Ersatzmaß).
- **Graph-Ansicht → `SPAETER.md`** (Streitfall Codex #18, Markus folgt Codex): Heute braucht keine Such- oder Prüfaufgabe sie. Die Kanten
  bleiben ohne Zusatzpflege ableitbar (Links im Text, `source`, `produktlinien`, `stuetzt_sich_auf`), es geht nichts verloren.
  Frei benannte Kanten gehören mit in diesen Eintrag.
- **Korrektur zum Beleg:** Die Annahme „`workspace-karte.md` hat nur Dateinamen“ stimmt nicht. Dort stehen Kurzbeschreibungen je Ordner
  (EL `.claude/references/workspace-karte.md:12,19,20`). An der Entscheidung ändert das nichts: Die Karte führt Ordner, `index.md` die Dateien offener Ordner.
- **Verworfen:** `README.md` als Verzeichnis, `INDEX.md` generiert (Tegards), feste Beziehungsfelder, Frontmatter nach OKF v0.2
  (doppelt zu Everlast-Feldern, ohne Leser im Workspace), ein eigenes Einheitsschema für alle Dateien, Status-Leiter
  draft/stable/deprecated mit `verified`.

---

## Teil D: Lernen aus Arbeit

### D1 Agent-Memory nur für Handwerk (Q5)
- **Ergebnis:**
  - Wie Everlast: `memory: project` für alle Fachagenten, je Lauf 3–5 Zeilen Destillat, nur der Head trägt in Wissensdateien ein,
    `.claude/agent-memory/` nicht in Git.
  - **Abweichung 1 – keine Doppelung:**
    - Das Destillat wird aufgeteilt. Fachliches (Winkel, Voice, was funktioniert hat) geht nur an den Head. Handwerk (Prompt- und
      Modell-Muster, Werkzeug-Fallen, Gate-Fehler) geht nur ins eigene Memory.
    - Der Halbsatz „dieselben Zeilen zusätzlich ins eigene Memory“ wird an sechs Stellen umformuliert (Liste unten).
    - „Gilt heute“ der Learnings steht in der Pflichtlektüre des Agenten.
  - **Abweichung 2 – Rückweg:** Bei der Verdichtung (D2) liest der Head auch die Agent-Memories und schlägt Wiederkehrendes als Änderung an
    Agent, Skill oder Rule vor. Freigabe per Diff.
  - Die Konflikt-Suche lässt `agent-memory` weiter aus (EL `steuerstand/bretter.ts:586`, `konflikt-scan.ts:36`). Eine Memory-Anzeige im
    Steuerstand wird nicht gebaut → `SPAETER.md`.
  - Das Agent-Memory wandert nicht auf andere Rechner mit (für P6).
- **Belege:**
  - Head-Regel und Zielorte: EL `head-of-marketing.md:47-49`.
  - `memory: project` in allen sechs Agenten: `content-marketer.md:21`, `copywriter.md:23`, `grafik-designer.md:23`, `ux-ui-designer.md:23`,
    `video-cutter.md:23`, `webdesigner.md:21`.
  - Die sechs Doppelungsstellen: `content-marketer.md:71`, `copywriter.md:65`, `ux-ui-designer.md:68`,
    `references/grafik-designer-workflows.md:115`, `references/video-cutter-workflows.md:174`, `references/webdesigner-messen.md:76`.
  - Nicht in Git: `git-branches.md:20`. Der Ordner `.claude/agent-memory/` ist in EL leer.
  - Eine „Voice-Datei“ ist in `head-of-marketing.md` nicht benannt, Agenten nennen `bildsprache.md`, `brand-design/assets/` und
    `strategie/brand-identity/brand-design/`. Den genauen Zielort klärt P7.
- **Befund Everlast:** `amm-workspace-setup/references/struktur.md:77` sagt, die Werkstatt-Reiter lesen `.claude/agent-memory/`.
  `steuerstand/build.ts` enthält „agent-memory“ nicht. Beim Übernehmen korrigieren (P7/P9).
- **Begründung:** Eine Wahrheit statt zwei Fassungen, Fachwissen sichtbar im Diff und für andere Agenten, Rechnerwechsel ohne Verlust.

### D2 Learnings: anhängen, verdichten zu „Gilt heute“ (Q10)
- **Ergebnis:**
  - **Einsammeln:** eine Datei je Fach (z. B. `kanaele/content-learnings.md`), je Zeile Datum · Erkenntnis · Beleg. Es wird nur angehängt
    (EL `AGENTS.md:50`).
  - **Verdichten:** Der Head schreibt oben „Gilt heute“ (höchstens 15 Punkte, je Punkt ein Verweis auf die Ursprungszeilen), darunter steht
    „Verlauf“. Freigabe per Diff.
  - **Auslöser:** ab 40 neuen Zeilen seit der letzten Verdichtung (der Head meldet sich im Brief) oder auf Zuruf.
- **Begründung:** Everlast hat keine Verdichtung, alte Zeilen gelten still weiter. Die Zeilenschwelle folgt dem Arbeitsrhythmus:
  Verdichtet wird, wenn es genug Neues gibt, nicht nach Kalender. Agenten lesen die Zeilen seit der letzten Verdichtung mit (C1), deshalb
  geht bis dahin nichts verloren. (Die frühere Begründung „Termin braucht Zeitplaner“ trug nicht, Codex #16: Eine Frist lässt sich wie in
  B6 beim nächsten Lauf prüfen.)
- **Verworfen:** quartalsweise.

### D3 Synthesen im Fach (Q11, P5 M-04)
- **Ergebnis:** Stützt sich eine Antwort auf mindestens 3 Dateien oder enthält sie eine eigene Auswertung, schlägt Claude in einem Satz vor,
  sie abzulegen. Höchstens einmal je Thema und Session, headless nie, vorher bestehende Synthesen prüfen. Bei Ja entsteht eine normale
  Datei im passenden Fach mit `stuetzt_sich_auf: [pfade]`. Kein Sammelordner, kein Paket.
- **Weggelassen:** Veraltungs-Skript für Synthesen → `SPAETER.md`. Die Warnung „Datei nach `verified` erweitert“ entfällt mit dem Feld
  `verified` (C3).

### D4 Kein Debrief-Command (Q17, P5 M-08)
- **Ergebnis:** Wird nicht übernommen.
- **Begründung:** Everlast sichert über drei Pflichten:
  - Jeder Lauf mit Ergebnis legt einen Brief ab (EL `.claude/rules/inbox-brief.md:16`).
  - Jede Session endet mit Merge und Push (`git-branches.md:13`).
  - Der Agent liefert ein Destillat an den Head (`head-of-marketing.md:47-49`).

  In `.claude/settings.json` gibt es nur `SessionStart`-Hooks, keinen Stop-Hook.
- **Weggelassen:** → `SPAETER.md`.

---

## Teil E: Übernommene Bausteine

### E1 `wissen/` eingefroren, Everlast-Abgleich, Challenge (Q6)
- **Ergebnis:**
  1. **`wissen/`** (Everlast-Kurshandbuch, 37 Blätter plus `README.md`; Codex #13) wird übernommen und eingefroren. Aufgefrischt wird nur auf Zuruf: Markus gibt den Pfad
     einer heruntergeladenen Everlast-Version an, es kommt zuerst eine Liste der Unterschiede (neu / geändert / weggefallen), Markus wählt
     aus, dann wird kopiert. Das ist Teil des manuellen Abgleichs aus Punkt 3, ohne eigenen Button.
  2. **Challenge** (`amm-challenge` + Rule `challenge-vor-handwerk`) wird übernommen. Damit ist der P1-Punkt für P9 „Challenge-Jury ja/nein“
     entschieden: ja. Details (u. a. Gattung „Lehrinhalt“ → `strategie/marketing-wissen/`) klärt P9.
  3. **Everlast-Abgleich bleibt der manuelle P1-Ablauf** (Streitfall Codex #19, Markus folgt Codex): Markus lädt eine neue Version
     herunter, eine Session vergleicht, er entscheidet je Punkt. Updates werden nie automatisch übernommen. Kein Knopfdruck, kein
     fester Abgleich-Baustein, kein `everlastpull`. Die P1-Entscheidung „Vergleich neuer Versionen manuell“ gilt unverändert.
     - Weggelassen: Update-Hinweis per Inbox-Brief (nur Versionsnummer vergleichen, nichts herunterladen oder ändern) → `SPAETER.md`,
       Auslöser: Everlast hat eine öffentlich lesbare Versions- oder Änderungsseite.
- **Belege:** EL `AGENTS.md:39` („Kurswissen und Handbücher“), `wissen/README.md:5` (ohne Unterordner, Widerspruch zu `AGENTS.md:39`
  „je Block ein Ordner“). `everlastpull` ersetzt Systemdateien inkl. Wissen und kennt keine Ordnerwahl. Die Umbenennung `amm-` → `tg-`
  würde den Abgleich des Skripts brechen.

### E2 `workspace-cleanup` (Q6-Rest)
- **Ergebnis:** Wird übernommen und läuft nur bei Bedarf, ohne festen Rhythmus.
  - Die Kern-Dateien gehen nach **`projekte/kern/<JJMMTT>-archiv-kern.md`** statt nach `wissen/workspace-memory/` (EL
    `workspace-cleanup/SKILL.md:18,41`).
  - `projekte/kern/` liegt nicht im Löschziel des Cleanups und wird dort ausdrücklich ausgeschlossen.
  - Codex #4: Die erste Fassung `projekte/archiv/<JJMMTT>-kern.md` lag im Löschziel. Der Skill leert `projekte/archiv` (EL
    `workspace-cleanup/SKILL.md:7`), der Kern wäre beim nächsten Aufräumen mitgelöscht worden.
  - `osascript` (`:44`) portiert P7.
- **Begründung:** `wissen/` bleibt reines Kurswissen. Der Steuerstand liest nur Dateien direkt in `wissen/`, ein Unterordner wäre dort unsichtbar.
- **Prüfpunkt P7/P9 (Deutung, nicht belegt):** Cleanup erkennt „in Nutzung“ über Verweise. Medien liegen laut P1 nicht in Git, also nie
  Stück-Ordner mit `web/` löschen.

### E3 `learn` → `tg-skill-aus-material` (Q19, Teil learn)
- **Ergebnis:** Wird übernommen und umbenannt: Der Name „learn“ verschleiert den Zweck. Aus fremdem Material (Video, PDF, Kursseite) entsteht
  genau ein Skill je Lauf, mit `references/herkunft.md`. Getrennt von `video-wissen`/`kanal-wissen`, die Wissen zusammenfassen.
- **Windows-Port (Bau P7):**
  - `material-zu-text.sh` → `material_zu_text.py`.
  - Transkription immer mit faster-whisper large-v3 auf der GPU (CUDA), Rückfall CPU mit gleichem Modell.
  - Fehlende Abhängigkeiten auf dem Rechner: ffmpeg, yt-dlp, uv, faster-whisper.
  - Risiko: RTX 50er braucht aktuelle CUDA-Bibliotheken.
- **Keyframe-Regel (Streitfall Codex #20, Markus folgt Codex):** fester Bildabstand wie Everlast. Der Skill fragt je Video nach dem
  Abstand und empfiehlt einen Wert: Screencast 5–10 s, Vortrag 20 s, nur Sprecher ohne Bilder (EL `learn/SKILL.md:48-49`).
  Er übergibt den Abstand auch beim Aufruf in Schritt 2. Szenenwechsel-Erkennung, Ähnlichkeitsfilter und Sprecher-Vorblick
  entfallen ohne SPAETER-Eintrag.
- **Befund Everlast:**
  - Die Transkription liegt nicht im Paket (`learn/SKILL.md:86`, Skript ruft `~/.claude/skills/media-use/scripts/transcribe.mjs`).
    `SKILL.md` nennt parakeet-mlx (nur Apple-Chips).
  - **Korrektur (Codex #14):** Das Skript nimmt den Bildabstand als dritten Parameter, 20 s ist nur der Default
    (`scripts/material-zu-text.sh:3,8`). Der Skill unterscheidet Screencast 5–10 s und Vortrag 20 s oder keine Bilder (`SKILL.md:46-50`).
    Nur der Aufruf in Schritt 2 übergibt keinen Abstand (`SKILL.md:22`).
  - Die Aussage „Everlast zieht stur alle 20 s ein Bild“ war falsch.

---

## Teil F: Altbestand

### F1 Die 12 Quellen werden überführt (Q16)
- **Ergebnis:**
  - Überführen heißt hier, nicht kopieren:
    - Ablage unter `quellen/<bereich>/<ordner>/` nach der neuen Ordnerregel, mit Frontmatter nach C3 auf jeder Karte und einem `index.md` für `quellen/`.
    - Original und `extrakt.md` bleiben 1:1 (Prüfung per sha256 gegen den Altbestand). Der Prüfstellen-Status und alle Korrekturen von
      Markus bleiben wörtlich erhalten (11 korrigierte Prüfstellen, B1).
    - Jede Quelle läuft einzeln über den Faktenweg (B2).
    - Die Wissensdateien darüber (`fakten.md`, Personas, Wettbewerber …) entstehen nach Weg 1 neu und belegen mit Seitenanker auf diese Quellen.
  - Die Terrawin-Webseite (`2026-11-01_webseite_terrawin-preiskonfigurator_de`, ohne Karte) wird regulär neu eingepflegt.
  - Der alte `E:\tegards\knowledge\eingang\` wird nicht übernommen und steht auf der Löschliste.
- **Begründung:** Weg 1 erlaubt „Fertiges wird übernommen“ (STAND.md, feste Entscheidung 14.11.). Quellen sind unveränderliche Rohdaten,
  sie neu einzupflegen wäre reiner Verlust. Durch das Überführen statt Kopieren folgen Ablage, Frontmatter und Index der neuen Architektur.
- **Ausführung:** P8 (Weg 1), Werkzeuge P7.

### F2 `marketing/marketing-wissen/` geht an P3/P4 (Q15)
- **Ergebnis:** P2 legt nur den Grundsatz fest: dieselben Fächer, nach Weg 1 neu eingearbeitet, nicht kopiert.
  - **P3:** SEO/GEO (7 Dateien: Playbook, Keyword-Landkarte, Website-Architektur, Verlinkung, Referenzseiten, Off-Page-GEO, KI-Sichtbarkeits-Log).
  - **P4:** Redaktionsstil (1) und Content-Inventar (5).

### F3 P5-Zeilen, die P2 betreffen
| ID | Ergebnis |
|---|---|
| W-00 + 30 ¹-Zeilen | entschieden in B1: 22 erledigt, 6 SPAETER (W-11–15, W-18), 2 P7 (W-21, W-32) |
| I-07 Seitenanker | Teil der Belegregel B3 |
| I-08 Linienstruktur | entschieden in A7 |
| M-04 Synthese-Rückweg | D3 |
| M-05 Rechercheur-Agent | nicht übernommen (C1), gemessen schlechter |
| M-06 Suche qmd | SPAETER (C3) |
| M-07 Wettbewerber teilen | SPAETER (A9) |
| M-08 Debrief | nicht übernommen, SPAETER (D4) |
| M-09 Wissenssystem-Konzept Oktober | nur Quelle, kein Bauauftrag |

---

## Querschnitt

### X1 Arbeitsregeln für Everlast-Aussagen (gilt für den ganzen Umbau, 16.11.2026)
Anlass: Empfehlungen zu Everlast-Bausteinen wurden mehrfach erst auf Nachfrage korrigiert (Beispiel Q19, Konflikt-Scan).
1. Kein Satz über Everlast ohne Fundstelle, nur nach eigenem Lesen in der laufenden Session mit Pfad:Zeile. Ungelesenes heißt „nicht gelesen“.
2. Unter jeder Empfehlung steht eine Zeile „Gelesen: …“.
3. Erst lesen, dann fragen: Vor jeder Grilling-Runde liest ein Subagent alle berührten Everlast-Dateien und liefert Zitate mit Fundstelle.
4. Der Codex-Review-Auftrag enthält den festen Punkt „jede Aussage über Everlast gegen die Datei prüfen“. Ein falscher Beleg ist ein Befund der Klasse Fehler.
5. Everlast ist Referenz, nicht Grenze: Neue Bausteine sind erwünscht, wenn es einen heutigen Fall gibt, gekennzeichnet mit
   „neu, nicht Everlast“ und erst nach der Prüfung, dass kein gelesener Everlast-Baustein den Fall abdeckt.
6. **Ganzen Zusammenhang lesen (Fixpunkt, 16.11.2026):** Vor jeder Empfehlung zu einem Everlast-Baustein werden alle Vorkommen eines
   Begriffs, Felds oder Status im ganzen Workspace gelesen (Skills mit `assets/` und `references/`, Rules, Agenten, Commands,
   Steuerstand-Code), nicht nur die erste Fundstelle. Dazu gehört seine Rolle in der Gesamtarchitektur: wer schreibt, wer liest, welcher
   Ablauf. Erst dann wird empfohlen. Anlass: `entwurf`, stub/Freigabe, Prime-Leselisten und Cleanup-Kern zeigten ihre Bedeutung erst
   nach mehrfacher Nachfrage.

### X2 Neue Anforderungen von Markus (Bau P7)
- **Workspace-Handbuch im Steuerstand:** ein Nachschlagewerk für alle Prozesse und Logiken (Wissen, Quellen und Belege, Pipelines, Projekte,
  Inbox und Briefe, Learnings und Memory, Cleanup, Everlast-Abgleich, Challenge, Personas-Ebenen, Freigabe und Fortschritt …).
  - **Korrektur (Codex #11):** Die Aussage „Everlast hat so etwas nicht“ war falsch. Der Steuerstand hat das „Agentic Marketing Playbook“
    (EL `steuerstand/build.ts:6022-6036`) mit Kapiteln wie „Wer führt“, „Die Regeln“ (Rules, Commands) und „Die Arbeit“ (Pipelines,
    Projekte) (`build.ts:5763-5885`).
  - Das Handbuch ist deshalb **dieses Playbook, übernommen und um die Tegards-Kapitel ergänzt** (Faktenweg, Quellen, Prüfungen,
    Learnings/Memory, Personas-Ebenen, Everlast-Abgleich …). Es ist kein neuer Baustein.
  - Der Inhalt kommt aus den Entscheidungsdateien P1–P9. Wie es gepflegt wird, legt P7 fest.
- **Knopf „Wissen prüfen“** im Bereich „Wissen“ mit Erklärtext (B6).
- **Steuerstand für mehrere Linien** (A7).
- Die Graph-Ansicht steht auf `SPAETER.md` (C3).

### X3 Korrigierte Belege aus den Nebensessions
- Die Aussage „Konflikt-Scan prüft `stammdaten/`, `strategie/`, `produkte/` nie“ ist falsch, richtig ist B6.
- „Steuerstand überspringt agent-memory (`bretter.ts:586`)“: Die Stelle gehört zur Konflikt-Suche, nicht zur Anzeige. Der eigentliche
  Widerspruch ist `struktur.md:77` gegenüber `build.ts` (D1).
- Die Zeilen in `build.ts` sind 3016–3018, nicht 3017–3018.
- „Workspace-Karte nur Dateinamen“ ist falsch (C3).
- „Playbook = nur Reihenfolge der Strategie-Dateien“ ist falsch, es ist ein Workspace-Buch (X2).
- „Everlast zieht stur alle 20 s ein Bild“ ist falsch, der Abstand ist ein Parameter (E3).
- Die Zählungen 38 bzw. 19 Korrekturen, 17 Seiten und 38 Kursblätter sind falsch. Richtig sind 11 korrigierte Prüfstellen, 16 Seiten
  und 37 Blätter (B1, B4, E1).
- `prime-content.md:14` (Nachricht der Nebensession) ist Zeile 13 (C1).
- „`entwurf` nur in der Brand Voice“ war falsch, `entwurf` heißt in 12 Skill-Dateien „noch nicht freigegeben“ (C3).
- „`titel`/`typ` nur in `wissen/`“ war falsch, auch 8 Skill-Vorlagen führen sie (C3).

---

## Weggelassen (→ `SPAETER.md`)
- Teilungsregel Wettbewerberdatei (M-07)
- zweiter Freigeber
- `WISSEN-AUSZUG` für Agenten
- Volltext- und semantische Suche (M-06)
- Graph-Ansicht im Steuerstand, mit frei benannten Kanten (Codex #18)
- Update-Hinweis zu neuen Everlast-Versionen per Inbox-Brief (Codex #19)
- Veraltungs-Skript für Synthesen
- Memory-Anzeige im Steuerstand
- Debrief-Command (M-08)
- Extrakt für Sonderformate (W-11 bis W-15)
- Komfort der Prüfseite (W-18)

Nicht auf SPAETER, weil verworfen oder erledigt: Python-Paketstack, Rechercheur-Agent (M-05), `log.md` und `pruefungen.md`, `kern.md`-Import,
`wiki-pruefen`, OKF-Frontmatter, Status-Leiter mit `verified`, Everlast-Abgleich auf Knopfdruck, adaptive Keyframes (Szenenwechsel). Bewusst als Grundregel und nicht auf SPAETER: Lesen über Workspace-Grenzen (A6).

---

## Offene Punkte nach Thema

- **P3:**
  - SERP-Analysen (A9).
  - SEO/GEO-Dateien aus `marketing-wissen` (F2).
- **P4:**
  - Redaktionsstil und Content-Inventar aus `marketing-wissen` (F2).
  - Welche Learnings-Dateien je Fach es gibt (D2).
- **P6:**
  - Agent-Memory nicht in die Rechner-Übertragung (D1).
  - Abhängigkeiten ffmpeg, yt-dlp, uv, faster-whisper und CUDA in die Rechner-Übertragungsliste (E3).
- **P7:**
  - **Werkzeuge und Prüfungen:**
    - Extrakt-Skript, Prüfseite und Pre-Commit bauen (B1), dazu W-21 („KI bestätigt“ nur gegen die PDF-Textebene) und W-32
      (mehrzeilige Belege).
    - Freigabe-Ausnahme für belegpflichtige Werte in der Git-Rule, egal in welcher Datei (B2).
    - `tg-wissen-pruefen` mit Fristen-Referenz (`profil_geprueft_am`, vorerst 6 Monate), Inbox-Brief und Kopplung an die Verdichtung (B6, C3).
    - Abgleich `--tief` in `tg-konflikt-scan/SKILL.md` korrigieren (B6).
  - **Felder und Leselisten:**
    - Wie Seitenanker (B3) und Everlasts `source` zusammengehen (C3).
    - `fakten.md` in die produktbezogenen `prime-<fach>`-Listen, Persona B in `prime-content`, Dateizahl im Text anpassen;
      Learnings-Leseregel in den Abschnitt „Context“ der Agenten (C1).
    - Ort des Kopf-Felds `oberkategorie` (A7).
  - **Steuerstand:**
    - für mehrere Linien (A7), Knopf „Wissen prüfen“ mit Erklärtext (B6), Handbuch (X2).
  - **Agenten und Memory:**
    - Destillat-Sätze an den sechs Stellen umformulieren, Zielort Voice/Design klären, `struktur.md:77` korrigieren (D1).
  - **Ports:**
    - `workspace-cleanup` (`osascript`), Ziel `projekte/kern/` mit Ausschluss aus dem Löschziel, Prüfpunkt `web/` (E2).
    - `tg-skill-aus-material` (Transkription, Abfrage des Bildabstands je Video, Test an deutschem Video) (E3).
- **P8:**
  - 12 Quellen überführen, Terrawin neu einpflegen (F1).
  - 9 Linien nach Vorlage anlegen, Personas A/B/C (A7/A8).
  - `fakten.md` je Linie nach Weg 1 neu entwerfen.
  - Inhalt von `kern.md` nach `stammdaten/unternehmen.md` (C2).
- **P9:**
  - Challenge-Details (E1).
  - Backlog und Pipeline für Absichten (A5).
  - `learn` gegen `video-wissen` abgeglichen: entschieden in E3, Inventurzeile nachziehen.
  - Den manuellen Everlast-Abgleich mit der Inventur verbinden (E1).
