# Klassifikation

{% hint style="success" %}
Hilft dir meine Webseite weiter? Falls du dieses Projekt unterstützen möchtest, kannst du mir gerne einen Kaffee an [paypal.me/markusbilz](https://paypal.me/markusbilz?country.x=DE\&locale.x=de\_DE) spenden. Danke.️:heart:
{% endhint %}

F: _Erstellen Sie einen morphologischen Kasten. Benutzen Sie als Beispiel ein Automobil. Verwenden Sie als Dimensionen Marke, Typ und Farbe. Ergänzen Sie zwei weitere Dimensionen Ihrer Wahl. Erklären Sie die zwei möglichen Verwendungen eines morphologischen Kastens._ (3+2+2P.=7P.)

A:

* Kreativitätstechnik
* Funktionale Problemdekomposition

![(Eigene Darstellung)](<../../.gitbook/assets/grafik (18).png>)

Grüner Pfad ist ausgewählte Alternative. Man würde also von BMW ein Coupe in Blau-Weiß mit zwei Tonnen Gewicht für 20.000 EUR fertigen lassen.

F: _Nennen Sie zwei Dimensionen der in der Vorlesung vorgestellten Klassifikation nach Gaul et al. Geben Sie für jede Dimension zwei Beispiele an Merkmalen._ (2+2\*2P.=6P.)

A:

**Input:** externes/internes Wissen, Konsum/Kaufverhalten, Navigationsverhalten

**Output**: Personalisierung, Art d. Informationsübermittlung, Informationsaufbereitung

**Methoden:** Multivariate Statistik, Machine Learning

F: _Begründen Sie, für welchen Einsatzzweck sich die Klassifikation nach Gaul et al. eignet. Nennen Sie zwei Schwächen._ (4+2\*3P.=10P.)

A:

**Ziele:**

* Konsistentes und einfaches Klassifikationsschema für Recommendersysteme
* Klassifikation nach Inputs, Outputs und Methoden
* Zielgruppe insbesondere für wissenschaftliche Zwecke

**Schwächen:**

* Keine Betrachtung von Anreizproblemen
* Keine Betrachtung von Geschäftsmodellen

F: _Schafer et al. schlagen ein Klassifikationssystem für Recommenderdienste vor._

F: _Zeichnen Sie ein Diagramm zur Veranschaulichung des Klassifikationssystems von Schafer et al. Stellen Sie jede Dimension als Achse dar. Beschriften Sie die Achsen. Zeichnen Sie bei diskreten Merkmalen alle Merkmalsausprägungen ein._ (5P.)

A:

![](<../../.gitbook/assets/grafik (22) (1).png>)

F: _Erklären Sie jede Merkmalsausprägung jedes diskreten Merkmals in 2 Sätzen._ (8P.)

A:

Nur Merkmal Methode ist diskret, auf der Abbildung kann es 4 mögliche Werte annehmen:

* **Kunde-Kunde-Relation**: Filmempfehlungen auf Basis der bisherigen Bewertungen des Nutzers (z. B. Movielense). Hier werden dem Nutzer Filme vorgeschlagen, die andere Nutzer mit einem ähnlichen Bewertungsprofil (Geschmack) auch gut fanden.
* **Item-Item-Relation**: "Kunden, die dieses Produkt kauften, kauften auch:" (z. B: Amazon). Hier wird nur auf Basis des aktuellen Produktes ein Produkt empfohlen, was häufig zusammen mit dem aktuellen Produkt gekauft wird. Dabei spielt nur die Eigenschaft, des zusammengekauft werden eine Rolle. Eigenschaften des Nutzers spielen keine Rolle.
* **Inhaltsanalyse**: Empfehlung aufgrund von ähnlichen Attributen, z.B. wenn man auf Amazon Bücher eines bestimmten Genres gekauft hat, werden oft Bücher desselben Autors oder desselben Genres vorgeschlagen -> "Bücher, die Ihnen gefallen könnten".
* **Nicht personalisiert**: "Beliebte Artikel, die ihnen vielleicht gefallen:" (Amazon). Hier werden Artikel vorgeschlagen, die allgemein beliebt sind. Z. B. Die in einem Zeitraum am häufigsten betrachteten/gekauften Artikel. Es fließen keine Informationen zum Benutzer und seinem aktuellen und bisherigen Verhalten ein.

F: _Nennen Sie für jede Merkmalsausprägung aus Aufgabenteil (2) einen Recommenderdienst aus der Industrie. Beschreiben und begründen Sie Ihre Wahl in 2-3 Sätzen._ (12P.)

A:

![](<../../.gitbook/assets/grafik (13).png>)

**Inhaltsanalyse/attribute-based**

* **Amazon.com Delivers**
* Kunden markieren Checkboxen, um aus einer Liste bestimmter Kategorien/Genres auszuwählen
* Benutzer von Amazon.com Delivers haben eine Auswahl von 50 Kategorien, zu denen sie periodisch Empfehlungen erhalten wollen.

**Nicht-personalisiert**

* **E-Bay - Feedback Profile**
* Kunden geben sich gegenseitig Feedback, nicht zu Produkten!
* Das durchschnittliche und individuelle Feedback steht dann den Käufern zur Verfügung, um zu entscheiden, ob ein bestimmter Verkäufer ein gutes Risiko darstellt, und den Verkäufern, um zu entscheiden, ob ein bestimmter Käufer ein gutes Risiko darstellt
* Vorschlag: Netflix: "Heute Top 10 Filme in Deutschland"? --> müssten ja für alle Personen in Deutschland gleich sein (nicht 100%ig sicher, ob da was Persönliches einfließt)
* Amazon Sterne Bewertungen --> werden über alle Nutzer aggregiert, Durchschnitt gebildet?

**Item-Item Relation**

* **Movie Matches von Reel.com**
* Movie Matches ist aus der Perspektive der Kundenerfahrung ähnlich. MOVIE MATCHES schlägt andere Produkte vor, an denen ein Kunde interessiert sein könnte, basierend auf einem einzigen anderen Produkt, für das der Kunde Interesse bekundet hat

**Kunde-Kunde Relation**

* **My CDNOW**
* Gesamte Kaufgeschichte des Kunden wird herangezogen.
* Wenn Kunden bei My CDNOW Empfehlungen anfordern, sagt das System 6 Alben voraus, die dem Kunden gefallen könnten, basierend auf dem, was er bereits besitzt (Vgl. Paper: 2001, Recommender Systems in E-Commerce)

F: _Skizzieren Sie in einer Grafik die Methode zur Klassifikation nach Schafer et al._ (5P.)

A:

![](<../../.gitbook/assets/grafik (22) (1) (2).png>)

F: _Ordnen Sie einen Assoziationsregel-Recommenderdienst gemäß der Dimension Methode nach Schafer et al. ein. Beschreiben und begründen Sie kurz._ (3P.)

A:

AR nutzen die Ähnlichkeit von Kaufhistorien von Produkten (Wenn ein Kunde die Menge X gekauft hat, empfiehl ihm Y -> Produkt-Produkt Korrelation / item-to-item Recommender.

F: _Nennen Sie ein Praxisbeispiel für einen Assoziationsregel-Recommender und erklären Sie Ihre Einordnung_ (2P.)

A:

Warenkorbanalyse im Supermarkt:

Berechnung der Wahrscheinlichkeit ein anderes Produkt zu kaufen, wenn ein bestimmtes Produkt bereits gekauft wurde -> Produkt-Produkt Korrelation

F: _Ordnen Sie einen Collaborative-Filtering Recommenderdienst gemäß der Dimension Methode nach Schafer et al. ein. Beschreiben und begründen Sie kurz._ (3P.)

A: Collaborative Filtering Ansätze setzen auf die Ähnlichkeit von Nutzern. Das passt zu der Merkmalsausprägung Kunde-Kunde Korrelation (Auf Basis ähnlicher Kunden) / People to People Correlation gemäß der Dimension Methode nach Schafer.

F: _Nennen Sie ein Praxisbeispiel für einen Collaborative-Filtering Recommenderdienst und erklären Sie Ihre Einordnung_ (2P.)

A:

**Jester:** Benutzer bewertet explizit ein Set aus 15 Witzen (Skale --15 bis +15). Danach erhält er einen Vorschlag von Witzen basierend auf seinen vorherigen Bewertungen. Daraufhin werden erneut Daten gesammelt.

**Amazon.com's Book Matcher:** Kunden können Feedback über gelesene Bücher abgeben. Kunden raten Buch auf Likert Skala. Nachdem Kunden einige Bücher gelesen haben, erhalten sie Vorschläge, die ihnen gefallen könnten. Die Empfehlungen werden generiert, indem Bücher von Nutzern mit ähnlichem Geschmack ausgewertet werden.

F: _Nennen Sie je 2 Vor- und Nachteile der Methode zur Klassifikation nach Schafer et al._ (2\*2=4P.)

A:

**Vorteile**:

* Strategien werden durch E-Marketing Instrumente implementiert
* Verlinkt wirtschaftliche Zielsetzung des E-Commerce Unternehmens mit E-Marketing Strategien

**Nachteile:**

* Auf der Methodenseite sehr grob (nur 4 Arten von Recommender)
* In der Methode steckt aber gerade die Magie eines Recommenders (Skalierbarkeit, Precision, Recall, etc.)
* Skizzieren Sie die Methode zur Klassifikation nach Gaul et al. (4P.)

A:

![](<../../.gitbook/assets/grafik (17).png>)

F: _Nennen Sie je einen Vor- und Nachteil der Methode zur Klassifikation nach Gaul et al._ (2\*1=2P.)

A:

**Vorteil**:

* Systematische Klassifikation entlang der Datenprozesse

**Nachteil**:

* Keine Betrachtung von Anreizprobleme
