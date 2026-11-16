# Handoff P3: vom Grilling zur Entscheidungsdatei

Stand: 17.11.2026. Geschrieben von der P3-Session nach abgeschlossenem Grilling. Markus hat die Zusammenfassung des
gemeinsamen Verständnisses am 17.11.2026 bestätigt („Ja, Handoff schreiben“).

```
Session: P3 Marke, Suche, SEO und GEO (Schritte 5 bis 7)
Lies: docs/umbau/STAND.md, docs/umbau/dossiers/03-lesen/grilling-protokoll.md,
      docs/umbau/dossiers/03-marke-serp-seo-geo.md (Teil 4.2 und Abschnitt 8 ganz; Teile 1 bis 3 und 5 nur zum Nachschlagen),
      docs/umbau/entscheidungen/02-wiki-architektur.md (als Formatvorbild)
Ziel der Session: Die im Grilling getroffenen Entscheidungen in die Entscheidungsdatei schreiben, von Codex prüfen lassen,
      Befunde mit Markus einarbeiten, STAND.md und SPAETER.md nachziehen.
Ergebnis: docs/umbau/entscheidungen/03-marke-serp-seo-geo.md + STAND.md (Zeile P3, feste Entscheidungen, Handoff-Block P3)
      + Zeilen in SPAETER.md
Offen aus Vorsession: siehe unten
```

## 1. Was die Folgesession tut

1. **Entscheidungsdatei** `docs/umbau/entscheidungen/03-marke-serp-seo-geo.md`: Ergebnis, Begründung, Verworfenes,
   Weggelassenes (nach `SPAETER.md` mit Auslöser), Offenes für P4, P7, P8, P9. Aufbau wie die Dateien zu P1 und P2.
2. **Codex-Review** über den Skill `agentic-os:three-brain`, stehende Wahl `--model gpt-6-astra --effort xhigh`. Fester
   Prüfpunkt im Auftrag: „jede Aussage über Everlast gegen die Datei prüfen; falscher Beleg = Fehler“. Befunde mit Markus
   einarbeiten. Vor dem Review-Auftrag und vor jedem Eintrag in `SPAETER.md` die Referenz
   `references/review-klassifikation.md` des Skills `agentic-os:umfang` laden.
3. **`STAND.md`**: Zeile P3 auf fertig, feste Entscheidungen ergänzen, Handoff-Block P3 nach der Vorlage.
4. **`SPAETER.md`**: Zeilen laut Abschnitt 4 unten.

## 2. Welche Fassung gilt

- Die Teile 5 bis 7 des Dossiers zeigen die ursprünglichen Empfehlungen. **Es gilt Abschnitt 8**, entstanden in elf
  Abzweigungen. Bei Widerspruch innerhalb von Abschnitt 8 gilt die späteste Fassung.
- Die Entscheidungsdatei führt nur die geltende Fassung, keine Entstehungsgeschichte.
- Das Grilling-Protokoll nennt je Frage die Antwort und die Herkunft. Q12 steht nur dort, nicht im Dossier.

Ersetzt oder geändert:

| Stelle | Ersetzt durch |
|---|---|
| D3 und Q4 (Entscheidungsbaum mit Schwellen) | 8.16 Punkt 101 bis 103: kein Baum, der Themenplan entscheidet; zwei kurze Regeln bleiben |
| 8.3 Punkt 9 („wenn die Linie den Entscheidungsbaum nicht erfüllt“) | lesen als „wenn die Suchergebnisse keine eigene Landingpage verlangen“ (8.16 Punkt 101) |
| D5 (eine Ebene, alte Analyse als Formatvorlage) | 8.1 Punkt 3, 8.2, 8.10 Punkt 40 und 41, 8.13 Punkt 69, Q9 im Protokoll |
| D6 (Grundgerüst mit fester Folge) | 8.4, dann 8.11, dann 8.12 |
| 8.4 Punkt 13 (zwei kreative Alternativvarianten) | 8.11 Punkt 48, dieser wieder durch 8.12 Punkt 55 und 56 |
| 8.11 Punkt 43 (Startfolge aus `seitenvorlagen.md`) | 8.12 Punkt 52 und 57 |
| 8.11 Punkt 49 (kein Layout am Designsystem vorbei) | gilt weiter, außer für eine der zwei Leitseiten-Varianten (8.12 Punkt 56) |
| D8 (zehn alte Prompts als Vorrat) | 8.13 Punkt 68, 8.14 |
| D10, Zeilen `amm-seo-audit` und `amm-seo-content` (weglassen) | 8.15 Punkt 87 bis 92: beide kommen angepasst mit |
| D10, Zeile `tg-keyword-research` („dazu der Entscheidungsbaum“) | 8.16 Punkt 101 bis 103 |
| D10, wöchentlicher Loop „SPAETER“ | 8.6: Fixpunkt |
| D13 (Zuordnung je alter Datei) | 8.13: fast nichts wird übertragen |
| 8.10 Punkt 42 und 8.13 Punkt 77 (`dfs` ohne Backlink-Befehl) | berichtigt: `dfs backlinks` gibt es (`EL:tools/dataforseo/dfs:12`, `:462`) |
| 8.12 Punkt 54 („Seitenart Leitseite“) | 8.13 Punkt 78: Seitenart ist „Landingpage“, „Leitseite“ ist die Rolle |
| Feste Entscheidung „Fachagenten 1:1 nach Everlast“ (`STAND.md` Zeile 20) | 8.10 Punkt 39: weitere Fachagenten dürfen vorgeschlagen werden |

