# Tic-Tac-Toe

A command-line Tic-Tac-Toe game in Python. You play `X` against a computer that picks random free cells (`O`). No third-party packages are needed.

## Run it

Requires Python 3.8+.

```bash
git clone https://github.com/Hammad-Ahmed-hk/tic-tac-toe.git
cd tic-tac-toe
python tic_tac_toe.py
```

Enter a number from 1 to 9 to place your mark. Cells are numbered left to right, top to bottom:

```
1 | 2 | 3
4 | 5 | 6
7 | 8 | 9
```

## Notes

- The computer plays randomly, so it is easy to beat. A minimax opponent would be a good next step.
- Game logic (`check_winner`, `is_board_full`, ...) is separate from input handling, which makes it easy to unit test.

## Changes from the first version

- The game code was stored in `README.md`; it now lives in `tic_tac_toe.py`.
- Removed `import jpg`, which crashed the game on start.
- Removed the empty `index.html`.
- Fixed input validation: `0` used to be accepted as cell 9.

## Author

Hammad Ahmed, [@Hammad-Ahmed-hk](https://github.com/Hammad-Ahmed-hk)
