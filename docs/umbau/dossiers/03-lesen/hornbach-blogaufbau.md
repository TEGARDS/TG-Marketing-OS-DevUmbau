# Hornbach „Projekte“-Seiten: Blogaufbau als Referenz (Machart, nicht Inhalt)

Stand: 2026-11-16. Quelle: sechs Seiten auf hornbach.at/projekte/, gelesen mit Firecrawl (JS-Rendering, 5 s Wartezeit, Markdown). Ein früherer Versuch mit WebFetch lieferte nur Seitenrahmen; Firecrawl liefert den vollen Artikeltext. Das Cookie-Banner musste nicht per Aktion akzeptiert werden, der Artikel kam auch so. Rohausgaben liegen nur im Temp-Ordner, nicht im Repo. Lokal gelesen: `E:\TG Design\ausgelagert\seitenvorlagen.md` (Zeilen 5-26) und `E:\TG Design\ausgelagert\inhaltliche-grundsaetze.md`. Übernommen wird nur die Machart, nie Text oder Bild.

## 1. Die sechs Seiten

Alle sechs Seiten tragen den Autor „HORNBACH Redaktion“, ein Shop-Link-Button unter dem Einstieg („… Zum Shop“) und ein Themen-Schlagwort (zum Beispiel „#Handwerkerwissen“). Seitentyp: Hornbach selbst kennzeichnet in den Teaserkarten „Anleitung“ oder „Ratgeber“; der Typ der Seite selbst ist hier aus dem Aufbau abgeleitet.

| Seite | Typ (abgeleitet) | Abschnittsfolge kompakt | Schritte |
|---|---|---|---|
| bodenfliesen-verlegen | Anleitung | Kopf, Kurzeinstieg, Steckbrief (3 Felder), Shop-Button, YouTube-Video (Einwilligung nötig), Sprungmarken, „Überblick“, „Das brauchst Du“ (Material, Werkzeuge), „Vorbereitung“ (Schritte 1-3), „So geht’s“ (Schritte 4-14), Service-Karten, FAQ (5), weiterführende Projekte | 14, durchnummeriert, je ein Bild |
| haus-und-wohnung-kuehlen | Ratgeber | Kopf, Kurzeinstieg, Shop-Button, Sprungmarken, „Das Wichtigste in Kürze“ (Fließtext plus 6 Merkpunkte), Themenkapitel (Sonnenschutz, Lüften, Klimageräte, Ventilatoren, Dämmen), „Produkt-Highlight“ (3), Hinweisboxen, Teaserkarten zu Ratgebern, FAQ (4), weiterführende Projekte | keine Schrittfolge; nur eine Mini-Anleitung „Mobile Klimaanlage aufstellen“ mit 4 Schritten |
| weihnachtsdeko-selber-machen | Ideensammlung mit Mini-Anleitungen | Kopf, Kurzeinstieg, Shop-Button, Sprungmarken, „Überblick“ mit Teaserkarten (21 „Anleitung“, 4 „Ratgeber“), je Idee: Einstieg, „Das brauchst Du“, „So geht’s“, FAQ (5), weiterführende Projekte | 8 Ideen, davon 7 mit 3 bis 5 Schritten (zusammen 27), 1 mit Kurztext ohne Nummern |
| waschtisch-mit-fliesen-bauen | Anleitung | Kopf, Kurzeinstieg, Shop-Button, Sprungmarken, „Überblick“, „Das brauchst Du“, „So geht’s“, 1 Hinweisbox, Service-Karten, FAQ (3), weiterführende Projekte | 10, je ein Bild |
| waschtisch-selber-bauen | Anleitung | Kopf, Kurzeinstieg, Shop-Button, Sprungmarken, „Das Wichtigste in Kürze“ (5 Merkpunkte), „Das brauchst Du“, „So geht’s“, Service-Karten, FAQ (4), weiterführende Projekte (10 Karten) | 6, je ein Bild |
| rohre-verbinden | Ratgeber | Kopf, Kurzeinstieg, Shop-Button, Sprungmarken (11), „Das Wichtigste in Kürze“ (Fließtext plus 5 Merkpunkte), Themenkapitel je Verbindungsart, „Produkt-Highlight“ (3), Hinweisboxen (3), Produkt-Sortiment-Karten, FAQ (4), weiterführende Projekte | keine Schrittfolge; eine Kurzliste „7 Schritte“ (Kleben) als nummerierte Liste ohne Bilder |

Gezählt wurde im Firecrawl-Text. Die Zahl der Bilder je Seite (9 bis 95) ist nur grob; sie enthält Produktkarten.

## 2. Gemeinsamkeiten

### Anleitungen (Bodenfliesen, Waschtisch mit Fliesen, Waschtisch selber bauen; Weihnachtsdeko je Idee)

Struktur:
- Reihenfolge fest: Kopf mit Kurzeinstieg, Sprungmarken, Überblick (oder „Das Wichtigste in Kürze“), Block „Das brauchst Du“, Block „So geht’s“, FAQ, weiterführende Projekte.
- Überschriften nach Muster „<Thema>: Das brauchst Du“, „<Thema>: So geht’s“, „<Thema>: häufige Fragen“.
- Schritte durchnummeriert, je Schritt eine H3 mit kurzer Tätigkeit („Dübellöcher bohren“, „Fuge abdichten“) und genau ein Bild. Bei Bodenfliesen wird in „Vorbereitung“ (1-3) und „So geht’s“ (4-14) geteilt.
- Schrittzahl 3 bis 14; die kürzeste Anleitung hat 6, die längste 14.

Bausteine:
- „Das brauchst Du“ ist ein Block mit zwei Karussells „Material“ und „Werkzeuge“, jeweils Bild plus Bezeichnung, am Ende „Zum Sortiment“ und „Material- und Werkzeugliste: Jetzt öffnen“. Umfang 5 bis 32 Einträge. Die Karten verlinken auf Sortiment oder Artikel.
- Hinweisboxen („Hinweis“, „Tipp“) nur gelegentlich (0 bis 4 je Seite), eingeschoben zwischen zwei Schritten.
- Service-Karten am Ende („Reservieren und abholen“, „Anhänger und Transporter mieten“, Montageservice) statt Produktkacheln.
- Steckbrief nur bei Bodenfliesen: Zeitaufwand (3 h/m²), Macher (1), Herausforderung (Wert als Symbol, nicht als Text lesbar). Kosten fehlen überall.
- Video nur bei Bodenfliesen (YouTube, erst nach Einwilligung).

Sprachstil:
- „Du“ durchgehend, im Satz großgeschrieben („Dir“, „Dein“). Redaktion spricht als „wir“ („Wir zeigen Dir …“).
- Einstieg oft mit rhetorischer Frage oder Zusage („Aber keine Panik!“), Schritte danach nüchtern, im Imperativ oder mit „wird/werden“ im Passiv, 1 bis 3 Sätze je Schritt, meist 10 bis 20 Wörter je Satz.
- Beispiel (Bodenfliesen): „Aber keine Panik! Wir zeigen Dir Schritt für Schritt, was zu tun ist.“
- Sicherheits- und Herstellerhinweise werden in Schritten mitgeführt („nach Herstellerangabe“, „Wasserzufuhr abdrehen“).

### Ratgeber und Ideenseiten (Haus kühlen, Rohre verbinden; Weihnachtsdeko als Sammlung)

Struktur:
- Nach dem Kurzeinstieg ein Block „Das Wichtigste in Kürze“ mit Fließtext, „Das solltest Du wissen:“ und 5 bis 6 Merkpunkten, danach „Direkt zu den Inhalten:“ mit Sprungmarken.
- Danach Themenkapitel, jedes mit H2 und Absatz, oft mit Aufzählung; keine durchgehende Schrittfolge, höchstens eine eingebettete Mini-Anleitung (Mobile Klimaanlage aufstellen, 4 Schritte; Rohre kleben, 7 Schritte).
- Am Ende: „… häufige Fragen“ (4), dann „Themen, die Dich auch interessieren könnten“ mit Karten, die als „Anleitung“ oder „Ratgeber“ markiert sind.
- Weihnachtsdeko: Überblick mit 8 Ideen als Teaserkarten, dann je Idee ein eigener Mini-Aufbau („Das brauchst Du“, „So geht’s“).

Bausteine:
- Hinweisboxen („Hinweis“, „Achtung“, „Tipp“) häufiger (Kühlen: 4 Boxen plus 8 Tipp/Achtung; Rohre: 3 plus 1), mit Warnungen zu Gas, Trinkwasser und Genehmigungen.
- „Produkt-Highlight“ als Karte mit Name, Bewertung, Preis, „Zum Artikel“ (je 3 auf Kühlen und Rohre), dazu Sortiment-Karten („Zu den Produkten“).
- Teaserkarten zu weiterführenden Ratgebern mitten im Text, bei Kühlen bis zu 8 in einer Gruppe.
- Kein Steckbrief, kein Video (Kühlen verweist nur in einer Teaserkarte auf ein Video).

Sprachstil:
- „Du“, „wir“; Einstieg mit Alltagsbild oder Frage, Merkpunkte als ganze Sätze im Imperativ („Schließe Rollläden …“) oder als Feststellung.
- Konkrete Werte bei Auswahlhilfen (Watt je Raumfläche, Dezibel), Hersteller- und Fachbetriebshinweise bei Risiko.
- Beispiele: Kühlen „Lass die Sonne gar nicht erst rein.“; Rohre „Nicht jedes Rohr wird gleich verbunden.“; Weihnachtsdeko „Such Dir Deine Lieblingsidee aus und spring direkt zur passenden Schritt-für-Schritt-Anleitung.“

Weitere wörtliche Beispiele (je eines): Waschtisch mit Fliesen „Du bestimmst, wie viel Stauraum Du hast und welche Fliesen Du verwendest.“; Waschtisch selber bauen „Drehe vor Arbeiten an den Wasseranschlüssen die Wasserzufuhr ab“ (Auszug).

## 3. Abgleich mit `seitenvorlagen.md`

### Unsere Bausteine (belegt, Blogartikel Anleitung oder Ratgeber)

1. `BlogHero` (Breadcrumb, Label „Anleitung“ grün mit Steckbrief oder „Ratgeber“ graphit ohne, H1, Kurzfassung, `ShopBanner`, `TagList`, Titelbild 3:2)
2. `TipBox` „💡 Das Wichtigste vorab“ (2-3 Sätze Antwort)
3. Kapitel als `Title` (nummerierte H2) mit `TextImage`, `ImageQuote`, `Prose`/`BulletList`, `NoteBox`, `TextGallery`, Tabellenbausteine, `TipBox` „Tipp vom Profi“, `AlertBanner`, `Tabs`
4. Bei Anleitungen: `NoteBox` Werkzeug/Material, dann `StepsPlain`, `StepsFill`/`StepsFillInverse` oder `StepsTitled`
5. `CheckActionBox` nach dem ersten kaufrelevanten Kapitel
6. `ProductTabs` (WPBakery) mit Zubehör
7. „💬 Fazit“ + `TipBox` „Conclusio:“
8. `Faq` (bei Ratgebern)
9. `CtaBanner`
10. Theme: Teilen, Vor/Zurück, ähnliche Beiträge

Sprachregeln bei uns (belegt): immer „du“, Ton „kompetenter Handwerker-Kumpel“, konkrete Werte statt Adjektive, Emojis nur als erstes Zeichen fester Box-/Kapiteltitel, Projekte starten mit „Auf einen Blick“.

### Abgleichtabelle

| Hornbach-Baustein | Baustein bei uns | Status |
|---|---|---|
| Kopf: H1, Autor „Redaktion“, Kurzeinstieg, Shop-Button „… Zum Shop“, Schlagwort | `BlogHero` mit `ShopBanner`, `TagList` | gleichwertig; Autorzeile haben wir laut Vorlage nicht |
| Steckbrief (nur Bodenfliesen: Zeitaufwand, Macher, Herausforderung) | `BlogHero` mit Steckbrief (Label „Anleitung“) | wir haben ihn bei jeder Anleitung, Hornbach nur bei einer von drei; Kosten fehlen bei beiden |
| „Das Wichtigste in Kürze“ mit Merkpunkten, oder „Überblick“ | Kurzfassung im `BlogHero` + `TipBox` „Das Wichtigste vorab“ | gleichwertig; Hornbach nutzt Merkpunkte-Liste mit Kerninfo, wir 2-3 Sätze |
| Sprungmarken „Direkt zu den Inhalten“ | keine Entsprechung in der Vorlage | Hornbach hat, uns fehlt (Theme-Inhaltsverzeichnis?) |
| „Das brauchst Du“ mit Material- und Werkzeug-Karussell, Bild je Eintrag, Links ins Sortiment | `NoteBox` Werkzeug/Material (Liste) | Hornbach reicher (Bild, Produktlink je Eintrag), wir schlanker |
| Schritte: nummeriert, H3 je Schritt, ein Bild je Schritt | `StepsPlain` / `StepsFill` / `StepsTitled` | gleichwertig |
| Hinweisboxen „Hinweis/Achtung/Tipp“ | `TipBox` „Tipp vom Profi“, `AlertBanner` | gleichwertig |
| „Produkt-Highlight“-Karte (Name, Bewertung, Preis) und Sortiment-Karten | `CheckActionBox`, `ProductTabs`, `ShopBanner` | Hornbach streut Karten im Text, wir bündeln am Ende |
| Service-Karten (Abholen, Mieten, Montageservice) | keine | Hornbach hat, uns fehlt (shopabhängig) |
| Teaserkarten „Anleitung/Ratgeber“ im Text | `ProductTabs` ist Produkt, nicht Beitrag; Theme „ähnliche Beiträge“ nur am Ende | Hornbach hat Mittelteil-Verweise, uns fehlt |
| FAQ (3 bis 5 Fragen, bei allen sechs Seiten) | `Faq` nur bei Ratgebern | bei uns nur Ratgeber, Hornbach auch bei Anleitungen |
| Weiterführende Projekte (Karten) | Theme „ähnliche Beiträge“ | gleichwertig |
| Video (nur Bodenfliesen, YouTube mit Einwilligung) | kein eigener Baustein | Hornbach hat, uns fehlt in der Vorlage |
| Fazit | `Title` „💬 Fazit“ + `TipBox` „Conclusio:“ | wir haben, Hornbach nicht (nicht auf den sechs Seiten) |
| Schlussaufruf | `CtaBanner` | wir haben, Hornbach nicht |
| Vergleichs- und Datentabellen | `ComparisonTable`, `FeatureTable`, `SpecTable` u. a. | wir haben viele; Hornbach nutzt Plus/Minus-Listen in einem FAQ-Fall und Wertelisten im Fließtext |
| Teilen, Vor/Zurück | Theme-Elemente | wir haben, bei Hornbach nicht gesehen |

Zusammengefasst:
- Hornbach hat, uns fehlt: Sprungmarken, Bild- und Linkkarten im Material-/Werkzeugblock, Service-Karten, Teaserkarten im Textverlauf, FAQ auch bei Anleitungen, Video-Einbettung.
- Wir haben, Hornbach nicht: Fazit mit Conclusio, `CtaBanner`, Steckbrief bei jeder Anleitung, große Tabellenfamilie, `ImageQuote`/`TextGallery`, Teilen und Vor/Zurück (letzteres bei Hornbach nicht beobachtet).

## 4. Was nicht prüfbar war

- Der Wert „Herausforderung“ im Steckbrief von Bodenfliesen kam nicht als Text, vermutlich ein Symbol. Die Felder „Zeitaufwand 3 h/m²“ und „Macher 1“ sind lesbar.
- Der YouTube-Film der Bodenfliesen-Seite ist nur als Einwilligungshinweis sichtbar; Länge und Inhalt wurden nicht geprüft. Das Banner anderer Dienste (Cookie, Marktauswahl) wurde nicht per Aktion bedient, es verdeckte den Artikel nicht.
- Bildzahl je Seite ist aus der Markdown-Ausgabe gezählt und enthält Produkt- und Teaserbilder; nur die Bilder je Schritt (eines je Schritt) wurden stichprobenartig an vier Seiten geprüft.
- Anzahl Wörter je Satz sind Schätzwerte aus Lesen, nicht gezählt.
- Typ „Ratgeber/Anleitung/Ideensammlung“ der Seite selbst ist aus Aufbau abgeleitet; Hornbach beschriftet nur die verlinkten Teaserkarten.
- Optik (Farben, Abstände, Karussell-Verhalten) ist aus Markdown nicht ablesbar.
- Eine Aussage zu „Kosten“ im Steckbrief ist nur negativ: auf keiner der sechs Seiten gefunden.
