# Windows installatie
Voor Windows moet eerst Windows Subsystem for Linux (WSL 1) geïnstalleerd worden.
Vervolgens kunnen we Ubuntu installeren en met een terminal check50 installeren.

#### Windows Subsystem for Linux
Windows Subsystem for Linux kan geactiveerd en geïnstalleerd worden met een paar simpele commando's.

1. Activeer de optie met een terminal.
    1. Open PowerShell als administrator en run:  
        ```
        dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
        ```
        ![Commando in PowerShell om WSL te activeren.](../windows/powershell_wsl_enable.png)

    {: start="2"}
    2. Start vervolgens de computer opnieuw op.

#### Installeer Ubuntu

{: start="2"}
2. Installeer Ubuntu via de Microsoft Store.
    1. Open de Microsoft Store en zoek naar Ubuntu.
    2. Selecteer `Ubuntu` (dus zonder versie erachter!) en installeer de applicatie door op de `Get` knop te klikken.
    ![Search for Ubuntu in the Windows Store.](../windows/ws_ubuntu.png)
3. Start de Ubuntu applicatie op en wacht tot de installatie voltooid is.
4. Geef een gebruikersnaam en wachtwoord op die je gaat gebruiken voor het Ubuntu besturingssysteem.
Dit account zal alle administrator rechten krijgen binnen Ubuntu.
5. Update Ubuntu door de volgende regel uit te voeren in de terminal:  
```
sudo apt update && sudo apt upgrade
```

#### Installeer Python, Pip & check50
De Ubuntu installatie komt met Git, dus alleen Python en Pip moeten geïnstalleerd worden voordat we check50 kunnen installeren.
De installatiestappen gebeuren allemaal binnen het Ubuntu besturingssysteem waar je in komt door de Ubuntu applicatie op te starten.

{: start="6"}
6. Installeer Python en Pip voor het Ubuntu besturingssyteem met:  
    ```
    sudo apt install python3 python3-pip
    ```
7. Open een terminal en installeer check50 met:  
    ```
    sudo pip3 install check50
    ```   

Vervolgens kan je de check50 scripts uitvoeren zoals aangegeven bij de door jou gekozen case.
