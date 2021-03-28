F: *Vergleichen Sie den k-means Clusteralgorithmus mit dem Basic
Leader-Follower Algorithmus. Welches sind jeweils die Vor- und die
Nachteile?*

A:

-   Konzeptioneller Unterschied: K-means ist ein *offline*
    Learning-Verfahren. Der Leader-Follower-Algorithmus ein
    *online*-Verfahren.

-   Vorteil Basic Leader-Follower
    -   Anzahl der zu bildenden Cluster muss nicht a priori festgelegt
        werden.
-   Vorteile $$k$$-means
    -   $$k$$-means konvergiert typischerweise sehr schnell.
    -   Konzeptionell einfach.
-   Nachteil $$k$$-means

    -   Anzahl Cluster $$k$$ ist exogener Parameter → erfordert Kenntnis
        über Datenbestand
    -   Ungeeignet für nicht-konvexe Mengen
    -   Kann nicht gut mit Rauschen und Ausreißern umgehen
    -   Nur anwendbar, wenn (Cluster-) Mittelpunkt definiert ist →
        Schwierigkeiten bei kategorischen Daten.

-   Nachteil Basic Leader-Follower
    -   Keine stabilen Cluster

------------------------------------------------------------------------

F: *Sie sind Leiter der technischen Abteilung der
Universitätsbibliothek. Sie wollen den Empfehlungsdienst für Ihre Nutzer
verbessern, indem Sie Nutzern einen Expertenstatus zuordnen (“Laie”,
“Fortgeschrittener”, “Experte”). Diesen wollen Sie nutzen, um
verbesserte Empfehlungen anzubieten (z.B. empfiehl nur Grundlagenwerke,
falls der Nutzer Laie ist). Der Expertenstatus bezieht sich auf
Fachgebiete, denen einzelne Bücher zuzuordnen sind.*

*Durch freiwillige Angaben können Nutzer ihren Expertenstatus zu
bestimmten Büchern oder Fachgebieten angeben, Sie erhalten also einige
Daten durch die Nutzerangaben selbst.*

*Welcher Clusteralgorithmus empfiehlt sich, um Ihren Nutzern
Expertenstati zuzuordnen, und wieso? Welche Daten benötigen Sie zur
Umsetzung des Clusterings und zur Nutzung der Ergebnisse für den
Empfehlungsdienst?*

A:

-   Die Anzahl der Cluster ist vorab bekannt mit 3 möglichen
    Ausprägungen. Aus diesem Grund sollte der iterative
    $$k$$-means-Algorithmus verwendet werden.

-   Zum Clustering benötigt man Daten über die Nutzer. Diese könnten
    etwa die Anzahl bereits gelesener Dokumente, akademischer Grad,
    Selbsteinschätzung Vorkenntnisse o. Ä. sein.

-   Zur Nutzung im Recommendersystem reicht dann das Wissen, in welchem
    Cluster sich ein Nutzer befindet, aus. Hierfür muss aber ein Mapping
    bestehen, um zu interpretieren, welches Cluster den „Experten" o. Ä.
    entspricht.

------------------------------------------------------------------------

F: *Zur Kundendialogsteuerung sollen Entscheidungsbäumen eingesetzt
werden. Erläutern Sie kurz, wie ein Entscheidungsbaum gelernt werden
kann und wie er anschließend zur Dialogsteuerung verwendet wird.*

A:

1.  Zunächst ist ein Trainingsdatensatz und Testdatensatz mit Attributen
    zu ermitteln (z. B. 70 / 30). Attribute sind ggf.
    vorzuverarbeiten z. B. zu standardisieren. Weiterhin muss der
    Datensatz ein diskretes Klassenlabel (hier: Expertenstati), das
    vorhergesagt wird, enthalten.

2.  Anhand der Entropie wird dann das Attribut mit dem höchsten
    durchschnittlichen Informationsgewinn ermittelt.

3.  Man lernt den Baum solange weiter bis man keine Attribute mehr hat
    zum Erklären oder bis sich die Attribute nicht mehr verändern.

4.  Der letzte Schritt kann das Pruning des gelernten Baums und die
    Evaluation des Baums auf nicht zum Training benutzte Testdaten sein.
    Gängige Maße zur Evaluation ist etwa die *Accuracy*. (Geyer-Schulz
    and Sonnenbichler 2017 S. 18, 19, 44)

------------------------------------------------------------------------

F: *Wie evaluieren Sie, ob gelernte Entscheidungsbäume gut für Ihr
System geeignet sind?*

A:

**Aufteilen in Trainings- und Testdaten / Training:**

