# Mechanism Design Problems

F: _Was verstehen Sie unter Mechanism Design Problemen beim Design von Recommendersystemen?_

A:

* Grundsätzliche Probleme und unerwünschte Nebeneffekte beim Einsatz von Recommendersystemen.
* Unabsichtliche oder vorsätzliche Schwierigkeiten durch das Sammeln, Aggregieren und Weiterleiten von Empfehlungen.

F: _Nennen Sie drei häufig vorkommende Mechanism Design Probleme und beschreiben Sie diese kurz._

A:

* **Bias in Empfehlungen**
  * Für Eigentümer/Beteiligte von \(Informations-\)Produkten besteht ein starker Anreiz, positive Empfehlungen zu geben. Denn ist ein Produkt schlecht und die Kosten für die Manipulation geringer als der zusätzliche Gewinn, besteht ein hoher Anreiz für Manipulationen. Verkäufer weiß, ob Produkt wirklich gut ist.
* **Free-Riding**
  * Es ist angenehm, Empfehlungen zu konsumieren, aber aufwändig, Empfehlungen/Bewertungen zu geben.
  * Die Folge sind wenige Empfehlungen \(Empfehlung geben ist mit Aufwand verbunden\) oder nicht repräsentative Empfehlungen \(Meckern ist einfacher als Loben\)
* **Glaubwürdigkeit**
  * Unzureichende Trennung zwischen Werbung und objektiven Empfehlungen \(durch den Betreiber des Recommenderdienstes\) für eine Empfehlung an sich.

F: _Erläutern Sie kurz, welche dieser Probleme durch verhaltensbasierte Recommenderdienste \(z.B. die Literaturempfehlungen der Universitätsbibliothek Karlsruhe \(TH\)\) vermieden oder nicht vermieden werden und warum\)_

A:

Mechanism Design Problems stellen bei **Verhaltensbasierten Recommender** wie BibTip weniger ein Problem dar. Siehe nachfolgend:

* **Freeriding** ist fast nicht möglich. Alle Nutzer des OPAC tragen zum Recommendersystem bei, unabhängig davon, ob sie Empfehlungen nutzen. Problem ist wenig präsent.
* **Bias** ist fast nicht gegeben, weil sehr hohe Transaktionskosten bestehen, um eine Empfehlung zu beeinflussen. Gilt auch für Seitenaufrufe durch Web Robots.
* **Glaubwürdigkeit / Credibility** im akademischen Umfeld kommt von der Institution, zu der der OPAC gehört. Dieses Problem kann gelöst werden, indem man Werbung oder Anzeigen jeder Art, die im OPAC ausgespielt werden, klar von Empfehlungen des Recommenders abhebt. Z. B. farblich hinterlegen, Text „Anzeige" \(vgl. Motivating and Supporting User Interaction with Recommender Systems\)

F: _Wie kann man die genannten Probleme lösen bzw. vermeiden? Nennen und beschreiben Sie kurz je zwei Lösungsmöglichkeiten für jedes der genannten Probleme._

A:

Free Riding:

* Anreizsysteme schaffen → Gamification oder Expertenstatus erreichen z. B. Google Maps Local Heros
* Belohnungssysteme schaffen → unter allen Bewertungsgebern werden regelmäßig Gutscheine verlost
* Gegenseitiges Bewerten als Pflicht → AirBnB eigene Bewertung wird nur öffentlich, wenn ich auch bewerte.

Bias in Empfehlungen:

* Keine anonymen Empfehlungen: Nutzer erkennen wer hinter den Kommentaren/ Bewertungen wirklich steckt → keine Anonymisierung
* Verifikation der Empfehlungen: Person muss bei Abgabe von Empfehlungen verifiziert werden

**Begrenzte Rationalität:**

