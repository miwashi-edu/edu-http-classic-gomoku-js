# edu-http-classic-gomoku-js

## Expected time 6:30 minutest

## Info

In this part we will attempt to find requrements for our value-objects. We use a mockup of the game to try to determine what data is required to display a game trough it different states from create to end. We also assume that all methods will return a game object. 

Finally we also deduce that we also need a state attribute to respond to the end states of the game (win/loose, tie).

## Instructions

```mermaid

sequenceDiagram
    actor Player
    participant Service
    participant UserHandler
    participant GameHandler
    participant Gomoku

    Player->>Service: Identifies
    activate Service
    activate UserHandler
    Service->>UserHandler: Identify
    UserHandler-->>Service: Player Id
    deactivate UserHandler
    Service-->>Player: Player Id
    deactivate Service
    
    Player->>Service: List Games
    activate Service
    Service->>GameHandler: List Games
    activate GameHandler
    GameHandler-->>Service: List of Games
    deactivate GameHandler
    Service-->>Player: List of games
    deactivate Service
    
    activate Service
    alt Choose game
        Player->>Service: Find Game
        Service->>GameHandler: Find Game by ID
        activate GameHandler
        GameHandler-->>Service: Selected Game
        deactivate GameHandler
    else Create Game
        Player->>Service: New Game
        Service->>GameHandler: Create Game
        activate GameHandler
        GameHandler-->>Service: Created Game
        deactivate GameHandler
    end
    Service-->>Player: Game
    deactivate Service
    
    activate Service
    loop Until Finnished
        Player->>Service: Play Game
        Service->>GameHandler: Play
        activate GameHandler
        GameHandler->>Gomoku: isFinished?
        activate Gomoku
        Gomoku->>GameHandler: true/false
        deactivate Gomoku
        GameHandler->>Service: isFinished?
        deactivate GameHandler
        Service-->>Player: Incremented Game
    end
    deactivate Service
```
