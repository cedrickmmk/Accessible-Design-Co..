# Accessible Design Co.

A responsive, accessibility-focused landing page built with semantic HTML5 and CSS3 for **Accessible Design Co.**, a digital agency specializing in inclusive UX design, WCAG audits, and accessibility consulting.

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Page Sections](#page-sections)
- [Built With](#built-with)
- [Accessibility Highlights](#accessibility-highlights)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Author](#author)

## Overview

### Key Features

- **Accessibility-First Navigation:** Includes a keyboard-focusable **Skip to Main Content** link (`.skip-link`), ARIA landmarks (`role="navigation"`, `aria-label`), and descriptive `alt` text across brand and social media icons.
- **Responsive Layout:** Combines **CSS Flexbox** (header navigation, hero banner, service cards, and footer) with a **CSS Grid** (`repeat(auto-fit, minmax(250px, auto))`) service showcase and a mobile media query (`@media screen and (max-width: 768px)`).
- **Interactive Contact Form:** Accessible form structure with explicit `<label for="...">` associations, required input fields (`Full Name`, `Email address`, `Subject`, `Message`), and styled focus states.

### Page Sections

1. **Header & Navigation (`<header>`):** Brand logo, company title, and navigation links (`Home`, `About`, `Services`, `Contact`).
2. **Hero Section (`#Home`):** Full-width hero banner with a mission statement and `"GET STARTED"` call-to-action button.
3. **About Us (`#About`):** Overview of the company's commitment to WCAG-compliant, inclusive digital design.
4. **Our Services (`#Services`):** Four-card responsive grid highlighting:
- *Web Accessibility*
- *Inclusive UX Design*
- *Accessibility Audits*
- *Training & Consulting*
5. **Contact Us (`#Contact`):** User inquiry form with text inputs, email validation, and message textarea.
6. **Footer (`<footer>`):** Social media links (Facebook, X/Twitter, Instagram, LinkedIn, GitHub), contact details, and legal/copyright information.

## Built With

- **HTML5:** Semantic structure (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`) and ARIA attributes.
- **CSS3:** Custom layout styling using Flexbox, CSS Grid, responsive media queries, and focus transitions.

## Accessibility Highlights

- **Skip Navigation Link:** Off-screen `.skip-link` becomes visible at the top-left of the viewport on `:focus`, letting keyboard and screen-reader users jump directly to `#main-content`.
- **Semantic Landmarks & Headings:** Logical heading hierarchy (`<h1>` through `<h3>`) paired with `<article>` cards for assistive technology navigation.
- **Form & Link Labeling:** Every form input is explicitly paired with a `<label>`, and icon-only social links include `aria-label` attributes.

## Project Structure

```text
Accessible-Design-Co./
├── images/ # Hero background, service card images, and social media icons
├── index.html # Main semantic HTML document
├── styles.css # Layout, responsive grid/flexbox, and accessibility styles
└── README.md # Project documentation
```

## Getting Started

1. **Clone the repository:**
```bash
git clone https://github.com
```
2. **Open the project:**
Open `index.html` directly in your browser or run it with VS Code's **Live Server** extension.

## Author

- **GitHub:** [@cedrickmmk](https://github.com)


## 📝 Project Reflection 

### 1. What accessibility challenges did you face, and how did you address them?

* **The Keyboard Navigation Trap (Bypassing Headers):** Sighted users can scan a page instantly, but keyboard/screen reader users must click `Tab` dozens of times through the top menu links just to reach the main page sections. I addressed this by implementing a hidden **Skip Link** (*Skip to main content*) as the very first focusable element inside the HTML `<body>`. It slides smoothly into view only when focused via keyboard navigation, instantly jumping focus down to the targeted `#main-content`.
* **Preventing Page Navigation Errors:** While wiring up the skip link, it initially threw page-not-found routing errors (`/main-content`). I corrected this by prepending a hash prefix (**`#`**) inside the anchor tag `href`, transforming a broken file path request into a functional internal page-jump link.

---

### 2. How did you ensure that your work was responsive and accessible to all users?

* **Fluid Responsive Grids:** I styled the `.service-grid` layout section using adaptive CSS Grid properties: `grid-template-columns: repeat(auto-fit, minmax(250px, auto));`. This prevents items from breaking or compressing blindly by allowing the rows to naturally collapse and auto-align cleanly on smaller screens while retaining explicit item boundaries.
* **Adaptive Theme Settings (Media Queries):** I implemented screen-width layout breakpoints (`@media screen and (max-width: 768px)`) to automatically force pure high-contrast text values on smaller device widths. This safeguards clear typographic readability under any environment change.
* **Preventing Layout Overflow:** To prevent interface text wrapping bugs on dynamic row headers—like the "Contact" nav item unexpectedly splitting off onto its own row, modified the navigation element with fixed width guidelines and strict horizontal tracking parameters (`flex-wrap: nowrap;`). This forces text to sit perfectly on a uniform layout row across multiple screen footprints.

---

### 3. What tools or resources did you find helpful during this project?

* **chrome Developer Tools (Inspector):** Invaluable for monitoring active CSS inheritances, discovering forgotten container layout boundaries, and finding broken margins or missing parent brackets that cause rendering drops.
* **Keyboard Accessibility Auditing (Tab-Testing):** Intentionally stepping through layout elements solely with the `Tab` and `Shift + Tab` commands to visually verify the visibility, layout layers (`z-index`), and focus paths of indicators like skip buttons.
* **Scrimba & MDN Web Docs:** Critical resources for understanding the structural relationship between semantic wrapper regions, focus anchors, and custom layout frameworks.
* **https://github.com/adam-p/markdown-here/wiki/markdown-cheatsheet:** to ubndestand te structure of wrtiting a README.
  
