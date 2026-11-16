1. **Klasse: Fehler. Stelle: B2** — „Alle übrigen Wissensdateien […] laufen im normalen `develop`-Fluss“.

   Die Freigabegrenze folgt Dateinamen, während B3 die Belegpflicht nach Aussageinhalt definiert. Technische Werte können laut B6 auch in `offer.md` stehen; Everlast sieht dort ausdrücklich eine Garantie vor ([struktur.md:116](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/amm-workspace-setup/references/struktur.md:116>)). Solche Aussagen könnten außerhalb von `fakten.md` ohne vorheriges Ja verändert werden.
   
   **Vorschlag:** Die Freigabeausnahme auf Änderungen belegpflichtiger Aussagen in sämtlichen Wissensdateien beziehen.

2. **Klasse: Fehler. Stelle: A2/B1/F1** — „`quellen/` unverändert“.

   F1 verlangt einen `quellen/index.md`, C3 dessen laufende Pflege; B1 verbietet gleichzeitig Änderungen unter `quellen/` ([P2:118](<E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/02-wiki-architektur.md:118>), [P2:223](<E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/02-wiki-architektur.md:223>), [P2:351](<E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/02-wiki-architektur.md:351>)). Bereits die nächste Quellenaufnahme müsste den vorhandenen Index ändern und würde damit gegen die beschriebene Prüfung verstoßen.
   
   **Vorschlag:** Unveränderliche Quellfassungen ausdrücklich von veränderlichen Verzeichnissen und dem Eingang abgrenzen.

3. **Klasse: Fehler. Stelle: B3/C3/F1** — „Belegpflicht mit Seitenanker (`[intern: quelle:/<ordner>/r<n>#seite-<n>]`)“.

   Dieses einzige vorgesehene Belegformat funktioniert für eine der zwölf vorhandenen Quellen nicht: Die Statik-Notiz besitzt ausdrücklich keinen Extrakt und verweist auf Überschriften in `original.md` ([karte.md:21](<E:/tegards/knowledge/quellen/technik/2026-08_notiz_statik-unterkonstruktion-glasschiebewand_de/karte.md:21>)). Der bisherige Vertrag erlaubt dafür `original#<anker>` ([‌_SCHEMA.md:72](<E:/tegards/knowledge/_SCHEMA.md:72>)).
   
   **Vorschlag:** Neben Seitenankern die vorhandene Belegform für Textoriginale mit Überschriftenankern übernehmen.

4. **Klasse: Fehler. Stelle: E2** — „Die Kern-Dateien gehen nach `projekte/archiv/<JJMMTT>-kern.md`“.

   Damit liegt das zu bewahrende Destillat innerhalb eines ausdrücklich unterstützten Löschziels: `workspace-cleanup` leert unter anderem `projekte/archiv/` und löscht die ausgewählten Ordner anschließend vollständig ([SKILL.md:7](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/workspace-cleanup/SKILL.md:7>), [SKILL.md:44](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/workspace-cleanup/SKILL.md:44>)). Beim Aufräumen dieses Archivs würde die gerade erzeugte Kern-Datei mit entfernt.
   
   **Vorschlag:** Den Kern außerhalb des jeweiligen Löschziels ablegen und ausdrücklich vom Cleanup-Umfang ausschließen.

5. **Klasse: Fehler. Stelle: C3 / Offene Punkte P7** — „Eigene Felder nur `produktlinien`, `stuetzt_sich_auf` […] und `oberkategorie`“.

   Die abschließende Feldliste kollidiert mit übernommenen Verträgen: Cleanup benötigt `quelle_commit` für den Rückweg, das eingefrorene Kurswissen `lektion` für seine Reihenfolge ([Cleanup:54](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/workspace-cleanup/SKILL.md:54>), [wissen/README.md:8](<E:/Everlast Learning/marketing-workspace-0.5.0/wissen/README.md:8>)). Auch die nach P7 verschobene Frage nach `last_updated` ist bereits beantwortbar: Der Steuerstand liest dieses Feld tatsächlich ([build.ts:89](<E:/Everlast Learning/marketing-workspace-0.5.0/steuerstand/build.ts:89>)).
   
   **Vorschlag:** Geltungsbereich, notwendige Ausnahmen und Feldzuordnungen in P2/P9 entscheiden und P7 deren Umsetzung übergeben.

