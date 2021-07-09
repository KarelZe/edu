# Collaborative Filtering

_Netflix ist der größte Anbieter von Videofiles \(Kino, Serien, TV\) in den USA. Wir nehmen an, dass Netflix jedem Benutzer eine Liste von Filmen, die diesen Benutzer interessieren könnten, anbietet. Das verwendete Verfahren basiere auf einem cf-Recommender, der über Korrelationen arbeitet \(keine Clusterverfahren!\)._

F: _Erklären Sie das Vorgehen, wie ein neuer Benutzer eine Liste von_  $$n $$ _Empfehlungen für Filme erhält. Beschreiben Sie, wie die Liste von n Empfehlungen entsteht. Gehen Sie auch darauf ein, was methodisch passiert, wenn der Benutzer Filme bewertet._ \(13P.\)

A:

CF-Recommender verwendet die Ähnlichkeit von Nutzern. Es wird angenommen, dass Nutzer, die in der Vergangenheit eine Vorliebe bzw. Abneigung gegenüber den gleichen Produkten gezeigt haben, auch in Zukunft gleiche Produkte ähnlich einschätzen.

Neue Benutzer bewertet eine kleine Stichprobe von Produkten durch explizite und implizite Bewertungen.

CF-Recommender ermittelt die Ähnlichkeit zwischen Benutzern. Benutzer erhält Empfehlungen auf Basis einer gewichteten Summe von Produkten anderer Benutzer mit ähnlichem Geschmack. Korrelation der Bewertungen von Benutzern dient als Gewicht.

Bewertet ein Nutzer einen Film, dann muss eine Neuberechnung der naiven Prognose des bewertenden Nutzers, eine Neuberechnung der Mittel der gemeinsamen Profile, eine Neuberechnung des Korrelationskoeffizienten zwischen einzelnen Nutzern und der verbesserten Prognose erfolgen. Da dies für alle Nutzer des Streaming-Portals aufwendig ist, sollte dies ggf. im Rahmen einer Batch-Verarbeitung einmal oder mehrmals täglich erfolgen.

Auf Basis des Korrelationskoeffizienten, der Mittelwerte und der daraus berechneten Vorhersage für eine Bewertung bisher ungesehener Filme des aktuellen Nutzers wird dann die Empfehlungsliste erstellt. Dafür werden die vorhergesagten Bewertungen absteigende sortiert und die Filme für die besten n Bewertungen als Liste zurückgegeben.

F: _Nennen Sie drei Wege, wie Netflix die Bewertung eines Benutzers messen kann \(mindestens ein Weg muss implizit, mindestens ein Weg explizit sein\)._ \(2\*3P.=6P.\)

A:

**Explizit:**

* Sterne-Bewertung
* Daumen hoch / runter
* Hinzufügen in Favoritenliste

**Implizit:**

* Auswertung der Wiedergabezeit von Filmen, um zu erkennen ob und wann ein Film abgebrochen wurde.
* Evtl. Auch Suche nach bestimmten Filmen/Serien in Suchfunktion? -&gt; besonders interessiert daran \(mehr als an "zufällig" entdeckten Inhalten\)

F: _Ann, Bob und Charly seien drei Benutzer von Netflix. Ann und Bob haben den gleichen Geschmack bei Actionfilmen, für andere Genres aber unkorrelierte Geschmäcker. Ann und Charly haben den gleichen Geschmack bei Liebesfilmen, aber einen genau gegenläufigen Geschmack bei Actionfilmen. Für andere Genres bestehe kein Zusammenhang. Lässt sich dies in dem vorgestellten cf-Standardmodell abbilden? Wenn ja: wie? Wenn nein: Schlagen Sie eine entsprechende Erweiterung vor \(keine Clusterverfahren!\)_ \(6P.\)

A:

Nein, Standard-Collaborative Filterung betrachtet immer nur die Ähnlichkeit des Geschmacks über den gesamten Filmbestand; Bewertungen treffen immer nur Einzelfilme/Serien, keine höheren Abstraktionslevel. Zur Umsetzung müsste für jedes Genre z. B. Action / Liebesfilm etc. ein eigenes Collaborative-Filterung-Modell erstellt werden.

