sequenceDiagram
    participant Player
    participant Duck
    participant Dog
    participant GameStatus
    participant Game

    activate Player
    Player->>Game: Start Game/Level
    Game-->>Dog: Create dog
    activate Dog
    Game->>Dog: Requests animation
    Dog-->>Game:Gives animation
    loop break when hit count max or game over
    Game-->>Duck: Create duck
    activate Duck
    Player-->>Duck: Shoot Duck
    loop break when shot duck or missed shot
        Duck-->>Duck: Changes x and y flying end positions
        Duck-->>Player: Show success/missed shot
    end
    deactivate Player
 
    Duck-->>Game:Gives Animation
    Duck-->>Player: Gives shot info
    Duck->>GameStatus: Give duck score
    GameStatus->>GameStatus:Updates score
    deactivate Duck
    Player-->>GameStatus: Gives hit count
    GameStatus->>GameStatus:Updates hit count
    Player->>Dog: Requests animation
    Dog->>Game: Gives animation
    GameStatus-->>GameStatus:Checks hit count
    GameStatus-->>GameStatus:Check if game over
    GameStatus->Dog: Request animation if game over
    Dog-->>Game: Gives animation
    deactivate Dog
    end

    GameStatus-->>Player: Updates level
