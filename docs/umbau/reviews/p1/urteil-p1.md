1. Klasse: **Fehler** · Stelle: **A4**, „Inhalte prüft Sonnet“.

   Grafik-Designer und Video-Cutter arbeiten bei Everlast bereits mit Sonnet; der pauschale Rückfall ermöglicht damit genau den ausgeschlossenen Selbst-Review. Everlast verlangt ausdrücklich ein anderes Prüfermodell. Beleg: [head-of-marketing.md:129](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/head-of-marketing.md:129>) und [head-of-marketing.md:134](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/head-of-marketing.md:134>).

   Vorschlag: Sonnet nur zulassen, wenn das Erzeugermodell verschieden ist; andernfalls bleibt auch die Inhaltsprüfung offen.

2. Klasse: **Fehler** · Stelle: **A1**, „Inhalt (Everlast-Skeptiker-Pass und eingebaute 6-Punkte-Bildrubrik)“.

   Der Skeptiker-Pass verlangt einen weichen CTA und mindestens ein „Earned Secret“; er ist ausdrücklich für große Stücke des Content-Marketers bestimmt. Als allgemeine Textprüfung würde er passende Verkaufsanzeigen oder Landingpage-CTAs beanstanden, obwohl Everlast diese bewusst dem Copywriter mit Conversion-Ziel zuordnet. Beleg: [content-marketer-pruefung.md:10](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/agents/references/content-marketer-pruefung.md:10>), [content-marketer-pruefung.md:18](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/agents/references/content-marketer-pruefung.md:18>) und [copywriter.md:104](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/agents/copywriter.md:104>).

   Vorschlag: Den einzigen Prüfweg beibehalten, aber die Inhaltsrubrik nach Auftragsart wählen und ihre Zuordnung zu den Content-Fähigkeiten ausdrücklich P4 geben.

3. Klasse: **Fehler** · Stelle: **A1/A3**, „Der Workspace prüft über einen Weg“ und „Beides steht fest im Juror-Aufruf“.

   Das Dossier nennt bereits die zusätzliche Challenge-Jury; Everlast verlangt bei jedem neuen Creative eine Challenge mit drei Juroren auf verschiedenen Modellen, davon nur einem über `juror.ts`. Offen bleibt, ob dieser heutige Standardablauf übernommen oder durch den einzigen fest besetzten Juror ersetzt wird; beide Vorgaben gleichzeitig ergeben keine eindeutige Reviewer-Regel. Beleg: [Dossier:25](</E:/TG Marketing OS DevUmbau/docs/umbau/dossiers/01-reviewer-design-medien.md:25>), [challenge-vor-handwerk.md:10](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/rules/challenge-vor-handwerk.md:10>) und [amm-challenge/SKILL.md:55](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/amm-challenge/SKILL.md:55>).

   Vorschlag: In P1 den Vorrang des beschlossenen Prüfwegs gegenüber der Challenge-Jury festlegen und P9 deren betroffene Verweise erfassen lassen.

4. Klasse: **Begründung trägt nicht** · Stelle: **A3**, „das Urteil liegt ohnehin als Datei vor“.

   Das von Codex mit `-o` geschriebene Urteil liegt zunächst im temporären Verzeichnis, das `juror.ts` anschließend löscht. Dauerhaft gespeichert wird es nur beim zusätzlichen Juror-Parameter `--out`; diese Voraussetzung fehlt in der Entscheidung. Beleg: [juror.ts:100](</E:/Everlast Learning/marketing-workspace-0.5.0/tools/juror.ts:100>) und [juror.ts:107](</E:/Everlast Learning/marketing-workspace-0.5.0/tools/juror.ts:107>).

   Vorschlag: Einen verbindlichen `--out`-Zielpfad beim Prüfgegenstand festlegen, ohne dafür ein Ledger einzuführen.

