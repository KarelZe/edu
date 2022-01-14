# Clustering

F: _Vergleichen Sie den k-means Clusteralgorithmus mit dem Basic Leader-Follower Algorithmus. Welches sind jeweils die Vor- und die Nachteile?_

A:

* Konzeptioneller Unterschied: K-means ist ein _offline_ Learning-Verfahren. Der Leader-Follower-Algorithmus ein _online_-Verfahren.
* Vorteil Basic Leader-Follower
  *   Anzahl der zu bildenden Cluster muss nicht a priori festgelegt

      werden.
* Vorteile $$k$$-means
  * $$k$$-means konvergiert typischerweise sehr schnell.
  * Konzeptionell einfach.
* Nachteil $$k$$-means
  *   Anzahl Cluster $$k$$ ist exogener Parameter → erfordert Kenntnis

      über Datenbestand
  * Ungeeignet für nicht-konvexe Mengen
  * Kann nicht gut mit Rauschen und Ausreißern umgehen
  *   Nur anwendbar, wenn (Cluster-) Mittelpunkt definiert ist →

      Schwierigkeiten bei kategorischen Daten.
* Nachteil Basic Leader-Follower
  * Keine stabilen Cluster

F: _Sie sind Leiter der technischen Abteilung der Universitätsbibliothek. Sie wollen den Empfehlungsdienst für Ihre Nutzer verbessern, indem Sie Nutzern einen Expertenstatus zuordnen (“Laie”, “Fortgeschrittener”, “Experte”). Diesen wollen Sie nutzen, um verbesserte Empfehlungen anzubieten (z.B. empfiehl nur Grundlagenwerke, falls der Nutzer Laie ist). Der Expertenstatus bezieht sich auf Fachgebiete, denen einzelne Bücher zuzuordnen sind._

_Durch freiwillige Angaben können Nutzer ihren Expertenstatus zu bestimmten Büchern oder Fachgebieten angeben, Sie erhalten also einige Daten durch die Nutzerangaben selbst._

_Welcher Clusteralgorithmus empfiehlt sich, um Ihren Nutzern Expertenstati zuzuordnen, und wieso? Welche Daten benötigen Sie zur Umsetzung des Clusterings und zur Nutzung der Ergebnisse für den Empfehlungsdienst?_

A:

* Die Anzahl der Cluster ist vorab bekannt mit 3 möglichen Ausprägungen. Aus diesem Grund sollte der iterative $$k$$-means-Algorithmus verwendet werden.
* Zum Clustering benötigt man Daten über die Nutzer. Diese könnten etwa die Anzahl bereits gelesener Dokumente, akademischer Grad, Selbsteinschätzung Vorkenntnisse o. Ä. sein.
* Zur Nutzung im Recommendersystem reicht dann das Wissen, in welchem Cluster sich ein Nutzer befindet, aus. Hierfür muss aber ein Mapping bestehen, um zu interpretieren, welches Cluster den „Experten" o. Ä. entspricht.

F: _Zur Kundendialogsteuerung sollen Entscheidungsbäumen eingesetzt werden. Erläutern Sie kurz, wie ein Entscheidungsbaum gelernt werden kann und wie er anschließend zur Dialogsteuerung verwendet wird._

A:

1. Zunächst ist ein Trainingsdatensatz und Testdatensatz mit Attributen zu ermitteln (z. B. 70 / 30). Attribute sind ggf. vorzuverarbeiten z. B. zu standardisieren. Weiterhin muss der Datensatz ein diskretes Klassenlabel (hier: Expertenstati), das vorhergesagt wird, enthalten.
2. Anhand der Entropie wird dann das Attribut mit dem höchsten durchschnittlichen Informationsgewinn ermittelt.
3. Man lernt den Baum solange weiter bis man keine Attribute mehr hat zum Erklären oder bis sich die Attribute nicht mehr verändern.
4. Der letzte Schritt kann das Pruning des gelernten Baums und die Evaluation des Baums auf nicht zum Training benutzte Testdaten sein. Gängige Maße zur Evaluation ist etwa die _Accuracy_. (Geyer-Schulz and Sonnenbichler 2017 S. 18, 19, 44)

