# Clustering

* Was ist der Vorteil von hierarchischem Clustering?
  * hierarchisches Clustering kommt ohne exogene Parameter aus. Anders als $k$ bei k-Means oder $T$ bei Birch.
* Welche Clustering-Verfahren kennen Sie?
  * Partionierende Verfahren:
    * $k$-means bzw. Variante CLARANS, BIRCH
      * **CLARANS:** $k$-means ist für sehr große Datenbestände ungeeignet, da sich in jeder Iteration die Medoide verändern. Mit jeder Iteration müssen also alle Datenobjekte neu mit Medoid verglichen werden. CLARANs löst das Problem durch Aufbau eines Graphen. Graph wird dann genutzt um auf einem Sample von Nachbarn Clusterings zu ermitteln.
  * Divisiv hierarchische Verfahren:
    * DIANA
  * Agglomerativ hierarchisches Verfahren:
    * Ohne Name
* Gegeben Szenario X, welche Clustering-Verfahren sind sinnvoll, und warum?
* $**k$-means / CLARANS:**
  * **Vorteil:**
    * $k$-means ist ein iterativer Ansatz → Man kann Abbruchkriterium dynamisch festlegen
    * $k$-means konvertiert typischerweise recht schnell. → Gut, wenn Performance eine Anforderung ist
  * **Nachteil:**
    * Es ist nicht garantiert, dass man globale Optima findet → Unterschiedliche / mehrmalige Initialisierung löst Problem etwas.
    * Nur anwendbar, wenn \(Cluster-\) Mittelpunkte definiert ist → Problematisch bei kategorischen Daten
    * Problematisch für Daten mit Rauschen / Ausreisern → Man braucht Strategien, um damit umzugehen.
    * Ungeeignet für nicht-konvexe Mengen → Vgl. two-moons Beispiel
  * **BIRCH**
    * Verbessert k-means hinsichtlich Initialsierung. Man baut eine hierarchische Repräsentation des Datenbestands auf. Daraus lässt sich Initialisierung für $k$-means ablesen.
    * **Vorteil:**
      * Nutzt den vorhandenen Arbeitsspeicher voll aus, um Zugriffskosten auf DB zu minimieren.
      * Die Zuordnung zu einem Cluster ist lokale Entscheidung → Es müssen nicht alle Objekte / Cluster untersucht werden
      * Inkrementelle Methode, die nicht die Kenntnisse aller Objekte erfordert.  → Einsetzbar auf Datenströme \(vgl. [wikipedia](https://de.wikipedia.org/wiki/BIRCH)\)
    * **Nachteil:**
      * Nur anwendbar, wenn \(Cluster-\) Mittelpunkte definiert ist → Problematisch bei kategorischen Daten
    * \[Weitere...\]
* Erklären Sie Clustering-Verfahren XY. Warum funktionieren herkömmliche Clustering-Verfahren in hochdimensionalen Merkmalsräumen nicht? Skizzieren Sie eine mögliche Lösung.
* $**k$-means:**

  **Probleme** von $k$-means im Hochdimensionalen:

  \[Probleme in hochdimensionalen Räumen → Teil 2 noch abwarten\]

  **Lösung** von $k$-means im Hochdimensionalen:

  * Verwendung **link-basierter Methode**.
  * Vorgehen: 1. Punkt wird dem medoid zugeordnet, zudem der Abstand am kleinsten ist. 2. D. h. als Abstand zu einem Cluster würde man die Zahl der gmeinsamen Links heranziehen. 3. Etwa: Datenobjekte sind Transaktionen Seeds sind ebenfalls Transaktionen Abstand - groß gdw. wenn wenige gemeinsame Nachbarn gem. Jaccard-Koeffizient bestehen.

    \[...\]

* Erklären Sie, warum Clustering mit kategorischen Attributen besonders ist?
  * Anzahl von kategorischen Attributen ist tendenziell groß z. B. Sortimentgröße → Featurevektoren mit sehr hoher Dimensionalität
  * Bei kategorischen Daten reicht es nicht einfach aus Übereinstimmung von Einkäufen zu vergleichen z. B. Kunde 1 kauf Kaviar 1, Kunde 2 kauft Kaviar 2. Man würde nicht erkennen, dass beide Kaviar kaufen.
  * Mengen der items, die Cluster bestimmen, haben unterschiedliche Größen z. B. Windeln vs. Luxusartikel im KDW. Schwellwert 1 bei Kleinkindsortiment / größerer bei Luxusartikel
  * Abstandsmaße sind zu schlicht z. B. Abstand = 0, wenn Wert identisch oder schwer zu definieren z. B. Taxonomie erforderlich.
* Warum ist Link-basiertes Clustering hier hilfreich?
  * **Beispiel:** Premiumkunden haben für sich genommen nur wenige Itemsets z. B. Lachs 1 vs. Lachs 2 gemeinsam in Ihren Transaktionen.
  * Durch Hinzunahme anderer Kunden, die gemeinsame Artikel kaufen d. h. gemeinsame Nachbarn \(Link\) bestehen, kann man sehen, ob die beiden ursprünglichen Kunden ähnlich sind.
  * Das Konzept der Nachbarschaft hilft also beim Clustering.
* Wann sind link-basierte Cluster-ing-Methoden sinnvoll?
  * "unförmige" Cluster z. B. langgezogen oder konkav z. B. stark Sichel-förmig geformt
  * unterschiedlich große Cluster \(solange Dichte nicht unter einem Schwellwert liegt\)

**Offene Fragen**

* Unterschied zwischen Clustering und Classifikation?
* Was passiert, wenn $k$ nicht gegeben ist.
* Welchen Vorteil hat es, wenn Medoid ein Datenpunkt sind? \(Eigene\)
* Wann könnte link-basierte Methode sinnvoll sein.
* Warum sollen Seeds weit auseinander liegen? \(Eigene\)
* Warum soll Medoid Datenobjekt sein? \(Eigene\)

Erkläre CLARANS "

* Ein Knoten ist Ausgangspunkt
* Wir betrachten ausgehend des Knoten eine bestimmte Anzahl an Nachbarn
* Für jeden dieser Knoten können wir durch Criterion Function die Güte des Clusterings bestimmen
* Der Nachbarknoten mit kleinster Criterion Function wird ausgewählt

Parameter:

* Anzahl der betrachteten Nachbarn
* Anzahl der Runs
* Abbruchkriterium

"

Erkläre BIRCH

* Partitionierendes Verfahren
* Aufbau eines Modells \(CF-Tree\), der Datenverteilung beschreibt
* Weniger Speicherplatz
* I/O Kosten wachsen linear mit der Größe des Datenbestands, wenn CF-Tree in Hauptspeicher passt
* Eine Iteration liefert bereits Clustering
  * Optionale Schritte verbessern Ergebnis
* Informationen \(Clustering Features\)0 werden zu jedem Cluster mitgeführt