5. Klasse: **Fehler** · Stelle: **C1/C3**, „einmal `upload add`, URL wiederverwenden“ und „Darunter ohne Rückfrage“.

   Die Entscheidung regelt die Kostenfreigabe, aber nicht, welche TGMB-Medien und Review-Unterlagen an OpenArt beziehungsweise Codex weitergegeben werden dürfen. Gerade der automatische Upload unterhalb der Credits-Grenze braucht eine Abgrenzung zur Datenfreigabe; Everlast verlangt für Schritte nach außen eine Freigabe, ohne diesen neuen Ablauf konkret aufzulösen. Beleg: [Entscheidung:106](</E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/01-reviewer-design-medien.md:106>), [Entscheidung:117](</E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/01-reviewer-design-medien.md:117>) und [geheimnisse-und-daten.md:12](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/rules/geheimnisse-und-daten.md:12>).

   Vorschlag: Einmal festlegen, welche Materialien für welchen Dienst freigegeben sind, und vor Upload beziehungsweise Review-Übergabe nur bei nicht abgedecktem Material rückfragen.

6. Klasse: **Fehler** · Stelle: **C9**, „Geprüft wird (1) mit der Everlast-Rule `referenz-diff.md`“ und „Keine neue Rubrikzeile“.

   Der Referenz-Diff prüft sichtbare Geometrie, Objektfehler und Ähnlichkeit; die sechs Juror-Fragen prüfen Gestaltung und KI-Artefakte. Beide verlangen keinen Abgleich dargestellter Maße oder Funktionen mit belegten Produkteigenschaften, sodass eine plausibel erfundene Funktion diese Prüfungen bestehen kann. Beleg: [referenz-diff.md:7](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/rules/referenz-diff.md:7>) und [juror.ts:13](</E:/Everlast Learning/marketing-workspace-0.5.0/tools/juror.ts:13>).

   Vorschlag: Eine verbindliche Produktwahrheitsprüfung gegen belegte Eigenschaften ergänzen und unbelegbare Darstellungen bis zur Klärung offenlassen.

7. Klasse: **Fehler** · Stelle: **C9**, „Kein Projektbeitrag ohne echtes Foto“.

   Für diese zweite harte Regel fehlt die Prüfstelle: Der folgende Satz weist ausdrücklich nur Regel (1) einen Prüfweg zu. Weder ein Verantwortlicher noch ein Zeitpunkt vor der Freigabe stellt sicher, dass tatsächlich ein echtes Foto vorhanden ist. Beleg: [Entscheidung:159](</E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/01-reviewer-design-medien.md:159>).

   Vorschlag: Den Content-Marketer vor dem Ergebnis-Checkpoint anhand von `medien.md` das echte Foto nachweisen lassen und den Beitrag andernfalls offenhalten.

8. Klasse: **Begründung trägt nicht** · Stelle: **C5**, „Nach Everlast“ und „`pipelines/<kanal>/<spalte>/JJMMTT-<slug>/`“.

   Everlast verlangt Medien neben dem jeweiligen Stück, aber keineswegs für jeden Kanal einen Stück-Ordner. Blogartikel sind ausdrücklich einzelne `JJMMTT-<slug>.md`-Dateien; C5 führt daher eine zusätzliche Strukturentscheidung ein, deren Auswirkungen auf Kanalverträge und Leser bisher keinem Thema zugeordnet sind. Beleg: [grafik-designer-workflows.md:19](</E:/Everlast Learning/marketing-workspace-0.5.0/.claude/agents/references/grafik-designer-workflows.md:19>) und [pipelines/blog/README.md:29](</E:/Everlast Learning/marketing-workspace-0.5.0/pipelines/blog/README.md:29>).

   Vorschlag: Stück-Ordner als bewusste Anpassung kennzeichnen, die betroffenen Kanalverträge in P4/P9 abgleichen und deren Umsetzung P7 zuordnen.

9. Klasse: **Fehler** · Stelle: **Q-3**, „muss vor P7 fertig sein“.

   P9 fehlt im zentralen Register vollständig; P7 nennt weiterhin nur P1, P2, P4 und P6 als Voraussetzungen. Auch das Planungsaudit setzt lediglich abgeschlossene Entscheidungen P1–P8 voraus, sodass der verbindliche Ablauf die neue Pflichtstation überspringen kann. Beleg: [STAND.md:35](</E:/TG Marketing OS DevUmbau/docs/umbau/STAND.md:35>) und [STAND.md:39](</E:/TG Marketing OS DevUmbau/docs/umbau/STAND.md:39>).

   Vorschlag: P9 im Register aufnehmen, als Voraussetzung von P7 eintragen und in die Voraussetzungen des Planungsaudits einschließen.

GESAMT: 7 Fehler, 0 Ergänzung, 2 Begründung trägt nicht

