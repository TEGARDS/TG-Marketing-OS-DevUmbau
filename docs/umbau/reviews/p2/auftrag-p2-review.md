CLI: codex exec
Rolle: Reviewer (Konzept-Review einer Entscheidungsdatei)
Modell: gpt-6-astra
Denkstufe/Tier: xhigh
Quelle der Wahl: stehende Wahl Markus (globale CLAUDE.md)

Umfang: gruendlich, aber strikt gegen Overengineering. Geprüft wird eine Planungs-Entscheidungsdatei, kein Code.
Ich entscheide: Wiki-Architektur eines neuen Marketing-Workspace (Everlast-Gerüst, Tegards-Faktensicherung, Windows nativ):
Wissensort und Ordnerregel, Produktlinien und Personas, Faktenweg mit Quellen/Belegen/Prüfstellen, Freigabe, Prüfungen,
Rückfluss in den Kontext, Learnings/Synthesen/Agent-Memory, übernommene Everlast-Bausteine, Überführung des Altbestands.
Bewusst weggelassen: alles in SPAETER.md (Grund: kein heutiger Fall), Bau-Details (P7, Specs folgen später), Inhalte von
SEO/GEO und Redaktion (P3/P4), Ausführung des Onboardings (P8).
Bedrohungsmodell: Einzelnutzer-Workspace auf eigenem Rechner, ein Freigeber, ein Git-Repo; Risiken sind falsche technische
Produktwerte (Haftung: Maße, Statik, Zertifikate), still widersprüchliches Wissen, Verlust geprüfter Arbeit beim Umzug,
Kontextkosten je Agentenlauf, unbemerkte Änderungen an Fakten ohne Freigabe.

## Auftrag

Prüfe die Entscheidungsdatei `docs/umbau/entscheidungen/02-wiki-architektur.md` (Arbeitsverzeichnis = Repo).
Kontext lesen: `docs/umbau/STAND.md` (v. a. „Feste Entscheidungen“), `docs/umbau/dossiers/02-wiki-architektur.md`,
`docs/umbau/dossiers/05-altbestand.md` (Zeilen W-00, I-07, I-08, M-04 bis M-09), `docs/umbau/entscheidungen/01-reviewer-design-medien.md`, `SPAETER.md`.
Faktenquellen bei Bedarf (nur lesen): `E:\Everlast Learning\marketing-workspace-0.5.0\` (z. B. `.claude/head-of-marketing.md`,
`.claude/agents/`, `.claude/commands/prime*.md`, `.claude/rules/`, `.claude/skills/amm-konflikt-scan/`, `.claude/skills/learn/`,
`.claude/skills/workspace-cleanup/`, `.claude/skills/amm-new-product/`, `.claude/skills/amm-workspace-setup/`, `steuerstand/`, `AGENTS.md`),
`E:\tegards\knowledge\` (`_SCHEMA.md`, `quellen/**/karte.md`, `log.md`, `pruefungen.md`).
Lies keine `.env*`, `*secret*`, `*.pem`, `*.key` und keine Zugangsdaten.

Prüfe gegen den Umfang oben, nicht gegen eine ideale Komplettlösung:
1. **Jede Aussage über Everlast (und Tegards) gegen die genannte Datei prüfen** (Pfad:Zeile, Wortlaut, was der Code wirklich tut).
   Ein falscher oder nicht tragender Beleg ist ein Befund der Klasse **Fehler**.
2. Widersprüche innerhalb der Datei und zu STAND.md/P1-Entscheidungen (z. B. Git-Regel von P1 gegen B2, Onboarding Weg 1 „kein Import“
   gegen F1, Namensregel `tg-`, Ordner- und Feldnamen, `index.md` vs. `README.md`).
3. Lücken, durch die der erklärte Zweck bricht (z. B. eine Regel ohne Prüfstelle, ein Ablauf, der so nicht ausführbar ist,
   ein Feld, das ein übernommener Everlast-Baustein erwartet, aber wegfällt).
4. Overengineering: Teile ohne heutigen Fall, die auf SPAETER.md gehören (insb. B6, C3 Graph, E1 Everlast-Abgleich, E3 Keyframes).
5. Falsch zugeordnete offene Punkte (P3/P4/P6/P7/P8/P9) und SPAETER-Zeilen ohne Auslöser.

## Ausgabeformat

Nummerierte Befundliste, Deutsch. Je Befund:
- Klasse: **Fehler** (erklärter Zweck bricht, falscher Beleg, oder Problem im Bedrohungsmodell) / **Ergänzung** (nett, für den
  Zweck nicht nötig) / **Begründung trägt nicht** (ein Grund für eine Entscheidung oder ein Weglassen ist falsch; gegen Quellen geprüft)
- Stelle: Abschnitt-ID (z. B. B1, C3) und wörtliches Kurzzitat
- Befund in 1–3 Sätzen, mit Beleg (Datei:Zeile), wenn du eine Quelle geprüft hast
- Vorschlag in einem Satz
Am Ende: `GESAMT: <n> Fehler, <n> Ergänzung, <n> Begründung trägt nicht`. Kein Lob, keine Zusammenfassung der Datei.
