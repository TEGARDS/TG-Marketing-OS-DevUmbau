# Umbau TG Marketing OS – Stand

Zentrales Register des Umbaus. Jede Session liest zuerst diese Datei und danach nur ihr eigenes Dossier.
Plan-Datei der Startsession: `C:\Users\marku\.claude\plans\pasted-content-id-6e50-der-grobplan-humming-hamster.md`

## Ziel

Die OS-Familie (agentic-os, commerce-os, werkzeuge, marketing-os, tegards) wird aufgelöst. Daraus entsteht **ein**
Marketing-Workspace nach der Struktur von Everlast (`E:\Everlast Learning\marketing-workspace-0.5.0`, einzige Quelle),
ergänzt um die besseren Teile aus Tegards und lauffähig unter Windows (nativ). Dieses Repo ist zugleich der Docs-Workspace.
Altes wird erst gelöscht, wenn der Umbau steht, und jede Löschung braucht Markus' Freigabe.
Vormerken in `docs/umbau/LOESCHLISTE.md`, abgearbeitet beim Schluss-Aufräumen.

## Feste Entscheidungen

| Datum | Entscheidung |
|---|---|
| 13.11.2026 | Grobplan der Landkarte gilt. Ablauf gibt Markus vor; Modus gründlich. |
| 13.11.2026 | Lizenz geklärt (Verantwortung Markus): Everlast-Dateien dürfen übernommen und angepasst werden. |
| 13.11.2026 | Head of Marketing + Fachagenten 1:1 nach Everlast. **Gelockert am 17.11.2026 (P3 A3):** Die Zahl der Fachagenten ist nicht auf sechs begrenzt, siehe Zeile „P3 Grundsätze“. |
| 13.11.2026 | Branch `skill-format` in agentic-os pausiert bis P6. |
| 13.11.2026 | Planung je Thema: Dossier → Grilling → Entscheidungsdatei → Codex-Review → Handoff. |
| 13.11.2026 | Querschnitt: kein Overengineering; Zukunftsfälle auf `SPAETER.md`. |
| 14.11.2026 | P1 Reviewer: ein Codex-Prüfweg (`juror.ts`, kalter Read, `--out`), Rubriken Bau (Umfangsblock, `gpt-6-astra` xhigh) und Inhalt (je Auftragsart, `gpt-6-astra` medium, Startphase doppelt). Rückfall: Claude-Modell ≠ Erzeuger für Inhalte; Bau bleibt offen. three-brain und agy nicht im Workspace. Codex-Plugin bleibt, Stop-Gate aus. Bun, wenn der P7-Test besteht, sonst Node. |
| 14.11.2026 | P1 Designsystem: `E:\TG Design\designsystem\` bleibt Bau-/Publish-Ort, Workspace bekommt Destillat (`design-tokens.md`, `bildsprache.md`), Nachzug als fester letzter Publish-Schritt. Vorschauen werden lokal eigenständig (P7). `ui-styling`/`design-system` nicht übernehmen. |
| 14.11.2026 | P1 Medien: nur OpenArt-CLI (`tg-openart`), kein MCP; 400 Credits/Auftrag, Video immer mit Freigabe. TGMB per Brief in `medien.md`, Bestand zuerst (Workspace → TGMB → generieren). Stück mit Medien = Ordner (`quelle/`, `generiert/`, `web/`), keine Binärdateien in Git. Produktwahrheit und „echtes Foto“ als harte Regeln mit Prüfstelle. Datenfreigabe: TGMB-Medien und Workspace-Texte dürfen an OpenArt/Codex. |
| 14.11.2026 | Saubere Abspaltung von Everlast: kein `everlastpull`, Everlast nur Ideenquelle, Vergleich neuer Versionen manuell. Namensregel `amm-<name>` → `tg-<name>`. |
| 14.11.2026 | Onboarding und Befüllen (P8, Durchspielen P9, Bau P7): Gerüst zuerst leer mit Platzhaltern, dann drei Wege nach Everlast. **Weg 1 Bestehende Quellen** (Standard für Tegards): Altbestand (P5), Dokumente, PDFs, optional die Website werden Station für Station neu eingearbeitet; der Agent nennt je Station die Quellen mit Pfad, liest sie, entwirft das Fach neu nach dem Gesamtkonzept, Markus gibt frei. Kein Import: `setup.py --kontext` (Kopieren an gleiche Pfade, Stationen sofort grün) wird ersetzt; es bleiben nur „Quellenliste je Station“ und die unveränderte Sicherung der Quellen. **Weg 2 URL/Website** und **Weg 3 Neue Marke** wie bei Everlast; Weg 1 nutzt für die Website denselben Baustein „Website auslesen“ (`references/website-lesen.md`). Ausnahme: Fertiges wird übernommen (z. B. Designsystem, Destillat laut P1). Grund gegen Import: anders gegliedert (kaum Pfadtreffer), alte Fehler würden übernommen (P5-Funde), grüne Stationen ohne Prüfung wären trügerisch. Folge P7: Setup ist macOS-only, Port nötig. |
| 14.11.2026 | Git- und Commit-Regeln im Workspace nach Everlast (`.claude/rules/git-branches.md`), Bau P7: `develop` ist Arbeitsstand, Sessions committen, mergen und pushen dort selbstständig und enden mit Merge nach `develop` + Push. `main` nur per PR von `develop` (Was, Warum, Wie geprüft, Offen), Merge nur durch Markus. Push auf `main` und jeder Force-Push technisch gesperrt (`.claude/settings.json`). Conventional Commits, Arbeitsbranches `bereich/kurzname` (nach Merge löschen), Worktrees je paralleler Session, Brief in `inbox/` nach jedem Merge, Varianten über `varianten.ts`. Ergänzung Tegards: Security-Check als fester Schritt vor jedem Commit. Folge P6: globale Regel „Commit/Push nur auf Anweisung“ braucht eine Ausnahme für den Marketing-Workspace. |
| 16.11.2026 | **Arbeitsregeln für Everlast-Aussagen (ganzer Umbau):** (1) Kein Satz über Everlast ohne eigenes Lesen in der laufenden Session mit Pfad:Zeile, Ungelesenes heißt „nicht gelesen“. (2) Unter jeder Empfehlung eine Zeile „Gelesen: …“. (3) Erst lesen, dann fragen: Vor jeder Grilling-Runde liest ein Subagent alle berührten Everlast-Dateien. (4) Codex-Review-Auftrag mit festem Punkt „jede Aussage über Everlast gegen die Datei prüfen“, ein falscher Beleg ist ein Fehler. (5) Everlast ist Referenz, nicht Grenze: neue Bausteine mit heutigem Fall, gekennzeichnet „neu, nicht Everlast“. (6) **Fixpunkt – ganzen Zusammenhang lesen:** Vor jeder Empfehlung zu einem Everlast-Baustein alle Vorkommen eines Begriffs, Felds oder Status workspace-weit lesen (Skills inkl. `assets/` und `references/`, Rules, Agenten, Commands, Steuerstand-Code), nicht nur die erste Fundstelle, und seine Rolle in der Gesamtarchitektur verstehen (wer schreibt, wer liest, welcher Ablauf). Erst dann empfehlen. Anlass: `entwurf`, stub/Freigabe, Prime-Leselisten und Cleanup-Kern zeigten ihre Bedeutung erst nach mehrfacher Nachfrage. |
| 16.11.2026 | P2 Ort und Struktur: ein Wissensort in den Everlast-Fächern (kein eigenes `wiki/`), oben fest, darunter offen mit `index.md` je offenem Ordner. Produktlinie = Everlast-Dateien + `fakten.md`; `quellen/` an der Wurzel (Original und Extrakt unveränderlich). 9 Linien, flache Ordner. Personas A/B/C. Wettbewerber mit Profil + Beobachtungen. Ein Schreibort, andere Workspaces lesen nur. |
| 16.11.2026 | P2 Faktenweg: Belegpflicht für technische und rechtlich heikle Werte (Seitenanker bzw. `original#anker`); Diff → Ja → Commit für `quellen/` und jeden belegpflichtigen Wert in jeder Datei, sonst `develop`-Fluss. Einziger Freigeber Markus. Python nur noch Extrakt-Skript, Prüfseite, Pre-Commit; Paket, Journal, Locks, Wächter usw. entfallen. `log.md`/`pruefungen.md` entfallen (Git-Log, „Offene Fragen“). `tg-konflikt-scan` unverändert + neu `tg-wissen-pruefen` (klein bei jeder Änderung; Vollprüfung nach 30 Tagen oder 10 Wissens-Commits, Brief + Steuerstand-Knopf, gegen Codex beibehalten). |
| 16.11.2026 | P2 Kontext und Lernen: Agenten lesen selbst; `fakten.md` in die produktbezogenen Prime-Listen, Persona B in `prime-content`, Learnings-Leseregel im Agenten-Abschnitt „Context“. Frontmatter je Datei wie ihre Everlast-Vorlage, kein Einheitsschema, Tegards-Zusatzfelder kommen nur dazu (OKF-Felder gestrichen). Freigabe und Fortschritt 1:1 wie Everlast: `stub` fällt erst nach Freigabe, offen = `stub`/fehlt, `entwurf` = noch nicht freigegeben. `kern.md`-Import entfällt. Agent-Memory nur für Handwerk. Learnings: anhängen, ab 40 Zeilen zu „Gilt heute“ verdichten. Synthesen im Fach. Kein Debrief. |
| 16.11.2026 | P2 Bausteine: `wissen/` eingefroren; Everlast-Abgleich bleibt der manuelle P1-Ablauf. Challenge wird übernommen (P9-Punkt „Challenge-Jury“ = ja). `workspace-cleanup` mit Kern unter `projekte/kern/`. `learn` → `tg-skill-aus-material` (faster-whisper CUDA, Bildabstand je Video abgefragt). Die 12 Quellen werden überführt (sha256), `marketing-wissen` geht an P3/P4. |
| 17.11.2026 | **P3 Grundsätze:** (1) Arbeitsteilung: Die Marke setzt Verkaufsargumente, Personas, Ton, Themenfelder, Verbote und Fakten; die Suche entscheidet über Seite, Seitenart, Pflichtthemen, Fragen und Wortlaut; Treffpunkt ist der Sektionsplan. Verkaufsargumente und Fakten kommen nie aus den Suchergebnissen. Rangfolge bei Konflikt: Fakten, Recht und Verbote, dann Marke, dann Suche. (2) **Grundsatz von Markus:** Was bei Everlast funktioniert, kommt mit und wird nur auf das Shopsystem angepasst, kein Umbau ohne Not. (3) **Agenten-Regel gelockert:** Ein weiterer Fachagent darf vorgeschlagen werden, wenn er Sinn ergibt (Maßstab: eigenes Handwerk, eigene Werkzeuge, scharfe Grenze); nichts Unnötiges. Für die Suchergebnis-Analyse kommt keiner. (4) Begriffe: „Säule“ = Themenfeld der Marke (`pillar`), „Landingpage“ = Seitenart, „Leitseite“ = Rolle der Hauptseite einer Linie, „Hauptbegriff und Unterfragen“ = Keyword-Cluster. |
| 17.11.2026 | P3 Suchwissen: Search Console, DataForSEO (`dfs`, Kostendeckel je Lauf) und Suggest; „Vergleichbarkeit, nicht Wahrheit“. Ein Keyword-Set `strategie/positionierung/keyword-set.md` mit Abschnitt je Linie (Suchbegriff, Absicht, genau eine Zielseite, Status, Volumen, Herkunft mit Datum). Themenplan je Linie vor dem Seitenbau, von Markus freigegeben; kein Entscheidungsbaum, keine Schwellen; Rollen `zielseite`/`shop-seite` und Familien-Regel bleiben. Ein Regelwerk für alle Linien; Bestandsaufnahme der Domain einmal je Markt (AT, DE); Reihenfolge Glasschiebewände, Verdeca, Lamellendächer. Neuer Skill `tg-serp-analyse` (Ebenen Linie und Seite, Ablage datiert unter `daten/`, vier Abnehmer, Seiten-Ebene 30 Tage wiederverwendbar, Linien-Ebene bei Auslöser, spätestens nach sechs Monaten). Säulen quer zu den Linien, höchstens fünf, Station 15. |
| 17.11.2026 | P3 Seitenaufbau: Seiten aus den Bausteinen des Designsystems, Auswahl und Folge beweglich (Kaufbremsen, drei Tests, Suchergebnisse); je Pflichtthema eine Abgleichzeile; Markus gibt den Sektionsplan vor dem Text frei; commerce-os-Templates entfallen. Leitseite: zwei freie Varianten, eine darf über das Designsystem hinausgehen. Übrige Seitenarten: je ein neu hergeleitetes Gerüst mit zwei festen Stellen (Arbeit P4), Hornbach als Vorbild für Ratgeber und Anleitung. `seitenvorlagen.md` ist Bestand, keine Vorlage; Glasschiebewände Deluxe und Verdeca werden neu gebaut (vorher Bewertung „muss bleiben“, Zahlen festhalten, Adresse und Hauptbegriff bleiben). Markup nur, wo Google es anzeigt oder das Plugin es liefert. |
| 17.11.2026 | P3 GEO, Frische, Bausteine: drei Schreibregeln ohne Zahlenvorgaben, kein `llms.txt`; Prüfung über den Codex-Prüfweg (P1), GEO-Punkte in der Inhaltsrubrik; Messung in drei Stufen; Such- und Trainingscrawler zugelassen (`kanaele/websites.md`); Off-Page bleibt Handarbeit. Ein Ort je Regel (`tg-seo`, Quelle und Abrufdatum), monatlicher Regel-Check gleich mit dem Workspace; Komplett-Audit einmal im Quartal; zwei Loops als Fixpunkte. Angepasst kommen mit: `tg-seo`, `tg-keyword-research`, `/seo-komplett-audit`, `tg-seo-audit`, `tg-seo-content`; ein Aufbau für Ratgeber und Anleitung (`tg-blog` und `tg-seo-content`). Aus dem alten SEO-Wissensordner wird nichts übertragen (ersetzt P2 F2 für den P3-Teil; Ausnahme Zeichenlängen als Hausregel). Produktdatenquelle der Bildprüfung: `fakten.md` der Linie. |
| 17.11.2026 | **Neuer Schritt nach P9, vor dem Planungsaudit (Markus, P3 X1):** Abgleich auf Datei- und Code-Ebene. Jeder Skill, Agent, Command, jede Datei, Funktion und Logik von Everlast wird geprüft, ob es bei Tegards ein Gegenstück oder einen vergleichbaren Ansatz gibt. P9 liefert dafür die Inventarliste; die Funde kommen vor dem Audit in die Entscheidungsdateien. Vorgehen siehe nächste Zeile. |
| 17.11.2026 | **Vorgehen beim Abgleich auf Datei- und Code-Ebene (Markus):** (1) **Landkarte per Skript, am Anfang von P9:** Inventar (jede Everlast-Datei mit Typ und Zugehörigkeit zu einem Baustein), Verweise je Datei mit Zeile (wer verweist herein, wohin verweist sie; dazu Waisen und tote Verweise), Lese-/Schreib-Matrix je Baustein (welche Workspace-Dateien er liest und schreibt), Begriffsverzeichnis (Frontmatter-Felder und Statuswerte mit allen Fundstellen). Für Code (Steuerstand, Werkzeuge) dasselbe: Funktionen, Aufrufe und die Pfade und Felder, die der Code erwartet. Ein Modell ergänzt nur, was das Skript nicht kann (Bedingung eines Verweises, nicht wörtliche Verweise). (2) **Abläufe statt aller Pfadkombinationen:** nachverfolgt wird ab den Einstiegspunkten (Commands, Agenten-Workflows, Loops, Onboarding-Stationen) und nur für Bausteine, die mitkommen. (3) **Bewertet wird je Baustein und Ablauf, nicht je Datei;** die Dateien hängen als Zeilen darunter. Der Zweck wird nur für Bausteine neu bewertet, die in keinem Dossier vorkommen. (4) **Status je Baustein gegen Tegards** (1:1 / teilweise mit Begründung / bewusst nicht / nur bei Tegards) bleibt der Schritt vor dem Planungsaudit; Markus entscheidet, Codex prüft eine Stichprobe der Landkarte gegen die Dateien. (5) **Probelauf:** zwei bis drei Everlast-Abläufe echt ausführen; das geht nur in Markus' WSL-Instanz (Ubuntu), vorher die Version dort mit der Kopie auf `E:` vergleichen. (6) **Neu: Abgleich nach dem Bau**, vor dem Aufräumen: dieselben Skripte laufen über den Tegards-Workspace (tote Verweise, Waisen), und die Statustabelle wird gegen die echten Dateien geprüft: 1:1 = Diff, erlaubt sind nur die Umbenennungen; teilweise = Abweichungen müssen in der Entscheidung stehen; bewusst nicht = Datei fehlt und nichts verweist darauf; nur bei Tegards = kommt in einer Entscheidung vor. Kein Inhaltsvergleich Datei gegen Datei über alles. Nicht geprüft: Aufwand und Anteil nicht wörtlicher Verweise (erst nach einem Probelauf des Skripts über einen Skill-Ordner bekannt). |

