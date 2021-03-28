Sie arbeiten für das Unternehmen Letfix, das Videostreaming von Serien
und Kinofilmen anbietet. Letfix möchte einen Recommenderdienst basierend
auf Modularity Clustering anbieten, indem Filme aus demselben Cluster
empfohlen werden. Im Folgenden finden Sie eine Matrix, wie oft ein Film
$$e_{i}$$ zusammen mit einem anderen Film $$e_{j}$$ angesehen wurde (der
Einfachkeit halber hier mit kleinen Zahlen):

$$
\left(\begin{array}{lllll}
0 & 5 & 2 & 1 & 3 \\
5 & 0 & 1 & 2 & 1 \\
2 & 1 & 0 & 4 & 4 \\
1 & 2 & 4 & 0 & 2 \\
3 & 1 & 4 & 2 & 0
\end{array}\right)
$$

Gegeben seien die
$$C_{1} = \left\{ \left\{ e_{1},e_{2} \right\},\left\{ e_{3},e_{4},e_{5} \right\} \right\}, \mathrm{\text{und }} C_{2} = \left\{ \left\{ e_{1},e_{2},e_{3} \right\},\left\{ e_{4},e_{5} \right\} \right\}$$.

------------------------------------------------------------------------

F: *Berechnen Sie die Modularity der Cluster $$Q(C_1)$$ und $$Q(C_2)$$.
Keine Punkte ohne Rechenweg!*

**Clustering 1**

$$M_1=\left(\begin{array}{ll|lll}
0 & 5 & 2 & 1 & 3 \\
5 & 0 & 1 & 2 & 1 \\ \hline
2 & 1 & 0 & 4 & 4 \\
1 & 2 & 4 & 0 & 2 \\
3 & 1 & 4 & 2 & 0
\end{array}\right)$$

$$e_{1,1} = \frac{1}{5}, e_{2,1} = \frac{1}{5}, e_{2,2} = \frac{2}{5}, a_{1} = \frac{2}{5}, a_{2} = \frac{3}{5}$$

$$e \times a = \left(\begin{array}{cc}
e_{1,1} & e_{1,2} \\
e_{2,1} & e_{2,2}
\end{array}\right)\left(\begin{array}{c}
a_{1} \\
a_{2}
\end{array}\right) = \left(\begin{array}{cc}
\frac{1}{5} & \frac{1}{5} \\
\frac{1}{5} & \frac{2}{5}
\end{array}\right)\left(\begin{array}{c}
\frac{2}{5} \\
\frac{3}{5}
\end{array}\right)$$

$$Q_1=\left(\frac{1}{5}-\frac{2}{5}^{2}\right)+\left(\frac{2}{5}-\frac{3}{5}^{2}\right)=\frac{2}{25}$$

**Clustering 2**

$$M_1=\left(\begin{array}{lll|ll}
0 & 5 & 2 & 1 & 3 \\
5 & 0 & 1 & 2 & 1 \\ 
2 & 1 & 0 & 4 & 4 \\\hline
1 & 2 & 4 & 0 & 2 \\
3 & 1 & 4 & 2 & 0
\end{array}\right)$$

$$e_{1,1} = \frac{8}{25}, e_{2,1} = \frac{3}{10}, e_{2,2} = \frac{2}{25}, a_{1} = \frac{31}{50}, a_{2} = \frac{19}{50}$$

$$e \times a = \left(\begin{array}{cc}
e_{1,1} & e_{1,2} \\
e_{2,1} & e_{2,2}
\end{array}\right)\left(\begin{array}{c}
a_{1} \\
a_{2}
\end{array}\right) = \left(\begin{array}{cc}
\frac{8}{25} & \frac{3}{10} \\
\frac{3}{10} & \frac{2}{25}
\end{array}\right)\left(\begin{array}{c}
\frac{31}{50} \\
\frac{19}{50}
\end{array}\right)$$

$$Q_1=\left(\frac{8}{25}-\frac{31}{50}^{2}\right)+\left(\frac{2}{25}-\frac{19}{50}^{2}\right)=-\frac{161}{1250}$$

------------------------------------------------------------------------

F: *Begründen Sie: Für welche der beiden Cluster C1 oder C2 entscheiden
Sie sich?*

A:

-   Man sollte sich für das erste Clustering entscheiden.
-   Modularity ist ein Maß für die Qualität eines Clusterings. Größere
    Modularity ist besser. Das zweite Clustering ist ein Hinweis darauf,
    dass die Cluster aus sg. Singelton-Clustern besteht. D. h. Cluster
    aus genau einem Knoten und es bestehen nur Inter-Cluster Kanten.

