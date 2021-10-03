# Indexstrukturen

Warum kann man für räumliche Anfragen nicht ohne weiteres auswerten, wenn man für jede Dimension separat einen B-Baum angelegt hat?
  * Da die Attribute der einzelnen Tupel unterschiedlich sind. Man muss separate Werte auswerten lassen, um Informationsbedürfnis zu sättigen.
  * Man kämpft mit Informationsverlust. Erstellt man für jede Dim einen eigenen Baum, so bekommt bekommt bei Auswertung der nearest-neighbour je Baum ggf. ursprüngliches Tupel z. B. \(Alter, Geschlecht\) nicht mehr zusammen.

Wie ist der R-Baum aufgebaut?
  * Aufbau ähnlich zu kd-Baum. Einzelne Knoten des Baums entsprechen unterschiedlichen Ausschnitten des Raums.
  * Ausschnitt eines Raums, der einem Knoten entspricht, ist in Ausschnitt des Raums, der dem übergeordneten Knoten entspricht, enthalten.

  **Beispiel:**
  * Dunkelblaues Rechteck ist _Minimum Bounded Rectangles_ der eingeordneten Datenobjekte.
  * Hellblaues Rechteck ist _Minimum Bounded Rectangle_ aller blauen Punkte.
  * Anfrageauswertung analog zu kd-Baum. D. h. Aufbau Queue durch Einfügen des Wurzelknotens etc.

Wie funktioniert die Suche nach dem nächsten Nachbarn mit dem R-Baum? \(Frage ich ganz gerne u. a. dann, wenn die Prüfung stockend verläuft...\)
  * Ähnlich dem kd-Baum mittels Priority Queue.

Was ändert sich, wenn die Objekte eine räumliche Ausdehnung haben? Dto. Anfragen.
  * Man splittet dann in mehrere Dimensionen.

* Stören uns Überlappungen von Knoten des R-Baums? Wenn ja, warum?
  * Ja, Überlappungen sind problematisch. Man muss dann mehrmals im Baum nach unten steigen. D. h. der Aufwand vergrößert sich.

Wie unterscheiden sich R-Baum, kD-Baum und kDB-Baum?\(Wie Balancierung für kDB-Baum funktioniert, muss man für Prüfung nicht wissen.\)
* kDB-Baum ist ein balancierter kD-Baum d. h. alle Knoten liegen etwa auf derselben Hierarchieebene.
* R-Bäume partionieren den Datensatz nicht. D. h. kD-Bäume lassen keine Überlappungen zu, wohingegen Überlappungen der minimum bounding rectangle beim R-Baum möglich sind.
* **KdB-Baum**
  * Kombination von kd- und B-Baum
  * Balancierter Baum
  * Wurzel enthält mehrere Objekte
  * Ineinander enthaltene Regionen können im gleichen physischen Knoten sein
  * Physischer Knoten enthält mehrere logische Regionen und nicht mehr pro Split-Dimension.
  * **Vorteil**: Abstand Daten und Wurzel immer gleich. Pro pyhsischem Knoten genau eine Speicherseite dadurch effizienter Zugriff.
  * **Nachteil**: Reorganisation sehr komplex.

    kd-Baum

  * Split-Richtung: eine Dimension nach der anderen
  * Daten kompakt dargestellt
  * Ausschnitte des Raums entsprechen unterschiedlichen Knoten, solange diese Knoten nicht ineinander enthalten sind, überlappen sie sich nicht
  * **Nachteil**: nicht balanciert. Man kann entweder von oben/unten kommend aufbauen → In beiden Fällen keine Garantie für balancierten Baum.
  * Tiefe Baum: Anzahl Splits
  * Unterscheidung zwischen logischen und physischen Knoten

Wie funktioniert Einfügen in den R-Baum, inklusive Split?
  * **Kapazität vorhanden:** Bei mehreren möglichen Kindern wird in den Knoten eingefügt, dessen Fläche sich am wenigsten vergrößert.
    * Punkt fällt in Zone genau eines Kind-Knotens → unproblematisch.
    * Punkt fällt in Überlappung von Zonen von Kind-Knoten → optimale Entscheidung schwierig bis unmöglich ohne weitere Hinweise.
    * Punkt fällt in keine Zone eines Kind-Knotens → bei mehreren möglichen Kindern in den Knoten, dessen Fläche sich am geringsten vergrößert
  * **Keine Kapazität vorhanden:** Man muss splitten. Gesplittet wird zwischen Kindern mit größtem Abstand.
  * Dann nimmt man Dimension mit größten Abstand zwischen beiden Objekten und splittet dann entlang im rechten Winkel zur x-Dimension, wenn x-Dimension am längsten ist.
  * **Skizze**:
    * Kapazität von Knoten ist 5. D. h. Es können keine weiteren Objekte eingefügt werden. Man splitet orthogonal zur X-Achse, da hier im Beispiel die rot umrandeten Punkte am entferntesten liegen. Danach hat jeder Knoten wieder ausreichend freie Kapazität. Nämlich zwei oder drei.

Was für Anfragen unterstützen die diversen räumlichen Indexstrukturen?
  * Punktanfragen
  * Bereichsanfragen
  * NN-Anfragen

Warum werden bei der NN-Suche nur genau die Knoten inspiziert, deren Zonen die NN-Sphere überlappen?
  * Weil alle anderen Knoten in der Priority Queue weiter hinten liegen und deshalb nicht "entpackt" werden müssen.

Welche Classifier kennen Sie? \(Inzwischen haben wir drei Möglichkeiten kennengelernt; es kommen voraussichtlich noch weitere.\)
  * Lineare Klassifikation
  * Entscheidungsbäume
  * 1-Rules

Was ist der Maximalabstand im Einheitsraum?
  * Anzahl der Dimensionen

Wie werden Bereichsanfragen umgesetzt?

Warum lässt man Überlappungen zu bei R-Baum?

Warum nimmt man Abstraktion in logische Knoten und und physische Knoten vor. Wie ist das Verhältnis beider zueinander?