Typischerweise wird der gesamte vorhandene Datenbestand in ein
Trainingsset und ein Test Set gesplittet. Testdaten bleiben für das
Training des Entscheidungsbaums außen vor. Der Baum wird auf
Trainingsdaten gelernt.

Eine Variante ist **k-fold cross validation** mit folgendem Vorgehen:

-   Partitioniere das Datenset in $$k$$ Partitionen

-   Schätze $$k$$ hold-out Prädikator mit 1 Partition Validation Set und
    $$k - 1$$ Partitionen als Trainingsset, dann zweiter Durchlauf mit
    zweiter Partition zur Validierung und übrigen Partitionen zum
    Training. Analog wiederholen bis zum $$k$$-ten Durchlauf.

**Performance am Testdatensatz feststellen:**

-   Das Test Set kann dann benutzt werden, um die prognostizierte
    Klasse z. B. Status Laie o. Ä. mit der tatsächlichen Klasse zu
    vergleichen. Die Performance lässt etwa mit einer Konfusionsmatrix
    darstellen. Typische abgeleitete Metriken sind *Precision*, *Recall*
    und *Accuracy*.

-   Obige Schritte mehrmalig wiederholen für statistische Sauberkeit.
    (Geyer-Schulz and Sonnenbichler 2017 S. 54)

------------------------------------------------------------------------

F: *Wozu dient Clusteranalyse?*

A:

Entdecken einer natürlichen Struktur in Daten (Geyer-Schulz 2017 S. 6).

------------------------------------------------------------------------

F: *Was ist eine Segmentierungsbase, was eine Segmentierungsmethode?*

A:

**Segmentierungsbasen**:

-   Variablen oder Kriterien für die Segmentierung

-   Auswahl auf Basis: Ziel der Segmentierung und des Marktes

**Segmentierungsmethoden**:

-   Methodenauswahl auf Basis: Ziel der Segmentierung und der
    Eigenschaften der Segmentierungsbasis.

F: *Nennen Sie je zwei Beispiele für (beobachtbare-nicht beobachtbare) ×
(allgemeine-produktspezifische) Basen.*

A:

<table>
<thead>
<tr class="header">
<th></th>
<th>Allgemein</th>
<th>Produktspezifisch</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Beobachtbar</td>
<td>Kulturell</td>
<td>Benutzerstatus</td>
</tr>
<tr class="even">
<td></td>
<td>Geographisch</td>
<td>Benutzungsfrequenz</td>
</tr>
<tr class="odd">
<td></td>
<td>Soziökonomisch</td>
<td>Store Loyalty</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Situationen</td>
</tr>
<tr class="odd">
<td></td>
<td>…</td>
<td>…</td>
</tr>
<tr class="even">
<td>Nicht beobachtbar</td>
<td>Psychographisch</td>
<td>Psychographisch</td>
</tr>
<tr class="odd">
<td></td>
<td>Werte</td>
<td>Nutzen</td>
</tr>
<tr class="even">
<td></td>
<td>Persönlichkeit</td>
<td>Wahrnehmung</td>
</tr>
<tr class="odd">
<td></td>
<td>Life-Style</td>
<td>Präferenzen</td>
</tr>
<tr class="even">
<td></td>
<td></td>
<td>Absichten</td>
</tr>
<tr class="odd">
<td></td>
<td>…</td>
<td>…</td>
</tr>
</tbody>
</table>

F: *Wie bewerten Sie, ob sich zwei Datenpunkte ähnlicher sind als
andere? Nennen Sie zwei Beispiel-Maße.*

A:

**Normalisiertes, inneres Produkt:**

$$
s\left( x_{1},x_{2} \right) = \frac{x_{1} \cdot x_{2}}{\left. \  \parallel x_{1} \right.\  \parallel \left. \  \parallel x_{2} \right.\  \parallel}
$$

**Anteil der gemeinsamen Attribute:**

$$
s\left(x_{1}, x_{2}\right)=\frac{x_{1}^{T} x_{2}}{d}
$$

F: *Nennen Sie einen Anwendungsfall, wie Clusteranalyse in einem
Recommenderdienst verwendet werden kann.*

A:

**Movielens** - Anhand der Ratings aus dem each-movie dataset werden
durch Clusteranalyse Geschmacks bzw. Interessengruppen gebildet. - Aus
diesen Geschmacks-/Interessen Gruppen wird für Werbezwecke ein
E-Mailverteiler automatisch erzeugt. - Auf Basis der Geschmacks- und
Interessens-Gruppen werden neue Filmrechte erworben, die den Nutzern
gefallen könnten. (Geyer-Schulz 2017 S. 7)

