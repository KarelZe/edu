# Evaluation

* Was ist die „10-fold cross validation“?
  * Variante der _Repeated-Hold-Out-Methode_
  * Partitioniere das Datenset in $k = 10$ Partitionen

    Verwende grundsätzlich $k−1$ Partitionen als Trainingsset und die übrige Partition zur Validierung.

  * Wiederhole Durchlauf  $k$-mal, wobei jeweils die nächste Partition der Validierung und die übrigen Partitionen dem Training dienen. Man erhält damit $k$ Testfehler und nutzt den gesamten Datenbestand zum Training!

Wie haben wir die Erfolgsquote definiert?
* $\frac{TP+TN}{TP+TN+FP+FN}$
* Was ist ein Lift Chart? Wie unterscheidet es sich von der ROC Kurve?
* **Lift-Chart** → typischerweise fallend
* Obacht, wird im Skript nicht **Gain-Chart** vorgestellt? \(S. 38\) \(Siehe z. B. [https://www3.nd.edu/~busiforc/Lift\_chart.html](https://www3.nd.edu/~busiforc/Lift_chart.html)\) Sieht Chart anders aus?
* **Lift Chart \(Gain Chart\)** ist ein Indikator für die Güte des Vorhersageverfahrens, denn je größer der Buch bis Maximum, desto besser ist der Classifier.
* **ROC-Kurven \(Receiver Operator Characteristic\)** setzen die True Positive Rate mit der False Positive Rate ins Verhältnis. Fläche unter der Kurve zeigt die Güte des Classifiers an. → wachsend

Was für Fehlerarten gibt es bei Vorhersagen von Klassenzugehörigkeiten?
  * Bias ist der Fehler ausgehend von falschen Annahmen im Lernalgorithmus.
  * Varianz ist der Fehler, der verursacht wird durch die Begrenztheit des Trainingsdatenbestands.
  * False Negative / False Positive → Vorhersage ist falsch
  * True Negative / True Positive → Vorhersage ist richtig

Was für Kennzahlen kennen Sie, die diese Fehlerarten sämtlich berücksichtigen?
  * Kappa-Koeffizient: Der Kappa-Koeffizient vergleicht die Prognosequalität eines Klassifizierers durch Vergleich mit einem Referenz-Klassifizierer.
  * \(Konfusionsmatrix\)

Was ist Unterschied zwischen Kovarianz und Correlation Coefficient?
  * $\text { cov }\(x, y\)=\frac{\sum_{i=1}^{N}\left\(x_{i}-\bar{x}\right\)\left\(y\_{i}-\bar{y}\right\)}{N-1}$
  * $\operatorname{corr}\(x, y\)=\frac{\operatorname{cov}\(x, y\)}{\sigma_{x} \cdot \sigma_{y}}=\frac{E\[\(x-\bar{x}\) \cdot\(y-\bar{y}\)\]}{\sigma_{x} \cdot \sigma_{y}}=\frac{\sum_{i=1}^{n}\left\(x_{i}-\bar{x}\right\)\left\(y_{i}-\bar{y}\right\)}{\sqrt{\sum_{i=1}^{n}\left\(x_{i}-\bar{x}\right\)^{2} \cdot \sum_{i=1}^{n}\left\(y\_{i}-\bar{y}\right\)^{2}}}$
  * Obacht, im Skript wird corr jeweils durch $$n-1$$ geteilt.
  * Korrelationskoeffizient ist normiert.
  * Kovarianz und Korrelation sind gleich, wenn z-standardisierte Daten vorliegen \(d. h. zero mean, var. von 1\)

    Video zu Kovarianz – Korrelation - Korrelationskoeffizient:

    Teil 1: [https://www.youtube.com/watch?v=X7eeyRX35wM](https://www.youtube.com/watch?v=X7eeyRX35wM)

    Teil 2: [https://www.youtube.com/watch?v=hUmxhN5Uuqg](https://www.youtube.com/watch?v=hUmxhN5Uuqg)

Warum kommt bei der informational loss Funktion die Logarithmusfunktion zur Anwendung?
  * $$-\log_{2} p_{i}$$, wobei $i$ die tatsächliche Klassenzugehörigkeit ist.
  * Man kann damit den Verlust gut abbilden. Bei Vorhersage 1 ergibt Verlust 0 und bei Vorhersage 0,001 ergibt Verlust 9,9658.


