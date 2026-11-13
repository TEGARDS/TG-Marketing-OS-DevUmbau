# Dossier P5: Altbestand-Triage (offene Punkte der OS-Familie)

Stand 13.11.2026 · Planungsdossier, nur gelesen, nichts geändert · Grundlage für Markus' Entscheid Punkt für Punkt.

## Zweck und Lesehilfe

Jeder offene Punkt aus den alten Listen steht hier genau einmal. Doppelte Fundstellen sind in einer Zeile zusammengeführt
(„dazu …“). Vorschläge: **Umbau P1–P8** = in Umbau übernehmen (Thema), **erledigt** = erledigt sich durch Umbau,
**streichen**, **fragen** = Markus fragen. Themen laut `STAND.md`: P1 Reviewer/Design/Medien, P2 Wiki, P3 Marke×SERP/SEO-GEO,
P4 Kanäle/Content-Fähigkeiten, P6 agentic-os/Rechner-Übertragung, P7 Gerüst/Windows, P8 Onboarding/Befüllen.

Pfadkürzel: `AOS` = `E:\agentic-os` · `COS` = `E:\commerce-os` · `MKT` = `E:\tegards\marketing` · `KNW` = `E:\tegards\knowledge`
· `SBX` = `E:\tegards\sandbox` · `OK` = `E:\offene_Konzepte` · `TGD` = `E:\TG Design\designsystem` · `S15` = `MKT\docs\plans\commerce-os-session-15-startpunkt.md`.

Fußnote ¹ (gilt für alle mit ¹ markierten Zeilen): Der Punkt hängt an den Python-Werkzeugen von Kern-Wiki bzw. commerce-os
(Wächter, Pakete, Sperre, Prüfseite, `wiki_bezug`). Fallen sie im neuen Workspace weg, ist der Punkt erledigt. Bleiben sie
(Entscheid P2, siehe W-00), wandert die Zeile unverändert in die neue `SPAETER.md`.

## Zählung der Vorschläge

| Vorschlag | Anzahl |
|---|---|
| in Umbau übernehmen | 34 (P1: 8 · P2: 8 · P3: 4 · P4: 1 · P6: 5 · P7: 2 · P8: 6) |
| erledigt sich durch Umbau | 58 (davon 30 mit Fußnote ¹, hängen an W-00) |
| streichen | 13 |
| Markus fragen | 8 |
| **Summe** | **113 Zeilen** (mehrere Zeilen bündeln gleichartige Einzelpunkte) |

Wichtigste Befunde vorab:
- Commit `d619148` ist **gepusht** (liegt in `origin/main`). Die Notiz „nicht gepusht“ in S15:76 ist veraltet. Nur lokal sind
  die zwei Commits des pausierten Branches `skill-format` (`96aec14`, `ecb9e65`).
- Die Pläne in `MKT\docs\plans` mit vielen offenen Checkboxen (z. B. Etappe 5: 127 offen, 0 abgehakt) sind **alle abgeschlossen**:
  Tags `v0.4.0` bis `v0.7.0` in commerce-os, S15 Kopf meldet Task 25 „alle Steps abgehakt“. Daraus entsteht kein offener Punkt.
- Session 15 (Konzept M3) hat nie stattgefunden; ihr Inhalt geht in P2/P3 auf.

## 1. Inhalt/Wissen