6. **Klasse: Fehler. Stelle: C3** — „dazu `stub`, weil das Everlast-Setup daran den Fortschritt erkennt“.

   Everlast behandelt jede vorhandene Ergebnisdatei ohne `status: stub` als fertig; auch der Steuerstand wartet nur auf `stub` oder fehlende Dateien ([Setup-SKILL.md:48](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/amm-workspace-setup/SKILL.md:48>), [build.ts:106](<E:/Everlast Learning/marketing-workspace-0.5.0/steuerstand/build.ts:106>)). Mit dem neuen Statusvorrat würde deshalb bereits ein ungeprüfter `draft` die Station abschließen – genau die grünen Stationen ohne Prüfung, die Weg 1 ausschließt ([STAND.md:28](<E:/TG Marketing OS DevUmbau/docs/umbau/STAND.md:28>)).
   
   **Vorschlag:** Festlegen, dass eine Onboarding-Station erst nach Markus’ Freigabe fertig ist, und die Fortschrittslogik entsprechend anpassen lassen.

7. **Klasse: Fehler. Stelle: A1/C1/A8** — „Prime-Listen und Agenten passen ohne Umbau“.

   Der Beleg trägt diese Aussage nicht: `/prime` verbietet eine siebte Datei, `prime-content` zusätzliche Dateien außerhalb seiner Liste ([prime.md:25](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/commands/prime.md:25>), [prime-content.md:19](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/commands/prime-content.md:19>)). Die neuen Pflichtlektüren `fakten.md`, gemeinsame Persona B und „Gilt heute“ sind damit keine unveränderte Everlast-Leseregel.
   
   **Vorschlag:** Die Aussage einschränken und eine verbindliche Zusatzleseregel nach dem Prime-Lauf als Anpassung für P7 festhalten.

8. **Klasse: Fehler. Stelle: C1/D2** — „die ‚Gilt heute‘-Abschnitte […] keine ganzen Verläufe“.

   Neue Erkenntnisse werden nur angehängt, verdichtet wird erst ab 40 neuen Zeilen oder auf Zuruf ([P2:276](<E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/02-wiki-architektur.md:276>), [P2:280](<E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/02-wiki-architektur.md:280>)). Dadurch fehlt für bis zu 39 neue Einträge der Rückweg in die Pflichtlektüre; vor der ersten Verdichtung existiert möglicherweise überhaupt kein „Gilt heute“.
   
   **Vorschlag:** Agenten zusätzlich die seit der letzten Verdichtung angehängten Erkenntnisse lesen lassen und den ersten Lernstand ausdrücklich regeln.

9. **Klasse: Fehler. Stelle: A9/C3** — „`stale_after` statt `profil_geprueft_am`“.

   Der bisherige Vertrag trennt vollständige Profilprüfung ausdrücklich von neuen Beobachtungen und Teilkorrekturen; nur Erstere erneuert die Profilfrische ([‌_SCHEMA.md:80](<E:/tegards/knowledge/_SCHEMA.md:80>)). Für das Ersatzfeld fehlen Frist und Erneuerungsregel, sodass eine neue Beobachtung ein ungeprüftes Profil wieder frisch erscheinen lassen könnte.
   
   **Vorschlag:** Die bisherige Bedeutung einschließlich fehlender Erstprüfung erhalten und festlegen, dass ausschließlich eine vollständige Profilprüfung die Frist erneuert.

10. **Klasse: Fehler. Stelle: B6** — „Ein Widerspruch wie `fakten.md` 7 m gegen `offer.md` 6 m bleibt also unentdeckt“.

    Die zitierte Ausschlussbedingung betrifft die mechanische Kandidatensuche, nicht den gesamten Scan. Wissensdateien gelangen weiterhin in Lesepakete, werden vollständig gelesen und der Leser soll zusätzlich selbst suchen ([konflikt-scan.ts:302](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/amm-konflikt-scan/scripts/konflikt-scan.ts:302>), [konflikt-scan.ts:442](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/amm-konflikt-scan/scripts/konflikt-scan.ts:442>), [rubrik.md:100](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/amm-konflikt-scan/references/rubrik.md:100>)). Eine fehlende mechanische Erkennung ist damit belegt, die behauptete vollständige Blindstelle nicht.
    
    **Vorschlag:** Die Aussage auf die nachgewiesene Grenze beschränken und den zusätzlichen Wissensprüfweg anhand seiner tatsächlich fehlenden Prüfkriterien begründen.