* Recommendersystem muss an die Rationalität appellieren
* Formulierung von möglichst vielen Aspekte als numerische Werte
* Bewertungen erst nach gewisser Zeit nach Kauf zulassen → Sicherstellen, dass Kunde mit Produkt ausgiebig vertraut ist und vermeidet impulsive Bewertungen.

F: _Nennen Sie fünf Mechanism Design Probleme und beschreiben Sie sie kurz. Welche der genannten Probleme können bei einem Empfehlungsdienst wie GroupLens auftreten und welche nicht? Begründen Sie kurz:_

A:

**Free Riding**

* Es ist angenehm, Empfehlungen zu konsumieren, aber aufwändig Empfehlungen/Bewertungen zu geben
* Bewerten von E-Mails explizit durch Bewertung auf Likert Skala oder implizit durch Lesedauer \(vgl. Folie 13 Kapitel CF\) → Problem tritt nicht auf
* Allgemein bezogen auf CF Recommender: tritt weniger auf, da Nutzer selbst Interesse daran haben, Bewertungen abzugeben, da so die für sie empfohlenen Produkte besser passen?

**Feedbackeffekt:**

* Spätere Bewertungen beeinflussen Einschätzung des Produktes weniger als die ersten. Die ersten Bewertungen eines Produktes haben viel größeren Einfluss als spätere Bewertungen
* Ratings anderer Nutzer sind zwar bei GroupLens für andere Nutzer nicht einsehbar. Wird eine News-Mail nur sehr selten bewertet, hat die Bewertungen einen sehr hohen Einfluss gegenüber einer News-Mail, die vielfach bewertet wurde.

**Netzwerkeffekte:**

* Recommendersystem braucht genügend Empfehlungen, um neue Benutzer anzuziehen und weitere Empfehlungen zu erhalten; fehlen Empfehlungen kommen keine neuen hinzu.
* Besteht, denn sind wenige Nutzer, da die News-Mails bewerten, werden alle E-Mails als gleichwichtig interpretiert, die Empfehlungen, die ein Nutzer erhält sind damit schlecht. Erst, wenn kritische Masse an bewertenden Nutzern erreicht ist, um eine gute Leseabdeckung sicherzustellen, ist Problem gelöst.

**Glaubwürdigkeit:**

* Oft sind Werbung und Empfehlung kaum voneinander zu unterscheiden
* Latent vorhanden, sofern die Architekten von GroupLens nicht trennen zwischen Werbung und Empfehlung.

**Bias in Empfehlung:**

* Für Eigentümer/Beteiligte von \(Informations-\)Produkten besteht ein starker Anreiz, positive Empfehlungen zu geben.
* Ja, Fanboys z. B. Linux-Freaks / Windows-Trolle / Autoren des Artikels der News-Mail haben Bias.

F: _Erläutern Sie kurz die Vor- bzw. Nachteile von impliziten gegenüber expliziten Recommendersystemen anhand von Mechanism Design Problemen._

A:

**Implizite Bewertung**

* **Implizite Bewertungen werden aus der Beobachtung von Nutzern erhoben.** 
  * **Vorteile:** 
    * **Free Riding** ist eher unproblematisch, da jeder Nutzer der Recommender benutzt, auch Empfehlungen generiert.
    * **Bias in Empfehlung auf Geberseite** ist für große Systeme unproblematisch, da Transaktionskosten für Beeinflussung von Empfehlungen sehr hoch wären.
  * **Nachteile:**
    * **Glaubwürdigkeit**, ist ein Problem. Es ist möglich, dass Anbieter unzureichend trennt zwischen Werbung und objektiven Empfehlungen.
    * **Privatsphäre vs. Anerkennung.** Schutz der Privatsphäre eher schlecht. Sämtliche Interaktionen mit Recommender werden erhoben, sofern kein Opt-Out**.**
    * **Begrenzte Realität.** Ungelöst.
    * **Feedback-Effekte:** Ungelöst. Liegen nur wenige implizite Empfehlungen vor, dann beeinflussen diese ersten, wenigen Empfehlungen mehr, ob eine Empfehlung generiert wird, als wenn sehr viele Bewertungen vorliegen.
    * **Netzwerk-Effekte:** Ungelöst. Hat System wenige Nutzer, dann werden nur wenige Empfehlungen generiert und in Folge wenige Nutzer angezogen. Aber, da Abgabe impliziter Empfehlungen leichter ist als die Abgabe expliziter Empfehlungen, ist Problem weniger ausgeprägt.

