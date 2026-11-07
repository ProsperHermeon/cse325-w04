# CSE 325 – W04: Connect Four with Blazor

Prosper Opara

A two-player Connect Four game built with Blazor (interactive server rendering) on .NET 10 LTS, following Microsoft Learn's [Build a Connect Four game with Blazor](https://learn.microsoft.com/en-us/training/modules/dotnet-connect-four/) module.

## Module work

- `Board` component with a 7 × 6 board, styled with CSS isolation (`Board.razor.css`)
- `GameState` service registered as a singleton that holds the board and checks for wins
- Clicking a column arrow drops a piece with a falling animation
- Turn indicator, "Column is full" and "Game is over" errors, and win and tie detection
- Reset button after the game ends
- Board and player colors are component parameters (`BoardColor`, `Player1Color`, `Player2Color`), set from `Home.razor`

## My added feature: Move History

A panel beside the board lists every move in the current game:

- Each entry shows the move number, which player played, and the column and row where the piece landed (rows count up from the bottom)
- A colored dot matches each player's piece color, so it updates when the colors change
- The newest move is listed first and highlighted
- A counter shows how many of the 42 spaces are used
- Moves that fail (a full column, or playing after the game ends) are not recorded
- The list clears when the game is reset

The code is in `Components/Board.razor` (the `Move` record, the `moves` list, and the `<aside class="move-history">` markup) and its styles are at the bottom of `Components/Board.razor.css`.

## Run it

```bash
cd ConnectFour
dotnet run
```

Then open the `http://localhost:...` address shown in the terminal.
