---
description: >-
  Mitschrift zum Vortrag mit dem Titel "Das IT-Sicherheitsgesetz in der Praxis:
  Das BSI als zentrale Bundesbehörde für IT-Sicherheit nach dem
  IT-Sicherheitsgesetz 2.0" von Moritz Glade.
---

# ⚖ Das IT-Sicherheitsgesetz in der Praxis

## Das BSI

* **Leitsatz:** Das BSI als Cyber-Sicherheitsbehörde des Bundes gestaltet Informationssicherheit in der Digitalisierung durch Prävention, Detektion und Reaktion für Staat, Wirtschaft und Gesellschaft.
* Leitsatz leitet sich aus Gesetz ab:
  * BSI ist eine Bundesbehörde, die zum Geschäftsbereich des BMI gehört. Ist die zentrale Stelle für Informationssicherheit auf nationaler Ebene, nicht aber auf Länderebene. (§ 1 Satz 1, 2 BSIG)
  * BSI arbeitet auf Grundlage wissenschaftlich-technischer Erkenntnisse (umstritten z. B. Stand der Technik). Weniger nach politischen Maßstäben (ebenfalls umstritten). (§ 1 Satz 3 BSIG)
  * BSI hat Eingriffsbefugnisse (§ 3 ff BSIG)
* Jedes Referat des BSI hat Anknüpfungspunkt zu **Aufgabenkatalog** (§ 3 BSIG).
* Nur Informationshalber: BSI wurde in 1991 gegründet. Anfangs nur IT-Beratung der Bundesbehörden und Schutz der Netze des Bundes. 2015 wurde BSI zur Aufsichtsbehörde. Auch wurde dann zum erstmal Reverse Engineering betrieben. In 2017 wurde NIS Richtlinie umgesetzt. In 2021 kam Kontrolle der Bundes IT hinzu und KRITIS+, Verbraucherschutz und IT-Sicherheitskennzeichen hinzu.
* BSI arbeitet mit anderen Behörden z. B. BAFIN / Akteuren zusammen.

## Motivation für die IT-Sicherheitsgesetze: Kritische Bedrohungslage, die über die Bundes-IT hinausgeht

* Motiviert durch IT-Sicherheitsvorfälle.
* Ziel ist die **(Wirtschafts-)erpressung**: Häufig durch Ransomware wie WannaCry. Ransomware ist ein Schadprogramm das Daten verschlüsselt. Gegen Geldzahlung wird Entschlüsselung versprochen.
* Ziel ist die **(Wirtschafts-)spionage**: Häufig mit Spionage Malware wie Sandworm. Ein Trojaner injiziert Schadcode in den identifizierten Endpunkt. Zweck ist der Diebstahl von Zugangsdaten, Geschäftsheimnissen, sensiblen Unternehmensdaten oder IP.
* Ziel ist die **(Wirtschafts-)sabotage**: Häufig mit Sabotage Trojanern wie Stuxnet. Trojaner, die gezielt industrielle Kontrollsysteme angreifen. Häufig staatlich gesteuert. Einfach umzusetzen, wenig teuer in der Umsetzung. Verursacht scherwiegende Störungen bis zum Shutdown.

## Herausforderungen bei der Erstellung von Gesetzen zum Schutz

1. Komplexität der Technik nimmt zu. Führt zu mehr kritischen Lücken.
2. Problem, das Markt mit unsicheren IT-Produkten überschwemmt ist. IT-Sicherheit kommt häufig bei Produktentwicklung von (Billig)-Produkten zu kurz. BSI führt Produktuntersuchungen durch.
3. Menschliches Problem der fehlenden Awareness in der Bevölkerung. Organisation und Sensibilisierung für IT-Sicherheit.

## Kritische Infrastrukturen🧫

* Schwierig zu bestimmen was kritische Infrastruktur ist per Gesetz. Gesetz enthält dadurch nur abstrakte Kriterien, um zu definieren, was kritische Infrastruktur ist.
* **Beispiele:**
  * Kraftwerk ist kritisch
  * Klärwerk ist kritisch
  * Ölhafen ist kritisch
  * Uni ist nicht kritisch
  * Zahnarzt ist nicht kritisch
  * Krankenhaus ist kritisch
  * Pharmalager ist kritisch
  * Militärgerät ist nicht kritisch
  * Kulturbetrieb ist nicht kritisch
  * Autowerk ist nicht kritisch
  * Bahn ist kritische Infrastruktur
  * Kölner Dom ist keine kritische Infrastruktur
  * Bankensystem ist kritisch
  * Bundesverfassungsgericht ist nicht kritisch
  * Müllentsorgung ist kritisch
