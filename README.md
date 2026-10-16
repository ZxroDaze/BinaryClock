# Binary Clock

A single-file, dependency-free **binary clock** that also teaches you how it works.
The live clock shows the time three ways at once and five short
interactive panels walk through the ideas behind it, one step at a time.

Everything lives in one file: `binary-clock.html`. so no dependencies needed.

---

## Running it

Just open `binary-clock.html` in any modern browser — double-clicking the file is enough.

## How to Nav

The six panels sit side by side on a horizontal track. Move between them with:

| Input              | Action                          |
| ------------------ | ------------------------------- |
| Drag / swipe       | Slide between panels (with flick momentum) |
| Mouse wheel / trackpad | Next / previous panel       |
| `←` / `→`          | Previous / next panel           |
| `Home` / `End`     | First / last panel              |
| Nav buttons        | Jump to the panel named on the button |
| URL hash           | Deep-link, e.g. `binary-clock.html#nibble` |

## The panels

| # | Panel            | What it does |
|---|------------------|--------------|
| 0 | **Clock**        | The live clock: six tubes, the 6×4 square grid, and the binary readout. Buttons switch 12/24-hour format and cycle the glow colour. |
| 1 | **A bit**        | One clickable square: off = 0, on = 1. The atom of the whole clock. |
| 2 | **Four bits**    | Four clickable squares with weights 8·4·2·1. Add the lit weights to read the number (0–15). |
| 3 | **Digits**       | Type 0–99 and see it split into a tens digit and a units digit, each drawn as its own column. |
| 4 | **Testing a bit**| Type 0–15 and see the `&` (AND) test the code uses to decide which squares light up. |
| 5 | **All together** | The whole chain running live: read time → split digits → convert to bits → light squares. |

## How the clock encodes time

1. Read the time, e.g. `13:07:45`.
2. Split each part into two decimal digits: `1 3 | 0 7 | 4 5` — six digits, six columns.
3. Write each digit in 4-bit binary (weights 8·4·2·1): `3 = 0011`, `7 = 0111`, …
4. Light one square per `1`. Add the lit weights in a column to get the digit back.

A digit is tested bit-by-bit with AND: `digit & weight != 0` → square on.

## Customising

You can change the colour of the clock if you find the orange a bit too orange lmao

I built this project to answer something I didnt quite fully grasp with actual simple digital clocks, what is a computer actually holding when it "knows" it's 13:07? 
I got my answer through building this :)