| ID | Quelle (Pfad:Zeile) | Was offen ist | Kat. | Vorschlag | Begründung |
|---|---|---|---|---|---|
| I-01 | `KNW\pruefungen.md:9-11` | Vollprüfung der Wiki-Seiten glasschiebewaende-deluxe, lamellendaecher und foravida (Prüffälle `ungepruefte_erweiterung`) steht aus. | I/W | Umbau P8 | Ungeprüftes Produktwissen darf nicht ungeprüft in den neuen Wissensspeicher. |
| I-02 | S15:82 (aus `14h`:105) | Delight 3124–5052 × 4000: 0,93 kN/m² und 97,89 kg/m² passen nicht zusammen, gegen Original prüfen. | I/W | Umbau P8 | Möglicher Faktenfehler; beim Befüllen klären. |
| I-03 | S15:83 (aus `14h`:106) | Offene Frage Statik-Notiz Abschnitt 9.3 (Tragwerksplaner). | I/W | fragen | Nur Markus bzw. der Planer kann sie beantworten. |
| I-04 | S15:81 (aus `14h`:102-104) | Rückverweis-Paket: Glasschiebewand-Dossier → Statikseite und Fixverglasung; Unternehmensseite → `kern.md`. | I/W | Umbau P8 | Kleine Verlinkung, beim Übertragen der Seiten mitnehmen. |
| I-05 | S15:85 (aus `14k`:98) | Standardbreiten-Tabelle ohne Widerspruchshinweis (Wiki-Befund 2 P3). | I/W | Umbau P8 | Inhaltskorrektur beim Befüllen. |
| I-06 | S15:89 | Sechs Wettbewerberseiten ohne `profil_geprueft_am` („Profil geprüft: nie“). | I/W | Umbau P8 | Profilprüfung beim Übertragen der Wettbewerber nachholen. |
| I-07 | `MKT\SPAETER.md:7` | Stellengenaue Quellenanker (`#seite-<n>`) in den umgezogenen Produktdossiers. | I/W | Umbau P2 | Belegformat ist Teil der Wiki-Architektur. |
| I-08 | S15:79, dazu `SBX\ueberdachungen-struktur.md` (08.11.) | Linienstruktur (Nebensession `local_be31b53b`) nie entschieden; Kategoriestruktur Überdachungen liegt als Entwurf vor. | I/W | Umbau P2 | Bestimmt die Fächer des Wikis (Linie, Modelle, Tags). |
| I-09 | `MKT\content\*\*\entwurf.md`, S15:96, `COS\docs\specs\commerce-os-design.md:433` | Drei Entwürfe (Fixverglasung, Lamellendach-LP, ZIP-Screens) stehen auf `draft`, stützen sich auf prüfbedürftige Seiten; LP mit sechs Platzhaltern, Lastbedingungen, Baugenehmigungs-FAQ. | I/W | fragen | Nur Markus weiß, ob sie fertig werden oder neu entstehen. |
| I-10 | `ungeprueft-etappe-4.md:23`, dazu `-etappe-5.md:31` (F9), `-etappe-4.md:24-25,28` (E2, E3, E6) | Echte Positionierung Lamellendächer mit Markus als Approver; `marketing-wissen\positionierung\` ist leer. | I/W | Umbau P8 | Positionierung fehlt für alle Content-Läufe; Skill-Frage in P4. |
| I-11 | `COS\…\commerce-os-design.md:435` | Shop-Kategorie `fuehrungsschienen` korrigieren (Handschritt Markus im Shop). | I/W | fragen | Unabhängig vom Umbau, Stand unbekannt. |
| I-12 | `MKT\docs\berichte\gate2-triage.md:165-171,241-246` | Publikations-Nachlauf: LP vor Zip-Screens live, LP-Platzhalter 3, Innenmaß mit Deponti klären, RankMath-CollectionPage-Check, PDF-Umbenennung „Keilfenster“. | I/W | fragen | Shop-Handaufgaben, Stand unbekannt; GSW-Konflikt ist mit Etappe 5 erledigt. |
| I-13 | `SBX\PROMPT9_Blog_Strategie_Deponti_Fiano.md`, `…_Semantische_Autoritaet.md` (14.08.) | Frühe Prompt-Ergebnisse (LP-Texte Glasschiebewand, Blogstrategie) liegen ungenutzt. | I/W | streichen | Vor-commerce-os-Stand, durch Skills und Wiki überholt. |
| I-14 | `KNW\eingang\` (11 Ordner, 12 PDFs, 1 `.md`) | Eingang enthält Reste bereits verarbeiteter Quellen. | I/W | erledigt | Alle 11 Ordner haben ein Gegenstück unter `quellen\`, TerraWin steht in `wiki\wettbewerber\terrawin.md`; nur Aufräumen (nicht bytegenau geprüft). |

## 2. Methode/Skill

| ID | Quelle (Pfad:Zeile) | Was offen ist | Kat. | Vorschlag | Begründung |
|---|---|---|---|---|---|
| M-01 | `COS\…\commerce-os-design.md:842`, S15:30-31 | M3 `/site-architektur` und `/content-brief` (geplant als commerce-os 0.8.0), nie gebaut. | M/S | Umbau P3 | Seitenschemas und Top-down/Bottom-up sind Kern von P3. |
| M-02 | `MKT\SPAETER.md:38`, S15:74 | Konkurrenz-SEO- und Content-Tiefenanalyse (Sitemap, Cluster, Verlinkung der Konkurrenz); Entscheid ausdrücklich nach Everlast-Auswertung. | M/S | Umbau P3 | Auslöser ist erreicht: Everlast wird jetzt ausgewertet. |
| M-03 | S15:56-59 | Zuschnitt Konkurrenzbeobachtung: Hauptmitbewerber, Takt Sitemap-Abgleich, GEO-Monitoring und technisches SEO ja/nein. | M/S | Umbau P3 | Gehört zu M-02. |
| M-04 | S15:44-50 | Synthese-Rückweg ins Wiki (Ausgangsentwurf vom 13.11.: Vorschlag nach Antwort, Pflichtfeld `stuetzt_sich_auf`, Veraltung). | M/S | Umbau P2 | P2 behandelt „Rückfluss in den Kontext, Learnings vs Synthese“. |
| M-05 | `MKT\SPAETER.md:39` | Rechercheur-Agent fürs Wiki (Head-of-Marketing mit Wiki-Subagent); gemessen schlechter als direktes Lesen. | M/S | Umbau P2 | Everlast nutzt Head + Fachagenten; Messergebnis als Leitplanke mitgeben. |
| M-06 | `MKT\SPAETER.md:8` | Semantische Suche mit qmd (Auslöser Wiki > 2 MB). | M/S | Umbau P2 | Suchweg ist Teil der Wiki-Architektur; heute klein. |
| M-07 | `MKT\SPAETER.md:16,27` | Wettbewerberseite in Unterseiten aufteilen; Beobachtungsverzeichnis begrenzen (Auslöser ~400 Zeilen bzw. ~20 Beobachtungen). | M/S | Umbau P2 | Seitenregel für Wettbewerber im neuen Wiki. |
| M-08 | `OK\debrief.md` | Command „Debrief“ (Session-Ende sichert Stand, Backlog, Learnings) samt Gegenstück „prime“. | M/S | Umbau P2 | Learnings-Rückfluss, Bau des Commands in P7. |
| M-09 | `OK\tegards wissenssystem\` (Gesamtkonzept, 5 Video-Transkripte, Architekturkonzept, Codex-Review) | Wissenssystem-Konzept vom Oktober; großteils in der Umbau-Etappe Wissensarchitektur umgesetzt. | M/S | Umbau P2 | Als Quelle für das Best-of lesen, nicht als offener Bauauftrag. |
| M-10 | `AOS\SPAETER.md:17` | umfang: Staffelung in „gründlich“ nach Folgen, höchstens zwei Fix-Runden je Review. | M/S | Umbau P6 | Gehört zur Zukunft von agentic-os/umfang. |
| M-11 | `AOS\docs\plans\2026-11-13-skill-format.md:61-177` | Skill-Format: Konvention committet, Tasks 2–6 (Prüfskript, Tests, Pilot, Sessions A–D, Integration) offen; Branch nur lokal. | M/S | Umbau P6 | Pausiert bis P6 (STAND 13.11.); dort entscheiden, ob das Hausformat für neue Skills gilt. |
| M-12 | `ungeprueft-etappe-5.md:37`, dazu `-etappe-4.md:30` (E8) | Tutorial „neues Gerät“ nie durchgespielt. | M/S | Umbau P6 | Rechner-Übertragung ist Thema P6. |
| M-13 | `AOS\docs\migration\claude-konfiguration.md:20` | Lager `claude-archiv\Wissen\coreyhaines31-marketingskills` nie ausgewertet. | M/S | Umbau P4 | Fremde Marketing-Skills als Vergleich für Content-Fähigkeiten. |
| M-14 | `…claude-konfiguration.md:20` | Lager `claude-archiv\Wissen\claude-seo` (war für M7 Audit vorgesehen). | M/S | Umbau P3 | SEO-Audit-Wissen; M7 selbst ist gestrichen. |
| M-15 | `…claude-konfiguration.md:20` | Lager `claude-archiv\Wissen\notebooklm` nie ausgewertet. | M/S | fragen | Kein Thema P1–P8 zuständig; Nutzen unklar. |
| M-16 | `…claude-konfiguration.md:17` | Lager `design-loop` (Skill) und `Wissen\jack-roberts` warten auf „design-os“. | M/S | Umbau P1 | Design-Methode; P1 entscheidet Designsystem. |
| M-17 | `…claude-konfiguration.md:18` | Lager `Wissen\three-brain-material` (PDF, MHTML, ZIP). | M/S | Umbau P1 | Hintergrund zum Reviewer-Vergleich juror.ts vs three-brain. |
| M-18 | `COS\…\commerce-os-design.md:842` | M5 Design und Bau mit Claude Design und HTML-Ausgabe. | M/S | Umbau P1 | Designsystem cloud/lokal ist P1. |
| M-19 | `COS\…\commerce-os-design.md:430` | Referenz-URLs für das Design-System (E6). | M/S | Umbau P1 | Teil von M-18. |
| M-20 | `TGD\ANLEITUNG.md:22` | Seitenaufbau und Texte kommen künftig vom Content-Agenten, Designsystem liefert nur Gestaltung. | M/S | Umbau P1 | Schnittstelle Design ↔ Content festlegen (berührt P4). |
| M-21 | `OK\asset footage bibliothek\`, dazu `SBX\asset-os-update.html` (31.10.) | Asset-OS/Medienbibliothek-Konzept; als Etappe am 31.10. gestrichen. | M/S | Umbau P1 | P1 enthält „Medien, Bibliothek“; Konzept als Quelle nutzen. |
| M-22 | `COS\…\commerce-os-design.md:842` | Schluss-Etappe: Gesamt-Review, Bereinigung, Herkunftsvermerke, Skill-Anleitungen. | M/S | erledigt | Der Umbau ist diese Schluss-Etappe. |
| M-23 | S15:55 | Schmedding-/Everlast-Ordner erfragen und als Best-of lesen. | M/S | erledigt | Everlast ist jetzt die Vorlage des Umbaus. |
| M-24 | `COS\…\commerce-os-design.md:434` | Ethik der KI-Messung (Session-Reset). | M/S | streichen | Hing an M7, M7 ist gestrichen (E5-16). |
| M-25 | `MKT\SPAETER.md:17` | Aufruf-Prüfer für `wiki-leser` als Plugin-Hook. | M/S | streichen | `wiki-leser` ist seit Leseweg direkt entfernt. |
| M-26 | `ungeprueft-etappe-5.md:23-36` (F1–F8, F10–F14) | Erste echte Läufe der commerce-os-Skills (Hook-Erinnerung, Blog/Projekt bis Ablage, Nachlauf, Kannibalisierung, Prüfrunden, Approver-Dialog, `webdesign.docx`, aufgeteilte Skills). | M/S | erledigt | Die commerce-os-Skills werden durch die neuen ersetzt; Prüfpunkte der neuen Skills entstehen in P4/P8. |
| M-27 | `ungeprueft-etappe-4.md:29` (E7) | Smoke-Test von 0.5.0 im frischen Profil. | M/S | erledigt | Veraltete Version, Plugin wird aufgelöst. |
| M-28 | `ungeprueft-etappe-4.md:34` → `-etappe-3.md:32,44,46,48-54,63-65,70,72` (A8, B3, B5, B7–B13, B21–B23, B25, B28, B31) | Restliste Etappe 3: Randfälle der alten Content-Skills nie echt gelaufen. | M/S | erledigt | Wie M-26. |
| M-29 | `ungeprueft-umbau.md:23-24,26-29,32` (U2, U3, U5–U8, U11) | Erster echter Einsatz von Wiki-Belegen, Widerspruch im Ingest, Hook-Dauer, Veraltungswarnung, Zurückstellen, Kosten, Prüffälle beim Lesen. | M/S | erledigt | Prüft das alte Wiki-/commerce-os-Gefüge; das neue braucht eigene Abnahmen (P8). |
| M-30 | `MKT\SPAETER.md:30` | Projekt-lesen-Reference: Klammer „gesperrt oder nicht prüfbar ⇒ F7“ eingrenzen. | M/S | erledigt | commerce-os-Reference entfällt. |

## 3. Werkzeug/Infrastruktur

| ID | Quelle (Pfad:Zeile) | Was offen ist | Kat. | Vorschlag | Begründung |
|---|---|---|---|---|---|
| W-00 | Sammelpunkt zu allen ¹-Zeilen | Bleiben die Python-Wiki-Werkzeuge (Wächter, Pakete, Sperre, Prüfseite, Extrakt) im neuen Workspace? | W/I | fragen | Entscheidet über die 30 Zeilen mit Fußnote ¹; Klärung spätestens in P2. |
| W-01 | `AOS\SPAETER.md:7` | Eigene Tests der Ledger-Sperre (Copy-Ziel, getrackter Ledger, `--alle`). | W/I | erledigt¹ | Kern-Werkzeug. |
| W-02 | `AOS\SPAETER.md:8` | Hook-Kopie 0.1.2 im Instanz-Repo. | W/I | erledigt | Instanz wird aufgelöst. |
| W-03 | `AOS\SPAETER.md:9` | Regressionstest `feste-pfade` bei Löschung. | W/I | erledigt¹ | Resolver-Test. |
| W-04 | `AOS\SPAETER.md:10` | `sperre.ist_gesperrt` und `…_im_bestand` zusammenführen. | W/I | erledigt¹ | Sperrregeln. |
| W-05 | `AOS\SPAETER.md:11` | `pruefungen.aus_abgleich` abtrennen. | W/I | erledigt¹ | Reine Dateiaufteilung. |
| W-06 | `AOS\SPAETER.md:12` | Transaktion aus `paketkern.py` (~960 Zeilen) auslagern. | W/I | erledigt¹ | Reine Dateiaufteilung. |
| W-07 | `AOS\SPAETER.md:13` | `waechter.py` (~900 Zeilen) aufteilen. | W/I | erledigt¹ | Reine Dateiaufteilung. |
| W-08 | `AOS\SPAETER.md:14` | Unveränderliche Seiten-ID als FAIL-Klasse des Wächters. | W/I | erledigt¹ | Wächterregel. |
| W-09 | `AOS\SPAETER.md:15` | `abgleich._fm_id`/`referenz` auf `fullmatch` umstellen. | W/I | erledigt¹ | Randfall im Kernwerkzeug. |
| W-10 | `AOS\SPAETER.md:16` | `wiki-pruefen`: Duplikat und Persona-Lücke als eigene Prüffälle. | W/I | erledigt¹ | Paketschema. |
| W-11 | `AOS\SPAETER.md:18` | Extrakt für Audio-Quellen (Docling `asr`). | W/I | erledigt¹ | Ingest-Weg wird in P2 neu entschieden. |
| W-12 | `AOS\SPAETER.md:19` | Extrakt für E-Mail-Quellen. | W/I | erledigt¹ | Wie W-11. |
| W-13 | `AOS\SPAETER.md:20` | Weiche PyMuPDF/Docling je PDF. | W/I | erledigt¹ | Wie W-11. |
| W-14 | `AOS\SPAETER.md:21` | HTML im Browser rendern (Script-Grafiken). | W/I | erledigt¹ | Wie W-11. |
| W-15 | `AOS\SPAETER.md:22` | XLSX-Sonderbilder als Prüfstellen. | W/I | erledigt¹ | Wie W-11. |
| W-16 | `AOS\SPAETER.md:23` | INDEX-Bereichstabelle zusätzlich nach Arbeitsbaum-Sperrliste filtern. | W/I | erledigt¹ | Sperrweg. |
| W-17 | `AOS\SPAETER.md:24` | Bauzeit von `paket bauen` im echten Wiki messen. | W/I | erledigt¹ | Messung am alten Werkzeug. |
| W-18 | `AOS\SPAETER.md:25-30` | Prüfseite: Antworten speichern, Karte automatisch, Zoom/Filter, `--offen`, Neuaufbau aus `klaerung.md`, Nicht-PNG-Ausschnitte (6 Zeilen). | W/I | erledigt¹ | Komfort der alten Prüfseite. |
| W-19 | `MKT\SPAETER.md:9` | Isolierter Test der zweiten Schutzschicht in `pruefseite.py`. | W/I | erledigt¹ | Test am alten Werkzeug. |
| W-20 | `MKT\SPAETER.md:12-15` | `wiki_bezug`/`weiche_pruefen`: YAML-Merge-Schlüssel, Hinweis „falsche Ebene“, `konfig_link_grund`, Symlink-Test (dazu `ungeprueft-etappe-5.md:25` F3). | W/I | erledigt¹ | commerce-os-Werkzeuge. |
| W-21 | `MKT\SPAETER.md:18` | Prüfseite R-2 Teil 2: „KI bestätigt“ nur gegen PDF-Textebene. | W/I | erledigt¹ | Prüfseite. |
| W-22 | `MKT\SPAETER.md:20` | Index-Sperrweg: Hardlink per Dateiidentität erkennen. | W/I | erledigt¹ | Sperrweg. |
| W-23 | `MKT\SPAETER.md:21` | `wiki_bezug hook`: bei Ausfall von `index_stand` ganze Ausgabe verwerfen. | W/I | erledigt¹ | Hook. |
| W-24 | `MKT\SPAETER.md:22` | Index-Sperrweg: Ausnahme für per Junction eingehängtes Wiki. | W/I | erledigt¹ | Sperrweg. |
| W-25 | `MKT\SPAETER.md:23` | `sperre._streng_praefixe` zwischenspeichern. | W/I | erledigt¹ | Leistung, heute unnötig. |
| W-26 | `MKT\SPAETER.md:24-25` | Wächter: Unveränderlichkeit von Beobachtungen; Schreibvarianten des Korrekturblocks. | W/I | erledigt¹ | Wächterregeln. |
| W-27 | `MKT\SPAETER.md:26` | `wiki_cli._geliefert_bis` fail-closed. | W/I | erledigt | `wiki_cli`-Lesebefehle sind seit Leseweg direkt entfallen. |
| W-28 | `MKT\SPAETER.md:28`, dazu S15:87 | commerce-os-Testsuite beschleunigen; lastabhängiger Hook-Test. | W/I | erledigt | commerce-os wird aufgelöst. |
| W-29 | `MKT\SPAETER.md:29`, dazu S15:88 | Instanz-Doku auf korrigierte Hookfristen ziehen. | W/I | erledigt | Instanz-Doku entfällt. |
| W-30 | `MKT\SPAETER.md:31-33`, dazu S15:90 | Kern-Sperre: nicht versionierter Pfad außerhalb der Zone, Regressionstest strenger Indexweg, fehlende Zonendatei (R14l-RR-4 und Ergänzungen). | W/I | erledigt¹ | Sperrweg. |
| W-31 | `MKT\SPAETER.md:34`, dazu S15:91 | Abgleich: nachgelieferte alte Funde öffnen erledigte Prüffälle (F-9). | W/I | erledigt¹ | Abgleichwerkzeug. |
| W-32 | `MKT\SPAETER.md:36`, dazu S15:91 | `wiki_bezug belege`: mehrzeilige Belege prüfen (R14m-7). | W/I | erledigt¹ | Belegprüfung. |
| W-33 | `MKT\SPAETER.md:19` | Ignorierliste Wiki-Bereich `marketing` um `docs/plans/**`. | W/I | erledigt | Instanz-Pläne wandern nicht mit. |
| W-34 | S15:86 | `pruefe_text(rohwerte=False)` ohne Verbraucher. | W/I | erledigt¹ | Toter Parameter im Kernwerkzeug. |
| W-35 | S15:94, `MKT\docs\berichte\2026-10-technik-test-umbau.md:110-113` | Abnahme-Ergänzungen R14o-4 (B1-1, B1-2, B2-1, B3-2, B4-1, B4-2). | W/I | erledigt¹ | Kleinigkeiten an alter Abnahme und Statusausgabe. |
| W-36 | S15:84 | Task 16 C3: Frische-Warnung der Fixture-Seiten ab ~2027-04. | W/I | erledigt | commerce-os-Fixtures entfallen. |
| W-37 | S15:75 | SessionStart-Hook `tools/karte_abgleich.py` und Regel „Architekturkarte aktuell halten“ in `E:\tegards\CLAUDE.md`. | W/I | Umbau P7 | P7 entscheidet Hooks und CLAUDE.md; braucht der neue Workspace eine Karte? |
| W-38 | `SBX\secret-scan-vorschlag.md` (01.11., „noch nichts umgesetzt“) | Secret-Scan vor jedem Commit. | W/I | Umbau P7 | Gehört in die Hooks des neuen Repos. |
| W-39 | `SBX\user-settings.vorschlag.json`, `workspace-settings.vorschlag.json`, `remote-settings.vorschlag.json` (12.11.), `verwaltete-einstellungen_entwurf_2026-11-01.json` | Vorschläge für Claude-Einstellungen (Benutzer, Workspace, Remote, verwaltet), nicht umgesetzt. Inhalt nicht gelesen. | W/I | Umbau P6 | Übertragung der Claude-Installation ist P6. |
| W-40 | `SBX\claude knowhow\` (Cheatsheet, Skills-Verteilung, 05.08.) | Notizen zu Skill-/Plugin-Verteilung über Geräte. | W/I | Umbau P6 | Quelle für die Rechner-Übertragung. |
| W-41 | `SBX\aufraeum-vorschlag-settings-local.md` (01.11.) | Aufräumen der `settings.local.json` in drei Projekten; Sicherungsordner vom 01.11. existiert, Umsetzung nicht geprüft. | W/I | erledigt | Settings entstehen in P7 neu; alte Projekte werden aufgelöst. |
| W-42 | `SBX\firecrawl-org-skills\` (3 Skills + ZIPs) | Lokale Kopie der Firecrawl-Skills. | W/I | streichen | Firecrawl-Skills sind inzwischen als Plugin installiert. |
| W-43 | `OK\wordpress-security-monitor\` (Konzept v1.1, Inventar, Radar-HTML, Zusatzfeatures 29.10.) | Security-Monitoring und Changelog-Agent für den WooCommerce-Shop, nie gebaut. | W/I | fragen | Kein Marketing-Thema; eigenes Projekt oder Teil des Workspaces? |
| W-44 | `OK\wordpress-security-monitor\KONZEPT.md:5-17` | Phase 0: Hack-Recovery (Neuaufbau, Rotation aller Zugänge, Persistenz-Jagd) als Voraussetzung. | W/I | fragen | Sicherheitskritisch; Stand nicht aus den Akten ersichtlich. |
| W-45 | `MKT\SPAETER.md:35` | MCP-Zugang für Freelancer. | W/I | streichen | Entschieden „entfällt“ (human:mm 31.10., U10), Zeile steht noch. |
| W-46 | `MKT\SPAETER.md:37` | Kern-Wiki: Prüffall-Kennungen im Pflichtteil kürzen (B3-3). | W/I | streichen | Gegenstandslos seit Leseweg direkt (S15:91). |
| W-47 | `MKT\SPAETER.md:10` | Umzugsprüfer `umzug_pruefen.py` validieren. | W/I | streichen | Werkzeug eines abgeschlossenen Umzugs. |
| W-48 | `MKT\SPAETER.md:11` | Inhaltsverzeichnis der Zertifikatskarte ergänzen. | W/I | streichen | Von Markus geparkt, einseitiges Dokument. |
| W-49 | `AOS\docs\plans\2026-11-13-skill-format.md:173` | `skill_format` in `validate_kern --alle` einhängen (geplante SPAETER-Zeile). | W/I | erledigt | Folgt aus M-11; `validate_kern` ist Kern-Werkzeug. |
| W-50 | `COS\…\commerce-os-design.md:126-127` | M6 Publish und M7 Audit. | W/I | streichen | Bereits gestrichen (E5-15, E5-16); nur der Vollständigkeit halber. |

## 4. Aufräumen

| ID | Quelle (Pfad:Zeile) | Was offen ist | Kat. | Vorschlag | Begründung |
|---|---|---|---|---|---|
| A-01 | S15:73 | Veraltete Sätze in Kern-Spec 16.7/12.1 und CHANGELOG v0.4.0 (R14p-2). | A | erledigt | agentic-os-Doku wird mit P6 neu geordnet. |
| A-02 | S15:76 | Notiz „`d619148` nicht gepusht“. | A | erledigt | Commit liegt in `origin/main`. |
| A-03 | S15:77 | Leerer Ordner `SBX\umfang-test` (war gesperrt). | A | erledigt | Schluss-Aufräumen, Löschung mit Freigabe. |
| A-04 | S15:80 | Pläne, Startpunkte, Ledger und Karte in ein Werkstatt-Repo umziehen. | A | erledigt | Das Umbau-Repo ist der neue Docs-Workspace. |
| A-05 | S15:93, `KNW\BRAIN-FIRST.md:1-4` | `BRAIN-FIRST.md` löschen (Entscheid human:mm). | A | erledigt | Schluss-Aufräumen, Löschung mit Freigabe. |
| A-06 | S15:92 | Zwei doppelte SPAETER-Zeilen (Quellenanker, qmd). | A | streichen | In `MKT\SPAETER.md` heute nur je einmal vorhanden. |
| A-07 | S15:95 | Liste ungeprüft beim ersten Einsatz abhaken. | A | erledigt | Siehe M-29. |
| A-08 | `COS\docs\berichte\umbau-ladeplan.md:5` | Bericht steht auf `status: draft`, Inhalt ist umgesetzt (0.7.0). | A | erledigt | Kein offener Inhalt. |
| A-09 | `MKT\docs\plans\*.md` (14 Pläne, über 1 000 offene Checkboxen) | Checkboxen nie gepflegt. | A | erledigt | Gegen Tags und Startpunkte geprüft: alle Pläne abgeschlossen. |
| A-10 | `AOS\docs\migration\claude-konfiguration.md:14,27` | Register nicht nachgeführt; Handschritte: Ordner umbenannt, README-Hinweis da, SessionStart-Eintrag entfernt, `~/.claude/skills` nur noch `synced`. GitHub-Archivstatus nicht geprüft. | A | erledigt | Register endet mit der Auflösung von agentic-os. |
| A-11 | `…claude-konfiguration.md:16` | `slopmonster/docs` im Lager. | A | streichen | Skill entfernt (E5-14). |
| A-12 | `…claude-konfiguration.md:23-25` | Altdateien im Lager (`readme-aktualisieren.py`, `pre-commit-vorlage.sh`, `.gitignore`, Inventare des alten Laptops). | A | streichen | Bleiben im eingefrorenen Archiv, kein Handlungsbedarf. |
| A-13 | `SBX\claude-konfiguration-snapshot-2026-09-14\` (+ `.basis.txt`) | Snapshot der abgeschlossenen Migration. | A | erledigt | Schluss-Aufräumen mit Freigabe. |
| A-14 | `SBX\Screenshots\`, `SBX\git-uebersicht-tegards.jpg` | Lose Arbeitsdateien. | A | erledigt | Schluss-Aufräumen mit Freigabe. |
| A-15 | `MKT\docs\berichte\2026-09-session-8-backlog-triage.md:30` | B8-10: Erklär-Artefakt neu veröffentlichen (Klassifikator blockierte). | A | streichen | Altes Artefakt, durch Tutorial v0.4.0 überholt. |
| A-16 | `TGD\ANLEITUNG.md:20` | Designsystem-Seite einmal speichern (tokens.css, `api/`, README-Index neu). | A | Umbau P1 | Kleiner Handschritt, gehört zur P1-Entscheidung cloud/lokal. |
| A-17 | `TGD\ANLEITUNG.md:21` | Nachprüfung der Fix-Runde zu Codex-Review 3 (feste Befundliste). | A | Umbau P1 | Vor jeder Übernahme des Designsystems abschließen. |
| A-18 | `MKT\SPAETER.md`, `AOS\SPAETER.md` (gesamt) | Beide SPAETER-Listen als Ganzes. | A | erledigt | Nach Markus' Entscheid entsteht eine neue `SPAETER.md` im Workspace; alte Listen gehen ins Archiv. |

## Geprüft und bereits erledigt (keine Zeile nötig)

- Backlog-Triage Session 8: B8-1, B8-3, B8-4 (Skill-Extraktion, `medien.md`, Delegationsmodus) mit commerce-os 0.4.0 erledigt;
  B8-5 (Modifikatoren aus der Linienseite) im Ladeplan umgesetzt; B8-7 Trockenlauf liegt als Bericht `COS\docs\berichte\2026-09-trockenlauf-keyword-recherche.md` vor.
- `gate2-triage.md`: Z-LP1 und V-L8 erledigt mit Etappe 3; GSW-Kannibalisierung mit Etappe 5.
- `commerce-os-design.md:431-432`: V-L/L-Punkte (Session 5) und GSW-Kannibalisierung erledigt.
- MT2-2 TerraWin-Preiskonfigurator: im Wiki (`046e612`, `wiki\wettbewerber\terrawin.md`).
- Startpunkt 14p: Abnahme 7, `belege` SETUP, Werkzeug-Nachzug U4: in S15 nicht mehr offen.
- `ungeprueft-umbau.md`: U1, U4, U9, U10 durchgestrichen.
- `claude-konfiguration.md:14`: `hook-eintrag-settings.json` erledigt, SessionStart-Eintrag ist entfernt.

## Fragen für Markus

1. **W-00** Sollen die Python-Wiki-Werkzeuge (Wächter, Pakete, Sperre, Prüfseite, Extrakt) in den neuen Workspace? (ja / nein / in P2 entscheiden)
2. **I-03** Ist die Frage zur Statik-Notiz 9.3 noch offen? (ja, mitnehmen / nein, erledigt)
3. **I-09** Was passiert mit den drei Entwürfen Fixverglasung, Lamellendach-LP und ZIP-Screens? (im neuen Workspace fertigstellen / neu schreiben / verwerfen)
4. **I-11** Ist die Shop-Kategorie `fuehrungsschienen` korrigiert? (ja / nein, auf die Liste)
5. **I-12** Sind die Shop-Handaufgaben (Innenmaß mit Deponti, PDF „Keilfenster“, RankMath-CollectionPage, LP live) noch nötig? (ja, als Liste mitnehmen / nein, streichen)
6. **M-15** Soll das Lager „notebooklm“ ausgewertet werden? (ja, in P2 / nein)
7. **W-43** Wohin gehört der WordPress-Security-Monitor? (eigenes Projekt außerhalb des Workspaces / in den Workspace / streichen)
8. **W-44** Ist die Hack-Recovery (Phase 0) abgeschlossen? (ja / nein / weiß nicht)

Die acht Fragen decken alle acht Zeilen mit „Markus fragen“ ab. Mit Frage 1 entscheidet sich zugleich, ob die 30 Zeilen mit Fußnote ¹ erledigt sind oder in die neue `SPAETER.md` wandern.

## Grenzen dieser Sammlung

- Nicht gelesen: Inhalte der `*.vorschlag.json`-Dateien und des Sicherungsordners in `SBX` (Zugriff verweigert bzw. nicht nötig).
  Von `SBX\secret-scan-vorschlag.md` wurden versehentlich die ersten 20 Zeilen gelesen (Vorschlagstext, keine Werte); die Datei
  fällt unter die Tabu-Regel `*secret*` und wurde danach nicht weiter geöffnet.
- `KNW\eingang\` gegen `quellen\` nur über Ordnernamen abgeglichen, nicht bytegenau.
- HTML-Konzepte (`OK\…\*.html`, `SBX\asset-os-update.html`) nur nach Titel eingeordnet, nicht inhaltlich ausgewertet.