* Zwei (qualitative) Merkmale für kritische Infrastruktur:

1. Erhebliche Versorgungsengpässe z. B. versorgt Kölner Dom nicht Deutschland. Quantitatives Merkmal: Schwellwert muss überschritten werden z. B. müssen min. 0.5 Mio Leute versorgt werden. Qualitatives Merkmal: Versorgung mit Dienstleistung, die wichtig ist. Qualitative Dienstleistungstypen: Energie, Wasser, Ernährung, IT und Telekommunikation, Siedlungsabfall, Transport und Verkehr, Gesundheit und Finanz- und Versicherungswesen.
2. Gefährdung für die öffentliche Sicherheit.

## Selbst-Identifizierung👨‍🔬

* Identifizierung als **kritische Infrastruktur** durch **Selbstidentifizierung** durch Unternehmen selbst anhand der Kritis-Verordnung. Viele Unternehmen wollen dabei zwar Informationen zu kritischen Lücken in ihrem Sektor, aber selbst nicht kritisch sein. Es gibt in Deutschland ca. 2000 - 3000 kritische Unternehmen. Umgekehrt existieren Unternehmen die wegen (Melde- / Finanz-)Aufwand nicht kritisch sein wollen, etwa BVG. Es werden einfache, objektive Kriterien vorgegeben, ob Infrastruktur kritisch ist.
* **Beispiel:** Zunächst qualitative Sektorenzuordnung z. B. Transport und Verkehr. In der Anlage der Kritis-Verordnung ist dann definiert, dass ÖPNV z. B. Leitsystem kritisch ist. Für jede Anlage existiert dann dann in Kritis Anlage ein konkreter Schwellwert.
* **Probleme:** Graubereiche z. B. Flughafen fällt aus kritischer Infrastruktur raus wegen Covid, wo Zuordnung nicht einfach ist. Erfordert Abwägung, wie man Unternehmen weiterbetreut. Auch in Gegenrichtung. Unternehmen im Graubereich sind selten.

## Notwendigkeit zu Gesetz trotz Kritis🤷‍♀️

* Staat darf **nicht** ohne Gesetz tätig werden d. h. nur mit gesetzlicher Ermächtigungsgrundlage handeln. Etwa ist Hack-back nicht ohne Weiteres möglich. Verlangsamt staatliche Reaktion.
* Staat darf auch nicht gegen Gesetze verstoßen. Kann nur im Rahmen bestehender Gesetze handeln und muss dies richtig anwenden.
* Nationales Sicherheitsgesetz notwendig, weil europäisches Recht nur bei Verordnung umsetzbar ist. EU-Richtlinien z. B. NIS-Richtlinie muss erst national umgesetzt werden z. B. in Kritis.

## Was das BSI darf?

### Sonderbefugnisse des BSI

1. Zentrale Meldestelle für IT-Sicherheit
2. Abwehr von Schadprogrammen und Gefahren z. B. wie entwickeln sich Angriffsmuster? Wie wird Bedrohungslage wahrgenommen?
3. Mobile Incident Response Team z. B. Hilfe bei Vorfällen in Unternehmen
4. Warnungen
5. Sicherheitsuntersuchung und Scans
6. Sicherheitsprüfung bei KRITIS z. B. Prüfung der kritischen Infrastrukturen mit Kriterienkatalog
7. Nationale Zertifizierungsstelle z. B. Zertifizierung für Unternehmen im Rüstungsbereich

### Produkte und Dienstleistungen des BSI

* **Für Verbraucher:**
* "BSI für Bürger" als Informationsmöglichkeit für nicht-it-affine Bürger
* "BürgerCert" ist Ansprechpartner bei Hacking-Angriffen
* **Für Staat:**
* Digitaler Personalausweis
* Grenzübergreifende Identifizierung sg. _smart borders_.
* Vorgaben für Staat
* Zertifizierung von IT für die Verwendung vom Staat
* Meldeportal MIRT
* **Für Wirtschaft:**
* Verbundnetzwerk "Allianz für Cyber-Sicherheit"
* Sicherheitsempfehlungen z. B. für MS Office
* Lagezentrumsreport

### Praxisbeispiele

