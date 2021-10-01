# Optimierte AR

* In welchen Situationen ist Apriori teuer und warum?
  * Aufwendig bei großen Frequent Itemsets
  * viele Schleifendurchläufe durch die Daten
  * große Zwischenergebnisse d. h. alle Teilmengen eines Frequent Itemsets werden erzeugt. Z. B. hätte Itemset $\|20\|$ hätte $2^{20}$ Teilmengen.
  * Eine große Zahl von Itemsets, die nicht interessant sind
* Wann kann man gegen diese Schwäche tun?
  * Verwendung von Direct Hash and Pruning → Verwendung einer Hash-Methode für die Candidate Itemset Generierung während der initalen Durchläufe und Verwndung einer Pruning-Technik zur  Verkleinerung der Transaktions-Datenbank-Größe. Beim Zählen des Supports eines jeden itemsets in $C_k$ werden auch die $C_{k+1}$ Elementigen Teilmengen jeder Transaktion betrachtet.
  * Verwendung von Sampling → Berechnung auf Stichprobe durchführen → Verringerung der Schritte über DB
  * Wechsel des Algorithmus von Apriori zu FP-Trees
* Was sind FP-Trees, und wie lassen sie sich für die Suche nach Frequent Itemsets verwenden?
  * Datenstruktur zum schnellen Finden von Frequent Itemsets. Die Struktur entspricht einem Baum. Die Struktur leitet sich aus dem Vorkommen der sortierten Itemsets ab. Zu jedem Knoten wird eine Referenz auf ein Item gespeichert und wie oft ein Item innerhalb eines Pfads erreicht wird. Einzelne Knoten im Baum sind miteiander verbunden, sofern sie gemeinsam als sortierte häufige Items vorkommen. In Header-Tabelle wird zu jedem Item eine Referenz auf Knoten im FP-Tree gespeichert, sofern diese das Item enthalten.
* Aufbau:
  1. Zählen wie oft Item vorkommt
  2. Sortieren nach Häufigkeit \(desc\). Bei Gleichhäufigkeit nach Alphabet o. Ä.
  3. Füge geordnete Transaktion in Baum ein
  4. Baue Header-Tabelle auf
  5. Extrahiere Frequent Itemsets aus FP-Tree → Beginnend mit niedrigstem Element in Header-Tabelle wird der Präfix \(Zähler\) auf den erwarteten Support geprüft.  Man geht Präfix-Pfade d. h. Pfade welche das Item z. B. $p$ enthalten, durch und überprüft auf erwarteten Support.  Prüfung in Apriori-manier
* Was kann man tun, wenn FP-Trees für den Hauptspeicher zu groß sind?
  * Verwendung von Projected Databases. Projected Databases dienen dazu, eine bestimmte Menge von Frequent Itemsets zu bestimmen. Eine z. B. $p$-projected Database ist dabei fast immer kleiner als die Gesamtmenge der Transaktionen, da nicht alle Transaktionen $p$ enthalten.

