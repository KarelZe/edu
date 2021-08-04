# Assoziationsregeln

## Assoziationsregeln

Erläutern Sie den Einsatz von Assoziationsregeln für die Erstellung eines Recommendersystems.

A:

Assoziationsregeln dienen der Identifikation von Korrelationen zwischen auftretenden Elementen \(Items\). Die Stärke der Korrelation \(Zusammenhang\) zwischen Items wird als Confidence bezeichnet. Die Information über die Häufigkeit der Items wird als Support bezeichnet. Alle Assoz.-algorithmen haben zwei Teile:

* Berechnen aller häufigen Item-Mengen über dem Mindest-Support
* Konstruktion aller Assoziationsregeln über der Mindest-Confidence

Ich hätte noch ergänzt: Recommendersysteme nutzen diese Regeln, um Produkte zu empfehlen. Assoziationsregeln sind immer in der Form X -&gt; Y. Wenn ein Nutzer Produkt\(e\) X in seinem Warenkorb hat, werden ihm Produkte Y empfohlen

_Gegeben seien die folgenden Warenkörbe:_ $$\{ a,d\},\{ a,b,d,e\},\{ a,c,d,f\},\{ d,e\},\{ b,d,f\}.$$ _Der Minimumsupport sei_ $$s_{min} = \frac{2}{5}$$ _, die Minimumkonfidenz_ $$c_{min} = \frac{3}{5}$$ _._

F: _Errechnen Sie die Supportwerte für die entstehenden Itemmengen nach dem apriori-Algorithmus. Markieren Sie dabei für diejenigen Itemmengen, die aus der Betrachtung gelöscht werden, ob dies aufgrund der Apriori-Regel geschieht oder aufgrund des zu niedrigen, berechneten Supports. Welche Regeln würden bei der gegebenen Konfidenzschranke entstehen?_

A:

Anmerkung: Rote Prune Werte -&gt; Löschung Aufgrund Apriori-Regel

$$c_{min} = \frac{3}{5};s_{min} = \frac{2}{5}$$ .

![\(Eigene Darstellung\)](../../.gitbook/assets/grafik%20%282%29.png)

Was sind die Vorteile, was die Nachteile des Verfahrens?

A:

**Vorteile:**

1. Keine Wahl von Cut-Methoden notwendig
2. Finden interessanter Warenkörbe mit mehr als zwei Artikeln möglich
3. Assoziationsregeln treffen keine Modellannahmen über Unabhängigkeit von Kaufprozessen, die Einsatz des Modells zunichtemachen, wenn sie nicht gelten.
4. Beschränken der Berechnungen je nach Anzahl gewünschter Empfehlungen möglich \(z.B. L7 für max. 6 Empfehlungen\)

**Nachteil:**

1. Verfahren berücksichtigt keine statistischen Zusammenhänge z. B. besteht keine Möglichkeit Ergebnisse statistisch zu interpretieren
2. Erfordert die Vorgabe zwei externen, nicht aus dem Modell begründbare Parameter $$s_{min}$$ und $$c_{min}$$ .
3. Parameter lassen sich ex ante nur schwer bestimmen. \(Folie 52 + 53\)

Erläutern Sie den Einsatz von Assoziationsregeln für die Erstellung eines Recommendersystems und beschreiben Sie den Assoziationsregelalgorithmus.

Assoziationsregeln dienen der Identifikation von Korrelationen zwischen auftretenden Elementen \(Items\). Die Stärke der Korrelation \(Zusammenhang\) zwischen Items wird als Konfidenz bezeichnet. Die Information über die Häufigkeit der Items wird als Support bezeichnet.

**Algorithmus:**

Schritt 1:

Berechne welche Itemmenge oft in Transaktionen vorkommen. "Oft" wird durch smin festgelegt. Dadurch werden zufällig gemeinsam gekaufte Produkte aus der Betrachtung ausgeschlossen. Diese Kombinationen sind eher selten und verhindern eine Explosion des Suchraumes

Schritt 2:

Berechne welche Teile der Itemmenge \(X\Y\) fast nie ohne die restlichen Teile der Menge \(Y\) gekauft werden \(Konfidenz\). "Fast nie" wird durch cmin festgelegt. \(Folie 30; Übung\)

