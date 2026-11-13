CLI: codex exec
Rolle: Reviewer (Konzept-Review einer Entscheidungsdatei)
Modell: gpt-6-astra
Denkstufe/Tier: xhigh
Quelle der Wahl: stehende Wahl Markus (globale CLAUDE.md)

Umfang: gruendlich, aber strikt gegen Overengineering. Geprüft wird eine Planungs-Entscheidungsdatei, kein Code.
Ich entscheide: Reviewer-Weg, Designsystem-Ort, Mediengenerierung und Medienbibliothek für einen neuen Marketing-Workspace
(Vorbild Everlast, Windows nativ). Bewusst weggelassen: alles in SPAETER.md (Grund: kein heutiger Fall), Bau-Details
(gehören in P7, Specs folgen später), Umsetzung der globalen CLAUDE.md (P6).
Bedrohungsmodell: Einzelnutzer-Workspace auf eigenem Rechner; Risiken sind Kosten (Credits), Datenabfluss an externe
Modelle/Dienste, falsche Produktdarstellung in generierten Bildern, Selbst-Review ohne zweites Modell.

## Auftrag

Prüfe die Entscheidungsdatei `docs/umbau/entscheidungen/01-reviewer-design-medien.md` (Arbeitsverzeichnis = Repo).
Kontext lesen: `docs/umbau/STAND.md`, `docs/umbau/dossiers/01-reviewer-design-medien.md`, `SPAETER.md`.
Faktenquelle bei Bedarf (nur lesen): `E:\Everlast Learning\marketing-workspace-0.5.0\` (z. B. `tools/juror.ts`,
`.claude/rules/referenz-diff.md`, `.claude/agents/references/grafik-designer-workflows.md`, `.claude/head-of-marketing.md`).
Lies keine `.env*`, `*secret*`, `*.pem`, `*.key` und keine Zugangsdaten.

Prüfe gegen den Umfang oben, nicht gegen eine ideale Komplettlösung:
1. Widersprüche innerhalb der Datei und zu Dossier/STAND.md (z. B. Pfade, Namen, Modell/Denkstufe, Rückfall-Regeln).
2. Entscheidungen, deren Begründung nicht trägt (gegen Everlast-Dateien und Dossier geprüft).
3. Lücken, durch die der erklärte Zweck bricht (z. B. ein Ablauf, der so nicht ausführbar ist; eine Regel ohne Prüfstelle).
4. Overengineering: Teile, die keinen heutigen Fall haben und auf SPAETER.md gehören.
5. Falsch zugeordnete offene Punkte (P4/P6/P7/P9).

## Ausgabeformat

Nummerierte Befundliste, Deutsch. Je Befund:
- Klasse: **Fehler** (erklärter Zweck bricht, oder Sicherheits-/Kostenproblem im Bedrohungsmodell) / **Ergänzung** (nett, für den
  Zweck nicht nötig) / **Begründung trägt nicht** (ein Grund für eine Entscheidung oder ein Weglassen ist falsch; gegen Quellen geprüft)
- Stelle: Abschnitt-ID (z. B. A3, C5) und wörtliches Kurzzitat
- Befund in 1–3 Sätzen, mit Beleg (Datei:Zeile), wenn du eine Quelle geprüft hast
- Vorschlag in einem Satz
Am Ende: `GESAMT: <n> Fehler, <n> Ergänzung, <n> Begründung trägt nicht`. Kein Lob, keine Zusammenfassung der Datei.
