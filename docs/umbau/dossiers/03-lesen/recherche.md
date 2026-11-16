# Recherche Stand 2026: GEO, SERP-Merkmale, Seitenschemas, Seitenaufbau, Wissenspflege

Abrufdatum aller Quellen: 16.11.2026. Sprache Deutsch. Markt: google.de, WooCommerce + RankMath.

Lesehinweise
- Die Seiten wurden per WebFetch geöffnet. Die Inhalte kamen als Zusammenfassung eines Hilfsmodells zurück, nicht als Volltext. Wörtliche Formulierungen sind deshalb nicht Zeichen für Zeichen geprüft; Zahlen und Daten wurden aber der geöffneten Seite entnommen.
- Evidenzstufen: **[P]** belegt (Primärquelle: Google, OpenAI, Microsoft, Perplexity, RankMath, WooCommerce-Code). **[S]** belegt (Studie, Sekundär: Hersteller- oder Branchenstudie, Methode und Stichprobe genannt). **[M]** Branchenmeinung oder unbelegt. **[nv]** nicht verifiziert (aus Suchtreffer-Zusammenfassung oder Gedächtnis, nicht selbst geöffnet).
- Fast alle Studien stammen von Tool-Anbietern mit Eigeninteresse (Ahrefs, Peec, SE Ranking, Seer). Sie sind korrelativ.
- WebFetch scheiterte (HTTP 403) bei searchengineland.com, OpenAI-Hilfecenter und openai.com. Diese Quellen sind nur über Suchtreffer bekannt und als [nv] markiert.

---

## A. 12 Kernaussagen für die Entscheidung

1. **Google sagt offiziell: Für AI Overviews und AI Mode gibt es keine Sonderoptimierung.** Voraussetzung ist: indexiert und mit Snippet anzeigbar. Google behandelt "GEO/AEO" als SEO. Der Leitfaden erschien am 15.05.2026. [P]
   https://developers.google.com/search/docs/appearance/ai-features
   https://developers.google.com/search/docs/fundamentals/ai-optimization-guide
   https://developers.google.com/search/blog/2026/05/a-new-resource-for-optimizing (Blog vom 15.05.2026, John Mueller)

2. **llms.txt ist für Google-Suche wirkungslos (Mythos).** Google stellte das am 15.06.2026 im Leitfaden klar; SE Ranking fand bei rund 300.000 Domains keine Korrelation mit KI-Zitaten. "GEO-Schema" nennt Google nicht und verlangt kein besonderes schema.org-Markup. [P] + [S]
   https://developers.google.com/search/updates (Eintrag 15.06.2026)
   https://www.searchenginejournal.com/llms-txt-shows-no-clear-effect-on-ai-citations-based-on-300k-domains/561542/ (20.11.2025)

3. **Strukturierte Daten bringen für KI-Zitate keinen belegten Vorteil.** Ahrefs (11.05.2026): 1.885 Seiten, die JSON-LD ergänzten, gegen Kontrollseiten, 30 Tage davor/danach: AI Overviews -4,6 %, AI Mode +2,4 % (n. s.), ChatGPT +2,2 % (n. s.). Strukturierte Daten bleiben für Rich-Result-Berechtigung und Verständnis sinnvoll, müssen zum sichtbaren Text passen. [P] + [S]
   https://ahrefs.com/blog/schema-ai-citations/
   https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data

4. **Zitierte Quellen sind nur zum Teil die Top-10 und wechseln stark.** Ahrefs (02.03.2026, 863.000 Suchanfragen, ca. 4 Mio. URLs): 37,9 % der in AI Overviews zitierten URLs standen in den Top 10, 31,0 % jenseits Platz 100 (Parsing gegenüber 76 % im Juli 2025 geändert, nicht direkt vergleichbar). Google bestätigt "Query Fan-out". Für ChatGPT zeigte Seer (02.2025, ca. 500 Zitate) eine Nähe zu Bing-Top-20. [S] + [P]
   https://ahrefs.com/blog/ai-overview-citations-top-10/
   https://www.seerinteractive.com/insights/87-percent-of-searchgpt-citations-match-bings-top-results

5. **KI-Antworten sind sehr volatil; Wettbewerbs-Snapshots veralten in Tagen.** Ahrefs (11.11.2025, über 43.000 Suchanfragen): AI-Overview-Inhalt ändert sich bei ca. 70 % der Beobachtungen, mittlere Beständigkeit ca. 2,15 Tage, ca. 45 % der zitierten URLs neu. Ahrefs (29.10.2026): mindestens die Hälfte der Zitate am Folgetag weg, ca. 75 % kehren binnen 20 Tagen zurück. [S]
   https://ahrefs.com/blog/ai-overview-change/
   https://ahrefs.com/blog/how-stable-are-ai-citations/

6. **Verfügbarkeit Deutschland: AI Overviews seit 26.03.2025, AI Mode auf Deutsch seit Oktober 2025.** Googles Hilfeseite führt Deutschland und Deutsch in der AI-Mode-Liste. SISTRIX: AI Overviews bei 57,9 % der beobachteten deutschen Keywords am 06.11.2026 (zählt Keywords, nicht Suchvolumen; Stichprobe nicht offengelegt). [P] + [S] (Start AIO: [S], t3n)
   https://support.google.com/websearch/answer/16011537?hl=en
   https://blog.google/products/search/ai-mode-expands-languages-locations/ (07.10.2025)
   https://www.drweb.de/google-ai-overviews-haelfte-keywords/ (06.11.2026)

7. **Shop-Sonderfall: Merchant-Center-Feed ist der Hebel, agentisches Einkaufen ist (noch) nicht in Deutschland.** Google nennt Merchant-Center-Feeds für Sichtbarkeit in KI-Antworten. UCP-Checkout/Universal Cart: nur USA, Kanada/Australien "in den kommenden Monaten", UK später; kein Wort zu Deutschland (20.05.2026). ChatGPT Instant Checkout: nach Quellen US-only. [P] (Google) / [nv] (OpenAI, ads in AI Mode DE)
   https://developers.google.com/search/docs/fundamentals/ai-optimization-guide
   https://blog.google/products-and-platforms/products/shopping/shopping-updates-google-marketing-live

8. **SERP-Merkmale wurden seit 2023 stark gestrichen.** FAQ-Rich-Result: 2023 auf Behörden/Gesundheit beschränkt, ab 07.05.2026 gar nicht mehr; HowTo 2023 abgeschafft; sieben Typen im Juni 2025; Sitelinks-Suchfeld 21.11.2024; Breadcrumb nur Desktop. Das ist der Grund, warum Seitenaufbau nicht mehr aus Rich-Result-Merkmalen der Top-Treffer abgeleitet werden sollte. [P]
   https://developers.google.com/search/updates
   https://developers.google.com/search/blog/2023/08/howto-faq-changes
   https://developers.google.com/search/blog/2025/06/simplifying-search-results

9. **Produktseiten: Merchant-Listing-Markup nur auf Einzelproduktseiten mit einem Offer; Kategorieseiten sind ausdrücklich nicht unterstützt.** Varianten über ProductGroup. Versand/Rückgabe möglichst auf Organisationsebene. WooCommerce-Kern gibt bei variablen Produkten ohne gewählte Variante AggregateOffer aus (kein Merchant-Listing-Offer). [P] (Google, WooCommerce-Code)
   https://developers.google.com/search/docs/appearance/structured-data/merchant-listing
   https://developers.google.com/search/docs/appearance/structured-data/product-variants
   https://raw.githubusercontent.com/woocommerce/woocommerce/trunk/plugins/woocommerce/includes/class-wc-structured-data.php