## 3. In `STAND.md` nachzuziehen

- Zeile P3 und der Handoff-Block P3.
- Feste Entscheidung zur Agenten-Regel (8.10 Punkt 39).
- Neuer Schritt am Schluss des Plans: Abgleich auf Datei- und Code-Ebene, jeder Skill, Agent, Command, jede Datei,
  Funktion und Logik von Everlast gegen Tegards (8.15 Punkt 96). Verhältnis zu P9 und zum Planungsaudit klären.
- Grundsatz von Markus: Was bei Everlast funktioniert, kommt mit und wird nur auf das Shopsystem angepasst (8.15
  Punkt 86).

## 4. `SPAETER.md`

Schon eingetragen (vier Zeilen vom 16.11.2026): wöchentlicher Loop als Fixpunkt, monatlicher Loop Content-Verfall als
Fixpunkt, RankMath-MCP, „ein Modus statt zwei Varianten“.

Zu ändern: die Zeile „ein Modus statt zwei Varianten“ nennt noch die Namen „Startfolge angepasst“ und „frei nach
Everlast“. Neuer Auslöser (8.16 Punkt 100): Markus wählt bei den Leitseiten immer wieder den Entwurf innerhalb oder
immer wieder den außerhalb des Designsystems.

Neu einzutragen, je mit Auslöser:

| Thema | Auslöser | Quelle |
|---|---|---|
| Markup `FAQPage`, `HowTo`, `speakable`, `Product` ohne Preis | belegte Wirkung | Q5 |
| GEO-Tracker (Peec AI, Profound, Otterly oder ähnlich) | die Messung zeigt, dass KI-Antworten für unsere Begriffe eine Rolle spielen | 8.8 Punkt 31 |
| Backlink-Analyse der Wettbewerber mit `dfs backlinks` (Werkzeug vorhanden) | die Linien-Analyse erklärt einen Aufsteiger nicht aus Inhalt und internen Links | 8.10 Punkt 42, 8.13 Punkt 77 |
| Eigener Fachagent für die Suchergebnis-Analyse | die Analyse sprengt nachweislich den Kontext des Planers | 8.10 Punkt 39 |
| Operative Off-Page-Arbeit durch einen Agenten | prüfen, ob Markus das überhaupt will; heute Handarbeit | 8.13 Punkt 76, 8.14 Punkt 83 |

## 5. Offenes für die anderen Planungsthemen

**P4 (Kanäle und Content-Fähigkeiten)**
- Gerüst je Seitenart für Kategorie, Produkt, Ratgeber, Anleitung, Projekt herleiten, je mit zwei festen Stellen (8.12
  Punkt 57 bis 60). Ein gemeinsames Gerüst für Ratgeber und Anleitung, nach dem `tg-blog` und `tg-seo-content` schreiben
  (8.15 Punkt 92).
- Hornbach-Abgleich nachholen: `hornbach-blogaufbau.md` ist leer, weil der Artikeltext nicht abrufbar war. Im Browser
  lesen und die Prüfliste dort ausfüllen.
- Varianten-Lauf der Leitseite ausgestalten; Weg eines neuen Bausteins ins Designsystem (8.11 Punkt 49, 8.12 Punkt 56).
- Bilder: Bildliste aus dem Sektionsplan, zwei Stufen, Alt-Text und Bildunterschrift als Schluss-Schritt, Register
  „Belegte Motive“ (8.5).
- Rückmeldung vom Markt über Google Analytics, Google Ads und Facebook-Werbung bei Everlast nachlesen (8.7 Punkt 24).
- Ob `amm-video-zu-blog` und `amm-pillar-to-blog` kommen; Abgrenzung des Transkript-Modus im Blog-Skill (8.15 Punkt 95).
- Live-Daten aus dem Shop (Sortiment, Attribute) als Quelle neben `fakten.md` (Q8).
- Anpassung von `amm-new-product` auf Linien mit drei Zusätzen (Protokoll, Abschnitt „Für die Folgesession“).
- Markus’ Angabe einer SEO-Regel zur Höchstzahl der Wörter oberhalb der Produktliste prüfen (8.11 Punkt 50).