------------------------------------------------------------------------

F: *Was müssten Sie tun, um mit Sicherheit die global optimale
Clusterung zu ermitteln? Hinweis: Beschreiben Sie nur das dafür
notwendige Vorgehen, Sie sollen nicht rechnen!*

A:

-   Man müsste für alle möglichen Clusterings die Modularity berechnen.
    Die Clusterverteilung mit der höchsten Modularity wird dann gewählt.

-   Mögliche algorithmische Ansätze sind Plain Greedy, Randomized Greedy
    oder Core Groups Graph Clustering Algorithmen.

------------------------------------------------------------------------

F: *Was müssten Sie tun, wenn nicht nur auf einem Merkmal (hier: wie oft
zusammen gesehen?), sondern auf n Merkmalen Empfehlungen erzeugen
wollten?*

A:

-   Man könnte für jedes Merkmal einen eigenen Graphen erzeugen.
-   Merkmale sind in verschiedenen Graphen dargestellt → Cluster werden
    unabhängig voneinander in jedem Graphen gefunden.
-   Für Empfehlungen müssen dann Überschneidungen der Cluster betrachtet
    werden.

Im Gegensatz zu Amazooon setzt der Konkurrent Letfix auf Recommender mit
Modularity Clustering als Verfahren. Hierbei werden Filme und Serien aus
demselben Cluster empfohlen. Im Folgenden finden Sie eine Matrix, wie
oft ein Film $$e_{i}$$ zusammen mit einem anderen Film $$e_{j}$$
angesehen wurde.

$$
\left(\begin{array}{cccc} 
& e_{B} & e_{C} & e_{D} \\
e_{A} & 3 & 5 & 1 \\
e_{B} & & 2 & 3 \\
e_{C} & & & 1
\end{array}\right)
$$

Gegeben seien die Cluster
$$C_{1}=\left\{\left\{e_{A}, e_{C}\right\},\left\{e_{B}, e_{D}\right\}\right\}$$
und
$$C_{2}=\left\{\left\{e_{A}, e_{B}, e_{C}\right\},\left\{e_{D}\right\}\right\}$$.

------------------------------------------------------------------------

F: *Berechnen Sie die Modularity der Cluster $$Q\left( C_{1} \right)$$
und $$Q\left( C_{2} \right).$$*

A:

**Variante 1:**

$$\left(\begin{array}{llll}
0 & 3 & 5 & 1 \\
3 & 0 & 2 & 3 \\
5 & 2 & 0 & 1 \\1 & 3 & 1 & 0 \\
\end{array}\right)\stackrel{vertauschen}{\implies} \left(\begin{array}{ll|ll}
0 & 5 & 3 & 1 \\
5 & 0 & 2 & 1 \\\hline
3 & 2 & 0 & 3 \\1 & 1 & 3 & 0 \\
\end{array}\right)$$

$$e_{1,1} = \frac{1}{30}, e_{2,1} = \frac{1}{30}, e_{2,2} = \frac{2}{30}, a_{1} = \frac{2}{30}, a_{2} = \frac{3}{30}$$

$$e \times a = \left(\begin{array}{cc}
e_{1,1} & e_{1,2} \\
e_{2,1} & e_{2,2}
\end{array}\right)\left(\begin{array}{c}
a_{1} \\
a_{2}
\end{array}\right) = \left(\begin{array}{cc}
\frac{10}{30} & \frac{7}{30} \\
\frac{7}{30} & \frac{6}{30}
\end{array}\right)\left(\begin{array}{c}
\frac{17}{30} \\
\frac{13}{30}
\end{array}\right)$$

$$Q_1=\left(\frac{1}{3}-\frac{17}{30}^{2}\right)+\left(\frac{1}{5}-\frac{13}{30}^{2}\right)=\frac{11}{450}$$

**Variante 2:**

$$M_2=\left(\begin{array}{lll|l}
0 & 3 & 5 & 1 \\
3 & 0 & 2 & 3 \\
5 & 2 & 0 & 1 \\\hline1 & 3 & 1 & 0 \\
\end{array}\right)$$

$$e \times a = \left(\begin{array}{cc}
e_{1,1} & e_{1,2} \\
e_{2,1} & e_{2,2}
\end{array}\right)\left(\begin{array}{c}
a_{1} \\
a_{2}
\end{array}\right) = \left(\begin{array}{cc}
\frac{20}{30} & \frac{5}{30} \\
\frac{5}{30} & 0
\end{array}\right)\left(\begin{array}{c}
\frac{25}{30} \\
\frac{5}{30}
\end{array}\right)$$

