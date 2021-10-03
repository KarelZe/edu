# Statistische Grundlagen

## Kapitel 2

* ‚Kategorisierung von Daten‘ \(erste Folie dieses Kapitels\) sprechend wiedergeben können.
* Gegeben Aggregationsfunktion X, ist sie distributiv/algebraisch/holistisch/self-maintainable.

  * **Algebraisch**: Es gibt Funktion $$G$$, die $$M$$-Tupel liefert, und $$H$$, so dass $$F\left(\left\{X_{i, j}\right\}\right)=H\left(\left\{G\left(\left\{X_{i, j} \mid i=1, \ldots, I\right\}\right) \mid j=1, \ldots, J\right\}\right)$$. $$M$$ ist apriori bekannt, ebenso der Typ der Tupel. Zwei Schritte mit Zwischenergebnis. Darauf kann man die Funktion $$G$$ anwenden, die dann das Endergebnis liefert. Zwischenergebnis hat nicht die gleiche Struktur wie das Endergebnis. Es handelt sich um Tupel bestimmter Größen. 
  * **Holistisch**: Man kann keine Beschränkung des Speicherbedarfs für Sub-Aggregate angeben.
  * **Distributiv**: Es gibt eine Funktion $$G$$, sodass: $$F\left(\left\{X_{i, j}\right\}\right)=G\left(\left\{F\left(\left\{X_{i, j}|=1, \ldots,|\right\}\right) \mid j=1, \ldots, J\right\}\right)$$. Man kann die Ergebnisse der Aggregationsfunktion auf Teilmengen berechnen und aus diesen Teilergebnissen dann das Gesamtergebnis erlangen, ohne dass weitere Informationen gespeichert werden müssen. 
  * **Self-maintainable** \(Eigenschaft ist bezüglich Einfügens oder Löschen\): wenn nach einer Änderung der Daten der neue Wert der Aggregationsfunktion aus dem alten Wert und den Änderungen berechnet werden kann.

  * Distributive und algebraische Aggregationsfunktionen sind vorteilhaft, weil Aggregation schrittweise bzw. parallel ausgeführt werden kann.

  * min, max, count → distributiv
  * average → algebraisch
  * median, modus → holistisch

* Sehen Sie einen allgemeinen Zusammenhang zwischen distributiv/algebraisch/holistisch auf der einen und self-maintainable auf der anderen Seite? \(Es gibt einen.\)
  * Da bei holistischen Aggregatfunktionen sowieso auf die gesamte Datenmenge zurückgegriffen werden muss, können diese nicht _self-maintainable_ sein.
  * Bei distributiven und algebraischen Aggregatfunktionen kommt es immer auf die Situation an - Welche Art von Operationen findet hier statt und welche Werte werden eingefügt oder gelöscht.

* Warum ist Median holistisch?
  * Weil der Median der Wert ist, der in der Mitte steht ist. Das heißt es müsste jeweils eine sortierte Liste ausgegeben werden, und anschließend aus der Anzahl der Elemente der mittlere Wert berechnet werden. Da die einzelnen Schichten aber nur intern sortiert sind kann man keinen Schluss darauf ziehen, wie der Median des gesamten Datensatz aussieht.

* Wie groß ist die Entropie, wenn alle Klassen gleich häufig sind? Schreiben Sie dafür eine allgemeine Formel hin.

  $$H(S)=-\sum_{j} p_{j} * \log p_{j}=-\sum_{i=1}^{n} \frac{1}{n} * \log \frac{1}{n}=-n *\left(\frac{1}{n} *\left(\log 1-\log n\right)\right)=-1 *\left(0-\log n\right)=\log n$$

  * $$H(S) \in (0;\infty)$$

* Welche Möglichkeiten kennen Sie, die Stärke des Zusammenhangs zwischen zwei Zufallsvariablen zu quantifizieren?
  * Kovarianz:
  * $$\text { Cov }(x, y)=\frac{\sum{i=1}^{N}\left(x{i}-\bar{x}\right)\left(y_{i}-\bar{y}\right)}{N-1}$$
  * Korrelation
  * Regressionsanalyse

* Welche statistischen Tests kennen Sie? Wofür genau sind die einzelnen Tests gut?
  * Chi-Quadrat-Test:  Test, ob zwei Variablen $$X$$ und $$Y$$ unabhängig sin.
  * Kolmogorow-Smirnow-Test: Test, ob zwei Verteilungen übereinstimmen.
  * Wilcoxon-Mann-Whitney-Test / U-Test: Test, ob Mediane zweier Verteilung statistisch signifikant sind.
    * H0-Hypothese: identischer Median der Verteilungen
    * H1-Hypothese: Die Mediane der Verteilungen unterscheiden sich nicht.

* Was bedeutet Dimensionality Reduction? Welche Möglichkeiten der Dimensionality Reduction kennen Sie?
  * **Dimensionality Reduction:** Ansatz, um die Anzahl der Attribute zu reduzieren.
  * **Abgrenzung zu Numerosity Reduction:** Numerosity Reduction reduziert die Anzahl der Datenobjekte
  * PCA: Verringerung der Attribute, indem man die Attribute auf einen Unterraum projiziert.  Die Datenobjekte werden auf eine Hyperebene projiziert, für  diejenige der Datenverlust minimal ist.  Auswahl gelingt durch Bestimmung der Eigenvektoren. Dimensionen, für welche die Varianz maximal ist, werden beibehalten.
  * Singular Value Decomposition \(SVD\)
  * Latent Semantic Indexing \(LSI\)

* Welche Diskretisierungsverfahren kennen Sie? Wie findet man jeweils den besten Merge bzw. Split?
  * Merge \(z. B. Chi-Merge\)- oder Split-basierte Diskretisierung
  * Besten Split mittels Entropie finden für $$S$$ in $$S{1}$$ _und_ $$S{2}$$ mit Begrenzung $$T$$:
  * $$\text{Entropie}\text {Split}(S, T)=\frac{\left|S{1}\right|}{|S|} \cdot\text{Entropie}\left(S{1}\right)+\frac{\left|S{2}\right|}{|S|} \cdot\text{Entropie}\left(S{2}\right)$$
  * Besten Merge finden, indem man benachbarte Intervalle zu einem größeren Intervall zusammenlegt, solange bis Abbruchkriterium erreicht wird.
  * **Chi-Merge**
    * Finde 'beste' benachbarte Intervalle und führ sie zu größerem Intervall zusammen. Wiederhole dies bis ein Abbruchkriterium erreicht ist.
    * Jeder Wert ist zunächst ein Intervall
    * $$\chi^2$$- Test für alle Paare benachbarter Intervalle → Folgen der gleichen Verteilung?
    * Menge benachbarter Intervalle mit kleinstem $$\chi^2$$-Wert
    * Wiederholung bis Abbruchkriterium erreicht ist.