F: _Wie evaluieren Sie, ob gelernte Entscheidungsbäume gut für Ihr System geeignet sind?_

A:

**Aufteilen in Trainings- und Testdaten / Training:**

Typischerweise wird der gesamte vorhandene Datenbestand in ein Trainingsset und ein Test Set gesplittet. Testdaten bleiben für das Training des Entscheidungsbaums außen vor. Der Baum wird auf Trainingsdaten gelernt.

Eine Variante ist **k-fold cross validation** mit folgendem Vorgehen:

* Partitioniere das Datenset in $$k$$ Partitionen
* Schätze $$k$$ hold-out Prädikator mit 1 Partition Validation Set und $$k - 1$$ Partitionen als Trainingsset, dann zweiter Durchlauf mit zweiter Partition zur Validierung und übrigen Partitionen zum Training. Analog wiederholen bis zum $$k$$-ten Durchlauf.

**Performance am Testdatensatz feststellen:**

* Das Test Set kann dann benutzt werden, um die prognostizierte Klasse z. B. Status Laie o. Ä. mit der tatsächlichen Klasse zu vergleichen. Die Performance lässt etwa mit einer Konfusionsmatrix darstellen. Typische abgeleitete Metriken sind _Precision_, _Recall_ und _Accuracy_.
* Obige Schritte mehrmalig wiederholen für statistische Sauberkeit. (Geyer-Schulz and Sonnenbichler 2017 S. 54)

F: _Wozu dient Clusteranalyse?_

A:

Entdecken einer natürlichen Struktur in Daten (Geyer-Schulz 2017 S. 6).

F: _Was ist eine Segmentierungsbase, was eine Segmentierungsmethode?_

A:

**Segmentierungsbasen**:

* Variablen oder Kriterien für die Segmentierung
* Auswahl auf Basis: Ziel der Segmentierung und des Marktes

**Segmentierungsmethoden**:

*   Methodenauswahl auf Basis: Ziel der Segmentierung und der

    Eigenschaften der Segmentierungsbasis.

F: _Nennen Sie je zwei Beispiele für (beobachtbare-nicht beobachtbare) × (allgemeine-produktspezifische) Basen._

A:

|                   | Allgemein       | Produktspezifisch  |
| ----------------- | --------------- | ------------------ |
| Beobachtbar       | Kulturell       | Benutzerstatus     |
|                   | Geographisch    | Benutzungsfrequenz |
|                   | Soziökonomisch  | Store Loyalty      |
|                   |                 | Situationen        |
|                   | …               | …                  |
| Nicht beobachtbar | Psychographisch | Psychographisch    |
|                   | Werte           | Nutzen             |
|                   | Persönlichkeit  | Wahrnehmung        |
|                   | Life-Style      | Präferenzen        |
|                   |                 | Absichten          |
|                   | …               | …                  |

F: _Wie bewerten Sie, ob sich zwei Datenpunkte ähnlicher sind als andere? Nennen Sie zwei Beispiel-Maße._

A:

**Normalisiertes, inneres Produkt:**

$$
s\left( x_{1},x_{2} \right) = \frac{x_{1} \cdot x_{2}}{\left. \  \parallel x_{1} \right.\  \parallel \left. \  \parallel x_{2} \right.\  \parallel}
$$

**Anteil der gemeinsamen Attribute:**

$$
s\left(x_{1}, x_{2}\right)=\frac{x_{1}^{T} x_{2}}{d}
$$

F: _Nennen Sie einen Anwendungsfall, wie Clusteranalyse in einem Recommenderdienst verwendet werden kann._

A:

**Movielens** - Anhand der Ratings aus dem each-movie dataset werden durch Clusteranalyse Geschmacks bzw. Interessengruppen gebildet. - Aus diesen Geschmacks-/Interessen Gruppen wird für Werbezwecke ein E-Mailverteiler automatisch erzeugt. - Auf Basis der Geschmacks- und Interessens-Gruppen werden neue Filmrechte erworben, die den Nutzern gefallen könnten. (Geyer-Schulz 2017 S. 7)

