# Hubs / Authorities

**12 Authority and Hub Algorithmen**

F: _Beschreiben Sie den Algorithmus zur Erstellung eines Teilgraphen des World-Wide Webs auf Basis der besten_ $$t$$ _Ergebnisse einer Suchmaschine im Pseudo-Code. \(Nur oberste Ebene. Kein Pseudocode von Funktionen bzw. Prozeduren!\)_

A:

Siehe hierzu Geyer-Schulz \(2020 S. 30\):

```text
ExtrahiereTeilgraph(nu; SE; t; d):
nu: Suchstring; 
SE: Suchmaschine; 
t <= 200: Anzahl Startseiten;
d in N: maximale Anzahl von Vorgängern; 
R_nu: besten t Resultate von SE auf nu
S_nu := R_nu

For Each Seite p 2 R_nu Do
    G+(p) := Eltern(p);
    G-(p) := Kinder(p);
    S_nu := S_nu join G+(p);
    If | G-(p) | <= d Then
        S_nu := S_nu join G-(p);
    Else
        S_nu := S_nu join Random(G-(p); d);
End
Return S_nu;
```

F: _Welche Heuristiken sollten zum Filtern dieses Teilgraphen verwendet werden und warum? \(Mindestens 2\)_

A:

Es bestehen 3 Probleme, die durch Filtern der Teilgraphen gelöst werden sollen:

* Reine Navigationslinks entfernen
* Werbung entfernen
* Relevante vs. Populäre Seiten unterscheiden

Folgende Heuristiken lösen oben genannte Probleme. \(Jeweils gehört Heuristik 1 zu Problem 1 usw.\)

* **Heuristik zur Elimination von Navigationslinks:**
  * $$G\left[S_{\nu}\right]$$ Teilgraph der Seiten in $$S_{\nu}$$.
  * **Man unterscheidet:**
    * Links zwischen Seiten aus verschiedenen Domänen
    * Links zwischen Seiten einer Domäne
  * Wir löschen alle Links zwischen Seiten in einer Domäne.
* **Heuristik, um Werbung zu filtern \(eliminieren\):** Höchstens $$m$$ Seiten \(z. B. 4-8\) aus einer Domäne dürfen auf $$p$$ zeigen.
* **Heuristik, um populäre Seite zu filtern:** Der In-Degree von $$p$$ ist die Anzahl der Links, die auf $$p$$ zeigen. Populäre Seiten haben hohen In-Degree und geringe Authority. Wir entfernen alle Seiten, die diese Eigenschaften erfüllen. \(Geyer-Schulz 2020 S. 32\)

F: _Erklären Sie die Linkstruktur von populären Seiten, von Hubs and Authorities!_

A:

**Populäre Seiten:** Seiten mit hohem _In-Degree_ d. h. vielen eingehenden Links.

![\(Eigene Darstellung\)](../../.gitbook/assets/authority%20%282%29%20%282%29%20%283%29%20%283%29%20%283%29%20%283%29%20%283%29%20%283%29%20%282%29%20%281%29%20%283%29.svg)

**Hubs:** Seite, die auf viele Authorities verweist.

![\(Eigene Darstellung\)](../../.gitbook/assets/hub.svg)

**Authorities:** Wird von vielen Hubs empfohlen.

![\(Eigene Darstellung\)](../../.gitbook/assets/authority%20%282%29%20%282%29%20%283%29%20%283%29%20%283%29%20%283%29%20%283%29%20%283%29%20%282%29%20%281%29.svg)

Zwischen Hubs und Authorities besteht Wechselwirkung, da sie sich gegenseitig verstärken \(Geyer-Schulz 2020 S. 33\).

F: _Wie ermitteln Sie die Gewichte von Hubs bzw. Authorities?_

A:

Siehe Geyer-Schulz \(2020 S. 35\):

**Authority:**

$$
x_{p} \leftarrow \sum_{q:(q, p) \in E} y_{q}
$$

**Hub:**

$$
y_{p} \leftarrow \sum_{q:(p, q) \in E} x_{q}
$$

## Quellen:

Geyer-Schulz, Andreas. 2020. “Relevante Objekte Empfehlen: Der Erste Eigenvektor Eines Graphen - Recommendersysteme.”

