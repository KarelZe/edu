**12 Authority and Hub Algorithmen**

F: *Beschreiben Sie den Algorithmus zur Erstellung eines Teilgraphen des World-Wide Webs auf Basis der besten $$t$$ Ergebnisse einer Suchmaschine im Pseudo-Code. (Nur oberste Ebene. Kein Pseudocode von Funktionen bzw. Prozeduren!)*

A:

Siehe hierzu @geyer-schulz_relevante_2020 [S. 30]:

```powershell
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


F: *Welche Heuristiken sollten zum Filtern dieses Teilgraphen verwendet werden und warum? (Mindestens 2)*

A:

Es bestehen 3 Probleme, die durch Filtern der Teilgraphen gelöst werden sollen:

-   Reine Navigationslinks entfernen
-   Werbung entfernen
-   Relevante vs. Populäre Seiten unterscheiden

Folgende Heuristiken lösen oben genannte Probleme. (Jeweils gehört Heuristik 1 zu Problem 1 usw.)

-   **Heuristik zur Elimination von Navigationslinks:**

    -   $$G\left[S_{\nu}\right]$$ Teilgraph der Seiten in $$S_{\nu}$$.

    -   **Man unterscheidet:**
        -   Links zwischen Seiten aus verschiedenen Domänen
        -   Links zwischen Seiten einer Domäne
    -   Wir löschen alle Links zwischen Seiten in einer Domäne.

-   **Heuristik, um Werbung zu filtern (eliminieren):** Höchstens $$m$$ Seiten (z. B. 4-8) aus einer Domäne dürfen auf $$p$$ zeigen.

-   **Heuristik, um populäre Seite zu filtern:** Der In-Degree von $$p$$ ist die Anzahl der Links, die auf $$p$$ zeigen. Populäre Seiten haben hohen In-Degree und geringe Authority. Wir entfernen alle Seiten, die diese Eigenschaften erfüllen. [@geyer-schulz_relevante_2020 S. 32]

F: *Erklären Sie die Linkstruktur von populären Seiten, von Hubs and Authorities!*

A:

**Populäre Seiten:** Seiten mit hohem *In-Degree* d. h. vielen eingehenden Links.

![(Eigene Darstellung)](./../.gitbook/assets/populaere_seite.svg)

**Hubs:** Seite, die auf viele Authorities verweist.

![(Eigene Darstellung)](./../.gitbook/assets/hub.svg)

**Authorities:** Wird von vielen Hubs empfohlen.

![(Eigene Darstellung)](./../.gitbook/assets/authority.svg)

Zwischen Hubs und Authorities besteht Wechselwirkung, da sie sich gegenseitig verstärken [@geyer-schulz_relevante_2020 S. 33].

F: *Wie ermitteln Sie die Gewichte von Hubs bzw. Authorities?*

A:

Siehe @geyer-schulz_relevante_2020 [S. 35]:

**Authority:**

$$
x_{p} \leftarrow \sum_{q:(q, p) \in E} y_{q}
$$

**Hub:**

$$
y_{p} \leftarrow \sum_{q:(p, q) \in E} x_{q}
$$

## Quellen:
