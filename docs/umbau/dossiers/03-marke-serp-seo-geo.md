# Dossier P3: Markengeführt × suchergebnisgeführt, SEO/GEO-Frische, Seitenschemas

Stand: 16.11.2026, vollständig. Belegprüfung (Haiku, 355 Belege): 338 in Ordnung, 9 Befunde, davon 8 korrigiert und
einer nach Nachsehen zurückgewiesen (`ELS:amm-keyword-research/SKILL.md:61` nennt „Priorität“). Bericht:
`docs/umbau/dossiers/03-lesen/belegpruefung.md`. Die mit **(B)** markierten Belege wurden gegen den Lesebericht geprüft,
nicht gegen die Originaldateien.
Session: P3, Modell Fable 5.2. Everlast und die Tegards-Kernstellen in dieser Session selbst gelesen; die vollständige
Tegards-Kette und die Webrecherche über zwei Subagenten (Berichte unter `docs/umbau/dossiers/03-lesen/`).

**Kurzfassung:** Everlast führt von der Marke zum Inhalt und lässt die Suche nur Thema und Format bestimmen. Tegards führt
von den Suchergebnissen zur Seite und holt die Marke über eine Weiche herein, die heute leer ist. Empfohlen wird eine
Arbeitsteilung: die Marke setzt Aussagen und Argumente, die Suche entscheidet über Seite, Seitentyp und Pflichtthemen,
beide treffen sich im Sektionsplan, den Markus vor dem Text freigibt. SEO- und GEO-Regeln stehen an einem Ort und werden
monatlich gegen feste Primärquellen geprüft.

**Pfad-Kürzel für alle Belege in dieser Datei:**

- `EL:` = `E:\Everlast Learning\marketing-workspace-0.5.0\`
- `ELS:` = `E:\Everlast Learning\marketing-workspace-0.5.0\.claude\skills\`
- `CO:` = `E:\commerce-os\`
- `TG:` = `E:\tegards\marketing\marketing-wissen\seo-geo\`

Ein Beleg `ELS:amm-seo/SKILL.md:29` heißt also Zeile 29 der Datei
`E:\Everlast Learning\marketing-workspace-0.5.0\.claude\skills\amm-seo\SKILL.md`.

---

## 1. Everlast: Fakten

### 1.1 Der markengeführte Weg (Top-down)

| # | Aussage | Beleg |
|---|---|---|
| E1 | Die Positionierung entsteht in Station 11 aus SWOT und Angebot, per Leitfragen. | `ELS:amm-workspace-setup/references/stationen.md:34`, `:103-104` |
| E2 | Die Content-Strategie ist die letzte Station (15), Vorbedingung ist Station 14. Sie füllt `content-saeulen.md` und `suchverhalten.md`. | `ELS:amm-workspace-setup/references/stationen.md:38` |
| E3 | Eine Säule wird zuerst aus `positionierung.md` und `usps.md` abgeleitet, danach aus Zielgruppen und Kundenwortlaut. Die Suche steht in dieser Reihenfolge nicht. | `ELS:amm-content-strategie/references/saeulen.md:26-33` |
| E4 | Eine Säule ist ein Themenfeld, „in dem die Marke mehr weiß als der Durchschnitt der Suchergebnisse“, und muss in zwei Schritten zum Angebot führen. Höchstens fünf Säulen. | `ELS:amm-content-strategie/references/saeulen.md:17`, `:44`, `:19` |
| E5 | `suchverhalten.md` schreibt `amm-content-strategie` im Modus S. Vorlage: je Kaufphase (1 Problem bis 4 Beschaffung) eine Tabelle Suche im Wortlaut, Stufe, Herkunft, Datum; dazu Rollenwörter und Schreibvarianten. | `ELS:amm-content-strategie/SKILL.md:38`, `:55`; `ELS:amm-content-strategie/assets/suchverhalten-vorlage.md:13-57` |
| E6 | Im Paket ist `suchverhalten.md` ein Stub. | `EL:strategie/positionierung/suchverhalten.md:2`, `:9` |
| E7 | Die Kaufphasen und Signalwörter sind für den „deutschen B2B-Weiterbildungsmarkt“ geschrieben (Schulung, Seminar, Teilnahmebescheinigung). | `ELS:amm-content-strategie/references/suchmodifikatoren.md:1`, `:40-42` |
| E8 | Nachfrage hat drei Stufen: 3 gemessen, 2 gehört, 1 Vermutung. Ein Suchvolumen wird nie geschätzt. | `ELS:amm-content-strategie/references/suchmodifikatoren.md:90-94`; `ELS:amm-content-strategie/SKILL.md:26`, `:93` |
| E9 | Ideen werden ungewichtet bewertet: Wert = Nachfrage + Passung + Beweis. Beweis 0 sperrt das Leitstück. | `ELS:amm-content-strategie/references/auswahl.md:60-70` |
| E10 | Verhältnis 60/30/10 (Suchthema, Resonanzthema, Versuch) in Stunden. Der Wert ist ein übernommener Startwert ohne eigenen Datenbeleg. | `ELS:amm-content-strategie/SKILL.md:63`; `ELS:amm-content-strategie/references/herkunft.md:18` |
| E11 | Ein Suchthema geht zuerst in den Blog, ein Resonanzthema zuerst zu LinkedIn oder Newsletter. | `ELS:amm-content-strategie/references/auswahl.md:44-48` |

**Wer liest `suchverhalten.md`** (alle Fundstellen workspace-weit):

| Leser | Wofür | Beleg |
|---|---|---|
| `amm-seo` | Gate: fehlt die Datei, wird gefragt; Kontext in Schritt 2; Hauptbegriff je Seite; Testfragen für KI-Suche | `ELS:amm-seo/SKILL.md:29`, `:44`; `ELS:amm-seo/references/on-page.md:15`; `ELS:amm-seo/references/ki-suche.md:120` |
| `amm-keyword-research` | liest die Beispielsuchen, misst sie und trägt das Volumen als Spalte nach | `ELS:amm-keyword-research/SKILL.md:37-38`, `:49`, `:54-55` |
| `amm-blog` | Feld Suchfrage im Briefing | `ELS:amm-blog/references/briefing.md:12` |
| Loop seo-audit | hält die Suchen gegen den Bestand, schlägt eine Seite vor | `EL:tools/seo-audit/auftrag.md:23-25` |
| `seo-voraussetzungen.py` | prüft, ob die Datei gefüllt ist | `EL:tools/seo-voraussetzungen.py:60` |
| `amm-content-strategie` | lädt sie selbst in Schritt 2 | `ELS:amm-content-strategie/SKILL.md:44` |

`suchverhalten.md` steht in keiner Prime-Liste. `prime-content` lädt `content-saeulen.md`, aber nicht das Suchverhalten
(`EL:.claude/commands/prime-content.md:7-13`).

### 1.2 Zwei SEO-Schichten, die nicht verbunden sind

**Schicht A, eingebunden: `amm-seo`.**

| # | Aussage | Beleg |
|---|---|---|
| E12 | Fünf Modi: A Audit, S Seite, D Daten (JSON-LD), K KI-Suche, V Vorlage für programmatische Seiten. | `ELS:amm-seo/SKILL.md:35-41` |
| E13 | `amm-seo` misst nicht, gemessen wird mit `amm-web-audit`. | `ELS:amm-seo/SKILL.md:24`; `EL:.claude/references/skills-karte.md:30` |
| E14 | Geladen wird er vom content-marketer (Workflow B Blog), vom webdesigner (Politur), vom Loop Content-Verfall, vom Loop seo-audit und von `/seo-komplett-audit`. | `EL:.claude/agents/content-marketer.md:108`; `EL:.claude/agents/webdesigner.md:111`; `ELS:amm-loops/references/loops-workspace.md:104`; `EL:tools/seo-audit/auftrag.md:1`; `EL:.claude/commands/seo-komplett-audit.md:6-7` |
| E15 | Ergebnisort: `projekte/JJMMTT-seo-<slug>/befunde.md`. Der Steuerstand-Reiter SEO/GEO sucht genau dort. | `ELS:amm-seo/references/befund-format.md:9-10`; `EL:steuerstand/build.ts:3590-3595` |
| E16 | Er steht in der Skills-Karte (Familie Auffindbarkeit) und in der Familien-Tabelle. | `EL:.claude/references/skills-karte.md:16`; `ELS:README.md:21` |

**Schicht B, Kursmodul „SEO und GEO“: `amm-keyword-research`, `amm-seo-content`, `amm-seo-audit`, `/seo-komplett-audit`, `tools/gsc`, `tools/dataforseo`, Ordner `seo/`.**

| # | Aussage | Beleg |
|---|---|---|
| E17 | Die drei Skills stehen weder in der Skills-Karte noch in der Familien-Tabelle. | `EL:.claude/references/skills-karte.md:7-20`; `ELS:README.md:17-24` |
| E18 | Keine Agentendatei und nicht die Head-Datei nennen einen der drei Skills (Suche nach `seo-audit`, `seo-content`, `keyword-research` in `EL:.claude/agents/`, `EL:.claude/head-of-marketing.md`, `EL:AGENTS.md`: kein Treffer). Erreichbar sind sie nur über ihre `description`, über `/seo-komplett-audit` und über die geplante Aufgabe. | `EL:.claude/commands/seo-komplett-audit.md:46`; `EL:seo/geplante-aufgaben/seo-neue-seite.md:5` |
| E19 | Die Herkunft der Schicht ist der Kurs. | `EL:tools/gsc/README.md:4` |
| E20 | `amm-keyword-research` baut ein Keyword-Set aus Bestandsaufnahme, Kundensprache, Volumen (DataForSEO), Seite eins je Kernbegriff samt KI-Übersicht und Clustern aus Pillar und Spokes. Ergebnis ist „eine Themenkarte, kein Text“. | `ELS:amm-keyword-research/SKILL.md:39-55`, `:13-14` |
| E21 | `amm-seo-content` macht aus einer Lücke einen Seitenentwurf: Lücke aus Search-Console-Positionen 4 bis 20, sonst aus dem Keyword-Set, sonst aus GEO-Daten; Briefing mit sieben Zeilen; Gate; Ablage zur Freigabe. Er nennt als Seitenarten Blogartikel, Ratgeberseite, Glossareintrag und Landingpage. | `ELS:amm-seo-content/SKILL.md:22-40`, `:9-10`; `ELS:amm-seo-content/references/briefing.md:8-18`, `:36-44` |
| E22 | `amm-seo-audit` prüft zehn Kriterien mit Konfidenzstufe je Befund; nur ein belegter Fehler darf die Note deckeln. | `ELS:amm-seo-audit/references/kriterien.md:8-17`; `ELS:amm-seo-audit/references/schwellen.md:16-20` |

**Widersprüche zwischen und in den Schichten:**

| # | Widerspruch | Beleg |
|---|---|---|
| W1 | Ort des Keyword-Sets: zwei Pfade für dieselbe Datei. Der Skill schreibt nach `strategie/positionierung/keyword-set.md`, andere Bausteine lesen `seo/keyword-set.md`. Der Stub liegt unter `seo/`. | Pfad `strategie/positionierung/`: Schreiber `ELS:amm-keyword-research/SKILL.md:54`; Prüfskript `EL:tools/seo-voraussetzungen.py:73`; Leser Loop `EL:tools/seo-audit/auftrag.md:23`. Pfad `seo/`: Leser `ELS:amm-seo-content/SKILL.md:25`, `:66`; `EL:seo/geplante-aufgaben/seo-neue-seite.md:7`; `ELS:amm-video-zu-blog/SKILL.md:79`. Stub: `EL:seo/keyword-set.md:2`, `:11` |
| W2 | Vier Berichtsorte für Audits. Der Steuerstand zeigt nur den ersten. | `ELS:amm-seo/references/befund-format.md:9`; `ELS:amm-seo-audit/SKILL.md:61`; `EL:tools/seo-audit/README.md:57`; `EL:.claude/commands/seo-komplett-audit.md:61`; `EL:steuerstand/build.ts:3590-3595` |
| W3 | `amm-seo-audit` setzt Werkzeuge voraus, die nicht im Paket liegen (`tools/firecrawl/fc`, `tools/ahrefs/ahrefs`). | `ELS:amm-seo-audit/SKILL.md:113-114` |
| W4 | Die README des Loops seo-audit nennt als Quelle `loops-workspace.md`. Dort stehen fünf Loops, seo-audit ist nicht dabei. | `EL:tools/seo-audit/README.md:4`; `ELS:amm-loops/references/loops-workspace.md:19-25` |
| W5 | Zwei Regeln für den Antwortblock. `amm-seo-content`: 134 bis 167 Wörter, selbst als Faustwert ohne Messung gekennzeichnet. `amm-blog`: höchstens drei Sätze, keine Wortzahl als Ziel. | `ELS:amm-seo-content/SKILL.md:34`; `ELS:amm-seo-content/references/zitierfaehigkeit.md:17-20`; `ELS:amm-blog/references/bauplaene.md:16`, `:20` |
| W6 | `llms.txt`: bei `amm-seo` ein Ergebnis von Modus K und ein Befund in Topf 3, bei `amm-seo-audit` ausdrücklich kein Hebel und außerhalb der Bewertung. | `ELS:amm-seo/SKILL.md:40`; `ELS:amm-seo/references/ki-suche.md:76-79`; `ELS:amm-seo-audit/SKILL.md:100-101` |
| W7 | Der lokale Träger des wöchentlichen Loops ist macOS (launchd, `launchctl`); die Alternative ist eine Cloud-Routine. | `EL:tools/seo-audit/README.md:35-40`, `:47-48` |

### 1.3 Wie Suchergebnisse bei Everlast eingehen

| # | Stelle | Was die Suchergebnisseite dort liefert | Beleg |
|---|---|---|---|
| E23 | `amm-keyword-research`, Schritt 7 | Seite eins je Kernbegriff, nebenbei ob eine KI-Übersicht erscheint und wen sie zitiert | `ELS:amm-keyword-research/SKILL.md:50-51` |
| E24 | Cluster-Regel | Die Suchabsicht entscheidet die Seitenform: Information → Glossar oder Ratgeber, Vergleich → Vergleichsseite, Kauf → Angebotsseite | `ELS:amm-keyword-research/references/cluster.md:15-22` |
| E25 | `amm-blog`, Briefing | Intention aus dem „Blick auf die ersten Treffer“; passen zwei Formate, „gewinnt das der ersten Treffer“ | `ELS:amm-blog/references/briefing.md:13`, `:37` |
| E26 | `amm-blog`, Kernregel | kein Artikel ohne Mehrwert gegenüber den Treffern der Suche | `ELS:amm-blog/SKILL.md:70` |
| E27 | `amm-blog`, Auffrischen | Suchfrage erneut gegen die ersten Treffer prüfen; verschobene Intention ist eine Rückfrage | `ELS:amm-blog/references/refresh.md:36` |
| E28 | `amm-content-strategie` | Suchergebnisseite als Ideenquelle („Ähnliche Fragen“, Übersicht mit KI, Formate der Top-Treffer) | `ELS:amm-content-strategie/references/auswahl.md:22`; `ELS:amm-content-strategie/references/suchmodifikatoren.md:78` |
| E29 | `amm-competitor` | Wettbewerber aus der Suchergebnisseite zu den Kaufkeywords, wenn keine Mikroanalyse vorliegt | `ELS:amm-competitor/SKILL.md:43` |
| E30 | `/seo-komplett-audit` | KI-Sichtbarkeit für die zehn Begriffe ohne Marke; geschätzte Positionen tragen einen Stichtag und werden live bestätigt | `EL:.claude/commands/seo-komplett-audit.md:56-57`, `:49-51` |

**Was fehlt (in den gelesenen Dateien keine Stelle gefunden):** Die Suchergebnisse bestimmen bei Everlast das Thema, das
Format und die Seitenform, aber nicht den Aufbau einer Verkaufsseite. Der Sektionsplan hat sechs Schritte, keiner davon
sieht Suchergebnisse an (`ELS:amm-sektionsplan/SKILL.md:28-33`). Seine Eingaben sind Plan, Swipe-Matrix und Material
(`EL:.claude/agents/references/webdesigner-workflows.md:41`). Die Swipe-Station sammelt 10 bis 16 Startseiten der Branche
nach Machart, nicht nach Rang für einen Suchbegriff (`EL:.claude/agents/references/webdesigner-workflows.md:39`).

### 1.4 Seitenbau und Seitentypen

| # | Aussage | Beleg |
|---|---|---|
| E31 | Der Sektionsplan kennt vier Seitentypen: Anmeldeseite, Sales-Page, Kursseite, Produktseite. Der Typ entscheidet, welche Kaufbremsen zählen. | `ELS:amm-sektionsplan/SKILL.md:28` |
| E32 | Prinzip: eine Sektion räumt genau eine von sechs Kaufbremsen weg. Der Einstieg liegt eine Stufe vor dem Awareness-Stand. | `ELS:amm-sektionsplan/SKILL.md:39-44`, `:48` |
| E33 | Der Plan ist eine Tabelle mit Sektion, Bremse, Ziel, Baustein, Copy-Quelle und „Nicht“ und geht an den webdesigner. | `ELS:amm-sektionsplan/SKILL.md:62-72` |
| E34 | Das Baustein-Repertoire (Hero, Statistik, Vergleich, FAQ, CTA …) ist „abgelesen an Seiten, die laufen“; die Wortzahlen sind an einer echten Seite gemessen. Es enthält keinen Baustein für Produktraster, Filter oder Attribut-Tabelle. | `ELS:amm-sektionsplan/references/bremsen-und-bausteine.md:40-41`, `:43-60` |
| E35 | Staffellauf Website-Bau: webdesigner (Vorphase), webdesigner (Sektionen mit `[COPY: ...]`), copywriter, grafik-designer, webdesigner. | `EL:.claude/head-of-marketing.md:101` |
| E36 | Der Stack für Neubauten ist fest Astro und Cloudflare. Ein Bestand in jedem anderen Stack, auch WordPress, läuft über Workflow B ohne Migration. | `EL:.claude/agents/webdesigner.md:35-36`, `:133`; `EL:.claude/agents/references/webdesigner-workflows.md:21-22`, `:82-86` |
| E37 | `amm-blog` hat sechs Formate; das Format folgt der Suchintention nach einer festen Tabelle. | `ELS:amm-blog/SKILL.md:5-6`, `:65`; `ELS:amm-blog/references/briefing.md:28-35` |
| E38 | Ein Blogartikel ist eine Datei in der Pipeline; `veroeffentlicht/` liest die Astro-Website direkt. | `EL:pipelines/blog/README.md:10-13`, `:36-48` |
| E39 | Die On-Page-Regeln von `amm-seo` sind „zugeschnitten auf Kursanbieter“; der Pflichtinhalt ist der einer Kursseite. | `ELS:amm-seo/references/on-page.md:3`, `:23-29` |
| E40 | Die Schema-Vorlagen decken die „Seitentypen eines Kursanbieters“ ab: Organization, BreadcrumbList, Course, Kursliste (ItemList), Article, Event. | `ELS:amm-seo/references/schema-vorlagen.md:3`, `:9` |
| E41 | Für viele Seiten aus einer Vorlage gibt es Modus V mit Dünne-Prüfung an fünf Beispielseiten. | `ELS:amm-seo/references/on-page.md:100-109` |

**Was fehlt:** Eine Kategorieseite (Produktliste eines Shops) kommt als Seitentyp nicht vor, ebenso wenig WooCommerce,
RankMath oder ein JSON-LD-Block `Product` (Suche nach `Kategorieseite`, `WooCommerce`, `RankMath`, `"Product"` in
`EL:.claude/`, `EL:tools/`, `EL:seo/`: kein Treffer in Skills, Agenten, Rules oder Commands). `Produktseite` steht als
Seitentyp nur in der Typenliste des Sektionsplans (E31); zwei weitere Nennungen sind beiläufig
(`ELS:amm-infografik/references/formen.md:171`, `ELS:amm-swipe/references/plattformen.md:613`).

**Produktlinien:** Suchverhalten und Säulen liegen einmal auf Markenebene unter `strategie/positionierung/`
(`ELS:amm-workspace-setup/references/struktur.md:105-106`). Je Produkt gibt es Angebot, Zielgruppe und Wettbewerb
(`ELS:amm-new-product/references/ordner.md:70-79`). Die Prime-Liste nimmt das im Auftrag genannte Produkt
(`EL:.claude/commands/prime-content.md:13`, `:17`). Ein Suchverhalten oder Keyword-Set je Produkt ist nicht vorgesehen.

### 1.5 GEO und KI-Suche

| # | Aussage | Beleg |
|---|---|---|
| E42 | Grundsatz: Google verlangt für KI-Übersichten nichts Zusätzliches und kein eigenes Schema. | `ELS:amm-seo/references/ki-suche.md:15` |
| E43 | Crawler-Tabelle mit Trennung Such- und Trainingscrawler; die Entscheidung trifft der Nutzer. | `ELS:amm-seo/references/ki-suche.md:24-38` |
| E44 | `llms.txt` ist ein offener Vorschlag, kein Standard. | `ELS:amm-seo/references/ki-suche.md:76` |
| E45 | Zitierfähigkeit in fünf Punkten, jeder an einer Google-Seite verankert. | `ELS:amm-seo/references/ki-suche.md:101-107` |
| E46 | Testfragen-Protokoll: fünf bis zehn Fragen aus `suchverhalten.md`, fester Zeilenschlüssel (Frage, Anbieter mit Modell, Sitzung, n), zehn Läufe je Zeile, Ablage `daten/testfragen.md` im Audit-Ordner. | `ELS:amm-seo/references/ki-suche.md:113-124`, `:134-136` |
| E47 | Fremdnennungen und Autorität kann ein Agent nicht erzeugen; das steht ausdrücklich da. | `ELS:amm-seo-audit/references/kriterien.md:16-17`, `:25-26` |
| E48 | `amm-blog` führt drei Muster der Zitierfähigkeit und sagt keine Zitierung zu. | `ELS:amm-blog/references/zitierfaehigkeit.md:22-57`, `:72` |
| E49 | FAQ-Markup bringt kein Rich Result; der Fragenblock bleibt als sichtbarer Text. | `ELS:amm-blog/references/on-page.md:55`; `ELS:amm-seo/references/schema-vorlagen.md:161` |
| E50 | Die Search-Console-Berichte zu AI Overviews und AI Mode sind über die Schnittstelle nicht abrufbar. | `EL:tools/gsc/README.md:64` |

### 1.6 Frische

| Was altert | Mechanismus bei Everlast | Beleg |
|---|---|---|
| Regelwissen in den Skills (Google-Doku, Crawler-Namen, Schema-Typen, Recht) | Je Skill eine `herkunft.md` mit Quelle und Abrufdatum 2026-09-29. Zwei Handanweisungen „vor jedem Audit prüfen“ (Crawler-Tabelle, entfallene Schema-Typen). Ein Takt oder Loop dafür ist nicht vorgesehen. | `ELS:amm-seo/references/herkunft.md:3`; `ELS:amm-seo/references/ki-suche.md:39`; `ELS:amm-seo/references/schema-vorlagen.md:164`; Loop-Liste `ELS:amm-loops/references/loops-workspace.md:19-25` |
| Messdaten (Positionen, Technik) | Datumsordner je Lauf, alter Lauf bleibt als Vergleich. Geschätzte Positionen tragen einen Stichtag und werden live bestätigt. Wöchentlicher Loop seo-audit montags 06:30. | `ELS:amm-seo/references/befund-format.md:13`; `EL:.claude/commands/seo-komplett-audit.md:49-51`; `EL:tools/seo-audit/README.md:9`, `:35` |
| Veröffentlichte Artikel | Kadenz je Format (Statistik bei neuem Stand der Quelle, Vergleich monatlich, Glossar, Howto, Fallstudie jährlich). Loop Content-Verfall monatlich ab 180 Tagen. Wiedervorlage nach drei bis sechs Monaten. | `ELS:amm-blog/references/refresh.md:10-17`; `ELS:amm-loops/references/loops-workspace.md:98-101`; `ELS:amm-content-strategie/references/distribution.md:71` |
| Umfeld und Wettbewerber | Loop Branchen-Update täglich aus Makroanalyse und `competitor.md`; er ändert die Makroanalyse nie. | `ELS:amm-loops/references/loops-workspace.md:193-204`, `:284-286` |
| Eigene Erfahrungswerte | Kalibrierung über `kanaele/content-learnings.md`; eigene Werte gehen vor Startwerten. | `ELS:amm-content-strategie/SKILL.md:71`; `ELS:amm-content-strategie/references/auswahl.md:72` |

Gelesen (Teil 1): `EL:AGENTS.md`, `EL:.claude/head-of-marketing.md`, alle sechs `prime*.md`, `seo-komplett-audit.md`,
`skills-karte.md`, `workspace-karte.md`, `ELS:README.md`; vollständig `amm-seo` (SKILL und sieben Referenzen),
`amm-seo-content`, `amm-seo-audit`, `amm-keyword-research`, `amm-content-strategie` (ohne `recht.md`), `amm-sektionsplan`,
`amm-blog` (ohne `compliance.md`, `youtube-textebene.md`, `assets/artikel-vorlage.md`), `amm-pillar-to-blog/SKILL.md`,
`amm-copywriting` (SKILL und `formeln-und-sektionen.md`), `amm-competitor/SKILL.md`, `amm-web-audit/SKILL.md`,
`amm-workspace-setup` (`stationen.md`, `struktur.md`), `amm-new-product/references/ordner.md`,
`amm-loops` (`loops-workspace.md`, `assets/branchen-update/auftrag.md`, `synthese.md`); Agenten `webdesigner.md`,
`copywriter.md`, `content-marketer.md` mit `webdesigner-workflows.md`, `webdesigner-laufzeit.md`,
`copywriter-website-lauf.md`, `content-marketer-awareness.md`; `EL:seo/` (beide Dateien), `EL:tools/seo-audit/`
(README, `auftrag.md`, `cloud/routine.md`), `EL:tools/gsc/README.md`, `EL:tools/dataforseo/README.md`,
`EL:tools/seo-voraussetzungen.py`, `EL:tools/README.md`, `EL:pipelines/README.md`, `EL:pipelines/blog/README.md`,
die Stubs `suchverhalten.md`, `content-saeulen.md`, `websites.md`, `content-learnings.md`;
`EL:steuerstand/build.ts` nur Zeilen 3505-3545, 3576-3600, 9086-9110 und die Trefferzeilen zu `seo`.
**Nicht gelesen:** `amm-video-zu-blog` (nur Trefferzeilen), `amm-content-planer` (nur Trefferzeilen),
`amm-competitor/references/`, `amm-mikroanalyse`, `amm-kundenanalyse`, `webdesigner-rubrik.md`, `-werkzeuge.md`,
`-varianten.md`, `-messen.md`, `content-marketer-pruefung.md`, `tools/seo-audit/messen.py`, `tools/dataforseo/dfs`,
`tools/gsc/gsc`, der Rest von `build.ts`.

---

## 2. Tegards: Fakten

Der vollständige Lesebericht mit allen Elementen (wer schreibt, wer liest) liegt unter
`docs/umbau/dossiers/03-lesen/tegards.md` (396 Zeilen, Subagent Opus 5.5). Hier stehen nur die Aussagen, auf denen die
Entscheidung ruht. Belege mit **(B)** stammen aus dem Lesebericht und wurden nicht selbst geöffnet; alle anderen habe ich
selbst gelesen.

### 2.1 Der suchergebnisgeführte Weg (Bottom-up)

| # | Aussage | Beleg |
|---|---|---|
| T1 | Grundregel „SEO-Optimum-First“: zuerst die ranking-optimale Variante aus SERP- und Wettbewerbsanalyse ableiten (Struktur, Argumente, Value Propositions), dann gegen die eigenen Quellen abgleichen. Dokumentiert werden nur Widersprüche. | `CO:references/querschnitt/bausteine-content-skills.md:21-26` |
| T2 | Dieselbe Regel gilt für alle fünf Content-Skills: aus den Top-Rankern zuerst „die optimale Struktur, Argumentation und Value Propositions“ ableiten. | `CO:references/querschnitt/bausteine-content-skills.md:131-135` |
| T3 | Keyword-Gate der Landingpage: ohne Landkarten-Eintrag mit dieser Seite als Zielseite und ohne frisches Keyword-Ergebnis derselben Session gilt STOPP, kein Entwurf, keine Analysen. | `CO:skills/landingpage/SKILL.md:38` |
| T4 | Die Keyword-Recherche arbeitet ohne Bezahlwerkzeug: Suggest-Endpunkte von Google, Bing und DuckDuckGo plus eigene SERP-Extraktion. Suchvolumen werden nicht genannt, für belastbare Werte verweist der Skill auf ein Keyword-Tool. | `CO:skills/keyword-recherche/SKILL.md:66-76`, `:108-110` |
| T5 | Ergebnis der Recherche ist eine 18-Zeilen-Tabelle (je Suchintention ein Haupt- und fünf Nebenkeywords) und je Keyword genau eine Zielseite. Die Landkarte wird erst nach Freigabe geändert. | `CO:skills/keyword-recherche/SKILL.md:9-12`, `:89-104` |
| T6 | Zielseiten-Entscheidungsbaum: eigene Landingpage nur bei breitem semantischem Feld (mindestens drei Blog-Themen, mindestens zwei erwartbare Projekte im Jahr) und eigenständigem kommerziellem Kern-Keyword; sonst Kategorieseite; Produktseite nur für Modell-, Maß- und Variantensuchen; Blog für Erklärbedarf, auch bei kommerziellen Keywords. | `CO:references/zielseiten-entscheidungsbaum.md:11-29` |
| T7 | Jede Kategorie- und Produktseite hat eine Rolle: `zielseite` (ein Keyword der Landkarte, volle Tiefe) oder `shop-seite` (kein eigenes Keyword, reduzierte Tiefe). | `CO:references/zielseiten-entscheidungsbaum.md:33-37`, `:49-50` |
| T8 | Derselbe Baum steht zweimal: als Plugin-Kopie und in der Instanz. | `CO:references/zielseiten-entscheidungsbaum.md:11-29`; `TG:website-architektur.md:133-154` |
| T9 | Die SERP-Analyse macht der Agent `serp-analyst` über die allgemeine Websuche. Sie ist nach eigenem Pflichtvorbehalt keine auf den Markt fixierte Google-SERP und keine positionsgenaue Messung. Jeder Rankinggrund ist als Hypothese zu kennzeichnen. | `CO:agents/serp-analyst.md:4`, `:54-62` |
| T10 | Modus voll liefert die Top 10 in neun Spalten (URL, Typ, Intent, Tiefe, Struktur, Trust, UX, Rankinggrund), eine SERP-DNA mit höchstens zehn Punkten und „Mindestanforderungen für SERP-Parität“. Modus kurz liefert Top 5, drei Punkte und einen eigenen Blickwinkel. | `CO:agents/serp-analyst.md:93-97`, `:131-136` |
| T11 | Der Agent erhebt weder „Ähnliche Fragen“ noch KI-Übersicht, Featured Snippet oder Wortzahl. | Lesebericht `tegards.md:79` **(B)**; in `CO:agents/serp-analyst.md:99-136` kommt keiner der Begriffe vor |
| T12 | SERP-Ergebnisse werden nie abgelegt und nie wiederverwendet: „jeder Durchgang erhebt frisch“. Eine alte Analyse dient nur als Formatvorbild (`SERP-VORBILD`). Der Agent selbst schreibt keine Dateien. | Verbot und Vorbild: `CO:skills/landingpage/SKILL.md:78`; `CO:references/landingpage/hintergrund-analysen.md:49-54`. Schreibt nie: `CO:agents/serp-analyst.md:13` |
| T13 | Im Bestand liegt genau eine SERP-Analyse, erhoben am 16.08.2026 für Glasschiebewände. | `E:\tegards\knowledge\wiki\wettbewerber\serp-analysen\2026-08-glasschiebewand.md:1-24` **(B)** |
| T14 | Der `wettbewerbs-analyst` analysiert danach die zwei bis drei besten organischen Treffer (keine Marktplätze, keine Baumärkte) auf Rankinggrund, tragende Value Propositions und Kaufpsychologie. | `CO:references/landingpage/hintergrund-analysen.md:58-81` |
| T15 | Die USP-Matrix ordnet jedes Merkmal gegen das Wettbewerbsbild aus der SERP ein: Marktstandard, teilweise, fehlt bei Wettbewerbern, einzigartig. Eigene Fakten kommen nur aus dem Produktdossier. | `CO:references/landingpage/usp-matrix.md:19-23`, `:53-54` |
| T16 | Das Seitenkonzept wird vor dem Volltext zur Freigabe vorgelegt (Zwischenfreigabe mit Value-Prop-Gate). Ohne Freigabe entsteht kein Volltext. | `CO:skills/landingpage/SKILL.md:52` |
| T17 | Teil des Konzepts ist die SERP-Paritäts-Vorschau: je Mindestanforderung das Modul, das sie abdeckt, mit erfüllt, teilweise oder bewusst nicht. | `CO:references/landingpage/seitenkonzept.md:55-58` |
| T18 | Die Zwischenfreigabe gibt es nur bei Landingpage, Kategorie- und Produktseite. Blog und Projekt haben nur das Value-Prop-Gate. | Lesebericht `tegards.md:103-105` **(B)** |
| T19 | Die Marke kommt über die Positionierungs-Weiche herein: liegt eine freigegebene Positionierungsdatei der Linie vor, sind deren Value Propositions gesetzt, und aus der SERP kommen nur neue Kandidaten zur Entscheidung. | `CO:references/querschnitt/bausteine-content-skills.md:138-146` |
| T20 | In der Instanz liegt keine Positionierungsdatei. Die Weiche ist damit heute nie aktiv, die Value Propositions entstehen je Lauf neu aus SERP, Quellen und Briefing. | Lesebericht `tegards.md:43`, `:97` **(B)**; `CO:references/landingpage/seitenkonzept.md:59-62` |

### 2.2 Wie das Seitenschema bei Tegards entsteht

| # | Aussage | Beleg |
|---|---|---|
| T21 | Die Modulfolge ist je Seitentyp ein festes Template: Landingpage 14 Module, Kategorieseite 12, Produktseite 12, Ratgeber 12, Anleitung 14, Projekt 13. | `CO:templates/landingpage.md:62-475` (Überschriften der Module 1 bis 14); Lesebericht `tegards.md:33`, `:243` **(B)** |
| T22 | Aus der SERP kommt nicht die Modulfolge, sondern die Belegung: Hauptkeyword, Marktstandard für die Vergleichstabelle, FAQ-Fragen (dritte Priorität), Pflichtthemen und die Paritäts-Checkliste. Die Regel T2 („optimale Struktur aus den Top-Rankern“) und das feste Gerüst stehen nebeneinander. | Lesebericht `tegards.md:243-249` **(B)**; `CO:references/landingpage/content-gap-und-personas.md:24-27` |
| T23 | Für Kategorie- und Produktseiten gibt es zusätzlich Referenzseiten: feste fremde Beispielseiten als Struktur-Benchmark, „kein Text-Vorbild“, mit je acht Ja/Nein-Abgleichsfragen und einer Prüfpflicht alle sechs Monate. | `CO:references/querschnitt/referenzseiten-methode.md:7-8`, `:17-21`, `:89-92`, `:102-135` |
| T24 | Eine dritte, unverbundene Quelle für den Seitenaufbau liegt im Designsystem: die Reihenfolge der Design-Bausteine je Seitenart für WordPress, WooCommerce und WPBakery. Weder sie noch commerce-os verweisen aufeinander. | `E:\TG Design\ausgelagert\seitenvorlagen.md:3`, `:28-45`, `:78-93`; Lesebericht `tegards.md:228` **(B)** |
| T25 | Die beiden Quellen weichen ab. Kaufberatung unter dem Produktraster: 300 bis 600 Wörter im Designsystem, 200 bis 300+ im Entscheidungsbaum. Das Designsystem kennt zwei Landingpage-Arten: „Landingpage (Produkt)“ mit 14 Bausteinen und „Produkt-Landingpage (einzelnes Produkt, Modellreihe)“ mit 13 Bausteinen, letztere als Muster für Lamellendächer. commerce-os hat ein Landingpage-Template („Produkt-Landingpage einer Produktlinie“). Welcher der beiden Arten es entspricht, steht nirgends. | `E:\TG Design\ausgelagert\seitenvorlagen.md:85`, `:28-45`, `:47-63`; `CO:references/zielseiten-entscheidungsbaum.md:14-15`; `CO:skills/landingpage/SKILL.md:9` |
| T26 | Strukturierte Daten je Seitentyp: Landingpage `Product` ohne Preisfelder, `FAQPage` empfohlen; Kategorie `CollectionPage` mit `ItemList`; Produktseite kein eigenes JSON-LD, weil WooCommerce und RankMath `Product` mit `offers` erzeugen; Blog `Article`, bei Anleitungen optional `HowTo`; Projekt `Article`. `BreadcrumbList` kommt immer vom Plugin. | `CO:references/landingpage/seitenkonzept.md:46-51`; `CO:templates/schema-org/landingpage-jsonld.md:72`; `CO:templates/schema-org/kategorieseite-jsonld.md:83-99`; `CO:templates/schema-org/blog-jsonld.md:51`, `:95`; Lesebericht `tegards.md:334-341` **(B)** |
| T27 | Feste Verbote im Content: keine Preise (auch nicht im Schema), keine Verfügbarkeits-Aussagen, Wettbewerber nur aggregiert und anonym. | `CO:skills/landingpage/SKILL.md:69-71`, `:76` |

### 2.3 GEO und KI-Sichtbarkeit

| # | Aussage | Beleg |
|---|---|---|
| T28 | Der `geo-validator` prüft elf Punkte mit Ja oder Nein, darunter den Answer-First-Block in den ersten 300 Zeichen, eine belegte Zahl, FAQ nach „Ähnliche Fragen“-Logik, Schema, Snippet- und Titellänge, Preisverbot. KI-Übersichten und Zitierung prüft er nicht ausdrücklich. | Lesebericht `tegards.md:277-280` **(B)**; Messkonvention `CO:references/landingpage/geo-block.md:25-31` |
| T29 | Das Playbook nennt neun Grundsätze. Die Zahlen zu Zitierfaktoren und zum Reddit-Anteil hat es selbst als nicht wörtlich belegbar korrigiert. | `TG:seo-geo-playbook.md:123-150`, `:187-198` |
| T30 | Bot-Politik: Trainings-Bots sperren, Such-Bots erlauben. `llms.txt` wird nicht empfohlen. | `TG:seo-geo-playbook.md:238-248`, `:272-278` |
| T31 | KI-Sichtbarkeit wird mit einem festen Satz von zehn Prompts gemessen. Es gibt genau eine Messung: 23.08.2026, Perplexity, je Prompt ein Lauf, Tegards wurde nie zitiert. Copilot und Googles KI-Übersichten waren nicht messbar. | `TG:ki-sichtbarkeit-log.md:40-55`, `:65-76` |
| T32 | `offpage-geo.md` und das KI-Log liest kein Skill und kein Agent. | Lesebericht `tegards.md:293`, `:351` **(B)** |

### 2.4 Frische

| # | Aussage | Beleg |
|---|---|---|
| T33 | Es gibt nur Warnungen beim Skill-Start: Marketing-Dateien, deren Prüfdatum älter als sechs Monate ist, und Dateien, die nach der Prüfung erweitert wurden („erweitert, aber ungeprüft“). Kein Abbruch, kein Auffrischungsauftrag. | `CO:references/querschnitt/frische-und-wiederverwendung.md:7-12`; `CO:references/landingpage/voraussetzungen-und-gates.md:84-92` |
| T34 | Jede Reference trägt im Kopf „Stand“ und „Nächste Prüfung“ (sechs Monate später). | `CO:references/landingpage/seitenkonzept.md:1-2`; `CO:references/zielseiten-entscheidungsbaum.md:1-2` |
| T35 | Der im Playbook genannte Pflegeweg `/seo-audit` (Module a, d, e) existiert nicht: commerce-os hat sieben Skills, keiner heißt so. | `TG:seo-geo-playbook.md:152-153`, `:226-230`; Skill-Liste `CO:skills/` (sieben Ordner) |
| T36 | Die Grundsätze des Playbooks tragen alle „Geprüft am: 2026-08-16“. Das Playbook wurde am 10.10.2026 erweitert, das Prüfdatum im Kopf steht weiter auf dem 16.08.2026. | `TG:seo-geo-playbook.md:6-7`, `:45`, `:157`, `:285` |
| T37 | Dieselbe Regel steht in drei Fassungen: FAQ-Rich-Results „seit 2023 nur noch eingeschränkt“ (Playbook), „eingestellt seit 7. Mai 2026“ (Kategorie-Template), und die Landingpage verlangt weiter genau zehn FAQ. | `TG:seo-geo-playbook.md:107-110`; Lesebericht `tegards.md:360-361` **(B)**; `CO:templates/landingpage.md:348` |

### 2.5 Produktlinien

| # | Aussage | Beleg |
|---|---|---|
| T38 | Die Landkarte hat 39 Zeilen: 18 für den Bestand (Glasschiebewände, Verglasung, Profile, Montage), 21 geplante für Lamellendächer. Für alle anderen Linien gibt es keine Zeile. | `TG:keyword-landkarte.md:77-115`, `:162` |
| T39 | Die Intents der Bestandszeilen sind „Hypothese aus Inhalt, nicht verifiziert“. Die Landkarte hat keine Datumsspalte. | `TG:keyword-landkarte.md:36-39`, `:75` |
| T40 | Ein Kannibalisierungs-Konflikt ist offen (dokumentiert mit dem Bestand vom 16.08.2026, „Entscheidung steht noch aus“): Landingpage und Shop-Kategorie Glasschiebewände zielen auf fast dasselbe Kern-Keyword. | `TG:keyword-landkarte.md:56-71`, `:77-78` |
| T41 | Für Lamellendächer ist die Leitseite entschieden (10.10.2026), keine der Zielseiten existiert. | `TG:keyword-landkarte.md:44-54`, `:124-130` |
| T42 | Live gibt es eine Leitseite mit Cluster nur für Glasschiebewände: 4 Blogartikel, 6 Projekte, 16 Kategorieseiten, 700 Produktseiten. | `TG:website-architektur.md:81-87` |
| T43 | Templates, Agenten, Schema und Playbook kennen keine Logik je Linie. Linienspezifisch sind nur Daten: Dossier, Personas, Keyword-Seeds, Sperrvermerke. | Lesebericht `tegards.md:327-328` **(B)** |
| T44 | Zwei Märkte, Österreich und Deutschland, werden je Lauf getrennt erhoben und nie vermischt. | `CO:references/landingpage/hintergrund-analysen.md:24-26`, `:37-40` |

## 3. Recherche Stand 2026

Der vollständige Bericht mit Quellenstufe je Aussage liegt unter `docs/umbau/dossiers/03-lesen/recherche.md` (351 Zeilen,
Subagent Sonnet 5.5, Abruf 16.11.2026). Die Spalte „Geprüft“ sagt, ob ich die Aussage am 16.11.2026 selbst an der
Originalseite nachgeprüft habe (WebFetch liefert eine Zusammenfassung der Seite mit wörtlichen Zitaten, keinen Volltext).

| # | Aussage | Quelle | Geprüft |
|---|---|---|---|
| R1 | Google verlangt für KI-Übersichten und KI-Modus nichts Zusätzliches: keine Sonderoptimierung, kein eigenes Schema, keine Sonderdateien. Voraussetzung ist, dass die Seite indexiert ist und mit Snippet gezeigt werden darf. Aus Googles Sicht ist das Optimieren für KI-Suche weiterhin SEO. | https://developers.google.com/search/docs/appearance/ai-features ; https://developers.google.com/search/docs/fundamentals/ai-optimization-guide | ja, bestätigt |
| R2 | `llms.txt` nutzt die Google-Suche nicht. | https://developers.google.com/search/docs/fundamentals/ai-optimization-guide ; Changelog-Eintrag 15.06.2026 unter https://developers.google.com/search/updates | ja, bestätigt |
| R3 | Strukturierte Daten bringen keinen belegten Vorteil bei KI-Zitaten. Ahrefs, 11.05.2026, 1.885 Seiten mit nachträglich ergänztem JSON-LD gegen Kontrollseiten: KI-Übersichten −4,6 %, KI-Modus +2,4 %, ChatGPT +2,2 % (beide nicht signifikant). Einschränkung der Studie: nur Seiten, die schon oft zitiert wurden. | https://ahrefs.com/blog/schema-ai-citations/ | ja, bestätigt |
| R4 | Nur gut ein Drittel der in KI-Übersichten zitierten Adressen steht für dieselbe Suche in den Top 10 (37,9 %), rund 31 % stehen jenseits von Platz 100. Ahrefs, 02.03.2026, 863.000 Suchen. Die Methode wurde gegenüber 2025 geändert, die Werte sind nicht direkt vergleichbar. | https://ahrefs.com/blog/ai-overview-citations-top-10/ | ja, bestätigt |
| R5 | KI-Antworten wechseln schnell: der Inhalt einer KI-Übersicht ändert sich bei 70 % der aufeinanderfolgenden Beobachtungen, im Mittel alle 2,15 Tage; 45,5 % der zitierten Quellen sind dabei neu. Ahrefs, 11.11.2025, über 43.000 Suchen. | https://ahrefs.com/blog/ai-overview-change/ | ja, bestätigt |
| R6 | Das FAQ-Rich-Result erscheint seit dem 07.05.2026 nicht mehr (Eintrag im Änderungsprotokoll vom 08.05.2026), die Dokumentation wurde am 15.06.2026 entfernt. Am 09.09.2025 fielen fünf weitere Typen weg. Breadcrumbs erscheinen seit Januar 2025 nur noch auf dem Desktop. | https://developers.google.com/search/updates | ja, bestätigt |
| R7 | Händler-Einträge (Merchant Listings) gibt es nur für Seiten, auf denen ein einzelnes Produkt gekauft werden kann, mit `Offer` (nicht `AggregateOffer`). Für Listen- und Kategorieseiten empfiehlt Google das Markup nicht. | https://developers.google.com/search/docs/appearance/structured-data/merchant-listing | ja, bestätigt |
| R8 | Laut Googles Leitfaden gibt es keine ideale Seitenlänge und keine Pflicht, Inhalte in kleine Stücke zu teilen. Eigene Seiten für jede Suchvariante können gegen die Regel zu skalierten Inhalten verstoßen. | https://developers.google.com/search/docs/fundamentals/ai-optimization-guide | ja, bestätigt |
| R9 | Der Search-Console-Bericht zu generativer KI (Beitrag vom 03.06.2026, laut Hinweis seit 31.08.2026 für alle Websites) zeigt nur Impressionen, KI-Übersichten und KI-Modus zusammen, keine Klicks. | https://developers.google.com/search/blog/2026/06/gen-ai-performance-reports | ja, bestätigt; der im Bericht genannte Ausschluss-Schalter steht nicht in diesem Beitrag, nur als Changelog-Eintrag vom 21.10.2026 |
| R10 | KI-Übersichten gibt es in Deutschland seit 26.03.2025; laut SISTRIX erschienen sie am 06.11.2026 bei 57,9 % der beobachteten deutschen Keywords. Österreich ist nicht verifiziert. | `recherche.md` Kernaussage 6 | nein |
| R11 | Der WooCommerce-Kern gibt bei variablen Produkten ohne gewählte Variante `AggregateOffer` aus. RankMath liefert das Produktschema automatisch und für Kategorien `CollectionPage`; `ItemList`, `Speakable` und mehrere Schemas je Seite gibt es nur in der Bezahlfassung. | `recherche.md:238-242` | nein |
| R12 | Googles Änderungsprotokoll der Dokumentation hat 2026 zwei bis sechs Einträge im Monat. Core- und Spam-Updates laut Status-Dashboard: 2025 vier, 2026 bis Mitte November sieben (davon drei Core). Am 10.11.2026 begann ein Core-Update, dessen Ende nicht geprüft ist. | `recherche.md:279`, `:286-305` | nein |
| R13 | Bewertung des Rechercheurs, aus R4, R6 und R8 abgeleitet: Die Top-Treffer zu analysieren taugt als Prüfung von Suchabsicht, Seitentyp und Lücken, nicht als Schablone für Aufbau und Markup. | `recherche.md:192-196` | Ableitung, keine Messung |

**Was das für die gelesenen Regeln heißt:**

- Everlasts Grundsatz E42 und die Aussagen zu `llms.txt` und FAQ (E44, E49) stimmen mit R1, R2 und R6 überein. Das Entfall-Datum
  in `ELS:amm-seo/references/schema-vorlagen.md:161` (Doku entfernt 2026-06-15) ist richtig.
- Die Zahlenregel „Antwortblock 134 bis 167 Wörter“ (Everlast W5, Tegards laut Lesebericht `tegards.md:281` **(B)**) hat nach R8
  keine Grundlage bei Google. Dasselbe gilt für Tegards’ Messkonvention „Antwort in den ersten 300 Zeichen“ (T28) als harte
  Grenze. „Antwort zuerst“ bleibt als Schreibregel durch Googles Snippet-Doku gedeckt (`ELS:amm-blog/references/zitierfaehigkeit.md:24-27`).
- Tegards’ Begründung, FAQ- und HowTo-Markup nütze der „maschinellen Extrahierbarkeit für KI-Suche“
  (`TG:seo-geo-playbook.md:107-110`), ist nach R1 und R3 nicht belegt.
- Tegards’ Regel T1 („zuerst die ranking-optimale Variante aus den Top-Treffern“) stützt sich auf eine Quelle, die nach R4
  nur einen Teil des Wettbewerbs in KI-Antworten zeigt, und nach R13 nicht als Bauvorlage taugt.
- Die einzige KI-Messung bei Tegards (T31, ein Lauf je Frage) sagt nach R5 fast nichts; Everlasts zehn Läufe je Zeile (E46)
  gehen in die richtige Richtung.
- `Product` ohne Preisfelder auf der Landingpage (T26) kann nach R7 kein Händler-Eintrag werden.

## 4. Unterschiede und Lücken beider Seiten

### 4.1 Gegenüberstellung

| Thema | Everlast | Tegards (commerce-os) |
|---|---|---|
| Was zuerst kommt | Marke: Positionierung, dann Säulen, dann Suchverhalten (E1 bis E4). | Suche: Keyword-Gate, SERP, dann Abgleich mit eigenen Quellen (T1 bis T3). |
| Woher Value Propositions kommen | Aus `positionierung.md`, `usps.md`, `copystrategie.md`; jeder Text wird dagegen geprüft (`ELS:amm-copywriting/SKILL.md:61`). | Je Lauf neu aus SERP, Wettbewerb, Quellen und Briefing; die Marken-Weiche ist heute nie aktiv (T19, T20). |
| Was die Suchergebnisse bestimmen | Thema, Format, Seitenform (E24, E25). Nicht den Aufbau einer Verkaufsseite. | Seitentyp, Pflichtthemen, Marktstandard, FAQ-Fragen, Paritäts-Checkliste (T17, T22). Nicht die Modulfolge. |
| Woher der Seitenaufbau kommt | Sektionsplan: eine Sektion räumt eine Kaufbremse weg, Einstieg nach Awareness (E32). Blog: sechs Baupläne nach Suchintention (E37). | Festes Template je Seitentyp (T21), dazu Referenzseiten (T23) und unverbunden die Design-Seitenvorlagen (T24). |
| Seitentypen | Anmeldeseite, Sales-Page, Kursseite, Produktseite, Blog (E31, E37). Keine Kategorieseite (1.4). | Landingpage, Kategorieseite, Produktseite, Ratgeber, Anleitung, Projekt (T21). |
| Suchdaten | Bezahlt und gemessen: DataForSEO für Volumen und echte Seite eins, Search Console für die eigene Domain (E20, E23). | Kostenlos und geschätzt: Suggest-Endpunkte, allgemeine Websuche, keine Volumen (T4, T9). |
| Keyword-Ablage | Keyword-Set als Cluster mit Volumen, Absicht, Priorität und heutiger Seite (`ELS:amm-keyword-research/SKILL.md:57-64`). Keine Regel „genau eine Zielseite“ als Spalte, aber als Kernregel (`ELS:amm-seo/SKILL.md:62`). | Landkarte: Keyword, Intent, genau eine Zielseite, Status; Konflikte werden nur gemeldet (T5, T40). Keine Volumen, kein Datum (T39). |
| Freigabe vor dem Text | Checkpoints des webdesigners (Ziel, Design-Richtung, Erster Eindruck …), Briefing beim Blog (`EL:.claude/agents/references/webdesigner-laufzeit.md:43-49`; `ELS:amm-blog/references/briefing.md:3-4`). | Zwischenfreigabe des Seitenkonzepts mit Value-Prop-Gate (T16). |
| Strukturierte Daten | Kursanbieter: Organization, Course, Article, Event (E40). | Shop: Product, CollectionPage mit ItemList, Article, HowTo; Arbeitsteilung mit WooCommerce und RankMath (T26). |
| KI-Sichtbarkeit messen | Testfragen-Protokoll mit festem Schlüssel und zehn Läufen je Zeile (E46). | Fester Satz von zehn Prompts, ein Lauf, eine Messung (T31). |
| Regeln und Quellen | Je Skill eine `herkunft.md` mit Quelle und Abrufdatum; eine Regel steht bei einem Skill, andere verweisen (`ELS:amm-blog/references/on-page.md:81-83`). | Regeln stehen mehrfach: Playbook, Templates, Agenten, Kontrakte; daraus entstehen Widersprüche (T37). |
| Website-Technik | Astro und Cloudflare; Bestand in WordPress läuft über Workflow B (E36). | WordPress, WooCommerce, RankMath, WPBakery (T24, T26). |
| Produktlinien | Suchverhalten und Säulen einmal auf Markenebene (1.4). | Landkarte nur für zwei Linien gefüllt; keine Logik je Linie (T38, T43). |

### 4.2 Lücken beider Seiten

| # | Lücke | Bei wem | Beleg |
|---|---|---|---|
| L1 | Kein aktiver Mechanismus, der SEO- und GEO-Regelwissen prüft. Everlast hat Handanweisungen, Tegards einen Verweis auf einen nicht vorhandenen Skill. | beide | 1.6 erste Zeile; T35 |
| L2 | Die SERP-Analyse einer Seite wird nicht aufbewahrt. Bei Tegards bewusst nie, bei Everlast gibt es sie für Verkaufsseiten nicht. Ein Vergleich über die Zeit ist damit nicht möglich. | beide | T12; 1.3 „Was fehlt“ |
| L3 | Marke und Suche treffen sich nicht an einer festen Stelle. Everlast führt die Suche nicht bis in den Seitenaufbau, Tegards führt die Marke nur über eine Weiche herein, die leer ist. | beide | 1.3; T20 |
| L4 | Der Seitenaufbau hat mehrere unverbundene Quellen. Everlast: Sektionsplan und Copy-Sektionstypen. Tegards: Templates, Referenzseiten, Design-Seitenvorlagen. | beide | E31 bis E34, `ELS:amm-copywriting/references/formeln-und-sektionen.md:70-96`; T21, T23, T24 |
| L5 | Keine Vorlage für Shop-Seitentypen und kein Shop-Schema. | Everlast | 1.4 „Was fehlt“, E40 |
| L6 | Keine gemessenen Suchdaten: keine Volumen, keine echte lokalisierte Seite eins, keine KI-Übersicht in der Analyse. | Tegards | T4, T9, T11 |
| L7 | Die Skills der Suchkette sind nicht in das Team eingebunden und widersprechen sich im Ablageort. | Everlast | E17, E18, W1, W2 |
| L8 | Sieben von neun Produktlinien haben kein Suchwissen. | Tegards | T38 |
| L9 | Off-Page (Bewertungen, Foren, Fremdnennungen) ist auf beiden Seiten nur beschrieben. Everlast sagt offen, dass ein Agent das nicht leistet. | beide | E47; T32 |
| L10 | KI-Sichtbarkeit wurde bei Tegards einmal gemessen, mit einem Lauf je Frage. Nach Everlasts Rechnung trennt ein Lauf „nie“ nicht von „manchmal“. | Tegards | T31; `ELS:amm-seo/references/ki-suche.md:127-136` |
| L11 | Dreifache Bedeutung von „Pillar“: Content-Säule der Marke (Everlast, Feld `pillar`), Hauptseite eines Keyword-Clusters (Everlast, `cluster.md`), Leitseite einer Produktlinie mit Cluster (Tegards). | beide | `EL:pipelines/README.md:75-78`; `ELS:amm-keyword-research/references/cluster.md:5-7`; `TG:seo-geo-playbook.md:34-36` |

## 5. Optionen und Empfehlung je Thema

Jedes Thema nennt die Optionen mit Vor- und Nachteilen, die Empfehlung und die Zeile „Gelesen“. Bausteine, die es bei
Everlast nicht gibt, tragen **neu, nicht Everlast** und den heutigen Fall.

### D1 Wer führt: Marke oder Suche

| Option | Vorteil | Nachteil |
|---|---|---|
| A Everlast pur: Marke führt, die Suche bestimmt nur Thema und Format | einfache Linie, jede Zeile prüfbar gegen die Positionierung | Verkaufsseiten entstehen ohne Blick auf die Suchergebnisse; Pflichtthemen fehlen (L3) |
| B Tegards pur: zuerst die ranking-optimale Variante, dann Abgleich | deckt, was Suchende erwarten | Value Propositions entstehen je Lauf neu (T20); die Quelle zeigt nach R4 nur einen Teil des Wettbewerbs; Kopieren der Struktur ist nach R13 riskant |
| C Arbeitsteilung mit fester Übergabe | jede Seite hat eine klare Zuständigkeit; nutzt beide Stärken | eine Regel mehr, die erklärt werden muss |

**Empfehlung C.** Die Marke setzt: wofür wir stehen, Value Propositions, Personas, Ton, Säulen, Verbote. Die Suche
entscheidet: ob eine Seite entsteht, welcher Seitentyp, welche Pflichtthemen und Fragen, welcher Wortlaut. Die
Suchergebnisse liefern nie Value Propositions und nie Fakten. Ein neues Argument aus der Suche wird ein Vorschlag für die
Positionierung und gilt erst nach Markus’ Freigabe dort. Das ist Tegards’ Weiche (T19) als Normalfall statt als Ausnahme.
Die „Positionierungsdatei je Linie“ sind die Everlast-Dateien `positionierung.md`, `usps.md` und `produkte/<linie>/offer.md`;
eine zusätzliche Datei entsteht nicht. Tegards’ Regel „SEO-Optimum-First“ (T1, T2) entfällt.

Gelesen: `ELS:amm-copywriting/SKILL.md`, `ELS:amm-content-strategie/references/saeulen.md`,
`CO:references/querschnitt/bausteine-content-skills.md` (Zeilen 15-26, 76-88, 127-146), `CO:skills/landingpage/SKILL.md`,
`CO:references/landingpage/seitenkonzept.md`, Recherche R4, R13.

### D2 Wo das Suchwissen liegt

| Option | Vorteil | Nachteil |
|---|---|---|
| A Everlast: `suchverhalten.md` und `keyword-set.md` unverändert | keine Abweichung | keine Spalte „Zielseite“ und kein Status; Ablageort widersprüchlich (W1) |
| B Tegards: Landkarte und Architekturdatei | Kannibalisierung sichtbar | keine Volumen, kein Datum (T39); eigener Ordner neben den Everlast-Fächern |
| C Ein Keyword-Set am Everlast-Ort, mit Tegards-Spalten und einem Abschnitt je Linie | ein Ort; Kannibalisierung über alle Linien prüfbar; Herkunft und Datum je Zeile | die Datei wächst mit jeder Linie |
| D Je Linie eine Keyword-Datei im Produktordner | passt zum Laden je Produkt | Kollisionen zwischen Linien sieht niemand; neun Dateien |

**Empfehlung C.** Ort: `strategie/positionierung/keyword-set.md`. Dorthin schreibt der Skill, und `/seo-komplett-audit`
darf außerhalb von `daten/` und `inbox/` nur im Ordner `strategie/positionierung/` ändern
(`EL:.claude/commands/seo-komplett-audit.md:86`), nicht unter `seo/`. Der Stub `seo/keyword-set.md` entfällt.
Je Zeile: Suchbegriff, Absicht, Zielseite (genau eine), Status, Volumen, Herkunft (gemessen, geschätzt, angenommen) mit
Datum. `suchverhalten.md` bleibt eine Datei auf Markenebene. Der Ist-Bestand der Seiten kommt in den Abschnitt Bestand von
`kanaele/websites.md`, den der Loop schon liest (`EL:tools/seo-audit/auftrag.md:24`).

Gelesen: `ELS:amm-keyword-research/SKILL.md`, `ELS:amm-seo-content/SKILL.md`, `EL:seo/keyword-set.md`,
`EL:tools/seo-voraussetzungen.py`, `EL:tools/seo-audit/auftrag.md`, `TG:keyword-landkarte.md`, `TG:website-architektur.md`.

### D3 Wie der Seitentyp entschieden wird

| Option | Vorteil | Nachteil |
|---|---|---|
| A Everlast: Tabelle Absicht → Seitenform (E24) | kurz | kennt keine Kategorie- und Produktseite, keine Rollen |
| B Tegards-Entscheidungsbaum mit Rollen (T6, T7), einmal abgelegt | passt zum Shop; löst den heutigen Fall | Schwellen (drei Blog-Themen, zwei Projekte) sind Hausregeln ohne Messung |

**Empfehlung B, neu, nicht Everlast.** Heutiger Fall: der offene Konflikt zwischen Landingpage und Kategorie (T40) und die
21 geplanten Lamellendach-Zeilen ohne Seite (T41). Der Baum steht einmal, als Referenz des Keyword-Skills, nicht doppelt
(T8). Everlasts Grundsatz „die Absicht entscheidet die Seitenform“ bleibt der Obersatz. Die Schwellen werden als Hausregel
gekennzeichnet.

Gelesen: `ELS:amm-keyword-research/references/cluster.md`, `CO:references/zielseiten-entscheidungsbaum.md`,
`CO:references/keyword-recherche/zielseiten-zuordnung.md`, `TG:website-architektur.md`, `TG:keyword-landkarte.md`.

### D4 Womit Suchdaten erhoben werden

| Option | Vorteil | Nachteil |
|---|---|---|
| A Tegards: nur kostenlose Quellen (Suggest, allgemeine Websuche) | keine Kosten, kein Konto | keine Volumen, keine echte lokalisierte Seite eins, keine KI-Übersicht (L6) |
| B Everlast: DataForSEO und Search Console | gemessene Daten der eigenen Domain; Volumen; Seite eins mit KI-Übersicht | Konto und Kosten (rund 0,60 USD je vollständigem Keyword-Audit einer Domain, nicht je Suchbegriff; `ELS:amm-keyword-research/SKILL.md:33`, `EL:tools/dataforseo/README.md:18`); Dienstkonto für die Search Console einrichten |
| C B, dazu Tegards’ Suggest-Abfrage als kostenlose Quelle für Wortlaute | Wortlaute ohne Kosten, Zahlen nur wo nötig | zwei Wege im selben Skill |

**Empfehlung C.** Die Search Console ist kostenlos und misst die eigene Domain, sie kommt in jedem Fall. DataForSEO
braucht Markus’ Entscheidung zu Konto und Budget. Ohne DataForSEO bleibt jede Nachfrage auf Stufe „gehört“ oder
„Vermutung“ (E8), und die Analyse sieht KI-Übersichten nicht.

Gelesen: `ELS:amm-keyword-research/SKILL.md`, `EL:tools/dataforseo/README.md`, `EL:tools/gsc/README.md`,
`CO:skills/keyword-recherche/SKILL.md`, `CO:agents/serp-analyst.md`.
Nicht gelesen: die Werkzeuge `dfs` und `gsc` selbst, also auch nicht, ob sie unter Windows laufen (P7).

### D5 Die Suchergebnis-Analyse einer Seite

| Option | Vorteil | Nachteil |
|---|---|---|
| A Keine (Everlast) | nichts zu bauen | Verkaufsseiten ohne Pflichtthemen aus der Suche (L3) |
| B Tegards-Agenten `serp-analyst` und `wettbewerbs-analyst` 1:1 | erprobt | zwei weitere Agenten gegen die feste Entscheidung „Fachagenten 1:1 nach Everlast“; Websuche statt echter Seite eins; nichts wird abgelegt (L2) |
| C Ein Skill, den der planende Agent lädt; Ablage als datierter Lauf | kein neuer Agent; Daten aus `dfs serp`; Vergleich über die Zeit möglich | ein neuer Skill |

**Empfehlung C, neu, nicht Everlast** (`tg-serp-analyse`). Heutiger Fall: die geplante Leitseite Lamellendächer (T41).
Bei Everlast wohnt Bedienwissen im Skill, ein neuer Agent braucht eigenes Handwerk, eigene Werkzeuge und eine scharfe
Grenze (`EL:.claude/head-of-marketing.md:105-106`).

- **Was der Skill liefert:** Verteilung der Seitentypen, Suchabsicht, Pflichtthemen (Fragen, die alle Top-Treffer
  beantworten), „Ähnliche Fragen“, KI-Übersicht ja oder nein mit zitierten Domains, erwarteter Marktstandard. Jeder
  Rankinggrund ist eine Hypothese (T9).
- **Was er nicht liefert:** eine Gliederung zum Nachbauen und das Markup der Wettbewerber (R13, R6).
- **Tiefe:** voll für Seiten mit eigenem Suchbegriff (Leitseite, Kategorie- und Produktseite als `zielseite`); beim Blog
  bleibt Everlasts „Blick auf die ersten Treffer“ (E25).
- **Wettbewerber:** das genaue Lesen von zwei bis drei Top-Seiten ist ein Schritt desselben Skills; was über einen
  Wettbewerber dauerhaft gilt, wird eine Beobachtung in dessen Datei (P2, A9).
- **Ablage:** `daten/JJMMTT-serp-<slug>/`, wie jeder Messlauf bei Everlast (`ELS:amm-seo/references/befund-format.md:13`).
  Kein Wissensfach.
- **Wiederverwendung:** bis 30 Tage für denselben Suchbegriff und Markt, danach neu. Der Teil zur KI-Übersicht wird nie
  wiederverwendet (R5). Die 30 Tage sind eine Hausregel: strenger als Everlasts Stichtag von bis zu zwei Monaten
  (`EL:.claude/commands/seo-komplett-audit.md:49-50`), lockerer als Tegards’ „nie“ (T12).
- **Altbestand:** die eine vorhandene Analyse (T13) wird nicht überführt, sie dient höchstens als Formatvorlage.

Gelesen: `CO:agents/serp-analyst.md`, `CO:references/landingpage/hintergrund-analysen.md`,
`CO:references/landingpage/content-gap-und-personas.md`, `ELS:amm-keyword-research/SKILL.md`,
`ELS:amm-blog/references/briefing.md`, `EL:.claude/head-of-marketing.md`, Recherche R4, R5, R13.
Nicht gelesen: `CO:agents/wettbewerbs-analyst.md` (nur Lesebericht), `CO:kontrakte.md`.

### D6 Wie das Seitenschema entsteht

| Option | Vorteil | Nachteil |
|---|---|---|
| A Everlast: Sektionsplan nach Kaufbremsen, Blog nach Bauplänen | jede Sektion hat einen prüfbaren Zweck | kein Gerüst für Shop-Seitentypen (L5); Suche fehlt |
| B Tegards: festes Template je Seitentyp plus Paritäts-Checkliste | vollständig, erprobt | starr (genau 14 Module, genau zehn FAQ); drei unverbundene Quellen (L4) |
| C Ein Grundgerüst je Seitentyp, Belegung aus drei Eingängen, Freigabe vor dem Text | ein Ort; Marke, Suche und Fakten treffen sich an einer Stelle | die Gerüste müssen einmal zusammengeführt werden |

**Empfehlung C.**

- **Ein Ort je Seitentyp:** eine Referenz des Sektionsplan-Skills je Seitentyp mit den Pflichtbausteinen und ihrer Folge.
  Sie wird aus dem commerce-os-Template und der Design-Seitenvorlage zusammengeführt und nennt die Bausteine beim Namen des
  Designsystems (T24). Welche Seitentypen es gibt und wie tief jedes Gerüst ist, entscheidet P4.
- **Drei Eingänge, feste Rangfolge:** 1. Fakten, Recht und Verbote. 2. Marke: Value Propositions und das Gewicht der
  Kaufbremsen. 3. Suche: Seitentyp und Pflichtthemen. Das Design bestimmt nur die Form des Bausteins.
- **Die Übergabe Suche → Seite:** Jedes Pflichtthema aus der Suchergebnis-Analyse bekommt im Sektionsplan eine Zeile:
  erfüllt durch Sektion X, im Fragenblock beantwortet, oder bewusst nicht mit Grund. Das ist Tegards’ Paritäts-Vorschau (T17)
  in Everlasts Tabelle (E33). Ein Pflichtthema wird nur dann eine eigene Sektion, wenn sie eine Kaufbremse wegräumt
  (`ELS:amm-sektionsplan/SKILL.md:42`).
- **Freigabe vor dem Text:** Der Sektionsplan ist das Seitenkonzept. Markus gibt ihn frei, bevor Copy entsteht. Das ist
  Tegards’ Zwischenfreigabe (T16) und Everlasts Checkpoint-Prinzip.
- **Keine Zahlenvorgaben ohne Grundlage:** „genau zehn FAQ“ und feste Wortkorridore gelten als Startwerte, nicht als
  Pflicht (R8).

Gelesen: `ELS:amm-sektionsplan/` (alle drei Dateien), `ELS:amm-copywriting/references/formeln-und-sektionen.md`,
`EL:.claude/agents/references/webdesigner-workflows.md`, `CO:references/landingpage/seitenkonzept.md`,
`CO:references/querschnitt/referenzseiten-methode.md`, `CO:templates/landingpage.md` (nur die Überschriften),
`E:\TG Design\ausgelagert\seitenvorlagen.md`.
Nicht gelesen: die Templates für Kategorie, Produkt, Blog und Projekt (nur Lesebericht).

### D7 Strukturierte Daten je Seitentyp

| Option | Vorteil | Nachteil |
|---|---|---|
| A Everlast-Vorlagen unverändert | nichts zu tun | Kursanbieter, kein Shop (E40) |
| B Tegards-Templates 1:1 | Shop-Typen vorhanden | enthält Blöcke ohne belegte Wirkung: `FAQPage`, `HowTo`, `speakable`, `Product` ohne Preis (R3, R6, R7) |
| C Shop-Vorlagen neu, nach dem Grundsatz „Markup nur, wo Google es anzeigt oder das Plugin es ohnehin liefert“ | wenig Pflege; stimmt mit dem Stand 2026 | weniger Markup als heute |

**Empfehlung C.** Je Schema-Typ gibt es genau eine führende Quelle, Plugin oder Skill (Tegards-Regel laut Lesebericht
`tegards.md:342` **(B)**).

| Seitentyp | Markup | Quelle |
|---|---|---|
| Produktseite | `Product` mit `Offer` | WooCommerce und RankMath; Prüfpunkt: variable Produkte geben `AggregateOffer` aus (R11) |
| Kategorieseite | `CollectionPage`, kein `Product` auf der Liste (R7) | RankMath |
| Leitseite, Landingpage | keines über das hinaus, was das Plugin liefert | Plugin |
| Ratgeber, Anleitung, Projekt | `Article` mit Autor und Datum | Plugin, sonst Vorlage aus `amm-seo` |
| Startseite | `Organization` | Vorlage aus `amm-seo` |
| überall | `BreadcrumbList` | Plugin |

Das sichtbare Fragenmodul bleibt. `FAQPage`, `HowTo`, `speakable` und `Product` ohne Preis werden nicht mehr erzeugt und
kommen mit Auslöser auf `SPAETER.md`.

Gelesen: `ELS:amm-seo/references/schema-vorlagen.md`, `ELS:amm-seo/references/herkunft.md`,
`CO:references/landingpage/seitenkonzept.md`, Überschriften und Typen in `CO:templates/schema-org/*.md`, Recherche R3, R6, R7, R11.
Nicht gelesen: die Schema-Templates im Volltext, `CO:templates/woocommerce/`, `CO:templates/rankmath/`.

### D8 GEO: Regeln und Messung

**Regeln.**

| Option | Vorteil | Nachteil |
|---|---|---|
| A Everlast: `ki-suche.md` und die drei Muster in `amm-blog` | jede Regel hängt an einer Google-Seite (E45, E48); stimmt mit R1 | – |
| B Tegards: elf Prüfpunkte des `geo-validator`, GEO-Block, Playbook | fester Prüfer | harte Zahlen ohne Grundlage (300 Zeichen, zehn FAQ); Begründungen teils widerlegt (R3) |

**Empfehlung A.** Die Zahlenregeln entfallen auf beiden Seiten: 134 bis 167 Wörter (W5), 300 Zeichen (T28), genau zehn FAQ
(T37). „Antwort zuerst“, „Herkunft im selben Satz“ und „Text trägt, was Grafik und Markup sagen“ bleiben. Die GEO-Punkte
werden Teil der Inhaltsrubrik je Auftragsart, die P1 dem Codex-Prüfweg zugewiesen hat; ein eigener Prüf-Agent kommt nicht.
`llms.txt` wird nicht gebaut (R2).

**Messung.**

| Option | Vorteil | Nachteil |
|---|---|---|
| A Tegards-Log: zehn Prompts, ein Lauf | wenig Aufwand | trennt nach R5 und Everlasts Rechnung „nie“ nicht von „manchmal“ (L10) |
| B Everlast-Testfragen-Protokoll: fünf bis zehn Fragen, zehn Läufe je Zeile | belastbar | viele Abfragen von Hand |
| C Drei Stufen nach Aufwand | das Billige läuft immer, das Teure selten | drei Quellen statt einer |

**Empfehlung C.** Stufe 1: der Search-Console-Bericht zu generativer KI (R9), kostenlos, nur in der Oberfläche (E50).
Stufe 2: bei jedem Komplett-Audit `dfs serp` für die zehn wichtigsten Begriffe ohne Marke (E30), setzt D4 voraus.
Stufe 3: Everlasts Testfragen-Protokoll mit fünf Fragen, nur im Komplett-Audit. Die zehn alten Prompts (T31) sind der
Vorrat für die Fragen; die alte Messung ist nicht vergleichbar und wird nicht fortgeschrieben.

**Off-Page.** Bewertungen, Foren und Fremdnennungen erzeugt kein Agent (E47). Dafür entsteht kein Baustein;
`offpage-geo.md` ist Quelle für Station 14, die operativen Teile kommen auf `SPAETER.md`.

**Bot-Politik.** Beide Seiten sagen dasselbe: Suchcrawler erlauben, Trainingscrawler nach Markus’ Entscheidung sperren
(E43, T30). Die Entscheidung steht einmal in `kanaele/websites.md`.

Gelesen: `ELS:amm-seo/references/ki-suche.md`, `ELS:amm-blog/references/zitierfaehigkeit.md`,
`ELS:amm-seo-content/references/zitierfaehigkeit.md`, `ELS:amm-seo-audit/references/kriterien.md`, `EL:tools/gsc/README.md`,
`CO:references/landingpage/geo-block.md`, `TG:seo-geo-playbook.md`, `TG:ki-sichtbarkeit-log.md`, Recherche R1 bis R5, R9.
Nicht gelesen: `CO:agents/geo-validator.md`, `TG:offpage-geo.md` (beide nur Lesebericht).

### D9 SEO- und GEO-Wissen frisch halten

| Option | Vorteil | Nachteil |
|---|---|---|
| A Everlast wie es ist: `herkunft.md` mit Abrufdatum, Handanweisung „vor jedem Audit prüfen“ | nichts zu bauen | hängt daran, dass jemand ein Audit startet (L1) |
| B Tegards-Kopf „Nächste Prüfung“ je Datei, Warnung beim Start | Frist sichtbar | warnt nur; die Regeln stehen mehrfach und laufen auseinander (T37) |
| C Ein Ort je Regel, dazu ein monatlicher Regel-Check gegen feste Primärquellen | Änderungen kommen an, ohne dass jemand daran denkt | ein Loop mehr |

**Empfehlung C.**

1. **Ein Ort je Regel.** SEO- und GEO-Regeln stehen nur in den Referenzen von `tg-seo`, mit Quelle und Abrufdatum in
   `herkunft.md` (Everlast). Andere Skills verweisen dorthin. Ein Playbook als zweite Regelquelle entsteht nicht.
2. **Monatlicher Regel-Check, neu, nicht Everlast.** Heutiger Fall: Die FAQ-Regel steht in drei Fassungen (T37), obwohl
   Googles Änderungsprotokoll die Abkündigung am 08.05.2026 nennt (R6); das Playbook wurde zuletzt am 16.08.2026 geprüft und nennt weiter
   den Stand 2023 (T36). Der Check ist ein Auftrag mit fester Quellenliste nach dem Muster des Branchen-Update-Loops
   (`ELS:amm-loops/references/loops-workspace.md:193-204`): Googles Änderungsprotokoll der Dokumentation, das
   Status-Dashboard der Updates, die Bot-Seiten von OpenAI, Anthropic und Perplexity, das RankMath-Änderungsprotokoll. Er
   schreibt nur dann einen Brief, wenn ein Eintrag eine Regel in `tg-seo` berührt, und ändert selbst nichts. Die Änderung an
   der Referenz ist eine Bau-Änderung mit neuem Abrufdatum.
3. **Daten tragen ihr Datum.** Jeder Messlauf liegt in einem Datumsordner, jede Zeile im Keyword-Set trägt Herkunft und
   Datum (D2, D5).
4. **Wissensdateien.** `suchverhalten.md` und `keyword-set.md` fallen unter `tg-wissen-pruefen` aus P2; dafür entsteht
   nichts Zusätzliches.
5. **Veröffentlichte Inhalte.** Everlasts Kadenz je Format und der Loop Content-Verfall (1.6) sind Sache von P4 und P9.

Gelesen: `ELS:amm-seo/references/herkunft.md`, `ELS:amm-seo/references/ki-suche.md`,
`ELS:amm-seo/references/schema-vorlagen.md`, `ELS:amm-loops/references/loops-workspace.md`,
`ELS:amm-loops/assets/branchen-update/auftrag.md`, `ELS:amm-blog/references/refresh.md`,
`CO:references/querschnitt/frische-und-wiederverwendung.md`, `TG:seo-geo-playbook.md`, Recherche R6, R12.
Nicht gelesen: `ELS:amm-loops/SKILL.md`, `anatomie-und-state.md`, `guardrails.md` und der Träger `lauf.sh`.

### D10 Welche Everlast-SEO-Skills kommen

| Option | Vorteil | Nachteil |
|---|---|---|
| A Alle vier Skills und der Command 1:1 | nichts geht verloren | sieben Widersprüche (W1 bis W7) kommen mit; drei Audit-Wege; zwei Wege zum Suchartikel |
| B Nur `amm-seo` | sauber eingebunden | keine Keyword-Recherche, keine gemessenen Daten (L6 bliebe) |
| C Bereinigte Kette | ein Weg je Aufgabe | einmaliger Zusammenführungs-Aufwand |

**Empfehlung C.**

| Baustein | Status | Begründung |
|---|---|---|
| `amm-seo` → `tg-seo` | anpassen | Regeln, Seite, JSON-LD, KI-Suche; On-Page und Schema von Kursanbieter auf Shop umschreiben (E39, E40, D7) |
| `amm-keyword-research` → `tg-keyword-research` | anpassen | dazu Tegards’ Suggest-Wortlaute, der Entscheidungsbaum und „genau eine Zielseite“ (D2 bis D4) |
| `/seo-komplett-audit` | anpassen | der eine Audit-Weg auf Zuruf; Befunde nach `projekte/JJMMTT-seo-<slug>/befunde.md`, damit der Steuerstand sie zeigt (W2) |
| `amm-seo-audit` | weglassen | doppelt zu Modus A von `amm-seo`; braucht Werkzeuge, die nicht im Paket liegen (W3). Übernommen werden die Konfidenzstufen (E22) und die Crawler-Prüfung mit Versionskennung (`ELS:amm-seo-audit/references/kriterien.md:39-45`), als Teil von `tg-seo` |
| `amm-seo-content` | weglassen | zweiter Weg zum Suchartikel neben `amm-blog`. Die Lückenwahl aus der Search Console bleibt als Ideenquelle der Content-Strategie (`ELS:amm-content-strategie/references/auswahl.md:21`) |
| wöchentlicher Loop seo-audit und geplante Aufgabe „neue SEO-Seite“ | SPAETER | macOS-Träger (W7), nicht in der Loop-Liste (W4); Auslöser: das erste Komplett-Audit ist abgearbeitet |
| `tg-serp-analyse` | neu, nicht Everlast | D5 |

Die endgültige Inventarzeile je Baustein setzt P9, die Abgrenzung zu den Content-Fähigkeiten P4.

Gelesen: alle vier Skills vollständig (siehe Teil 1), `EL:.claude/commands/seo-komplett-audit.md`,
`EL:tools/seo-audit/README.md`, `EL:tools/seo-audit/auftrag.md`, `EL:steuerstand/build.ts` (Zeilen 3576-3600).

### D11 Unterschiede je Produktlinie

| Option | Vorteil | Nachteil |
|---|---|---|
| A Everlast: keine Unterscheidung, alles auf Markenebene | einfach | neun Linien in einer Sicht, Lücken unsichtbar (L8) |
| B Eigene Regeln je Linie in den Skills | maßgeschneidert | Pflege mal neun; heute kein Fall, der es verlangt (T43) |
| C Die Skills sind für alle Linien gleich, unterschiedlich sind nur die Daten | ein Regelwerk; Unterschiede stehen dort, wo sie entstehen | – |

**Empfehlung C.** Je Linie unterscheiden sich: der Abschnitt im Keyword-Set, die Entscheidung „Leitseite ja oder nein“
nach dem Baum (D3), `fakten.md`, Persona, Angebot und Wettbewerb. Suchwissen entsteht nicht auf Vorrat: Die
Keyword-Recherche einer Linie läuft, wenn für die Linie Inhalte anstehen. Reihenfolge nach heutigem Stand: Glasschiebewände
(Bestand, offener Konflikt T40), Lamellendächer (21 geplante Zeilen, T41), die übrigen bei Bedarf. Die beiden Märkte werden
nur für die Kernbegriffe getrennt erhoben (T44).

Gelesen: `ELS:amm-new-product/references/ordner.md`, `EL:.claude/commands/prime-content.md`,
`ELS:amm-workspace-setup/references/struktur.md`, `TG:keyword-landkarte.md`, `TG:website-architektur.md`,
`docs/umbau/entscheidungen/02-wiki-architektur.md` (nur Trefferzeilen zu A7 bis A9).

### D12 Begriffe: Säule, Leitseite, Cluster

„Pillar“ hat drei Bedeutungen (L11). Der Steuerstand erkennt eine Säule nur an einem Slug aus Kleinbuchstaben, und Planer
und LinkedIn-Skill rechnen mit höchstens fünf (`ELS:amm-content-strategie/references/saeulen.md:19`, `:56`).

| Option | Vorteil | Nachteil |
|---|---|---|
| A Säule = Produktlinie | deckt sich mit Tegards’ Sprachgebrauch | neun Linien, höchstens fünf Säulen; eine Säule ist bei Everlast ein Themenfeld, kein Produkt |
| B Säule = Themenfeld der Marke quer zu den Linien; der Linienbezug steht im Zusatzfeld `produktlinien` | passt zu Everlast und zu P2 | Themenfelder müssen in Station 15 erst gefunden werden |

**Empfehlung B.** Sprachregel: „Säule“ für das Feld `pillar`, „Leitseite“ für die Hauptseite einer Produktlinie,
„Hauptbegriff und Unterfragen“ für einen Keyword-Cluster.

Gelesen: `ELS:amm-content-strategie/references/saeulen.md`, `EL:pipelines/README.md`,
`ELS:amm-keyword-research/references/cluster.md`, `TG:seo-geo-playbook.md`.

### D13 Was aus dem Altbestand wird

Grundsatz vom 14.11.2026: Altbestand ist Quelle, kein Import.

| Altbestand | Wird Quelle für | Eigene Datei im neuen Workspace |
|---|---|---|
| `seo-geo-playbook.md` | die Anpassung der Referenzen von `tg-seo` | nein (D9) |
| Snippet- und Titellängen (60, 155, 149 Zeichen) | Feldgrenzen von RankMath in `kanaele/websites.md`, als Hausregel; Google nennt keine feste Länge (`ELS:amm-seo/references/on-page.md:76`) | nein |
| `keyword-landkarte.md` | `keyword-set.md`; die 39 Zeilen werden neu gemessen, weil die Absichten ungeprüft sind (T39) | nein |
| `website-architektur.md` | Bestand in `kanaele/websites.md`; Baum in den Keyword-Skill (D3); die sechs Befunde ins erste Audit | nein |
| `verlinkungsstrategie.md` | Abschnitt „Text und Links“ in `tg-seo`; der Agent dazu ist Sache von P4 | nein |
| `referenzseiten.md` | Swipefile: fremde Seiten als Struktur-Vorbild sind genau dessen Zweck (`EL:swipefile/README.md:3-8`); neue Fächer für Shop-Kategorie und Shop-Produkt mit eigener README (`EL:swipefile/README.md:29-30`) | ja, im Swipefile |
| `offpage-geo.md` | Station 14 | nein (D8) |
| `ki-sichtbarkeit-log.md` | Vorrat der Testfragen (D8) | nein |
| die eine SERP-Analyse | Formatvorlage für `tg-serp-analyse` | nein (D5) |
| `E:\TG Design\ausgelagert\seitenvorlagen.md` | die Gerüste je Seitentyp (D6) | geht in den Referenzen auf |

Gelesen: `TG:seo-geo-playbook.md`, `TG:keyword-landkarte.md`, `TG:website-architektur.md`, `TG:ki-sichtbarkeit-log.md`,
`CO:references/querschnitt/referenzseiten-methode.md`, `EL:swipefile/README.md` (Zeilen 1-70),
`EL:swipefile/landingpages/README.md` (Zeilen 1-30), `E:\TG Design\ausgelagert\seitenvorlagen.md`.
Nicht gelesen: `TG:verlinkungsstrategie.md`, `TG:referenzseiten.md`, `TG:offpage-geo.md` (nur Lesebericht).

### D14 Produktdatenquelle für die Bildrubrik (offen aus P1)

**Empfehlung:** `produkte/<linie>/fakten.md` mit Belegpflicht aus P2 ist die Produktdatenquelle. Eine zweite Quelle
entsteht nicht. Live-Daten aus dem Shop (Sortiment, Attribute) sind eine Frage der Content-Fähigkeiten und gehen an P4.

Gelesen: `docs/umbau/STAND.md` (Zeilen 26, 31-32), `docs/umbau/entscheidungen/01-reviewer-design-medien.md` (Trefferzeilen 183, 222).

---

## 6. Gesamtbild der Empfehlung

Der Ablauf für eine Seite mit eigenem Suchbegriff, von oben und von unten:

1. **Marke (Top-down, steht schon):** Positionierung, USPs, Angebot und Persona der Linie, `fakten.md`.
2. **Nachfrage (Bottom-up):** Keyword-Recherche der Linie; Zeilen im Keyword-Set mit genau einer Zielseite; der
   Entscheidungsbaum legt den Seitentyp fest. Markus gibt die Zuordnung frei.
3. **Suchergebnis-Analyse:** datierter Lauf; Pflichtthemen, Fragen, Marktstandard, KI-Übersicht.
4. **Treffpunkt Sektionsplan:** Grundgerüst des Seitentyps; Value Propositions aus der Marke; je Pflichtthema eine Zeile;
   jede Sektion räumt eine Kaufbremse weg. Markus gibt den Plan frei.
5. **Text, Bild, Bau:** nach Everlast-Staffellauf; welche Agenten und Skills je Seitentyp, entscheidet P4.
6. **Prüfen:** Inhaltsrubrik mit den GEO-Punkten über den Codex-Prüfweg aus P1.
7. **Frisch halten:** Regel-Check monatlich, Messläufe mit Datum, Komplett-Audit auf Zuruf.

**Neu, nicht Everlast:** `tg-serp-analyse` (D5), der Zielseiten-Entscheidungsbaum mit Rollen (D3), die Spalten Zielseite
und Status im Keyword-Set (D2), die Paritäts-Zeile im Sektionsplan (D6), die Grundgerüste für Shop-Seitentypen (D6), die
Shop-Schema-Vorlagen (D7), der monatliche Regel-Check (D9), zwei Swipefile-Fächer (D13).

**Von Everlast weggelassen:** `amm-seo-audit`, `amm-seo-content`, der wöchentliche Loop seo-audit, die geplante Aufgabe,
`llms.txt`-Entwurf, die Zahlenregel für den Antwortblock.

**Von Tegards weggelassen:** „SEO-Optimum-First“, die Agenten `serp-analyst`, `wettbewerbs-analyst` und `geo-validator`
als eigene Agenten, das Playbook als Datei, `FAQPage`, `HowTo`, `speakable`, `Product` ohne Preis, die Regel „nie
wiederverwenden“, die harten Zahlen (300 Zeichen, zehn FAQ).

**Offen für andere Themen:**

- **P4:** Seitentypen und Tiefe der Grundgerüste; welcher Agent und welcher Skill je Seitentyp schreibt; Blog-Baupläne
  gegen Ratgeber- und Anleitungs-Template; `positionierung`-Skill von commerce-os; Verlinkung; Content-Inventar;
  Sortiments-Daten aus dem Shop; GEO-Punkte in die Inhaltsrubriken.
- **P7:** `dfs` und `gsc` unter Windows; Träger für den Regel-Check; Pfadkorrekturen W1 und W2; Umschreiben von `tg-seo`
  auf Shop.
- **P8:** Station 15 für neun Linien (Säulen quer, Suchverhalten für einen Shop statt Weiterbildung, E7); Reihenfolge der
  Keyword-Recherche je Linie; Bestand nach `kanaele/websites.md`.
- **P9:** Inventarzeilen der SEO-Bausteine; ob der Branchen-Update-Loop kommt (Vorbild für den Regel-Check).

---

## 7. Fragen fürs Grilling

In dieser Reihenfolge, weil spätere Antworten von früheren abhängen.

1. **Vorrang (D1):** Gilt „die Marke setzt, die Suche entscheidet über Seite, Typ und Pflichtthemen, Value Propositions
   kommen nie aus den Suchergebnissen“? Empfehlung: ja.
2. **Suchdaten (D4):** Search Console anbinden und ein DataForSEO-Konto mit Budget, oder ohne Bezahlwerkzeug? Empfehlung:
   beides, DataForSEO mit festem Budget je Lauf.
3. **Keyword-Ablage (D2):** Ein Keyword-Set mit Abschnitt je Linie und den Spalten Zielseite und Status? Empfehlung: ja.
4. **Seitentyp (D3):** Den Entscheidungsbaum mit den Rollen `zielseite` und `shop-seite` übernehmen, einmal abgelegt?
   Empfehlung: ja, Schwellen als Hausregel.
5. **Suchergebnis-Analyse (D5):** Ein Skill statt zweier Agenten, Ablage unter `daten/`, Wiederverwendung bis 30 Tage?
   Empfehlung: ja.
6. **Seitenschema (D6):** Ein Grundgerüst je Seitentyp beim Sektionsplan, je Pflichtthema eine Zeile, Freigabe vor dem
   Text? Dazu: Sind „Landingpage (Produkt)“ und „Produkt-Landingpage“ aus dem Designsystem zwei Seitentypen oder einer?
   Empfehlung: ja; die Typenfrage braucht Markus.
7. **Strukturierte Daten (D7):** Markup nur, wo Google es anzeigt oder das Plugin es liefert; `FAQPage`, `HowTo`,
   `speakable` und `Product` ohne Preis streichen? Empfehlung: ja.
8. **GEO (D8):** Everlast-Regeln ohne Zahlenvorgaben; Messung in drei Stufen; Off-Page auf später? Empfehlung: ja.
9. **Frische (D9):** Ein Ort je Regel und ein monatlicher Regel-Check gegen feste Quellen? Empfehlung: ja.
10. **SEO-Skills (D10):** Bereinigte Kette, `amm-seo-audit` und `amm-seo-content` weglassen, wöchentlicher Loop später?
    Empfehlung: ja.
11. **Produktlinien (D11):** Gleiche Skills für alle Linien, Suchwissen erst, wenn eine Linie Inhalte bekommt, Reihenfolge
    Glasschiebewände, dann Lamellendächer? Empfehlung: ja.
12. **Begriffe (D12):** Säulen als Themenfelder quer zu den Linien, „Leitseite“ für die Hauptseite einer Linie?
    Empfehlung: ja.
13. **Altbestand (D13):** Zuordnung laut Tabelle, Referenzseiten ins Swipefile, kein Playbook mehr? Empfehlung: ja.
14. **Produktdatenquelle (D14):** `fakten.md` der Linie? Empfehlung: ja.

---

## 8. Ergänzungen aus der Abzweigung (16.11.2026, von Markus freigegeben)

Entstanden in einer Abzweigung der P3-Session zu Grilling-Frage Q1. Markus hat die Punkte dort freigegeben und die
Übertragung in die Hauptsession ausdrücklich angeordnet. Sie sind Entscheidungen, keine Vorschläge mehr. Q1 (D1) ist damit
beantwortet: ja.

### 8.1 Marke und Suche (ergänzt D1)

1. Es gilt die Arbeitsteilung mit einem Treffpunkt. Die Marke setzt Verkaufsargumente, Personas, Ton, Themenfelder,
   Verbote und Fakten. Die Suche entscheidet, ob eine Seite entsteht, welcher Seitentyp, welche Pflichtthemen und Fragen,
   welcher Wortlaut.
2. Verkaufsargumente und Fakten kommen nie aus den Suchergebnissen. Die Regel „zuerst die ranking-optimale Variante“
   entfällt.
3. Das gilt für alle Seitenarten: Leitseite, Kategorie, Produkt, Ratgeber, Anleitung, Projekt. Die Suchergebnis-Analyse
   ist voll bei Seiten mit eigenem Suchbegriff, kurz bei Ratgeber, Anleitung und Projekt, und entfällt bei Shop-Seiten
   ohne eigenen Suchbegriff.

### 8.2 Wohin die Erkenntnisse aus den Suchergebnissen fließen (ergänzt D5)

4. Jede Analyse hat vier Abnehmer: den Sektionsplan der Seite (einmalig), die Wettbewerberdatei als datierte Beobachtung
   (`strategie/umwelt/wettbewerber/<name>.md`, P2 A9), das Keyword-Set der Linie, und Vorschläge an die Marke.
5. Ein Argument, das Wettbewerber führen und wir belegen könnten, ist ein Vorschlag für die USPs. Es gilt erst nach
   Markus’ Freigabe und dann für alle Seiten der Linie.
6. Jede Analyse endet mit einem Nachlauf: drei bis fünf Zeilen Destillat, was dauerhaft ins Wissen gehört. Der Head pflegt
   ein, nie der Agent (Everlast: `EL:.claude/head-of-marketing.md:45-49`).

### 8.3 Themenplan je Linie (neu, nicht Everlast, ergänzt D2, D3, D11)

Heutiger Fall: die 21 geplanten Lamellendach-Zeilen ohne Seite (T41) und der offene Konflikt Landingpage gegen Kategorie
(T40). Beide Systeme haben dafür nur Bruchstücke (Entscheidungsbaum, „eine Zielseite je Suchbegriff“, Sitemap-Abgleich bei
Tegards; Hauptbegriff und Unterfragen mit „Seite heute“ bei Everlast).

7. Bevor für eine Linie Seiten gebaut werden, entsteht ein Themenplan als Vorschlag mit Begründung: Bestand lesen
   (Sitemap, veröffentlichte Artikel, Projekte, Kategorien), Nachfrage erheben, Suchergebnisse je Kernbegriff ansehen,
   dann die Verteilung vorschlagen.
8. Der Plan sagt je Frage oder Suchbegriff: Form (eigene Seite, Abschnitt, Frage im Fragenblock), Zielseite, ob es sie
   schon gibt, worauf sie verlinkt, und warum.
9. Regeln: eigene Seite nur bei eigenen Suchergebnissen (andere Treffer oder anderer Seitentyp als beim Hauptbegriff);
   sonst Abschnitt oder Frage auf einer bestehenden Seite; die Kategorieseite ist die Leitseite, wenn die Linie den
   Entscheidungsbaum nicht erfüllt; jede neue Seite nennt ihr Linkziel und eine bestehende Seite, die auf sie verlinkt;
   Bestand wird erweitert, nicht verdoppelt.
10. Markus gibt den Themenplan frei, erst danach entstehen Sektionspläne und Seiten. Der Plan liegt im Abschnitt der Linie
    im Keyword-Set. Er ist der Abschluss der Keyword-Recherche einer Linie, kein eigener Agent.

### 8.4 Seitenaufbau (ergänzt D6)

11. Seiten entstehen aus den festen Content-Bausteinen des Designsystems, damit das Erscheinungsbild einheitlich bleibt.
12. Welche Bausteine auf eine Seite kommen und in welcher Folge, ist beweglich. Kriterien: Everlasts Logik (eine Sektion
    räumt eine Kaufbremse weg; Streich-, Doppel- und Kettentest) und was die Top-Konkurrenz auf ihren Seiten hat.
13. **Ausnahme Landingpage:** Neben der Fassung aus den Content-Bausteinen des Designsystems werden zwei zusätzliche
    Alternativvarianten angeboten: kreativ, passend, modern, benutzerfreundlich, professionell. Markus wählt. (Everlast
    kennt dafür den Varianten-Lauf mit drei Varianten, `EL:.claude/head-of-marketing.md:51-54`; die Ausgestaltung klärt P4.)
14. Für Ratgeber und Anleitungen ist Hornbach („Projekte“) das Referenzunternehmen für Aufbau, Bausteine und Sprachstil.
    Übernommen wird die Machart, nie Text oder Bild. Abgleich: `docs/umbau/dossiers/03-lesen/hornbach-blogaufbau.md`.

### 8.5 Bilder (an P4, baut auf P1 auf)

15. Aus dem freigegebenen Sektionsplan entsteht eine Bildliste: je Platz Motiv, Zweck, Format und ob ein echtes Foto
    nötig ist.
16. Stufe 1 (heute): Der Agent schreibt den Bildbedarf in den Brief (`medien.md`, P1). Markus sucht in der TG
    Medienbibliothek (TGMB) und legt die Dateien in den Arbeitsordner des Stücks.
17. Stufe 2 (wenn die TGMB-Schnittstelle fertig ist): Der Agent sucht selbst und schlägt vor.
18. Für Stimmungs- und Erklärbilder darf er über OpenArt generieren: erst ein Testbild, dann wenige Varianten. Echte
    Produktbilder werden nie generiert, dort bleibt eine benannte Lücke.
19. Der Erstentwurf zeigt Bilder, keine leeren Flächen. Markus wählt je Platz.
20. Am Schluss stehen die Dateien fest, jede mit Dateiname, Alt-Text und Bildunterschrift als fertigem Vorschlag
    (neu gegenüber Everlast als fester Schritt).
21. `bildsprache.md` bekommt ein Register „Belegte Motive“ nach Everlast
    (`EL:.claude/agents/grafik-designer.md:43`, `:63`), damit ein Motiv nicht zwei Bedeutungen trägt.

### 8.6 Loops und Werkzeuge (ändert D10)

22. Der wöchentliche Loop „fehlende Seite vorschlagen“ und der monatliche Loop „veraltete Artikel auffrischen“ kommen
    sicher, mit Windows-Träger. Beide stehen als **Fixpunkte** in `SPAETER.md` (Auslöser: Themenplan der ersten Linie
    bzw. erste veröffentlichte Artikel). D10 nannte den wöchentlichen Loop nur „SPAETER“; das ist damit verschärft.
23. RankMath-MCP: von der Planung gestrichen, Zeile in `SPAETER.md`.

### 8.7 Offen, an P4

24. Rückmeldung vom Markt über Google Analytics, Google Ads und künftig Facebook-Werbung: bei Everlast gezielt nachlesen.
    Bisher gesehen: Search Console, Meta-Ads-Skill, A/B-Tests mit PostHog, Learnings-Datei; Analytics und Google Ads nicht
    gezielt gesucht.
25. Hornbach-Abgleich (Punkt 14) in die Blog-Gerüste einarbeiten.

Gelesen für diese Ergänzungen zusätzlich: `EL:.claude/agents/grafik-designer.md`,
`EL:.claude/agents/references/grafik-designer-workflows.md`.

### 8.8 Suchdaten (beantwortet Q2, ergänzt D4)

Entstanden in einer zweiten Abzweigung zu Grilling-Frage Q2. Laut deren Nachricht hat Markus Variante a) gewählt und die
Übertragung in die Hauptsession ausdrücklich angeordnet. Eingetragen von der P3-Session; die beiden Everlast-Belege unten
sind dabei nachgelesen.

26. **Entscheidung:** Search Console und DataForSEO, dazu die kostenlose Suggest-Abfrage für Wortlaute.
27. **Aufgabenteilung der Quellen:** Eigene Rankings kommen aus der Search Console (gemessen). Wortlaute kommen aus
    Suggest. Suchvolumen kann auch der Keyword-Planer liefern, weil laufend Google-Ads-Anzeigen geschaltet sind;
    DataForSEO bringt beim Volumen nur den Abruf ohne Handarbeit.
28. **Wofür DataForSEO da ist:** (1) Seite eins automatisch und unter festen Bedingungen (Ort, Sprache, Gerät, ohne
    Verlauf), für Österreich und Deutschland, mit KI-Übersicht, wiederholbar und über die Zeit vergleichbar
    (`dfs serp`, `EL:tools/dataforseo/README.md:10`, `:21`). (2) Unbekannte Begriffe der Wettbewerber finden
    (`dfs ranked`, `competitors`, `gap`, `EL:tools/dataforseo/README.md:11-14`; laut `:20` geschätzt, nicht gemessen).
    Grund: Die Suchergebnis-Analyse und die beiden Loops sollen ohne Markus laufen; die Websuche des Agenten ist nicht
    Google.
29. **Sprachregel:** Ein absolut richtiges Ranking gibt es nicht. Der Gewinn ist Vergleichbarkeit, nicht Wahrheit.
30. **Kosten:** Die rund 0,60 USD gelten je vollständigem Keyword-Audit einer Domain, nicht je Suchbegriff
    (`EL:tools/dataforseo/README.md:18`: 0,59 USD am 23.09.2026; `EL:tools/seo-voraussetzungen.py:110`). Das ist ein
    Messwert von Everlast, bei DataForSEO nicht nachgeprüft. Geld ist laut Markus kein Kriterium. Ein festes Budget je
    Lauf als Schutz gegen Fehlläufe ist **nicht entschieden**.
31. **Andere Anbieter:** SerpApi, Serper, Ahrefs, Semrush, Sistrix und GEO-Tracker (Peec AI, Profound, Otterly) wurden
    nur aus dem Wissensstand besprochen, **nicht recherchiert**. Es bleibt bei DataForSEO, weil das Everlast-Werkzeug `dfs`
    dafür fertig ist. KI-Sichtbarkeit wird zuerst über die drei Stufen aus D8 gemessen. Ein GEO-Tracker ist ein Fall für
    `SPAETER.md` mit dem Auslöser „die Messung zeigt, dass KI-Antworten für unsere Begriffe eine Rolle spielen“ (Zeile
    noch nicht eingetragen).
32. **Stand Konten:** Google Ads läuft. Ein DataForSEO-Konto gibt es noch nicht, Markus legt es an und trägt die
    API-Zugangsdaten selbst ein. **Offen:** ob tegards.com in der Search Console bestätigt ist. Ob `dfs` und `gsc` unter
    Windows laufen, bleibt bei P7.
33. **Lücke bei Everlast, die für D5 zählt:** Was `dfs competitors` und `gap` liefern, landet dort laut der Abzweigung in
    keiner Wettbewerberdatei, und die Suchdaten erreichen nur den Blog, nicht den Sektionsplan. Abschnitt 8.2 (vier
    Abnehmer) schließt das. Der erste Halbsatz ist von der P3-Session nicht eigens nachgelesen; der zweite deckt sich mit
    L3 in Teil 4.

### 8.9 Säulen und Begriffe (beantwortet Q7, D12)

Entstanden in einer Abzweigung zu Grilling-Frage Q7. Markus hat mit „ja passt so“ entschieden und die Übertragung in die
Hauptsession ausdrücklich angeordnet.

34. **Entscheidung:** Säulen sind Themenfelder der Marke quer zu den Produktlinien, gebaut nach Everlast
    (`ELS:amm-content-strategie/references/saeulen.md:17-20`). Jedes Stück trägt zwei Etiketten: `pillar` für das
    Themenfeld und das Zusatzfeld `produktlinien` aus P2 für die Linie.
35. **Sprachregel:** „Säule“ für das Feld `pillar`, „Leitseite“ für die Hauptseite einer Produktlinie, „Hauptbegriff und
    Unterfragen“ für einen Keyword-Cluster.
36. **Entstehung wie bei Everlast:** Der Agent schlägt Säulen aus den Workspace-Dateien vor, nicht aus Branchenwissen
    (`saeulen.md:26-35`), jede besteht die Prüffragen (`:41-48`), Markus gibt frei (`:96`). Höchstens fünf (`:19`).
    Welche Säulen es werden, ergibt Station 15 im Onboarding (P8).
37. **Änderbar mit Bremse:** 90 Tage ohne Stück ist ein Befund „stärken oder streichen“ (`:87`); Umbenennen nur nach
    Rückfrage (`:59`).
38. **Nur Beispiel, nicht entschieden:** In der Abzweigung dienten `montage`, `planung`, `vergleich`, `projekte` als
    Anschauung.

### 8.10 Analyse in zwei Ebenen und Agenten-Regel (ergänzt Q9, D5; lockert eine feste Entscheidung)

Entstanden in einer Abzweigung zu Grilling-Frage Q9. Markus hat die drei Punkte dort bestätigt („Ja, das passt so. Schreib
es fest“) und die Weitergabe an die Hauptsession angeordnet. Die Teilfragen von Q9 selbst (Form als Skill, Ablage unter
`daten/`, 30 Tage Wiederverwendung) sind damit **nicht** beantwortet.

39. **Agenten-Regel gelockert:** Die Zahl der Fachagenten ist nicht generell auf sechs begrenzt. Ein weiterer Fachagent
    darf vorgeschlagen werden, wenn er Sinn ergibt; nichts Unnötiges, nichts, was verkompliziert. Das ändert die feste
    Entscheidung „Head + sechs Fachagenten 1:1 nach Everlast“ in `STAND.md`; dort nachzuziehen. Für die
    Suchergebnis-Analyse wird **kein** neuer Fachagent vorgeschlagen: Die Linien-Ebene liest viel, aber selten, der
    planende Agent kann sie als Unterauftrag auslagern. Ein eigener Agent erst, wenn die Analyse nachweislich den Kontext
    des Planers sprengt.
40. **Zwei Ebenen der Analyse:**
    - **Linie**, beim Themenplan: bei zwei bis drei Top-Wettbewerbern den Unterbau lesen, also Leitseite, stützende
      Seiten (Ratgeber, Projekte, Kategorien), interne Links und die Verteilung des Themens über die Domain. Ergebnis geht
      in den Themenplan und als datierte Beobachtung in die Wettbewerberdatei.
    - **Seite**, vor jedem Sektionsplan: wie in D5, also Suchabsicht, Pflichtthemen, zwei bis drei Top-Seiten genau lesen.
    Grund (Markus): Eine Seite rankt als Teil eines Gesamtkonstrukts der Domain. D5 hatte nur die einzelne Seite gemeint.
    Dass der Unterbau das Ranking trägt, ist fachliche Einschätzung, in der P3-Recherche nicht eigens belegt.
41. **Wiederholung der Linien-Ebene:** kein fester Kalendertermin, sondern ein Auslöser mit Obergrenze.
    - Auslöser: Bei einem Kernbegriff der Linie kommt eine neue Domain unter die ersten fünf, oder die eigene Seite rutscht
      deutlich ab. Dann nur für diesen Wettbewerber.
    - Wer es bemerkt: das Komplett-Audit über den Vergleich von `dfs serp` mit dem letzten abgelegten Lauf; später der
      wöchentliche Loop.
    - Obergrenze: spätestens nach sechs Monaten neu, auch ohne Auslöser. Hausregel.
    - Ergebnis: Beobachtung in der Wettbewerberdatei („was hat ihn nach vorne gebracht“) und ein Vorschlag für den
      Themenplan; umgesetzt wird erst nach Markus’ Freigabe.
    - Schwäche: Der Auslöser greift nur, wenn das Komplett-Audit regelmäßig läuft. Der Takt ist **nicht festgelegt**.
42. **Für `SPAETER.md` (noch nicht eingetragen):** Backlink-Analyse der Wettbewerber. **Berichtigt am 16.11.2026:** Die frühere Aussage, `dfs` führe dafür keinen
    Befehl, war falsch; gelesen war nur die unvollständige Liste der README (`EL:tools/dataforseo/README.md:8-14`). Der Code
    hat den Befehl `backlinks` (`EL:tools/dataforseo/dfs:12`, `:462`, `:558`; `EL:tools/README.md:41`). Das Werkzeug ist
    also da, offen ist nur, ob und wann es genutzt wird. Auslöser: die Linien-Analyse erklärt einen Aufsteiger
    nicht aus Inhalt und internen Links.

### 8.11 Seitenaufbau (beantwortet Q10, D6; ändert 8.4 Punkt 13)

Entstanden in einer Abzweigung zu Grilling-Frage Q10. Markus hat die Punkte dort einzeln mit Ja freigegeben, Punkt 48
korrigiert und die Übertragung in die Hauptsession ausdrücklich angeordnet („übertragen“).

43. **Startfolge:** Die Folge aus `E:\TG Design\ausgelagert\seitenvorlagen.md` ist der Ausgangspunkt je Seitentyp. Der
    Sektionsplan darf mit Begründung streichen, umstellen **und ergänzen** (Everlasts Kettentest zeigt, wo eine Sektion
    fehlt, `ELS:amm-sektionsplan/SKILL.md:59`).
44. **commerce-os-Templates:** entfallen als Pflichtfolge und als zweite Quelle. Zwei Ideen bleiben:
    - der Technik-Baustein (`CO:templates/landingpage.md:248-251`) kommt in den Vorrat des Sektionsplan-Skills;
      Everlasts Repertoire kennt keinen (`ELS:amm-sektionsplan/references/bremsen-und-bausteine.md:42-58`). Dass er
      „Kein Vertrauen“ und „Zu viel Risiko“ wegräumt, ist Deutung, nicht belegt.
    - „Antwort zuerst“ (`CO:templates/landingpage.md:102-106`) wird GEO-Regel für jede Seite, ohne feste Satzzahl.
    Der Meta-Block (Titel, Beschreibung, URL) wandert als Schluss-Schritt in den SEO-Skill. „Problem und Lösung je
    Persona“ entfällt als eigenes Modul (deckt sich mit Everlasts Zielgruppen-Raster, `bremsen-und-bausteine.md:47`, und
    `TextImage` je Zielgruppe im Designsystem). Der Markup-Verweis entfällt (Q5). Gelesen wurden vom Template nur die
    Überschriften und die Zweck-Zeilen der Module 3, 5 und 7; die Templates für Kategorie, Produkt und Blog nicht.
45. **Abgleich mit der Suche:** Jedes Pflichtthema aus der Analyse bekommt im Sektionsplan eine Zeile: erfüllt durch
    Sektion X, im Fragenblock beantwortet, oder bewusst nicht, mit Grund.
46. **Rangfolge bei Konflikt:** Fakten, Recht und Verbote, dann die Marke, dann die Suche. Das Design bestimmt nur die
    Form. Die Suche bestimmt, worüber die Seite spricht; Marke und Fakten bestimmen, was sie dazu sagt.
47. **Zahlen:** „Genau zehn Fragen“ und feste Wortkorridore sind Startwerte, keine Pflicht.
48. **Zwei Varianten mit festen Annahmen** (ersetzt 8.4 Punkt 13, dort „zwei zusätzliche kreative Alternativvarianten“):
    Variante 1 „Startfolge angepasst“ (Punkt 43), Variante 2 „frei nach Everlast“ (nur Kaufbremsen und die drei Tests,
    ohne Startfolge). Beide bauen aus den Bausteinen des Designsystems. Pflicht bei der Leitseite, auf Zuruf bei jeder
    anderen Seite. Form nach Everlasts Varianten-Lauf mit Leithypothese je Variante
    (`EL:.claude/head-of-marketing.md:51-54`); dort sind es drei Varianten mit freien Hypothesen. Eine dritte, frei
    kreative Variante hat Markus gestrichen. Die Ausgestaltung klärt weiter P4.
49. **Baustein-Vorschlag ans Designsystem** (neu als ausdrückliche Regel): Braucht eine Sektion einen Baustein, den es
    nicht gibt, steht im Sektionsplan ein Vorschlag: was er leisten soll, welche Bremse oder welches Pflichtthema er
    deckt, auf welcher Seite. Markus entscheidet (bauen lassen oder mit vorhandenem Baustein lösen). Bis dahin nimmt der
    Entwurf den nächstbesten Baustein und markiert die Stelle. Kein eigenes Layout am Designsystem vorbei. Wer baut und
    wie der Baustein ins Designsystem kommt, klärt P4.
50. **Richtigstellung von Markus zum Shop:** WooCommerce gibt bei Produkt- und Kategorieseiten nicht das Gerüst vor. Bei
    Produktseiten nimmt ein freies HTML-Element unter der Produktbeschreibung alles auf, was die Seite zum Ranken
    braucht; bei Kategorieseiten mit der Rolle `zielseite` gilt dasselbe unterhalb der Produktliste. Laut Markus gibt es
    eine SEO-Regel zur Höchstzahl der Wörter oberhalb der Produktliste; **nicht nachgeprüft**. Mehrere Varianten als
    Standard bleiben für diese Seitentypen trotzdem aus (Punkt 48).
51. **`SPAETER.md` (eingetragen):** Fällt die Wahl bei der Leitseite immer wieder auf dieselbe der zwei Varianten, wird
    dieser Modus fest und die andere Variante entfällt.

### 8.12 Bestand ist Quelle, Gerüste werden neu hergeleitet (beantwortet Q11; ersetzt 8.11 Punkt 43, ändert Punkt 48 und 49)

Entstanden in einer Abzweigung zu Grilling-Frage Q11. Markus hat die Punkte einzeln freigegeben („ja passt“) und die
Übertragung in die Hauptsession ausdrücklich angeordnet („schreibe ins dossier und übertrage“).

52. **Bestand, keine Vorlage:** Die Einträge in `E:\TG Design\ausgelagert\seitenvorlagen.md` beschreiben den heutigen
    Stand bestehender Seiten (Landingpage: Glasschiebewände Deluxe, `:28-45`; Produkt-Landingpage: Verdeca, `:47-63`;
    Projekt: Poolhaus Deutsch Wagram, `:67`). Sie sind Inhaltsquelle und Beispiel, kein Muster. Das gilt für alle
    Seitenarten. Gelesen: Zeilen 26 bis 77; der Blog-Teil nur über `03-lesen/hornbach-blogaufbau.md`, von der
    Kategorieseite nur der Anfang.
53. **Neubau:** Die Seiten Glasschiebewände Deluxe und Verdeca entstehen komplett neu nach dem neuen Ablauf (Themenplan,
    Suchergebnis-Analyse, Sektionsplan nach Kaufbremsen mit Abgleichzeile, Freigabe, dann Text und Bilder).
54. **Q11 erledigt:** Es gibt eine Seitenart „Leitseite“. Die Frage „ein Landingpage-Typ oder zwei“ entfällt.
55. **Leitseite ohne Startfolge** (ändert 8.11 Punkt 48): Beide Varianten entstehen frei aus Kaufbremsen und
    Suchergebnis-Analyse, mit je eigener Leithypothese. Die Namen „Startfolge angepasst“ und „frei nach Everlast“
    entfallen. Die `SPAETER.md`-Zeile aus 8.11 Punkt 51 nennt noch die alten Namen und ist anzupassen (nicht geändert).
56. **Eine Variante darf über das Designsystem hinausgehen** (ändert 8.11 Punkt 48 und 49 für die Leitseite): Eine der
    zwei Varianten darf neue Bausteine und eigenes Layout zeigen. Wählt Markus sie, werden die neuen Bausteine ins
    Designsystem aufgenommen. Farben, Schrift und Ton der Marke gelten in jeder Variante. Für alle anderen Seitenarten
    bleibt 8.11 Punkt 49 (Baustein-Vorschlag, kein Layout am Designsystem vorbei).
57. **Gerüst je übriger Seitenart wird neu hergeleitet** (ersetzt 8.11 Punkt 43): für Kategorie, Produkt, Ratgeber,
    Anleitung und Projekt einmal, aus drei Quellen: Everlasts Logik (Kaufbremsen bei Kategorie und Produkt, Baupläne je
    Suchabsicht bei Ratgeber und Anleitung), was die Suchergebnisse für die Seitenart zeigen, und der Bestand als Inhalt.
    Die Startfolge kommt aus diesem Gerüst, nicht aus `seitenvorlagen.md`. Die Aussagen über Everlast in diesem Punkt
    stammen aus Teil 1 des Dossiers, in der Abzweigung nicht neu nachgelesen; für Shop-Kategorie und Shop-Produkt hat
    Everlast kein Gerüst (1.4).
58. **Aufgabe im Gesamtbau:** Jedes Gerüst hat zwei feste Stellen: den Link zur Leitseite der Linie und einen nächsten
    Schritt Richtung Kauf oder Anfrage. Welche Seite worauf verlinkt, steht im Themenplan (8.3 Punkt 9).
59. **Ein Gerüst, keine zwei Varianten:** Je übriger Seitenart gibt es ein Gerüst, von dem der Sektionsplan mit
    Begründung abweicht. Varianten nur auf Zuruf.
60. **Herleitung der Gerüste ist Arbeit für P4.** P3 legt nur die Regel fest. Bis dahin gibt es für diese Seitenarten
    keine fertige Ausgangsfolge.
61. **Bewertung des Bestands vor dem Neubau:** was gut ist, was fehlt, welche Kaufbremsen die Seite wegräumt. Sie endet
    mit einer Liste „muss bleiben“; jede Zeile bekommt im Sektionsplan einen Platz oder eine begründete Streichung.
62. **Vergleichswert:** Vor dem Umbau einer bestehenden Seite werden ihre heutigen Zahlen festgehalten (Search Console,
    Analytics).
63. **Adresse und Hauptbegriff** einer bestehenden Seite bleiben beim Neubau gleich.

Die Einschätzung, dass der freie Neubau besser verkauft als die Überarbeitung des Bestands, ist fachliche Deutung, nicht
gemessen. Die Punkte 61 bis 63 fangen die drei Verluste auf (Bewährtes ohne Nachweis, Vergleichswert, Ranking).

### 8.13 Altbestand und Begriffe (beantwortet Q13; ersetzt die Tabelle in D13, ändert D5 und D8)

Entstanden in einer Abzweigung zu Grilling-Frage Q13. Markus hat die Punkte 64 bis 78 freigegeben („ja und ja“) und die
Übertragung in die Hauptsession ausdrücklich angeordnet („nach freigabe festschreiben und übertragen“). Abweichung von der
Empfehlung in D13: statt einer Zuordnung je alter Datei wird fast nichts übertragen.

64. **Grundsatz:** Aus dem alten SEO-Wissensordner (`E:\tegards\marketing\marketing-wissen\seo-geo\`) wird nichts
    übertragen. Was keinen Abnehmer im neuen Ablauf hat, bleibt draußen. Die alten Dateien bleiben unangetastet im alten
    Ordner.
65. **Playbook:** keine eigene Datei. Eine einzelne Regel kommt nur dann in den SEO-Skill, wenn sie die Schranke aus Q6
    besteht: Primärquelle und Abrufdatum.
66. **Keyword-Landkarte:** nichts wird übernommen. Das Keyword-Set entsteht neu aus der Bestandsaufnahme der Domain
    (Q12, Punkt 2).
67. **Website-Architektur:** nichts wird übernommen. `kanaele/websites.md` entsteht im Onboarding, der Seitenbestand aus
    der Bestandsaufnahme vor dem Themenplan (8.3 Punkt 7), Mängel findet das erste Audit.
68. **KI-Sichtbarkeits-Log:** nichts wird übernommen. Die Testfragen der neuen Messung kommen aus dem neuen Keyword-Set.
    Das ändert D8 und Q14; dort waren die zehn alten Prompts als Vorrat vorgesehen.
69. **Alte Suchergebnis-Analyse:** entfällt, auch als Formatvorlage. Das ändert D5.
70. **Verlinkungsstrategie:** nichts wird übernommen. Das Thema ist im neuen Ablauf verankert (8.3 Punkt 9, 8.12
    Punkt 58). Die alte Datei wurde nicht gelesen.
71. **Off-Page-Notizen:** nichts wird übernommen. Die alte Datei wurde nicht gelesen.
72. **Zeichenlängen für Titel und Beschreibung (60, 155, 149):** kommen als Hausregel in den Schluss-Schritt
    „Meta-Block“ des SEO-Skills (8.11 Punkt 44). Google nennt keine feste Länge (`ELS:amm-seo/references/on-page.md:76`).
73. **Swipefile-Regel:** Fremde Vorbilder liegen im Swipefile. Die Fächer heißen wie die eigenen Seitenarten
    (Landingpage, Kategorieseite, Produktseite, Blogartikel, Projekt). Ein Fach entsteht erst mit dem ersten Fund, als
    Unterordner mit eigener README (`EL:swipefile/README.md:29-30`). Jeder Eintrag braucht einen Griff (`:3-8`).
74. **Heute ein Fach:** Blogartikel, mit den Hornbach-Seiten als Vorbild für Ratgeber und Anleitung. Die Auswertung der
    Hornbach-Seiten steht noch aus (P4). Aus `referenzseiten.md` zieht nur um, was einen Griff hat. Die Datei wurde nicht
    gelesen.
75. **Everlasts Fach `landingpages/`:** nimmt nur Anmeldeseiten gegen E-Mail-Adresse auf
    (`EL:swipefile/landingpages/README.md:15-22`). Diese Einschränkung gilt für Tegards nicht. Was mit dem Fach geschieht,
    entscheidet das Inventar (P9).
76. **Off-Page messen:** Das Thema bleibt wichtig, die Bearbeitung ist Handarbeit bei Markus. Neu im Komplett-Audit: ein
    Prüfpunkt „Links-Bericht aus der Search Console exportieren und auswerten“. Dass der Bericht nur in der Oberfläche
    verfügbar ist, ist **nicht nachgeprüft**.
77. **Für `SPAETER.md`:** Die automatische Link-Messung über DataForSEO fällt mit der Zeile „Backlink-Analyse der
    Wettbewerber“ aus 8.10 Punkt 42 zusammen (dort auch der Auslöser). Eine zweite Zeile entsteht nicht.
78. **Begriffe geschärft:** „Landingpage“ ist die Seitenart, „Leitseite“ die Rolle der Hauptseite einer Linie. Die
    Leitseite ist meist eine Landingpage, bei kleinen Linien die Kategorieseite (8.3 Punkt 9). In 8.12 Punkt 54 ist die
    Seitenart gemeint, also „Landingpage“. Everlast verwendet „Leitseite“ nirgends (kein Treffer im Workspace) und
    „Landingpage“ für Anmeldeseiten sowie im Steuerstand-Feld `landingpage:` (`EL:steuerstand/build.ts:2194-2229`,
    Fach-Etikett `:1560`); zu welchem Stück das Feld gehört, ist nicht nachgelesen.

Gelesen für diese Ergänzungen: `EL:swipefile/README.md` (Zeilen 1-45), `EL:swipefile/landingpages/README.md` (Zeilen 1-30),
Treffersuche „leitseite“ und „landingpage“ im Everlast-Workspace. Nicht gelesen: `TG:verlinkungsstrategie.md`,
`TG:referenzseiten.md`, `TG:offpage-geo.md`.

### 8.14 GEO: Regeln, Prüfung, Messung, Roboter (beantwortet Q14, D8)

Entstanden in einer Abzweigung zu Grilling-Frage Q14. Markus hat die vier Punkte dort entschieden und die Übertragung in
die Hauptsession ausdrücklich angeordnet („festschreiben und dann übertragen“). GEO heißt hier, in KI-Antworten (Googles
KI-Übersicht, ChatGPT, Perplexity) als Quelle genannt zu werden.

79. **Schreibregeln:** Es gelten drei Regeln: Antwort zuerst (schon 8.11 Punkt 44), Herkunft einer Angabe im selben Satz,
    der Text trägt, was Grafik und Markup sagen. Die Zahlenvorgaben beider Seiten entfallen (134 bis 167 Wörter, 300
    Zeichen, genau zehn Fragen; W5, T28, T37). `llms.txt` wird nicht gebaut (R2).
80. **Prüfung:** Codex prüft die Inhalte, wie in P1 entschieden. Die GEO-Punkte werden Teil der Inhaltsrubrik je
    Auftragsart. Ein eigener Prüf-Agent (`geo-validator`) kommt nicht. P1 bleibt unverändert, auch der Rückfall auf ein
    anderes Claude-Modell, wenn Codex nicht erreichbar ist (P1 A4).
81. **Erwogen und zurückgenommen:** Markus hatte in der Abzweigung zunächst vorgeschlagen, alle Inhalte innerhalb von
    Claude durch ein anderes Modell prüfen zu lassen, und das danach ausdrücklich zurückgenommen. Es gilt Punkt 80.
82. **Messung in drei Stufen:** (1) laufend und kostenlos der Bericht zu generativer KI in der Search Console, er zeigt
    nur Impressionen (R9). (2) Bei jedem Komplett-Audit `dfs serp` für die zehn wichtigsten Begriffe ohne Markennamen:
    KI-Übersicht ja oder nein und welche Domains sie nennt. (3) Nur im Komplett-Audit: fünf Testfragen, jede mehrfach
    gestellt, nach Everlasts Testfragen-Protokoll. Die Testfragen kommen aus dem neuen Keyword-Set (8.13 Punkt 68). Die
    alte Messung wird nicht fortgeschrieben.
83. **Off-Page:** kein Agent erzeugt Bewertungen, Forenbeiträge oder Fremdnennungen; das bleibt Handarbeit bei Markus
    (schon 8.13 Punkt 76).
84. **Roboter, Ort der Regelung:** Welche KI-Crawler die Website zulässt, steht einmal in `kanaele/websites.md`.
85. **Roboter, Entscheidung:** Suchcrawler und Trainingscrawler werden zugelassen. Grund: Für einen Shop überwiegt, dass
    die Modelle Marke und Produkte kennen; Produkttexte haben keinen Lizenzwert. Das ist Einschätzung, nicht gemessen.
    Eingetragen wird die Entscheidung beim Befüllen von `websites.md` im Onboarding (P8).

Für diese Ergänzungen wurde nichts neu gelesen; die Belege stehen in D8 und in Teil 3 (Recherche).

### 8.15 SEO-Bausteine und Schreib-Skills (beantwortet Q15, D10; ersetzt zwei Zeilen der Tabelle in D10)

Entstanden in einer Abzweigung zu Grilling-Frage Q15, nach Markus’ Einwand, Everlast irre sich hier kaum. Die
Originaldateien wurden neu gelesen. Markus hat die Punkte freigegeben und die Übertragung ausdrücklich angeordnet
(„festschreiben und übertragen“). Abweichung von der Empfehlung in D10: `amm-seo-audit` und `amm-seo-content` kommen mit.

86. **Grundsatz (Markus):** Was bei Everlast funktioniert, kommt mit und wird nur auf die Besonderheit Shopsystem
    angepasst. Kein Umbau ohne Not.
87. **Berichtigung zu D10:** „`amm-seo-audit` ist doppelt zu Modus A von `amm-seo`“ war zu hart. Der Audit-Skill misst die
    ganze Website (Indexstatus je Adresse über die Search Console, Antwortstatus je Crawler-Kennung, Rendering ohne
    JavaScript, Vergleich zum Vorlauf, freie Fragen an die Search Console) und grenzt sich selbst ab: die einzelne Seite
    prüft `amm-seo` (`ELS:amm-seo-audit/SKILL.md:17-19`, `:36-52`, `:64-80`); `amm-seo` misst nicht
    (`ELS:amm-seo/SKILL.md:24`). Weder `/seo-komplett-audit` (`EL:.claude/commands/seo-komplett-audit.md:7`) noch der
    Wochen-Loop (`EL:tools/seo-audit/auftrag.md:1`) laden ihn; die Indexprüfung je Adresse kommt im Command nicht vor
    (Suche nach „inspect“ und „user-agent“ in der Command-Datei: kein Treffer).
88. **`amm-seo-audit` kommt angepasst mit** (`tg-seo-audit`). Anpassungen: Berichtsort angleichen (W2); der Messpunkt
    „Rendering ohne JavaScript“ läuft über Markus’ eingerichtetes Firecrawl (Everlasts Paket liefert das Aufrufskript
    `tools/firecrawl/fc` nicht mit, `SKILL.md:113`). Ahrefs kommt nicht; bei Everlast ist es nur eine freiwillige
    Zusatzquelle (`:78-80`, `:114`), Backlinks liefert `dfs backlinks`. Das große Audit ruft ihn für Index und Crawler auf.
89. **Abgrenzung zum Altsystem:** Der Abgleich Bestand gegen Sitemap (`inventar-sync` aus commerce-os; nur die
    Beschreibung gelesen, nicht die Datei) ist etwas anderes als die Frage an Google, ob eine Adresse im Index steht.
    Er ist nicht verworfen, er steckt im Themenplan (8.3 Punkt 7) und im Wochen-Loop.
90. **`amm-seo-content` kommt angepasst mit** (`tg-seo-content`). Er ist der Schritt von der Lücke zum Entwurf, nach
    Lückenliste (Themenplan im Keyword-Set) und Wochen-Vorschlag; er führt keine zweite Lückenliste. Drei Bausteine
    stützen sich auf ihn: `amm-video-zu-blog` (Briefing und Gate, `SKILL.md:154`, `:232`, `:303`), `amm-pillar-to-blog`
    (`SKILL.md:13-16`), `amm-kampagne` (`references/traffic.md:33`); dazu die geplante Aufgabe
    (`EL:seo/geplante-aufgaben/seo-neue-seite.md:5`). Anpassungen: Pfad zum Keyword-Set auf
    `strategie/positionierung/keyword-set.md` (Q3); Antwortblock ohne Wortzahl (heute 134 bis 167 Wörter,
    `ELS:amm-seo-content/SKILL.md:34`; `ELS:amm-video-zu-blog/scripts/pruefe_artikel.py:31` prüft das hart); Seitenarten
    um Shop-Kategorie und Shop-Produkt ergänzen; gemeinsamer Aufbau nach Punkt 92.
91. **Vier Schreiber bei Everlast, vier Endprodukte:**
    - `amm-blog`: Antwort im ersten Absatz in höchstens drei Sätzen, Zwischentitel als Frage, Bauplan je Format, keine
      Wortzahl (`ELS:amm-blog/references/bauplaene.md:14-22`); sechs Formate howto, glossar, statistik, vergleich,
      fallstudie, thought-leadership (`:26-79`); Ablage in der Blog-Pipeline.
    - `amm-seo-content`: Frage als H1, Antwortblock, Ausführung, nächster Schritt; kennt keine Formate
      (`SKILL.md:32-35`); Ablage im Projektordner.
    - `amm-video-zu-blog`: neun feste Stationen; das Video ist „der Aufhänger und der Beleg, nicht die Vorlage“
      (`SKILL.md:16-20`, `:172-182`).
    - `amm-pillar-to-blog`: je Kapitel des Videos ein Abschnitt mit Zeitmarken, am Ende „Lücken“ (`SKILL.md:59-79`).
    Abgrenzung bei Everlast: die drei aus dem Kursmodul grenzen sich untereinander ab
    (`ELS:amm-video-zu-blog/SKILL.md:11-13`, `ELS:amm-pillar-to-blog/SKILL.md:13-16`). Zu `amm-blog` gibt es keine:
    keiner der drei nennt `amm-blog` und umgekehrt (Suche in allen vier Skill-Ordnern); der content-marketer und die
    Skills-Karte führen nur `amm-blog` (`EL:.claude/agents/content-marketer.md:88`, `:107`;
    `EL:.claude/references/skills-karte.md:13`). `amm-blog` hat einen eigenen Transkript-Modus (`SKILL.md:36`). Dass die
    Dreiergruppe später dazukam und nicht verzahnt wurde, ist Einschätzung, nicht belegt.
92. **Ein Aufbau für Ratgeber und Anleitung (Markus: „Ja, ein Aufbau“):** `tg-blog` und `tg-seo-content` schreiben beide
    nach demselben Gerüst, das P4 mit Hornbach als Vorbild herleitet (8.4 Punkt 14, 8.12 Punkt 57). `tg-seo-content`
    behält Lückenwahl, Auftrag und Prüfung. Von den sechs Everlast-Formaten bleiben für Tegards Ratgeber und Anleitung;
    fallstudie geht in der Seitenart Projekt auf. Das ist eine Anpassung gegenüber Everlast.
93. **Unverändert aus D10, bestätigt:** `amm-seo` wird `tg-seo` (der eine Ort für alle Regeln, Schluss-Schritt
    Meta-Block), `amm-keyword-research` wird `tg-keyword-research`, `/seo-komplett-audit` wird angepasst,
    `tg-serp-analyse` ist neu, die zwei Loops sind Fixpunkte.
94. **Monatlicher Regel-Check:** kommt gleich mit dem Workspace (Q6).
95. **An P4:** ob `amm-video-zu-blog` und `amm-pillar-to-blog` kommen (wenn ja, mit eigenem Aufbau, kein Umbau); die
    Abgrenzung des Transkript-Modus im Blog-Skill gegen die Video-Skills.
96. **Neuer Schritt am Schluss des Plans (Markus):** ein Abgleich auf Datei- und Code-Ebene. Jeder Skill, Agent, Command,
    jede Datei, Funktion und Logik von Everlast wird geprüft, ob es bei Tegards ein Gegenstück oder einen vergleichbaren
    Ansatz gibt. In `STAND.md` als fester Schritt nachzuziehen (noch nicht eingetragen).

Gelesen für diese Ergänzungen: `ELS:amm-seo-audit/SKILL.md` (ganz), `ELS:amm-seo-content/SKILL.md` (ganz),
`ELS:amm-blog/SKILL.md` (ab Zeile 17), `ELS:amm-blog/references/bauplaene.md` (Zeilen 14-35, 89-110, sonst Überschriften),
`ELS:amm-video-zu-blog/SKILL.md` (Zeilen 3-29, 168-197, sonst Überschriften), `ELS:amm-pillar-to-blog/SKILL.md` (Zeilen
3-18, sonst Überschriften), `EL:tools/dataforseo/dfs` (Befehlsliste). Nicht gelesen: die Baupläne der Formate glossar bis
thought-leadership im Wortlaut, `formregeln.md` des Video-Skills, `CO:agents/inventar-sync.md`.

### 8.16 Audit-Takt, Kostendeckel, Seitenwahl ohne Zahlenregel (beantwortet Q16 und die Reste; ändert Q4, D3)

Entstanden in einer Abzweigung der P3-Session zu den letzten offenen Punkten. Markus hat jeden Punkt dort mit Ja
entschieden und die Übertragung ausdrücklich angeordnet („festschreiben im plan und dann übertragen“).

97. **Takt des Komplett-Audits (Q16):** einmal im Quartal, als Hausregel. Wie Markus daran erinnert wird, klärt P7.
98. **Kostendeckel je DataForSEO-Lauf:** Ja. Eine Obergrenze je Lauf; ist sie erreicht, bricht der Lauf ab und meldet
    das. Zweck ist der Schutz gegen Fehlläufe (etwa ein Loop, der Abfragen wiederholt), kein Sparen. Die Höhe legt P7
    fest, sobald die echten Kosten für die eigene Domain bekannt sind.
99. **Search Console:** tegards.com ist dort bestätigt (Auskunft Markus). Die Entscheidung aus 8.8 steht damit ohne
    Vorbehalt.
100. **`SPAETER.md`, Zeile „ein Modus statt zwei Varianten“ (8.11 Punkt 51):** Der Auslöser wird neu formuliert, weil es
     die alten Variantennamen seit 8.12 Punkt 55 nicht mehr gibt: Markus wählt bei den Leitseiten immer wieder den
     Entwurf innerhalb des Designsystems oder immer wieder den außerhalb. Die Zeile selbst ist noch nicht geändert.
101. **Seitenwahl ohne Zahlenregel (ändert Q4 und D3):** Der Entscheidungsbaum aus commerce-os wird nicht übernommen.
     Die Schwellen „mindestens drei Blog-Themen, mindestens zwei Projekte im Jahr“
     (`CO:references/zielseiten-entscheidungsbaum.md:11-13`) entfallen: Bei einer neuen Linie gibt es noch keine
     Projekte, die Zahlen wären geraten und sind nie gemessen worden. Ob eine Linie eine eigene Landingpage bekommt oder
     die Kategorieseite die Leitseite ist, entscheidet der Themenplan je Linie aus den Suchergebnissen zum Kernbegriff
     (welche Seitenart dort vorne steht; 8.3, 8.10 Punkt 40). In 8.3 Punkt 9 ist „wenn die Linie den Entscheidungsbaum
     nicht erfüllt“ entsprechend zu lesen als „wenn die Suchergebnisse keine eigene Landingpage verlangen“.
102. **Zwei Regeln bleiben, als kurze Regeln im Keyword-Skill:**
     - Rollen der Shop-Seiten: `zielseite` (eigener Suchbegriff, ausführlicher Text) und `shop-seite` (kein eigener
       Suchbegriff, kurzer Text); `CO:references/zielseiten-entscheidungsbaum.md:30-34`. Daran hängt die Analyse-Tiefe
       aus 8.1 Punkt 3.
     - Familien-Regel: Varianten aus dem Konfigurator sind nie eigene Zielseiten, Zielseite ist die Kategorie oder der
       Haupttext der Produktfamilie (`:41-44`).
     „Je Suchbegriff genau eine Zielseite“ steht schon als Spalte im Keyword-Set (Q3).
103. **Für die Anpassung des Keyword-Skills:** Everlasts Regel „Die Absicht entscheidet die Seitenform, nicht das
     Suchvolumen“ (`ELS:amm-keyword-research/references/cluster.md:22`) bleibt; die Tabelle dort ist um
     Kategorie- und Produktseite zu ergänzen (siehe 1.4).

Gelesen für diese Ergänzungen: `CO:references/zielseiten-entscheidungsbaum.md` (Zeilen 1-53), bei Everlast nur die
Trefferzeilen `ELS:amm-keyword-research/SKILL.md:53`, `:61` und `references/cluster.md:13-22`.
