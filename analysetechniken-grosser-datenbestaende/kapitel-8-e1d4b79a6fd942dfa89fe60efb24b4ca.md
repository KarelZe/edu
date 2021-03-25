# Kapitel 8

* Was ist Constraint-basiertes Mining?
  * Suche nach Association Rules unter Bedingungen \(engl. _constraint_\). Varianten sind Data und Rule Constraints \(siehe übernächste Frage\)
* Was sind die Vorteile?
  * Um übersichtlichere Resulte zu erhalten
  * Um kürzere Laufzeiten der Algorithmen zu erhalten
  * Beschleunigung des Mining-Prozesses
* Was für Arten von Constraints kennen sie? Beispiele hierfür.
  * Data Constraint: Einschräkung auf konkrete Werte und bestimmte Attribute wie Region, Preis oder Marke → Bsp: Finde alle Wertpapiere, die in New York am 25. Oktober 1929 oft zusammen gekauft wurden.
  * Rule Constraint: Einschränkung der Itemsets auf betimmte Größen. Man spezifiziert Struktur oder Eigenschaften der zu ermittelnden Regeln.  → Bsp: Nur Frequent Itemsets der Größe 4
* Was ist Anti-Monotonizität, Succinctness? &lt;Für ein bestimmtes Constraint sagen/begründen, ob anti-monoton/succinct.&gt;
* **Anti-Monotonizität: \(Constraint Eigenschaft\):** Ein 1-var Constraint heißt anti-monoton, wenn für alle Mengen $S, S^{\prime}$ gilt: $\left\(S \supset S^{\prime} \wedge\left\(S \text { erfüllt } C\right\)\right\) \Rightarrow S^{\prime} \text { erfüllt } C$
* **Beispiel nicht antimononton:** Regex: \(AT\)\* ist nich antimonoton. Da AAAAA z. B. Teilfolge von Gensequenz ATATATAT ist. Der Regex "greift" aber für Teilmenge nicht und ist damit nicht antimonoton.
* **Succinctness \(Constraint Eigenschaft\):** Wenn alle Itemsets, die das Constraint erfüllen explizit in „kurzer Art und Weise" hingegeschrieben werden können.
* **Beispiel Succinctness:** Man hat das Constraint, dass der Typ "Non-Food" sein soll. Aber es gibt nur 3 Produkte von diesem Typ. Kandidaten, die das Constraint nicht erfüllen werden dann gar nicht erst erzeugt.
* Wie lässt sich Apriori für das Mining von Teilfolgen verallgemeinern?
  * Prinzip von Apriori bleibt gleich: „Support einer Folge“. Man generiert aus dem Ergebnis des $k$-ten Schritts Kandidaten der Größe $k+1$. Ergebnisse der $k$-ten Schritte sind Strukturen der Größe $k$, die frequent sind. Apirio muss lediglich angepasst werden, damit mit Listen gearbeitet werden kann.
* Antagonismus von Support-basiertem und Constraint-basiertem Pruning erklären können.
  * Support-basiertes Pruning:  ein Kandidat $c$ der Länge $k$ ist gegeben. $c$ wird elemeniert, wenn $\(k-1\)$-elementige Teilfolge, die Constraint $R$ efüllt, nicht frequent ist.
  * Constraint-basiertes Pruning:
  * Support vs. Constraint-basiertes Pruning:
    * Es scheint: Je selektiver Constraint, desto beser. In Wirklichkeit jedoch:
    * Angenommen Constraint ist extrem selektiv und nicht anti-monoton, dann funktioniert Constraint-baisertes Pruning offensichtlich gut, support-basiertes Pruning jedoch nicht.
      * support-basiertes Pruning betrachtet alle Teilstrukturen der Größe $k-1$ und $L\_{k-1}$
      * Es gibt möglicherweise nur wenige solche Strukturen
      * Schwächere Constraints erleichtern support-basiertes Pruning
* Alternativen für Constraint-basiertes Pruning \(wenn Constraint nicht anti-monoton\) erklären können.
  1. Naives Postprocessing → Algorithmus laufen lassen. Im Nachgang Constraint anwenden.
  2. Wenn Succinctness → Aus Constraint Kandidaten zu generieren
  3. Kombination von Support- und Constraint-Basiertem Pruning
  4. Pruning mit abgeschwächtem Constraint z. B. statt \(ab\) _nimmt man \(a\|b\)_ als Constraint. Constraint wäre anti-monoton, Abschwächung ist nicht anti-monton.
* Was bedeutet Support Counting?
  * Abzählen, wie häufig ein Kandidat ist. \(Teilschritt von Apriori\)