**Explizite Bewertung**

* **Vorteile:** 
  * **Bias in Empfehlung auf Geberseite** ist für große Systeme unproblematisch, da Transaktionskosten für Beeinflussung von Empfehlungen sehr hoch wären.
  * **Privatsphäre vs. Anerkennung.** Unproblematisch, seine Privatsphäre geschützt haben, so braucht er einfach keine öffentliche Empfehlung abzugeben.
* **Nachteile:**
  * **Free Riding** ist ein Problem, da Abgabe einer expliziten Bewertung höheren Aufwand verursacht als implizite Bewertung.
  * **Glaubwürdigkeit**, ist ein Problem. Es ist möglich, dass Anbieter unzureichend trennt zwischen Werbung und objektiven Empfehlungen.
  * **Begrenzte Realität.** Ungelöst.
  * **Feedback-Effekte:** Ungelöst. Liegen nur wenige explizite Empfehlungen vor, dann beeinflussen diese ersten, wenigen Bewertungen mehr, ob eine Empfehlung generiert wird, als wenn sehr viele Bewertungen vorliegen.
  * **Netzwerk-Effekte:** Ungelöst. Hat System wenige Nutzer, dann werden nur wenige Empfehlungen generiert und in Folge wenige Nutzer angezogen. Problematischer bei expliziten Recommendern.

F: _Nennen Sie vier Mechanism Design Probleme und erläutern Sie diese kurz. Welche Lösungen gibt es für die von Ihnen genannten Mechanism Design Probleme? Nennen und erläutern Sie für jedes Problem mindestens einen Lösungsansatz._

A:

Siehe oberhalb.

Zeigen Sie tabellarisch die Vor- bzw. Nachteile von impliziten gegenüber expliziten Recommendersystemen anhand von Mechanism Design Problemen auf.

A:

Siehe oberhalb.

F: _Beschreiben Sie kurz fünf Design Probleme bei Recommenderdiensten und skizzieren Sie jeweils eine mögliche Lösung._ \(5\*3P\)

A:

**Free Riding:**

* Es ist angenehm, Empfehlungen zu konsumieren, aber aufwändig, Empfehlungen/Bewertungen zu geben
* Nash-Gleichgewicht ist der global nicht-optimale Punk \(no rate / no rate\)
* Einführung eines Anreizsystems oder Belohnungssystems:
  * Sodass die Auszahlungsfunktion so geändert wird, dass \(no rate / no rate\) kein Nash-Gleichgewicht mehr ist.

**Bias in Empfehlungen:**

* Für Eigentümer/Beteiligte von \(Informations-\)Produkten besteht ein starker Anreiz, positive Empfehlungen zu geben.
* Keine anonymen Empfehlungen: Nutzer erkennen wer hinter den Kommentaren/ Bewertungen wirklich steckt → keine Anonymisierung
* Verifikation der Empfehlungen: Person muss bei Abgabe von Empfehlungen verifiziert werden

**Begrenzte Rationalität:**

* Menschen entscheiden nur teilweise rational, viele Entscheidungen werden nicht vernünftigerweise getroffen
* Recommendersystem muss an die Rationalität appellieren
* Formulierung von möglichst vielen Aspekte als numerische Werte

**Glaubwürdigkeit:**

* Oft sind Werbung und Empfehlung kaum voneinander zu unterscheiden
* Einführung einer Kommentarfunktion oder Bewertung für Empfehlungen

  Umgang und Trennung zwischen Werbung und Empfehlung sollte transparent sein

  **Feedbackeffekte**

