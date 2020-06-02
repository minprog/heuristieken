# macOS installatie
Alle installaties worden in de terminal gedaan.
Deze kan je met Spotlight openen door `⌘CMD + spatie` in te drukken en vervolgens op 'terminal' te zoeken.

#### Installeer CLT & Homebrew
De eerste stappen zijn het installeren van de Command Line Tools en Homebrew, die je nodig gaat hebben voor het installeren van de software.
Door de Command Line Tools te installeren krijg je meteen toegang tot Git.

1. Installeer Command Line Tools met:
    ```
    xcode-select --install
    ```
2. Ga naar de [Homebrew](https://brew.sh/) website en copy-paste het "Install Homebrew" commando in de terminal.
Voer het commando uit door op enter te drukken, waarna Homebrew geïnstalleerd is.

#### Installeer Python & Pip

{: start="3"}
3. Vervolgens moeten we Python en Pip installeren met:
    ```
    brew install python
    ```

Vervolgens kan je python gebruiken voor het runnen van code met het `python3` commando.
Als je extra python packages wilt installeren kan dat met het `pip3` commando.

#### Installeer check50

{: start="4"}
4. check50 is een python package en kan geïnstalleer worden met:
    ```
    pip3 install check50
    ```

Vervolgens kan je de check50 scripts uitvoeren zoals aangegeven bij de door jou gekozen case.