* Prävention, Detektion und Reaktion von Sicherheitsrisiken.
* **Prävention** von IT-Sicherheitsstörfällen. BSI hackt sich nicht in Systeme. Es ist auf Informationen von Unternehmen angewiesen. Für Unternehmen ist es die Möglichkeit neutral über eine Sicherheitslücke in Systemen zu informieren. Meldemöglichkeit wird aber schlecht angenommen. In Lagezentrum werden dann Meldungen analysiert und daraus Lagebild erstellt. Mit Nachweisprüfung wird gezeigt, dass bestimmte Angriffe sich in Unternehmen nicht auswirken. Sichert nicht gegen gezielte Angriffe gegen bestimmte Unternehmen ab.
* **Detektion** Untersuchung von IT-Produkten, die besonders häufig verbreitet sind. Detektion von Sicherheitsrisiken über zentrale Meldestelle. Durchführung von Portscans, um ungeschützte öffentlich erreichbare IT-Systeme zu erkennen. Betroffene müssen unverzüglich benachrichtigt werden. Mit sg. **Honeypots** (zwecks Anlocken von Angriffen) sollen Angriffsmethoden verstanden werden und Schadensprogramme erkannt und analysiert werden.
* Detektion von Auskunftsverlangen zur Ergänzung der Untersuchung von auf dem Markt bereitgestellte IT-Produkten (§ 7a BSIG) Detektion von Sicherheitsrisiken
* **Reaktion:** Umfasst Warnung z. B. für Produktwarnungen und MIRT-Unterstützung z. B. bei gehackten Unternehmen durch Squad Team. Konsequenzen für Produktwarnungen sind sehr weitreichend.

## Ausblick🖼️

Entwicklungen der BSI-Gesetzgebung durch EU-Recht (nur informationshalber)

![Entwicklung der BSI-Gesetzgebung durch EU-Recht (Glade; 2022)](../../.gitbook/assets/entwicklungen\_bsi.jpg)

### Verbesserung von IT-Sicherheitsrecht in der Zukunft

* **Was erhöht die IT-Sicherheit?**
  * Aufklärung
  * Freiwillige Zertifizierung
  * Zwingende Sicherheits- oder Produktvorgaben (z. B. bei Herstellern)
  * Kontrolle oder Sanktionen
* **Verantwortung?**
  * Hersteller
  * Verkäufer
  * Anwender (gewisse Verantwortung muss bei Verbraucher verbleiben)
* **Durchsetzbarkeit?**
  * Nationale Regulation und Marktortprinzip bei internationalem IT-Markt? (Schwierige Durchsetzbarkeit z. B. Prüfungen bei Huawei)
  * Behördliche Aufsicht oder Erleichterung privater Rechtsdurchsetzung?

### Verbraucherschutz durch BSI

* Einfaches Siegel für Produkte. QR Code auf Produkt kann gescannt werden, um abzufragen, ob derzeit Schwachstellen bestehen.
* Ziel der Verbrauchersensibilisierung ist:
  * Risikobewusstsein erhöhen
  * Beurteilungsfähigkeit stärken
  * Lösungskompetenz steigern
  * **Fazit:** Es wird kooperativ gelöst. Es wird nicht IT-Sicherheit bei Verbrauchern erzwungen. Bürger soll lediglich sensibilisiert werden.

## KRITIS+ und Unternehmen im besonderen öffentlichen Interesse

* **Neuer KRITIS-Sektor "Entsorgung"**
  * Entsorgung von Siedlungsabfällen (vgl. Beispiel Neapel)
* **Neue Unternehmen im besonderen öffentlichen Interesse (UBIs)**
  * KRITIS-ähnliche Pflichten (abgestuft, weniger strikt), aber keine KRITIS Unternehmen.
  * Beispiel: Rüstungsunternehmen, deren Infrastruktur nicht übernommen werden sollte; Chemieunternehmen wegen Gefahr oder andern Großunternehmen wegen wirtschaftlicher Abhängigkeit
  * Aufweichung des Versorgungsgrad-Ansatz → Fortsetzung in NIS-2

## Wichtige Themen

* Was sind wichtige Grundsätze?
* Wie arbeitet das BSI?

## Referenzen

Glade, Moritz. 2022. „Das IT-Sicherheitsgesetz in der Praxis: Das BSI als zentrale Bundesbehörde für IT-Sicherheit nach dem IT-Sicherheitsgesetz 2.0“.
