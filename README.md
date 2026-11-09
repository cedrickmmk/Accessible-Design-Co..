# 📝 Project Reflection 

## 1. What accessibility challenges did you face, and how did you address them?

* **The Keyboard Navigation Trap (Bypassing Headers):** Sighted users can scan a page instantly, but keyboard/screen reader users must click `Tab` dozens of times through the top menu links just to reach the main page sections. I addressed this by implementing a hidden **Skip Link** (*Skip to main content*) as the very first focusable element inside the HTML `<body>`. It slides smoothly into view only when focused via keyboard navigation, instantly jumping focus down to the targeted `#main-content`.
* **Preventing Page Navigation Errors:** While wiring up the skip link, it initially threw page-not-found routing errors (`/main-content`). I corrected this by prepending a hash prefix (**`#`**) inside the anchor tag `href`, transforming a broken file path request into a functional internal page-jump link.

---

## 2. How did you ensure that your work was responsive and accessible to all users?

* **Fluid Responsive Grids:** I styled the `.service-grid` layout section using adaptive CSS Grid properties: `grid-template-columns: repeat(auto-fit, minmax(250px, auto));`. This prevents items from breaking or compressing blindly by allowing the rows to naturally collapse and auto-align cleanly on smaller screens while retaining explicit item boundaries.
* **Adaptive Theme Settings (Media Queries):** I implemented screen-width layout breakpoints (`@media screen and (max-width: 768px)`) to automatically force pure high-contrast text values on smaller device widths. This safeguards clear typographic readability under any environment change.
* **Preventing Layout Overflow:** To prevent interface text wrapping bugs on dynamic row headers—like the "Contact" nav item unexpectedly splitting off onto its own row, modified the navigation element with fixed width guidelines and strict horizontal tracking parameters (`flex-wrap: nowrap;`). This forces text to sit perfectly on a uniform layout row across multiple screen footprints.

---

## 3. What tools or resources did you find helpful during this project?

* **chrome Developer Tools (Inspector):** Invaluable for monitoring active CSS inheritances, discovering forgotten container layout boundaries, and finding broken margins or missing parent brackets that cause rendering drops.
* **Keyboard Accessibility Auditing (Tab-Testing):** Intentionally stepping through layout elements solely with the `Tab` and `Shift + Tab` commands to visually verify the visibility, layout layers (`z-index`), and focus paths of indicators like skip buttons.
* **Scrimba & MDN Web Docs:** Critical resources for understanding the structural relationship between semantic wrapper regions, focus anchors, and custom layout frameworks.
* **https://github.com/adam-p/markdown-here/wiki/markdown-cheatsheet:** to ubndestand te structure of wrtiting a README.
  