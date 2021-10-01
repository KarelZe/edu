# Identifikation von Ausreißern

* Welche Definitionen von Outlier kennen Sie?
  * Intuitiv: Outlier ist definiert als Element des Datenbestands, das in bestimmter Hinsicht vom restlichen Datenbestand erheblich abweicht.
  * Abstandsbasierter Outlier: Objekt $O$, das in Datenbestand $T$ enthalten ist, ist ein DB\(p, D\)-Outlier, wenn der Abstand von $O$ zu min. $p$ Prozent der Objekte in $T$ größer ist als $D$.
  * Dichtebasierte Outlier: Punkt ist ein Outlier, wenn er in irgendeinem niedrigdimensionalen Teilraum in Region mit ungewöhnlich niedriger Dichte liegt.
* Gegeben die abstandsbasierte Definition von Outlier, welche Techniken zur Ermittlung der Outlier kennen Sie?
  * **Definition**: Siehe oben.
  * **Techniken**:
    * **Index-basierte Ermittlung:** k-nearest neighbour Auswertung für jedes Datenobjekt. Liegen mehr Objekte innerhalb der Umgebung $Q$ von $O$, die aufgespannt wird durch Distanz $D$, als einem Schwellwert $p$, dann handelt es sich nicht um einen Ausreißer. \(vgl. Knorr & NG\)
    * **nest-loop Verfahren:** Teilen des gesamten Datensets in zwei Hälften, genannt erster und zweiter Array. Man liest dann das Datenset in die zwei Arrays ein und berechnet die Distanz zwischen jedem Objektpaar oder tupel. Für jedes Objekt t im ersten Array zählt man, ob die D-Nachbarschaft errreicht wird. Das Zählen hört auf, wenn ein Tupel die D-Nachbarschaft für M überstiegen wird. \(vgl. Knorr & NG\)
    * **Zellenbasierte Verfahren:**
      * Man partioniert den Raum in würfelförmige Zellen mit Kantenlänge $D / 2 \sqrt{k}$. und ordnet jedes Tupel einer Zelle zu.
      * Man berechnet L1 Nachbarschaft. Das ist die Zelle selbst und die direkt umgebenden Zellen, wie viele Objekte in Zelle liegen \(→ Keine Betrachtung einzelner Objekte sondern Zelle\)
      * Man berechnet dann L2 Nachbarschaft. Das sind alle Zellen die genau oder weniger als 2 Diagonalenlängen entfernt sind.
      * Handelt es sich um Ausreiser? Zellen mit $≤ m$ Tupeln in L2 Nachbarschaft sind Ausreiser.
      * Handelt es sich um keinen Ausreiser? Zellen mit $≥1-p$ Tupeln in L1-Nachbarschaft sind **keine** Ausreiser.  \(TODO: Klärt Niklas\)
      * Restliche Zellen: Für alle Objekte innerhalb der gelben Zelle muss jeweils einzeln geprüft werden, ob Ausreiser vorliegt. z. B. nested loop mit gelber Zelle und Gesamtbestand \(→ Reduzierte Komplexität!\)
* Warum kann man beim Dichte-basierten Clustering nicht einfach die Dichte um die Punkte herum vergleichen und die mit der geringsten Dichte zurückgeben?
  * Local outlier factor von $p - \operatorname{lof}\(p\)$ - Durchschnitt der Verhältnisse der local reachability density von $p$ und der $k$ nächsten Nachbarn von $p$.
  * **Beispiel:** In Alaska wohnen fast alle Jäger weit ausseinander, In New York wenn \(z.B.: Trump\) weit weg /oben von allen wohnt ist es eine Besonderheit. - Besonderheiten im Vergleich zu übrigen Menschen um ihn herum, die in einfachen Mietskasernen wohnen.
* Sehen Sie einen Zusammenhang zwischen Clustering und Outlier Detection?
  * Clustering-Methoden können verwendet werden um Outlier zu finden.
  * **Beispiel:** Finden von Ausreisern mittels dem hierarchischen Ansatz Dendrogram.
* Welche Anomalien hochdimensionaler Merkmalsräume kennen Sie?
  * Nicht behandelt?
* Wieso funktionieren hierarchische Indexstrukturen in hochdimensionalen Merkmalsräumen nicht?
  * Datenobjekte in hochdimensionalen Räumen liegen weit auseinander.
  * Bezeichnet man als Curse of Dimensionality: In einem 2 oder 3-dimensionalen Raum sind die meisten Punkte nahe des Ursprungs. In einem hochdimensionalen Raum hingegen nicht mehr. Man braucht also deutlich mehr Punkte um den Raum auszufüllen.
* Was ist der Zusammenhang zwischen der Zelldichte und Outlier Detection in hochdimensionalen Merkmalsräumen? Wie groß sollten die Zellen sein?
  * Ein $k$-dimensionaler Raum wird partitioniert in würfelförmige Zellen der Länge $D / 2 \sqrt{k}$ \(k - Dimensionalität\). Zelle skaliert damit mit Dimensionalität des Raums.
* Geben Sie die Klassifizierung aus der LV in "interessante" und "weniger interessante" Objekte wieder.
  * **Nicht-Trivialer Ausreiser:** $P$ ist ein nicht-trivialer Outlier in Attribut-Raum $\mathcal{A}_{P}$, wenn  $P$ nicht Outlier in einem Teilraum $B \subset \mathcal{A}_{P}$ ist.
  * D. h. die Menge an Attributen, die Ausreiser identifiziert, ist die einfachst mögliche.
  * **Trivialer Ausreiser:** Man verwendet Menge aus Attributen, um Ausreiser zu erklären, obwohl ein Attribut weniger allein bereits den Ausreiser erklärt.
  * **Strong outlier:** $P$ ist strong outlier in  $\mathcal{A}_{P}$ \*wenn kein Outlier in irgendeinem $B \subset \mathcal{A}_{P}$\* existiert.
  * **Weak outlier:** nichttrivialer, aber kein strong outlier.

