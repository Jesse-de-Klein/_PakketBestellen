# Communicatie tussen taken


Het onderstaande sequence diagram toont de communicatie tussen het Amazon proces en het PostNL proces.
Het begint met de klant die een bestelling plaatst bij Amazon, waarna het pakket wordt ingepakt en overgedragen aan PostNL.
PostNL vraagt de klant vervolgens om een keuze te maken: ophalen of bezorging.
Afhankelijk van de keuze volgt het pakket het juiste pad, waarbij het ofwel bezorgd wordt door PostNL of naar het ophaalpunt wordt gebracht.


```plantuml
@startuml

actor Klant
participant "Amazon Proces" as Amazon
participant "PostNL Proces" as PostNL

' Amazon Proces
Klant -> Amazon : Plaatst bestelling
Amazon -> Amazon : Bestelling wordt gepakt
Amazon -> PostNL : Pakket overhandigen

' PostNL Proces
PostNL -> PostNL : Pakket ontvangen
PostNL -> Klant : Keuze ophalen of bezorging
Klant -> PostNL : Klant kiest ophalen of bezorging

alt Bezorging gekozen
    PostNL -> PostNL : Bezorger onderweg
    PostNL -> Klant : Bezorger belt aan
    Klant -> PostNL : Deur open
    PostNL -> Klant : Pakket bezorgd
else Ophalen gekozen
    PostNL -> PostNL : Pakket naar ophaalpunt
    PostNL -> Klant : Pakket wordt opgehaald
end

@enduml
```