Gegeben seien die folgenden Warenkörbe: $$\{a, b, d\}, \{d, f\}, \{b, e\}, \{b, d, e\}, \{a, b, d, e\}, \{a, c, d, f \}$$ . Der Minimumsupport smin = 1/2, die Minimumkonfidenz cmin = 3/4. Errechnen Sie die Supportwerte für die entstehenden Itemmengen nach dem apriori-Algorithmus. Markieren Sie dabei für diejenigen Itemmengen, die aus der Betrachtung gelöscht werden. Führen Sie alle möglichen Schritte aus. \(10P.\)

Welche Regeln würden bei der gegebenen Konfidenzschranke entstehen? Hier reicht es, wenn Sie die Konfidenzwertberechnung anhand von 6 Beispielen veranschaulichen.

A:

![\(Eigene Darstellung\)](../../.gitbook/assets/grafik%20%287%29.png)

Sie arbeiten als IT-Leiter für die "Nützlinge Online GmbH", die Nützlinge, z.B. Marienkäfer, online anbietet und via Post an Endkunden verschickt. Ihr Auftrag lautet, für die Geschäftsführung einen Assoziationsregel-Recommender zu entwickeln. Ziel ist es, dem Kunden bei Interesse an einem Nützling \(z.B. Marienkäfer\) einen anderen ebenfalls geeigneten Nützling \(z.B. Schlupfwespe\) zu empfehlen.

F: _Beschreiben Sie für die Geschäftsführung folgende Schritte: Woraus und wie wird die Empfehlung generiert? Wie kann die Empfehlung dem Kunden präsentiert werden? Geben Sie Definitionen für die bei einem Assoziationsregel-Recommenderdienst wichtigen Begriffe Support und Confidence._ \(3+3+3P\)

A:

Wir betrachten eine Menge $$I = i_1, i_2, \cdots$$ _, im von Items \(Nützlinge\) und eine Reihe_ $$T= (t_1,t_2,\cdots,t_n)$$ von Transaktionen. Jede Transaktion enthält mindestens ein Item. Wir suchen nun häufige Assoziationsregel X-&gt;Y \(Wenn ein Kunde die Menge X gekauft hat, empfiehl ihm Y\)

Falls ein Kunde sich für einen Marienkäfer entschieden hat, wird dieser auf der Benutzeroberfläche eine Liste mit weiteren Empfehlungen zu diesem Marienkäufer angezeigt.

Support: Sagt aus, wie oft ein Item oder eine Menge von Items zusammengekauft wird

Confidence: Sagt aus, wie oft die Itemmenge X und Y zusammengekauft werden, wenn X gekauft wurde.

F: _Welche personenbezogenen Daten müssen Sie mindestens speichern? Begründen Sie kurz_. \(4P\)

A:

Die Transaktionen der Kunden. Transaktionen der Kunden mit den jeweiligen Items sind der Input für den Assoziationsregel Algorithmus. Ohne diesen Input können keine Empfehlungen für den Kunden erzeugt werden. Es müssen keine personenbezogenen Daten gespeichert werden. Es genügen die \(anonymisierten\) Kauftransaktionen / Warenkörbe, welche gespeichert werden müssen. Es geht hierbei nur um eine Produkt/Produkt-Korrelation wofür keine Kundendaten notwendig sind.

F: _Klassifizieren Sie einen entsprechende Assoziationsregel-Recommender nach Schafer et al. für die Merkmale Methode, Gedächtnislänge und notwendige Kundenaktivität für den Erhalt der Empfehlung. Wenn Sie Annahmen treffen, geben Sie diese an._ \(2+2+2P\)

A:

**Methode:** Item-to-Item Korrelation

**Gedächtnislänge**: flüchtig

**Kundenaktivität, um Empfehlung zu erhalten:** Empfehlung wird Kunden automatisch bereitgestellt.

F: _Ein Geschäftsführer meint: "Wieviel billiger wird Ihr Recommender, wenn Sie den Teil zur Auswahl geeigneter Kandidaten weglassen? " Kaufen Sie einen neuen schnellen Rechner und berechnen Sie alle möglichen Kombinationen. Was antworten Sie? \(Sie wissen, dass Sie derzeit 1.000 Nützlinge anbieten\)._ \(6P\)