**Erweiterung:**

Es müssen spezifische Bewertungen vorliegen anhand dessen entsprechende Korrelationen ermittelt werden können, anstatt dass nur allgemeine Aussagen vorliegen.

Erweiterung, indem eine Ratingskala festgesetzt wird, eventuell eine Tabelle mit Bewertungen für Filmgenres \(Spalten Personen, Zeilen Genre, Zelle: Ratingwert\), wo gemeinsam gemochte Genre mit demselben Wert bewertet worden ist z. B. Ann und Bob haben den Actionfilm XY für Genre Actionfilm beide mit einer 3 bewertet, da beide hierfür den gleichen Geschmack haben. Für die Genres wo für jeweilige Personen keine Meinung vorliegt, die Zelle einfach leer lassen. -&gt; Also Aggregation der Bewertungen für Filme desselben Genres über eine Person?

F: _Mit welcher statistischen Kennzahl können CF-Recommender Zusammenhänge voraussagen?_ \(2P.\)

A:

Pearson'sche Korrelationskoeffizienten $$r $$ 

F: _Geben Sie alle notwendigen Inputs an, damit ein Collaborative Filtering \(CF\) Recommender Empfehlungen erzeugen kann._ \(6P.\)

A:

**Daten:**

Rater: $$k,\, l\, \in 1,\ldots.m$$ \[Spalten\]

Item: $$p\, \in 1,\ldots.,n$$ \[Zeilen\]

Rating Matrix: $n\, \times m$ Matrix, Matrixeintrag $p\left\( i,j \right\)$ enthält Bewertung von Rater $i$ über Item $j$.

F: _Nennen Sie ein Praxisbeispiel eines CF-Recommenders und erklären Sie in 3-4 Sätzen._ \(5P.\)

A:

**Jester**

* Entwicklung der University of Berkely California
* Explizite Bewertung von einem Set aus 15 Witzen
* Bewertung der Witze auf einer Skala von -15 bis +15
* Danach Vorschlag von Witzen nach eigenem Geschmack und erneutes Sammeln von Daten

F: _Wie geht ein CF-Recommender mit neu hinzukommenden Produkten um? Wie mit neuen Usern?_ \(2\*3=6P.\)

A:

**Neue Produkte**:

* Können erst empfohlen werden, wenn mind. ein Benutzer dieses gekauft hat. -&gt; schwaches Coldstartproblem
* Neue Produkte sollten einer Stichprobe an Nutzern zum Rating angeboten werden.

**Neue Benutzer:**

* Empfehlung kann erst erzeugt werden, wenn genügend Bewertungen des Benutzers vorliegen \(Stichprobenmenge\) -&gt; starkes Coldstartproblem
* Neue Nutzer müssen eine Stichprobe von Filmen raten, um etwas über den Geschmack von neuen Nutzern herauszufinden. \(Tonspur Geyer-Schulz\)

F: _Kann man einen CF-Recommender als Benutzer "manipulieren"? Begründen Sie._ \(6P.\)

A:

* Ein einzelner Nutzer hat wenig Macht.
* Schlechtes bewerten, außer bei eigenem Produkt führt dazu, dass keine anderen Nutzer den Geschmack teilen.
* Bei mehreren "schlechten/manipulativen" Bewertungen eines Nutzers entfernt sich dieser von den anderen -&gt; Isolation.
* Aber nur der Nutzer selbst hat wirklich Nachteile durch dieses "Manipulieren". Es ist keine Manipulation wie z.B. bei öffentlichen Amazon Bewertungen möglich, bei denen sich Nutzer an bereits vorhandenen \(ggf. Negativen\) Bewertungen orientieren. Also meine Antwort wäre: Ja, Manipulation ist möglich, aber es bringt nur dem jeweiligen Nutzer selbst Nachteile.

_Use Case: Das Unternehmen Koogle möchte die Spamerkennung für seinen Dienst Koogle Mail verbessern und dazu die Methode des Collaborative Filterings einsetzen. Koogle Mail hat 50 Millionen Nutzer mit einem durchschnittlichen Mailaufkommen von 20 eMails je Benutzer und Tag. Spam-eMails beinhalten häufig denselben Mail-Body jedoch unterschiedliche Empfänger._

F: _Beschreiben Sie in 4-5 Sätzen, wie Spamerkennung bei Koogle Mail mittels eines cf-Ansatzes funktioniert._ \(8P.\)

A: Unsicher ob meine Antwort soweit stimmt.

Benutzer erhalten im Durchschnitt 20 E-Mails. Sie bewerten jede einzelne entweder mit Daumen hoch \(Spam\) oder Daumen runter \(kein Spam\). Koogle sammelt täglich alle Emails mit den jeweiligen Bewertungen und speichert zu jedem Mail-Body ob es sich um eine Spam-Mail handelt oder nicht. Erhält Benutzer eine neue E-Mail, wird aufgrund von Bewertungen anderer Benutzer entschieden, ob es sich um eine Spam-Mail handelt oder nicht, sodass bei Vorliegen einer Spam-Mail diese direkt in den Spam-Ordner gefiltert wird.

F: _Welches Maß zur Ähnlichkeitsbestimmung für den cf-Ansatz wählen Sie? Begründen Sie in 1-2 Sätzen._ \(3P.\)

A:

Korrelationskoeffizient $$r$$ 

Gewichtete Summe von bewerteten E-Mails anderer Benutzer mit ähnlicher Bewertung. Korrelation der Benutzerbewertungen dient als Gewicht.

Geben Sie die Formel an, mit der das Spam-Rating von User k für Mail m vorhergesagt wird. Erklären Sie alle Formelbestandteile. \(6P.\)

A:

![](../../.gitbook/assets/grafik%20%2831%29.png)

$$
x_{p, k}=\bar{x}_{k}+\frac{\sum_{j}\left(x_{p, j}-\bar{x}_{j}\right) r_{k, j}}{\sum_{j}\left|r_{k, j}\right|}
$$

E-Mail $$p$$ 

User $$k$$ 

 $$r_{k,j}$$ : Korrelation von Rater k und Rater l

$${\overline{x}}_{k}$$ : Naive Prognose \(Globaler Mittelwert\)

$${\overline{x}}_{j}$$ : Lokale Mittelwerte

Quotient: Korrektur

Nenner: Gewichtete Different ähnlicher Benutzer

_Argumentieren Sie: Halten Sie einen cf-Recommender für dieses Szenario für effektiv und effizient? \(Denken Sie auch an die Skalierbarkeit!\)._ \(8P.\)

A:

Ich halte es nicht für effektiv und effizient, denn:

**Probleme mit dünnbesetzter Benutzer-E-Mail-Matrix**

* Hat schlechte Qualität der Vorschläge zur Folge
* Coldstart Probleme bei neuen Benutzern und E-Mails \( Spamwellen werden nicht erkannt, d. h. Spam-Mails zugestellt, da CF vorherige Bewertung durch andere Nutzer voraussetzt\)

**Skalierungsproblem:**

* Laufzeit wächst linear mit der Anzahl von Benutzer und E-Mails
* Die Suche nach ähnlichen Nutzern ist langwierig
* Es wird auf der gesamten Benutzer-E-Mail-Matrix gearbeitet, sie muss im Hauptspeicher gehalten werden.

_Amazooon Time Films sei ein aufstrebender Video-on-Demand Service für Filme und Serien. Jedem Benutzer bietet Amazooon eine Liste von Filmen, die diesen interessieren könnten, an. Das verwendete Verfahren basieren auf einem Collaborative Filtering-Recommender, der über Korrelationen arbeitet \(keine Clusterverfahren!\)._

F: _Erklären Sie, wem ein neuer Film empfohlen wird. Welche Information wird für die Wahl des Empfängers dieser Empfehlung verwendet? Wie wird dieses Problem genannt?_ \(6P\)

A:

Wem wird ein neuer Film empfohlen:

* Benutzer mit ähnlichem Geschmack für bestimmte Filme gegenüber denjenigen Benutzern, die bereits den neuen Film bewertet haben.

Welche Information wird für die Wahl des Empfängers dieser Empfehlung verwendet:

* Liste von Filmen, die der Benutzer bereits bewertet hat.
* Korrelation der Präferenzen des Nutzers zu anderen Nutzern

-&gt; Schwaches coldstartproblem \(neues Item\)

Für neue Filme im Filmkorpus besteht ein **schwaches Coldstart-Problem** hinsichtlich des Produkts. Generell besteht die Herausforderung, eine möglichst repräsentative Stichprobe aufzubauen, um rasch zu verlässlichen Empfehlungen des Produkts zu gelangen. Folgende Varianten sind denkbar:

* **Eigene:** Eine Möglichkeit besteht darin, dass Experten das Genre eines Films identifizieren und der neue Film mit dem durchschnittlichen Rating des Filmgenres eingestuft wird \(vgl. [https://developers.google.com/machine-learning/recommendation/collaborative/summary](https://developers.google.com/machine-learning/recommendation/collaborative/summary)\). Die Information wäre damit die Ähnlichkeit zum Filmkorpus.
* **Geyer-Schulz Tonspur:** Eine Möglichkeit besteht darin, neue und alte Filme von neuen Nutzern raten zu lassen. Die Information wäre dann, ob Neu- oder Bestandskunde.

F: _Beschreiben Sie, wie die Liste von $n$ Empfehlungen für einen bestehenden Nutzer entsteht. Gehen Sie auch darauf ein, was methodisch passiert, wenn der Benutzer Filme bewertet._ \(7P\)

A:

\(Teilfrage 1 siehe weiter oben\)

Bewertet ein Nutzer einen Film, dann muss eine Neuberechnung der naiven Prognose des bewertenden Nutzers, eine Neuberechnung der Mittel der gemeinsamen Profile, eine Neuberechnung des Korrelationskoeffizienten zwischen einzelnen Nutzern und der verbesserten Prognose erfolgen. Da dies für alle Nutzer des Streaming-Portals aufwendig ist, sollte dies ggf. im Rahmen einer Batch-Verarbeitung einmal oder mehrmals täglich erfolgen.

F: _Nennen Sie drei Wege, wie Amazooon die Bewertung eines Benutzers messen kann \(mindestens ein Weg muss implizit, mindestens ein Weg explizit sein\)._ \(2\*3 Punkte = \(6P\)\)

A:

**Explizit:**

* Sterne-Bewertung
* Daumen hoch / runter
* Hinzufügen in Favoritenliste

**Implizit:**

* Auswertung der Wiedergabezeit von Filmen, um zu erkennen ob und wann ein Film abgebrochen wurde.
* „Skippen" von Filmen in Serien entspricht negativer Empfehlung
* Ggf. auch, ob Filme wiederholt angeschaut wurden \(aber wahrscheinlich eher selten der Fall\)

F: _Tick, Trick und Track seien drei Benutzer von Amazooon. Trick und Track haben den gleichen Geschmack bei Actionfilmen, für andere Genres aber unkorrelierte Geschmäcker. Tick und Trick haben den gleichen Geschmack bei Liebesfilmen, aber einen genau gegenläufigen Geschmack bei Actionfilmen. Für andere Genres bestehe kein Zusammenhang. Lässt sich dies in dem vorgestellten cf-Standardmodell abbilden? Wenn ja: wie? Wenn nein: Schlagen Sie eine entsprechende Erweiterung vor \(keine Clusterverfahren!\)_ \(6P\)

A:

Nein, Standard-Collaborative Filterung betrachtet immer nur die Ähnlichkeit des Geschmacks über den gesamten Filmbestand. Zur Umsetzung müsste für jedes Genre z. B. Action / Liebesfilm etc. ein eigenes Collaborative-Filterung-Modell erstellt werden.

![](../../.gitbook/assets/grafik%20%2827%29.png)

F: _Geben Sie eine naive Prognose für das Rating des Films der Herr der Ringe für den Benutzer Anton an!_ \(5 Punkte\)

A:

Mittleres Rating von Rater Anton $A$.

$${\widetilde{x}}_{A} = \frac{1}{n}\sum_{}^{}{}\, s_{A} = \frac{4 + 4 + 1 + 5 + 2}{5} = \frac{16}{5}$$

F: _Mit welchem Maß messen Sie die Abhängigkeit im Ratingverhalten zwischen zwei Benutzern?_ \(5 Punkte\)

A:

Um die Abhängigkeit zwischen zwei Benutzern zu messen, kann der Pearson'sche Korrelationskoeffizient verwendet werden. Definiert als:

$$r_{\text{kl}} = \frac{\text{cov}\left( s_{k},s_{l} \right)}{\sigma_{k}\sigma_{l}} = \frac{\sum_{i}^{}\mspace{2mu}\left( x_{i,k} - {\overline{x}}_{k} \right)\left( x_{i,l} - {\overline{x}}_{l} \right)}{\sqrt{\sum_{i}^{}\mspace{2mu}\left( x_{i,k} - {\overline{x}}_{k} \right)^{2}}\sqrt{\sum_{i}^{}\mspace{2mu}\left( x_{i,l} - {\overline{x}}_{l} \right)^{2}}}$$

F: _Berechnen Sie die Abhängigkeit zwischen Anton und Dora sowie zwischen Anton und Emil!_ \(5 Punkte\)

A:

Zunächst sind die Mittel der gemeinsamen Profile zu bestimmen:

$${\overline{x}}_{D} = \frac{2 + 2 + 4 + 1 + 5}{5} = \frac{14}{5}$$

$${\overline{x}}_{E} = \frac{5 + 4 + 2 + 4}{4} = \frac{15}{4}$$

Woraus später der Korrelationskoeffizient bestimmt werden kann. Weiterhin sind die lokalen Mittelwerte für Anton notwendig. Diese sind:

$${\overline{x}}_{A} = \frac{4 + 4 + 1 + 5 + 2}{5} = \frac{16}{5}$$

Und

$${\overline{x}}_{A} = \frac{4 + 4 + 1 + \, 5}{4} = \frac{7}{2}$$

Mit dem Korrelationskoeffizient folgt:

$$
\begin{matrix} r_{A,D} & = \frac{2\left( 4 - \frac{16}{5} \right)\left( 2 - \frac{14}{5} \right) + \left( 1 - \frac{16}{5} \right)\left( 4 - \frac{14}{5} \right) + \left( 5 - \frac{16}{5} \right)\left( 1 - \frac{14}{5} \right) + \left( 2 - \frac{16}{5} \right)\left( 5 - \frac{14}{5} \right)}{\sqrt{2\left( 4 - \frac{16}{5} \right)^{2} + \left( 1 - \frac{16}{5} \right)^{2} + \left( 5 - \frac{16}{5} \right)^{2} + \left( 2 - \frac{16}{5} \right)^{2}}\sqrt{2\left( 2 - \frac{14}{5} \right)^{2} + \left( 4 - \frac{14}{5} \right)^{2} + \left( 1 - \frac{14}{5} \right)^{2} + \left( 5 - \frac{14}{5} \right)^{2}}}  & = - \frac{49}{54} = - 0.9074,  \end{matrix}
$$

$$
\begin{matrix} r_{A,E} & = \frac{\left( 4 - \frac{7}{2} \right)\left( 5 - \frac{15}{4} \right) + \left( 4 - \frac{7}{2} \right)\left( 4 - \frac{15}{4} \right) + \left( 1 - \frac{7}{2} \right)\left( 2 - \frac{15}{4} \right) + \left( 5 - \frac{7}{2} \right)\left( 4 - \frac{15}{4} \right)}{\sqrt{\left( 4 - \frac{7}{2} \right)^{2} + \left( 4 - \frac{7}{2} \right)^{2} + \left( 1 - \frac{7}{2} \right)^{2} + \left( 5 - \frac{7}{2} \right)^{2}}\sqrt{(5 - \frac{15}{4})^{2} + (4 - \frac{15}{4})^{2} + (2 - \frac{15}{4})^{2} + (4 - \frac{15}{4})^{2}}}  & = \frac{11\sqrt{19}}{57} = 0.8412  \end{matrix}
$$

F: _Wie interpretieren Sie diese Abhängigkeit?_ \(5 Punkte\)

A:

Der Korrelationskoeffizient nimmt einen Wert zwischen -1 und 1 an, wobei 1 eine vollständige positive Korrelation indiziert. Die hohe negative Korrelation zwischen Anton und Dora lässt darauf schließen, dass die beiden häufig grundsätzlich gegensätzlich bewerten. Um besser Dora bewertet, umso schlechter bewertet Anton und umgekehrt.

Da der Korrelationskoeffizient für Anton und Emil nahe Eins liegt, lässt sich schließen, dass eine hohe positive Korrelation zwischen Anton und Emil besteht. Die beiden bewerten also sehr ähnlich.

F: _Berechnen Sie eine verbesserte Prognose für das Rating des Films der Herr der Ringe für den Benutzer Anton, die die Abhängigkeit zwischen den Ratern berücksichtigt_. \(5 Punkte\)

A:

![](../../.gitbook/assets/grafik%20%2832%29.png)

F: _Geben Sie eine naive Prognose für das Rating des Buch Rabenfrauen: Roman für den Benutzer Lina an_ \(5 Punkte\)

A:

Die allgemeine Formel für das mittlere Rating von Rater k lautet wie folgt:

$${\widetilde{x}}_{L} = \frac{1}{n}\sum_{}^{}{}\, s_{L} = \frac{4 + 4 + 1 + 5 + 2}{5} = \frac{16}{5}$$

F: _Mit welchem Maß messen Sie die Abhängigkeit im Rating verhalten zwischen zwei Benutzern?_ \(5 Punkte\)

A:

Um die Abhängigkeit zwischen zwei Benutzern zu messen, kann der Pearson'sche Korrelationskoeffizient verwendet werden.

$$
r_{k l}=\frac{\operatorname{cov}\left(s_{k}, s_{l}\right)}{\sigma_{k} \sigma_{l}}=\frac{\sum_{i}\left(x_{i, k}-\bar{x}_{k}\right)\left(x_{i, l}-\bar{x}_{l}\right)}{\sqrt{\sum_{i}\left(x_{i, k}-\bar{x}_{k}\right)^{2}} \sqrt{\sum_{i}\left(x_{i, l}-\bar{x}_{l}\right)^{2}}}
$$

F: _Berechnen Sie die Abhängigkeit zwischen Lina und Felix sowie zwischen Lina und Johannes_ \(5 Punkte\)

A: Ausführlicher Rechenweg siehe [hier](https://github.com/KarelZe/recommendersysteme).

$$
r(Lina,Felix) = -0.9074
$$

$$
r(Lina,Johannes)= 0.1054
$$

F: _Wie interpretieren Sie diese Abhängigkeit?_ \(5 Punkte\)

A:

Zwischen Lina und Felix: Es besteht eine hohe negative Korrelation. Beide bewerten eher gegensätzlich d. h. Filme, die von Lina gut bewertet werden, werden von Felix schlecht bewertet und vice versa.

Zwischen Lina und Johannes: Es besteht nur eine sehr geringe positive Korrelation zwischen Lina und Johannes. Geringe Ähnlichkeit in Bewertungen aber auch keine systematisch gegensätzlichen Bewertungen.

F: _Berechnen Sie eine verbesserte Prognose für das Rating des Buchs Rabenfrauen: Roman für den Benutzer Lina, die die Abhängigkeit zwischen den Ratern berücksichtigt._ \(5 Punkte\)

A: Ausführlicher Rechenweg siehe Solution Exercise 6

$$
x(1,Lina)= 3.558
$$

Lina würden den Roman wahrscheinlich mit 4 Punkten bewerten.

