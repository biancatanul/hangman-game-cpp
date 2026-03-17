# Hangman Game (C++)

A command-line Hangman game built in C++ as a first-year Programming Project.  
Split into two executables that communicate through shared text files.

## How to Compile
```bash
g++ hangman_player.cpp -o hangman_player
g++ hangman_host.cpp -o hangman_host
```

## How to Run

**Player app — play a game:**
```bash
./hangman_player play <username>
```
The program will choose a random word, process letter guesses, and update the leaderboard and history.

**Host app — admin commands:**
```bash
./hangman_host view_words
./hangman_host add_word <word>
./hangman_host delete_word <word>
./hangman_host view_leaderboard
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
| `hangman_host.cpp` | Admin: word list, leaderboard & history management |
| `game.h` | Game class — word state, guessing logic |
| `leaderboard.h` | Score read/write |
| `history.h` | History read/write |
| `utils.h` | Shared utilities — header display, word loading |
| `words.txt` | Word list (required to run) |
| `leaderboard.txt` | Auto-generated on first game |
| `history.txt` | Auto-generated on first game |

## Data Flow
`hangman_player` updates `leaderboard.txt` and `history.txt` after each game.  
`hangman_host` reads and modifies those same files — no keyboard input used.

## Authors
- **Tanul Bianca** — host app, word list & player data management
- **Preduț Alexia** — player app, game logic & score saving
