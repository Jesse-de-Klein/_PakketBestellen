# Functie

Het onderstaande sequence diagram toont de interactie tussen de klant, het PostNL proces en de Track & Trace functie.
Wanneer de klant de Track & Trace informatie opvraagt, bepaalt het PostNL proces de huidige stap van het pakket.
Afhankelijk van de stap wordt de Track & Trace functie aangeroepen, die de bijbehorende statusinformatie retourneert.
Uiteindelijk wordt de Track & Trace informatie aan de klant verstrekt.
s

```plantuml
@startuml

actor Klant
participant "PostNL Proces" as PostNL
participant "TrackAndTrace Functie" as TrackAndTrace

Klant -> PostNL : Verzoekt Track & Trace Informatie
PostNL -> PostNL : Bepaal de huidige stap (CASE)
PostNL -> TrackAndTrace : Roep functie aan met stapnummer
TrackAndTrace -> PostNL : Retourneer Track & Trace Informatie
PostNL -> Klant : Geef Track & Trace Informatie door

@enduml
```