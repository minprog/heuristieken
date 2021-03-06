![Hup naar binnen.](Roostering2.jpg)


## Inleiding

Lesroosters, of roosters in het algemeen, zijn buitengewoon lastig goed in te richten. Dienstregelingen voor treinen, vliegtuigen, multicore-processors en assembly lines hebben in dat opzicht een boel met elkaar gemeen. Zalenroostering op een universiteit is geen uitzondering. In deze case  moet een weekrooster gemaakt worden voor een vakkenlijst op Science Park.

* Vakken bestaan uit vakactiviteiten: hoorcolleges en/of werkcolleges en/of practica.
* Alle zalen zijn voor alledrie collegetypes geschikt.
* Voor ieder vak is in de waarde E(studenten) aangegeven hoeveel inschrijvingen er verwacht worden.
* Bij hoorcolleges moeten alle ingeschreven studenten ineens bedeeld worden. 
* Hoorcolleges moeten éérder in de week ingeroosterd worden dan andere activiteiten.
* Bij werkgroepen en practica moeten de studenten, afhankelijk van de capaciteit, worden opgedeeld in zo weinig mogelijk groepen (zie kolommen "max. stud." in de vakkentabel).
* Een college duurt van 9:00-11:00, 11:00-13:00, 13:00-15:00 of 15:00-17:00 op een werkdag. Eén zo'n periode van twee uur wordt een tijdsslot genoemd
* Een geldig weekrooster is een weekrooster waarvoor aan alle roosterbare activiteiten van ieder vak een tijdsslot met een zaal hebben. We noemen het paar tijdsslot-zaal een zaalslot.
* Sommige vakken moeten tegelijkertijd volgbaar zijn; de verschillende opleidingsdirecteuren hebben dat aangegeven met een 'x' in een [matrix](tegelijkvolgbaar.csv).

## Opdracht

1. Rooster alle vakken uit de onderstaande tabel in. Hou rekening met de vereiste volgorde van de colleges, en met de matrix. Je mag de verwachte studentenaantallen nog even vergeten.


2. Hou nu wel rekening met de studentenaantallen. Voor iedere student die niet meer in de zaal past krijg je een maluspunt. Hoe minder maluspunten, hoe beter. De grootste zaal heeft ook een avondslot van 17:00-19:00, maar gebruik van het avondslot kost 20 maluspunten.


Studenten leren het meest als de activiteiten zoveel mogelijk verdeeld zijn over de week. Een vak van twee tot vier activiteiten die maximaal verdeeld zijn over de week levert 20 bonuspunten op. Voor twee activiteiten is dat ma-do of di-vr, voor drie activiteiten is dat ma-wo-vr en voor vier activiteiten is dat ma,di,do,vr. 

{:start="3"}
3. Voor ieder vak van x activiteitsoorten geldt dat ze 10 maluspunten opleveren als er activiteiten op x-1 dagen geroosterd zijn, 20 voor x-2 en 30 voor x-3. Zorg voor een zo goed mogelijk rooster met dit nieuwe criterium.


4. Roostering wil bekijken of roosters rekening kunnen houden met [individuele vakinschrijvingen](studentenenvakken.csv). Iedere student die geen vakconflicten heeft levert een bonuspunt op, ieder vakconflict van een student een maluspunt.

## Zalen, Vakken en Inschrijvingen



| Zaalnummber | Max. capaciteit |
| ---------- | --------------- |
| A1.04 | 41 |
| A1.06 | 22 |
| A1.08 | 20 |
| A1.10 | 56 |
| B0.201 | 48 |
| C0.110 | 117 |
| C1.112 | 60 |

|Vakken voor periode 4 | #Hoorcolleges | #Werkcolleges | Max. stud. | #Practica | Max. stud. | E(studenten) |
| --- | --- | --- | --- | --- | --- | --- |
| Advanced Heuristics | 1 | 0 | nvt| 1 | 10 | 22 |
| Algoritmen en complexiteit | 1 | 1 | 25 | 1 | 25 | 47 |
| Analysemethoden en -technieken | 1 | 0 | nvt | 0 | nvt | 60 |
| Architectuur en computerorganisatie | 2 | 0 | nvt | 0 | nvt | 19|
| Autonomous Agents 2 | 2 | 1 | 10 | 1 | 10 | 19 |
| Bioinformatica | 3| 1 | 20 | 1 | 20 | 40 |
| Calculus 2| 1| 1| 40| 0| nvt| 90  |
| Collectieve Intelligentie| 3 | 1 | 20 | 1 | 20| 65 |
| Compilerbouw | 2 | 1| 40| 1| 40| 70 |
| Compilerbouw (practicum)| 0| 0| nvt| 1| 15| 35 |
| Data Mining | 2 | 1| 10| 1| 10| 30 |
| Databases 2| 1| 1| 40| 0| nvt| 69 |
| Heuristieken 1| 1| 1| 25| 0| nvt| 44 |
| Heuristieken 2| 1| 1| 20| 0| nvt | 30 |
| Informatie- en organisatieontwerp | 2| 1| 15| 1| 15| 40 |
| Interactie-ontwerp | 2| 0| nvt| 0| nvt| 31 |
| Kansrekenen 2 | 2| 0| nvt| 0| nvt| 70 |
| Lineaire Algebra | 2| 0| nvt| 0| nvt| 50 |
| Machine Learning | 2| 0| nvt| 0| nvt| 25 |
| Moderne Databases| 1| 1| 20| 1| 20| 60 |
| Netwerken en systeembeveiliging| 0| 0| nvt| 1| 20| 50 |
| Programmeren in Java 2 | 0| 0| nvt| 1| 20| 95 |
| Project Genetic Algorithms | 0 | 0 | nvt | 1 | 15 | 40 |
| Project Numerical Recipes| 0| 0| nvt| 1| 15| 40 |
| Reflectie op de digitale cultuur | 2| 1| 20| 0| nvt| 53  |
| Software engineering | 1| 1| 40| 1| 40| 75 |
| Technology for games | 2| 1| 20| 0| nvt| 50 |
| Webprogrammeren en databases| 2| 1| 20| 1| 20| 46 |
| Zoeken, sturen en bewegen | 0| 0| nvt| 1| 15| 45 |

## Misc

Deze case op verzoek van Justin Oud, Wouter Bohlken en Remco Mokveld (Heuristieken 2015a) tot eerste versie uitgewerkt. Overige betrokkenen in het proces zijn Marcella van Wijngaarden en Reinout Verbeek.
