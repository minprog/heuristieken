# Git

[Heb je deze pagina al gelezen, maar wil je snel even kijken welke git-commando's er ook alweer allemaal waren? Gebruik dan de Git cheatsheet!](https://education.github.com/git-cheat-sheet-education.pdf)

Git is een systeem om de broncode van softwareprojecten te beheren. Er zijn twee belangrijke redenen om zo'n speciaal systeem te gebruiken:

* Tijdens de ontwikkeling van een applicatie maak je steeds wijzigingen. Soms gooi je zelfs grote delen weg of schrijf je weer een heel stuk opnieuw. Je wil misschien wat dingen helemaal omgooien, maar niet alles kwijtraken als het mislukt. Een versiebeheersysteem kan steeds versies opslaan die je makkelijk kunt terughalen.

* Bijna alle software wordt in samenwerking met anderen geschreven. Dat betekent niet dat iedereen samen achter één computer zit, maar wel dat er veel afgestemd moet worden en dat mensen vanaf verschillende computers kunnen bijdragen aan hetzelfde project.

Git faciliteert deze behoeftes door elke ontwikkelaar de mogelijkheid te geven versies van bestanden te markeren, of versies van complete *sets* bestanden, en deze versies met andere ontwikkelaars te delen. In de meeste gevallen is er sprake van één centrale opslagplaats (*repository*) waar iedereen versies heen kan versturen. In Git-termen heet dat *pushen*.

GitHub is een service die Git-repositories host op het internet. Deze service is gratis en kan gebruikt worden door jouw groep, zodat je één centrale plek hebt, die altijd beschikbaar is, waarop al jullie code staat.

## Git klaarzetten

Om Git te kunnen gebruiken op je computer, zijn er een aantal commando's op de command line die je moet leren gebruiken. We beginnen met het opzetten van één repository voor jullie hele groep. Deze koppelen we daarna aan ieder van de computers van de groepsleden.

> Git werkt niet hetzelfde als Dropbox! Het houdt je bestanden niet automatisch up-to-date. Dit is precies wat we willen, want we willen natuurlijk geen kapotte code of code die niet af is naar onze groepsleden sturen.

### GitHub-account aanmaken

Ieder groepslid begint door een account aan te maken op [GitHub](https://github.com/). Als je al een GitHub-account hebt, gebruik die dan.

### Git instellen op je computer

Git is al geïnstalleerd op de computers die je voor dit vak gebruikt. Voordat je Git gaat gebruiken, moet je nog wel een paar instellingen goed zetten.

Open een terminal en voer eerst de volgende commando's uit. Vervang de naam en het e-mailadres door je eigen gegevens:

    git config --global user.name "Voornaam Achternaam"
    git config --global user.email "jouw-email@example.com"

Deze gegevens worden gebruikt om bij te houden wie welke wijzigingen heeft gemaakt.

Daarna stellen we in dat Git een eenvoudige editor gebruikt. Dit voorkomt dat Git per ongeluk Vim opent, een editor die voor beginners vaak lastig te gebruiken is.

Voer daarom het volgende commando uit:

    git config --global core.editor "nano"

Nano is een eenvoudige editor die in de terminal opent. Als Git later een bericht wil laten aanpassen, bijvoorbeeld bij een merge commit, kun je in Nano opslaan met `Ctrl+O`, daarna op Enter drukken, en afsluiten met `Ctrl+X`.

Tot slot stellen we in hoe Git standaard moet omgaan met `git pull` wanneer jouw lokale versie en de online versie allebei nieuwe commits hebben. Voor deze cursus gebruiken we de simpele standaard waarbij Git probeert de versies samen te voegen met een merge:

    git config --global pull.rebase false

## SSH instellen

Voor de meeste acties die interactie vereisen met de GitHub-servers is het nodig om jezelf via de terminal te identificeren. GitHub staat sinds 13 augustus 2021 niet meer toe dat je dit doet met je gebruikersnaam en wachtwoord. Om dit toch mogelijk te maken is het nodig om een SSH-key aan te maken en deze bij GitHub te registreren.

> SSH (Secure Shell) is een protocol dat wordt gebruikt voor veilige communicatie over een netwerk.

Voer om een SSH-key aan te maken in een terminal het volgende commando uit. Vervang het e-mailadres door het e-mailadres dat je voor GitHub gebruikt:

    ssh-keygen -t ed25519 -C "jouw-email@example.com"

Wanneer je een prompt krijgt om de key ergens op te slaan, druk op Enter. Hiermee sla je de key op op de standaardlocatie.

Je wordt daarna gevraagd of je een wachtwoord wilt invullen voor het gebruik van je SSH-key. Druk ook hier gewoon op Enter. Je krijgt nu als het goed is een "randomart"-plaatje te zien. Dat kun je negeren.

Voer nu het volgende uit in een terminal:

    cat ~/.ssh/id_ed25519.pub

Dit laat je openbare sleutel op het scherm zien: een reeks tekens die begint met `ssh-ed25519`. Selecteer en kopieer deze hele regel. Let op dat je de prompt van je terminal, bijvoorbeeld `$`, niet mee kopieert.

Ga naar https://github.com/settings/keys en log in met je GitHub-gegevens.

Klik op **New SSH key** en plak je public SSH key in het tekstvak onder **Key**. Eventueel kun je ook een titel invoeren, zoals "Minor". Klik daarna op **Add SSH key**.

Test daarna in de terminal of de verbinding werkt:

    ssh -T git@github.com

Je wordt mogelijk gevraagd of je verbinding wilt maken met GitHub. Typ dan `yes` en druk op Enter.

Als het goed is zie je nu een bericht zoals:

    Hi <USERNAME>! You've successfully authenticated, but GitHub does not provide shell access.

Als dit niet werkt, bijvoorbeeld omdat poort 22 geblokkeerd is op het netwerk waar je op zit, probeer dan deze variant:

    ssh -T git@ssh.github.com -p 443

Je zou nu gebruik moeten kunnen maken van GitHub via SSH zonder iedere keer je gebruikersnaam en wachtwoord in te vullen.

## Repository aanmaken en downloaden

Nu Git en SSH goed ingesteld zijn, kunnen jullie de repository aanmaken en downloaden.

1. Na het inloggen start **één** van de groepsleden met het aanmaken van een nieuw **Team** via [GitHub Classroom](https://classroom.github.com/a/gh-jNDFO). Bedenk een leuke naam voor jullie groep, die je dan ook direct kunt gebruiken als naam voor jullie repository.

2. De overige leden volgen nu ook de link naar [GitHub Classroom](https://classroom.github.com/a/gh-jNDFO) en klikken op **Join** bij jullie eigen team. Zij krijgen dan ook toegang tot de repository.

3. Ieder groepslid opent nu een terminal en navigeert naar de folder waar diegene het project wil opslaan. Op de hoofdpagina van jullie repository staat een knop waar **Code** op staat. Als je hierop drukt, staan er onder het woord **Clone** drie tabjes. Druk op **SSH**. Nu komt er als het goed is een link tevoorschijn die lijkt op:

   git@github.com:<gebruikersnaam>/<teamnaam>.git

   Kopieer deze link en gebruik het volgende commando, waarbij je `<link>` vervangt door de link die je zojuist gekopieerd hebt:

   git clone <link>

Hiermee wordt de Git-repository naar je computer gedownload. De repository kan nu worden gebruikt alsof het een gewone folder op je computer is.

> **LET OP: Als je op enig moment niet zeker weet hoe je verder moet, terug wilt naar een eerdere versie van je code, of andere problemen hebt met Git, neem dan contact op met een van de ervaren TA's of docenten van dit vak. Het gebruik van commando's die je vindt op Stack Overflow of Google kan onherstelbare effecten hebben en resulteren in een hoop verloren werk.**

## Git gebruiken

Het gebruik van Git is nu vrij simpel. Iedere keer dat je iets wilt doen in de Git-repository, navigeer je in de terminal naar de folder van je project.

Er zijn 5 commando's die je moet kennen:

* **`git pull`**
  Dit commando haalt de huidige versie van de repository van GitHub. Dit zou daarom altijd het eerste commando moeten zijn dat je uitvoert als je begint met werken.

  Let op: als je lokaal al veranderingen hebt gemaakt, kan dit commando soms niet meteen uitgevoerd worden. Sla dan eerst je lokale veranderingen op met `git commit`.

* **`git status`**
  Dit commando laat zien welke bestanden en folders je hebt aangepast, welke commits je wel lokaal hebt gemaakt maar nog niet hebt gepusht, en welke bestanden nog niet door Git worden gevolgd.

  Gebruik dit commando vaak. Als je niet zeker weet hoe het ervoor staat, is `git status` meestal het eerste commando dat je moet proberen.

* **`git add <filepath>`**
  Dit commando gebruik je om nieuwe bestanden of folders toe te voegen aan Git.

  Bijvoorbeeld: als je lokaal een folder hebt aangemaakt die `coole_dingen` heet, met een bestand daarin dat `lees_data.py` heet, kun je dat bestand toevoegen met:

      git add coole_dingen/lees_data.py

  Het is ook mogelijk om `git add .` uit te voeren om alle nieuwe bestanden in de huidige folder en subfolders toe te voegen aan de repository.

  Als een bestand eenmaal door Git gevolgd wordt, hoef je het niet opnieuw als nieuw bestand toe te voegen. Latere wijzigingen aan dat bestand kunnen automatisch worden meegenomen met `git commit -am`. Nieuwe bestanden moet je wel eerst met `git add` toevoegen.

* **`git commit -am "<bericht>"`**
  Dit commando slaat alle veranderingen aan bestanden die Git al kent lokaal op met een bericht erbij.

  Bijvoorbeeld:

      git commit -am "Voeg grafiek toe aan analyse"

  Gebruik een bericht dat duidelijk uitlegt wat je gedaan hebt. Dat maakt het een stuk makkelijker om oude versies van specifieke stukken code terug te vinden.

  Let op: `git commit -am` neemt geen nieuwe bestanden mee. Als je een nieuw bestand of een nieuwe map hebt gemaakt, gebruik dan eerst `git add <bestand>` of `git add .`.

* **`git push`**
  Dit commando duwt alle commits die je lokaal gemaakt hebt naar de GitHub-server. Totdat je dit gedaan hebt, staat niets wat je lokaal hebt opgeslagen op GitHub.

  Als de repository tussentijds veranderd is, moet je eerst `git pull` uitvoeren om de veranderingen van GitHub samen te voegen met de veranderingen die je lokaal gemaakt hebt.

En dat is het! Als je lokale veranderingen naar de online Git-repository wilt sturen, doe je meestal het volgende:

1. Haal eerst de laatste versie op:

       git pull

2. Werk aan je project.

3. Kijk wat er veranderd is:

       git status

4. Heb je nieuwe bestanden gemaakt? Voeg die dan toe:

       git add .

5. Sla je veranderingen lokaal op:

       git commit -am "Beschrijf kort wat je hebt gedaan"

6. Haal eventuele veranderingen van anderen op:

       git pull

7. Stuur jouw veranderingen naar GitHub:

       git push

Als je niet zeker weet hoe het op enig moment staat, kun je altijd `git status` gebruiken om te kijken welke bestanden je nog moet toevoegen, of welke veranderingen nog niet opgeslagen zijn.

> Werkt tenminste één van jullie met macOS? Voeg dan direct handmatig de regel `.DS_Store` toe aan de `.gitignore`!

## Mergen

Wanneer je samenwerkt met anderen is het altijd mogelijk dat iemand in dezelfde file als jij heeft gewerkt, maar eerder diens veranderingen naar de repository heeft gepusht dan jij. Git zal dan proberen om de aanpassingen met elkaar te *mergen* wanneer je `git pull` gebruikt.

Git is hier normaal best goed in, maar voor sommige bestandstypen, of wanneer jullie allebei iets hebben aangepast op dezelfde regels in een bestand, weet Git niet goed wat er moet gebeuren. Git zal dan een *merge conflict* maken.

Deze conflicten gebeuren alleen op de computer van de persoon die `git pull` heeft gebruikt. Andere mensen die aan hetzelfde project werken zullen hier niets van merken.

Je kunt de conflicten niet onopgelost laten. Git wil dat je de conflicten oplost voordat je je aanpassingen daadwerkelijk kunt opsturen naar GitHub. Git zal altijd laten weten wanneer een conflict plaatsvindt en geeft daarbij ook aan in welke bestanden dit zo was. Als je dit gemist hebt, of als je meer informatie wilt, kun je altijd `git status` uitvoeren.

Als je een bestand met een merge conflict opent in een editor, zul je tenminste één keer, maar soms ook meerdere keren, regels zien die lijken op:

    <<<<<<< HEAD
    Jouw variant van de code
    =======
    De variant van de code die nu online staat
    >>>>>>> een boel getallen en letters

Ieder stuk code dat tussen de `<<<<<<< HEAD`-regel en de `=======`-regel staat, is de code die je lokaal hebt staan. Alle code die tussen de `=======`-regel en de `>>>>>>>`-regel staat, is code die van de online versie van het bestand komt.

Na de laatste `>>>>>>>`-tekens staat een reeks getallen en letters. Dit is een ID voor de online versie, en kan gebruikt worden om exact te vinden waar de code vandaan komt.

Om het merge conflict op te lossen, verwijder je de variant van de code die je niet nodig hebt, en alle extra regels die het conflict aangeven. Dat zijn de regels met `<<<<<<<`, `=======` en `>>>>>>>`.

Sla daarna het bestand op.

Vervolgens moet je Git vertellen dat je het conflict hebt opgelost:

    git add <bestand>

Daarna maak je een commit:

    git commit

Git opent nu mogelijk Nano, de editor die je eerder hebt ingesteld. Er staat al een standaardbericht klaar voor de merge commit. Meestal kun je dat bericht gewoon laten staan. Sla op met `Ctrl+O`, druk op Enter, en sluit af met `Ctrl+X`.

Nu kun je je aanpassingen online zetten:

    git push

## Oefenen met Git

Om even te oefenen met de workflow van Git, kun je een korte interactieve cursus [online](https://learngitbranching.js.org/) doen. Dit is niet noodzakelijk, maar het geeft je mogelijk wat meer zelfvertrouwen in het gebruik van Git.

Ook is er een handige korte referentie: [Simple Guide to Git](http://rogerdudler.github.io/git-guide/).