* Spätere Bewertungen beeinflussen Einschätzung des Produktes weniger als die ersten
* Die besten/schlechtesten Empfehlungen anzeigen

F: _Welche vier Schritte sollten für Auswahl und Einsatz eines Recommendersystems beachtet werden? Nennen Sie jeweils eine zugehörige Fragestellung._ \(2\*2P\)

A: Zur Vollständigkeit: Copy Paste aus Vorlesungsfolien \(2011\)

* Produkt/Produzenten/Kunden
* Welche Produkte sollen bewertet werden?
* Bündel von Recommenderdiensten
* Welche Recommenderdienste sollen angeboten werden?
* Transaktionskostenanalyse
* Welche Kosten werden durch Recommenderdienste verändert?
* Netzwerkeffekte und Lock-in
* Welche Netzwerkeffekte existieren?

F: _Was versteht man unter einem Recommender-Dienst auf Basis expliziter bzw. impliziter Empfehlungen? Geben Sie je zwei Beispiele an._ \(2+2\*2P\)

A:

**Implizit:** Vorhersagen von Kaufgelegenheiten aus beobachtetem Kaufverhalten

* Generierung von Vorschlägen aufgrund von Lesezeit von E-Mails bei GroupLens-Recommender.
* Generierung von Kanal-Vorschlägen bei Twitch aufgrund von Wiedergabezeit von Streams durch ähnliche Nutzer.

**Explizit:** Recommendersysteme auf Basis von Konsumentenempfehlungen und Meinungen

* Rezension über Bücher
* Theaterkritiken

F: _Nennen Sie drei häufig vorkommende Mechanism Design Probleme und beschreiben Sie diese kurz. Untermauern Sie die Probleme mit Beispielen aus der Praxis und geben Sie für jedes Problem einen möglichen Lösungsweg an._ \(3\*4=12P.\)

A:

**Begrenzte Rationalität:**

* Menschen entscheiden nur teilweise rational und machen viele irrationale \(unbewusste\) Annahmen.
* **Beispiel:** Empfehlung eines bestimmten Rotweins, da dieser gut zum ausgewählten Käse passt. Kunde kauft trotzdem seinen Lieblingswein
* **Lösung:** Möglichst viele Aspekte als numerische Werte formulieren \(Preis für Wein/Käse; Reifegrad von Käse\)

**Bias von Empfehlungen:**

* Für Eigentümer/Beteiligte von \(Informations-\)Produkten besteht ein starker Anreiz, positive Empfehlungen zu geben und negativ über die Konkurrenz zu berichten
* **Beispiel:** Weinproduzent muss seine Lagerbestände verkaufen, obwohl andere Weine besser zu einem Käse passen müssen.
* **Lösung:** Möglichst keine anonymen Empfehlungen. Auch Einführung eines Bewertungssystems für Empfehlungen ähnlich zu _reddit_ / _bored panda_ kann helfen.

**Glaubwürdigkeit:**

* Oft sind Werbung und Empfehlung kaum voneinander zu unterscheiden
* **Beispiel:** Empfehlung als bezahlte Werbung auf Gourmet Website
* **Lösung:** Umgang und Trennung zwischen Werbung und Empfehlung sollte transparent sein

F: _Das Szenelokal aus Aufgabe 3 möchte einen Recommender bauen. Die Kunden sollen in Zukunft per Tablet bestellen und bekommen während des Bestellvorgangs des Hauptgerichtes passende Getränke und passende Desserts empfohlen._

\(a\) _Sie werden als Recommender-Ersteller eingestellt. Auf welche Punkte sollten Sie achten? Nennen Sie 3 Aspekte und erklären Sie anhand des Use-Case, wie Sie diese einzelnen Aspekte designen würden_ \(3\*2=6P.\)

A:

Aspekte:

1. **Anreizproblematik:**
   * Sind Anreize zum Erstellen von Empfehlungen zu schaffen?
   * Lokal will Kunde dazu bringen, dass er Empfehlungen abgibt → Gibt Kunde am Tablet eine Empfehlung ab, so erhält er ein Süßigkeit for-free.
2. **Produktebene:**
   * Was soll bewertet werden? Wie soll bewertet werden? Wie groß ist die Lebensdauer des Produkts?
   * Kunde kann an seinem Tablet seine jeweiligen Bestellungen \(Hauptspeise, Getränk und Dessert\) nach seinem Verzehr anhand von Likert-Skalen \(1...5\) bewerten. Die Bewertungen sind öffentlich einsehbar. Produkt kann erst bewertet werden, nachdem Sous Chef Gericht in der Küche freigegeben hat.
3. **Zielgruppe meiner Empfehlungen:**
   * An wen richtet sich der Recommender? Wie sieht der Payoff der Beteiligten aus?
   * Zielgruppe: Jeder, der das Szenelokal betritt, soll auch in der Lage seine Bewertungen am Tablet abgeben zu können.
   * Payoff: Gäste im Lokal haben leichtere Entscheidungsfindung. Wirt, kann Speisekarte auf Gerichte hin optimieren, die gut ankommen. Außerdem wird Verkauf gesteigert. \(u. A. Folie 38\)

\(b\) _Welche Art Recommender würden Sie für diesen Zweck bevorzugen? Begründen Sie ca. 4 Sätzen._ \(4P.\)

A:

**Assoziationsregel-Recommender:**

Empfehlungen können sofort für einen neuen Kunden erzeugt werden. So kann den Kunden passend zum Hauptgericht ein häufig dazu konsumierter Nachtisch und ein Getränk angeboten werden. Und sind nicht abhängig vom Benutzer \(kein Coldstart- Problem\). Passende Getränke und Desserts werden empfohlen basierend auf häufig zusammen gekaufte Hauptspeisen/Getränke/Desserts. Finden interessanter Empfehlungen mit mehr als 2 Artikeln \(Getränk, Dessert\) möglich.

Man benötigt dann auch keine Experten, da die Generierung des Assoziationsregeln vollständig aus Transaktionen erfolgt. Einzig Mindest-Support und Mindest-Confidence ist durch Experten festzulegen.

Es besteht allerdings die Notwendigkeit, Transaktionen nach Person zu erheben, d. h. Bestellungen eines Tisches aufzuteilen auf die einzelnen Tischgäste, da ansonsten schlechte Assoziationsregeln generiert werden.

\(Ggf. auch Verwendung von Association Rules mit Constraints sinnvoll, um z. B. nur vegane oder vegetarische Gerichte filtern zu können.\)

\(c\) _Woher würden Sie die Inputs/Daten für ihren Recommender beziehen? Begründen Sie ca. 3 Sätzen._ \(3P\).

A:

* Die Transaktionsdaten müssten über die Bestelltablets erhoben werden. Hierfür muss die Möglichkeit bestehen, Gerichte / Getränke einem Gast zuzuordnen.
* Eine Transaktion wird in einer Transaktionsdatenbank gespeichert, sofern die Bestellung in der App ausgelöst wurde.
* Zwischen den Items einer Transaktion z. B. Id des Gerichts sollte ein Mapping zu den Gerichten selbst besehen z. B. Name des Gerichts, Hintergrundinfo, Allergene.
* Saisonale Gerichte wie Maiforelle auf Spargelbett oder Federweißer sollten von Auswertung ausgeschlossen werden.

Use Case: Sie arbeiten für Jupiter, einen großen, deutschlandweit operierenden Elektronikanbieter, der sein Onlinegeschäft ausbauen möchte. Sie sollen für die Abteilung Haushaltsgeräte einen Recommenderdienst aufbauen: Zusatzartikel, die beim Kauf eines Kühlschrankes oft dazu erworben wurden, sollen künftig auf der Produktseite empfohlen werden. Sie haben sich noch nicht für eine Methode entschieden. Ohne Use Case Bezug max. die Hälfte der Punkte!

