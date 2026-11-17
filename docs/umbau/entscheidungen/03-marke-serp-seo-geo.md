# Entscheidungen P3: Marke, Suche, SEO und GEO

Stand 17.11.2026 · Grilling abgeschlossen (Q1–Q16), Codex-Review (gpt-6-astra, xhigh, 10 Befunde: 9 Fehler, 1 „Begründung trägt
nicht“) eingearbeitet, Befund 2 und die Lage des Schluss-Schritts (X1) von Markus entschieden · Grundlage: `docs/umbau/dossiers/03-marke-serp-seo-geo.md`
(es gilt Abschnitt 8 in der spätesten Fassung) und `docs/umbau/dossiers/03-lesen/grilling-protokoll.md`.
Elf Entscheidungen fielen in Abzweigungen (btw) und wurden auf Markus' ausdrücklichen Auftrag übertragen; Markus hat die Zusammenfassung
am 17.11.2026 bestätigt. Diese Datei führt nur die geltende Fassung, keine Entstehungsgeschichte.

Kürzel: EL = `E:\Everlast Learning\marketing-workspace-0.5.0\` · ELS = EL `.claude\skills\` · CO = `E:\commerce-os\`.
Die Everlast- und CO-Fundstellen in dieser Datei sind am 17.11.2026 in dieser Session nachgelesen; „nicht gelesen“ steht ausdrücklich dabei.
Verweise wie „Dossier T40“ oder „R6“ zeigen auf Tegards-Fakten und Recherche im Dossier und sind hier nicht neu geprüft.

Leitsatz: **Die Marke setzt, die Suche entscheidet über Seite und Themen, beide treffen sich im Sektionsplan.**
Was bei Everlast funktioniert, kommt mit und wird nur auf den Shop angepasst.

---

## Teil A: Grundsätze

### A1 Arbeitsteilung Marke und Suche (Q1)
- **Ergebnis:**
  - Die Marke setzt Verkaufsargumente, Personas, Ton, Themenfelder, Verbote und Fakten.
  - Die Suche entscheidet, ob eine Seite entsteht, welche Seitenart, welche Pflichtthemen und Fragen, welcher Wortlaut.
  - Verkaufsargumente und Fakten kommen nie aus den Suchergebnissen. Ein Argument, das Wettbewerber führen und wir belegen könnten,
    ist ein Vorschlag für die USPs. Es gilt erst nach Markus' Freigabe und dann für alle Seiten der Linie.
  - Das gilt für alle Seitenarten: Landingpage, Kategorie, Produkt, Ratgeber, Anleitung, Projekt.
  - **Rangfolge bei Konflikt:** Fakten, Recht und Verbote, dann die Marke, dann die Suche. Das Design bestimmt nur die Form.
    Die Suche bestimmt, worüber die Seite spricht; Marke und Fakten bestimmen, was sie dazu sagt.
  - Die „Positionierungsdatei je Linie“ sind die Everlast-Dateien `positionierung.md`, `usps.md` und `produkte/<linie>/offer.md`.
    Eine zusätzliche Datei entsteht nicht.
- **Begründung:** Beide Systeme haben keine feste Stelle, an der Marke und Suche zusammenkommen (Dossier L3). Bei Everlast sieht keiner
  der sechs Schritte des Sektionsplans Suchergebnisse an (ELS `amm-sektionsplan/SKILL.md:28-33`). Bei Tegards entstehen die
  Verkaufsargumente je Lauf neu aus den Suchergebnissen (Dossier T20).
- **Verworfen:**
  - Everlast pur (die Suche bestimmt nur Thema und Format): Verkaufsseiten entstehen ohne Pflichtthemen aus der Suche.
  - Tegards pur („zuerst die ranking-optimale Variante“, Dossier T1, T2): Argumente wechseln je Lauf; die Regel entfällt.

### A2 Everlast zuerst, Anpassung nur für den Shop (Q15, Grundsatz von Markus)
- **Ergebnis:** Was bei Everlast funktioniert, kommt mit und wird nur auf die Besonderheit Shopsystem angepasst. Kein Umbau ohne Not.
- **Folge:** Zwei Bausteine, die das Dossier weglassen wollte, kommen mit (F1).

### A3 Agenten-Regel gelockert (zu Q9; ändert eine feste Entscheidung in `STAND.md`)
- **Ergebnis:**
  - Die Zahl der Fachagenten ist nicht auf die sechs von Everlast begrenzt (EL `.claude/agents/`: sechs Agentendateien).
    Ein weiterer Fachagent darf vorgeschlagen werden, wenn er Sinn ergibt. Nichts Unnötiges, nichts, was verkompliziert.
  - Maßstab bleibt Everlasts eigene Regel: Ein neuer Spezialist braucht eigenes Handwerk, eigene Werkzeuge und eine scharfe Grenze,
    Bedienwissen wohnt im Skill (EL `.claude/head-of-marketing.md:105-106`).
  - Für die Suchergebnis-Analyse wird **kein** neuer Fachagent vorgeschlagen (B5).
- **Weggelassen:** eigener Fachagent für die Suchergebnis-Analyse → `SPAETER.md`.

### A4 Begriffe (Q7, Q13)
- **Ergebnis:**
  - **Säule:** Themenfeld der Marke, das Feld `pillar` (B6).
  - **Landingpage:** eine Seitenart.
  - **Leitseite:** die Rolle der Hauptseite einer Produktlinie. Meist ist das eine Landingpage, bei kleinen Linien die Kategorieseite (B3).
  - **Hauptbegriff und Unterfragen:** ein Keyword-Cluster.
  - **`zielseite` und `shop-seite`:** Rollen von Kategorie- und Produktseiten (B3).
  - **Seitenarten:** Landingpage, Kategorieseite, Produktseite, Ratgeber, Anleitung, Projekt.
- **Begründung:** „Pillar“ hatte drei Bedeutungen (Dossier L11). Everlast verwendet „Leitseite“ nicht (Suche nach „leitseite“ in allen
  `.md`-, `.ts`- und `.py`-Dateien von EL: kein Treffer). „Landingpage“ ist dort kein fester Begriff für eine Seitenart
  (Codex #1): Das Swipefile-Fach `landingpages/` nimmt nur Optin-Seiten gegen E-Mail-Adresse auf
  (EL `swipefile/landingpages/README.md:15-16`, Etikett `steuerstand/build.ts:1560`), die Copywriting-Referenz führt unter
  „Landingpage-Sektionstypen“ auch Preis-Anker und Garantie (ELS `amm-copywriting/references/formeln-und-sektionen.md:70`, `:91`),
  und der Steuerstand kennt ein Projektfeld `landingpage:` (`build.ts:2194-2197`).

---

## Teil B: Suchwissen

### B1 Suchdaten: Search Console, DataForSEO, Suggest (Q2)
- **Ergebnis:**
  - **Search Console** für die eigenen Rankings (gemessen). tegards.com ist dort bestätigt (Auskunft Markus).
  - **Suggest-Abfrage** (kostenlos) für Wortlaute.
  - **DataForSEO** über Everlasts Werkzeug `dfs` für zwei Aufgaben:
    1. Seite eins automatisch und unter festen Bedingungen, für Österreich und Deutschland, mit KI-Übersicht, wiederholbar und
       über die Zeit vergleichbar (`dfs serp`).
    2. Unbekannte Begriffe der Wettbewerber finden (`dfs ranked`, `competitors`, `gap`). Diese Werte sind geschätzt, nicht gemessen.
  - **Suchvolumen** kann auch der Keyword-Planer liefern, weil Google Ads läuft. DataForSEO spart dabei nur die Handarbeit.
  - **Sprachregel:** Ein absolut richtiges Ranking gibt es nicht. Der Gewinn ist Vergleichbarkeit, nicht Wahrheit.
  - **Kostendeckel je DataForSEO-Lauf:** ja. Ist die Obergrenze erreicht, bricht der Lauf ab und meldet das. Zweck ist der Schutz
    gegen Fehlläufe, kein Sparen. Die Höhe legt P7 fest, sobald die echten Kosten für die eigene Domain bekannt sind.
  - **Konten:** Das DataForSEO-Konto legt Markus an und trägt die Zugangsdaten selbst ein (P8).
- **Begründung:** Die Suchergebnis-Analyse und die beiden Loops sollen ohne Markus laufen; die Websuche des Agenten ist nicht Google.
  Tegards hat heute keine gemessenen Suchdaten (Dossier L6).
- **Beleg:** EL `tools/dataforseo/README.md:10` (`serp`, auch die KI-Übersicht), `:11-14` (`ranked`, `competitors`, `gap`),
  `:20` (geschätzt, nicht gemessen), `:21` (`ai_overview`). Kosten: „0,59 USD“ für ein vollständiges Keyword-Audit einer Domain am
  23.09.2026 (`:18`), also je Audit, nicht je Suchbegriff; rund 0,60 USD auch in ELS `amm-keyword-research/SKILL.md:33` und
  EL `tools/seo-voraussetzungen.py:110`. Das ist ein Messwert von Everlast, bei DataForSEO nicht nachgeprüft.
- **Für den Bau (P7):** `dfs` kennt Österreich (`LAND`-Tabelle mit `AT`, EL `tools/dataforseo/dfs:41`), der Standard ist aber
  `--land DE` (`:507`), und `seo-voraussetzungen.py:134` gibt „DE, de“ fest aus. Österreich muss ausdrücklich dazu.
- **Verworfen:** nur kostenlose Quellen. Ihnen fehlt der automatische, vergleichbare Abruf von Seite eins für Österreich und
  Deutschland samt KI-Übersicht. Volumen fehlen nicht, die liefert der Keyword-Planer (Codex #2, von Markus so entschieden).
- **Nicht geprüft:** Andere Anbieter (SerpApi, Serper, Ahrefs, Semrush, Sistrix) wurden nicht recherchiert. Es bleibt bei DataForSEO,
  weil `dfs` dafür fertig ist. Ob `dfs` und `gsc` unter Windows laufen, klärt P7.
- **Weggelassen:** GEO-Tracker (Peec AI, Profound, Otterly oder ähnlich) → `SPAETER.md`.

### B2 Ein Keyword-Set mit Abschnitt je Linie (Q3)
- **Ergebnis:**
  - Ort: `strategie/positionierung/keyword-set.md`, eine Datei mit einem Abschnitt je Linie.
  - Je Zeile: Suchbegriff, Absicht, Zielseite (genau eine), Status, Volumen, Herkunft (gemessen, geschätzt, angenommen) mit Datum.
  - Der Themenplan der Linie (B3) liegt im Abschnitt der Linie.
  - `suchverhalten.md` bleibt eine Datei auf Markenebene.
  - Der Ist-Bestand der Seiten steht im Abschnitt „Bestand“ von `kanaele/websites.md`.
  - Der Stub `seo/keyword-set.md` entfällt; alle Leser zeigen auf den einen Ort.
- **Begründung:** Ein Ort, Kannibalisierung über alle Linien prüfbar, Herkunft und Datum je Zeile.
- **Beleg:** Der Keyword-Skill schreibt nach `strategie/positionierung/keyword-set.md` (ELS `amm-keyword-research/SKILL.md:54`),
  das Prüfskript sucht dort (EL `tools/seo-voraussetzungen.py:73`), und `/seo-komplett-audit` darf außerhalb von `daten/` und `inbox/`
  nur in `strategie/positionierung/` ändern (EL `.claude/commands/seo-komplett-audit.md:86`). Der Wochen-Loop liest das Keyword-Set
  dort und den Abschnitt Bestand in `kanaele/websites.md` (EL `tools/seo-audit/auftrag.md:23-24`).
- **Befund Everlast:** Zwei Pfade für dieselbe Datei. `amm-seo-content` (`SKILL.md:25`, `:66`), `amm-video-zu-blog` (`SKILL.md:79`)
  und die geplante Aufgabe (EL `seo/geplante-aufgaben/seo-neue-seite.md:7`) lesen `seo/keyword-set.md`. Beim Übernehmen korrigieren (P7).
- **Verworfen:** Tegards-Landkarte und Architekturdatei (keine Volumen, kein Datum); je Linie eine eigene Keyword-Datei
  (Kollisionen zwischen Linien sieht niemand).

### B3 Themenplan je Linie, Seitenwahl ohne Zahlenregel (neu, nicht Everlast; Q4)
Heutiger Fall: 21 geplante Lamellendach-Zeilen ohne Seite und der offene Konflikt Landingpage gegen Kategorie (Dossier T40, T41).
- **Ergebnis:**
  - Bevor für eine Linie Seiten gebaut werden, entsteht ein Themenplan als Vorschlag mit Begründung. Schritte: Bestand lesen
    (Sitemap, veröffentlichte Artikel, Projekte, Kategorien), Nachfrage erheben, Suchergebnisse je Kernbegriff ansehen,
    Verteilung vorschlagen.
  - Der Plan sagt je Frage oder Suchbegriff: Form (eigene Seite, Abschnitt, Frage im Fragenblock), Zielseite, ob es sie schon gibt,
    worauf sie verlinkt, und warum.
  - **Regeln:**
    - Eine eigene Seite gibt es nur bei eigenen Suchergebnissen (andere Treffer oder andere Seitenart als beim Hauptbegriff).
      Sonst wird es ein Abschnitt oder eine Frage auf einer bestehenden Seite.
    - Ob eine Linie eine eigene Landingpage bekommt oder die Kategorieseite die Leitseite ist, entscheidet der Themenplan aus den
      Suchergebnissen zum Kernbegriff (welche Seitenart dort vorne steht).
    - Jede neue Seite nennt ihr Linkziel und eine bestehende Seite, die auf sie verlinkt.
    - Bestand wird erweitert, nicht verdoppelt.
  - Markus gibt den Themenplan frei, erst danach entstehen Sektionspläne und Seiten.
  - Der Themenplan ist der Abschluss der Keyword-Recherche einer Linie, kein eigener Agent und kein eigener Skill.
  - **Zwei kurze Regeln im Keyword-Skill** (aus commerce-os übernommen):
    - Rollen: `zielseite` (eigener Suchbegriff, ausführlicher Text) und `shop-seite` (kein eigener Suchbegriff, kurzer Text).
      Daran hängt die Tiefe der Analyse (B5).
    - Familien-Regel: Varianten aus dem Konfigurator sind nie eigene Zielseiten. Zielseite ist die Kategorie oder der Haupttext
      der Produktfamilie.
  - Everlasts Regel „Die Absicht entscheidet die Seitenform, nicht das Suchvolumen“ bleibt. Die Tabelle dort wird um Kategorie- und
    Produktseite ergänzt.
- **Begründung:** Beide Systeme haben für die Verteilung von Themen auf Seiten nur Bruchstücke. Die Schwellen des alten
  Entscheidungsbaums sind bei einer neuen Linie geraten: Es gibt dort noch keine Projekte, und gemessen wurden die Zahlen nie.
- **Beleg:** ELS `amm-keyword-research/references/cluster.md:22` (Regel), `:15-20` (Tabelle mit Glossar oder Ratgeber,
  Vergleichsseite, Angebotsseite, eigene Seite). CO `references/zielseiten-entscheidungsbaum.md:33-35` (Rollen), `:45-46`
  (Familien-Regel), `:11-13` (Schwellen).
- **Verworfen:** der Entscheidungsbaum aus commerce-os mit den Schwellen „mindestens drei Blog-Themen, mindestens zwei Projekte
  im Jahr“.

### B4 Produktlinien: ein Regelwerk, Daten je Linie (Q12)
- **Ergebnis:**
  1. Ein Regelwerk für alle Linien. Unterschiedlich sind nur die Daten: Abschnitt im Keyword-Set, Themenplan, `fakten.md`, Persona,
     Angebot, Wettbewerb.
  2. Die Bestandsaufnahme der Domain läuft einmal am Anfang für alle Linien, je einmal für Österreich und Deutschland.
  3. Themenplan und Linien-Analyse entstehen je Linie erst, wenn dort Seiten gebaut werden. Suchwissen entsteht nicht auf Vorrat.
  4. Reihenfolge: Glasschiebewände, dann Verdeca, dann Lamellendächer.
- **Begründung:** Heute verlangt kein Fall eigene Regeln je Linie (Dossier T43). Glasschiebewände Deluxe und Verdeca werden ohnehin
  neu gebaut (C4).
- **Verworfen:** eigene Regeln je Linie in den Skills; alles nur auf Markenebene (sieben von neun Linien haben kein Suchwissen,
  Dossier L8).
- **Hinweis:** Q12 steht nur im Grilling-Protokoll, nicht im Dossier.

### B5 Suchergebnis-Analyse: ein Skill, zwei Ebenen (neu, nicht Everlast; Q9)
Heutiger Fall: Neubau der Seiten Glasschiebewände Deluxe und Verdeca (C4), geplante Leitseite Lamellendächer.
- **Ergebnis:**
  - **Form:** ein Skill `tg-serp-analyse`, den der planende Agent lädt. Kein neuer Agent. Die Linien-Ebene liest viel, aber selten;
    der planende Agent kann sie als Unterauftrag auslagern.
  - **Ebene Linie**, beim Themenplan: bei zwei bis drei Top-Wettbewerbern den Unterbau lesen, also Leitseite, stützende Seiten
    (Ratgeber, Projekte, Kategorien), interne Links und die Verteilung des Themas über die Domain.
  - **Ebene Seite**, vor jedem Sektionsplan: Verteilung der Seitenarten, Suchabsicht, Pflichtthemen (Fragen, die alle Top-Treffer
    beantworten), „Ähnliche Fragen“, KI-Übersicht ja oder nein mit zitierten Domains, erwarteter Marktstandard; dazu zwei bis drei
    Top-Seiten genau lesen. Jeder Rankinggrund ist eine Hypothese.
  - **Tiefe der Seiten-Ebene:** voll bei Seiten mit eigenem Suchbegriff (Leitseite, Kategorie- und Produktseite als `zielseite`),
    kurz bei Ratgeber, Anleitung und Projekt, keine bei Shop-Seiten ohne eigenen Suchbegriff.
  - **Was der Skill nicht liefert:** eine Gliederung zum Nachbauen, das Markup der Wettbewerber, Verkaufsargumente oder Fakten (A1).
  - **Vier Abnehmer je Analyse:** der Sektionsplan der Seite (einmalig), die Wettbewerberdatei als datierte Beobachtung
    (`strategie/umwelt/wettbewerber/<name>.md`, P2 A9), das Keyword-Set der Linie, Vorschläge an die Marke (A1).
  - **Nachlauf:** Jede Analyse endet mit drei bis fünf Zeilen Destillat, was dauerhaft ins Wissen gehört. Der Head pflegt ein,
    nie der Agent.
  - **Ablage:** jeder Lauf datiert unter `daten/JJMMTT-serp-<slug>/`. Kein Wissensfach.
  - **Wiederverwendung Seiten-Ebene:** bis 30 Tage für denselben Suchbegriff und Markt (Hausregel). Der Teil zur KI-Übersicht wird
    nie wiederverwendet (Dossier R5).
  - **Wiederholung Linien-Ebene:** kein Kalendertermin, sondern ein Auslöser mit Obergrenze.
    - Auslöser: Bei einem Kernbegriff der Linie kommt eine neue Domain unter die ersten fünf, oder die eigene Seite rutscht deutlich
      ab. Dann nur für diesen Wettbewerber.
    - Wer es bemerkt: das Komplett-Audit (E2) über den Vergleich von `dfs serp` mit dem letzten abgelegten Lauf, später der
      wöchentliche Loop (E3).
    - Obergrenze: spätestens nach sechs Monaten neu, auch ohne Auslöser (Hausregel).
    - Ergebnis: Beobachtung in der Wettbewerberdatei und ein Vorschlag für den Themenplan; umgesetzt wird erst nach Markus' Freigabe.
- **Begründung:**
  - Markus: Eine Seite rankt als Teil eines Gesamtkonstrukts der Domain. Das ist fachliche Einschätzung, in der Recherche nicht
    eigens belegt.
  - Beide Systeme bewahren die Analyse einer Seite nicht auf (Dossier L2). Mit der datierten Ablage wird ein Vergleich über die
    Zeit möglich.
- **Beleg:** Head pflegt die Wissensdateien, der Agent liefert drei bis fünf Zeilen Destillat (EL `.claude/head-of-marketing.md:47-49`).
  Ein neuer Datumsordner je Lauf, der alte bleibt als Vergleich (ELS `amm-seo/references/befund-format.md:13`). Die 30 Tage und
  die sechs Monate sind Hausregeln ohne Vorbild bei Everlast (Codex #3).
- **Verworfen:**
  - keine Analyse (Everlast): Verkaufsseiten ohne Pflichtthemen aus der Suche.
  - die Tegards-Agenten `serp-analyst` und `wettbewerbs-analyst`: allgemeine Websuche statt echter Seite eins, und die
    Suchergebnis-Analyse wird nie abgelegt (Dossier T12), ein Vergleich über die Zeit fehlt. Einen Ablageweg hat dort nur das
    Wettbewerbs-Dossier (CO `references/landingpage/pruefung-und-ablage.md:86-95`; Codex #4); den übernimmt die Wettbewerberdatei
    als Abnehmer.
  - Tegards' Regel „nie wiederverwenden“.
- **Weggelassen:** Backlink-Analyse der Wettbewerber → `SPAETER.md`. Das Werkzeug ist vorhanden: `dfs backlinks`
  (EL `tools/dataforseo/dfs:12`, `:462`, `:558`; `tools/README.md:41`).

### B6 Säulen (Q7)
- **Ergebnis:**
  - Säulen sind Themenfelder der Marke quer zu den Produktlinien, gebaut nach Everlast. Jedes Stück trägt zwei Etiketten: `pillar`
    für das Themenfeld und das Zusatzfeld `produktlinien` (P2 C3) für die Linie.
  - Entstehung wie bei Everlast: Der Agent schlägt Säulen aus den Workspace-Dateien vor, nicht aus Branchenwissen. Jede besteht die
    Prüffragen. Höchstens fünf. Markus gibt frei.
  - Änderbar mit Bremse: 90 Tage ohne Stück ist ein Befund „stärken oder streichen“; Umbenennen nur nach Rückfrage.
  - Welche Säulen es werden, ergibt Station 15 im Onboarding (P8). Die Beispiele `montage`, `planung`, `vergleich`, `projekte` aus
    dem Grilling sind nicht entschieden.
- **Beleg:** ELS `amm-content-strategie/references/saeulen.md:17` (Themenfeld), `:19` (höchstens fünf), `:26-35` (Quellen in fester
  Reihenfolge, nicht aus Branchenwissen), `:41-48` (Prüffragen), `:56` (Slug aus Kleinbuchstaben), `:59` (Umbenennen nur nach
  Rückfrage), `:87` (90 Tage), `:96` (Status wechselt erst nach Freigabe).
- **Verworfen:** Säule = Produktlinie (neun Linien, höchstens fünf Säulen).

---

## Teil C: Seitenaufbau

### C1 Der Sektionsplan ist der Treffpunkt (Q10)
- **Ergebnis:**
  - Seiten entstehen aus den festen Content-Bausteinen des Designsystems, damit das Erscheinungsbild einheitlich bleibt.
  - Welche Bausteine auf eine Seite kommen und in welcher Folge, ist beweglich. Kriterien: Everlasts Logik (eine Sektion räumt eine
    Kaufbremse weg; Streich-, Doppel- und Kettentest) und was die Top-Konkurrenz auf ihren Seiten hat. Der Sektionsplan darf mit
    Begründung streichen, umstellen und ergänzen.
  - **Abgleich mit der Suche:** Jedes Pflichtthema aus der Analyse (B5) bekommt im Sektionsplan eine Zeile: erfüllt durch Sektion X,
    im Fragenblock beantwortet, oder bewusst nicht, mit Grund.
  - **Freigabe vor dem Text:** Der Sektionsplan ist das Seitenkonzept. Markus gibt ihn frei, bevor Text entsteht.
  - **Zahlen:** Es gibt keine Zahlenvorgaben für Fragen, Zeichen oder Wörter (D1; Codex #5). Die Wortzahlen in Everlasts
    Baustein-Repertoire sind dort selbst „Größenordnung, nicht Vorgabe“ (ELS `amm-sektionsplan/references/bremsen-und-bausteine.md:41`).
  - **commerce-os-Templates entfallen** als Pflichtfolge und als zweite Quelle. Es bleiben:
    - der Technik-Baustein, er kommt in den Vorrat des Sektionsplan-Skills;
    - „Antwort zuerst“ als GEO-Regel für jede Seite, ohne feste Satzzahl (D1);
    - der Meta-Block (Titel, Beschreibung, URL) als Schluss-Schritt im SEO-Skill (F1).
    „Problem und Lösung je Persona“ entfällt als eigenes Modul.
  - **Baustein-Vorschlag ans Designsystem:** Braucht eine Sektion einen Baustein, den es nicht gibt, steht im Sektionsplan ein
    Vorschlag: was er leisten soll, welche Bremse oder welches Pflichtthema er deckt, auf welcher Seite. Markus entscheidet (bauen
    lassen oder mit vorhandenem Baustein lösen). Bis dahin nimmt der Entwurf den nächstbesten Baustein und markiert die Stelle.
    Kein eigenes Layout am Designsystem vorbei. Einzige Ausnahme: C2.
  - **Shop (Richtigstellung von Markus):** WooCommerce gibt bei Produkt- und Kategorieseiten nicht das Gerüst vor. Bei Produktseiten
    nimmt ein freies HTML-Element unter der Produktbeschreibung alles auf, was die Seite zum Ranken braucht. Bei Kategorieseiten mit
    der Rolle `zielseite` gilt dasselbe unterhalb der Produktliste.
- **Begründung:** Der Seitenaufbau hatte auf beiden Seiten mehrere unverbundene Quellen (Dossier L4). Jetzt gibt es einen Ort, an dem
  Marke, Suche und Fakten zusammenkommen.
- **Beleg:** Eine Sektion räumt genau eine Bremse weg (ELS `amm-sektionsplan/SKILL.md:41-42`); die drei Tests (`:55-59`), der
  Kettentest zeigt, wo eine Sektion fehlt (`:59`); der Plan ist eine Tabelle für den `webdesigner` (`:62-72`). Das Repertoire
  (ELS `amm-sektionsplan/references/bremsen-und-bausteine.md:43-60`) hat keinen Technik-Baustein und führt ein Zielgruppen-Raster
  (`:49`). CO `templates/landingpage.md:248-251` (Technik-Modul), `:102-106` (Answer-First-Block); vom Template sind nur diese
  Zeilen gelesen.
- **Verworfen:** festes Template je Seitenart mit Pflichtfolge (commerce-os); Sektionsplan ohne Blick auf die Suche (Everlast pur).
- **Nicht geprüft:** Markus' Angabe einer SEO-Regel zur Höchstzahl der Wörter oberhalb der Produktliste (an P4). Dass der
  Technik-Baustein „Kein Vertrauen“ und „Zu viel Risiko“ wegräumt, ist Deutung.

### C2 Leitseite: zwei freie Varianten
- **Ergebnis:**
  - Bei der Leitseite entstehen genau zwei Varianten, beide frei aus Kaufbremsen und Suchergebnis-Analyse, je mit eigener
    Leithypothese. Es gibt keine Startfolge.
  - Eine der zwei Varianten darf über das Designsystem hinausgehen und neue Bausteine und eigenes Layout zeigen. Wählt Markus sie,
    werden die neuen Bausteine ins Designsystem aufgenommen. Farben, Schrift und Ton der Marke gelten in jeder Variante.
  - Bei allen anderen Seiten gibt es Varianten nur auf Zuruf.
- **Beleg:** Everlasts Varianten-Lauf hat drei Varianten auf drei Branches, je ein Agent mit eigener Leithypothese
  (EL `.claude/head-of-marketing.md:53-54`). Zwei statt drei ist eine Anpassung.
- **Verworfen:** eine dritte, frei kreative Variante; Varianten mit festen Annahmen („Startfolge angepasst“, „frei nach Everlast“).
- **Weggelassen:** nur noch ein Modus statt zwei Varianten → `SPAETER.md`.
- **Nicht belegt:** Dass der freie Neubau besser verkauft als die Überarbeitung des Bestands, ist fachliche Deutung, nicht gemessen.
  C4 fängt die Verluste auf.

### C3 Ein Gerüst je übriger Seitenart, neu hergeleitet
- **Ergebnis:**
  - Für Kategorie, Produkt, Ratgeber, Anleitung und Projekt gibt es je ein Gerüst. Der Sektionsplan weicht mit Begründung davon ab.
  - Jedes Gerüst wird einmal neu hergeleitet, aus drei Quellen: Everlasts Logik (Kaufbremsen bei Kategorie und Produkt, Baupläne bei
    Ratgeber und Anleitung), was die Suchergebnisse für die Seitenart zeigen, und der Bestand als Inhalt.
  - Jedes Gerüst hat zwei feste Stellen: den Link zur Leitseite der Linie und einen nächsten Schritt Richtung Kauf oder Anfrage.
    Welche Seite worauf verlinkt, steht im Themenplan (B3).
  - Für Ratgeber und Anleitung ist Hornbach („Projekte“) das Vorbild für Aufbau, Bausteine und Sprachstil. Übernommen wird die
    Machart, nie Text oder Bild.
  - Die Herleitung ist Arbeit für P4. P3 legt nur die Regel fest. Bis dahin gibt es für diese Seitenarten keine fertige Ausgangsfolge.
- **Beleg:** Der Sektionsplan kennt vier Seitentypen (Anmeldeseite, Sales-Page, Kursseite, Produktseite; ELS
  `amm-sektionsplan/SKILL.md:28`); eine Kategorieseite ist nicht dabei. `amm-blog` führt sechs Formate (ELS `amm-blog/SKILL.md:5-6`).
- **Verworfen:** die Folge aus `E:\TG Design\ausgelagert\seitenvorlagen.md` als Startfolge (C4).
- **Grundlage für P4:** Der Hornbach-Abgleich liegt vor (`dossiers/03-lesen/hornbach-blogaufbau.md`, Stand 16.11.2026): sechs
  Seiten mit Firecrawl gelesen, Abgleichtabelle Hornbach-Baustein gegen eigenen Baustein ausgefüllt. Offen sind dort nur die
  Punkte im Abschnitt „Was nicht prüfbar war“ (Optik, Video, Bildzahlen). Handoff und Grilling-Protokoll nennen die Datei noch
  „leer“; das ist überholt (Codex #6).

### C4 Bestand ist Quelle, keine Vorlage
- **Ergebnis:**
  - Die Einträge in `E:\TG Design\ausgelagert\seitenvorlagen.md` beschreiben den heutigen Stand bestehender Seiten. Sie sind
    Inhaltsquelle und Beispiel, kein Muster. Das gilt für alle Seitenarten.
  - Die Seiten Glasschiebewände Deluxe und Verdeca entstehen komplett neu nach dem neuen Ablauf (Themenplan, Suchergebnis-Analyse,
    Sektionsplan mit Abgleichzeile, Freigabe, dann Text und Bilder).
  - Vor dem Neubau einer bestehenden Seite:
    1. **Bewertung des Bestands:** was gut ist, was fehlt, welche Kaufbremsen die Seite wegräumt. Sie endet mit einer Liste „muss
       bleiben“; jede Zeile bekommt im Sektionsplan einen Platz oder eine begründete Streichung.
    2. **Vergleichswert:** Die heutigen Zahlen der Seite werden festgehalten (Search Console, Analytics).
    3. **Adresse und Hauptbegriff** bleiben gleich.
- **Begründung:** Die drei Schritte fangen die drei Verluste eines Neubaus auf: Bewährtes ohne Nachweis, Vergleichswert, Ranking.
- **Beleg (Tegards, nachgelesen):** `seitenvorlagen.md:28-30` (Landingpage, Vorbild Glasschiebewände Deluxe, „wird neu gebaut“),
  `:47-49` (Produkt-Landingpage, Vorbild Verdeca), `:65-67` (Projekt, Vorbild Poolhaus Deutsch Wagram).

### C5 Strukturierte Daten (Q5)
- **Ergebnis:** Markup gibt es nur, wo Google es anzeigt oder das Plugin es ohnehin liefert. Je Schema-Typ gibt es genau eine
  führende Quelle, Plugin oder Skill.

  | Seitenart | Markup | Quelle |
  |---|---|---|
  | Produktseite | `Product` mit `Offer` | WooCommerce und RankMath; Prüfpunkt: variable Produkte geben ein Sammelangebot (`AggregateOffer`) aus (Dossier R11) |
  | Kategorieseite | `CollectionPage`, kein `Product` auf der Liste (Dossier R7) | RankMath |
  | Landingpage | keines über das hinaus, was das Plugin liefert | Plugin |
  | Ratgeber, Anleitung, Projekt | `Article` mit Autor und Datum | Plugin, sonst Vorlage aus `tg-seo` |
  | Startseite | `Organization` | Vorlage aus `tg-seo` |
  | überall | `BreadcrumbList` | Plugin |

  Das sichtbare Fragenmodul bleibt.
- **Begründung:** Das FAQ-Rich-Result erscheint seit dem 07.05.2026 nicht mehr (Dossier R6). Strukturierte Daten bringen keinen
  belegten Vorteil bei KI-Zitaten (Dossier R3). Everlast sagt dasselbe: „`FAQPage` bringt kein Extra“, der Fragenblock bleibt als
  sichtbarer Text (ELS `amm-seo/references/schema-vorlagen.md:161`).
- **Beleg:** Everlasts Schema-Vorlagen sind für einen Kursanbieter geschrieben (`schema-vorlagen.md:3`, `:9`: Organization,
  BreadcrumbList, Course, Kursliste, Article, Event). Shop-Typen kommen neu dazu.
- **Verworfen:** die Tegards-Templates 1:1 (enthalten Blöcke ohne belegte Wirkung).
- **Weggelassen:** `FAQPage`, `HowTo`, `speakable`, `Product` ohne Preis → `SPAETER.md`.
- **Nicht geprüft:** R11 (Verhalten von WooCommerce und RankMath) stammt aus dem Recherchebericht und ist nicht an der Quelle
  nachgeprüft; deshalb der Prüfpunkt.

### C6 Bilder (Richtung entschieden, Ausgestaltung P4)
- **Ergebnis:**
  - Aus dem freigegebenen Sektionsplan entsteht eine Bildliste: je Platz Motiv, Zweck, Format und ob ein echtes Foto nötig ist.
  - Stufe 1 (heute): Der Agent schreibt den Bildbedarf in den Brief (`medien.md`, P1). Markus sucht in der TGMB und legt die Dateien
    in den Arbeitsordner des Stücks. Stufe 2 (wenn die TGMB-Schnittstelle fertig ist): Der Agent sucht selbst und schlägt vor.
  - Für Stimmungs- und Erklärbilder darf er über OpenArt generieren: erst ein Testbild, dann wenige Varianten. Echte Produktbilder
    werden nie generiert, dort bleibt eine benannte Lücke (P1 C9).
  - Der Erstentwurf zeigt Bilder, keine leeren Flächen. Markus wählt je Platz.
  - Am Schluss stehen die Dateien fest, jede mit Dateiname, Alt-Text und Bildunterschrift als fertigem Vorschlag.
  - `bildsprache.md` bekommt einen Abschnitt „Belegte Motive“ nach Everlast, damit ein Motiv nicht zwei Bedeutungen trägt.
- **Beleg:** „Belegte Motive“ ist bei Everlast Pflichtlektüre des grafik-designers, mit Kollisionsprüfung vor dem Vorschlagsfeld
  (EL `.claude/agents/grafik-designer.md:43`, `:63`).

---

## Teil D: GEO

GEO heißt hier, in KI-Antworten (Googles KI-Übersicht, ChatGPT, Perplexity) als Quelle genannt zu werden.

### D1 Drei Schreibregeln, keine Zahlenvorgaben (Q14)
- **Ergebnis:**
  - Es gelten drei Regeln: Antwort zuerst; Herkunft einer Angabe im selben Satz; der Text trägt, was Grafik und Markup sagen.
  - Die Zahlenvorgaben beider Seiten entfallen: 134 bis 167 Wörter für den Antwortblock, 300 Zeichen, genau zehn Fragen.
  - `llms.txt` wird nicht gebaut.
- **Begründung:** Google verlangt für KI-Übersichten nichts Zusätzliches und nennt keine ideale Länge (Dossier R1, R8); `llms.txt`
  nutzt die Google-Suche nicht (Dossier R2).
- **Beleg:** Everlast selbst: „nichts Zusätzliches … kein eigenes Schema“ (ELS `amm-seo/references/ki-suche.md:15`); `llms.txt` ist
  „ein offener Vorschlag, kein Standard“ (`:76`). Die Spanne 134 bis 167 Wörter nennt Everlast selbst einen Faustwert ohne
  offengelegte Methode (ELS `amm-seo-content/references/zitierfaehigkeit.md:17-20`). „Antwort zuerst“ ist dort an Googles
  Snippet-Doku verankert (ELS `amm-blog/references/zitierfaehigkeit.md:22-27`).
- **Befund Everlast, beim Übernehmen bereinigen (P7):**
  - Zwei Regeln für den Antwortblock: `amm-seo-content` verlangt 134 bis 167 Wörter (`SKILL.md:34`), ebenso `amm-seo-audit`
    (`references/kriterien.md:13`) und `amm-video-zu-blog` (`SKILL.md:176`; `scripts/pruefe_artikel.py:31` prüft es hart).
    `amm-blog` verlangt höchstens drei Sätze und keine Wortzahl (`references/bauplaene.md:16`, `:20`).
  - `llms.txt`: Entwurf als Ergebnis von Modus K bei `amm-seo` (`SKILL.md:40`), „kein Ranking- oder Zitierhebel“ bei `amm-seo-audit`
    (`SKILL.md:100-101`).

### D2 Prüfung über den Codex-Prüfweg aus P1
- **Ergebnis:** Codex prüft die Inhalte, wie in P1 entschieden. Die GEO-Punkte werden Teil der Inhaltsrubrik je Auftragsart (P1 A1).
  Ein eigener Prüf-Agent (`geo-validator`) kommt nicht. P1 bleibt unverändert, auch der Rückfall ohne Codex (P1 A4).
- **Verworfen:** Prüfung aller Inhalte durch ein anderes Claude-Modell (von Markus erwogen und ausdrücklich zurückgenommen).

### D3 Messung in drei Stufen
- **Ergebnis:**
  1. Laufend und kostenlos: der Bericht zu generativer KI in der Search Console. Er zeigt nur Impressionen (Dossier R9).
  2. Bei jedem Komplett-Audit: `dfs serp` für die zehn wichtigsten Begriffe ohne Markennamen: KI-Übersicht ja oder nein und welche
     Domains sie nennt.
  3. Nur im Komplett-Audit: fünf Testfragen, jede zehnmal gestellt, nach Everlasts Testfragen-Protokoll. Die Testfragen kommen aus
     dem neuen Keyword-Set.
  Die alte Tegards-Messung wird nicht fortgeschrieben.
- **Begründung:** Das Billige läuft immer, das Teure selten. Ein Lauf je Frage trennt „nie“ nicht von „manchmal“ (Dossier L10).
- **Beleg:** Schritt 6 des Komplett-Audits (EL `.claude/commands/seo-komplett-audit.md:56-57`). Testfragen-Protokoll: fünf bis zehn
  Fragen je Audit (ELS `amm-seo/references/ki-suche.md:120`), zehn Läufe je Zeile mit Herleitung (`:123`, `:127-136`). Bei Everlast
  kommen die Fragen aus `suchverhalten.md`; das Keyword-Set als Quelle ist eine Anpassung. Die Search-Console-Berichte zu
  AI Overviews und AI Mode gibt es nur in der Oberfläche (EL `tools/gsc/README.md:64`).

### D4 KI-Crawler
- **Ergebnis:**
  - Welche KI-Crawler die Website zulässt, steht einmal in `kanaele/websites.md`.
  - Suchcrawler und Trainingscrawler werden zugelassen. Eingetragen wird das beim Befüllen von `websites.md` im Onboarding (P8).
- **Begründung (Markus):** Für einen Shop überwiegt, dass die Modelle Marke und Produkte kennen; Produkttexte haben keinen Lizenzwert.
  Das ist Einschätzung, nicht gemessen.
- **Beleg:** Everlast trennt Such- und Trainingscrawler und überlässt die Entscheidung dem Nutzer (ELS
  `amm-seo/references/ki-suche.md:24-38`).
- **Verworfen:** Trainingscrawler sperren (Empfehlung des Dossiers und des alten Tegards-Playbooks).

### D5 Off-Page
- **Ergebnis:**
  - Kein Agent erzeugt Bewertungen, Forenbeiträge oder Fremdnennungen. Das bleibt Handarbeit bei Markus.
  - Neu im Komplett-Audit: ein Prüfpunkt „Links-Bericht aus der Search Console exportieren und auswerten“.
- **Beleg:** „Ein Agent schreibt keine Fremdnennungen herbei“ (ELS `amm-seo-audit/references/kriterien.md:25-26`; Kriterien 9 und 10,
  `:16-17`).
- **Weggelassen:** operative Off-Page-Arbeit durch einen Agenten → `SPAETER.md`.
- **Nicht geprüft:** ob der Links-Bericht nur in der Oberfläche der Search Console verfügbar ist.

---

## Teil E: Frische und Takte

### E1 Ein Ort je Regel, monatlicher Regel-Check (Q6)
- **Ergebnis:**
  1. **Ein Ort je Regel.** SEO- und GEO-Regeln stehen nur in den Referenzen von `tg-seo`, mit Quelle und Abrufdatum in `herkunft.md`.
     Andere Skills verweisen dorthin. Ein Playbook als zweite Regelquelle entsteht nicht. Eine Regel kommt nur hinein, wenn sie
     Primärquelle und Abrufdatum hat.
  2. **Monatlicher Regel-Check (neu, nicht Everlast).** Ein Auftrag mit fester Quellenliste: Googles Änderungsprotokoll der
     Dokumentation, das Status-Dashboard der Updates, die Bot-Seiten von OpenAI, Anthropic und Perplexity, das
     RankMath-Änderungsprotokoll. Er schreibt nur dann einen Brief, wenn ein Eintrag eine Regel in `tg-seo` berührt, und ändert
     selbst nichts. Die Änderung an der Referenz ist eine Bau-Änderung mit neuem Abrufdatum. Der Check kommt gleich mit dem Workspace.
  3. **Daten tragen ihr Datum.** Jeder Messlauf liegt in einem Datumsordner, jede Zeile im Keyword-Set trägt Herkunft und Datum.
  4. **Wissensdateien.** `suchverhalten.md` und `keyword-set.md` fallen unter `tg-wissen-pruefen` (P2 B6). Dafür entsteht nichts
     Zusätzliches.
- **Begründung:** Heutiger Fall: Die FAQ-Regel steht bei Tegards in drei Fassungen, obwohl Google die Abkündigung am 08.05.2026
  eingetragen hat (Dossier T37, R6). Keine der beiden Seiten hat einen aktiven Mechanismus (Dossier L1).
- **Beleg:** `amm-seo` führt eine `herkunft.md` mit Abrufdatum (ELS `amm-seo/references/herkunft.md:3`: 2026-09-29) und zwei
  Handanweisungen „vor jedem Audit prüfen“ (`ki-suche.md:39`, `schema-vorlagen.md:164`). Eine `herkunft.md` haben 9 von 76
  Skill-Ordnern, darunter `amm-seo` und `amm-blog`; `amm-keyword-research`, `amm-seo-content` und `amm-seo-audit` haben keine
  (Codex #7). Dass jede übernommene SEO- und GEO-Regel Quelle und Abrufdatum trägt, ist deshalb eine Tegards-Anpassung nach dem
  Muster von `amm-seo`. Unter den fünf Workspace-Loops ist kein
  Regel-Check (ELS `amm-loops/references/loops-workspace.md:19-25`). Muster für den Auftrag ist der Branchen-Update-Loop (`:193-204`).
- **Verworfen:** Everlast wie es ist (hängt daran, dass jemand ein Audit startet); Tegards-Kopf „Nächste Prüfung“ je Datei (warnt nur).

### E2 Komplett-Audit einmal im Quartal (Q16)
- **Ergebnis:** `/seo-komplett-audit` läuft einmal im Quartal (Hausregel). Wie Markus daran erinnert wird, klärt P7.
- **Begründung:** Am Audit hängen die Stufen 2 und 3 der GEO-Messung (D3), der Auslöser für die Linien-Analyse (B5) und der
  Prüfpunkt Links-Bericht (D5). Ohne festen Takt greifen sie nicht.

### E3 Zwei Loops als Fixpunkte
- **Ergebnis:** Der wöchentliche Loop „fehlende Seite vorschlagen“ (Everlasts Loop seo-audit) und der monatliche Loop
  „Content-Verfall“ kommen sicher, mit einem Träger für Windows. Offen ist nur der Zeitpunkt; beide stehen als Fixpunkte mit
  Auslöser in `SPAETER.md`.
- **Beleg:** Der Loop seo-audit hält Suchverhalten und Keyword-Set gegen den Bestand und fragt, welche Suche noch keine Seite hat
  (EL `tools/seo-audit/auftrag.md:23-25`); sein lokaler Träger ist launchd, also macOS (EL `tools/seo-audit/README.md:35-40`).
  Content-Verfall: monatlich, ab 180 Tagen (ELS `amm-loops/references/loops-workspace.md:98-101`).
- **Befund Everlast:** Die README des Loops nennt als Quelle `loops-workspace.md` (EL `tools/seo-audit/README.md:4`); dort steht der
  Loop nicht in der Liste (`loops-workspace.md:19-25`).

---

## Teil F: Bausteine

### F1 SEO-Bausteine (Q15)
| Baustein | Status | Was sich ändert |
|---|---|---|
| `amm-seo` → `tg-seo` | anpassen | Der eine Ort für alle Regeln (E1). On-Page und Schema von Kursanbieter auf Shop umschreiben (C5). Neuer Schluss-Schritt „Meta-Block“ (Titel, Beschreibung, URL) mit den Zeichenlängen 60, 155, 149 als Hausregel. Kein `llms.txt`-Entwurf (D1). |
| `amm-keyword-research` → `tg-keyword-research` | anpassen | Suggest-Wortlaute, Spalten Zielseite und Status, Abschnitt je Linie (B2); Themenplan als Abschluss, Rollen und Familien-Regel, Tabelle um Kategorie- und Produktseite ergänzt (B3). |
| `/seo-komplett-audit` | anpassen | Einmal im Quartal (E2). Ruft für Index und Crawler `tg-seo-audit` auf. Neu: Prüfpunkt Links-Bericht (D5), Vergleich `dfs serp` gegen den letzten Lauf (B5). Berichtsort angleichen. |
| `amm-seo-audit` → `tg-seo-audit` | anpassen | Misst die ganze Website. Berichtsort angleichen. Der Messpunkt „Rendering ohne JavaScript“ läuft über Markus' eingerichtetes Firecrawl. Ahrefs kommt nicht. Antwortblock ohne Wortzahl (D1). |
| `amm-seo-content` → `tg-seo-content` | anpassen | Der Schritt von der Lücke zum Entwurf. Lücken kommen aus dem Themenplan und dem Wochen-Vorschlag; er führt keine zweite Lückenliste. Pfad zum Keyword-Set berichtigen (B2), Antwortblock ohne Wortzahl (D1), Seitenarten um Shop-Kategorie und Shop-Produkt ergänzen, Aufbau nach F2. |
| `tg-serp-analyse` | neu, nicht Everlast | B5 |
| Monatlicher Regel-Check | neu, nicht Everlast | E1, kommt gleich mit dem Workspace |
| Wöchentlicher Loop seo-audit, monatlicher Loop Content-Verfall | Fixpunkt, `SPAETER.md` | E3 |
| RankMath-MCP | gestrichen, `SPAETER.md` | Nicht geprüft, was der MCP kann. |

- **Begründung für `tg-seo-audit`:** Der Skill misst, was sonst niemand misst: Antwortstatus je Crawler mit voller Kennung,
  Rendering ohne JavaScript, Indexstatus für jede Adresse der Sitemap, Vergleich mit dem Vorlauf, einzelne Fragen an die Search
  Console. Die einzelne Seite prüft `amm-seo`. `amm-seo` selbst misst nicht.
- **Beleg:** ELS `amm-seo-audit/SKILL.md:34-35` (Vorlauf), `:36-48` (Crawler, Rendering über `tools/firecrawl/fc`), `:49-52`
  (`gsc inspect` für jede Adresse), `:69-80` (Einzelfragen), `:17-18` (Abgrenzung zu `amm-seo`); EL
  `.claude/references/skills-karte.md:30` („`amm-seo` misst nicht“). `tools/firecrawl/fc` liegt nicht im Paket (`SKILL.md:113`; in
  EL `tools/` gibt es keinen Ordner `firecrawl`). Ahrefs ist dort freiwillig (`:81-82`, `:114`).
- **Befund Everlast:** Weder `/seo-komplett-audit` noch der Wochen-Loop laden `amm-seo-audit`. Der Command liest `amm-web-audit`,
  `amm-seo` und `amm-keyword-research` (EL `.claude/commands/seo-komplett-audit.md:6-7`), der Loop `amm-loops`, `amm-web-audit` und
  `amm-seo` (EL `tools/seo-audit/auftrag.md:1`). Im Command kommen „inspect“ und „user-agent“ nicht vor (Suche: kein Treffer).
  Deshalb die Anpassung „das Komplett-Audit ruft `tg-seo-audit` auf“.
- **Befund Everlast, Berichtsorte:** Vier Orte für Audit-Berichte: `projekte/JJMMTT-seo-<slug>/befunde.md`
  (ELS `amm-seo/references/befund-format.md:9-10`), `daten/seo/JJMMTT-audit/befund.md` (ELS `amm-seo-audit/SKILL.md:61`),
  `daten/JJMMTT-seo-audit/report.md` (EL `tools/seo-audit/README.md:57`), `daten/JJMMTT-seo-komplett/report.md`
  (EL `.claude/commands/seo-komplett-audit.md:61`). Der Steuerstand sucht nur unter `projekte/` in Ordnern mit `seo`, `geo` oder
  `audit` im Namen (EL `steuerstand/build.ts:3590-3595`). Welcher Ort gilt, legt P7 fest.
- **Begründung für `tg-seo-content`:** Drei Bausteine stützen sich auf ihn: `amm-video-zu-blog` (Briefing und Gate, `SKILL.md:154`,
  `:232`, `:303`), `amm-pillar-to-blog` (`SKILL.md:13-16`), `amm-kampagne` (`references/traffic.md:33`); dazu die geplante Aufgabe
  (EL `seo/geplante-aufgaben/seo-neue-seite.md:5`). `amm-blog` wählt keine Themen (ELS `amm-blog/SKILL.md:12`).
- **Verworfen:** `amm-seo-audit` und `amm-seo-content` weglassen (Empfehlung des Dossiers; die Begründung „doppelt“ trug nicht, X2).
- **Zeichenlängen:** Google nennt keine feste Länge (ELS `amm-seo/references/on-page.md:76`), deshalb Hausregel.

### F2 Ein Aufbau für Ratgeber und Anleitung
- **Ergebnis:**
  - `tg-blog` und `tg-seo-content` schreiben beide nach demselben Gerüst, das P4 mit Hornbach als Vorbild herleitet (C3).
    `tg-seo-content` behält Lückenwahl, Auftrag und Prüfung.
  - Von den sechs Everlast-Formaten bleiben für Tegards Ratgeber und Anleitung. Die Fallstudie geht in der Seitenart Projekt auf.
    Das ist eine Anpassung gegenüber Everlast.
- **Beleg:** `amm-blog`: Antwort im ersten Absatz in höchstens drei Sätzen, keine Wortzahl (ELS `amm-blog/references/bauplaene.md:16`,
  `:20`), sechs Formate (`amm-blog/SKILL.md:5-6`), eigener Transkript-Modus (`:40`). `amm-seo-content`: Frage als H1, Antwortblock,
  Ausführung, nächster Schritt (`SKILL.md:33-35`), Ablage im Projektordner (`:38`). Keiner der drei Skills `amm-seo-content`,
  `amm-video-zu-blog`, `amm-pillar-to-blog` nennt `amm-blog` und umgekehrt (Suche in allen vier Skill-Ordnern: kein Treffer); der
  content-marketer und die Skills-Karte führen nur `amm-blog` (EL `.claude/agents/content-marketer.md:88`, `:107`;
  `.claude/references/skills-karte.md:13`).
- **Offen (P4):** ob `amm-video-zu-blog` und `amm-pillar-to-blog` kommen (wenn ja, mit eigenem Aufbau, kein Umbau); die Abgrenzung
  des Transkript-Modus im Blog-Skill gegen die Video-Skills.

---

## Teil G: Altbestand

### G1 Aus dem alten SEO-Wissensordner wird nichts übertragen (Q13)
- **Ergebnis:** Aus `E:\tegards\marketing\marketing-wissen\seo-geo\` wird nichts übertragen. Was keinen Abnehmer im neuen Ablauf hat,
  bleibt draußen. Die alten Dateien bleiben unangetastet im alten Ordner.

  | Altbestand | Was stattdessen gilt |
  |---|---|
  | Playbook | keine eigene Datei; einzelne Regel nur mit Primärquelle und Abrufdatum in `tg-seo` (E1) |
  | Keyword-Landkarte | das Keyword-Set entsteht neu aus der Bestandsaufnahme der Domain (B4) |
  | Website-Architektur | `kanaele/websites.md` entsteht im Onboarding, der Seitenbestand aus der Bestandsaufnahme vor dem Themenplan, Mängel findet das erste Audit |
  | KI-Sichtbarkeits-Log | Testfragen kommen aus dem neuen Keyword-Set (D3) |
  | die eine alte Suchergebnis-Analyse | entfällt, auch als Formatvorlage |
  | Verlinkungsstrategie | im neuen Ablauf verankert (B3, C3); alte Datei nicht gelesen |
  | Off-Page-Notizen | nichts; alte Datei nicht gelesen (D5) |
  | Referenzseiten | nur was einen Griff hat, zieht ins Swipefile (G2); alte Datei nicht gelesen |

- **Ausnahme:** Die Zeichenlängen für Titel und Beschreibung (60, 155, 149) kommen als Hausregel in den Meta-Block-Schritt (F1).
- **Begründung:** Onboarding Weg 1 (`STAND.md`, 14.11.2026): Altbestand ist Quelle, kein Import. Hier hat fast nichts einen Abnehmer,
  weil Keyword-Set, Themenplan und Regeln neu und mit gemessenen Daten entstehen.
- **Verworfen:** Zuordnung je alter Datei (Empfehlung des Dossiers, D13).
- **Ersetzt P2 F2** für den P3-Teil: Dort hieß es, die sieben SEO/GEO-Dateien würden nach Weg 1 neu eingearbeitet.

### G2 Swipefile
- **Ergebnis:**
  - Fremde Vorbilder liegen im Swipefile. Die Fächer heißen wie die eigenen Seitenarten (Landingpage, Kategorieseite, Produktseite,
    Blogartikel, Projekt). Ein Fach entsteht erst mit dem ersten Fund, als Unterordner mit eigener README. Jeder Eintrag braucht
    einen Griff.
  - Heute gibt es ein Fach: Blogartikel, mit den Hornbach-Seiten als Vorbild für Ratgeber und Anleitung. Die Auswertung liegt vor
    (C3); den Griff je Eintrag formuliert P4.
- **Beleg:** EL `swipefile/README.md:3-8` (Griff), `:29-30` (neue Sammlung = Unterordner mit README). Everlasts Fach `landingpages/`
  nimmt nur Optin-Seiten auf, keine Produktseiten ohne Formular (EL `swipefile/landingpages/README.md:15-16`, `:22`); diese
  Einschränkung gilt für Tegards nicht. Was mit dem Fach geschieht, entscheidet P9.

### G3 Produktdatenquelle der Bildprüfung (Q8, offen aus P1)
- **Ergebnis:** `produkte/<linie>/fakten.md` mit Belegpflicht (P2 A3, B3) ist die Produktdatenquelle für die Produktwahrheits-Zeile
  der Bildrubrik (P1 C9). Eine zweite Quelle entsteht nicht. Live-Daten aus dem Shop (Sortiment, Attribute) gehen an P4.

---

## Querschnitt

### X1 Neuer Schluss-Schritt: Abgleich auf Datei- und Code-Ebene (Markus)
- **Ergebnis:** Am Schluss der Planung steht ein Abgleich auf Datei- und Code-Ebene. Jeder Skill, Agent, Command, jede Datei,
  Funktion und Logik von Everlast wird geprüft, ob es bei Tegards ein Gegenstück oder einen vergleichbaren Ansatz gibt.
  Der Schritt steht in `STAND.md` im Abschnitt „Danach“ (eingetragen 17.11.2026).
- **Verhältnis zu P9 und zum Planungsaudit (von Markus am 17.11.2026 entschieden):** P9 liefert die Inventarliste je
  Everlast-Baustein mit Status. Der Abgleich geht eine Ebene tiefer (Funktion und Logik) und in die Gegenrichtung (was hat Tegards
  dazu). Er läuft nach P9 und vor dem Planungsaudit, damit seine Funde noch in die Entscheidungsdateien kommen.
- **Verworfen:** als Teil von P9; nach dem Planungsaudit.

### X2 Berichtigungen gegenüber dem Dossier
- „`dfs` führt keinen Backlink-Befehl“ war falsch. Gelesen war nur die Beispielliste der README (EL `tools/dataforseo/README.md:8-14`).
  Der Code hat `backlinks` (EL `tools/dataforseo/dfs:12`, `:462`, `:558`).
- „`amm-seo-audit` ist doppelt zu Modus A von `amm-seo`“ war zu hart, „`amm-seo-content` ist nur ein zweiter Weg neben `amm-blog`“
  unvollständig (F1).
- Zeilenangaben aus den Abzweigungen, beim Nachlesen berichtigt:
  - Transkript-Modus von `amm-blog`: `SKILL.md:40`, nicht `:36`. „Nicht für Themenwahl“: `:12`, nicht `:11`.
  - Ahrefs freiwillig: `amm-seo-audit/SKILL.md:81-82`, nicht `:78-80`.
  - Zielgruppen-Raster: `bremsen-und-bausteine.md:49`, nicht `:47`; die Tabelle reicht bis `:60`.
  - Rollen im Entscheidungsbaum: CO `zielseiten-entscheidungsbaum.md:33-35`, Familien-Regel `:45-46` (nicht `:30-34`, `:41-44`).
  - Ein Produkt im Steuerstand: Kommentar und Code stehen in `build.ts:3015-3018`.
- „`hornbach-blogaufbau.md` ist leer“ (Handoff, Grilling-Protokoll) ist überholt: Die Auswertung liegt seit 16.11.2026 vor (C3).
- „Bei neun Linien zeigt der Steuerstand die alphabetisch erste“ ist nicht belegt (X3).

### X3 Befunde zu Everlast für den Bau
- **Steuerstand und mehrere Linien:** Der Steuerstand nimmt den ersten Eintrag unter `produkte/` als das eine Produkt
  (EL `steuerstand/build.ts:3015-3018`). `listDir` filtert nur versteckte Einträge und sortiert nicht (`:48-52`); welcher Eintrag
  der erste ist, hängt also vom Dateisystem ab (Codex #9). Das Keyword-Set liest er nicht (Suche nach „keyword“ in `build.ts`:
  kein Treffer). Bei neun Linien zeigt er nur eine und nicht, welche Linie einen Themenplan hat. P2 A7 hat den Umbau auf mehrere Linien
  schon an P7 gegeben; neu ist die Anzeige von Keyword-Set und Themenplan.
- **Die Skills der Suchkette sind nicht ins Team eingebunden:** Keine Agentendatei, nicht die Head-Datei und nicht `AGENTS.md` nennen
  `amm-seo-audit`, `amm-seo-content` oder `amm-keyword-research` (Suche: kein Treffer). Beim Übernehmen einbinden (P7/P9).
- **`amm-new-product` kommt in `head-of-marketing.md` nicht vor** (Suche: kein Treffer). Ob der Head das Anlegen einer Linie
  auslöst, ist offen (P9).
- Weitere Befunde stehen bei B2 (zwei Pfade Keyword-Set), D1 (Antwortblock, `llms.txt`), E3 (Loop-Liste), F1 (Berichtsorte,
  Audit-Skill wird nicht geladen).

---

## Weggelassen (→ `SPAETER.md`)
Je Zeile der beschlossene Auslöser (Codex #10).

| Thema | Auslöser, ab dem es gebaut wird |
|---|---|
| Markup `FAQPage`, `HowTo`, `speakable`, `Product` ohne Preis (C5) | belegte Wirkung |
| GEO-Tracker (B1) | die Messung (D3) zeigt, dass KI-Antworten für unsere Begriffe eine Rolle spielen |
| Backlink-Analyse der Wettbewerber mit `dfs backlinks` (B5) | die Linien-Analyse erklärt einen Aufsteiger nicht aus Inhalt und internen Links |
| Eigener Fachagent für die Suchergebnis-Analyse (A3) | die Analyse sprengt nachweislich den Kontext des Planers |
| Operative Off-Page-Arbeit durch einen Agenten (D5) | Markus will das; heute Handarbeit, vorher zu prüfen |
| Nur noch ein Modus statt zwei Varianten bei der Leitseite (C2; Zeile vom 16.11., Auslöser neu) | Markus wählt bei den Leitseiten immer wieder den Entwurf innerhalb oder immer wieder den außerhalb des Designsystems |
| Wöchentlicher Loop „fehlende Seite vorschlagen“ (E3; Fixpunkt, eingetragen 16.11.) | für die erste Linie steht der Themenplan |
| Monatlicher Loop Content-Verfall (E3; Fixpunkt, eingetragen 16.11.) | die ersten Artikel sind über die neue Pipeline veröffentlicht |
| RankMath-MCP (F1; eingetragen 16.11.) | der Link-Plan oder die Meta-Prüfung bremst nachweislich ohne RankMath-Daten |

Nicht auf SPAETER, weil verworfen: „zuerst die ranking-optimale Variante“, der Entscheidungsbaum mit Schwellen, die Agenten
`serp-analyst`, `wettbewerbs-analyst` und `geo-validator`, die commerce-os-Templates als Pflichtfolge, das Playbook als Datei,
`llms.txt`, die Zahlenvorgaben (134 bis 167 Wörter, 300 Zeichen, genau zehn Fragen), die dritte kreative Variante, Ahrefs,
die Übernahme des alten SEO-Wissensordners.

---

## Offene Punkte nach Thema

- **P4 (Kanäle und Content-Fähigkeiten):**
  - Gerüst je Seitenart für Kategorie, Produkt, Ratgeber, Anleitung, Projekt herleiten, je mit zwei festen Stellen (C3); ein
    gemeinsames Gerüst für Ratgeber und Anleitung (F2).
  - Hornbach-Abgleich (`hornbach-blogaufbau.md`, liegt vor) in das Gerüst einarbeiten; nur die dort als nicht prüfbar genannten
    Punkte bei Bedarf im Browser nachsehen (C3, G2).
  - Varianten-Lauf der Leitseite ausgestalten; Weg eines neuen Bausteins ins Designsystem, wer baut (C1, C2).
  - Bilder ausgestalten (C6).
  - Rückmeldung vom Markt über Google Analytics, Google Ads und Facebook-Werbung bei Everlast nachlesen.
  - Ob `amm-video-zu-blog` und `amm-pillar-to-blog` kommen; Transkript-Modus im Blog-Skill (F2).
  - Live-Daten aus dem Shop als Quelle neben `fakten.md` (G3).
  - Anpassung von `amm-new-product` auf Linien mit drei Zusätzen: Linienprüfung vor dem Anlegen, Quellenfrage am Anfang, Kette zur
    Seite (Themenplan, dann Sektionsplan). Einzelheiten im Grilling-Protokoll, Abschnitt „Für die Folgesession“; die Everlast-Belege
    dort sind in dieser Session nicht nachgelesen.
  - SEO-Regel zur Höchstzahl der Wörter oberhalb der Produktliste prüfen (C1).
  - GEO-Punkte in die Inhaltsrubriken (D2).
- **P7 (Gerüst, Windows-Port):**
  - Laufen `dfs` und `gsc` unter Windows; Österreich ausdrücklich ergänzen (B1).
  - Höhe des Kostendeckels je DataForSEO-Lauf (B1); Erinnerung an das Komplett-Audit im Quartal (E2).
  - Träger für die drei Loops unter Windows; der monatliche Regel-Check kommt gleich mit (E1, E3).
  - Rendering-Messpunkt von `tg-seo-audit` über Markus' Firecrawl (F1).
  - Ein Berichtsort für Audits; ein Pfad fürs Keyword-Set (F1, B2).
  - Wortzahl des Antwortblocks aus Skills und Prüfskript nehmen, auch `pruefe_artikel.py:31` (D1).
  - `tg-seo` von Kursanbieter auf Shop umschreiben, Meta-Block-Schritt (F1, C5).
  - Steuerstand: Keyword-Set und Themenplan je Linie anzeigen (X3; mit P2 A7 und P9 abgleichen).
- **P8 (Onboarding):**
  - Station 15: welche Säulen es werden (B6).
  - `kanaele/websites.md`: Bestand der Website, Eintrag „Such- und Trainingscrawler zugelassen“ (B2, D4).
  - DataForSEO-Konto: Markus legt es an und trägt die Zugangsdaten selbst ein (B1).
  - Bestandsaufnahme der Domain einmal für alle Linien, je für Österreich und Deutschland (B4).
  - Vor dem Neubau einer bestehenden Seite: Bewertung mit Liste „muss bleiben“, heutige Zahlen, Adresse und Hauptbegriff bleiben (C4).
- **P9 (Inventur):**
  - Endgültige Inventarzeile je SEO-Baustein (F1).
  - Was mit Everlasts Swipefile-Fach `landingpages/` geschieht (G2).
  - Ob der Head das Anlegen einer neuen Linie auslöst (X3).
  - Wann der Wochen-Loop eingeplant wird (E3).
  - Verhältnis der Inventur zum Abgleich auf Datei- und Code-Ebene (X1).

---

## Nicht geprüft

- Die Tegards-Belege mit **(B)** im Dossier sind nur gegen den Lesebericht `03-lesen/tegards.md` geprüft, nicht gegen die
  Originaldateien. Die Haiku-Belegprüfung deckt nur die Teile 1 bis 7 des Dossiers ab.
- Verweise auf Dossier-Nummern (T…, R…, L…) sind in dieser Session nicht neu geprüft. Die Recherche-Aussagen R10 bis R12 hat auch
  die P3-Session nicht an der Quelle nachgeprüft.
- Die 0,59 USD je Audit sind ein Messwert von Everlast (B1). Andere Anbieter als DataForSEO wurden nicht recherchiert.
- Dass der Unterbau einer Domain das Ranking trägt (B5) und dass ein freier Neubau besser verkauft (C2), ist fachliche Einschätzung.
- Ob der Links-Bericht der Search Console nur in der Oberfläche verfügbar ist (D5).
- Was der RankMath-MCP kann (F1).
