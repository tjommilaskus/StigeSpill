sequenceDiagram
    participant P as Player
    participant G as Game Logic
    participant B as Board

    P->>G: Roll dice
    G-->>P: Dice value
    G->>B: Move player position
    B-->>G: New position

    alt Ladder or Snake
        G->>B: Move along ladder/snake
        B-->>G: Updated position
    end

    G-->>P: Show updated position

    alt Position = 100
        G-->>P: Player wins
    end