## Planungsthemen

| # | Thema | Punkte Markus | hängt ab von | Status |
|---|---|---|---|---|
| P0 | Rahmen: Repo, STAND.md, Kontext-Schutz | 9 | – | fertig bis auf Kontext-Schutz-Bau (wartet auf OK) |
| P1 | Landkarte-Fixes, Reviewer (juror.ts vs three-brain), Designsystem cloud/lokal, Medien (Higgsfield, OpenArt, Bibliothek) | 1, 10 | P0 | **fertig** 14.11.2026: `entscheidungen/01-reviewer-design-medien.md` (Codex-Review eingearbeitet); Landkarte aktualisiert |
| P2 | Wiki-Architektur Best-of (feste Fächer vs LLM-gepflegt, Rückfluss in den Kontext, Learnings vs Synthese) | 2 | P0 | **fertig** 16.11.2026: `entscheidungen/02-wiki-architektur.md` (Codex-Review eingearbeitet, Streitfälle von Markus entschieden); 11 Zeilen in SPAETER.md |
| P3 | Markengeführt × suchergebnisgeführt, SEO/GEO-Frische, Seitenschemas, Top-down/Bottom-up | 3 | P2 | **fertig** 17.11.2026: `entscheidungen/03-marke-serp-seo-geo.md` (Codex-Review eingearbeitet, Befund 2 und Lage des Schluss-Schritts von Markus entschieden); 9 Zeilen in SPAETER.md |
| P4 | Kanäle + Content-Fähigkeiten je Fähigkeit Everlast vs commerce-os | 4 | P3 | offen |
| P5 | Altbestand-Triage: was wird noch gebraucht | 5 | – | Dossier fertig (`dossiers/05-altbestand.md`), Grilling offen |
| P6 | agentic-os-Zukunft + Übertragung der Claude-Installation auf andere Rechner | 11 | – | Dossier fertig (`dossiers/06-agentic-os-und-rechneruebertragung.md`), Grilling offen |
| P7 | Gerüst: Head, Agenten, Rules, Hooks, Commands, AGENTS/CLAUDE.md, Windows-Port | 7 | P1, P2, P4, P6, P9 | offen |
| P8 | Onboarding + Befüllen Punkt für Punkt (simulierte Stationen). Grundsatz 14.11.: leeres Gerüst zuerst, dann drei Wege (1 Bestehende Quellen = Standard, 2 URL/Website, 3 Neue Marke); in Weg 1 ist Altbestand Quelle mit Pfad, wird je Station gelesen, neu entworfen und freigegeben, nicht importiert; Fertiges (z. B. Designsystem) wird übernommen | 6 | P7 | offen |
| P9 | **Beginnt mit der Landkarte per Skript (17.11.2026, siehe feste Entscheidungen): Inventar, Verweise, Lese-/Schreib-Matrix, Begriffsverzeichnis.** Everlast-Inventur und Durchspielen: Workflows, Pipelines (Spaltenlogik), Swipefile, Steuerstand, Skills, Rules, Commands, Prozesse; Inventarliste mit Status je Baustein (1:1 / anpassen / weglassen → SPAETER) + Durchspiel-Protokoll. Aus P1: Challenge-Jury (in P2 entschieden: ja, Details offen), Stück-Ordner vs. Kanalverträge/Steuerstand | Wunsch 13.11. | P0 | offen (überschneidet sich mit P8, Rohlesen über Subagenten) |