A:

Ohne Einsatz externer Parameter \(smin, cmin\) müssen 1000! Produktkombinationen berechnet werden. Dazu ist nicht einmal ein schneller Rechner in kurzer Zeit in der Lage. Es scheitert somit an der Skalierbarkeit. Ein Problem ist auch, dass man dann zwingend eine Datenbank braucht, da definitiv nicht mehr alles in den RAM passt -&gt; ggf. wieder zusätzliche Kosten durch DB Server.

## **Assoziationsregel-Recommender**

Ordnen Sie einen Assoziationsregel-Recommenderdienst gemäß der Dimension "Methode" nach Schafer et al. ein. Begründen Sie kurz. \(3P.\)

A:

Produkt-Produkt-Korrelation / Item-to-Item-Recommender, denn Empfehlung wird basierend auf einer kleinen Menge an Produkten generiert, für die sich der Kunde interessiert. Item-to-Item Recommender schlagen, dann Produkte vor, um die Order zu vergrößern \(vgl. Schafer et. Al.\) Assoziationsregel-Recommender nutzen Ähnlichkeit von Kaufhistorien aus \(vgl. Übung 3 Seite 4\).

Geben Sie alle notwendigen Inputs an, damit ein Assoziationsregel-Recommender Empfehlungen erzeugen kann. \(7P.\).

A:

Eine Menge I = i1,i2,..., im von Items \(Produkte, URLs, Webseiten\)

Eine Reihe T = \(t1, t,2, ..., tn\) von Transaktionen mit tj Teilmenge von I

Support \(smin\)

Confidence \(cmin\)

Aktueller Warenkorb/aktuell angeschautes Produkt

Nennen Sie ein Praxisbeispiel eines Assoziationsregel-Recommenders. \(3P.\)

A:

Supermarkt: Warenkorbanalyse

Definieren Sie die Begriffe "Support" und "Confidence". \(6P.\)

A:

Support\(X\) : Wie oft eine Menge von Items zusammen vorkommen.

Confidence\(X,Y\): Wie oft Itemmengen X und Y zusammen vorkommen, wenn X vorkommt.

Begründen oder beweisen Sie \(6P.\): $\text{support}\(X\) \leq s \Rightarrow \text{support}\(X \cup Y\) \leq \text{support}\(X\) \leq s$

A:

Implikation stimmt:

Durch Hinzunahme eines weiteren Produktes Y kann X gemeinsam mit diesem Produkt nicht öfter vorkommen, als es allein vorkommt. \(siehe Tutorium, Folie 33\)

**Beispiel:**

Setze für X = Seife und für Y = Shampoo.

Support für Seife ist 0,4

Support für Seife und ein weiteres Y kann nie über 0,4 steigen, da Seife nur 4-mal in der Transaktionsmenge vorkommt.

Durch Hinzunahme eines weiteren Produktes kann Seife gemeinsam mit diesem Produkt nicht öfter vorkommen als es allein vorkommt.

Gegeben sei folgende Datenbanktabelle mit einer Zuordnung von Transaktionen T und Produkten P. Der erste Eintrag \(T1, P1\) bedeutet, in Transaktion T1 war Produkt P1 enthalten.

![](../../.gitbook/assets/grafik%20%2820%29.png)

Geben Sie allgemein die Formel für den Support einer Menge X von Produkten an. \(2P.\)

A:

$$
\operatorname{support}(X)=\frac{|\{t \in T \mid X \subseteq t\}|}{|T|}
$$

Geben Sie folgende Supports an: sup\({P1}\), sup\({P1, P2}\), sup\({P1, P3}\), sup\({P1, P2, P3}\). \(4P.\)

A:

Transaktionen \(infohalber\): T1 = {P1, P2, P3}, T2 = {P2, P3, P4}, T3= {P1, P4}, T4 = {P1, P2, P3}, T5 = {P2, P3, P5} und T6 = {P4, P5}

sup\({P1}\) = 3/6

sup\({P1, P2}\)= 2/6

sup\({P1, P3}\)= 2/6

sup\({P1, P2, P3}\)= 2/6

Erklären Sie: Was bedeutet sup\({P1, P2, P3}\) in Hinblick auf Empfehlungen? \(3P.\)

A:

Support\({P1,P2,P3}\) gibt an, wie oft die Items P1, P2 und P3 gemeinsam gekauft werden. Es ist ein Maß für die Häufigkeit der Itemmenge {P1,P2,P3}.

Use Case Bezug --&gt; die Itemmenge kommt in 1/3 aller TAs im Durchschnitt vor

Bestimmen Sie den Support von allen zweielementigen Produktmengen. \(3P.\)

A:

C\_1 / L\_1:

{p\_1}

{p\_2} -&gt; Support 4/6

{p\_3} -&gt; Support 4/6

{p\_4}

{p\_5}

C\_2 / L\_2:

{p\_1, p\_2} -&gt; Support 2/6

{p\_1, p\_3} -&gt; Support 2/6

{p\_1, p\_4} -&gt; Support 1/6

{p\_2, p\_3} -&gt; Support 4/6

{p\_2, p\_4} -&gt; Support 1/6

{p\_2, p\_5} -&gt; Support 1/6

{p\_3, p\_4} -&gt; Support 1/6

{p\_3, p\_5} -&gt; Support 1/6

{p\_4, p\_5} -&gt; Support 1/6

Geben Sie allgemein die Formel für Confidence an. Erklären Sie kurz die Bestandteile der Formel. \(2P.\)

A:

$$
\operatorname{confidence}(X, Y)=\frac{\operatorname{support}(X \cup Y)}{\operatorname{support}(X)}
$$

Die Confidence sagt aus, wie oft die Itemmenge X und Y zusammengekauft werden \(Zähler\), wenn X gekauft wurden \(Nenner\)

Bestimmen Sie die Conficence conf\({P2}, {P3}\) und conf\({P3}, {P2}\). \(3P.\)

A:

Conf\(P2,P3\)= 4/6 / 4/6 = 1

Conf\(P3,P2\) = 4/6 / 4/6 = 1

Erklären Sie: Was bedeutet conf\({P2}, {P3}\) in Hinblick auf Empfehlungen? \(3P.\)

A:

![](../../.gitbook/assets/grafik%20%2814%29.png)

Use case Bezug: conf\(2, 3\) = 1 --&gt; Regel hat Zuverlässigkeit von 100%, ist also sehr zuverlässig

Wie oft wurde P2 und P3 zusammengekauft, wenn P2 gekauft wurde.

Beweisen oder widerlegen Sie \(5P.\): Sei X, Y ⊆ P, X ∩ Y = {}: conf\({X}, {Y}\) ⇔ conf\({Y }, {X}\)

A:

Widerlegen mit Gegenbeispiel:

Annahme:

sup\(P1\)=2/6

sup\(P2\)= 3/6

sup\(P1,P2\)=2/6

conf\(P1,P2\)= 2/6 : 2/6 = 1

conf\(P2,P1\) = 2/6 : 3/6 = 0,66

-&gt; conf\(P1,P2\) != conf\(P2,P1\)

Geben Sie eine allgemeine Definition für ein typisches Recommendersystem an. \(2P.\)

A:

Recommenderservices \(-dienste\) sind Marktinformationssysteme und -kanäle basierend auf beobachtetem Benutzerverhalten. Dabei bestehen Recommendersysteme aus Bündeln von \(komplementären\) Recommenderservices.

Erläutern Sie allgemein was man unter einer Warenkorbanalyse versteht und welche Schritte für eine erfolgreiche Warenkorbanalyse durchgeführt werden müssen. \(5P.\)

A:

Ein Warenkorb enthält alle \(Informations-\) Produkte, die ein Benutzer, während eines/r einzelnen Besuchs \(Session\) gekauft hat. Die Warenkorbanalyse berechnet für jedes \(Informations-\) Produkt die Wahrscheinlichkeit, ein anderes Produkt zu kaufen, wenn wir dieses Produkt bereits gekauft haben.

Schritte:

