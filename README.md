
# Rock, paper & scissors

This is the API (definition) of a 'rock, paper & scissors' game.

## About

This API was defined using Postman and the OpenAPI 3.0 specification.

However, in order to follow an API-first approach, any method chosen to design the API is valid, as long as the result is specification-compatible.

## How it works

First, the user will select one of the three available moves (*ROCK*, *PAPER* or *SCISSORS*) and lock its move for the current play.

At this point there cannot be another active play, and any attempts to restart the game will be revoked.

Once the move is selected, the play can be revealed simultaneously for both players and the winner is decided.

## Endpoints

### Play a move

This action will lock the player's move to start a new play. If there is already an ongoing play or the selected move is not a valid one, the action will be revoked.

**POST** `/play/<move>`
```
No body
```

Headers:
> **X-USER-ID**: *UUID v4 of the user playing*

### Resolve active play

This action will resolve the current play (if there is one), and will determine if either the player or the machine won (or if it's a tie), based on the move previously selected by the player.

**GET** `/play/reveal`

Headers:
> **X-USER-ID**: *UUID v4 of the user playing*