11. **Klasse: Fehler. Stelle: X2** — „Everlast hat so etwas nicht“.

    Das vorhandene Playbook ist bereits ein gegliedertes Nachschlagewerk für Rollen, Skills, Rules, Commands, Betriebsdokumentation und Arbeitsabläufe ([build.ts:5763](<E:/Everlast Learning/marketing-workspace-0.5.0/steuerstand/build.ts:5763>), [build.ts:5799](<E:/Everlast Learning/marketing-workspace-0.5.0/steuerstand/build.ts:5799>), [build.ts:5883](<E:/Everlast Learning/marketing-workspace-0.5.0/steuerstand/build.ts:5883>)). Neue Tegards-Prozesse fehlen dort naturgemäß; das belegt keinen fehlenden Handbuch-Baustein.
    
    **Vorschlag:** Das bestehende Playbook als Ausgangspunkt übernehmen und nur die fehlenden Tegards-Prozesskapitel ergänzen.

12. **Klasse: Fehler. Stelle: B1/F1** — „38 Werte hat Markus […] korrigiert“.

    Die eigene Zählung der zwölf Quellenkarten ergibt elf konkret als korrigiert gekennzeichnete Prüfstellen; 38 ist die Summe sämtlicher Kennungen in den betroffenen Sammelzeilen. Beispielsweise enthält eine Zeile acht Kennungen, korrigiert ist darin ausschließlich PS-14, während andere ausdrücklich „KI bestätigt“ bleiben ([Pinela-Tilt-Karte:68](<E:/tegards/knowledge/quellen/produkte/lamellendaecher/2026-08_montageanleitung_pinela-tilt_de/karte.md:68>)).
    
    **Vorschlag:** Korrigierte Einzelstellen und Kennungen betroffener Sammelzeilen getrennt zählen und F1 auf den vollständigen Erhalt der tatsächlichen Korrekturen beziehen.

13. **Klasse: Fehler. Stelle: B4/E1** — „alle 17 Seiten `human:mm`“ / „38 Blätter“.

    Die eigene Bestandszählung ergibt 16 Wiki-Seiten mit `verified`, jeweils `human:mm`, sowie 37 Kursblätter zuzüglich `wissen/README.md`. Die README ist eine Ordnungsdatei und wird vom Steuerstand ausdrücklich aus den Wissensblättern ausgeschlossen ([wissen/README.md:5](<E:/Everlast Learning/marketing-workspace-0.5.0/wissen/README.md:5>), [build.ts:8751](<E:/Everlast Learning/marketing-workspace-0.5.0/steuerstand/build.ts:8751>)).
    
    **Vorschlag:** Beide Bestandszahlen korrigieren und jeweils die gezählte Einheit nennen.

14. **Klasse: Fehler. Stelle: E3** — „Everlast zieht stur alle 20 s ein Bild“.

    Das Skript akzeptiert den Abstand als dritten Parameter; 20 Sekunden sind lediglich der Default ([material-zu-text.sh:3](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/learn/scripts/material-zu-text.sh:3>), [material-zu-text.sh:8](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/learn/scripts/material-zu-text.sh:8>)). Der Skill verlangt bereits 5–10 Sekunden für Screencasts und 20 Sekunden oder keine Frames für Vorträge ([SKILL.md:48](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/learn/SKILL.md:48>)).
    
    **Vorschlag:** Den konfigurierbaren Abstand und die vorhandene Unterscheidung korrekt beschreiben.

15. **Klasse: Begründung trägt nicht. Stelle: B1/F3** — „Die 30 Zeilen mit Fußnote ¹ […] sind erledigt“.

    Die Fußnote erklärt diese Punkte nur beim Wegfall ihrer jeweiligen Werkzeuge für erledigt ([P5-Dossier:15](<E:/TG Marketing OS DevUmbau/docs/umbau/dossiers/05-altbestand.md:15>)). B1 behält jedoch Extrakt und Prüfseite; beispielsweise betreffen W-18 und W-21 gerade die Prüfseite beziehungsweise die Bedeutung von „KI bestätigt“ ([P5-Dossier:112](<E:/TG Marketing OS DevUmbau/docs/umbau/dossiers/05-altbestand.md:112>), [P5-Dossier:115](<E:/TG Marketing OS DevUmbau/docs/umbau/dossiers/05-altbestand.md:115>)).
    
    **Vorschlag:** Die betroffenen Zeilen einzeln als weiterhin erforderlich, bereits gelöst oder bewusst verworfen einordnen.