Use Case: Sie arbeiten für Jupiter, einen großen, deutschlandweit
operierenden Elektronikanbieter, der sein Online Geschäft ausbauen
möchte. Sie sollen für die Abteilung Haushaltsgeräte einen
Recommenderdienst für Kühlschränke aufbauen: Ähnliche Kühlschränke
sollen auf der jeweiligen Produktseite einander gegenüber gestellt
werden, damit der Kunde diese besser vergleichen kann. Sie entscheiden
sich deshalb für einen inhaltsbasierten Recommender auf Basis von
Clusterverfahren. Ohne Use Case Bezug max. die Hälfte der Punkte!

F: *Definieren Sie als erstes den “Feature Space” für Kühlschränke, in
dem Sie jeden Kühlschrank mit einem Vektor $$x_{i}$$ beschreiben, also
Kühlschrank 1 mit $$x_{1}$$, Kühlschrank 2 mit $$x_{2}$$ usw. $$x_{i}$$
ist dabei selbst ein k-dimensionaler Vektor mit $$k$$ Eigenschaften des
Kühlschranks. Geben Sie ein konkretes Beispiel mit 5 Dimensionen, wie
ein $$x_{i}$$ aussehen könnte und überlegen Sie sich, welche
Eigenschaften Sie im Use Case abbilden wollen.*

A:

5-Dimensionaler Feature Space mit den Dimensionen Energieeffizienz,
Preis, Farbe, Einbaugerät und Eiswürfeleinheit.

Binäre / Nominale Attribute werden konvertiert in Abstand

-   Einbaugerät und Einbaugerät: Ja → 1, Nein → 0.

-   Preis wird standardisiert.

-   Energieeffizienzklasse wird auf Skala von 0-1 gemappt.

-   Farbe wird auf Skala von 0-1 gemappt.

<table>
<colgroup>
<col style="width: 17%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 26%" />
<col style="width: 26%" />
</colgroup>
<thead>
<tr class="header">
<th>Dimensionen</th>
<th>Kühlschrank 1</th>
<th>Kühlschrank 2</th>
<th>Kühlschrank 1 (standardisiert)</th>
<th>Kühlschrank 2 (standardisiert)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Energieeffizienz</td>
<td>A++</td>
<td>C</td>
<td>0</td>
<td>0.6</td>
</tr>
<tr class="even">
<td>Preis</td>
<td>500 EUR</td>
<td>150 EUR</td>
<td>0.7</td>
<td>0.2</td>
</tr>
<tr class="odd">
<td>Farbe</td>
<td>Space Grey</td>
<td>Weiß</td>
<td>0.8</td>
<td>0</td>
</tr>
<tr class="even">
<td>Einbaugerät</td>
<td>Ja</td>
<td>Nein</td>
<td>1</td>
<td>0</td>
</tr>
<tr class="odd">
<td>Eiswürfeleinheit</td>
<td>Ja</td>
<td>Nein</td>
<td>1</td>
<td>0</td>
</tr>
</tbody>
</table>

$$
S=\left(\left(\begin{array}{c} 0 \\ 0.7 \\ 0.8 \\ 1 \\ 1\end{array}\right),\left(\begin{array}{c}0.6 \\ 80.2 \\ 0 \\ 0 \\ 0\end{array}\right)\right)
$$

2. Sie stellen einen Werkstudenten ein, der alle bei Jupiter gelisteten
Kühlschränke mit den $$k$$ Dimensionen erfasst. Sie erhalten als
Ergebnis $$n$$ $$k$$-dimensionale Vektoren $$x_1, x_2, \ldots, x_n$$.
Beschreiben Sie kurz 3 Praxis-Probleme, auf die der Werkstudent Ihrer
Erwartung nach bei der Aufbereitung der Daten stoßen wird.

A:

1.  **Nominale Attribute** z. B. Einbaukühlschrank vs. Freistehend
    müssen in Dimension abgebildet werden.

2.  **Standardisierung von Attributen** z. B. müssen einzelne Attribute
    standardisiert werden. Würde man z. B. Temperatur (z. B. 4 - 10) und
    Preis (100 - 2.000) als solches beim Abstandsmaß Euklidische Distanz
    verwenden, wäre das Distanzmaß stark verfälscht, weil Preis Abstand
    stark verfälschen würde.

3.  **Fehlende Daten** z. B. könnte Produktbeschreibung der Hersteller
    unvollständig sein. Es braucht dann eine Strategie, um fehlende
    Werte aufzufüllen.

