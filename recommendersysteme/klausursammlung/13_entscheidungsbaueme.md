# Entscheidungsbäume

{% hint style="success" %}
Hilft dir meine Webseite weiter? Falls du dieses Projekt unterstützen möchtest, kannst du mir gerne einen Kaffee an [paypal.me/markusbilz](https://paypal.me/markusbilz?country.x=DE\&locale.x=de\_DE) spenden. Danke.️:heart:
{% endhint %}



_Sie sind Manager eines Internet-Geschenke Portals. Analysieren Sie die Kaufsituation Ihrer Kunden und identifizieren Sie für die Kaufentscheidung wesentliche Attribute._

A:

Internet-Geschenke Portal bildet Kaufsituation der Kunden ab:

* Produkte haben hohe Kaufwahrscheinlichkeit
* Typischerweise Produkte im niedrigen Preissegment
* Typischerweise kleine Warenkörbe
* Typischerweise physische Produkte
* Typischerweise wenige Repeat-Buys
* Kunden möchten: sich, Familie, Freunde oder Arbeitskollegen beschenken. Portal schlägt Empfehlungen für Geschenke vor auf Basis von vorher abgefragten Basisdaten. (Folie 6-8 + Eigene)

Wesentliche Attribute:

* Geschenk für ...
  * Ihn
  * Sie
  * Ein paar
* Alter
* Zu welchem Anlass
  * Geburtstag
  * Valentinstag
  * Hochzeit
  * ...
* Person ist..
  * Lebhaft
  * Ruhig
  * Emotional
  * ...

F: _Der Kundendialog soll mit Hilfe von Entscheidungsbäumen optimal gesteuert werden. Erläutern Sie kurz, wie ein Entscheidungsbaum gelernt werden kann und wie er dann zur Dialogsteuerung verwendet werden kann._

A:

siehe oberhalb.

**Alternativ:**

* Zunächst ist ein Trainingsdatensatz zu erstellen. Dieser muss die für die Vorhersage relevanten Attribute enthalten und das zu prognostizierende Label. Ein Testdatenbestand ist zurückzuhalten.
* Anhand des Informationsgewinns wird dann das aussagekräftigste Attribut im Datenbestand ausgewählt. Hierfür ist es notwendig den Informationsgewinn aller Attribute zu berechnen.
* Das aussagekräftigste Kriterium ist dann für den ersten Split herangezogen. Analog fährt man für dessen Kindknoten fort, sofern das vorgenommene Split nicht alle Attribute vollständig erklärt und ermittelt wieder weitere Attribute, die dann den höchsten Informationsgewinn bieten.
* Optional ist ein Pruning-Schritt nach dem vollständigen Aufbau des Baums notwendig, indem der Baum zurückgeschnitten wird.
* Der vollständig aufgebaute Entscheidungsbaum sollte dann mittels des Testdatenbestands unter Verwendung geeigneter Metriken z. B. Accuracy evaluiert werden. (vgl. 18 ff.)

**Dialogsteuerung:** Für jedes Produkt wird ein Entscheidungsbaum gelernt. Von Wurzel aus werden Attribute über den Kunden abgefragt. Blätter des Baums enthalten dann, ob Produkt empfohlen wird, oder nicht. Alle Produkte mit Entscheidungsbäume mit „Empfohlen" werden ausgegeben.

Wie prüfen Sie, ob gelernte Entscheidungsbäume gut für Ihr System geeignet sind?

A:

Siehe oberhalb.

_Die Geschäftsführung der Nützlinge Online GmbH stellt fest, dass es den B2C-Kunden schwerfällt, die für sie richtigen Nützlinge auszuwählen. Sie sollen einen Empfehlungsdienst bauen, der dem Endkunden je nach Schädlingsbefall über Diagnosefragen einen geeigneten Nützling empfiehlt (Sind die Blätter von Milben entfallen? Wenn ja, empfehlen wir die Raubmilbe)_

F: _Was für eine Methode empfehlen Sie?_ (2P)

A:

Entscheidungsbäume (Decision Trees)

F: _Die Geschäftsführung hat fünf Gärtner engagiert, die für Sie das notwendige Experten-Wissen entwickeln sollen. Die Gärtner nennen Ihnen 5 Dimensionen, nach denen eine Auswahl des Nützlings erfolgt (Aussehen Wurzeln, Stamm, Blätter, Farbe und Geruch). Skizzieren Sie einen geeigneten Fragebogen/Erfassungsbogen, den Sie den Gärtnern vorlegen._ (5P)

A:

Fragebogen

Wurzel ist ... Baum 1 Baum 2

* Tiefwurzler
* Flachwurzler

Stamm ist ....

* Klein (\\<5m)
* Mittel (von 5m bis 10m)
* Groß (über 10 m)

Blätter sind ...

1. Rund
2. Eckig

Farbe ist ...

* Blau
* Grün
* Rot

Geruch ist ...

* Angenehm
* Stinkt
* neutral
* Die Experten füllen den Erfassungsbogen aus. Nach welchem Maß M wählen Sie das erste, wichtigste Kriterium aus, das dem Kunden vorgelegt wird? (3P)

A: Entropie nach Shannon im Information Gain.

F: _Geben Sie die mathematische Definition von M an._ (3P)

A:

$$H = - \sum_{i = 1}^{n}{}p_{i}\log_{2}p_{i}$$

$$\Delta H\ = \ H\left( y \right) - H\left( y\mid x \right)$$

Mit $$H(y \mid x) = - \sum_{i,j} p(i,j)\log_{2}p(y = j \mid x = i)$$

1. Das wichtigste Kriterium sei das Aussehen der Blätter. Ihre Experten geben 8 Merkmalsausprägungen an. Wie groß kann M in diesem Fall minimal bzw. maximal werden? (3+3P)

A:

**Minimal:** Gilt $$p_{i} = \, 1$$ und alle anderen $$p_{j} = 0$$, mit $$j = 1,\ldots,i - 1,i + 1,\cdots, 8$$ gilt; (Bei Sicherheit über Ergebnis verschwindet Entropie), dann ist $$H = 0$$.

**Maximal:** Liegt Gleichverteilung vor, d. h. $$p_{i} = \frac{1}{8}$$. Dann gilt:

$$H = - \log_{2}\left( \frac{1}{8} \right) = 3$$ (Vgl. Folie 38)

1. Was bedeutet ein minimaler bzw. maximaler Wert? (3+3P)

Ein **minimaler Wert** (d. h. $$0$$) bedeutet, dass ein Attribut perfekt die Output-Variable erklärt und **keine** Unsicherheit mehr besteht. Man hat homogene Klassen nach Split vorliegen.

Ein **maximaler Wert** (d. h. $$3$$) bedeutet, dass eine hohe Unsicherheit besteht. Nach Split sind Klassen sehr heterogen. Der durchschnittliche Informationsgewinn ist gering. (vgl. Tutorium 6 with solutions: Slide 13+14)

F: _Stellen Sie einen Entscheidungsbaum zum Kauf eines Computers graphisch dar_ (6P.):

(a) Typ: Netbook, Notebook, Workstation

(b) CPU: Mobilprozessor Intel (nur für Notebooks), Mobilprozessor AMD (nur für Notebooks), Standardprozessor Intel (nur für Workstations), Standardprozessor AMD (nur für Workstations).

(c) TV-Karte: USB (alle Systeme), PCIe (nur Workstation)

A:

Annahme: Knoten werden weggelassen, sofern sie keine Entscheidungsrelevanz mehr haben.

![(Eigene Darstellung)](<../../.gitbook/assets/grafik (3) (3) (4) (4) (4) (4) (4) (4) (2) (1) (1).png>)

F: _Die Reihenfolge der Attribute ist bei einem Entscheidungsbaum wichtig. Wann ist ein Attribut ein "gutes" (sollte früh abgefragt werden)? Können Sie aus der obigen Teilfrage beurteilen, welches Attribut das "beste" ist? Wenn ja, warum? Wenn nein, was fehlt, um diese Aussage treffen zu können?_ (6+5P.=11P.)

A:

**Allgemein:** Ein Attribut ist ein „gutes" Attribut (Attribut, das für frühzeitigen Split verwendet werden sollte), sofern man einen möglichst hohen durchschnittlichen Informationsgewinn erzielt.

**Teilfrage:**

Was fehlt?: Outputvariable "Kauf" mit den jeweiligen Zielprädikaten "Ja" und "Nein" für alle Datensätze

Wie oft welche Kombinationen vorkommen.

F: _Nennen Sie zwei Probleme, die Entscheidungsbäume haben können, wenn man sie mit Hilfe von Beispieldaten trainiert. Erklären Sie, wie es dazu kommt._ (4+4P.=8P.)

A:

**Overfitting:** Es werden zufällige und irrelevante Zusammenhänge gelernt. Gründe können Noise, fehlende repräsentative Instanzen o. Ä. sein. Der Baum generalisiert zu wenig und lernt hingegen die Trainingsdaten perfekt.

**Noise**: Falsch gelabelte Instanzen können den Labels ähnlicher Instanzen widersprechen. Es wird dann eine weitere Fallunterscheidung gelernt, was zu Overfitting führt. Der Baum wird tiefer. (eigene)

**Underfitting**: Der Baum ist nicht detailliert genug. Dies kann passieren, wenn er zu früh abgeschnitten (gepruned) wird und/oder es nicht genug Trainingsdaten gibt, d.h. die zugrundeliegenden Daten werden nicht ausreichend repräsentiert; die Entscheidungsebene wird zu simpel (eigene)

Stellen Sie einen Entscheidungsbaum zum Kauf eines Handys graphisch dar (6P.):

(a) OS: Android, iOS, Windows Mobile

(b) Display: 3,2\\"(nur Android und Win Mobile), 3,5\\"(alle), 4,0\\"(nur Android und iOS)

(c) RAM: 512 MB (nur Android), 768 MB (alle), 1024 (nur iOS)

A:

![(Eigene Darstellung)](<../../.gitbook/assets/grafik (19).png>)

F: _Die Reihenfolge der Attribute ist bei einem Entscheidungsbaum wichtig. Wann ist ein Attribut ein "gutes" (sollte früh abgefragt werden)? Können Sie aus der obigen Teilfrage beurteilen, welches Attribut das "beste" ist? Wenn ja, warum? Wenn nein, was fehlt, um diese Aussage treffen zu können? (6+5P.=11P.)_

A: siehe oberhalb.

F: _Nennen Sie zwei Probleme, die Entscheidungsbäume haben können, wenn man sie mit Hilfe von Beispieldaten trainiert. Erklären Sie, wie es dazu kommt._ (4+4P.=8P.)

A: Siehe oberhalb.

_Gegeben seien untenstehende Beobachtungsdaten. Es soll basierend auf Outlook, Temperature, Humidity und Wind vorhergesagt werden, ob Tennis gespielt werden soll, oder nicht._

![](<../../.gitbook/assets/grafik (4).png>)

F: _Wie entscheiden Sie, welches Attribut Sie als erstes in den Entscheidungsbaum einführen wollen? Erklären Sie dies in 5-6 Sätzen._ (6P.)

A: Vorlesung (Folie 39+40) grob in seinen Worten wiedergegeben

* Für die Wahl des besten Attributs wird als Maß für Information in Daten die Entropie verwendet
* Benutze Algorithmus, mit dem die Wahl des besten Attributs berechnet wird.
* Berechne den Informationsgehalt in den Daten, bevor ein Attribut überhaupt zur Hilfe genommen wird (Entropie H(y), y ist Zielprädikat mit den Werten "ja" und "Nein"
* Berechne Informationsgehalt in Daten unter der Bedingung, dass wir das Attribut kennen (bedingte Entropie H(y|x) )
* Berechne Informationsgewinn für das Attribut: H(y) - H(y|x)
* Gewählt wird das Attribut mit dem größten Informationsgewinn
* Geben Sie eine mathematische Definition der Entropie H nach Shannon. (2P.)

A: Siehe oberhalb.

F: _Wie hoch ist im obigen Beispiel, Reihen D1-D6, die Entropie von "Outlook"?_ (5P.)

A:

![(Eigene Darstellung)](<../../.gitbook/assets/grafik (34).png>)

**Entropie:**

$$
H_{o}\left(\frac{3}{6} ; \frac{3}{6}\right)= 
-\frac{1}{2} \log _{2} \frac{1}{2}-\frac{1}{2} \log _{2} \frac{1}{2} \approx 1
$$

1. Erklären Sie: Was ist in obigem Beispiel der Informationsgewinn des Attributes "Outlook"? (Nicht berechnen, nur erklären!) (5P.)

A:

* Der Informationsgewinn $$\Delta H$$ gibt die Änderung der Entropie vor und nach Benutzung eines Attributes $$A$$ an und stellt somit die erwartete Reduzierung der Entropie durch die Einsortierung über $$A$$ (z.B. Outlook) dar. Der Informationsgewinn für Outlook berechnet sich aus der gewichteten Summe der Informationsgewinne der einzelnen Attribute (z.B. "sunny").
* Für Outlook ist zu sehen, dass "Sunny" und "Overcast" die Zielvariable "Tennis" bereits homogen separieren, weshalb ein hoher Informationsgewinn für die Einsortierung des Attributs $$A=\text{"Outlook"}$$ zu erwarten ist. Wenn gilt $$\text{Outlook} = \text{sunny}$$wird nie Tennis gespielt, während bei $$\text{Outlook} = \text{overcast}$$ immer Tennis gespielt wird.

F: _Für ein beliebiges Attribut, nicht beschränkt auf das Beispiel: Wie groß kann die Entropie minimal und maximal werden? Wann ist dies der Fall?_ (1+1+2,5+2,5=7P.)

A:

**Minimal:** Gilt $$p_{i} = \, 1$$ und alle anderen $$p_{j} = 0$$, mit $$j = 1,\ldots,i - 1,i + 1,\, n$$ gilt; (Bei Sicherheit über Ergebnis verschwindet Entropie), dann ist $$H\, = \, 0$$.

**Maximal**:

Entropie ist nach oben nicht beschränkt. Es gilt:

$$
\begin{aligned}
H\left( S \right) &= - \sum_{j}^{}{}\mspace{2mu} p_{j}*\log_{2}p_{j} \\&= - \sum_{i = 1}^{n}{}\mspace{2mu}\frac{1}{n}*\log_{2}\frac{1}{n} = - n*\left( \frac{1}{n}*\left( \log_{2}1 - \log_{2}n \right) \right) \\&=- 1*\left( 0 - \log_{2}n \right) = \log_{2}n \rightarrow \infty\left( n \rightarrow \infty \right)
\end{aligned}
$$

Entropie wird **maximal** bei Gleichverteilung.

_Sie wollen ein Gesundheitsportal aufbauen. Für einfache Krankheiten wollen Sie den Patienten mittels einer Selbstdiagnose unterstützen, pflanzliche, nebenwirkungsarme Medikamente für sich zu finden, die dieser dann bei Ihnen online bestellen kann. Beispiel: Es ist Frühjahr, der Patient berichtet Husten, vermehrte Schleimbildung und erhöhte Temperatur. Empfehlung: Umkaloabo gegen akute Bronchitis._

F: _Welche Methode würden Sie für diesen Dienst einsetzen? Begründen Sie in einem Satz._ (2P.)

A:

Es sollte ein Entscheidungsbaum verwendet werden, da dieser anhand gegebener Attributausprägungen wie Temperatur oder Husten (ja / nein), eine Produktempfehlung generieren lässt. Die Attributkombinationen für ein Medikament könnte durch Experten anhand des Beipackzettels generiert werden. Recommender wie Collaborative Filterung oder Association Rules sind im medizinischen Bereich sogar gefährlich.

F: _Sie sollen einen geeigneten Erfassungsbogen für Experten (Ärzte, Apotheker) entwickeln. Für den Anfang erfassen Sie folgende Symptome: Körpertemperatur, Allgemeinbefinden, betroffene Körperbereiche, Dauer der Erkrankung, Alter des Patienten, Jahreszeit. Skizzieren Sie einen geeigneten Fragebogen/Erfassungsbogen, den Sie den Experten vorlegen._ (5P.)

A:

Fragebogen

Körpertemperatur ist ...

* normal
* erhöht

Allgemeinbefinden ist ....

* normal
* schlapp

betroffene Körperbereiche ...

1. Kopf
2. Torso
3. Extremitäten

Dauer der Erkrankung ist ...

* kleiner 3 T
* kleiner T
* größer 14 T

Alter ist ...

* kleiner 18 Jahre
* größer 18 Jahre größer 60 Jahre
* größer 60 Jahre

Jahreszeit ist

* Frühling
* Sommer
* Herbst
* Winter
* Die Experten füllen den Erfassungsbogen aus. Nach welchem Maß M wählen Sie das erste, wichtigste Kriterium aus, das der Patient beantworten soll? (3P.)

A: Entropie nach Shannon enthalten im Informationsgewinn.

F: _Geben Sie die mathematische Definition von M an_. (3P.)

A: Siehe oberhalb.

F: _Das wichtigste Kriterium sei der betroffene Körperbereich. Ihre Experten geben 32 Merkmalsausprägungen an. Wie groß kann M in diesem Fall minimal bzw. maximal werden?_ (3+3P.)

A:

**Minimal:** Gilt $$p_{i} = \, 1$$ und alle anderen $$p_{j} = 0$$, mit $$j = 1,\ldots,i - 1,i + 1,\, 32$$ gilt;

Bei Sicherheit über Ergebnis verschwindet Entropie, dann ist $$H\, = \, 0$$.

**Maximal:** Liegt Gleichverteilung vor, d. h. $$p\_{i} = \frac{1}{32}$$. Dann gilt:

$$
H = - \log_{2} \left(\frac{1}{32} \right) = 5
$$

(Vgl. Folie 38)

F: _Was bedeutet ein minimaler bzw. maximaler Wert?_ (3+3P.)

A:

Ein **maximaler Wert** (d. h. $$0$$) bedeutet, dass ein Attribut perfekt die Output-Variable erklärt und **keine** Unsicherheit mehr besteht. Man hat homogene Klassen nach Split vorliegen.

Ein **minimaler Wert** (d. h. $$5$$) bedeutet, dass eine hohe Unsicherheit besteht. Nach Split sind Klassen sehr heterogen. Der durchschnittliche ist Informationsgewinn gering.

_Das neue Szenelokal in Karlsruhe hat momentan zwei Tagesmenüs im Einsatz. Um Kosten zu sparen möchte das Restaurant auf ein Tagesmenü pro Tag wechseln. Der Chefkoch hat das Gefühl das die Kunden wetterabhängig, das eine oder das andere Tagesmenü wählen._

![](<../../.gitbook/assets/grafik (29).png>)

F: _Geben Sie die mathematische Formel für die Entropie an und erklären Sie die verwendeten Variablen._ (2\*1,5=3P.)

A: Siehe oberhalb.

F: _Wie groß kann die Entropie minimal und maximal werden? Wann ist dies jeweils der Fall? (Bitte beantworten Sie diese Frage allgemein für ein Attribut und ohne Bezug auf den Use-Case)._ (2\*1,5=3P.)

A: Siehe oberhalb.

F: _Berechnen Sie den Informationsgehalt des Inputattributes Wetter mit Hilfe eines Entscheidungsbaums. Geben Sie auch Ihre Zwischenergebnisse und den Teilbaum für Wetter an. Zeichen Sie den Teilbaum._ (10P.)

A:

![(Eigene Darstellung)](<../../.gitbook/assets/grafik (10).png>)

**Informationsgewinn:**

A: $$H_0 (\frac{5}{8}, \frac{3}{8}) = 0.95$$

$$H_{\text{Wetter=sonnig}} (\frac{4}{6}, \frac{2}{6}) = 0.92$$

$$H_{\text{Wetter=bewölkt}} (\frac{1}{2}, \frac{1}{2}) = 1$$

$$\text{Durchschnittlicher Inf. G. Wetter} = (0.95-0.92) \left(\frac{6}{8}\right) + (0.95 -1) \times \left(\frac{2}{8}\right) = 0.01$$

F: _Halten Sie aus diesem Grund das Wetter für ein aussagekräftiges Output Attribut. Begründen Sie in 3 Sätzen._ (2P.)

A: Wetter ist ein wenig aussagekräftiges Attribut. Einerseits liegt der durchschnittliche Informationsgewinn nahe 0, andererseits sind die Datensätze, die nach dem Split mit dem Attribut einem Knoten zugeordnet sind, sehr heterogen (vgl. bei sonnig 4x Menü 1 und 2x Menü 2) Ein besseres Attribut wäre hier Temperatur, da es die Ausgabevariable perfekt erklärt ( Menü 1, →20 Grad -→ Menü 2). Somit benötigt man das Attribut Wetter überhaupt nicht.

F: _Die Restaurantleitung bittet Sie eine Regel aufzustellen, nach der entschieden wird, wann welches Tagesmenü zum Einsatz kommen soll. Berechnen Sie von dem entsprechenden Attribut den Informationsgewinn und geben Sie eine Handelsempfehlung für das Restaurant ab. Welchen Vorteil hat das von Ihnen gewählte Attribut in Aufgabenteil 4?_ (5+2= 7P.)

A: Es sollte das Attribut Temperatur gewählt werden, da es die Output-Variable **vollständig erklärt**. D. h. nach Split mit Temperatur sind alle Menüs innerhalb eines Knotens homogen. Darüber hinaus ist der erlernte Baum kleinstmöglich.

![(Eigene Darstellung)](<../../.gitbook/assets/grafik (26).png>)

**Informationsgewinn:**

A: H\_0 (5/8, 3/8) = 0.95

H\_Temperatur=\\<20° (5/5; 0/5) = 0

H\_Temperatur=größer 20° (0/3; 3/3) = 0

Durchschnittlicher Inf. G. Temperatur = (0.95-0) \* (5/8) + (0.95 -- 0) \* (3/8) = 0.95

**Handelsempfehlung:**

* Bei Temperaturen unter 20 Grad sollte das Restaurant genügend Zutaten für Menu 1 vorrätig haben
* Bei Temperaturen über 20 Grad sollte das Restaurant genügend Zutaten für Menü vorrätig haben. (vgl. Übung)

_Ein Kino on Karlsruhe möchte derzeit aus zwei Filmen auswählen. Der Manager hat das Gefühl, dass die Kunden den Film abhängig von ihrem Alter und Geschlecht auswählen._

![](<../../.gitbook/assets/grafik (42).png>)

F: _Geben Sie die mathematische Formel für die Entropie an und erklären Sie die verwendeten Variablen_ (2\*1,5=3P)

A: Siehe oberhalb.

F: _Wie groß kann die Entropie minimal und maximal werden? Wann ist dies jeweils der Fall? (Bitte beantworten Sie diese Frage allgemein für ein Attribut und ohne Bezug auf den Use-Case)._ (2\*1,5=3P.)

A:

A: Siehe oberhalb.

F: _Berechnen Sie den Informationsgehalt des Inputattributes Geschlecht mit Hilfe eines Entscheidungsbaums. Geben Sie auch Ihre Zwischenergebnisse und den Teilbaum für Wetter an. Zeichen Sie den Teilbaum._ (10P.)

A:

![(Eigene Darstellung)](<../../.gitbook/assets/grafik (5).png>)

**Informationsgewinn:**

A: H\_0 (5/8, 3/8) = 0.95

H\_Geschlecht=m (4/5; 1/5) = 0.72

H\_Geschlecht=w (1/3; 2/3) = 0.92

Durchschnittlicher Inf. G. Geschlecht = (0.95-0.72) \* (5/8) + (0.95 -- 0.92) \* (3/8) = 0.16

F: _Halten Sie aus diesem Grund das Geschlecht für ein aussagekräftiges Outputattribut. Begründen Sie in 3 Sätzen._ (2P.)

A: Geschlecht ist ein wenig aussagekräftiges Attribut. Einerseits liegt der durchschnittliche Informationsgewinn nahe 0 (vgl. 0.16), was ein Indiz für einen schlechten Split ist. Andererseits sind die Datensätze, die nach dem Split mit dem Attribut „Geschlecht" einem Knoten zugeordnet sind, sehr heterogen (vgl. bei „männlich" 4x Film 1 und 1x Film 2 bzw. bei weiblich 1x Film 1 und 2x Film 2)

F: _Die Kinoleitung bittet Sie eine Regel aufzustellen, nach der entschieden wird, wann welcher Film zeigen soll. Berechnen Sie von dem entsprechenden Attribut den Informationsgewinn und geben Sie eine Handelsempfehlung für das Kino ab. Welchen Vorteil hat das von Ihnen gewählte Attribut in Aufgabenteil 4?_ (5+2= 7P.)

A:

**Vorteil:** Es sollte das Attribut Alter gewählt werden, da es die Output-Variable **vollständig erklärt**. D. h. nach Split mit Alter sind alle Filme innerhalb eines Knotens homogen.

**Handlungsempfehlung:** Kunden über 35 sollte der Film 2 angeboten werden, Kunden unter 35 sollte der Film 1 angeboten werden.

![(Eigene Darstellung)](<../../.gitbook/assets/grafik (36).png>)

**Informationsgewinn:**

A: H\_0 (5/8, 3/8) = 0.95

H\_Temperatur=\\<20° (5/5; 0/5) = 0

H\_Temperatur= größer 20° (0/3; 3/3) = 0

Durchschnittlicher Inf. G. Temperatur = (0.95-0) \* (5/8) + (0.95 -- 0) \* (3/8) = 0.95

_Bei der Entwicklung eines neuen Sensors zur Früherkennung von Stoffwechselstörungen wurde die Existenz von drei Enzymen (A, B, und C) im Blut gemessen:_

![](<../../.gitbook/assets/grafik (33).png>)

F: _Berechnen Sie den Informationsgewinn für jedes der drei Attribute (9P) und geben Sie die Formel für die Entropie und den Informationsgewinn an_ (2\*2 = (4P)).

A:

**Informationsgewinn:**

A:

$$
H_0 = (\frac{90}{100}, \frac{10}{100}) = 0.47
$$

H\_A=1(85/85; 0/85) = 0

H\_A=0(5/15; 10/15) = 0.92

Durchschnittlicher Inf. G. A = (0.47-0) \* (85/100) + (0.47 -- 0.92) \* (15/100) = 0.33

B: H\_0 (90/100, 10/100) = 0.47

H\_B=1(80/80; 0/80) = 0

H\_B=0(10/20; 10/20) = 1

Durchschnittlicher Inf. G. B = (0.47-0) \* (80/100) + (0.47 -- 1) \* (20/100) = 0.27

C: H\_0 (90/100, 10/100) = 0.47

H\_C =1(50/50; 0/50) = 0

H\_C=0(40/50; 10/50) = 0.72

Durchschnittlicher Inf. G. C = (0.47-0) \* (50/100) + (0.47-- 0.72) \* (50/100) = 0.11

**Ergebnis:** Enzym A sollte gewählt werden, weil höchster Informationsgehalt.

**Formel Entropie**

Siehe oberhalb.

**Formel Informationsgewinn**

$$\Delta H\ = \ H(y) - H(y \mid x)$$

F: _Welches der Attribute sollte als erstes für den Aufbau eines Entscheidungsbaums verwendet werden?_ (4P)

A: Attribut A, siehe vorherige Teil-Aufgabe.

F: _Zeichnen Sie den kompletten Entscheidungsbaum!_ (4P)

A:

![(Eigene Darstellung)](<../../.gitbook/assets/grafik (8).png>)

F: _Ist der Entscheidungsbaum optimal?_ (4P)

A:

Ja, denn würde man man B = no mit dem Attribut A weiter aufsplitten, hätte man weiterhin heterogene Attribute je Node. Mit dem Split mit A und dann C sind jedoch die Labels in beiden Knoten nach dem Split homogen. Damit alle Output-Variablen vollständig erklärt.

Der Baum ist optimal, da er kleinstmöglich ist. Der Baum, der zuerst mit B und dann mit C splittet, hat dieselbe Tiefe. Der Baum ist es bestehen damit mehrere optimale Bäume.