16. **Klasse: Begründung trägt nicht. Stelle: D2** — „Ein fester Termin bräuchte einen Zeitplaner“.

    Eine zeitabhängige Fälligkeit kann beim nächsten normalen Lauf festgestellt werden. B6 beschreibt selbst genau dieses Modell „ohne Zeitplaner“ mit einer 30-Tage-Frist ([P2:181](<E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/02-wiki-architektur.md:181>)).
    
    **Vorschlag:** Die Zeilenschwelle mit dem gewünschten Arbeitsrhythmus begründen und die behauptete technische Notwendigkeit eines Zeitplaners streichen.

17. **Klasse: Ergänzung. Stelle: B6** — „fällig nach 30 Tagen oder 10 Wissens-Commits“.

    Neun neu entstehende Faktenblätter begründen eine Prüfung beim Aufbau; sie begründen noch keine wiederkehrende Vollprüfung mit zwei Schwellen, Steuerstand-Karte, Brief und Kopplung an die Verdichtung ([P2:182](<E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/02-wiki-architektur.md:182>)). Die laufende Prüfung berührter Dateien und eine Vollprüfung auf Zuruf decken den beschriebenen unmittelbaren Fall bereits ab.
    
    **Vorschlag:** Wiederkehrende Fälligkeit samt Oberfläche nach SPAETER verschieben, ausgelöst durch einen nachweislich übersehenen Widerspruch oder wiederholt versäumte Prüfungen.

18. **Klasse: Ergänzung. Stelle: C3/X2** — „Graph-Ansicht im Steuerstand“.

    Der Wunsch ist dokumentiert, aber keine konkrete heutige Such- oder Prüfaufgabe, die diese Ansicht erfüllen soll ([P2:235](<E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/02-wiki-architektur.md:235>)). Der beschlossene Leseweg und die Prüfungen funktionieren ohne Graph.
    
    **Vorschlag:** Die Ansicht als optionale Anforderung nach SPAETER verschieben, bis eine konkrete Beziehungsfrage mit Index und Links nicht praktikabel beantwortbar ist.

19. **Klasse: Ergänzung. Stelle: E1** — „Everlast-Abgleich […] Auf Knopfdruck“.

    P1 enthält bereits einen vollständigen Ablauf: Version herunterladen, durch eine Session vergleichen lassen, Neuerungen auflisten und einzeln entscheiden ([P1:200](<E:/TG Marketing OS DevUmbau/docs/umbau/entscheidungen/01-reviewer-design-medien.md:200>)). Ein heutiger Engpass, der zusätzliche Buttons und einen eigenen Baustein rechtfertigt, wird nicht genannt.
    
    **Vorschlag:** Den manuellen P1-Ablauf beibehalten und die Bedienautomatisierung erst bei wiederholt relevantem Aufwand vorsehen.

20. **Klasse: Ergänzung. Stelle: E3** — „Ein Bild bei großem Szenenwechsel“.

    Szenenwechselerkennung, Ähnlichkeitsfilter und automatische Sprecher-Erkennung führen zusätzliche Verfahren und einzustellende Schwellen ein, ohne dass ein heutiges Materialbeispiel deren Bedarf belegt. Der vorhandene parametrierbare Abstand bietet bereits eine einfache Anpassung an Screencasts und Vorträge ([learn/SKILL.md:48](<E:/Everlast Learning/marketing-workspace-0.5.0/.claude/skills/learn/SKILL.md:48>)).
    
    **Vorschlag:** Zunächst den einfachen Abstand unter Windows übernehmen und adaptive Auswahl erst bei nachweislich verpasstem Bildwissen oder untragbarer Bildmenge ergänzen.

GESAMT: 14 Fehler, 4 Ergänzung, 2 Begründung trägt nicht

