# Oplevering

Bij deze laatste milestone lever je de code van het project in. De code is een artifact bij de eindpresentatie. Het idee is dat anderen (lees: de staff) de resultaten uit de presentatie kan reproduceren. Dat betekent dat de code vooral begrijpbaar moet zijn en er instructies moeten zijn om de verschillende resultaten te reproduceren.

## Minimumeisen

* Er is een README.md aanwezig.
* Eventuele afhankelijkheden (dependencies) staan in een `requirements.txt` of soortgelijks.
* Alle code om de resultaten uit de presentatie te produceren is aanwezig.

### README

Voor de README kijken we o.a. naar:

* De case waar de studenten mee bezig geweest zijn is duidelijk geïntroduceerd in de README.
* De aanpak van de verschillende algoritmen is duidelijk beschreven in de README.
* Het is na lezen van de README duidelijk hoe de resultaten te reproduceren zijn, via een interface (command line), argumenten die meegegeven kunnen worden voor de verschillende functionaliteiten/algoritmen, of bijvoorbeeld een duidelijke uitleg welke file te runnen om welk resultaat te krijgen.

### Repository

Voor de repository kijken we o.a. naar:

* Zitten er geen overbodige bestanden in de repository (pycache, .DS_Store, algoritmeA, algoritmeA2, algoritmeA2Final, etc.)
* Heeft de repository heeft een duidelijke en overzichtelijke indeling die ervoor zorgt dat bestanden makkelijk te vinden zijn.

### Code

Voor de kwaliteit van de code kijken we o.a. naar:

* Stijl van de code is consistent.
* De code is modulair geschreven, met korte functies, duidelijk ordening van files, en geen duplicate code.
* Abstractie is aangebracht waar nodig; alleen relevante data over een object is beschikbaar om complexiteit laag te houden en onderhoud aan code simpel te maken.
* Code bevat alleen magic numbers, `* imports`, `while True`, of `try-excepts` waar uiterst noodzakelijk
* Code heeft duidelijke control flow; e.g. geen ellenlange if-statements midden in al grote functies.
* De code is duidelijk in functionaliteit; docstrings, comments en variabelenamen zijn nuttig/beschrijven wat functies doen.
* De code is intuitief en direct te gebruiken voor soortgelijke projecten.


# Beoordeling

De code wordt beoordeeld op een schaal van 1 t/m 5, en vormt samen met de beoordeling van de eindpresentatie een cijfer. Beide onderdelen wegen even zwaar mee.

5. Uitermate goed gestructureerde code en repository, met uitgebreide uitleg over implementatiedetails en de structuur van de code
4. Code is systematisch gestructureerd en documentatie wijst goed de weg in de code voor iemand die deze nog niet eerder heeft gelezen
3. Code is overwegend goed gestructureerd en de onderdelen worden afzonderlijk goed uitgelegd met commentaar en verdere documentatie
2. Code is globaal geordend in mapjes en files, en de code is grotendeels gedocumenteerd met commentaar op lokaal niveau
1. Code staat op GitHub, maar er is geen coherente documentatie of herkenbare structurering van de code
{: start="5" reversed="reversed"}