Danach, in dieser Reihenfolge:
1. **Abgleich auf Datei- und Code-Ebene (Markus, 17.11.2026, P3 X1)**: Wenn P1–P9 entschieden sind, wird jeder Skill, Agent,
   Command, jede Datei, Funktion und Logik von Everlast geprüft, ob es bei Tegards ein Gegenstück oder einen vergleichbaren
   Ansatz gibt. Grundlage ist die Inventarliste aus P9; der Abgleich geht eine Ebene tiefer und in die Gegenrichtung.
   Funde werden in die Entscheidungsdateien eingearbeitet. Die Landkarte dafür (Skripte) entsteht schon am Anfang von P9;
   hier folgt der Status je Baustein gegen Tegards. Vorgehen: feste Entscheidung vom 17.11.2026.
2. **Planungsaudit (Markus)**: Danach lässt Markus sein eigenes Planungsaudit über alle
   Entscheidungsdateien und STAND.md laufen. Befunde werden eingearbeitet, erst dann beginnen die Specs.
   Das Audit liefert Markus zu diesem Zeitpunkt.
3. Specs und Arbeitspakete (Planungsmodus für die Freigabe der Paketliste), Abhängigkeitsprüfung, Umsetzung in Sessions mit getrennten Dateibereichen,
zum Schluss Aufräumen der OS-Familie.
4. **Abgleich nach dem Bau (Markus, 17.11.2026)**, vor dem Aufräumen: dieselben Skripte über den Tegards-Workspace und
   Prüfung der Statustabelle gegen die echten Dateien (siehe feste Entscheidung vom 17.11.2026).

## Offene Fragen

- Statusline in der Desktop-App: läuft sie dort überhaupt? (P0, siehe unten)

## Kontext-Schutz (P0)

Befund (13.11.2026):
- `~/.claude/settings.json` ruft `python3 ~/.claude/statusline.py` auf. Das Skript zeigt den Füllstand nur an,
  Claude selbst sieht ihn nicht.
- Ob die Desktop-App (Code-Tab) die Statusline überhaupt ausführt, ist **nicht geprüft**. Von außen lässt es sich
  nicht beobachten, weil das Skript nichts schreibt.

Vorschlag (schlank, Bau erst nach OK, weil `~/.claude` betroffen ist):
1. `statusline.py` schreibt bei jedem Aufruf zusätzlich `{session_id, used_percentage, zeit}` nach
   `~/.claude/state/kontext.json`. Das ist zugleich der Test, ob die Desktop-App das Skript ausführt.
2. Ein `UserPromptSubmit`-Hook liest die Datei für die eigene Session. Ab 50 % fügt er einen Hinweis ein:
   „Kontext ≥ 50 %: Handoff-Block schreiben, STAND.md aktualisieren, neue Session vorschlagen.“
3. Wenn die Desktop-App die Statusline nicht ausführt, schätzt der Hook ersatzweise über die Größe des Transkripts.