$$Q_2=\left(\frac{20}{30}-\frac{25}{30}^{2}\right)+\left(0-\frac{5}{30}^{2}\right)=-\frac{1}{18}.$$

------------------------------------------------------------------------

F: *Begründen Sie: Für welche der beiden Cluster $$C_{1}$$ oder
$$C_{2}$$entscheiden Sie sich?*

-   Grundsätzlich gilt je größer die Modularity, desto zusammenhängender
    das Cluster. Es sollte damit Clustering 1 gewählt werden.

------------------------------------------------------------------------

F: *Was müssten Sie tun, um mit Sicherheit die global optimale
Clusterings zu ermitteln? Hinweis: Beschreiben Sie nur das dafür
notwendige Verfahren. Sie sollen nicht rechnen!*

Siehe oben.

------------------------------------------------------------------------

F: *Was müssten Sie tun, wenn nicht nur auf einem Merkmal (hier: wie oft
zusammen gesehen?), sondern auf $$n$$ Merkmalen Empfehlungen erzeugen
wollten?*

Siehe oben.

------------------------------------------------------------------------

F: *Gegeben sei folgende folgender Graph in Matrixdarstellung. Jeder
Knoten repräsentiert eine Person. Die Kantengewichte geben an, wie oft
Person $$i$$ mit Person $$j$$ per e-Mail kommuniziert hat.*

$$
\left(\begin{array}{lllll}
0 & 3 & 1 & 0 & 0 \\
3 & 0 & 1 & 0 & 2 \\
1 & 1 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 \\
0 & 2 & 0 & 1 & 0
\end{array}\right)
$$

F: *Zeichnen Sie den gewichteten Kommunikationsgraphen!*

A:

![Kommunikationsgraph (Eigene Darstellung)](./../.gitbook/assets/kommunikationsgraph.svg)

------------------------------------------------------------------------

F: *Berechnen Sie die Modularität für jeden Knoten.*

A:

$$
e \times a = \left(\begin{array}{l|l|l|l|l}
0 & \frac{3}{16} & \frac{1}{16} & 0 & 0 \\ \hline
\frac{3}{16} & 0 & \frac{1}{16} & 0 & \frac{2}{16} \\ \hline
\frac{1}{16} & \frac{1}{16} & 0 & 0 & 0 \\ \hline
0 & 0 & 0 & 0 & \frac{1}{16} \\ \hline
0 & \frac{2}{16} & 0 & \frac{1}{16} & 0
\end{array}\right)\left(\begin{array}{c}
\frac{1}{4} \\
\frac{3}{8} \\
\frac{1}{8}\\
\frac{1}{16} \\
\frac{3}{16}
\end{array}\right)
$$

$$Q_1=\left(0-\frac{1}{4}^{2}\right)+\left(0-\frac{3}{8}^{2}\right)+\left(0-\frac{1}{8}^{2}\right)+\left(0-\frac{1}{16}^{2}\right)+\left(0-\frac{3}{16}^{2}\right)=-\frac{33}{128}$$

------------------------------------------------------------------------

F: *Berechnen Sie für jeden Knoten die Änderung der Modularität, wenn er
mit einem seiner Nachbarn in ein Cluster gruppiert wird (für alle
möglichen Nachbarn).*

A:

Annahme man legt einfach $$A$$ mit $$B$$ zusammen, $$C$$ mit $$D$$ und
$$E$$ bleibt allein.

$$M = \left(\begin{array}{ll|ll|l}
0 & 3 & 1 & 0 & 0 \\
3 & 0 & 1 & 0 & 2 \\ \hline
1 & 1 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 1 \\ \hline
0 & 2 & 0 & 1 & 0
\end{array}\right)$$

$$e \times a = \left(\begin{array}{lll}
\frac{6}{16} & \frac{2}{16} & \frac{2}{16}\\
\frac{2}{16} & 0 & \frac{1}{16}\\ 
\frac{2}{16} & \frac{1}{16} & 0\\
\end{array}\right)\left(\begin{array}{c}
\frac{10}{16} \\
\frac{3}{16} \\
\frac{3}{16}\\
\end{array}\right)$$

$$Q_2=\left(\frac{6}{16}-\frac{10}{16}^{2}\right)+\left(0-\frac{3}{16}^{2}\right)+\left(0-\frac{3}{16}^{2}\right)=-\frac{11}{128}$$

