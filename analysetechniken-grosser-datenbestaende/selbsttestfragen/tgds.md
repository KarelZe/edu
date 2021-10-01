# Theory guided data science

* Was versteht man unter "physikalisch konsistenten Modellen"?
  * Modelle/ Vorhersagen die Konsistent zu Naturgesetzen oder wissenschaftlichen Erkenntnissen sind.
  * **Beispiel:** Errechnete Temperatur darf nicht unterhalb absolutem Nullpunkt liegen. Keine negativen, prognostizierten Aktienkurse
* Was ist die Matrix-Vervollständigung _\(Matrix completion\)_?
  * Die Matrix-Vervollständigung ist die Vorhersage von Werten fehlender Features.
  * Kann sowohl unter Zurhilfenahme anderer Zeilen / Spalten oder beider vorgenommen werden.
    * Ähnlich zu Collaborative Filtering?
* Was sind **Reste** _\(residuals\)_?
  * Residuals, sind die Daten, die angeben, wie sehr sich die tatsächlichen Begebenheiten z. B. Beobachtungen vom rein Domänen-gestützten Modell unterschreiben.
  * Residuals sind nahe 0 für gute Vorhersagen.
  * Bei schlechten Vorhersagen sind residuals groß.
  * Man könnte residuals zum Trainieren von Datengestützten Modellen verwenden.
* Beschreibe das Ziel und die Hauptzutat von GLUE.
  * Entfällt.
* Reproduzieren Sie die Klassifikationsansätze für Theorie-getriebene Data Science
  * _Wahl der Modellstruktur_
    * Aufgrund von Domänenwissen "theory guided knowledge" wählt man ein bestimmtes Modell "data science model"
    * **Beispiel:** Beschreibung der Beziehungen zwischen Eingabe- und Ausgabevariablen
    * Mit Domänenwissen erreicht man eine bessere Problemzerlegung
    * **Beispiel:** Eigene Modelle für die Verdunstung und Versickerung von Wasser in der Hydrologie
  * _Verwendung von Domänenwissen zum Tuning des Modells_
    * Verbesserte Initialisierung
      * **Beispiel:** Bei k-Means werden Seeds verwendet die physikalisch plausibel sind. z. B. Verhältnis Laktatwert / Übergewicht.
    * Restriktion von Modellen
      * **Beispiel:** Bei Bayesian Modellen zur Kreditvergabe werden bekannte Zusammenhänge / Korrelationen für Attributpaare von Schuldnern berücksichtigt und nicht jedmögliches Attributpaar verwendet.
    * Beschränkungen, um physikalische Konsistenz zu erreichen
      * **Beispiel:** Wasser fließt immer den größten Abstieg hinab / zum Meer hin und sammelt sich dort, weswegen Auswertung des Höhenprofils bei Modell hilfreich ist.
    * Domänenwissen um Regularisierung zu kontrollieren
      * Regularisierung mit $\lambda$ ist eine Technik, um Overfitting zu vermeiden.
      * **Beispiel:** Verlustfunktion logistische Regression $L\(\tilde{w}, D\)=\log \operatorname{lik}\(\bar{w}, D\)-\lambda \text { penalty }\(\tilde{w}\)$
      * Verwendung von Lasso als Qualtitätsmaß das Anzahl der Variablen mit Prognosequalität verbindet.
      * Variante davon ist Group Lasso / Graph Lasso.
      * **Beispiel:** Wertet ein Klimamodell nur Y-Koordinaten aus, nicht aber Breitenkoordinaten, würde man das Modell mit Fehlerterm bestrafen,  da beide notwendig sind, um Geoposition zu beschreiben. Anderes könnte zu Overfitting führen.
  * _Verbesserung des Modelloutputs durch Domänenwissen_
    * Domänenwissen ist explizit verfügbar
    * **Beispiel:** man verwendet Datenbank mit Material-Eigenschaften als Ausgangspunkt für die Generierung neuer Verbundwerkstoffe / Legierungen etc., die bestimmte Eigenschaften erfüllen
    * Domänenwissen ist nur implizit verfügbar
    * **Beispiel:** Ableiten von Höhenprofilen aus zeitlichen Sequenzen von Satellitenbildern und der Entwicklung von Wasserständen.
  * _Hybride Modelle_
    * Wissenschaftler verfügen bereits über unterschiedlich ausgefeilte Modelle.
    * Modelle unterliegen aber Vereinfachungen \(vgl. Simplification Feature\) oder Betrachten nur einen Ausschnitt \(vgl. Reduction Feature\).
    * Man könnte nun aus wissenschaftlichen Modellen und tatsächlichen Modellen die Residuals ableiten und diese zum Trainieren Datengestützter Modelle verwenden.
    * Dass nur Ausschnitte betrachtet werden liese sich aufheben, indem man bei hybriden Modellen Daten-basierte und wissenschaftliche Modelle verwendet.
  * _Daten-basierte Verfeinerung / Kalibrierung der Modelle_
    * Entfällt.
* Für was steht $\Omega$ bei Group Lasso? Was ist die genaue Bedeutung?

