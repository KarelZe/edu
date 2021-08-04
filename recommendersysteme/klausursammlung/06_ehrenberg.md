# Ehrenberg-Recommender

F: _Erläutern Sie, auf welche Weise man mit Hilfe von Ehrenbergs Repeat-Buying Theorie Empfehlungen generieren kann. Unter welchen Voraussetzungen ist das Verfahren anwendbar? Welche Verteilungen werden bei diesem Verfahren angewendet \(Verteilungen bitte hinschreiben\) und welche Daten benötigt man, um die Berechnungen durchzuführen?_

A:

**Annahmen \(Folie 22\):**

![](../../.gitbook/assets/grafik%20%2838%29.png)

* Ergänzung von Übungsfolien \(7. Übung\):
  * Markt ist stationär -&gt; keine Änderungen bei Produkten, Kunden, Kaufverhalten
  * Markt ist homogen -&gt; Produkte sind hinreichend ähnlich
  * Gleichgewicht -&gt; Ausreichende Versorgung mit Produkten und Käufern
  * Konzept der Kaufgelegenheit existiert und hält
  * Mittlere Kaufrate und Penetration sind in Beobachtungsperiode bestimmbar für Käufer

**Verteilungen \(Folie 27 / 28\):**

* Gamma-Verteilung \(betrifft Parameter $$\mu$$\)
* Käufe von allen Kunden in Perioden folgen Poisson-Verteilung: $$p_{r} = \frac{e^{- \mu}\mu^{r}}{r!}$$
* Logarithmische Reihenverteilung \(betrifft Kaufprozesse der Konsumenten $$c{1},\, c{2},\ldots,c_{n}$$. $$P\left( r\mathrm{ }\mathrm{Kä}\text{ufe} \right) = \frac{- q^{r}}{\text{rln}\left( 1 - q \right)},r \geq 1$$

**Vorgehen**

![](../../.gitbook/assets/grafik%20%281%29.png)

**Benötigte Daten:**

* $$b$$, $$m$$ beobachtet aus vorverarbeiteten Transaktionsdaten
* Evtl. Auch Transaktionsdaten selbst pro Kunde, Items, Anzahl Kunden?

Welche Varianten gibt es, um zu bestimmen, ab wann eine Anzahl gemeinsamer Käufe als Empfehlung gewertet wird? Auf welche Art und Weise kann man die passendste Variante bestimmen?

A:

1. Sobald die Anzahl Ausreißer unter kumulierte Anzahl von theoretisch erwarteten Wiederkäufen fällt: $$f\left( x_{\text{beobachtet }} \right) < \left( 1 - F\left( x_{\text{theoretisch }} \right) \right)$$
2. Sobald die Anzahl Ausreißer unter Anzahl von theoretisch erwarteten Wiederkäufen fällt: $$f\left( x_{\text{beobachtet }} \right) < f\left( x_{\text{theoretisch }} \right)$$
3. Sobald kumulierte Anzahl Ausreißer unter kumulierte Anzahl von theoretisch erwarteten Wiederkäufen fällt: $$\left( 1 - F\left( x_{\text{beobachtet }} \right) \right) < \left( 1 - F\left( x_{\text{theoretisch }} \right) \right)$$
4. Wenn der Anteil der \(zufällig\) nach dem LSD-Modell erwarteten Produkte im Verhältnis zu beobachteten gering ist.
   * Bestimmen $$\frac{f\left( x_{\text{theoretisch }} \right)}{f\left( x_{\text{beobachtet }} \right)}$$ für jede Klasse $$r$$.
   * Produkte aller Klassen, deren Verhältnis unter einer bestimmten Schranke $$\theta\left( 0 < \theta < 1 \right)$$ liegt, werden empfohlen.

Die passendste Variante könnte durch **Experteneinschätzung** bestimmt werden.

Wie können auf der Basis von Ehrenbergs Repeat-Buying Theorie Empfehlungen berechnet werden? Beschreiben Sie die Schritte beginnend von einzelnen Warenkörben. Nennen Sie sowohl notwendige Voraussetzungen als auch die mathematischen Verteilungen, die den theoretischen Hintergrund des Verfahrens bilden und welche beim Algorithmus eine Rolle spielen.

A: siehe oben.

Beschreiben Sie beginnend von einzelnen Warenkörben, wie man mit Hilfe von Ehrenbergs Repeat-Buying Theorie Empfehlungen generieren kann. Unter welchen Voraussetzungen ist das Verfahren anwendbar? Nennen Sie die mathematischen Verteilungen, die den theoretischen Hintergrund des Verfahrens bilden und welche beim Algorithmus eine Rolle spielen.

A: Siehe oben.

**6.2 Recommender basierend auf Ehrenbergs Repeat Buying Theorie**

Ehrenberg verwendet die Begriffe Kaufgelegenheit, Warenkorb, Penetration $$b$$ und Kaufrate $$w$$. Was versteht man unter diesen Begriffen? \(2+1+2+2P.\)

* A:
* Kaufgelegenheit = Ein Kunde betritt ein Geschäft und kann ein oder mehrere Produkte erwerben.
* Warenkorb = Produkte, die wiederholt bei derselben Kaufgelegenheit gekauft werden.
* Warenkorb enthält alle Informationsprodukte, die besucht\(=gekauft\) wurden \(Folie 13\)
* Penetration b = Man versteht darunter den Anteil der Kunden, die ein Produkt p in einer gegebenen Periode t erworben haben. Alternativ Anteil der Warenkörbe, in denen ein Produkt p enthalten ist.
* Kaufrate w = Ist die durchschnittliche Anzahl von Kaufgelegenheiten, bei denen ein Kunde ein Produkt p in t erworben hat.

In dem in der Vorlesung genannten Beispiel wurden die Log-Daten des Apache Webservers als Warenkorbdaten interpretiert. Nennen Sie vier Schwierigkeiten, die bei der Interpretation eines Logfiles als Warenkörbe auftreten können. Führen Sie jeweils eine Lösung für das Problem an. \(4\*2P.=8P.\)

A:

* Zu kurze Sitzungen z. B. Browserprobleme \(Crash\) / Unabsichtliches Aussteigen aus dem Browser. **Zur Lösung:** Sitzungen kleiner Threshold ausschließen.
* Zu lange Sitzungen z. B. Benutzer loggen sich nie aus. Benutzer verlassen Browser nie. **Zur Lösung:** Sitzungen größer Threshold ausschließen.
* **Eigene:** Zugriff über mehrere Endgeräte / Browsern z. B. Nutzt Benutzer ein mobiles Endgerät und einen Desktop-Rechner. Zur Lösung: Tracking von Nutzern nicht über IP, sondern ausgefeilter Techniken wie Trackingpixel, die über Geräte hinweg funktionieren.
* **Eigene:** Zugriff von Spidern / Scrapern: Spider verursachen viel Traffic, damit Einträge im Log. **Zur Lösung:** Spider aussperren durch robots.txt, um Verfälschung von Warenkörben vermeiden.

Der vorgestellte Algorithmus ermittelt für ein festes Produkt die kombinierten Wiederkäufe mit anderen Produkten. Es wird der Verteilungsparameter q der LSD-Verteilung geschätzt. Benennen Sie die Wiederkaufsklassen in untenstehendem Beispiel, die Sie empfehlen würden. Verwenden Sie zwei unterschiedliche Abschneideregeln \(A und B\), markieren Sie die empfohlenen Klassen in der Tabelle und begründen Sie jeweils Ihre Entscheidung. Hinweis: Die verwendeten Truncate-Regeln dürfen zum gleichen Ergebnis führen. \(2\*5P.=10P.\)

![](../../.gitbook/assets/grafik%20%2840%29.png)

A:

Regel A \(weniger als 40 %\) Zufallsbeobachtung:

| Repeat-buys | $$f(x)_{obs}$$ | $$f(x)_{ theo}$$ | $$f(x)_{theo} /(f(x_{obs})$$ | Klasse wird gezeigt |
| :---: | :---: | :---: | :---: | :---: |
| 1 | 87 | 83.565 | 0.961 | 0 |
| 2 | 17 | 21.355 | 1.256 | 0 |
| 3 | 2 | 7.276 | 3.638 | 0 |
| 4 | 5 | 2.789 | 0.558 | 0 |
| 5 | 3 | 1.140 | 0.380 | 1 |
| 6 | 1 | 0.486 | 0.486 | 0 |
| 7 | 1 | 0.213 | 0.213 | 1 |
| 8 | 1 | 0.095 | 0.095 | 1 |

Regel B:

| Repeat-buys | $$f(x)_{obs}$$ | $$f(x)_{ theo}$$ | $$f\left(x_{\text{obs}}\right)<f\left(x_{\text {theo }}\right)$$ | Klasse wird gezeigt |
| :---: | :---: | :---: | :---: | :---: |
| 1 | 87 | 83.565 | Falsch | 0 |
| 2 | 17 | 21.355 | Wahr | 0 |
| 3 | 2 | 7.276 | Wahr | 0 |
| 4 | 5 | 2.789 | Falsch | 1 |
| 5 | 3 | 1.140 | Falsch | 1 |
| 6 | 1 | 0.486 | Falsch | 1 |
| 7 | 1 | 0.213 | Falsch | 1 |
| 8 | 1 | 0.095 | Falsch | 1 |

Ehrenberg gibt eine theoretische Wahrscheinlichkeit dafür, wie oft ein Produkt bzw. Paare von Produkten gekauft werden. Ein Recommender-Dienst nutzt Ausreißer und empfiehlt diese. Erklären Sie, welche Ausreißer genutzt werden und warum diese als Empfehlungen angesehen werden. \(6P.\)

A: Aus Folie 50:

Es werden Produktpaare nur empfohlen, sofern Produkte tatsächlich häufiger gekauft wurden, als es theoretisch erwartbar gewesen wäre. Ist der tatsächliche Wiederkauf kleiner der theoretischen Anzahl an Wiederkäufen, wird nicht empfohlen. Die Erwartung und der Grund, warum diese als Empfehlung verwendet werden, ist die Erwartung, dass auch in Zukunft die Produktpaare häufiger gekauft werden als andere.

!\[\]\[25\]

![](../../.gitbook/assets/grafik%20%2835%29.png)

Zeichnen Sie ein qualitatives Diagramm der Häufigkeitsverteilungen für ein festes Produkt p und weiteren Produkten. Zeichnen Sie die theoretische Verteilung und beobachtete Verteilung ein. Beschriften Sie die Achsen. Kennzeichnen Sie, was Sie empfehlen. \(7P.\)

A:

![](../../.gitbook/assets/grafik.png)

Nennen Sie je zwei Vor- und Nachteile eines Ehrenberg Recommenders. \(6P.\)

**Vorteile:**

* Keine exogenen Parameter wie Mindest-Support außer Abschneideregel.
* Sauberes, statistisches Verfahren.

**Nachteile**

* Mathematisch deutlich komplexer als Assoziationsregel-Recommender
* Kann in Standard-Variante nicht mit Trends umgehen
* Braucht Abschneideregel

Gegeben sei untenstehende Tabelle von Repeat-buys eines festen Produkts p mit anderen Produkten.

Was bestimmt der LSD-Verteilungsparameter q in der untenstehenden Tabelle? \(3P.\)

$$f_{\text{theo}}$$ in untenstehender Tabelle ist abgleitet aus LSD-Modell, dass die Wahrscheinlichkeit in Abhängigkeit von den Parametern $$q$$ und $$r$$ angibt:

$$P(rK\ddot{a}ufe) = \frac{- q^{r}}{r\ln(1 - q)},r \geq 1$$

Um also $$f_{\text{theo}}$$ in der Tabelle und damit die theoretische Verteilung der Wiederkäufe zu bestimmen, wird der Parameter $$q$$ benötigt. $$q$$ gibt den Anteil der Repeat-Buyer an gesamten Käufen an \(vgl. Folie 29, Ehrenberg\)

$$q$$ ist der Parameter der geschätzten LSD Verteilung $$f_{theo}$$ aufgrund des beobachteten Kaufverhaltens $$w = m/b$$ \(siehe Tutorium 7 \(mit Solution\) Folie 36+37

Die Summe der theoretisch vorhergesagten Repeat-Buys ergibt nicht 100. Stellt dies ein Problem dar? Begründen Sie. \(3P.\)

A:

Nein, nur für relative Häufigkeiten relevant nicht für absolute Häufigkeiten.

Erklären Sie die Zahl $$f_{obs} = 87$$ in der Zeile $$r = 1$$. \(4P.\)

A: **Anzahl der Produktpaare**, die im Zeitraum $$t$$ **einmal** wiedergekauft wurden.

Stellen Sie drei verschiedene Abschneideregeln als Formeln da. \(9P.\)

A:

* Sobald die Anzahl Ausreißer unter kumulierte Anzahl von theoretisch erwarteten Wiederkäufen fällt: $$f\left( x_{\text{beobachtet }} \right) < \left( 1 - F\left( x_{\text{theoretisch }} \right) \right)$$
* Sobald die Anzahl Ausreißer unter Anzahl von theoretisch erwarteten Wiederkäufen fällt: $$f\left( x{_\text{beobachtet }} \right) < f\left( x_{\text{theoretisch} } \right)$$
* Sobald kumulierte Anzahl Ausreißer unter kumulierte Anzahl von theoretisch erwarteten Wiederkäufen fällt: $$\left( 1 - F\left( x{_\text{beobachtet }} \right) \right) < \left( 1 - F\left( x{_\text{theoretisch }} \right) \right)$$

Wenden Sie diese Abschneideregeln auf den untenstehenden Beispieldatensatz an: Markieren Sie in den Spalten R1 . . . R3, welche Zeilen Sie empfehlen. \(Ohne zumindest kurzen Rechenweg keine Punkte!\) \(6P.\)

![](../../.gitbook/assets/grafik%20%2837%29.png)

Regel A \(weniger als 40 %\) Zufallsbeobachtung:



| Repeat-buys | $$f(x_{obs})$$ | $$f(x_{ theo})$$ | $$\frac{f\left(x_{theo }\right)}{f\left(x_{obs }\right)}$$ | Klasse wird gezeigt |
| :---: | :---: | :---: | :---: | :---: |
| 1 | 87 | 83.5 | 0,96 | 0 |
| 2 | 17 | 21.5 | 1,26 | 0 |
| 3 | 2 | 7.3 | 3,65 | 0 |
| 4 | 4 | 2.8 | 0,70 | 0 |
| 5 | 3 | 1.0 | 0,33 | 1 |
| 6 | 1 | 0.5 | 0,50 | 0 |
| 7 | 1 | 0.2 | 0,20 | 1 |
| 8 | 1 | 0.1 | 0,10 | 1 |

Regel B:

| Repeat-buys | $$f(x_{obs})$$ | $$f(x)_{theo}$$ | $$f(x_{obs}) < f(x_{theo})$$ | Klasse wird gezeigt |
| :---: | :---: | :---: | :---: | :---: |
| 1 | 87 | 83.5 | FALSCH | 0 |
| 2 | 17 | 21.5 | WAHR | 0 |
| 3 | 2 | 7.3 | WAHR | 0 |
| 4 | 4 | 2.8 | FALSCH | 1 |
| 5 | 3 | 1.0 | FALSCH | 1 |
| 6 | 1 | 0.5 | FALSCH | 1 |
| 7 | 1 | 0.2 | FALSCH | 1 |
| 8 | 1 | 0.1 | FALSCH | 1 |

Regel C Alternative \(ähnlich Skript, S. 53\):

| Repeatbuys | $$f(x)_ {obs}$$ | $$f(x) _{theo}$$ | $$1-F(x)_{obs}$$ |  | $$1-F(x_{obs}) < 1- F(x_{theo})$$ | Klasse wird gezeigt |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| 1 | 87,00 | 83,50 | 116,00 | 116,00 | FALSCH | 0 |
| 2 | 17,00 | 21,50 | 29,00 | 32,50 | WAHR | 0 |
| 3 | 2,00 | 7,30 | 12,00 | 11,00 | FALSCH | 1 |
| 4 | 4,00 | 2,80 | 10,00 | 3,70 | FALSCH | 1 |
| 5 | 3,00 | 1,00 | 6,00 | 0,9 | FALSCH | 1 |
| 6 | 1,00 | 0,50 | 3,00 | 0 | FALSCH | 1 |
| 7 | 1,00 | 0,20 | 2,00 | 0 | FALSCH | 1 |
| 8 | 1,00 | 0,10 | 1,00 | 0 | FALSCH | 1 |
| Summe | 116,00 | 116,90 |   |   |   |   |

**Ehrenberg Recommender**

Ehrenberg verwendet die Begriffe Kaufgelegenheit, Warenkorb, Penetration und Kaufrate. Erklären Sie diese Begriffe für einen Online-Empfehlungsdienst bei Amazon. \(1+1+2+2=6P.\)

A:

* Kaufgelegenheit = Ein Kunde ruft Amazon.com auf und kann shoppen.
* Warenkorb = Produkte, die wiederholt bei Amazon gekauft werden.
* Penetration b = Anteil der Amazon-Kundschaft, die ein Produkt p z. B. Amazon Basic Kopfhörer in einer Periode $$t$$ z. B. in 2020 erworben hat.
* Kaufrate w = Durchschnittliche Anzahl von Kaufgelegenheiten, bei der Kunden von Amazon das Produkt p z. B. Amazon Basic Kopfhörer in einer Periode $$t$$ z. B. in 2020 erworben haben.

Man kann Log-Daten eines \(Apache\) Webservers als Warenkorbdaten interpretiert. Nennen Sie drei Schwierigkeiten, die hierbei auftreten können. \(3\*2P.=6P.\)

A:

* Zu kurze Sitzungen z. B. Browserprobleme \(Crash\) / Unabsichtliches Aussteigen aus dem Browser.
* Zu lange Sitzungen z. B. Benutzer loggen sich nie aus. Benutzer verlassen Browser nie.
* \[Eigene:\]{.underline} Zugriff über mehrere Endgeräte / Browsern z. B. Nutzt Benutzer ein mobiles Endgerät und einen Desktop-Rechner.

Der Ehrenberg-Recommender-Algorithmus ermittelt für ein festes Produkt die Kaufrate. Es wird auch ein Verteilungsparameter $$q$$ der LSD-Verteilung geschätzt \(13P.\)

\(a\) Geben Sie den mathematischen Zusammenhang zwischen w und q an. \(3P.\)

A:

$$\mathrm{\text{Mean}}\mathrm{\,}\mathrm{\text{purchase}}\mathrm{\,}\mathrm{\text{frequency}}\mathrm{\,}w = \frac{- q}{\left( 1 - q \right)\ln\left( 1 - q \right)}$$

D. h. anhand von Mittelwert $$m$$ und Penetration $$b$$ wird erstmal die mean purchase frequency $$w$$ berechnet, daraus lässt sich dann $$q$$ anhand von Tabellen ablesen.

\(b\) Kann man q interpretieren? Wenn ja, geben Sie eine Interpretation für q = 0, 45; wenn nein, was ist q? \(4P.\)

A: $$q$$ gibt den Anteil der Repeat-Buyer an den gesamten Käufen an. \(vgl. Folie 29\)

\(c\) Beobachtet man w oder q? \(2P.\)

A: Man beobachtet $$w$$ und kann daraus $$q$$ ableiten.

\(d\) Kann man entsprechend q, respektive w, dann direkt aus dem beobachteten w, respektive q, berechnen? Welches Verfahren wendet man beispielsweise an? \(4P.\)

A:

Kennt man w, so kann man q ableiten / via Bisektionsverfahren:

$$\mathrm{\text{Mean}}\mathrm{\,}\mathrm{\text{purchase}}\mathrm{\,}\mathrm{\text{frequency}}\mathrm{\,}w = \frac{- q}{\left( 1 - q \right)\ln\left( 1 - q \right)}$$

Alternativ liegt q auch in tabellierter Form vor z. B.:



| W | 1.0 | 1.1 | 1.2 | 1.3 | 1.4 | 1.5 | 1.6 |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| q | 0.00 | 0.17 | 0.30 | 0.40 | 0.47 | 0.53 | 0.58 |

Use Case: Sie arbeiten nach Ihrem Abschluss am KIT als Business Consultant für den neuen und aufstrebenden Online-Vertrieb der Einzelhandelskette Lidl. Lidl möchte künftig alle in seinen Läden verfügbaren Produkte auch Online anbieten. Sie sollen hierzu aus den Transaktionsdaten der einzelnen Filialen einen Recommenderdienst für den neuen Onlineshop realisieren. Sie entscheiden sich für einen Recommender basierend auf der Ehrenberg-Theorie.

Nennen Sie drei Vorteile und zwei Nachteile gegenüber einem klassischen Assoziationsregel-Recommenderdienst. Beziehen Sie sich auf den Use Case! \(3+2=5P.\)

A:

**Vorteile:**

* **Keine exogenen Parameter notwendig.** Wohingegen bei Assoziationsregeln Mindestsupport und Mindest-Confidence festgelegt. Typischerweise wäre dann auch ein individueller Mindest-Support und eine Mindest-Confidence für verschiedene Produktgruppen notwendig, was hohen Aufwand in der Administration erfordert und systematischen Fehlern _\(Bias\)_ z. B. weil Parameter-Bestimmung für bestimmte Produktgruppen schwierig ist_,_ unterliegen kann.
* **Sauberes, statisches Verfahren**. Klassische Assoziationsregeln brauchen Mindest-Support und Mindest-Confidence, die durch Anwender festgelegt werden muss. Unterliegt damit einem Bias. Der Ehrenberg-Recommender basiert hingegen auf wissenschaftlicher Theorie und kommt ohne Benutzer-definierte Parameter wie Mindest-Support aus, die etwa für bestimmte Produkte oder Produktgruppen bei Lidl notwendig wären.
* **Skalierendes Verfahren**. Anders als Assoziationsregeln skaliert der Ehrenberg-Recommender sehr gut. Dies ist ein großer Vorteil bei dem großen Warensortiment von Lidl ggü. klassischen Assoziationsregel-Recommendern, bei der dann eine exponentiell wachsende Zahl an Frequent Itemsets generiert werden und damit großer Rechenaufwand verursacht wird.

**Nachteil:**

* Mathematisch anspruchsvoller. Ggü. Assoziationsregeln ist der Ehrenberg-Recommender schwieriger zu verstehen. Ggf. muss also das Lidl-Personal erst geschult werden, um den Algorithmus des Recommenders zu verstehen.
* Schwerer erklärbar für Management, weil Verteilungsannahme zugrunde liegt und Wiederkaufstheorie nach Ehrenberg verstanden werden muss.
* Teurer in der Entwicklung

Ehrenberg sagt die erwartete Kaufhäufigkeit von n-Tupeln von Produkten voraus. Erklären Sie in ca. 6 Sätzen, wie dies zur Generierung von Empfehlungen verwendet werden kann. Beziehen Sie sich auf den Use Case! \(6P.\)

A: Folie 48. \(Alles was über Kasse gezogen wird, wird zum Warenkorb\)

Wir haben in der Vorlesung 4 verschiedene statistische Abschneideregeln besprochen, durch die entschieden wird, welche Produktpaare miteinander empfohlen werden und welche nicht.

\(a\) Zeichnen Sie ein qualitatives Diagramm mit dem Sie eine Abschneideregel Ihrer Wahl veranschaulichen. Die x-Achse sei die Anzahl der Wiederkäufe in Periode t. Beschriften Sie alle Achsen und Zeichenelemente! Erklären Sie den Zusammenhang zum Use Case! \(2+2+2\*2=8P.\)

A:

!\[\]\[29\]

![](../../.gitbook/assets/grafik%20%289%29.png)

Sobald Anzahl der Ausreißer unter Anzahl von theoretisch erwarteten Wiederkäufen fällt:$$f\left( x_{\text{beobachtet }} \right) < f\left( x_{\text{theoretisch }} \right)$$, wird keine Empfehlung gegeben.

Usecase: wird für die Paare Schoko-Ostertiere mit Backware oder Wurstware mit veganem Brotaufstrich, die theoretische Anzahl der Wiederkäufe nicht erreicht. Theoretisch hätten 5 Paare 3-mal zusammengekauft werden sollen, praktisch aber nur 4 Paare 3-Mal. Es wird also **keine** Empfehlung gegeben.

\(b\) Geben Sie diese auch mathematisch an. \(2P.\)

A: Sobald Anzahl der Ausreißer unter Anzahl von theoretisch erwarteten Wiederkäufen fällt: $$f\left( x_{\text{beobachtet }} \right) < f\left( x_{\text{theoretisch }} \right)$$, wird keine Empfehlung gegeben.

\(c\) Geben Sie eine weitere Abschneideregel mathematisch an und erklären Sie diese, Sie müssen nicht zeichnen! \(2+2=4P.\)

A: Sobald die Anzahl der Ausreißer unter die kumulierte Anzahl von theoretisch erwarteten Wiederkäufen fällt, wird keine Empfehlung mehr gegeben:

$$f\left( x_{\mathrm{\text{beobachtet}}} \right) < \left( 1 - F\left( x_{\mathrm{\text{theoretisch }}} \right) \right)$$

Use Case: Sie arbeiten für Jupiter, einen großen, deutschlandweit operierenden Elektronikanbieter, der sein Onlinegeschäft ausbauen möchte. Sie sollen für die Abteilung Haushaltsgeräte einen Ehrenberg-Recommenderdienst aufbauen: Zusatzartikel, die beim Kauf eines Kühlschrankes oft dazu erworben wurden, sollen künftig auf der Produktseite empfohlen werden. Ohne Use Case Bezug max. die Hälfte der Punkte!

Nennen Sie je zwei Use-Case bezogene Vorteile und Nachteile gegenüber einem klassischen Assoziationsregel-Recommenderdienst. Beziehen Sie sich auf den Use Case! \(2+2=4P.\)

A:

**Vorteile:**

* **Keine exogenen Parameter notwendig.** Wohingegen bei Assoziationsregeln Mindestsupport und Mindest-Confidence festgelegt. Typischerweise wäre dann auch ein individueller Mindest-Support und eine Mindest-Confidence für verschiedene Produktgruppen z. B. Kühlschrank-Reiniger o. Ä. notwendig, was hohen Aufwand in der Administration durch das Personal von Jupiter erfordert und systematische Fehler _\(Bias\)_ z. B. weil Parameter-Bestimmung für bestimmte Produktgruppen schwierig ist_,_ einführt.
* **Skalierendes Verfahren**. Anders als Assoziationsregeln skaliert der Ehrenberg-Recommender sehr gut. Dies ist ein großer Vorteil bei dem großen Warensortiment von Haushaltsgeräten ggü. klassischen Assoziationsregel-Recommendern, bei denen dann eine exponentiell wachsende Zahl an Frequent Itemsets generiert werden und damit großer Rechenaufwand verursacht wird.

**Nachteil:**

* **Keine Verteilung zu parametrisieren** Verfahren wie Ehrenberg basieren darauf, dass sich eine Verteilung verlässlich parametrisieren lässt. Da nur selten Kühlschränke gekauft werden mit anderen Artikeln, ist es aber schwierig eine verlässliche Verteilung zu parametrisieren.
* **Mathematisch anspruchsvoller**. Ggü. Assoziationsregeln ist der Ehrenberg-Recommender schwieriger zu verstehen. Ggf. muss also das Jupiter-Personal erst geschult werden, um den Algorithmus des Recommenders zu verstehen.
* **Unentdecktes Potential**. Ggf. bleibt Potential unentdeckt, weil bislang bestimmte Produkte z. B. teure Haushaltsgeräte, die hohen Deckungsbeitrag erwirtschaften, selten gemeinsam gekauft werden. Diese Produktpaare werden dann auch in Zukunft nicht empfohlen, obwohl sie „als weniger passende Empfehlung" das Potential haben dem Unternehmen einen höheren Deckungsbeitrag zu erwirtschaften, als Produkte, die zwar oft gemeinsam gekauft werden, aber wenig Deckungsbeitrag erwirtschaften z. B. Kühlgeräte-Montageservice \(vgl. Folie 60\).

Ehrenberg sagt die erwartete Kaufhäufigkeit von n-Tupeln von Produkten voraus. Erklären Sie in ca. 6 Sätzen, wie dies zur Generierung von Empfehlungen verwendet werden kann. Beziehen Sie sich auf den Use Case! \(6P.\)

A: Siehe oben.

Wir haben in der Vorlesung 4 verschiedene statistische Abschneideregeln besprochen, durch die entschieden wird, welche Produktpaare miteinander empfohlen werden und welche nicht.

\(a\) Zeichnen Sie ein qualitatives Diagramm, mit dem Sie eine Abschneideregel Ihrer Wahl veranschaulichen. Die x-Achse sei die Anzahl der Wiederkäufe in Periode t. Beschriften Sie alle Achsen und Zeichenelemente! Erklären Sie den Zusammenhang zum Use Case! \(1+2+2\*2=7P.\)

A:

![](../../.gitbook/assets/grafik%20%2821%29.png)

\(Übung 7; Folie 43\)

**Usecase:** wird für Kühlschränke und beispielsweise Kühlschrankmagneten die theoretische Anzahl der Wiederkäufe nicht erreicht, dann wird **keine** Empfehlung gegeben. Theoretisch hätten 5 Paare 3-mal zusammengekauft werden sollen, praktisch aber nur 4 Paare 3-Mal.

\(b\) Geben Sie diese auch mathematisch an. \(1P.\)

A: Sobald Anzahl der Ausreißer unter Anzahl von theoretisch erwarteten Wiederkäufen fällt: $$f\left( x_{\text{beobachtet }} \right) < f\left( x_{\text{theoretisch}} \right)$$, wird keine Empfehlung gegeben.

\(c\) Geben Sie eine weitere Abschneideregel mathematisch an und erklären Sie diese, Sie müssen nicht zeichnen! \(2+2=4P.\)

A: Sobald die Anzahl der Ausreißer für Kühlschrankmagneten unter die kumulierte Anzahl von theoretisch erwarteten Wiederkäufen fällt, wird keine Empfehlung mehr gegeben:

$$f\left( x_{\mathrm{\text{beobachtet}}} \right) < \left( 1 - F\left( x_{\mathrm{\text{theoretisch }}} \right) \right)$$

\(d\) Für den Use Case: Würden Sie eher eine klassischen AR-Recommender oder einen Ehrenberg-Recommender einsetzen? Begründen Sie! \(3P.\)

A: Für den gegebenen Use Case sollte ein Ehrenberg-Recommender verwendet werden. Er erfordert anders als AR-Recommender keine exogenen Parameter. Damit spart sich die Jupiter Administrations-/ Validierungsaufwand für die Festlegung von Mindest-Support und Mindest-Confidence für unterschiedliche Produktgruppen wie Kühlschrank-Reinigungsmittel, Magnete, Anbauteile etc.

