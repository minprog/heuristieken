# Experiment

De uitdaging bij dit vak is om de case zo goed mogelijk op te lossen. Natuurlijk gaat het daarbij ook om de manier om deze oplossing te vinden. Hiervoor heb je verschillende algoritmes geschreven en nu is het taak om te experimenteren.

## Wat ga je doen?

De verschillende algoritmes draaien op de verschillende instanties van de case. Om vervolgens de resultaten van de algoritmes met elkaar te vergelijken.

Bij het vergelijken van de resultaten zijn vooral de distributie van de behaalde scores en de beste score van belang. Het doel is namelijk om een zo goed mogelijke oplossing te vinden en dat is natuurlijk de oplossing met de beste score. Dat betekent ook dat alle mindere scores niet zozeer van belang zijn. De distributie van de scores is wel interessant. Op basis van deze distributie kunnen er onder andere claims gemaakt worden over hoe waarschijnlijk het is dat er een bepaalde score wordt gevonden na een x-aantal runs van het algoritme. Sla dus wel degelijk alle behaalde resultaten en scores op en visualiseer deze ook. Het is handig om je resultaten op te slaan in een csv formaat, zodat je de visualisaties en grafieken los van de experimenten kunt runnen.

## Parameters tunen

Grote kans dat je algoritmes een aantal parameters kennen. Dit roept direct een vraag op: welke waardes kies je voor deze parameters? Gebruik hiervoor de grid search methode als volgt:

1. Kies voor iedere parameter een discreet domein van waardes, bijvoorbeeld [0, 1, 2, 3]. Wat dat domein echt is hangt natuurlijk af van de parameters zelf.
2. Maak alle mogelijke combinaties van waardes voor deze paremeters. Kent het algoritme twee parameters met de domeinen [0, 1] en [5, 7, 9], dan zijn er zes mogelijke combinaties.
3. Draai het algoritme meerdere keren binnen een vaste hoeveelheid tijd voor iedere combinatie.
4. Kies uiteindelijk voor de combinatie die de beste score oplevert.

Wees hier praktisch en kijk voor het tunen goed op de klok. Bereken hoeveel tijd je wilt besteden, en verdeel deze tijd over de combinaties. Hierbij heb je natuurlijk de afweging hoeveel combinaties je wilt proberen en hoeveel tijd je iedere combinatie kunt gunnen.

Je kan ervoor kiezen om parameters per instantie van de case te tunen. Het zou kunnen dat verschillende parameters beter werken op verschillende instanties. Dat is ook zeker interessant om te noemen bij de eindpresentaties.

## Resultaten verzamelen

Hoe je dit doet verschilt per case, maar wel een algemeen advies:

- Schrijf een script dat een algoritme voor een gezette tijd kan draaien.
- Schrijf na iedere run van het algoritme de resultaten weg naar een bestand. Zo raak je niet per ongeluk uren rekentijd kwijt. Hier spreken we uit ervaring!
- Ga praktisch met tijd om en kap een algoritme af na een gezette hoeveelheid tijd. Bij verschillende algoritmes kunnen verschillende runs buitensporig lang duren, probeer dat voor te zijn.
- Print een soort statusbericht. Als er niks op het scherm komt wantrouw je als mens al snel of er nou wel echt iets gebeurt. Print daarom bijvoorbeeld uit welke run nu gaande is. Print tegelijkertijd niet te veel, iets uitprinten is namelijk een dure operatie en kan onbedoeld het programma flink vertragen.

Hieronder een opzet voor een script dat het programma `random_algorithm.py` draait door middel van de aanroep `python3 random_algorithm.py`. Iedere run duurt maximaal 60 seconden en na 3600 seconden stopt het geheel.

    import subprocess
    import time

    start = time.time()
    n_runs = 0

    while time.time() - start < 3600:
        print(f"run: {n_runs}")
        subprocess.call(["timeout", "60", "python3", "random_algorithm.py"])
        n_runs += 1