Hauptschutz bleibt der Zuschnitt: eine Session pro Thema, Rohlesen in Subagenten, nur STAND.md und das Dossier
im Hauptkontext.

## Handoff-Vorlage

```
Session: P<n> <Thema>
Lies: docs/umbau/STAND.md, docs/umbau/dossiers/<nn>-<thema>.md
Ziel der Session: <ein Satz>
Ergebnis: docs/umbau/entscheidungen/<nn>-<thema>.md + STAND.md-Zeile aktualisieren
Offen aus Vorsession: <Liste>
```

## Querbefunde aus den Dossiers (13.11.2026)

- `~/.codex/config.toml` hat die Denkstufe `medium`, laut globaler CLAUDE.md sollte es `xhigh` sein. Klären in P6.
- Plugin agentic-os ist installiert auf 0.4.0; `d619148` (umfang, Ablauf-Wahl) ist gepusht, aber nicht installiert.
- commerce-os ist doppelt registriert (zwei Marketplaces, zweimal im Projekt-Scope). Klären in P6.
- Die Wiki-Python-Werkzeuge (Frage W-00 in P5) entscheiden über rund 30 Zeilen in SPAETER. Klären in P2.
  **Erledigt 16.11.:** P2 B1, 22 Zeilen erledigt, 6 auf SPAETER, 2 an P7.
