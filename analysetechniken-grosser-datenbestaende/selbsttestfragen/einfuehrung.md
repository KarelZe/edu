# Einführung

_Was ist Overfitting?_

Zu kleinteiliges Model, das zu sehr auf Trainingsbestand zugeschnitten ist und auf neuen Daten schlecht performt.

_Wie kann man Overfitting vermeiden?_

* Häufig wird folgendes Verfahren verwendet. Aufteilung des Datenbestands in Trainingsdaten, Validierungsdaten und Testdaten.
  * Trainingsdaten dienen zur Erstellung eines Modells
  * Validierungsdaten zur Überprüfung der Modellgüte und gegebenfalls Veränderung des Modells
  * Testdaten zur nochmaligen Überprüfung der Güte des endgültigen Modells

_Was ist Change Detection?_

* Technik zur Erkennung wesentlicher Veränderung in einer Zeitreihe.
* Gleichbedeutend mit einer Änderung in einer Wahrscheinlichkeitsverteilung sprich deren Parameter.

_Wie unterschieden sich multivariate von univariaten Datenströmen?_

* **univariate Change-Detection:** Zeitreihenelemente sind eindimensional z. B. Börsenkurs
* **multivariate Change-Detection:** mehrere Dimensionen z. B. $$(x,y)$$-Positionen \(zwei Dimensionen\) oder Vektor von Börsenkursen \(viele Dimensionen\). Nicht ganz klar, was Change hier ist.

_Was sind Beispiele für Klassifikations-Algorithmen?_

* 1-Rules
* Lineare Klassifikatoren
* Entscheidungsbäume

_Was unterscheidet Attribute von Features?_

* **Attribut**: Für Klassifikation bedingt hilfreich z. B. Temperatur-Werte
* **Features**: Funktionen, die Attribute auf einen Wert abbildet z. B. Mittelwert der bisherigen Daten

_Was unterscheidet supervised von unsupervised clustering?_

* **Unsupervised:** Welche Cluster es gibt und wo genau ihre Grenzen verlaufen, ist vorab nicht bekannt. Es werden Algorithmen auf ungelabelten Daten verwendet. Salopp gesagt, es gibt keinen Lehrer, der sagt, was eine Banane ist.
* **Supervised:** Man kennt Klassenzugehörigkeiten des Trainingsdatenbestands. Man verwendet Algorithmus auf gelabelten Daten. Salopp gesagt, es gibt einen Lehrer, der sagt, was eine Banane ist.

_Geben Sie Beispiele für Anwendungsgebiete, in denen Cluster anwendbar sind._

- Spam-Filtering
- Erkennung von Betrugsfällen
- Erstellung von Taxonomien in der Biologie

_Skizzieren Sie ein Szenario aus den Naturwissenschaften, in dem Klassifikation sinnvoll einsetzbar ist._

- Entwicklung einer Maschine zur Sortierung von Bauteilen in vordefinierte Kategorien. Maschine hat Sensoren zur Erkennung des Materials und der Umrisse. Diese Daten dienen dem Klassifikationsalgorithmus als Input.

_Welche Technologien zur Generierung von Daten, die nicht in der Vorlesung diskutiert wurden, kennen Sie?_

- Smartphones z. B. Geoposition, 
- Wearables z. B. Pulsuhr, Smarte Handschuhe in Produktion

_Vor- und Nachteile von supervised / unsupervised learning?_
- Man benötigt keine gelabelten Daten. Labeling ist oft teuer und mühsam. (+)
- Das Labelling von Daten nach dem Clustering ist häufig einfacher. (+)
- Unsupervised Learning can beim Verständnis der Rohdaten helfen. (+)
- Unsupervised Learning ist subjektiver, da es kein Objective gibt. (-)

