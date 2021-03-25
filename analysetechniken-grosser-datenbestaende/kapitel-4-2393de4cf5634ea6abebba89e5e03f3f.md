# Kapitel 4

* Wie baut man einen Entscheidungsbaum auf?
* Travesiere alle Attribute. Finde für jedes einzelne Attribut den Wert, der die niedrigste Schnitt-Entropie hat. Nehme dann das Attribut als Split-Attribut, welches die niedrigste Schnitt-Entropie hat. Fahre so mit den beiden Kindknoten fort, bis ein Abbruchkriterium erfüllt ist. Das könnte z.B. eine Entropie von 0 oder eine maximale Tiefe sein. Split sollte den Datenbestand immer möglichst homogen teilen. \(vgl. [martin thoma](https://martin-thoma.com/analysetechniken-grosser-datenbestaende/)\)
* **Algorithmus:**

```python
split (Datenbestand D) { # Umgang mit Overfitting bleibt hier noch außen vor!
    Abbruch, wenn D komplett homogen;
    Split mit niedriger Entropie für D finden
        Split-Attribut geeignet wählen,
        Split-Wert geeignet wählen.
    D-links : = Menge der Tupel aus D, für die gilt:
        Wert des Split-Attributs < Split-Wert
    D-rechts : = D-D-links;
    split(D-links);
    split(D-rechts);
}
```

* Wie kann man Overfitting beim Aufbau eines Entscheidungsbaums berücksichtigen?
* Post-Pruning / Pre-Pruning
  * Pre-Pruning: Generiere einen Baum mit weniger Zweigen als vollständiger Baum. D. h. man beläst Knoten als Blatt, wenn Split in irgendeiner Dimension nicht mehr viel bringt.
    * Kombinationen von Attributen sind nicht erkennbar!
  * Post-Pruning: Generiere einen vollständigen Baum, schneide ihn dann zurück.
    * Kosten sind nicht entscheidend!
  * Sonstige:
    * Minimale Anzahl der Einträge pro Blatt / Maximale Tiefe / Maximale Zweiganzahl
    * Mehrere Bäume zu Random Forest kombinieren.
* Wie kann Aufbau des Entscheidungsbaums berücksichtigen, dass unterschiedliche Fehlerarten unterschiedlich schlimm sind?
  * Baum wird mit mehr Trainingsdaten für teuren Fehler trainiert
  * **Beispiel:**

    Angenommen, False Positives \(No-Instanz wird mit Yes markiert\) sind relativ teuer \(z. B. Faktor 10\). → 10-mal mehr NO-Instanzen im Trainingsdatenbestand \(z. B. durch Ziehen und Zurücklegen\)

  * Bei **Decision Tree mit Wahrscheinlichkeiten** erhält man auch Wahrscheinlichkeiten. D. h. man kann damit auch erwartete Kosten der Vorhersage minimieren. \(vlg. [stackexchange](https://stats.stackexchange.com/questions/193424/is-decision-tree-output-a-prediction-or-class-probabilities)\)
  * **Beispiel:**
  * False Positive \(Vorhersage ist YES, Klasse ist NO\) kostet $10$, Miss \(Vorhersage ist NO, Klasse ist YES\) kostet $1$. Richtige Vorhersagen „kosten“ $0$.
  * Classifier sagt für ein Objekt vorher: NO mit WS=$0.7$. Erwartete Kosten, wenn wir Vorhersage NO aufgreifen: $0,3 \times 1$, weil $\(0,3 \times 1 + 0,7 \times 0\)$.
* Wann ist ein Entscheidungsbaum besser?
  * Enscheidungsbäume sind gut erklärbar / gut nachvollziehbar
  * Kompakte Bäume sind zu bevorzugen.
* Conditional Risk verbal erklären.
  * Conditional Risk $R\(i \mid x\)=\sum\_j P\(j \mid x\) \cdot \operatorname{Cost}\(i, j\)$
  * $j$ ist mögliche tatsächliche Klasse
  * $i$ ist vorhergesagte Klasse \(d. h. Klasse auf die wir uns einstellen\)
  * $Cost\(i, j\)$ gem. Modell. Z. B. stehen Kosten für Kunde aus Klasse $j$ und  vorhergesagt für $_i_$ dafür, ob ich Kunde als guten oder schlechten Kunde behandele.
  * $R\(i \mid x\)$ ist Vorhersage ob gut oder schlecht.
  * $P\(j \mid x\)$ ist Wahrscheinlichkeit der Vorhersage für neues Objekt
  * Kombinert Wahrscheinlichkeiten und Kosten
* Wie geht man mit NULL-Werten im Datenbestand um?
  1. NULL als einen weiteren möglichen Wert behandeln z. B. Schulabschluss
  2. Tupel für Training nicht weiter verwenden → Problematisch. Verringert Datenbestand
  3. Variante eines Entscheidungsbaums, die mit gewichteten Trainingsdatenobjekten umgehen kann, wählen. D . h.
     * Bei Split-Findung NULL-Werte ignorieren
     * Bei Partionierung
     * Angenommen,  $n_{1}$ Datenobjekte haben Attributwert $\leq$ Split-Wert, dto. $n_{2},&gt;$ Objekt, das fur Split-Attribut den Wert NULL hat.
     * Kommt mit Gewicht $\frac{n_{i}}{n_{1}+n\_{2}}$ nach links.
     * Dto. $\frac{n_{z}}{n_{1}+n\_{2}}$ rechts.
     * Vorhersage eines Blatts war ja: Haufigstes Label. NULL-Objekte antelig, gemaß inres Gewichts, berücksichtigen.

