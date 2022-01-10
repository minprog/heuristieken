# Case: Lectures & Lesroosters

![Hup naar binnen.](Roostering2.jpg)

## Inleiding

Lesroosters, of roosters in het algemeen, zijn buitengewoon lastig goed in te richten. Dienstregelingen voor treinen, vliegtuigen, multicore-processors en assembly lines hebben in dat opzicht een boel met elkaar gemeen. Zalenroostering op een universiteit is geen uitzondering. In deze case moet een weekrooster gemaakt worden voor een vakkenlijst op Science Park.

- Vakken bestaan uit vakactiviteiten: hoorcolleges en/of werkcolleges en/of practica.
- Alle zalen zijn voor alledrie collegetypes geschikt.
- Voor ieder vak is in de waarde E(studenten) aangegeven hoeveel inschrijvingen er verwacht worden.
- Bij hoorcolleges moeten alle ingeschreven studenten ineens bedeeld worden.
- Een college duurt van 9:00-11:00, 11:00-13:00, 13:00-15:00 of 15:00-17:00 op een werkdag. Eén zo'n periode van twee uur wordt een tijdsslot genoemd
- Een geldig weekrooster is een weekrooster waarvoor aan alle roosterbare activiteiten van ieder vak een tijdsslot met een zaal hebben. We noemen het paar tijdsslot-zaal een zaalslot.
- Een zaalslot kan enkel gebruikt worden voor één activiteit.

## Opdracht

1. Rooster alle vakken uit de onderstaande tabel in. Je mag de verwachte studentenaantallen nog even vergeten.

2. Hou nu wel rekening met de studentenaantallen. Voor iedere student die niet meer in de zaal past krijg je een maluspunt. Hoe minder maluspunten, hoe beter. De grootste zaal heeft ook een avondslot van 17:00-19:00, maar gebruik van het avondslot kost vijf maluspunten.

3. Werkcolleges en practica mogen in meerdere groepen gegeven worden. In tegenstelling tot een hoorcollege hoeven daarbij niet alle ingeschreven studenten ineens bedeeld te worden. Maak hiervan gebruik om het rooster te verbeteren.

4. Roostering wil bekijken of roosters rekening kunnen houden met [individuele vakinschrijvingen](studentenenvakken.csv). Ieder vakconflict van een student levert één maluspunt op.

Studenten zien het liefst aaneengesloten activiteiten en zo min mogelijk "tussensloten". Dat zijn tijdsloten zonder ingeroosterde activiteiten voor de student, maar waarvoor en waarna wel een activiteit plaatsvindt. Naast de wens van de student is dit ook belangrijk voor het onderwijs, zo zal het verzuim bij de verschillende activiteiten lager zijn als activiteiten aaneengesloten worden geroosterd. Ook is dit belangrijk voor de drukte op de faculteit, want bij zulke tussensloten nemen studenten plaats op (zelf)studieplekken en studieplekken zijn er er maar beperkt. Daarom wil roostering kijken of tussenuren geminimaliseerd kunnen worden.

{:start="5"}

5. Een tussenslot voor een student op een dag levert één maluspunt op. Twee tussensloten op één dag voor een student levert drie maluspunten op. De kans op verzuim bij meerdere tussensloten is namelijk aanzienlijk groter dan bij één tussenslot.

## Zalen, Vakken en Inschrijvingen

| Zaalnummber | Max. capaciteit |
| ----------- | --------------- |
| A1.04       | 41              |
| A1.06       | 22              |
| A1.08       | 20              |
| A1.10       | 56              |
| B0.201      | 48              |
| C0.110      | 117             |
| C1.112      | 60              |

| Vakken voor periode 4               | #Hoorcolleges | #Werkcolleges | Max. stud. | #Practica | Max. stud. | E(studenten) |
| ----------------------------------- | ------------- | ------------- | ---------- | --------- | ---------- | ------------ |
| Advanced Heuristics                 | 1             | 0             | nvt        | 1         | 10         | 22           |
| Algoritmen en complexiteit          | 1             | 1             | 25         | 1         | 25         | 47           |
| Analysemethoden en -technieken      | 1             | 0             | nvt        | 0         | nvt        | 60           |
| Architectuur en computerorganisatie | 2             | 0             | nvt        | 0         | nvt        | 19           |
| Autonomous Agents 2                 | 2             | 1             | 10         | 1         | 10         | 19           |
| Bioinformatica                      | 3             | 1             | 20         | 1         | 20         | 40           |
| Calculus 2                          | 1             | 1             | 40         | 0         | nvt        | 90           |
| Collectieve Intelligentie           | 3             | 1             | 20         | 1         | 20         | 65           |
| Compilerbouw                        | 2             | 1             | 40         | 1         | 40         | 70           |
| Compilerbouw (practicum)            | 0             | 0             | nvt        | 1         | 15         | 35           |
| Data Mining                         | 2             | 1             | 10         | 1         | 10         | 30           |
| Databases 2                         | 1             | 1             | 40         | 0         | nvt        | 69           |
| Heuristieken 1                      | 1             | 1             | 25         | 0         | nvt        | 44           |
| Heuristieken 2                      | 1             | 1             | 20         | 0         | nvt        | 30           |
| Informatie- en organisatieontwerp   | 2             | 1             | 15         | 1         | 15         | 40           |
| Interactie-ontwerp                  | 2             | 0             | nvt        | 0         | nvt        | 31           |
| Kansrekenen 2                       | 2             | 0             | nvt        | 0         | nvt        | 70           |
| Lineaire Algebra                    | 2             | 0             | nvt        | 0         | nvt        | 50           |
| Machine Learning                    | 2             | 0             | nvt        | 0         | nvt        | 25           |
| Moderne Databases                   | 1             | 1             | 20         | 1         | 20         | 60           |
| Netwerken en systeembeveiliging     | 0             | 0             | nvt        | 1         | 20         | 50           |
| Programmeren in Java 2              | 0             | 0             | nvt        | 1         | 20         | 95           |
| Project Genetic Algorithms          | 0             | 0             | nvt        | 1         | 15         | 40           |
| Project Numerical Recipes           | 0             | 0             | nvt        | 1         | 15         | 40           |
| Reflectie op de digitale cultuur    | 2             | 1             | 20         | 0         | nvt        | 53           |
| Software engineering                | 1             | 1             | 40         | 1         | 40         | 75           |
| Technology for games                | 2             | 1             | 20         | 0         | nvt        | 50           |
| Webprogrammeren en databases        | 2             | 1             | 20         | 1         | 20         | 46           |
| Zoeken, sturen en bewegen           | 0             | 0             | nvt        | 1         | 15         | 45           |

## Misc

Deze case is op verzoek van Justin Oud, Wouter Bohlken en Remco Mokveld (Heuristieken 2015a) tot eerste versie uitgewerkt. Overige betrokkenen in het proces zijn Marcella van Wijngaarden en Reinout Verbeek.

## Output

Voor deze case is er nog geen gespecificeerd format voor de output. Het is aan de eerste teams om een voorstel te doen. Als staff stellen wij het volgende voor:
