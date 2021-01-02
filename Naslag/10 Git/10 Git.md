# Git

- [cheatsheet](https://education.github.com/git-cheat-sheet-education.pdf)

Git is een systeem om de broncode van softwareprojecten te beheren. Er zijn twee belangrijke redenen om zo'n speciaal systeem te gebruiken:

- Tijdens de ontwikkeling van een applicatie maak je steeds wijzigingen, soms gooi je zelfs grote delen weg of schrijf je weer een heel stuk. Je wil misschien wat dingen helemaal omgooien, maar niet alles kwijtraken als het mislukt. Een beheerssysteem kan steeds weer versies opslaan die je makkelijk kunt terughalen.

- Bijna alle software wordt in samenwerking met anderen geschreven. Dat betekent niet dat iedereen samen achter één computer zit, maar wel dat er veel afgestemd moet worden en ook dat mensen van verschillende computers kunnen bijdragen aan het geheel.

Git faciliteert deze behoeftes door elke ontwikkelaar de mogelijkheid te geven versies van bestanden te markeren (of versies van complete *sets* bestanden) en deze versies met andere ontwikkelaars te delen. In de meeste gevallen is er sprake van één centrale *repository* (opslagplaats) waar iedereen versies heen kan *pushen*.

Stel, je hebt op je eigen computer een kopie van de repository staan, en je opent de bestanden in je IDE (ontwikkelomgeving). Dan doe je wat wijzigingen en je sla de bestanden op. Je kunt dan alle wijzingen *committen* (vastleggen) in een nieuwe versie van het systeem:

    git commit -a -m "nieuwe feature: ..."

Deze nieuwe versie bestaat op dat moment alléén op je eigen computer. Als je samenwerkt met anderen en de taken zijn niet helemaal goed verdeeld (tip!), is er namelijk een grote kans dat er twee mensen nieuwe versies hebben gemaakt van dezelfde bestanden. Er moet dan een moment zijn om te belissen welke versie het moet worden, of erger: welke wijzigingen van de beide nieuwe versies moeten worden overgenomen en ge*merged* (samengevoegd) in een definitief nieuwe versie.

Het moment van waarheid is dus als je probeert je eigen nieuwe versie te *pushen* naar de centrale repository:

    git push origin master

Als er geen conflicten zijn met andere nieuwe versies, dan gaat dit gewoon meteen goed. Mocht iemand anders nét eerder een nieuwe versie hebben gepusht, dan krijg je meteen een foutmelding. Sad! Daarover later meer.

In deze cursus gebruiken we allemaal GitHub: dat is een dienst die centrale repositories aanbiedt. Voor publieke software is dat gratis. Studenten kunnen ook gratis ruimte krijgen voor source code die niet zomaar publiek gemaakt kan worden.

## Oefenen met Git

Om nu even te oefenen met de workflow van Git, doe je een korte cursus op [Code School](https://www.codeschool.com/courses/try-git). Ook is er een handige korte referentie: [Simple Guide to Git](http://rogerdudler.github.io/git-guide/).
