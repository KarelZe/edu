# Messung Benutzerverhalten

SciNetPub möchte für seine global vertriebenen Informatik-, Informationswirtschafts- und Data-Science Zeitschriften ein verhaltensbasiertes Recommendersystem für Empfehlungen der Art Others Also Use aufbauen.

F: Was bedeutet Other Also Use? \(5P\)

A:

1. „Other also use" steht für „Andere Nutzer nutzen auch". Es handelt sich also um einen verhaltensbasierten Recommender, der auf Grundlage des Nutzerverhaltens anderer Nutzer Empfehlungen generiert.
2. Nutzerverhalten entspricht im Kontext von SciNetPub dem Leseverhalten von Nutzern mit ähnlichen Interessen und ähnlichen Fachgebieten.
3. Ein derartiger Recommender basiert typischerweise auf einem Ehrenberg-Recommender / auf der Auswertung von Sessions mit digitalen Informationsprodukten im Rahmen einer Warenkorbanalyse.

F: Wie muss SciNetPub seinen OPAC aufbauen und was muss SciNetPub messen, um einen solchen Recommenderdienst aufbauen zu können? \(5P\)

A:

* SciNetPub muss in seinem OPAC eine Möglichkeit zum **Logging von Transaktionen** integrieren.
* Transaktionen müssen messen, welche Seiten / Dokumente zu welchem Zeitpunkt im Rahmen welcher Session aufgerufen wurden. \(Eigene\)
* Weiterhin wird ein **User-Observation Agent** benötigt, der das Nutzerverhalten beobachtet und die Transaktionslogs schreibt.
* **Aggregation Agent** \(nicht abgebildet, da nicht Teil von OPAC\) schätzt LSD-Verteilung und berechnet Ausreiser.
* Ferner wird ein **Recommendation-Agent** benötigt. Dieser generiert Vorschlagsseiten und wird über eingebettete Links im OPAC aufgerufen.
* Die Ergebnisse des Bibliothekssystems und des Recommendation-Agents werden im User-Interface integriert. \(Folie 48; BibTip\)

![](../.gitbook/assets/grafik%20%2839%29.png)

F: Erstellen Sie ein Datenmodell für diese Messungen! \(Hinweis: Vergessen Sie die Metadaten nicht!\) \(10P\)

A:

**Tabelle für Einkäufe \(angelehnt an Grafik auf Folie 26 BibTip Recommender\):**

| User\_id    | First\_Name    | Last\_Name    | …    |
| :--- | :--- | :--- | :--- |
| String    | String    | String    | …    |

**Weitere Tabellen:**

| Document\_Id    | Title    | Author    | …    |
| :--- | :--- | :--- | :--- |
| String    | String    | String    | …    |



| User\_id    | First\_Name    | Last\_Name    | …    |
| :--- | :--- | :--- | :--- |
| String    | String    | String    | …    |

F: Welche Preprocessing-Schritte müssen durchgeführt werden, damit dieser Datensatz für einen Ehrenberg-Recommender geeignet ist? \(5P\)

A:

1. Auswahl eines geeigneten Betrachtungszeitraums $t$. \(eigene\)
2. Aggregation der Einkäufe unterschiedlicher User auf Dokumentenebene, d. h. wann wurde ein Produkt in einem Zeitraum $t$ betrachtet. \(eigene\)
3. Ausreißer Erkennung im Rahmen der Datenvorverarbeitung z. B. durch Abschneiden von Perzentilen \(eigene\)
4. Session-Splitting bei öffentlichen Terminals \(vgl. Bib-Tip Folien\)
5. Extraktion von GET Anfragen \(Bib-Tip Folien\)
6. Wenn 1 Produkt in 1 Session mehrmals angeschaut wurde --&gt; auf 1 "standardisieren"