Use Case: Sie arbeiten für Jupiter, einen großen, deutschlandweit operierenden Elektronikanbieter, der sein Online Geschäft ausbauen möchte. Sie sollen für die Abteilung Haushaltsgeräte einen Recommenderdienst für Kühlschränke aufbauen: Ähnliche Kühlschränke sollen auf der jeweiligen Produktseite einander gegenüber gestellt werden, damit der Kunde diese besser vergleichen kann. Sie entscheiden sich deshalb für einen inhaltsbasierten Recommender auf Basis von Clusterverfahren. Ohne Use Case Bezug max. die Hälfte der Punkte!

F: _Definieren Sie als erstes den “Feature Space” für Kühlschränke, in dem Sie jeden Kühlschrank mit einem Vektor_ $$x_{i}$$ _beschreiben, also Kühlschrank 1 mit_ $$x_{1}$$_, Kühlschrank 2 mit_ $$x_{2}$$ _usw._ $$x_{i}$$ _ist dabei selbst ein k-dimensionaler Vektor mit_ $$k$$ _Eigenschaften des Kühlschranks. Geben Sie ein konkretes Beispiel mit 5 Dimensionen, wie ein_ $$x_{i}$$ _aussehen könnte und überlegen Sie sich, welche Eigenschaften Sie im Use Case abbilden wollen._

A:

5-Dimensionaler Feature Space mit den Dimensionen Energieeffizienz, Preis, Farbe, Einbaugerät und Eiswürfeleinheit.

Binäre / Nominale Attribute werden konvertiert in Abstand

* Einbaugerät und Einbaugerät: Ja → 1, Nein → 0.
* Preis wird standardisiert.
* Energieeffizienzklasse wird auf Skala von 0-1 gemappt.
* Farbe wird auf Skala von 0-1 gemappt.

| Dimensionen      | Kühlschrank 1 | Kühlschrank 2 | Kühlschrank 1 (standardisiert) | Kühlschrank 2 (standardisiert) |
| ---------------- | ------------- | ------------- | ------------------------------ | ------------------------------ |
| Energieeffizienz | A++           | C             | 0                              | 0.6                            |
| Preis            | 500 EUR       | 150 EUR       | 0.7                            | 0.2                            |
| Farbe            | Space Grey    | Weiß          | 0.8                            | 0                              |
| Einbaugerät      | Ja            | Nein          | 1                              | 0                              |
| Eiswürfeleinheit | Ja            | Nein          | 1                              | 0                              |

$$
S=\left(\left(\begin{array}{c} 0 \\ 0.7 \\ 0.8 \\ 1 \\ 1\end{array}\right),\left(\begin{array}{c}0.6 \\ 0.2 \\ 0 \\ 0 \\ 0\end{array}\right)\right)
$$

F: _Sie stellen einen Werkstudenten ein, der alle bei Jupiter gelisteten Kühlschränke mit den_ $$k$$ _Dimensionen erfasst. Sie erhalten als Ergebnis_ $$n$$ _\__$$k$$-dimensionale Vektoren __ $$x_1, x_2, \ldots, x_n$$. Beschreiben Sie kurz 3 Praxis-Probleme, auf die der Werkstudent Ihrer Erwartung nach bei der Aufbereitung der Daten stoßen wird.\_

A:

1. **Nominale Attribute** z. B. Einbaukühlschrank vs. Freistehend müssen in Dimension abgebildet werden.
2. **Standardisierung von Attributen** z. B. müssen einzelne Attribute standardisiert werden. Würde man z. B. Temperatur (z. B. 4 - 10) und Preis (100 - 2.000) als solches beim Abstandsmaß Euklidische Distanz verwenden, wäre das Distanzmaß stark verfälscht, weil Preis Abstand stark verfälschen würde.
3. **Fehlende Daten** z. B. könnte Produktbeschreibung der Hersteller unvollständig sein. Es braucht dann eine Strategie, um fehlende Werte aufzufüllen.
4. **Redundante Daten** z. B. können Kühlschränken in mehreren Farben angeboten wären. Mit Ausnahme der Farbe hätten diese Kühlschränke eine ähnliche Position im Raum, würden dann wegen der hohen Ähnlichkeit empfohlen werden. Eigentlich handelt es sich aber um eine „schlechte / triviale Empfehlung".
5. **Erfassungsfehler** z. B. kann Werkstudent Fehler bei Datenerfassung machen, was zu fehlerhaften Empfehlungen führt.

F: _Sie möchten nun die_ $$n$$ _Kühlschränke in_ $$c$$ _Partitionen trennen._ $$M_{1},\, m_{2},\,\ldots,\, m_{c}$$ _seien die c Clustermittelpunkte der Partitionen_ $$D_{1},\, D_{2},\,\ldots,\, D_{c}$$_. Welches Kriterium (exakt: Zielfunktion) setzen Sie an? Geben Sie die Formel mit der hier verwendeten Notation an und erklären Sie alle Bestandteile!_

A:

Man minimiert die Summe der Varianzen. Die _Criterion Function_ ist definiert als:

$$
J = \sum_{i = 1}^{c}\sum_{x_{j} \in D_{i}}\left. \  \parallel x_{j} - m_{i} \right.\  \parallel^{2},
$$

wobei $$m_{i}$$, der Mittelwert der Partition $$D_{i}$$, definiert ist als:

$$
m_{i} = \frac{1}{n_{i}}\sum_{x_{j} \in D_{i}} x_{j}.
$$

Man iteriert also über jeden Punkt im Cluster und berechnet die Distanz zu zum Cluster-Mittelpunkt und wiederholt das Vorgehen für jedes Cluster. Das Ergebnis wird aufsummiert. Oberhalb wird die quadrierte Norm verwendet. Liegt ein Punkt im falschen Cluster wird die Summe entsprechend groß. (Geyer-Schulz 2017 S. 25)

**Problem:** Man versucht eigentlich $$J$$ zu minieren (minimales Varianz-Kriterium). Hat man genauso viele Cluster wie Datenpunkte, dann ist $$J = 0$$ wenig aussagekräftig (Geyer-Schulz 2017 S. 29)

F: _Wie heißt der Fachausdruck für den “Abstand” zwischen zwei Datenpunkten_ $$x_{a}$$ _und_ $$x_{b}$$_? Schlagen Sie eine geeignete konkrete (!) Metrik für Ihren Feature Space (aus Teil 1!) vor._ $$x_{i,k}$$ _notiere dabei die Merkmalsausprägung_ $$k$$ _des Kühlschranks_ $$i$$_._

A:

1. Der Fachbegriff ist Ähnlichkeitsmaß. (euklidischer Abstand)
2. Verhältnis der gemeinsamen Attribute zur Anzahl der Attribute in $$x_{1}$$ oder $$x_{2}$$ „Tanimoto"-Distanz:

$$
s\left( x_{1},x_{2} \right) = \frac{x_{1}^{T}x_{2}}{x_{1}^{T}x_{1} + x_{2}^{T}x_{2} - x_{1}^{T}x_{2}}
$$

F: _Nach welchem Kriterium wählt der Algorithmus “iterative k-means” die optimale Anzahl der Cluster aus? Wie bestimmt man allgemein die optimale Anzahl der Cluster?_

A:

Die Anzahl der Cluster ist ein exogener Parameter beim $$k$$-means-Algorithmus. Muss also durch den Nutzer vorgegeben werden.

Ansätze, um das optimale $$k$$ zu finden:

$$H_{0}$$: es sind $$c$$ Cluster, da $$(J(c))$$\
$$H_{1}$$: es sind $$c+1$$ Cluster, da $$(J(c+1))$$.

$$
J(c)-J(c+1) \leq \varepsilon \text { und } P\left(H_{1} \text{wahr} \mid J(c)-J(c+1) \leq \varepsilon\right) \leq \theta,
$$

Wir akzeptieren $$H_{0}$$, wenn:

… wenn also Wahrscheinlichkeit, dass $$H_{1}$$ trotz dieser “geringen” Abnahme von $$J(c+1)$$ verglichen mit $$J(c)$$ stimmt, akzeptabel klein ist. (Geyer-Schulz 2017 S. 29)

## Quellen

Geyer-Schulz, Andreas. 2017. “Cluster-Analyse.”

Geyer-Schulz, Andreas, and Andreas Sonnenbichler. 2017. “Verkaufsunterstützung Mit Hilfe von Entsheidungsbaumverfahren.”