- Windows: bun, higgsfield und ffmpeg fehlen; bildgen braucht `sips`. Einplanen in P7.
  Nach P1 (14.11.): Higgsfield und `bildgen` entfallen (SPAETER); offen bleiben Bun (Test in P7) und `ffmpeg`.
- P5-Subagent hat 20 Zeilen von `E:\tegards\sandbox\secret-scan-vorschlag.md` gelesen (Regelverstoß, laut Bericht nur
  Vorschlagstext ohne Werte). An Markus gemeldet.

## Handoff P1 (14.11.2026)

```
Session: P1 Reviewer, Designsystem, Medien (abgeschlossen)
Lies: docs/umbau/STAND.md, docs/umbau/entscheidungen/01-reviewer-design-medien.md
Ziel der Session: Reviewer-Weg, Designsystem-Ort und Medien-Ablauf entscheiden – erledigt, Codex-Review (gpt-6-astra, xhigh, 9 Befunde) eingearbeitet.
Ergebnis: entscheidungen/01-reviewer-design-medien.md, 13 Zeilen in SPAETER.md, STAND.md (feste Entscheidungen, P1, neues P9), Landkarte (3 Karten).
Offen aus Vorsession:
- P3/P4: Produktdatenquelle für die Produktwahrheits-Zeile der Bildrubrik.
- P4: Inhaltsrubrik je Content-Fähigkeit; Content-Skills ↔ design-tokens.md; Newsletter-Design; OpenArt-Video-Qualität; Weg von bundle.css auf die Website.
- P6: globale CLAUDE.md-Regel zu three-brain umstellen; stehende Wahl nur noch für Bau-Reviews; ~/.codex/config.toml; Bun in die Rechner-Übertragung.
- P7: Bun-Test (codex.cmd, Bun.serve); Bau-Rubrik; Juror --out und Effort je Rubrik; Generator-Vorschauen + _blob-Zuordnung; ANLEITUNG-Zeile; tg-openart; inbox/-Pfad; Web-Fassung/IPTC/ffmpeg; .gitignore; CLI-endFrame; Umbenennung amm- → tg-.
- P9: Challenge-Jury ja/nein; Stück-Ordner gegen Kanalverträge und Steuerstand-Karte.
```