Ter naslag, dit is het [timeout](https://linuxize.com/post/timeout-command-in-linux/) programma en dit is Python's [subprocess module](https://docs.python.org/3/library/subprocess.html).

> Belangrijk, hou de tijd voor ieder algoritme dat je gaat vergelijken constant. Daarin moet er een afweging worden gemaakt, met meer tijd per algoritme kunnen er wellicht betere resultaten worden behaald, maar blijft er ook minder tijd over om andere experimenten te draaien. Kijk dus goed naar hoeveel experimenten je wilt draaien en hoeveel tijd er beschikbaar is.

### Parallel?

Het is het overwegen waard om verschillende scripts in parallel te draaien. Al zouden deze scripts wel effect kunnen hebben op elkaar. Er is namelijk maar zoveel geheugen en je processor kent maar zoveel rekenkernen. Hierbij adviseren we dan om een script te draaien voor iedere fysieke rekenkern op je processor. Dat laatste moet je zelf opzoeken.

De simpelste manier om het geschreven script in parallel te draaien is om een X aantal terminals te openen en het script daarbinnen aan te roepen. Dat maakt ook het monitoren van de output begrijpbaar. Let hierbij wel op dat de verschillende scripts elkaars output niet overschrijven!

Eventueel zou je ook gebruik kunnen maken van Python's [multiprocessing module](https://docs.python.org/3/library/multiprocessing.html#module-multiprocessing). Dit is wel buiten de scope van dit vak en daarom alleen aan te raden bij eerdere ervaring met parallel programmeren.

## Context

### Tijd

Voor de problemen in deze cases zijn we op zoek naar een zo goed mogelijke oplossing. Als een algoritme die oplossing kan vinden voor het einde van het vak, maakt de tijd eigenlijk niet uit.

Als voorbeeld, denk hierbij aan het maken van lesroosters voor de UvA. Ieder semester wordt er een rooster ontwikkeld. Bij het ontwikkelen van dit rooster is het alleen belangrijk dat er een goed rooster wordt afgeleverd voor het volgende semester. Of het algoritme daar secondes over doet, of maanden, dat maakt dan niet zo gek veel uit. Zolang de oplossing er maar is binnen een half jaar.

Ook bij programmeertheorieprojecten is de tijd eindig. Binnenkort sta je te presenteren en dat betekent dat je tot dan je computer kan laten rekenen. Dat betekent wel dat je de algoritmes nog flink wat rekentijd kan gunnen. Maak daar dan ook goed gebruik van en zet gerust je computer een nacht aan het werk.

We rekenen algoritmes voor dit soort cases dan ook niet zozeer af op de run-time, de hoeveelheid tijd die het algoritme gebruikt voor één run. Maar op de mogelijkheid om een goede oplossing te vinden binnen een gezette tijd. Een algoritme is in deze context beter als het een betere oplossing kan vinden binnen dezelfde tijd als een ander algoritme.

Hou bij het vergelijken van algoritmes daarom de tijd constant. Het liefst hou je hier ook de computer constant, zodat het hebben van bijvoorbeeld een snellere processor geen invloed heeft. In praktijk is dit vaak lastig, omdat je veel experimenten gaat draaien. Kies je dan om verschillende computers te gebruiken, benoem dan altijd op welke hardware het algoritme heeft gedraaid.

### Iteraties

Naast tijd bestaat er de mogelijkheid om verschillende iteraties in een algoritme te meten. Het aantal bezochte states met een zoekalgoritme, het aantal pogingen tot aanpassingen met een hillclimber etc. Dit kan helpen bij het verklaren waarom een algoritme een ander algoritme verslaat. Zo kan een simpel algoritme wellicht meer iteraties maken in dezelfde tijd als een ingewikkelder algoritme.

Let hier wel bij op dat het aantal gemaakte iteraties ook afhangt van de implementatie van het algoritme. Kijk hier goed naar de theoretische complexiteit van verschillende operaties in het algoritme. Ook zou je hier een profiler kunnen gebruiken om eventuele bottlenecks in de implementatie op te sporen.

### Wat is een goede oplossing?

De kans is groot dat je niet zeker weet of je de beste oplossing hebt gevonden. Toch zijn er manieren om te laten zien dat de oplossing die je hebt gevonden goed is.

#### Vergelijken met de baseline

Met het baseline algoritme kan je vergelijkingsmateriaal produceren. Hoe ziet een willekeurige oplossing eruit en hoe zijn de scores van willekeurige oplossingen verdeeld?

In een ideaal geval genereert het algoritme voor de baseline een willekeurige oplossing, een willekeurige state uit de state space. Dat maakt het mogelijk om steekproeven te nemen uit de state space, en vervolgens claims te maken over de state space.

Let wel, de kans is groot dat het algoritme niet compleet willekeurig een state uit de state space kiest. Er kan een bias in het algoritme zitten, een voorkeur voor het vinden van bepaalde oplossingen. Het is belangrijk om deze bias te vinden en te noemen. Zo maak je niet per ongeluk onterechte claims over de state space.

#### Vergelijken met een theoretisch optimum

Voor sommige cases kan je de best mogelijke score beredeneren. Of die oplossing met die score ook haalbaar is, dat is de vraag. Wel geeft dit je een ander punt om mee te vergelijken, namelijk hoe ver zitten de gevonden oplossingen van de beste score af.

Bij het berederen van dit theoretisch optimum is het belangrijk dat er nooit wordt onderschat als het gaat om het vinden van een maximum score, of overschat als de case draait om het vinden van een minimum score. Het moet onmogelijk zijn om een betere score te kunnen vinden.

#### Analyseer de structuur van de gevonden oplossingen zelf

Waar komt de score precies vandaan en waar ligt nog ruimte voor verbetering? Zijn er patronen in de oplossing te herkennen die potentieel leiden tot een goede score? Zijn verschillende onderdelen van de oplossing optimaal?

Dit alles is natuurlijk sterk afhankelijk van de case. Wel biedt het een uitgelegen kans om jullie opgebouwde kennis over het probleem te laten zien.

## Submit

Lever hieronder opnieuw de url naar de GitHub repo. Daarin moeten de scripts staan om de resultaten te verzamelen. Zet ook in de README.md alvast concrete instructies om deze scripts te draaien en hoe daarmee de verschillende experimenten kunnen worden gereproduceerd.

Eventueel mogen de resultaten ook in de repo staan, maar in sommige gevallen is dat niet goed mogelijk.

**Maar één persoon uit je team hoeft dit formulier in te leveren.**