F: _Nennen Sie drei Mechanism Design Probleme, die Sie für diesen Use Case erwarten und beschreiben Sie diese kurz._ \(3\*2=6P.\)

A:

**Glaubwürdigkeit:**

* Oft sind Werbung und Empfehlung kaum voneinander zu unterscheiden
* **Use Case-Bezug:** Empfehlung als bezahlte Werbung der Hersteller auf Jupiter Website.

**Begrenzte Rationalität:**

* Menschen entscheiden nur partiell rationell \(z. B. Markentreue / Bewusstsein\) und treffen viele irrationale \(unbewusste\) Annahmen.
* **Use Case-Bezug:** Zum Kühlschrank wird ein mittel-teurer Eisbehälter empfohlen. Kunde kauft am Ende doch den billigen Eisbehälter, da dieser von Boris Becker - seinem Lieblings-Tennisspieler - beworben wird.

**Free Riding:**

* Es ist angenehm, Empfehlungen zu konsumieren, aber aufwändig, Empfehlungen/Bewertungen zu geben
* **Use Case-Bezug:** Kunde konsumiert Empfehlungen von der Jupiter-Website für den Kauf eines neuen Kühlschranks, doch gibt keine Bewertung für andere Produkte ab, die er bereits selbst gekauft hat. Der Bestand an Bewertungen ist gering.
* Geben Sie für jedes von Ihnen genannte Problem einen möglichen Lösungsweg für den Use Case an. \(3\*2=6P.\)

A:

**Free Riding:**

* Belohnungssystem für den Kunden: Kunde erhält einen 5 Euro Gutschein von Jupiter bei seinem nächsten Online-Kauf, nachdem dieser 10 Bewertungen abgegeben hat.

**Begrenze Rationalität:**