## Handoff P2 (16.11.2026)

```
Session: P2 Wiki-Architektur (abgeschlossen)
Lies: docs/umbau/STAND.md, docs/umbau/entscheidungen/02-wiki-architektur.md
Ziel der Session: Wissensort, Faktenweg, Rückfluss in den Kontext und Lernen aus Arbeit entscheiden – erledigt, Codex-Review (gpt-6-astra, xhigh, 20 Befunde) eingearbeitet, Streitfälle 17–20 von Markus entschieden.
Ergebnis: entscheidungen/02-wiki-architektur.md, Zeilen in SPAETER.md, STAND.md (feste Entscheidungen inkl. Arbeitsregeln, P2, Querbefund W-00), Review-Dateien unter reviews/p2/ (auf der Löschliste).
Offen aus Vorsession:
- P3: SERP-Analysen; SEO/GEO-Dateien aus marketing-wissen.
- P4: Redaktionsstil und Content-Inventar aus marketing-wissen; welche Learnings-Dateien je Fach.
- P6: Agent-Memory nicht übertragen; ffmpeg, yt-dlp, uv, faster-whisper, CUDA in die Übertragungsliste.
- P7: Extrakt-Skript, Prüfseite, Pre-Commit (+ W-21, W-32); B2-Ausnahme in der Git-Rule; tg-wissen-pruefen mit Fristen-Referenz, Brief und Knopf „Wissen prüfen“; --tief im Konflikt-Scan korrigieren; Seitenanker vs. source; fakten.md/Persona B in die Prime-Listen, Learnings-Regel in „Context“; oberkategorie; Steuerstand für mehrere Linien + Handbuch (Everlast-Playbook erweitert); Destillat-Sätze an sechs Stellen, struktur.md:77; Cleanup-Port mit projekte/kern/; tg-skill-aus-material.
- P8: 12 Quellen überführen, Terrawin neu; 9 Linien, Personas A/B/C; fakten.md je Linie neu; kern.md → stammdaten/unternehmen.md.
- P9: Challenge-Details; Backlog/Pipeline für Absichten; learn-Inventurzeile; manuellen Everlast-Abgleich mit der Inventur verbinden.
```