* Loggen von ausführlichen POS bzw. Webserver
* Tägliche Analyse der Protokolle zum Erstellen und Aktualisieren von Warenkörben
* Generieren von Empfehlungen aus Warenkörben und Kaufhistorien

Definieren und erläutern Sie die Begriffe „Support" und „Confidence". \(2\*2=4P.\)

A:

Siehe oben.

Gegeben seien die folgenden Warenkörbe: {a, b, d}, {d, f}, {b, e}, {b, d, e}, {a, b, d, e}, {a, c, d, f}. Der Minimumsupport smin = 1/2 , die Minimumkonfidenz cmin = 3/4 . Errechnen Sie die Supportwerte für die entstehenden Itemmengen nach dem apriori-Algorithmus. Markieren Sie dabei für diejenigen Itemmengen, die aus der Betrachtung gelöscht werden. Führen Sie alle möglichen Schritte aus. \(10P.\)

A:

Sup\(a\)= 3/6; Sup\(b\) = 4/6; Sup\(c\) = 1/6; Sup\(d\) = 5/6; Sup\(e\) = 3/6, Sup\(f\) = 2/6 -&gt; Eliminierung {c}, {f} -&gt; L1=

C\_2 = {a,b}, {a,d}, {a,e}, {b,d}, {b,e}, {d,e}

Sup\(a,b\) = 2/6 ; Sup\(a,d\)= 3/6; Sup\(a,e\)= 1/6; Sup\(b,d\) = 3/6; Sup\(b,e\)= 3/6 ; Sup\(d,e\)=2/6

**Join**

{a, b, d} -&gt; {a,b}, {a, d}, {a, b} -&gt; in L\_2

~~{b, d, e}~~ -&gt; {d, e} **nicht** in L\_2

C3={a,b,d}; L\_3 = {}

L =

Conf\(a,d\) -&gt; 3/6 : 3/6 = 1

~~Conf\(d,a\) -&gt; 3/6 : 5/6 = 3/5~~

Conf\(b,d\) -&gt; 3/6 : 4/6 = 3/4

~~Conf\(d,b\) -&gt; 3/6 : 5/6 = 3/5~~

Conf\(b,e\) -&gt; 3/6 : 4/6 = 3/4

Conf\(e,b\) -&gt; 3/6 : 3/6 = 1/1

**Assoziationsregeln** a-&gt; d, b -&gt; d, b-&gt;e, e-&gt;b

Beurteilen Sie das Verfahren kritisch. Nennen Sie je zwei Vor- und Nachteile. \(2\*2=4P.\)

A

**Vorteile:**

1. Keine Wahl von Cut-Methoden notwendig
2. Finden interessanter Warenkörbe mit mehr als zwei Artikeln möglich

**Nachteil:**

1. Verfahren berücksichtigt keine statistischen Zusammenhänge
2. Erfordert die Vorgabe zwei externen, nicht aus dem Modell begründbare Parameter s\(min\) und c\(min\)

_Use Case: Sie arbeiten für Jupiter, einen großen, deutschlandweit operierenden Elektronikanbieter, der sein Online-Geschäft ausbauen möchte. Sie sollen für die Abteilung Haushaltsgeräte einen AR-basierten Recommenderdienst aufbauen: Zusatzartikel, die beim Kauf eines Kühlschrankes oft dazu erworben wurden, sollen künftig auf der Produktseite empfohlen werden. Ohne Use Case Bezug max. die Hälfte der Punkte!_

F: _Welche Daten müssen Sie sich von der IT-Abteilung geben lassen? Erstellen Sie eine kurze Liste der benötigten Daten! Welche hiervon sind personenbezogen?_ \(4P.\)

A:

* Transaktionsdaten vergangener Verkäufe mit Produkt-ID der verkauften Produkte von Jupiter.
* Produktdaten, die ein Mapping der Produkt-ID auf weitere Produktinformationen z. B. Name des Produkts, Preis und Kurzbeschreibung ermöglicht.
* Produktdaten sind nicht personenbezogen. Transaktionsdaten sind personenbezogen können aber anonymisiert sein für die Verwendung im Recommender.

