# Editing my portfolio

Open this folder in VS Code. Right-click index.html and choose Open with Live Server.
There is no build step, framework or package installation.

## Which file should I edit?

| Change | File |
| --- | --- |
| Name, introduction, experience, skills, education, contact | index.html |
| All project cards | projects.html |
| Eicher Motors project content | eicher-motors.html |
| S&P 500 project content | sp500-volatility.html |
| Customer churn project content | customer-churn.html |
| SEC sentiment project content | sec-sentiment.html |
| Colours, text sizes, spacing, cards and phone layout | style.css |
| Mobile menu behaviour | app.js |
| Browser tab icon | favicon.svg |

Use Ctrl+F to search for the exact heading or sentence you see in the browser.
Save with Ctrl+S and check the preview. Edit the text between tags; keep the tags.

## Make headings bigger or smaller

At the top of style.css, find the EASY SETTINGS section.

```css
--size-name: clamp(3rem, 6vw, 5.25rem);
--size-section-title: clamp(1.9rem, 3.4vw, 2.75rem);
--size-card-title: 1.3rem;
--size-body: 1rem;
```

1rem is normally 16px. A bigger number means bigger text.
clamp(minimum, flexible size, maximum) adjusts a heading for different screens.
For a smaller name, try clamp(2.5rem, 5vw, 4.5rem).
For a larger section heading, try clamp(2rem, 4vw, 3rem).

To change only one heading, add a rule such as:

```css
#skills h2 {
  font-size: 2rem;
}
```

## Change the colours

Edit these variables at the top of style.css:

```css
--color-dark: #172b29;          /* Header, hero and footer */
--color-dark-soft: #274a44;     /* Background shading */
--color-accent: #087c65;        /* Buttons and small headings */
--color-accent-hover: #065c4b;  /* Button hover */
--color-accent-light: #8de0c5;  /* Accent on dark backgrounds */
--color-text: #203630;          /* Main text */
--color-muted: #586a65;         /* Supporting text */
--color-page: #ffffff;          /* White sections */
--color-section: #f1f5f3;       /* Alternate sections */
```

Click a colour swatch in VS Code to use the colour picker. Keep text readable against its background.
The small decorative SVG chart colours are in index.html and projects.html. The tab icon colour is in favicon.svg.

## Change spacing and card corners

```css
--section-space: 5rem;
--card-padding: 1.75rem;
--grid-gap: 1.75rem;
--card-radius: 12px;
```

Phone and tablet rules are at the bottom of style.css. These change the layout at smaller widths.

## Add a skill

Find the correct skill-list in index.html. Copy one entire <li>...</li> block and edit its text.
Use evidence labels only when they are accurate. No ratings or progress bars are needed.

## Add a section (for example, certifications)

Paste this inside <main>, after Education and before Contact. Replace the example text with verified details.
Do not leave the example visible as a real qualification.

```html
<section class="section" id="certifications">
  <div class="section-heading">
    <p class="eyebrow">CERTIFICATIONS</p>
    <h2>Certifications</h2>
  </div>

  <div class="education-list">
    <article>
      <h3>Your qualification name</h3>
      <p>Issuing organisation</p>
      <p class="muted">Completion date or In progress</p>
      <!-- Add a real verification link here if available. -->
    </article>
  </div>
</section>
```

Give each section a unique id. If you want a menu link, add this inside #navigation:

```html
<a href="index.html#certifications">Certifications</a>
```

The header is repeated on all six pages. Update every page if you change the menu.

## Add a project

1. Copy one project page, such as eicher-motors.html, and give it a new filename.
2. Change the browser title, description, heading, question and section content.
3. In projects.html, copy a complete project-card link (from <a class="project-card" to its closing </a>).
4. Update the copied card's href, title, tags, description and visual.
5. Optionally add the same card to index.html. Keep the homepage focused on the strongest projects.
6. Update the Next project links if you want the new page in that sequence.

Each project page is plain HTML so you can edit it directly. No data file or generator is required.

## Add real project screenshots

Create an images folder, save your screenshot there, and replace the decorative project-art block with:

```html
<img src="images/my-project.png" alt="Describe the actual chart or dashboard" style="width: 100%; display: block;">
```

Use your own actual results and readable images. Decorative charts currently shown are illustrative.

## Add CV and contact links

Replace the CV coming-soon span with:

```html
<a class="button outline" href="cv.pdf" download>Download CV</a>
```

Put your real CV PDF beside index.html and name it cv.pdf. Replace contact placeholders with real links.
Never publish example email addresses, dummy links or unverified claims.

## Before publishing

Confirm all draft skill descriptions, internship labels, dates and employer names.
Complete the project content and add your actual contact links and CV.
Check desktop and phone layouts, 200% zoom, keyboard navigation and every link.
Upload the contents of this folder to your GitHub Pages publishing folder. Keep filenames and relative links intact.

## Verification

Local links, fragment targets, HTML nesting and JavaScript syntax were checked.
Automated visual browser testing has not been completed. Review the new theme in your VS Code Live Server preview.