## Handoff P3 (17.11.2026)

```
Session: P3 Marke, Suche, SEO und GEO (abgeschlossen)
Lies: docs/umbau/STAND.md, docs/umbau/entscheidungen/03-marke-serp-seo-geo.md
Ziel der Session: Verhältnis von Marke und Suche, Suchwissen, Seitenaufbau, GEO, Frische und SEO-Bausteine entscheiden – erledigt, Codex-Review (gpt-6-astra, xhigh, 10 Befunde) eingearbeitet, Befund 2 und die Lage des Schluss-Schritts von Markus entschieden.
Ergebnis: entscheidungen/03-marke-serp-seo-geo.md, Zeilen in SPAETER.md, STAND.md (feste Entscheidungen inkl. gelockerter Agenten-Regel und Everlast-Grundsatz, P3, neuer Schritt „Abgleich auf Datei- und Code-Ebene“), Review-Dateien unter reviews/p3/ (auf der Löschliste).
Offen aus Vorsession:
- P4: Gerüst je Seitenart (Kategorie, Produkt, Ratgeber, Anleitung, Projekt) mit zwei festen Stellen, ein Gerüst für Ratgeber und Anleitung; Hornbach-Abgleich (liegt vor) einarbeiten; Varianten-Lauf der Leitseite und Weg eines neuen Bausteins ins Designsystem; Bilder (Bildliste, zwei Stufen, Alt-Text, „Belegte Motive“); Rückmeldung vom Markt (Analytics, Google Ads, Facebook) bei Everlast nachlesen; ob amm-video-zu-blog und amm-pillar-to-blog kommen, Transkript-Modus; Live-Daten aus dem Shop; amm-new-product auf Linien anpassen (drei Zusätze); Wortzahl-Regel oberhalb der Produktliste prüfen; GEO-Punkte in die Inhaltsrubriken.
- P7: dfs und gsc unter Windows, Österreich ergänzen; Höhe des Kostendeckels; Erinnerung ans Quartals-Audit; Träger für drei Loops; Rendering-Messpunkt über Firecrawl; ein Berichtsort für Audits, ein Pfad fürs Keyword-Set; Wortzahl des Antwortblocks aus Skills und pruefe_artikel.py nehmen; tg-seo auf Shop umschreiben mit Meta-Block-Schritt; Steuerstand zeigt Keyword-Set und Themenplan je Linie.
- P8: Station 15 (Säulen); kanaele/websites.md mit Bestand und Crawler-Eintrag; DataForSEO-Konto durch Markus; Bestandsaufnahme der Domain je Markt; Bewertung „muss bleiben“ vor dem Neubau einer bestehenden Seite.
- P9: Inventarzeile je SEO-Baustein; Swipefile-Fach landingpages/; ob der Head das Anlegen einer Linie auslöst; wann der Wochen-Loop eingeplant wird; Inventur als Grundlage des Abgleichs auf Datei- und Code-Ebene.
```
