# Taak 1

State diagram die Task 1 weergeeft.

Het onderstaande diagram toont het proces bij Amazon voor de verwerking van een bestelling. 
Het proces begint wanneer de bestelling nog niet is geplaatst. 
Zodra de bestelling is geplaatst en ingepakt, wordt het pakket overhandigd aan PostNL voor verdere verwerking en bezorging.


```plantuml
@startuml

' Amazon Proces
state "Amazon Proces" as Amazon {
    [*] --> Stap0 : Bestelling niet geplaatst
    Stap0 --> Stap1 : Bestelling geplaatst
    Stap1 --> Stap2 : Bestelling ingepakt
    Stap2 --> [*] : Pakket overhandigd aan PostNL
}

@enduml

```