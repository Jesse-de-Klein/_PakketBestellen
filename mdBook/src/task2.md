# Taak 2

State diagram die Task 2 weergeeft.

Het onderstaande diagram toont het proces bij PostNL voor de verwerking en bezorging van een pakket. 
Het proces begint wanneer PostNL een pakket ontvangt van Amazon. 
De klant heeft tijdens het bestellen de keuze gemaakt om het pakket zelf op te halen of te laten bezorgen. 
Afhankelijk van de keuze volgt het pakket verschillende routes, waarbij het via een bezorgingstraject of via het ophaalpunt naar de klant gaat.



```plantuml
@startuml

' PostNL Proces
state "PostNL Proces" as PostNL {
    [*] --> Stap0 : Wachten op pakket van Amazon
    Stap0 --> Stap1 : Pakket ontvangen van Amazon
    Stap1 --> KeuzeKlant : Pakket gesorteerd
    KeuzeKlant --> Stap3 : Pakket zelf ophalen
    KeuzeKlant --> Stap4 : Pakket laten bezorgen
    Stap4 --> Stap5 : Bezorger onderweg met pakket
    Stap5 --> Stap6 : Bezorger belt aan
    Stap6 --> PakketBinnen : Deur open
    Stap6 --> Stap8 : Deur blijft dicht
    Stap8 --> Ophaalpunt : Pakket gaat naar ophaalpunt
    Stap3 --> Ophaalpunt : Pakket gaat naar ophaalpunt
    Ophaalpunt --> PakketBinnen : Pakket wordt opgehaald
    
}

@enduml


```
