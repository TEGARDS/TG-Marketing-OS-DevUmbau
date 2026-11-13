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
| 13.11.2026 | Head of Marketing + Fachagenten 1:1 nach Everlast. |
| 13.11.2026 | Branch `skill-format` in agentic-os pausiert bis P6. |
| 13.11.2026 | Planung je Thema: Dossier → Grilling → Entscheidungsdatei → Codex-Review → Handoff. |
| 13.11.2026 | Querschnitt: kein Overengineering; Zukunftsfälle auf `SPAETER.md`. |
| 14.11.2026 | P1 Reviewer: ein Codex-Prüfweg (`juror.ts`, kalter Read, `--out`), Rubriken Bau (Umfangsblock, `gpt-6-astra` xhigh) und Inhalt (je Auftragsart, `gpt-6-astra` medium, Startphase doppelt). Rückfall: Claude-Modell ≠ Erzeuger für Inhalte; Bau bleibt offen. three-brain und agy nicht im Workspace. Codex-Plugin bleibt, Stop-Gate aus. Bun, wenn der P7-Test besteht, sonst Node. |
| 14.11.2026 | P1 Designsystem: `E:\TG Design\designsystem\` bleibt Bau-/Publish-Ort, Workspace bekommt Destillat (`design-tokens.md`, `bildsprache.md`), Nachzug als fester letzter Publish-Schritt. Vorschauen werden lokal eigenständig (P7). `ui-styling`/`design-system` nicht übernehmen. |
| 14.11.2026 | P1 Medien: nur OpenArt-CLI (`tg-openart`), kein MCP; 400 Credits/Auftrag, Video immer mit Freigabe. TGMB per Brief in `medien.md`, Bestand zuerst (Workspace → TGMB → generieren). Stück mit Medien = Ordner (`quelle/`, `generiert/`, `web/`), keine Binärdateien in Git. Produktwahrheit und „echtes Foto“ als harte Regeln mit Prüfstelle. Datenfreigabe: TGMB-Medien und Workspace-Texte dürfen an OpenArt/Codex. |
| 14.11.2026 | Saubere Abspaltung von Everlast: kein `everlastpull`, Everlast nur Ideenquelle, Vergleich neuer Versionen manuell. Namensregel `amm-<name>` → `tg-<name>`. |

## Planungsthemen

| # | Thema | Punkte Markus | hängt ab von | Status |
|---|---|---|---|---|
| P0 | Rahmen: Repo, STAND.md, Kontext-Schutz | 9 | – | fertig bis auf Kontext-Schutz-Bau (wartet auf OK) |
| P1 | Landkarte-Fixes, Reviewer (juror.ts vs three-brain), Designsystem cloud/lokal, Medien (Higgsfield, OpenArt, Bibliothek) | 1, 10 | P0 | **fertig** 14.11.2026: `entscheidungen/01-reviewer-design-medien.md` (Codex-Review eingearbeitet); Landkarte aktualisiert |
| P2 | Wiki-Architektur Best-of (feste Fächer vs LLM-gepflegt, Rückfluss in den Kontext, Learnings vs Synthese) | 2 | P0 | Dossier fertig (`dossiers/02-wiki-architektur.md`), Grilling offen |
| P3 | Markengeführt × suchergebnisgeführt, SEO/GEO-Frische, Seitenschemas, Top-down/Bottom-up | 3 | P2 | offen |
| P4 | Kanäle + Content-Fähigkeiten je Fähigkeit Everlast vs commerce-os | 4 | P3 | offen |
| P5 | Altbestand-Triage: was wird noch gebraucht | 5 | – | Dossier fertig (`dossiers/05-altbestand.md`), Grilling offen |
| P6 | agentic-os-Zukunft + Übertragung der Claude-Installation auf andere Rechner | 11 | – | Dossier fertig (`dossiers/06-agentic-os-und-rechneruebertragung.md`), Grilling offen |
| P7 | Gerüst: Head, Agenten, Rules, Hooks, Commands, AGENTS/CLAUDE.md, Windows-Port | 7 | P1, P2, P4, P6, P9 | offen |
| P8 | Onboarding + Befüllen Punkt für Punkt (simulierte Stationen) | 6 | P7 | offen |
| P9 | Everlast-Inventur und Durchspielen: Workflows, Pipelines (Spaltenlogik), Swipefile, Steuerstand, Skills, Rules, Commands, Prozesse; Inventarliste mit Status je Baustein (1:1 / anpassen / weglassen → SPAETER) + Durchspiel-Protokoll. Aus P1: Challenge-Jury ja/nein, Stück-Ordner vs. Kanalverträge/Steuerstand | Wunsch 13.11. | P0 | offen (überschneidet sich mit P8, Rohlesen über Subagenten) |

Danach, in dieser Reihenfolge:
1. **Planungsaudit (Markus)**: Wenn P1–P9 entschieden sind, lässt Markus sein eigenes Planungsaudit über alle
   Entscheidungsdateien und STAND.md laufen. Befunde werden eingearbeitet, erst dann beginnen die Specs.
   Das Audit liefert Markus zu diesem Zeitpunkt.
2. Specs und Arbeitspakete (Planungsmodus für die Freigabe der Paketliste), Abhängigkeitsprüfung, Umsetzung in Sessions mit getrennten Dateibereichen,
zum Schluss Aufräumen der OS-Familie.

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