10. **RankMath liefert viel kostenlos, ItemList/Speakable/Q&A nur PRO.** WooCommerce-Produktschema kommt automatisch; GTIN/MPN-Zusatzfelder PRO; mehrere Schema-Typen je Seite PRO. RankMath selbst schreibt, dass Google FAQ-Rich-Snippets nicht mehr zeigt. [P] (Hersteller-Doku)
    https://rankmath.com/kb/rich-snippets/
    https://rankmath.com/kb/gtin-mpn-woocommerce/

11. **Inhalt: Google verlangt Originalität statt Struktur-Tricks.** Kein Chunking nötig, keine ideale Länge, Seiten nur für Fan-out-Varianten verletzen die Scaled-Content-Abuse-Policy. Zitierte Passagen liegen laut Studien überproportional im oberen Seitendrittel (ca. 44-46 %). [P] + [S]
    https://developers.google.com/search/docs/fundamentals/ai-optimization-guide
    https://www.practicalecommerce.com/studies-reveal-ai-citation-clues (09.03.2026)

12. **Messen geht nur teilweise.** Search Console hat seit 03.06.2026 einen Generative-AI-Bericht (alle Websites seit 31.08.2026): nur Impressionen, AI Overviews und AI Mode zusammen, ohne Klicks und Suchanfragen. Dazu der Schalter "Search generative AI control" (Property-Ebene). Bing Webmaster Tools: AI Performance (Copilot, 10.02.2026). Rankings in KI-Antworten sind nach SparkToro kaum reproduzierbar. [P] + [S]
    https://developers.google.com/search/blog/2026/06/gen-ai-performance-reports
    https://support.google.com/webmasters/answer/16908024?hl=en-GB
    https://blogs.bing.com/webmaster/February-2026/Introducing-AI-Performance-in-Bing-Webmaster-Tools-Public-Preview

---

## 1. GEO / KI-Sichtbarkeit

### 1.1 Was Google offiziell sagt [P]

Quellen: https://developers.google.com/search/docs/appearance/ai-features (ohne Datum auf der Seite); https://developers.google.com/search/docs/fundamentals/ai-optimization-guide (ohne Datum; Veröffentlichung 15.05.2026 laut Blog); Changelog https://developers.google.com/search/updates.

- Keine zusätzlichen Anforderungen und keine Sonderoptimierungen für AI Overviews/AI Mode. Seite muss indexiert und snippet-fähig sein; Crawling in robots.txt/CDN erlauben, interne Verlinkung, Seitenerlebnis, textbasierter Inhalt, aktuelle Merchant-Center- und Business-Profile-Daten.
- AI Overviews erscheinen nur, wenn sie laut Google "additiv" zur klassischen Suche sind. AI Mode und AI Overviews können unterschiedliche Modelle und Techniken nutzen, deshalb abweichende Links.
- Query Fan-out: mehrere verwandte Suchen parallel zu Teilthemen; dadurch breitere Linkmenge als in der klassischen Suche.
- Mythen laut Google (Leitfaden, Abschnitt "Myths"): llms.txt und "spezielle" Dateien/Markup (Google Search nutzt sie nicht; Changelog 15.06.2026), Zerlegen in kleine Häppchen, "für KI umschreiben", künstliche Erwähnungen im Web, Überfokus auf Strukturierte Daten. "Es gibt keine ideale Seitenlänge."
- Empfohlen: eigener, nicht austauschbarer Inhalt mit Erfahrung/Expertise; klare Struktur mit Absätzen und Überschriften; relevante Bilder/Video; Semantic HTML (empfohlen, nicht nötig).
- Spam-Policy gilt auch für KI-Antworten (Changelog 15.05.2026). Seiten nur für Abfragevarianten oder Fan-out-Anfragen können gegen Scaled Content Abuse verstoßen.
- Misstrauen gegenüber Drittanbieter-Tools, die Ranking-Erfolg oder Einblick in Google-Interna versprechen (Leitfaden; Changelog 05.06.2026 "third-party SEO tools and advice"; die Detailseite selbst konnte ich nicht öffnen, 404).
- Controls: nosnippet, data-nosnippet, max-snippet, noindex; Google-Extended für Training/Grounding in anderen Google-Systemen.

### 1.2 Verfügbarkeit Deutschland/DACH Stand 2026

| Aussage | Beleg | Stufe |
|---|---|---|
| AI Overviews ("Übersicht mit KI") Start in Deutschland ab Nacht auf 26.03.2025 mit acht weiteren europäischen Ländern; nur angemeldete Nutzer ab 18; zunächst keine Anzeigen in den Übersichten | https://t3n.de/news/?p=1679953 | [S] Fachpresse, keine Google-Primärquelle |
| AI Mode: Google-Blog 07.10.2025: mehr als 35 neue Sprachen, mehr als 40 neue Länder, insgesamt über 200; "viele in Europa" (Länder im Blog nicht aufgelistet) | https://blog.google/products/search/ai-mode-expands-languages-locations/ | [P] |
| AI-Mode-Hilfeseite führt Deutschland unter Europa/Nahost/Afrika und "German" als Sprache; Seite ohne Datum, Footer 2026 | https://support.google.com/websearch/answer/16011537?hl=en | [P] |
| Deutschsprachiger AI Mode ab ca. 07./08.10.2025 | https://onlinemarketing.de/technologie/google-search-ai-mode-startet-in-deutschland (08.10.2025; Leserkommentar: anfangs noch nicht nutzbar) | [S] |
| Österreich und Schweiz im AI Mode | Nur Suchtreffer-Zusammenfassung (Futurezone, tt.com, onlinemarketing), nicht geöffnet | [nv] |
| Anzeigen im AI Mode: Deutschland fehlt bei Ausweitung vom 28.10.2026; gesponserte Einträge in KI-Antworten laut Ads-Hilfe nur Englisch | Suchtreffer-Zusammenfassung, Google-Seiten nicht geöffnet | [nv] |

Hinweis: Die Hilfeseite erwähnt Modellvarianten mit abweichenden Ländermengen (laut Zusammenfassung ist Deutschland bei einer Variante nicht gelistet). Details nicht geprüft; vor Planungsentscheidung die Hilfeseite direkt lesen.

Verbreitung in Deutschland (SISTRIX, Anbieterdaten [S]):
- 06.11.2026: AI Overview bei 57,9 % der beobachteten deutschen Keywords. Meilensteine: 10 % am 10.06.2025, 20 % am 15.11.2025, 30 % am 10.07.2026, 40 % am 11.09.2026, 50 % am 02.11.2026. Zählt Keywords, nicht Suchvolumen; Stichprobengröße nicht genannt; keine Aufteilung nach Kaufabsicht. https://www.drweb.de/google-ai-overviews-haelfte-keywords/ (06.11.2026). SISTRIX-Original nicht geöffnet.
- 17.03.2026 (SEJ über SISTRIX, über 100 Mio. deutsche Keywords): Klickrate Position 1 27 % ohne, 11 % mit AI Overview; ca. 265 Mio. verlorene organische Klicks pro Monat; Shopping- und Reiseseiten "kaum betroffen", Baby-/Elternseiten über 24 % Klickverlust. Unklar, ob der deutsche Wert echte Marktunterschiede oder Methodik zeigt. https://www.searchenginejournal.com/google-ai-overviews-cut-germanys-top-organic-ctr-by-59/
- Der Prozentwert vom Februar/März 2026 (20 %) und der vom November 2026 (57,9 %) sind nicht gleich definiert verglichen; beide Anbieterdaten.

### 1.3 Wie wählen die Systeme Quellen? (belegt vs. offen)

**Google AI Overviews / AI Mode**
- [P] Basis ist Googles Kernsuche mit Fan-out (siehe 1.1). Keine weiteren Kriterien offiziell.
- [S] Überschneidung mit Top 10: Ahrefs, Update 02.03.2026 (Louise Linehan; 863.000 Keyword-SERPs, ca. 4 Mio. AI-Overview-URLs, Ahrefs Brand Radar): 37,9 % in den Top-10-Blöcken, 31,2 % auf Plätzen 11-100, 31,0 % jenseits 100. Reine Blue-Links-Version: 37,1 / 26,2 / 36,7 %. Frühere Zahl 76 % (Juli 2025) nicht vergleichbar, weil Parsing geändert. YouTube war 5,6 % aller zitierten URLs und 18,2 % der Zitate jenseits Platz 100. Fan-out-Queries wurden nur über Drittwerkzeuge simuliert; Google legt sie nicht offen. https://ahrefs.com/blog/ai-overview-citations-top-10/
- [S] Andere Studie (BrightEdge, ca. 17 % Überschneidung) nur als Suchtreffer-Hinweis, [nv].
- [S] Stabilität: Seiten mit Google-Ranking hatten ca. 7-fach höhere Chance, mindestens eine Woche zitiert zu bleiben (28-29 % vs. 4 %); DR zeigte wenig Zusammenhang (Ahrefs 29.10.2026). https://ahrefs.com/blog/how-stable-are-ai-citations/

**Markenerwähnungen**
- [S] Ahrefs (Veröffentlichung 26.05.2025, ca. 75.000 Marken, Spearman, nur Domains mit DR über 40 und Top-Keyword mit mindestens 800 Suchen/Monat): Marken-Web-Erwähnungen 0,664, Markenanker 0,527, Marken-Suchvolumen 0,392, DR 0,326, Backlinks 0,218 Korrelation mit AI-Overview-Markennennungen. Korrelation, nicht Ursache. Google nennt künstliche Erwähnungen ausdrücklich nutzlos. https://ahrefs.com/blog/ai-overview-brand-correlation/
- Der oft zitierte YouTube-Wert 0,737 (Dezember 2025) ist [nv] (nur Sekundärzusammenfassung).

**ChatGPT Search**
- [P] OpenAI-Bot-Doku: OAI-SearchBot steuert die Aufnahme in ChatGPT-Suchantworten (robots.txt und IP-Bereiche erlauben); GPTBot ist Training; ChatGPT-User ist nutzergesteuert. robots.txt-Änderungen wirken nach ca. 24 Stunden. https://developers.openai.com/api/docs/bots
- [P-nv] OpenAI-Hilfecenter (Publisher-FAQ) war per WebFetch nicht abrufbar (403). Aus Suchtreffer-Zusammenfassung: jede öffentliche Seite kann erscheinen; Verweise tragen utm_source=chatgpt.com [nv].
- [S] Seer Interactive, 06.02.2025 (Christina Blake, Alisa Scharf): ca. 500 Zitate aus ca. 100 Fragen; 87 % der Zitate in Bings Top 20, Google 56 %; Autoren nennen es "richtungsweisend", Fragen enthielten oft "best/top". Älter als ein Jahr. https://www.seerinteractive.com/insights/87-percent-of-searchgpt-citations-match-bings-top-results
- [nv] Search-Engine-Land-Fallstudie (Hotel, 68 Wiederholungen) zu Bing-Ranking und ChatGPT-Nennungen: nur über Suchtreffer bekannt.
- [S] Frische: Ahrefs 28.07.2025, ca. 17 Mio. zitierte URLs: KI-zitierte URLs im Mittel 1.064 Tage alt gegenüber 1.432 Tagen bei organischen Ergebnissen (25,7 % "frischer"); ChatGPT zeigt die stärkste Präferenz für Neues, Google die geringste. Zitierte Inhalte sind trotzdem im Mittel ca. 2,9 Jahre alt. https://ahrefs.com/blog/do-ai-assistants-prefer-to-cite-fresh-content
- [M/nv] Zitat-Halbwertszeit 4,5 Wochen und "13-Wochen-Regel": nur Sekundärblogs, nicht geöffnet.

**Perplexity**
- [P] Perplexity-Bot-Doku nennt PerplexityBot (Aufnahme in Suchergebnisse; kein Modelltraining) und Perplexity-User (nutzergesteuert, ignoriert robots.txt weitgehend); Änderungen bis 24 Stunden. Die Seite beschreibt keine Kriterien für Ranking oder Zitierwahl. https://docs.perplexity.ai/guides/bots
- Alles Weitere über Perplexity-Auswahlkriterien ist [M/nv].

**Microsoft Copilot / Bing**
- [P] Microsoft Advertising Blog 06.01.2026 "From discovery to influence": Produktfeeds, gecrawlte Daten und Off-Site-Daten sind drei Datenwege; Vollständigkeit der Produktdaten wird betont (Zusammenfassung; Strukturierte-Daten-Aussagen in der Blogseite nicht ausdrücklich). https://about.ads.microsoft.com/en/blog/post/january-2026/from-discovery-to-influence-a-guide-to-geo
- Detailaussagen aus dem PDF-Leitfaden zu Schema: nur Sekundärzusammenfassung [nv].