4.  **Redundante Daten** z. B. können Kühlschränken in mehreren Farben
    angeboten wären. Mit Ausnahme der Farbe hätten diese Kühlschränke
    eine ähnliche Position im Raum, würden dann wegen der hohen
    Ähnlichkeit empfohlen werden. Eigentlich handelt es sich aber um
    eine „schlechte / triviale Empfehlung".

5.  **Erfassungsfehler** z. B. kann Werkstudent Fehler bei
    Datenerfassung machen, was zu fehlerhaften Empfehlungen führt.

------------------------------------------------------------------------

F: *Sie möchten nun die $$n$$ Kühlschränke in $$c$$ Partitionen trennen.
$$M_{1},\, m_{2},\,\ldots,\, m_{c}$$ seien die c Clustermittelpunkte der
Partitionen $$D_{1},\, D_{2},\,\ldots,\, D_{c}$$. Welches Kriterium
(exakt: Zielfunktion) setzen Sie an? Geben Sie die Formel mit der hier
verwendeten Notation an und erklären Sie alle Bestandteile!*

A:

Man minimiert die Summe der Varianzen. Die *Criterion Function* ist
definiert als:

$$
J = \sum_{i = 1}^{c}\sum_{x_{j} \in D_{i}}\left. \  \parallel x_{j} - m_{i} \right.\  \parallel^{2},
$$

wobei $$m_{i}$$, der Mittelwert der Partition $$D_{i}$$, definiert ist
als:

$$
m_{i} = \frac{1}{n_{i}}\sum_{x_{j} \in D_{i}} x_{j}.
$$

Man iteriert also über jeden Punkt im Cluster und berechnet die Distanz
zu zum Cluster-Mittelpunkt und wiederholt das Vorgehen für jedes
Cluster. Das Ergebnis wird aufsummiert. Oberhalb wird die quadrierte
Norm verwendet. Liegt ein Punkt im falschen Cluster wird die Summe
entsprechend groß. (Geyer-Schulz 2017 S. 25)

**Problem:** Man versucht eigentlich $$J$$ zu minieren (minimales
Varianz-Kriterium). Hat man genauso viele Cluster wie Datenpunkte, dann
ist $$J = 0$$ wenig aussagekräftig (Geyer-Schulz 2017 S. 29)

------------------------------------------------------------------------

F: *Wie heißt der Fachausdruck für den “Abstand” zwischen zwei
Datenpunkten $$x_{a}$$ und $$x_{b}$$? Schlagen Sie eine geeignete
konkrete (!) Metrik für Ihren Feature Space (aus Teil 1!) vor.
$$x_{i,k}$$ notiere dabei die Merkmalsausprägung $$k$$ des Kühlschranks
$$i$$.*

A:

1.  Der Fachbegriff ist Ähnlichkeitsmaß. (euklidischer Abstand)

2.  Verhältnis der gemeinsamen Attribute zur Anzahl der Attribute in
    $$x_{1}$$ oder $$x_{2}$$ „Tanimoto"-Distanz:

$$
s\left( x_{1},x_{2} \right) = \frac{x_{1}^{T}x_{2}}{x_{1}^{T}x_{1} + x_{2}^{T}x_{2} - x_{1}^{T}x_{2}}
$$

------------------------------------------------------------------------

F: *Nach welchem Kriterium wählt der Algorithmus “iterative k-means” die
optimale Anzahl der Cluster aus? Wie bestimmt man allgemein die optimale
Anzahl der Cluster?*

A:

Die Anzahl der Cluster ist ein exogener Parameter beim
$$k$$-means-Algorithmus. Muss also durch den Nutzer vorgegeben werden.

Ansätze, um das optimale $$k$$ zu finden:

$$H_{0}$$: es sind $$c$$ Cluster, da $$(J(c))$$<br>$$H_{1}$$: es sind
$$c+1$$ Cluster, da $$(J(c+1))$$.

$$
J(c)-J(c+1) \leq \varepsilon \text { und } P\left(H_{1} \text{wahr} \mid J(c)-J(c+1) \leq \varepsilon\right) \leq \theta,
$$

Wir akzeptieren $$H_{0}$$, wenn:

… wenn also Wahrscheinlichkeit, dass $$H_{1}$$ trotz dieser “geringen”
Abnahme von $$J(c+1)$$ verglichen mit $$J(c)$$ stimmt, akzeptabel klein
ist. (Geyer-Schulz 2017 S. 29)

Quellen
-------

Geyer-Schulz, Andreas. 2017. “Cluster-Analyse.”

Geyer-Schulz, Andreas, and Andreas Sonnenbichler. 2017.
“Verkaufsunterstützung Mit Hilfe von Entsheidungsbaumverfahren.”
