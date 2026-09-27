# Campus Event Board Notes

Team members: Rakshit kumar (20261651069), Sakshi kuntal (20261651076), Ravi singh singal (20261651072), Yash anand (20261651099), Ankit chaturvedi (20261651013)

## 1. Palette

The palette in `style.css` is:

- `--brand: #c94f2d`
- `--brand-deep: hsl(14 64% 28%)`
- `--accent: rgb(244 183 64)`
- `--ink: #24313a`
- `--muted: rgb(82 96 105)`
- `--paper: #fffaf3`
- `--surface: #ffffff`
- `--line: #e4d8ca`

Named variables are better because one change updates the whole design. They also make rules easier to read than repeated color codes.

## 2. Color formats

- Hex: `--brand: #c94f2d` is the main brand color.
- `rgb()`: `--accent: rgb(244 183 64)` is used for highlights and the navigation button border.
- `hsl()`: `--brand-deep: hsl(14 64% 28%)` is used for the header and headings.
- Semi-transparent color: `rgb(0 0 0 / 40%)` is the hero overlay, which improves contrast over the banner background.

## 3. Relative units

`rem` respects the user's root font size, so text and spacing can scale more accessibly than fixed pixels. The stylesheet uses `width: calc(100% - 1rem)` for the hero, which leaves a small edge space while keeping it fluid. It uses `font-size: clamp(1.5rem, 4vw, 3rem)` for the main heading, which grows with the viewport but stays within readable limits.

## 4. Box model calculation

With `content-box`, the rendered width is `200px + 20px + 20px + 5px + 5px = 250px`.

With `border-box`, the rendered width is `200px`; the content area becomes `150px` after subtracting padding and borders. This project uses `box-sizing: border-box` because declared widths include padding and borders, making responsive layouts easier to control.

## 5. Box model layers

From inside out: content, padding, border, and margin.

## 6. Responsive card grid

`repeat(auto-fit, minmax(15rem, 1fr))` creates as many columns as fit, gives each card a minimum width of `15rem`, and shares remaining space between cards. It needs no media query because the grid automatically recalculates the number of columns as the available width changes.

## 7. Mobile-first design

Phone styles are the base because they provide a usable layout for the smallest screen first. `min-width` queries progressively add columns when there is enough room, keeping the CSS simple and resilient. The viewport meta tag makes the browser use the device width instead of a wide virtual desktop, so responsive CSS works correctly on phones.

## 8. Grid map

```css
grid-template-areas:
  "hero hero"
  "faq events"
  "info events"
  "submit submit";
```

The hero and submit regions span both columns. The events region spans two rows because it occupies the same grid area in the `faq/events` and `info/events` rows.

## 9. Responsive images and type

`img { max-width: 100%; height: auto; }` keeps images inside their containers without a media query. `clamp(1.5rem, 4vw, 3rem)` makes the heading fluid without a media query.

## 10. Submission checklist

The project includes `README.md`, the final `index.html`, and the final `style.css`. Git should be initialized in this folder with several descriptive commits so the history shows the work. A GitHub repository named `event-board` and its Pages URL should be added here after publishing.

Repository link: to be added after GitHub authentication and push.

Pages link: to be added if GitHub Pages is enabled.

## Code appendix

The final code appendix is the complete contents of [`index.html`](index.html) followed by [`style.css`](style.css). These are the exact final files used by the project and are kept as separate readable source files for submission and review.