------------------------------------------------------------------------

F: *Wie ändert sich die Modularität, wenn nicht benachbarte Knoten
gemeinsam in ein Cluster gruppiert werden?*

A: Modularity verbessert sich. Im Graph oberhalb ist zu sehen, dass A, B
und C ein natürliches Cluster bilden.

------------------------------------------------------------------------

F: *Beschreiben Sie den Randomized Greedy Cluster Algorithmus im
Pseudocode.*

A:

![Randomized Greedy Cluster Algorithmus (Ovelgönne and Geyer-Schulz 2010
S. 1.206)](../.gitbook/assets/randomized_greedy.jpg)

------------------------------------------------------------------------

F: *Das Modularity-Maß für die Partition der Knoten eines Graphen in c
Cluster lautet:*

$$Q = \sum_{i = 1}^{c} \left( e_{ii} - a_{i}^{2} \right).$$

F: *Welche Interpretation hat $$e_{ij}$$ und wie wird $$e_{ii}$$ aus der
Adjazenzmatrix eines Graphen berechnet?*

-   $$e_{i j}$$: Wahrscheinlichkeit, dass zufällige Kante $$\in E$$
    Cluster $$C_{i}, C_{j}$$ verbindet
-   $$e_{i i}$$: Wahrscheinlichkeit eine Kante im Cluster $$C_{i}$$ zu
    wählen (bzw. der Anteil der Kanten im Cluster)

------------------------------------------------------------------------

F: *Welche Interpretation hat $$a_{i}^{2}$$ und wie wird $$a_{i}$$
berechnet?*

A:

$$a_{i}^{2}$$: Erwarteter Anteil an Kanten für einen zufälligen Graphen
mit gleichem Knotengrad aller Knoten.

$$a_{i} = \sum_{j = 1}^{c} e_{ij}$$

------------------------------------------------------------------------

F: *Warum ist das Modularity-Maß als Clusterkriterium geeignet?*

A:

-   Modularity $$Q$$ ist ein globales Maß für Güte einer Partitionierung
    $$C$$ eines Graphen $$G$$
-   Modularity: Summe der Abweichungen der tatsächlichen inneren Dichte
    jeden Clusters vom Null-Modell
-   Abweichung groß: Knoten nicht unabhängig voneinander → lässt auf
    Community-Struktur schließen

------------------------------------------------------------------------

F: *Modularity Clustering hat den Vorteil, dass im Gegensatz zu anderen
Clusterverfahren die richtige Anzahl von Clustern automatisch gefunden
wird. Wie beurteilen Sie diese Aussage?*

A: Grundsätzlich lässt durch Maximierung der Modularity die optimale
Anzahl der Cluster finden. Es handelt sich aber um NP-Schweres
Optimierungsproblem. Die Anzahl der kombinatorischen Möglichkeiten
Cluster zu bilden, steigt schneller als exponentiell in der Anzahl
Knoten $$n$$. Praktisch stellt es also für sehr große Graphen ein
Problem dar $$Q$$ zu maximieren. Sinnvollerweise werden weniger
rechenintensive Algorithmen wie Randomized Greedy benutzt. Eine
Garantie, dass es sich tatsächlich um das Beste Clustering handelt, hat
man dann aber nicht. (Geyer-Schulz 2017 S. 54)

F: *Beschreiben Sie kurz eine Anwendung von Modularity-Clustering im
Bereich von Empfehlungsdiensten!*

A:

In Bibliothek wird ein Recommenderdienst eingesetzt. Er erlaubt es,
Nutzer Vorschläge zu seiner aktuellen Suche zu machen. Verlinkungen
zwischen Literatur, welche bei der Suche vorgeschlagen wird, lassen sich
als Graph darstellen. Clustert man diesen Graphen nun hierarchisch, so
kann man verschiedene Detailstufen und damit unterschiedliche Größen von
Clustern erreichen. Zur Charakterisierung eines Clusters (bzw. einer
Obermenge) wird Tag-Cloud aus den Titeln der Literatur erzeugt.
(Geyer-Schulz 2017 S. 45)

Quellen:
--------

Geyer-Schulz, Andreas. 2017. “Cluster-Analyse.”

Ovelgönne, M., and A. Geyer-Schulz. 2010. “Cluster Cores and Modularity
Maximization.” In *2010 IEEE International Conference on Data Mining
Workshops*, 1204–13. <https://doi.org/10.1109/ICDMW.2010.63>.