* Möglichst viele Aspekte als numerische Werte über die Zusatzartikel auf der saturn-Website angeben. \(Z. B. Durchschnittliche monetäre Einsparung für Artikel "Add-on Kühlschranktemperaturregler\)

**Glaubwürdigkeit:**

* Umgang und Trennung zwischen Werbung und Empfehlung auf der Saturn-Website sollte transparent sein. Z. B. durch Klarnamen zu Bewertung.
* Geben Sie für jede Ihrer Lösungsmöglichkeiten aus \(2\) nur wiederrum ein Folge-Problem an, das durch diese Lösung entstehen könnte! \(3\*2=6P.\)

A:

**Free-Riding:**

* Kunden geben im Schnelldurchlauf Bewertungen ab z. B. Zick-Zack-Muster bei Matrixfragen, ohne sich wirklich darüber Gedanken gemacht zu haben. Im Vordergrund stehen nur die 5 Euro für den nächsten Kauf.

**Begrenzte Rationalität:**

* Kunde fühlt sich erschlagen von der Vielzahl von Informationen der jeweiligen Zusatzartikel, sodass er unsicher in seiner Entscheidung ist, den Zusatzartikel am Ende überhaupt zu kaufen.

**Glaubwürdigkeit:**

* Benötigt vermehrt persönliche Informationen über Personen, die Kommentare/Bewertungen abgeben.
* Zu viel Transparenz hindert wiederum andere, Bewertungen erst abzugeben.
* \(Ohne Use Case Bezug\) Was versteht man unter einem Recommender-Dienst auf Basis expliziter bzw. impliziter Empfehlungen? \(2P.\)

A:

**Explizite Empfehlungen** werden durch den Nutzer ausdrücklich abgegeben z. B. Bewertet der Nutzer mit Sternen oder anhand einer Skala.

Bei **impliziter Empfehlung** wird die **Empfehlung** implizit / ohne Zutun des Nutzers aus dem beobachteten Kaufverhalten erhoben z. B. durch Session-Tracking.

F: _Beschreiben Sie kurz je ein mögliches Beispiel für explizite und implizite Verfahren für den Use Case._ \(2\*2,5P.=5P.\)

A:

**Explizites Verfahren:**

* Nutzer gibt für einen Zusatzartikel, nachdem er diesen verwendet hat, eine Bewertung auf der Saturn-Website ab in Form einer Sterne Bewertung \(1 bis 5\)
* Aufgrund der vielen Bewertungen in Form von Sterne-Bewertungen werden bestimmte Zusatzartikel eher empfohlen als andere.

**Implizites Verfahren:**

* Implizites Verfahren berechnet welche und wie oft bestimmte Zusatzartikel gekauft wurde in Verbindung mit dem Kühlschrank und erstellen darauf aufbauend eine Empfehlungsliste der Zusatzartikel auf der Saturn-Website. Die Datenerhebung erfolgt durch Auswertung von Bestellhistorien ohne Zutun des Users.

F: _Nennen Sie 5 Mechanism Design Problems und erklären Sie diese in 1-2 Sätzen. \(5\*1,5=7,5P.\). Geben Sie zu jedem von Ihnen genannten Problem ein konkretes Beispiel für ein bestehendes Recommendersystem in der Praxis und erklären Sie, wo das Problem auftritt. Erklären Sie kurz \(1-2 Sätze\)._ \(5\*1,5P.=7,5P.\)

A:

**Free Riding:**

* Es ist angenehm, Empfehlungen zu konsumieren, aber aufwändig, Empfehlungen/Bewertungen zu geben
* **Beispiel:** Nur wenige Nutzer schreiben eine Buchrezension auf Good Reads oder Amazon, da das Schreiben mit hohem Aufwand verbunden ist. Viele Nutzer lesen hingegen gern Rezession, um einzuschätzen, ob ein Buch einen Kauf wert ist. Hat ein Benutzer besonders schlechte Erfahrungen gemacht, werden Empfehlungen verfasst, um Frust zu teilen. Die Bewertungen sind dann nicht repräsentativ.

**Bias in Empfehlungen:**

* Für Eigentümer/Beteiligte von \(Informations-\)Produkten besteht ein starker Anreiz, positive Empfehlungen zu geben.
* Verkäufer weiß, ob sein Produkt gut ist. Wenn das Produkt schlecht ist und die Kosten für die Manipulation von Empfehlungen geringer sind als der zusätzliche Gewinn, besteht ein hoher Anreiz für Manipulation.
* **Beispiel:** Vorstand von WeTab GMBH veröffentlichte auf Amazon auf der Produktseite von WeTab begeisterte Rezensionen unter falschem Namen

**Begrenzte Rationalität:**

* Menschen entscheiden nur partiell rationell \(z. B. Markentreue / Bewusstsein\) und treffen viele irrationale \(unbewusste\) Annahmen.
* **Beispiel:** ADAC Empfehlungsseite für Autos. Entscheidung für ein benzinsparendes Automodell, dann aber doch Bestellung von Sonderausstattung, die Treibstoffverbrauch erhöht.

**Glaubwürdigkeit:**

* Oft sind Werbung und Empfehlung kaum voneinander zu unterscheiden
* **Beispiel:** Webseite Mydealz: Jeder Nutzer kann sogenannte "Dealz" einstellen. Das sind Sonderangebote, die der Nutzer entdeckt hat und teilen will. Dabei wird auch Eigenwerbung von Benutzern betrieben

  **Feedbackeffekte:**

* $$n$$ -te Bewertungen beeinflussen Einschätzung des Produktes weniger als die erste Bewertung.
* Amazon Produktseite.
  * Produkt war anfangs zufriedenstellend → Gute Bewertungen
  * Benutzer kaufen Produkt aufgrund guter Kommentare