**Reddit, Foren, YouTube, Quellenmix**
- [S] Peec AI (31.03.2026, ca. 30 Mio. Quellen, USA, alle fünf Plattformen; Prompts, Zeitraum, Sprache nicht angegeben; Anbieter verkauft Monitoring): Gesamt-Top 10: Reddit, YouTube, LinkedIn, Wikipedia, Forbes, G2, Yelp, Facebook, Medium, TechRadar. Reddit und YouTube in allen fünf Top-Listen. Google-Plattformen bevorzugen Social-Quellen, ChatGPT eher redaktionell/Wikipedia. Branchenabhängig. **Nur USA, nicht auf Deutschland übertragbar.** https://peec.ai/blog/top-domains-cited-by-ai-search-analysis-based-on-30m-sources
- [S] SISTRIX 31.08.2025: Reddit erreichte Platz 13 der sichtbarsten Domains in Deutschland (Sekundär: https://ppc.land/ai-overviews-now-trigger-on-17-of-german-keywords-as-reddit-climbs-rankings/); ältere Daten, AIO damals 17 % der Keywords.
- Bewertung: Für einen deutschen Technik-Shop ist belegt, dass Fremdquellen (Foren, Videos, Fachportale) in KI-Antworten oft zitiert werden; wie stark das für deutsche, erklärungsbedürftige B2B-Produkte gilt, ist nicht belegt.

**GEO-Paper**
- [S] Aggarwal et al. (Princeton, IIT Delhi, Georgia Tech), arXiv 2311.09735, v1 16.11.2023, v3 28.06.2024, KDD 2024: "GEO" kann Sichtbarkeit in Antworten generativer Maschinen um bis zu 40 % steigern; wirkt je nach Fachgebiet unterschiedlich; Benchmark GEO-bench. Methodenzahlen (z. B. +41 % Zitate) in Sekundärblogs widersprechen sich, [nv]. Wegen Alter (Modelle 2023) und Black-Box-Setup nicht auf Google AI Mode 2026 übertragbar. https://arxiv.org/abs/2311.09735

### 1.4 llms.txt und "GEO-Schema"

- [P] Google: nicht genutzt (Changelog 15.06.2026; Leitfaden). Schädlich ist es nicht, "für andere Dienste" unbedenklich.
- [S] SE Ranking (Seite zeigt Byline 15.10.2026; SEJ-Bericht 20.11.2025, ca. 300.000 Domains, 10,13 % mit Datei): keine Korrelation, Modell wird ohne die Variable besser. Korrelativ. https://seranking.com/blog/llms-txt/
- [nv] Server-Log-Studien (Ahrefs: 97 % der Dateien ohne Abrufe) nur aus Suchtreffer.
- "GEO-Schema" / spezielles Markup für KI: [P] Google verlangt keins; [S] Ahrefs-Studie ohne messbaren Effekt; [nv] searchVIU-Experiment (Okt. 2025), dass KI-Systeme beim Abruf nur sichtbaren HTML-Text lasen (aus der Ahrefs-Seite zitiert, Original nicht geöffnet).

### 1.5 Shop-Besonderheiten

- [P] Google-Leitfaden: Merchant Center und Produktfeeds machen Produkte in KI-Antworten und anderen Suchergebnissen sichtbar; "Business Agent" als Chat-Option; Browser-Agenten lesen Seiten per Screenshot, DOM und Accessibility-Tree (web.dev-Hinweis; die genannte web.dev-URL gab 404, Inhalt nicht geprüft); UCP "erwartet" mehr Agentenfähigkeit.
- [P] Google Marketing Live, 20.05.2026: Universal Cart, UCP-Checkout, Händler bleibt Merchant of Record; UCP-Checkout geplant für Kanada und Australien, später UK; "AI performance insights" im Merchant Center zunächst Australien, Kanada, Indien, Neuseeland, USA; "Conversational attributes" für Händler weltweit. Kein Wort zu Europa/Deutschland. https://blog.google/products-and-platforms/products/shopping/shopping-updates-google-marketing-live
- [P] Merchant-Center-Änderungsprotokoll (Auszug): Produktdatenspezifikation 2026 ab 14.04.2026 (Handling-Cutoff, Mindestbestellwert); Abholkosten und Mindestbestellwert ab 30.09.2026 Pflicht in EWR inkl. Deutschland (nur für Händler mit Abholung relevant); Shopping-Richtlinien im September 2026 zusammengelegt. https://support.google.com/merchants/answer/13863814?hl=en
- [P] Google-Dokumentation für Händler: KI-generierte Produkttitel/-beschreibungen im Feed müssen getrennt als KI-generiert gekennzeichnet werden; KI-Bilder mit IPTC DigitalSourceType. https://developers.google.com/search/docs/fundamentals/using-gen-ai-content
- [nv] Shopping Graph speist AI Mode vor allem über Merchant-Center-Feeds; Merchant Center nicht als direktes Ranking-Signal bestätigt (Suchtreffer-Zusammenfassung). Channable-Auswertung Okt. 2026 (77 % der Feeds mit Lücken) nur Sekundär.
- [nv] ChatGPT Instant Checkout/ACP: US-Start September 2025, Ausweitung auf alle US-Nutzer Februar 2026; kein bestätigter Start in Deutschland; OpenAI-Seiten nicht abrufbar. Microsoft "Copilot Checkout/Brand Agents" ebenfalls nur Teaser gesehen.
- [S] SISTRIX/SEJ 17.03.2026: Shopping-Seiten kaum von AIO-Klickverlusten betroffen (siehe 1.2). Semrush-US-Test (400 Keywords, Okt. 2026): 88 % der kaufnahen Anfragen mit AIO, nur Sekundärbericht, nicht auf Deutschland übertragbar.

---

## 2. SERP-Merkmale 2026 und Folgen für die Methode "Top-Ergebnisse analysieren"

### 2.1 Zeitleiste der Streichungen und Änderungen

| Datum | Änderung | Quelle | Stufe |
|---|---|---|---|
| 08.08.2023, Update 14.09.2023 | FAQ-Rich-Results nur noch für bekannte Behörden-/Gesundheitsseiten; HowTo-Rich-Results abgeschafft (zuerst nur Desktop, dann ganz ab 13.09.2023) | https://developers.google.com/search/blog/2023/08/howto-faq-changes | [P] |
| 21.11.2024 | Sitelinks-Suchfeld entfernt, Ranking unberührt, Site-Name-Markup bleibt | https://developers.google.com/search/blog/2024/10/sitelinks-search-box | [P] |
| 22.01.2025 | Hinweis: Breadcrumb-Markup erscheint nur auf Desktop | Changelog; Breadcrumb-Doku nennt nur Desktop | [P] |
| 12.06.2025 | "Simplifying search results": Book Actions, Course Info, Claim Review, Estimated Salary, Learning Video, Special Announcement, Vehicle Listing auslaufend; Ranking unverändert; ab 09.09.2025 aus Berichten/Rich-Results-Test | https://developers.google.com/search/blog/2025/06/simplifying-search-results | [P] |
| 05.11.2025 | Practice-Problem-Markup abgekündigt; Dataset-Markup nur noch Dataset Search | Changelog | [P] |
| ca. 08.-12.09.2025 | `num=100` wirkt nicht mehr: 10 Ergebnisse je Seite; Search-Console-Impressionen und Durchschnittsposition verschieben sich; Rank-Tracker verteuert. Google soll laut Berichten gesagt haben, der Parameter sei nie formal unterstützt gewesen. Keine Google-Doku. | Botify https://www.botify.com/blog/googles-removes-num-100 (Daten eines Anbieters; ca. 30-40 % "synthetischer Abschlag" ist deren Vorschlag); Zitat des Google-Sprechers nur [nv] | [S]/[nv] |
| 07.05.2026 | FAQ-Rich-Result erscheint gar nicht mehr; Hinweis 08.05.2026; Doku am 15.06.2026 entfernt | Changelog | [P] |
| 06.01.2026 | Practice-Problem-Doku entfernt | Changelog | [P] |
| 13.04.2026 | Neue Spam-Policy "Back Button Hijacking" | Changelog | [P] |
| 01.07.2026 | AMP-Doku vereinfacht | Changelog | [P] |
| 24.07.2026 | Neue Review-Snippet-Richtlinie gegen gefälschte/nicht offengelegte incentivierte Bewertungen | Changelog; Inhalt in https://developers.google.com/search/docs/appearance/structured-data/review-snippet | [P] |
| 28.08.2026 | Site-Reputation-Policy: angepasste Durchsetzung im EWR | Changelog | [P] |
| 08.09.2026 | Neue Doku "Regional differences in Search experience": Aggregator-/Lieferanten-Einheiten im EWR (Produkte, Hotels, Flüge u. a.) | https://developers.google.com/search/docs/appearance/aggregator-features | [P] (Teilnahmebedingungen dort nicht erkennbar) |

Hinweis: Das Changelog meldet für 2026 keine Entfernung von Product-/Merchant-Listing-Markup. Es gibt ergänzende Änderungen (Product.category, Verkaufsdauer 07.07.2026; hasAdultConsideration 20.05.2026; VideoObject creator 24.09.2026).

### 2.2 Aktuelle SERP-Elemente laut Google-Dokumentation

- [P] Dokumentierte Elemente: Textergebnis (Titel, Snippet, Sitelinks, Byline-Datum, Text-Ergebnisbild, Rich Attributes), Rich Result, Bild, Video, "Exploration Features" (Verwandte Suchen, Verwandte Fragen). Darstellung hängt von Gerät, Land und Sprache ab. https://developers.google.com/search/docs/appearance/visual-elements-gallery
- [P] Rich-Result-Galerie (Strukturierte Daten, 25 Einträge): u. a. Article, Breadcrumb, Carousel, Discussion forum, Event, Image metadata, Job posting, Local business, Organization, Product, Profile page, Q&A, Recipe, Review snippet, Software app, Speakable, Video. Kein FAQ, kein HowTo. https://developers.google.com/search/docs/appearance/structured-data/search-gallery
- [P] Im EWR gibt es Aggregator- und Lieferanten-Einheiten für Produktanfragen (Wettbewerbsrecht, DMA). Das beeinflusst, was auf google.de bei kommerziellen Anfragen sichtbar ist und ist bei SERP-Analysen zu beachten.
- [P] "Preferred sources" (Top Stories): seit 30.01.2026 dokumentiert, in allen Sprachen ab 30.04.2026, in AI Overviews/AI Mode ab 27.05.2026 (Changelog). Für Shop-Inhalte kaum relevant.
- AI Overviews/AI Mode: Position bei ca. 79 % der deutschen AIOs oberhalb der organischen Ergebnisse (SISTRIX/SEJ, [S]).
- Welche Features genau bei kommerziellen deutschen Anfragen auftauchen (Shopping-Einheit, PAA, Produktkarussell), konnte ich nicht aus Primärquelle belegen; siehe Abschnitt "Nicht geklärt".

### 2.3 Folgen für die Methode "Top-Ergebnisse analysieren, Seitenaufbau ableiten"

Aus belegten Fakten, mit Bewertung:
- [P/S] Rich-Result-Merkmale der Top-Treffer sind heute kein verlässlicher Hinweis mehr auf "was belohnt wird": FAQ/HowTo weg, andere Typen eingeschränkt. Nach Markup-Typen der Wettbewerber zu bauen, führt zu Markup ohne sichtbaren Effekt.
- [S] Die Überschneidung zwischen klassischen Top-10 und KI-Zitaten liegt bei ca. 38 % (Ahrefs 2026), und die KI-Zitate wechseln; die Top-10-Analyse liefert also nur einen Teil der Konkurrenz in KI-Antworten. Fan-out-Teilfragen werden nicht offengelegt.
- [P] Google sagt selbst, dass das System Seiten auch ohne exakte Keyword-Übereinstimmung zuordnet; die Gleichung "Wettbewerber-Struktur kopieren" kann dadurch ins Scaled-Content- und Commodity-Risiko laufen.
- [S] Search-Console-Daten ab 11.09.2025 sind wegen num=100 nicht mehr direkt mit früheren Impressions- und Positionswerten vergleichbar (Anbieterdaten; Annotation empfohlen).
- Bewertung (Branchenmeinung, aus den Belegen abgeleitet): Top-Ergebnisse analysieren bleibt als Intent- und Format-Check (Seitentyp, Suchintention, Lücken) brauchbar, nicht als Schablone für Aufbau und Markup.

---

## 3. Seitenschemas / Strukturierte Daten für Shops je Seitentyp

Grundsätze [P]: Markup muss zum sichtbaren Inhalt passen; JSON-LD wird empfohlen; Erscheinen als Rich Result ist nicht garantiert. https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data

### 3.1 Matrix: Google-Unterstützung, Rich-Result-Wirkung, Risiko, RankMath/WooCommerce

Legende Wirkung: **RR** erzeugt Rich Result oder Darstellung, **V** nur Verständnis (kein garantierter Effekt), **0** kein Effekt in Google-Suche mehr.

| Typ | Seitentyp | Google-Status (Stand 2026) | Wirkung | Risiko / Policy | RankMath / WooCommerce |
|---|---|---|---|---|---|
| Product (Merchant listing) | Produktseite | Unterstützt: Pflicht name, image, offers = einzelnes Offer (kein AggregateOffer), price, priceCurrency; empfohlen availability, itemCondition, hasMerchantReturnPolicy, shippingDetails, gtin/mpn/brand, aggregateRating, review. Nur kaufbare Einzelprodukte (oder Varianten mit eigener URL); je Währung eigene URL. Kategorie-/Listenseiten ausdrücklich nicht unterstützt. Merchant-Center- und Search-Console-Einstellungen haben Vorrang vor Markup. [P] | RR (Händlerlisting/Produktdarstellung, nicht garantiert) | Markup ohne passende sichtbare Preise/Verfügbarkeit; Preisabweichungen zum Feed | WooCommerce-Kern erzeugt Product-JSON-LD auf Einzelproduktseiten; RankMath erkennt WooCommerce und ergänzt Product automatisch [P] |
| Product snippet | Produktseite ohne Kaufmöglichkeit (z. B. reine Info-/Herstellerseite) | Unterstützt, mehr Optionen für Redaktionsbewertung (Pro/Contra) [P] | RR (Bewertungssterne u. ä.) | Self-serving-Regel bei Organisation/LocalBusiness | RankMath: Pros/Cons nicht für WooCommerce-Produkte, nur redaktionelle Review-Seiten [P] |
| ProductGroup / Varianten | Produktseite mit Varianten | Unterstützt: ProductGroup (name Pflicht), variesBy, hasVariant oder isVariantOf, productGroupID; jede Variante eigene URL mit vorgewählter Variante; bei mehreren Seiten Markup auf jeder Seite wiederholen [P] | RR (Variantenanzeige im Listing) | JS-generiertes Markup wird evtl. seltener gecrawlt | WooCommerce-Kern: ProductGroup nicht belegt (Code gesichtet: Product mit Offer/AggregateOffer); bei variablen Produkten ohne gewählte Variante AggregateOffer (kein gültiges Merchant-Listing-Offer) [P Code, trunk, Datum unbekannt] |
| ItemList / Carousel | Kategorie, Übersichten | Google-Carousel nur mit Kursen, Filmen, Rezepten, Restaurants dokumentiert; für Produktlisten nicht dokumentiert. Bedingungen: mindestens zwei ListItem, gleicher Typ [P] | 0 für Produktkategorien (nicht belegt, dass Google sie auswertet), V möglich | Kein Policy-Risiko erkennbar, aber auch kein belegter Nutzen | RankMath: ItemList und Carousel nur PRO; Kategorien erhalten automatisch CollectionPage [P] |
| BreadcrumbList | alle Seitentypen | Unterstützt, nur Desktop [P] | RR (Desktop) | Gering | WooCommerce-Kern (BreadcrumbList) und RankMath Breadcrumb Schema (kostenlos) [P]; Doppelausgabe möglich |
| Article / BlogPosting | Ratgeber, Referenzbeitrag | Unterstützt; keine Pflichtfelder; hilft bei Titel, Bild, Datum; Autor mit url/sameAs empfohlen [P] | V / begrenzte Darstellung | Gefälschte Autoren (Helpful-Content-Regeln) | RankMath: Article/BlogPosting/NewsArticle kostenlos, Standard für Beiträge [P] |
| Organization (OnlineStore) | Startseite/Über uns | Unterstützt; keine Pflichtfelder; Logo, sameAs, Kontakt; hasMerchantReturnPolicy und hasShippingService auf Organisationsebene empfohlen [P] | RR (Logo, Wissensfeld, Händlerprofil), V | Falsche Angaben, Self-serving-Bewertungen | RankMath Person/Organization und Local SEO kostenlos; WooCommerce-Kern erzeugt OnlineStore mit Rückgaberegel (Code) [P] |
| LocalBusiness | Standort/Kontakt | Unterstützt; Bewertungen der eigenen Firma nicht für Sterne qualifiziert (Self-serving) [P] | RR | Self-serving-Regel | RankMath Local SEO kostenlos [P] |
| Review / AggregateRating | Produkt, nicht Kategorie | Unterstützt für Product u. a.; nur Bewertungen zu einem Gegenstand (nicht Kategorie/Liste); AggregateRating nur auf der Seite sichtbar und nicht von anderen Websites aggregiert; keine gefälschten oder nicht offengelegten incentivierten Bewertungen (neue Richtlinie 24.07.2026) [P] | RR (Sterne) | Hoch: eigene Firmenbewertungen auf Organization/LocalBusiness (Self-serving), importierte Fremdbewertungen, Bewertungen ohne sichtbaren Text | WooCommerce: aggregateRating und bis zu fünf Reviews im Product-JSON-LD, nur wenn Bewertungen aktiv sind [P Code] |
| FAQPage | beliebig | Google-Rich-Result seit 07.05.2026 beendet, Doku entfernt; schema.org-Typ besteht weiter [P] | 0 in Google; V/unbelegt für KI | Kein Policy-Risiko, aber kein belegter Nutzen; RankMath verweist selbst auf Fortbestand "für UX und KI-Plattformen" (Herstellermeinung, [M]) | RankMath: FAQ-Block kostenlos, Generator PRO [P] |
| HowTo | Ratgeber | Rich Result 2023 abgeschafft [P] | 0 | wie oben | RankMath HowTo-Block kostenlos [P]; Doku nennt Abschaffung nicht |
| Speakable | Ratgeber/News | In der Google-Galerie gelistet [P]; Aussagekraft für deutsche Shop-Inhalte nicht belegt | unklar | gering | RankMath PRO [P] |
| Q&A / Discussion forum | Nutzerinhalte | Unterstützt für Nutzerforen/Q&A-Seiten (Erweiterung 24.03.2026) [P] | RR | Nicht für Herstellerseiten mit eigener FAQ | RankMath Q&A PRO [P] |
| WebSite | Startseite | Sitelinks-Suchfeld abgeschafft (21.11.2024); Site-Name-Markup bleibt [P] | V (Site-Name) | gering | RankMath und WooCommerce erzeugen WebSite mit SearchAction (nutzlos für Google-Suchfeld, schadet nicht) [P] |
| Merchant-Policies | Organisation/Produkt | Versand und Rückgabe auf Organisationsebene empfohlen, Produktebene zum Überschreiben; Merchant-Center-Einstellungen schlagen Markup [P] | RR | Inkonsistenz Markup/Feed/Seite | WooCommerce-Kern: shippingDetails nur bei vorhandenen Versanddaten; OnlineStore mit MerchantReturnPolicy; AggregateOffer ohne shippingDetails [P Code] |

### 3.2 Zusammenfassung nach Seitentyp (Empfehlung auf Basis der Belege, nicht Googles Wortlaut)

- **Produktseite**: Product mit einzelnem Offer, GTIN/MPN, Brand, Versand/Rückgabe auf Organisationsebene, ProductGroup bei Varianten mit eigener URL; Bewertungen nur, wenn echte, sichtbare Kundenbewertungen vorhanden.
- **Kategorieseite**: Kein Merchant-Listing-Markup auf der Kategorieseite selbst (Google schließt Listenseiten aus). CollectionPage (RankMath automatisch) und BreadcrumbList genügen. Product-Markup nicht auf Listenseiten duplizieren.
- **Landingpage**: Je nach Zweck WebPage/Service/Product; Product nur wenn kaufbar. Kein belegter Mehrwert durch ergänzende Typen.
- **Ratgeber/Blog**: Article/BlogPosting mit Autor (Person, url/sameAs), Datum; BreadcrumbList. FAQ/HowTo für Rich Results nicht mehr.
- **Referenz-/Projektbeitrag**: Article oder BlogPosting; Bewertungen/Kundenaussagen nicht als Review der eigenen Organisation markieren (Self-serving-Regel).
- **Organisation**: Organization/OnlineStore auf Startseite oder Über-uns, mit sameAs, Logo, Kontakt, Versand/Rückgabe.
- **Für KI**: [P] Google verlangt kein Markup; [S] Ahrefs-Studie ohne Effekt. Markup als Verständnishilfe ist unschädlich, aber ohne Wirkungsnachweis.

### 3.3 Was RankMath und WooCommerce von Haus aus liefern

- [P] RankMath (Free): 29 Schematypen laut KB: u. a. Article, BlogPosting, NewsArticle, Product, Person/Organization, Local SEO, Breadcrumb, CollectionPage, WebPage, WebSite, WooCommerce-Schema, FAQ- und HowTo-Blöcke, ProfilePage. PRO: ItemList, Carousel, Q&A, Speakable, Dataset, Movie u. a., Custom Schema, mehrere Schemas je Seite, Schema-Generator für FAQ/HowTo. Datum der KB-Seite unbekannt (Footer 2026). https://rankmath.com/kb/rich-snippets/
- [P] RankMath: WooCommerce-Produktschema automatisch; Daten (Preis, Verfügbarkeit, Bewertungen) aus dem Produkt, nicht im Schema-Editor änderbar; Kategorien erhalten CollectionPage; Standard für Beiträge einstellbar (Article empfohlen). GTIN/MPN-Zusatzfelder PRO, wandern in das WooCommerce-eigene GTIN-Feld (Versionsangabe fehlt auf der Seite). https://rankmath.com/kb/gtin-mpn-woocommerce/
- [P] WooCommerce-Kern (Quellcode class-wc-structured-data.php, trunk, Datum nicht festgestellt): Product mit Offer/AggregateOffer, Reviews (bis 5), aggregateRating, GTIN-Prüfung (8, 12-14 Ziffern), MPN, BreadcrumbList, WebSite, OnlineStore mit Rückgabepolitik, Order (E-Mails). Preis über UnitPriceSpecification, priceValidUntil Ende nächsten Jahres als Standard. Beim variablen Produkt ohne gewählte Variante AggregateOffer ohne Versanddetails.
- [nv] Dubletten-Risiko: Wenn WooCommerce-Kern und SEO-Plugin beide Product ausgeben, entstehen zwei JSON-LD-Graphen. Nur aus Blog-Zusammenfassung. Im konkreten Shop mit Rich Results Test prüfen.
- Folge für den Shop: Die Merchant-Listing-Anforderung "einzelnes Offer" und Versand/Rückgabe sind bei variablen WooCommerce-Produkten ein konkreter Prüfpunkt (Quelle: Google-Doku plus Code, daraus abgeleitet).

---

## 4. Seitenaufbau-Best-Practices (Inhalt) für Ranking und KI-Zitierung

### 4.1 Belegt durch Google [P]

- Helpful Content / people-first: Originalinformation, Analyse, Erfahrung aus erster Hand, vollständige Abdeckung statt umgeschriebener Zusammenfassungen; Autorenangabe mit Link zu Autoreninfo; Offenlegung der Erstellungsweise (inkl. KI), wo Leser sie erwarten; Warnzeichen: Massenproduktion, Datum ändern ohne inhaltliche Änderung. https://developers.google.com/search/docs/fundamentals/creating-helpful-content
- Trust ist der wichtigste Teil von E-E-A-T; erhöhte Strenge nur bei Themen zu Gesundheit/Finanzen/Sicherheit (YMYL). Für einen Technikshop mit sicherheitsrelevanten Produkten ist YMYL-Nähe im Einzelfall zu prüfen (Bewertung, nicht Google-Aussage).
- Leitfaden KI-Features: nicht austauschbarer Inhalt, klare Struktur mit Überschriften, keine ideale Länge, kein Chunking, kein Umschreiben "für KI", Bilder/Video ergänzend. https://developers.google.com/search/docs/fundamentals/ai-optimization-guide
- Generative-KI-Inhalte: erlaubt, aber ohne Mehrwert in Masse = Scaled Content Abuse; Fakten prüfen; Titel, Meta-Beschreibungen, Strukturierte Daten und Alt-Texte ebenso; Hinweis auf Search Quality Rater Guidelines Abschnitte 4.6.5 (Scaled Content Abuse) und 4.6.6 (geringer Aufwand/Originalität). Changelog 01.10.2026: Seite mit Rater-Informationen aktualisiert; Rater-Bewertungen beeinflussen das Ranking nicht direkt. https://developers.google.com/search/docs/fundamentals/using-gen-ai-content
- Spam-Policy Scaled Content Abuse: gilt unabhängig von der Methode; Beispiele: KI-Massenseiten ohne Mehrwert, Scraping von Feeds mit Synonymen/Übersetzung, Zusammenkleben fremder Inhalte. https://developers.google.com/search/docs/essentials/spam-policies

### 4.2 Belegt durch Studien [S] (alle mit Eigeninteresse und Einschränkungen)

- **Position der zitierten Passage**: Kevin Indig, Growth Memo 16.02.2026 (Original hinter Paywall, Zahlen nicht selbst geprüft): 1,2 Mio. ChatGPT-Ergebnisse, 18.012 Zitate; ca. 44 % aus dem ersten Drittel (30 %) des Textes. Sekundär Practical Ecommerce 09.03.2026: dort 44,3 %; zusätzlich Bright Data/D. Shashko: 42.971 Zitate, 520 Anfragen, sechs Plattformen; bei AI Mode und Gemini 74,8 % in der ersten Seitenhälfte, 46,1 % im ersten Drittel; rund 70 % der AI-Mode-/Gemini-Zitate mit Textfragment-Link auf den zitierten Satz; 92,4 % der Zitate sind Sätze mit 6-20 Wörtern. Original-Studien nicht geöffnet, [nv] für Einzelzahlen. https://www.practicalecommerce.com/studies-reveal-ai-citation-clues
- Das stützt: wichtigste Aussage früh, eigenständig verständliche Sätze. Google sagt zugleich, man müsse nicht "chunken" (Leitfaden) und Danny Sullivan riet von "Häppchen-Content" ab (Berichte Januar 2026, [nv] Podcast nicht geöffnet). Beides ist vereinbar als: klare Absätze ja, künstliche Zerlegung nein.
- **Frische**: siehe 1.3 (Ahrefs 28.07.2025). Mueller warnt (laut Ahrefs) vor reinen Datumsänderungen.
- **Markenerwähnungen/Fremdquellen**: siehe 1.3; für DE nicht belegt.
- **Tabellen, Originaldaten, Statistiken, Zitate**: Das GEO-Paper nennt Zitate/Statistiken als wirksamer; Einzelzahlen nicht verifiziert (1.3). Eigenständige Studien zu Tabellen konnte ich nicht belegen.
- **Antwort-zuerst (Answer-first)**: indirekt durch Positionsstudien gestützt; Google formuliert es nicht als Regel. Als Praxisempfehlung zulässig, als Rankingfaktor nicht belegt.

### 4.3 Seitentyp-Hinweise (abgeleitet, Branchenmeinung/Praxis, nicht als Google-Aussage)

- **Produktseite**: eindeutige Produktdaten (Bezeichnung, Kennzahlen, GTIN), Kernaussage und Einsatzgrenzen oben, Datenblatt/Tabelle mit Messwerten, Versand/Rückgabe konsistent mit Feed und Markup, echte Bewertungen, Autor/Prüfer bei beratungsintensiven Produkten.
- **Kategorieseite**: kurzer Einleitungstext mit Auswahlkriterien, Produktliste, Vergleich oder Auswahlhilfe; keine Massen-Variantenseiten (Scaled-Content-Risiko); Fan-out-Varianten nicht als eigene Seiten anlegen (Google).
- **Landingpage**: ein Zweck, Nutzenaussage zuerst, belegte Eigenschaften, klare nächste Schritte.
- **Ratgeber**: Frage/Antwort-nahe Überschriften, Antwort im ersten Absatz, eigene Messwerte oder Erfahrungen (nicht austauschbar), Autor mit Qualifikation, sichtbares Aktualisierungsdatum nur bei echter Änderung.
- **Referenzbeitrag**: konkrete Kundensituation, Zahlen, Bilder; Bewertungs-Markup der eigenen Firma vermeiden.

---

## 5. Wissen frisch halten und Messung

### 5.1 Quellen erster Hand [P]

- Search Central Dokumentations-Changelog: https://developers.google.com/search/updates. Für 2026 enthält es 2-6 Einträge je Monat (eigene Zählung aus der Seite: Jan 3, Feb 2, Mär 3, Apr 5, Mai 4, Jun 4, Jul 6, Aug 3, Sep 4, Okt 6, Nov 2 bis 12.11.). Es ist die schnellste Primärquelle für Policy-/Markup-Änderungen und enthielt z. B. die FAQ-Abkündigung und die llms.txt-Klarstellung.
- Search Central Blog: https://developers.google.com/search/blog (2026 u. a. 15.05. KI-Leitfaden, 03.06. KI-Berichte, Oktober "Shared AI training control", August Site-Reputation-Update, 02.2026 Discover Core Update). Datumsangaben in der Listenansicht nur Monat.
- Search Status Dashboard (Ranking-Updates): https://status.search.google.com/products/rGHU1u87FJnkP6W2GwMi/history
- Merchant-Center-Änderungsprotokoll: https://support.google.com/merchants/answer/13863814
- Bing: https://blogs.bing.com/webmaster; OpenAI/Perplexity: Bot-Dokus (siehe 1.3).
- Review-Takt (Empfehlung, nicht belegt): monatlich Changelog und Blog, nach jedem Core-/Spam-Update 48 Stunden nach Ende prüfen, quartalsweise Regelwerk-Review. Keine belegte Praxisstudie dazu gefunden [M].

### 5.2 Ranking-Update-Historie laut Status Dashboard [P]

| Update | Start | Dauer |
|---|---|---|
| März 2025 Core | 13.03.2025 | 13 Tage 21 Std |
| Juni 2025 Core | 30.06.2025 | 16 Tage 18 Std |
| August 2025 Spam | 26.08.2025 | 26 Tage 15 Std |
| Dezember 2025 Core | 11.12.2025 | 18 Tage 2 Std |
| Februar 2026 Discover | 05.02.2026 | 21 Tage 17 Std |
| März 2026 Spam | 24.03.2026 | 19 Std 30 Min |
| März 2026 Core | 27.03.2026 | 12 Tage 4 Std |
| Mai 2026 Core | 21.05.2026 | 11 Tage 21 Std |
| Juni 2026 Spam | 24.06.2026 | 2 Tage 1 Std |
| August 2026 Spam | 18.08.2026 | 2 Tage 16 Std |
| September 2026 Spam | 24.09.2026 | 13 Tage 16 Std |
| November 2026 Core | 10.11.2026 | laufend/nicht angegeben |

- Zeiten laut Dashboard in US/Pacific. Die Spalte heißt "Date"; als Beginn interpretiert.
- Seit 09.12.2025 weist Google darauf hin, dass kleinere Core-Updates zwischen den großen wirken (Changelog 09.12.2025).
- Das November-2026-Core-Update begann 6 Tage vor dem Abrufdatum; das Dashboard nennt keine Dauer. Ob es abgeschlossen ist, ist nicht geprüft; Messungen und Analysen aus diesem Zeitraum sind unsicher.
- Ranking-Änderungen wie die FAQ-Abschaffung 2023 erscheinen laut Google nicht im Dashboard (Blog 2023).

### 5.3 Wie schnell veralten Analysen? (belegte Zahlen)

- [S] AI Overviews: Inhalt ändert sich bei ca. 70 % der Beobachtungen; mittlere Beständigkeit ca. 2,15 Tage (untere Schätzung, Abtastung nicht täglich); ca. 54,5 % der zitierten URLs bleiben zwischen Antworten bestehen; Suchvolumen und Änderungsrate unkorreliert; semantische Ähnlichkeit 0,95. Ahrefs 11.11.2025, über 43.000 Suchanfragen, Brand Radar. https://ahrefs.com/blog/ai-overview-change/
- [S] Zitier-Stabilität über 20 Tage (Ahrefs 29.10.2026, 37.500 Zitate, fünf Werkzeuge; Beobachtung 28.08.-04.10.2026 für einen Teilversuch): am Folgetag fehlen ca. 60 % (AI Mode, ChatGPT), 50 % (AI Overviews), 80 % (Gemini, Copilot); ca. 75 % der verschwundenen Zitate kehren zurück; 20-27 % bleiben dauerhaft weg; "Best X"-Fragen am instabilsten (64-76 % täglich wechselnde Seiten bei ChatGPT/AI Mode). https://ahrefs.com/blog/how-stable-are-ai-citations/
- [S/nv] SparkToro/Gumshoe (Fishkin/O'Donnell): identische Markenlisten bei wiederholten Anfragen unter 1 %; Stichprobenangaben in Berichten uneinheitlich; Original nicht geöffnet. Suchtreffer: https://www.searchenginejournal.com/ai-recommendations-change-with-nearly-every-query-sparktoro/
- [S] Frische des Gesamtkorpus: zitierte Inhalte im Mittel ca. 2,9 Jahre alt (Ahrefs 2025); klassische Ranking-Updates im Abstand von wenigen Wochen (Tabelle 5.2).
- Schlussfolgerung (abgeleitet): KI-bezogene Wettbewerbs-Snapshots sind nach Tagen überholt und nur als Stichprobenreihe über mehrere Läufe belastbar; klassische SERP-Analysen vor einem Core-Update gelten nur bis zum nächsten Update (4-5 große Core-/Spam-Zyklen pro Jahr 2025/2026).

### 5.4 Messmöglichkeiten 2026 und Grenzen

**Search Console (Google)** [P]
- Generative-AI-Performance-Bericht: angekündigt 03.06.2026 (Blog); laut Hinweis im Blog seit 31.08.2026 für alle Websites weltweit (Blogtext selbst sagt "Teilmenge"; Hilfeseite zur Steuerung nennt ebenfalls 31.08.2026). Zeigt Impressionen von URLs in AI Overviews und AI Mode (zusammen, nicht getrennt) und in Discover-KI; Aufteilung nach Seiten, Ländern, Geräten (nur Suche), Datum. Keine Klicks, keine CTR, laut Dritten auch keine Suchanfragen; Datenbeginn 18.05.2026 laut Sekundärquelle [nv]. https://developers.google.com/search/blog/2026/06/gen-ai-performance-reports
- Die Daten sind auch im Gesamt-Leistungsbericht (Suchtyp "Web") enthalten (AI Mode seit 16.06.2025 laut Changelog). https://developers.google.com/search/docs/appearance/ai-features
- Steuerung "Search generative AI control": Property-Ebene; ausgeschlossen = keine Links, Inhalte nicht für Grounding, keine Impressionen/Traffic aus diesen Funktionen; wirkt nicht auf Ranking sonst, nicht auf Training (dafür Google-Extended), nicht auf Merchant Center/Ads; Wirkung in 1-2 Tagen. Seitenebene fehlt; UK-CMA-Frist März 2027 für Page-Level-Kontrollen [nv, Sekundär]. https://support.google.com/webmasters/answer/16908024?hl=en-GB
- Changelog 12.11.2026: neue Seite zur Erkennung von Google-Suchtraffic über HTTP-Referer (Inhalt nicht geprüft). Frühere AI-Mode-Referrer-Probleme (Direct-Traffic) nur aus Sekundärquellen [nv].
- Search Analytics API: Aussage, der AI-Datentyp sei dort anfangs nicht gelistet gewesen, [nv] (eine Quelle).

**Bing Webmaster Tools** [P]: "AI Performance" (Public Preview ab 10.02.2026): Zitate gesamt, durchschnittlich zitierte Seiten pro Tag, Grounding-Queries (Stichprobe), Zitierte Seiten, Zeitverlauf; Microsoft nennt Grenzen: keine Position innerhalb der Antwort, keine Klicks, Grounding-Queries nur Stichprobe. Deckt nur das Microsoft-Ökosystem (Copilot, Bing-KI-Zusammenfassungen, ausgewählte Partner). https://blogs.bing.com/webmaster/February-2026/Introducing-AI-Performance-in-Bing-Webmaster-Tools-Public-Preview

**ChatGPT** [nv/P]: UTM-Parameter utm_source=chatgpt.com (OpenAI-FAQ laut Suchtreffer); keine Impressions-/Zitierdaten für Publisher (nur Sekundär, nicht verifiziert).

**Drittanbieter (Ahrefs Brand Radar, Peec, Semrush, Profound u. a.)** [S]: Stichproben von Prompts, keine echten Nutzerabfragen. Grenzen aus den Studien selbst: Fan-out-Queries nicht sichtbar (Ahrefs), Antworten nicht reproduzierbar (SparkToro), Markenzuordnung fehleranfällig (Ahrefs: 30-36 % der scheinbaren Verluste waren Namensvarianten), Anbieter mit Verkaufsinteresse. Google rät zur Vorsicht bei Tools, die Interna versprechen (Leitfaden).

**Manuelle Prompt-Logs** [M]: Als Methode nicht belegt; nach den Volatilitätsdaten nur mit mehreren Läufen, festen Prompts, Datum und Standort sinnvoll.

**Merchant Center** [P]: "AI performance insights" angekündigt (27.05.2026, "coming soon", zunächst AU, CA, IN, NZ, US). Für Deutschland kein Termin gefunden.

**Was die Messung nicht kann**: Klicks und Umsatz aus KI-Antworten getrennt ausweisen (Google), Position innerhalb der KI-Antwort (Bing), AI Overviews getrennt von AI Mode (Google), Gemini/Perplexity-Einblicke von den Anbietern selbst.

---

## 6. Was ich nicht klären konnte

- Welche SERP-Features auf google.de für kommerzielle und informationale Anfragen tatsächlich wie häufig erscheinen (Shopping-Einheit, Verwandte Fragen, Videos, Foren-Boxen). Dafür fand ich keine belegte deutsche Auswertung; vermutlich nur über eigene SERP-Stichproben oder SISTRIX-Daten prüfbar.
- Ob AI Mode in Österreich und der Schweiz auf Deutsch verfügbar ist (Googles Hilfeseite nur für Deutschland und die deutsche Sprache gesichtet) sowie der genaue Wortlaut zu Modellvarianten mit abweichender Länderliste.
- OpenAI-Hilfecenter und openai.com ließen sich nicht öffnen (403). Auswahlkriterien von ChatGPT Search, Produktfeeds/ACP und Verfügbarkeit in Deutschland sind daher nur über Sekundärquellen bekannt.
- Perplexity beschreibt keine Zitierkriterien; Aussagen darüber sind unbelegt.
- Google-Seiten ohne eigenes Datum: AI-Features-Seite, KI-Leitfaden (Seite), Search-Gallery, Produktdoku. Aktualitätsstand lässt sich nur über Changelog-Einträge eingrenzen.
- Search Console: Ob der KI-Bericht bei kleinen Properties überhaupt Daten zeigt (Google nennt keine Mindestschwelle laut Sekundärquelle), ob Suchanfragen enthalten sind und wie die API mit dem Datentyp umgeht.
- Search Engine Land (403) und Original-Studien von Indig (Paywall), Bright Data, SparkToro, BrightEdge, Semrush, Profound sowie SISTRIX-Originalseiten wurden nicht selbst gelesen; ihre Zahlen sind [nv] bzw. nur über Sekundärberichte belegt.
- WooCommerce-Quellcode-Stand: Datei aus dem Zweig "trunk"; welche Version im konkreten Shop läuft, wurde nicht geprüft. Ob in aktuellen RankMath-Versionen WooCommerce-Produktschema Dubletten mit dem Kern vermeidet, ist nicht belegt.
- Googles Aussage zu YMYL-Einstufung für technische Produkte mit Sicherheitsbezug (Einzelfall).
- Praxisstudien zu Review-Takten professioneller SEO-Teams: nichts Belastbares gefunden; die Taktempfehlung in 5.1 ist Empfehlung, kein Beleg.
- Widersprüche in Quellen: Ahrefs-Schemastudie wird in Sekundärquelle mit 12.05.2026, auf der Ahrefs-Seite mit 11.05.2026 datiert (Ahrefs-Seite gilt). SE-Ranking-Seite zeigt Byline 15.10.2026, SEJ berichtet am 20.11.2025 (Seite vermutlich aktualisiert; Aktualisierungsdatum nicht ausgewiesen). Googles Report-Blog nennt "Teilmenge" im Text und "alle Websites" im Nachtrag.
