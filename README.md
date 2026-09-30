# Mercy Hire Car Website

**IS229 – Web Design | Assessment 3: Web Design Using HTML5 + CSS3 – Responsive Website**

## Project Overview

This is a multi-page, responsive website for **Mercy Hire Car**, a local car-hire business based in Lae, Morobe Province, Papua New Guinea.

In Assessment 2 the site was built with HTML5 only and used the browser's default styling. For Assessment 3 the same five pages have been extended with hand-written CSS3 to give the site a consistent visual identity and a layout that adapts to mobile, tablet and desktop screens.

**No CSS framework, downloaded theme or page builder was used** (no Bootstrap, no Tailwind). All styling is written directly in CSS.

## Target Audience

* Local customers in Lae
* Visitors and travellers to Lae
* Individuals and families looking for a hire car
* Businesses requiring vehicle hire
* Customers who want to make a booking or enquiry, often from a phone

## Website Pages

| Page | File | Stylesheet | Purpose |
|------|------|------------|---------|
| Home | `index.html` | `css/index.css` | Introduces the business, "Why Choose Us", services overview and opening hours |
| About Us | `about.html` | `css/about.css` | Business background, location map, mission, values and team |
| Services & Vehicles | `services.html` | `css/services.css` | Services, vehicle photos and hire-rates table |
| Gallery | `gallery.html` | `css/gallery.css` | Photo gallery, useful hire information and fleet photo |
| Contact & Booking | `contact.html` | `css/contact.css` | Contact details and the booking/enquiry form |

## Technologies Used

* **HTML5** – semantic structure, forms, tables, figures, embedded map
* **CSS3** – external stylesheets, custom properties (variables), Flexbox, CSS Grid, media queries, flexible units
* **Visual Studio Code** – code editor
* **Git** and **GitHub** – version control and repository hosting
* **GitHub Pages** – hosting the live website

## Visual Design System

### Colour system

Colours are defined once as CSS custom properties in `:root` and reused throughout.

| Variable | Value | Used for |
|----------|-------|----------|
| `--green` | `#0f4c3a` | Header, headings, primary buttons, table headers |
| `--green-dark` | `#0a3528` | Footer, hover states, sub-headings |
| `--gold` | `#e0a100` | Accent borders, focus outline |
| `--text` | `#1f2a26` | Body text |
| `--muted` | `#55625d` | Captions and secondary text |
| `--bg` | `#f4f6f5` | Page background |
| `--white` | `#ffffff` | Cards, panels and form fields |
| `--border` | `#d3dad7` | Card, table and fieldset borders |

### Typography

* Font stack: `"Segoe UI", Arial, Helvetica, sans-serif`
* Base size `1rem` with a `1.6` line height for readability
* Heading scale: `h1` 2rem (1.6rem on small screens), `h2` 1.5rem, `h3` 1.15rem
* Captions `0.9rem`; paragraph and list width limited to `70ch` for comfortable line length

### Spacing and hierarchy

* Spacing uses `rem` units (for example 0.25rem, 0.75rem, 1rem, 1.5rem, 2rem) so it scales with the user's font size
* `--page-pad` keeps page content centred with a maximum width of about `62rem` and a minimum side padding of `1rem`
* Content sits in white "panel" cards with a border and rounded corners; article blocks have a gold left border to separate them visually

### Consistent components

* **Navigation** – green header bar; the current page is highlighted using `aria-current="page"`
* **Cards/panels** – `main section` and `main aside` share the same background, border, radius and padding
* **Buttons** – shared size, font and border; the Submit button is filled green, the Clear button is outlined
* **Forms** – grouped in fieldsets with consistent field width, padding, borders and labels
* **Tables** – green header row, bordered cells, shaded row headers

## Layout Techniques

### Flexbox

* The main navigation (`nav ul`) is a flex container with `flex-wrap` and `gap`, so links sit in a row and wrap when space runs out. On small screens the direction changes to a column.

### CSS Grid

Grid is used for the main content layouts. Each uses `repeat(auto-fit, minmax(…, 1fr))`, so the number of columns adjusts to the space available without needing fixed breakpoints:

* **Home** – "Why Choose Us" cards
* **About** – "Our Values" cards
* **Services** – service cards and vehicle photos (the rates table spans the full row)
* **Gallery** – photo grid

Headings and intro paragraphs inside these grids span all columns using `grid-column: 1 / -1`.

## Responsive Design

The site is designed to adapt its structure to mobile, tablet and desktop viewports rather than simply shrinking the desktop layout.

| Viewport | Behaviour |
|----------|-----------|
| **Mobile** (up to 600px) | Navigation links stack in a single column; header title is smaller; panel padding is reduced; grids fall to a single column; table cell padding and font size are reduced |
| **Tablet** (approx. 601px – 1000px) | Grid layouts automatically show two columns where space allows; navigation wraps in a row |
| **Desktop** (above approx. 1000px) | Content is centred at a maximum width of about 62rem; grids show three or more columns; navigation sits on one row |

Responsive techniques used:

