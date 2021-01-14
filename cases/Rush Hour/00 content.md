# Case: Rush Hour
![een strak uitgesneden foto van de voorkant van een doos van het spel Rush hour, waarop een aantal cartoonfiguren in geparkeerde auto's heel boos en verrast kijkt naar een chauffeur in een rode auto die langsscheurt, met rechtsonder in beeld nog een lichte weerspiegeling van de flitser of ander licht](Rushhour.jpg){:.inline}

Rush Hour is een ogenschijnlijk eenvoudig puzzeltje met een verrassend uitdagend karakter. 
In een veld van 6 hoog en 6 breed staat een rode auto, de jouwe, en die moet naar de uitgang. die recht voor je ligt. 
Maar andere voertuigen versperren de weg; auto's van twee eenheden lang en trucks van drie eenheden lang, die alleen in hun rijrichting bewogen mogen worden. 
Ze mogen niet draaien. De opdracht is simpel: beweeg je auto naar buiten, of beter: schrijf een computerprogramma om dat voor je te doen.


## Opdracht
1. Los [games 1, 2 en 3](gameboards.zip) op. Doe hoe je dat goed lijkt. 
Het is natuurlijk goed om daar een programma voor te schrijven, maar als je een ander idee hebt, of het met de hand kunt, mag dat ook.
Let er op dat de _row_ en _column_ waarden beginnen vanaf 1 en niet vanaf 0!

Game #1  
![](Rushhour6x6_1.jpg)

Game #2  
![](Rushhour6x6_2.jpg)

Game #3  
![](Rushhour6x6_3.jpg)

{:start="2"}
2. Verzin een implementatie voor het bord, en schrijf een algoritme dat series van zetten uitvoert. 
Laat het algoritme [games 4, 5 en 6](gameboards.zip) oplossen. Kortere series zijn betere series.

Game #4  
![](Rushhour9x9_1.jpg)

Game #5  
![](Rushhour9x9_2.jpg)

Game #6  
![](Rushhour9x9_3.jpg)

{:start="3"}
3. Los [game 7](gameboards.zip) op. Pas je algoritme aan indien dat nodig is.

Game #7  
![](Rushhour12x12_1.jpg)


## Advanced

{:start="4"}
4. Maak random Rush Hour borden en probeer ze op te lossen met je algoritmes.
5. Probeer te achterhalen wat het verschil is tussen een moeilijke rushhour-opgave en een even grote makkelijk rushhour opgave.
Ook aantonen waar de moeilijkheid **niet** aan ligt is waardevol.


## Output
Om resultaten te kunnen verifiëren is het handig om in een uniform format je output te genereren.
Bekijk [het voorbeeld](example_output.csv) en zorg ervoor dat jouw programma een oplossing in hetzelfde format kan omzetten.
De enige vereiste aan de output is de header-regel (regel 1), die identiek moet zijn.
Het getal naast het voertuig geeft afhankelijk van de orientatie van het voertuig het aantal kolommen of rijen aan dat deze opschuift.

N.B. Je programma hoeft hier verder niets mee te doen. Het programma hoeft dit enkel als laatste stap in het process te kunnen doen.


## Check50
Je kan je programma's testen door de output mee te geven aan de check50. Dit doe je als volgt:

1. Genereer een antwoord en sla deze met het bovenstaande formaat op in een nieuw bestand met de naam `output.csv`
2. Open een terminal in de folder waar je `output.csv` hebt opgeslagen
3. Run het commando van het betreffende probleem:
    1. Voor de 6x6 borden: 
        1. `check50 minprog/theorie-check50/2021/rush_hour/board1`
        2. `check50 minprog/theorie-check50/2021/rush_hour/board2`
        3. `check50 minprog/theorie-check50/2021/rush_hour/board3`
    2. Voor de 9x9 borden: 
        1. `check50 minprog/theorie-check50/2021/rush_hour/board4`
        2. `check50 minprog/theorie-check50/2021/rush_hour/board5`
        3. `check50 minprog/theorie-check50/2021/rush_hour/board6`
    3. Voor het 12x12 bord: 
        1. `check50 minprog/theorie-check50/2021/rush_hour/board7`
