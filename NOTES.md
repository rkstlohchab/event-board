# Campus Event Board Notes

**Team members:** Rakshit Kumar (20261651069), Sakshi Kuntal (20261651076), Ravi Singh Singal (20261651072), Yash Anand (20261651099), Ankit Chaturvedi (20261651013)

## 1. Palette

The palette in `style.css` is:

- `--brand: #153e75`
- `--brand-deep: hsl(219 70% 18%)`
- `--accent: rgb(244 164 45)`
- `--accent-soft: #fff1d6`
- `--ink: #17243d`
- `--muted: rgb(79 94 117)`
- `--paper: #eef3f9`
- `--surface: #ffffff`
- `--line: #cad5e2`
- `--overlay: rgb(0 0 0 / 40%)`

Named variables are better than repeated color codes because a single edit updates the whole design, the names explain each color's purpose, and they keep the rules consistent.

## 2. Color formats

- Hex: `--brand: #153e75` supplies the primary campus blue.
- RGB: `--accent: rgb(244 164 45)` supplies the saffron highlights and date numerals.
- HSL: `--brand-deep: hsl(219 70% 18%)` supplies the header, footer, and hero base.
- Semi-transparent color: `--overlay: rgb(0 0 0 / 40%)` darkens the hero background so its white text remains easy to read.

## 3. Relative units

`rem` units follow the user's root font size, so text and spacing scale more accessibly than fixed pixels. The hero uses `width: calc(100% - 1rem)` to remain fluid while leaving a small inset. The main heading uses `font-size: clamp(2rem, 7vw, 4.5rem)` so it grows with the viewport without becoming too small or too large.

## 4. Box model calculation

For `width: 200px; padding: 20px; border: 5px`, `content-box` renders at `200 + 20 + 20 + 5 + 5 = 250px`. With `border-box`, the rendered width stays `200px`, leaving `150px` for the content. This project uses `* { box-sizing: border-box; }` so padding and borders are included in declared widths and responsive layouts are easier to predict.

## 5. Box model layers

From the inside out: content, padding, border, margin.

## 6. Responsive card grid

`repeat(auto-fit, minmax(15rem, 1fr))` creates as many columns as fit, prevents a card from becoming narrower than `15rem`, and shares any remaining space evenly. Grid recalculates the column count automatically, so this card reflow needs no media query.

## 7. Mobile-first design

Phone styles are the base because every device gets a simple, usable single-column layout first. `min-width` media queries progressively add the full navigation, form columns, and sidebar only when space is available. The viewport meta tag makes the browser use the real device width instead of a wide virtual layout viewport, which is essential for the breakpoints to behave correctly on phones.

## 8. Grid map

```css
grid-template-areas:
  "hero hero"
  "events faq"
  "events info"
  "submit submit";
```

The hero and submit regions span both columns by repeating their area names across a row. The events region spans two rows because `events` appears in the first column of both supporting-panel rows.

## 9. Responsive images and type

Images use `img { max-width: 100%; height: auto; }`, so they never overflow their containers. The heading uses `clamp(2rem, 7vw, 4.5rem)`, so its type scales fluidly. Neither technique needs a media query.

## 10. Repository and submission checklist

- Repository: https://github.com/rkstlohchab/event-board
- GitHub Pages: https://rkstlohchab.github.io/event-board/
- The repository includes `README.md`, `index.html`, `style.css`, retained lab CSS files, images, notes, and a readable commit history.
- `screenshot-event-cards.png` shows all six styled cards.
- `screenshot-phone.png` shows the narrow single-column layout and compact menu.
- `screenshot-desktop.png` shows the wide grid, full navigation, and responsive reflow.
- `screenshot-validator.png` shows the W3C CSS Validator result: **Congratulations! No Error Found.**
- `style.css` contains comments identifying the design system, box model, card component, responsive images, Grid, and mobile-first breakpoints.

## Code appendix

The PDF version of these notes ends with the complete final `index.html` and `style.css`, exactly as submitted.
