# Hangman Game (C++)

A command-line Hangman game built in C++ as a first-year Programming Project.  
Split into two executables that communicate through shared text files.

## How to Compile
```bash
g++ hangman_player.cpp -o hangman_player
g++ hangman_host.cpp -o hangman_host
```

## How to Run

**Play a game:**
```bash
./hangman_player <username>
./hangman_player <username> <words_file>
```

**Admin commands:**
```bash
./hangman_host view_leaderboard
./hangman_host view_history
./hangman_host view_history <username>
```

## Features
- Random word selection from `words.txt`
- First and last letters revealed, matching letters auto-filled
- 5 incorrect guesses allowed per word
- Score = length of correctly guessed word
- Persistent leaderboard saved to `leaderboard.txt`
- Per-player game history saved to `history.txt`
- ANSI color output

## File Structure
| File | Role |
|------|------|
| `hangman_player.cpp` | Game logic, player interaction |
| `hangman_host.cpp` | Admin: leaderboard & history viewer |
| `game.h` | Game class — word state, guessing logic |
| `leaderboard.h` | Score read/write |
| `history.h` | History read/write |
| `utils.h` | Shared utilities — header display, word loading |
| `words.txt` | Word list (required to run) |
| `leaderboard.txt` | Auto-generated on first game |
| `history.txt` | Auto-generated on first game |

## Data Flow
`hangman_player` updates `leaderboard.txt` and `history.txt` after each game.  
`hangman_host` reads those same files to display results — no keyboard input used.

## Authors
- **Tanul Bianca** — host/admin side, word & player data management
- **Preduț Alexia** — player side, game logic & score saving