**P7 (Gerüst, Windows-Port)**
- Laufen `dfs` und `gsc` unter Windows? Österreich ausdrücklich ergänzen: `dfs` hat Standard `--land DE`,
  `seo-voraussetzungen.py:134` schreibt „DE, de“ fest.
- Höhe des Kostendeckels je DataForSEO-Lauf; Erinnerung an das Komplett-Audit im Quartal (8.16 Punkt 97 und 98).
- Träger für die drei Loops unter Windows (Everlast nutzt launchd). Der monatliche Regel-Check kommt gleich mit dem
  Workspace, die beiden anderen sind Fixpunkte.
- Rendering-Messpunkt von `tg-seo-audit` über Markus’ Firecrawl (8.15 Punkt 88).
- `amm-video-zu-blog/scripts/pruefe_artikel.py:31` prüft die Wortzahl des Antwortblocks hart; die Vorgabe ist entfallen.
- Steuerstand für mehrere Linien: nimmt den ersten Ordner unter `produkte/` als das eine Produkt
  (`EL:steuerstand/build.ts:3017-3018`) und liest das Keyword-Set nicht. Mit P2 und P9 abgleichen.

**P8 (Onboarding)**
- Station 15: welche Säulen es werden (8.9 Punkt 36). Die Beispiele aus der Abzweigung sind nicht entschieden.
- `kanaele/websites.md`: Bestand der Website, Eintrag „Such- und Trainingscrawler zugelassen“ (8.14 Punkt 85).
- DataForSEO-Konto legt Markus selbst an und trägt die Zugangsdaten selbst ein (8.8 Punkt 32).
- Vor dem Neubau einer bestehenden Seite: Bewertung mit Liste „muss bleiben“, heutige Zahlen festhalten, Adresse und
  Hauptbegriff bleiben (8.12 Punkt 61 bis 63).

**P9 (Inventur)**
- Endgültige Inventarzeile je SEO-Baustein (8.15 Punkt 88, 90, 93).
- Was mit Everlasts Swipefile-Fach `landingpages/` geschieht (8.13 Punkt 75).
- Ob der Head das Anlegen einer neuen Linie auslöst (`amm-new-product` kommt in `head-of-marketing.md` nicht vor).
- In der Abzweigung zu Q9 offen geblieben: wann der Wochen-Loop eingeplant wird.

## 6. Nicht geprüft

- Die Tegards-Belege mit **(B)** im Dossier sind nur gegen den Lesebericht `03-lesen/tegards.md` geprüft, nicht gegen die
  Originaldateien. Die Haiku-Belegprüfung (`belegpruefung.md`) deckt nur die Teile 1 bis 7 ab, nicht Abschnitt 8.
- Von den Everlast-Belegen in Abschnitt 8 hat die P3-Session nachgelesen: 8.8 (README des DataForSEO-Werkzeugs,
  `seo-voraussetzungen.py`), 8.9 (alle sechs Stellen in `saeulen.md`), `dfs backlinks`, die Skills des Wochen-Loops
  (`tools/seo-audit/auftrag.md:1`, `:14-15`). Alle übrigen Belege in 8.10 bis 8.16 stammen aus den Abzweigungen.
- Elf Entscheidungen kamen über Nachrichten der Abzweigungen in die P3-Session. Markus hat die Zusammenfassung danach
  in der P3-Session bestätigt.
- Ob der Links-Bericht der Search Console nur in der Oberfläche verfügbar ist (8.13 Punkt 76).
- Andere Anbieter als DataForSEO wurden nicht recherchiert (8.8 Punkt 31). Die 0,59 USD je Audit sind ein Messwert von
  Everlast.
- Dass der Unterbau einer Domain das Ranking trägt (8.10 Punkt 40) und dass ein freier Neubau besser verkauft (8.12), ist
  fachliche Einschätzung, nicht belegt.

## 7. Regeln, die weiter gelten

- Nicht committen ohne Markus’ Anweisung. Nur `docs/umbau/` und `SPAETER.md` ändern. Tabu: `.env*`, `*secret*`, `*.pem`,
  `*.key`.
- Kein Satz über Everlast ohne eigenes Lesen mit Pfad und Zeile; „Gelesen:“-Zeile unter jeder Empfehlung.
- Reviews macht Codex, nicht die eigene Session.
- Der Stand nach dem Grilling ist committet (`d310cea` auf `main`, 17.11.2026, nicht gepusht): `SPAETER.md`, das Dossier
  und der Ordner `docs/umbau/dossiers/03-lesen/`. Das Ergebnis der Folgesession wird getrennt committet, nach Markus’ Ja;
  den Commit an jedem Sicherungspunkt aktiv vorschlagen.
