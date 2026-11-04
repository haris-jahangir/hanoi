# Tower of Hanoi

A browser version of the classic Tower of Hanoi puzzle, by **Haris Jahangir**.

Move the whole stack of disks over to Tower 3 — one disk at a time, and never a
larger disk onto a smaller one.

**▶ [Play it here](https://KibroPixen.github.io/tower-of-hanoi/)**

## Features

- **Drag and drop or click** — drag a disk between towers, or click one tower to
  pick up its top disk and another to drop it
- **1 to 10 disks**, set with the ▼ ▲ steppers
- **Move counter** and the minimum number of moves for the current disk count
- **Move log** — a numbered list of every move made
- **Solve!** — animates a solution from *any* legal position, not just the
  starting one, and can be stopped mid-run
- **Keyboard play** — `1` `2` `3` select towers, `Esc` cancels a selection
- Responsive layout that works on phones

## Running it

There is no build step and there are no dependencies. Open `index.html` in any
browser, or serve the folder:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Hosting on GitHub Pages

The whole game is one static file, so Pages needs no configuration beyond
pointing at the branch:

1. Push the repository to GitHub
2. Go to **Settings → Pages**
3. Under **Source**, choose branch `main` and folder `/ (root)`
4. Save — the site goes live at `https://<username>.github.io/<repo>/`

## How the puzzle works

With `n` disks the shortest solution takes `2ⁿ − 1` moves, which is also what
the "Minimum Moves" readout shows. Three disks need 7 moves, ten disks need
1,023.

The solver uses the standard recursive strategy: to move the largest disk `n` to
its target tower, first move the `n−1` disks above it onto the spare tower, move
disk `n` across, then move those `n−1` disks on top of it. Because it reads the
live board rather than assuming a fresh start, it can finish a game you have
already played partway through.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The entire game — markup, styles and logic in one file |
| `README.md` | This file |

## License

MIT — free to use, change and share.