* `<meta name="viewport" content="width=device-width, initial-scale=1.0">` on every page
* A `@media (max-width: 600px)` media query in each stylesheet
* Intrinsic grid responsiveness using `auto-fit` and `minmax()`
* Flexible units (`rem`, `%`, `ch`) rather than fixed pixel layouts
* Images use `max-width: 100%` and `height: auto` so they scale within their containers; `width`/`height` attributes are set in the HTML to reduce layout shift
* The embedded Google Map on the About page uses `width="100%"` and `loading="lazy"`

## Accessibility

* Visible keyboard focus: a 3px gold `:focus-visible` outline with offset on all interactive elements
* Dark text on light backgrounds and white text on dark green for strong contrast
* Semantic HTML5 landmarks (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`)
* `aria-current="page"` and `aria-label` on navigation; `aria-labelledby` on sections
* Logical heading hierarchy and descriptive link text
* Alternative text on all images, with figures and captions
* Labels associated with every form control; fieldsets and legends group related fields
* Invalid form fields are shown with a red border (`:user-invalid`) in addition to browser validation messages
* Links and buttons have hover styles as well as focus styles

## Project Structure

```text
mercy-hire-car/
│
├── index.html
├── about.html
├── services.html
├── gallery.html
├── contact.html
│
├── css/
│   ├── index.css
│   ├── about.css
│   ├── services.css
│   ├── gallery.css
│   └── contact.css
│
├── images/
│   ├── fleet.jpg
│   ├── img1.jpg
│   ├── img2.jpg
│   ├── img4.jpg
│   ├── imgs1.jpg
│   ├── imgs2.jpg
│   ├── imgs3.jpg
│   └── imgs4.jpg
│
├── screenshots/
│   ├── mobile.png
│   ├── tablet.png
│   └── desktop.png
│
└── README.md
```

## Testing

### Responsive testing

Pages were checked using the browser's developer tools (responsive/device mode) at the following widths. **Complete the Result column after testing and save screenshots in the `screenshots/` folder.**

| Device type | Width tested | Pages checked | Result | Screenshot |
|-------------|--------------|---------------|--------|------------|
| Mobile | 375px | All 5 pages | ☐ Pass / ☐ Fail | `screenshots/mobile.png` |
| Tablet | 768px | All 5 pages | ☐ Pass / ☐ Fail | `screenshots/tablet.png` |
| Desktop | 1280px | All 5 pages | ☐ Pass / ☐ Fail | `screenshots/desktop.png` |

### Browser testing

| Browser | Version | Result | Notes |
|---------|---------|--------|-------|
| Google Chrome | | ☐ Pass / ☐ Fail | |
| Microsoft Edge | | ☐ Pass / ☐ Fail | |
| Mozilla Firefox | | ☐ Pass / ☐ Fail | |
| Mobile browser (real phone) | | ☐ Pass / ☐ Fail | |

### Checklist

* ☐ Navigation links work on all five pages
* ☐ No horizontal scrolling at mobile width
* ☐ Images scale and do not overflow their containers
* ☐ Grid layouts reflow correctly between widths
* ☐ Tables remain readable on mobile
* ☐ Form fields, buttons and validation work at all widths
* ☐ Keyboard focus is visible when tabbing through each page
* ☐ HTML passes the W3C Markup Validation Service
* ☐ CSS passes the W3C CSS Validation Service
* ☐ Published site loads correctly from GitHub Pages

## Git and Development

Git was used to track development. Changes were committed progressively, including:

* Reviewing the Assessment 2 structure and planning the visual system
* Creating CSS variables for colour, typography and spacing
* Styling the header, navigation, buttons and forms
* Adding Flexbox and Grid layouts
* Adding media queries and responsive adjustments
* Testing on mobile, tablet and desktop, then fixing defects
* Publishing with GitHub Pages

The full commit history is available in the GitHub repository.

## Published Website

**GitHub Repository:** 

<<<<<<< HEAD
`[paste repository URL here]`
=======
https://github.com/dashatelikadah-coder/A3-Web-Design.git
>>>>>>> cae6cce221919d443c210fca88a4fe95e292ba67

**Live Website:** 

`[paste GitHub Pages URL here]`

## Known Limitations

* The booking form's `action` points to a placeholder address, so submissions are not sent anywhere. The form is used to demonstrate HTML5 validation and styling only.
* The website uses one main breakpoint (600px) plus the automatic reflow of the grid layouts.
* The contact details in the footer and contact page use a placeholder phone number and email address.

## AI Use Declaration

AI-assisted tools were used during this assessment for learning support, brainstorming, reviewing the assessment requirements, and help with drafting and updating this README. The website design, code, content, images, testing and submission were reviewed, edited and checked by the student, who takes responsibility for the final work.

## Assessment Information

**Course:** IS229 – Web Design
**Assessment:** Assessment 3 – Web Design Using HTML5 + CSS3 – Responsive Website
**Project:** Mercy Hire Car Website
**Student:** Dasha Telikadah
**Year:** 2026