Für eine Regel \(Kühlschrank → Zusatzartikel\) kennen Assoziationsregel-Recommender zwei zentrale Kennzahlen. Geben Sie jeweils die mathematische Definition an, erklären Sie alle Bestandteile. Geben Sie eine Interpretation der Kennzahlen. \(2\*\(2+1\)=6P.\)

A:

Menge I = Kühlschrank, Eiswürfelbehälter, Weinregal, Kühlschrankthermometer ... von Items

Eine Reihe T ={ {Kühlschrank, Weinregal, Kühlschrankthermometer}, {Kühlschrank Eiswürfelbehälter} .....} von Transaktionen

$$
\text { support }(X)=\frac{|\{t \in T \mid X \subseteq t\}|}{|T|}
$$

$$
\operatorname{confidence}(X, Y)=\frac{\operatorname{support}(X \cup Y)}{\operatorname{support}(X)}
$$

Support\(Kühlschrank\): Wie oft wurde Kühlschrank gekauft.

Confidence \(Kühlschrank, Weinregal\) : Wie oft wurden Kühschrank und Weinregal zusammen gekauft, wenn Kühlschrank gekauft wurde.

_Sie haben den Apriori-Algorithmus kennen gelernt. Sie ändern diesen Algorithmus nun so ab, dass jeweils eine der beiden Kennzahlen von Teil 1 entfällt \(also zwei zu untersuchende Fälle: Kennzahl 1 entfällt, Kennzahl 2 entfällt, aber nie beide gemeinsam!\). Argumentieren Sie für beide Fälle: Was würde passieren? Funktioniert der Algorithmus noch? Welche weiteren Annahmen müssen Sie treffen, damit er noch funktioniert? Wie sehen die Resultate aus? \(Denken Sie an den Use Case Bezug!\)_ \(4+4=8P.\)

A:

Gemeint sind wohl Minimum Support und Minimum Confidence. Würde man keinen Minimum Support definieren, d. h. Minimum Support = 0, so würde Jupiter sehr viele gültige Assoziationsregeln generieren, die aber selten vorkommen.

Außerdem würde sich die Rechenintensität erhöhen, da alle Kombinationen der Produkte aus den Warenkörben von Jupiter-Kunden betrachtet werden würden.

Würde man keine Minimum Confidence definieren, d. h. Minimum Confidence = 0, würde man sehr viele Regeln, definieren, wovon viele „sehr unsicher" / sehr unverlässlich sind. \(Folien AGD, Kap. 6\)

Im Ergebnis wären die Empfehlungen des AR trivial und unbrauchbar sein, da jede Transaktion, bei der ein Kühlschrank gemeinsam mit einem Produkt gekauft worden wäre, grundsätzlich für Empfehlungen berücksichtigt wurde, unabhängig des Vorkommens dieser Kombination.

Da es sich bei Jupiter um einen großen Versender handelt, sind auch die generierten Itemsets groß, was zu Laufzeitproblemen des Apriori-Algorithmus führen wird.

\(Ohne Use Case Bezug\) Sie haben folgende Regel kennen gelernt: Seien X und Y Itemmengen und s eine Schranke. Sei $$\operatorname{support}(X) <s$$. Dann gilt: $$\forall Y \supseteq X: \operatorname{support}(Y) <s$$

F: _Interpretieren Sie diese Regel. \(2P.\)_

A:

Item $$X$$ wird weniger als $$s$$ mal gekauft. Dann werden alle Itemmengen $$Y$$ wo $$X$$ vorkommt ebenfalls weniger als $$s$$ mal verkauft.

Erreicht eine Itemmenge $$X$$ den Mindestsupport $$s$$ nicht, so kann auch keine Ihrer echten / unechten Obermengen den Mindest-Support erreichen, da diese mindestens so selten in den Transaktionen vorkommen.

F: _Beweisen oder widerlegen Sie diese Regel. \(5P.\)_

A:

Aussage stimmt.

Item $$X$$ kommt weniger als $$s$$-Mal vor. Durch Hinzunahme eines weiteren Produktes kommt $$X$$ gemeinsam mit $$X$$ ebenfalls weniger als $$s$$-Mal vor, da $$Y$$ mit $$X$$ nicht öfter vorkommen kann, als $$X$$ allein vorkommt.

