# DESIGN.md — Xinyutong ZHANG Portfolio

## 1. Color Palette

| Token      | Hex       | Use                                    |
| ---------- | --------- | -------------------------------------- |
| background | `#fefaf6` | Page background, card fills            |
| text       | `#000000` | All headings and body text             |
| muted      | `#888888` | Captions, secondary info               |
| border     | `#000000` | Grid lines, card borders               |

## 2. Typography

| Role     | Family           | Weight | Use                           |
| -------- | ---------------- | ------ | ----------------------------- |
| Display  | Instrument Sans  | 700    | Name, project titles, nav     |
| Body     | Instrument Serif | 400    | Tagline, descriptions         |
| UI       | Instrument Sans  | 400    | Tags, footer links            |

**Import:**
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Instrument+Sans:wght@400;500;700&family=Instrument+Serif:ital@0;1&display=swap" rel="stylesheet">
```

## 3. Grid System

- **Cell size:** 56 × 56 px (`--u: 56px`)
- **Content columns:** 24 cells = 1344px
- **Page width:** 26 cells = 1456px (24 content + 1 margin each side)
- **Horizontal padding:** 1 cell = 56px
- **Grid stroke:** `#000000`, weight `1px`, corner radius `10px`
- **Grid anchored to `.page`** with `background-position: 0 0` so card edges snap to grid lines

```css
background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='56' height='56'%3E%3Crect x='0.5' y='0.5' width='55' height='55' rx='10' fill='none' stroke='%23000' stroke-width='1'/%3E%3C/svg%3E");
background-size: 56px 56px;
background-position: 0 0;
```

## 4. Card & Element Rules

All cards, images, and containers must:
- **Dimensions:** width and height are multiples of `--u` (56px)
- **Border:** `1px solid #000000`
- **Border-radius:** `10px`
- **Fill:** `background: #fefaf6` (opaque, hides grid behind card for readability)
- **Padding:** multiples of `--u` (56px) for internal spacing
- **Exception:** image placeholder areas use `background: transparent` so the grid shows through

## 5. Layout

```
Page:      max-width: calc(26 * 56px) = 1456px, centered
Padding:   0 56px (1 cell each side)
Nav:       fixed bottom, 56px tall (1 cell)
```

**Project card dimensions (index.html):**

| Card              | Width (cells) | Width (px) | Min-height (cells) | Min-height (px) |
| ----------------- | ------------- | ---------- | ------------------ | --------------- |
| Binder (total)    | 20            | 1120       | 11                 | 616             |
| Binder image      | 10            | 560        | 11                 | 616             |
| Binder card text  | 10            | 560        | 11                 | 616             |
| Yulin Dream       | 18            | 1008       | 9                  | 504             |
| Does a Quiet St.  | 18            | 1008       | 8                  | 448             |

**Does a Quiet Street Listen?** has a 2-cell (112px) left offset.

**About page hero:**

| Section    | Width (cells) | Width (px) | Min-height (cells) | Min-height (px) |
| ---------- | ------------- | ---------- | ------------------ | --------------- |
| Photo      | 8             | 448        | 11                 | 616             |
| Info panel | 16            | 896        | 11                 | 616             |

Education section is inset by 9 cells (504px) to align with the info column.

## 6. Pages

| File        | Description                                   |
| ----------- | --------------------------------------------- |
| index.html  | Homepage: hero + Selected Works + 3 cards     |
| about.html  | About: photo placeholder + education          |
