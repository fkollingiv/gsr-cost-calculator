# Genomics Cost Calculator — Website Setup Instructions

These instructions walk you through three steps:

1. Creating the calculator page on omics.dartmouth.edu
2. Adding a button to the Genomics and Molecular Biology page on omics.dartmouth.edu
3. Adding a button to the GSR homepage at geiselmed.dartmouth.edu/gsr

---

## Step 1: Create the Calculator Page

**Target URL:** `sites.dartmouth.edu/omics/genomics-and-molecular-biology/genomics-cost-calculator`

1. In your WordPress dashboard for `sites.dartmouth.edu/omics`, go to **Pages → Add New**
2. Set the **Page Title** to: `Genomics Cost Calculator`
3. Under **Page Attributes** (right sidebar), set the **Parent Page** to: `Genomics and Molecular Biology`
   - This will create the URL: `/genomics-and-molecular-biology/genomics-cost-calculator`
4. In the page editor, add a **Custom HTML** block (not a paragraph block)
5. Paste the entire contents of the file **`gsr-estimator-wp.html`** into the Custom HTML block
6. Click **Publish**

> **Tip:** Use the "Preview" button first to make sure the calculator renders correctly before publishing.

---

## Step 2: Add a Button on the Genomics and Molecular Biology Page (omics.dartmouth.edu)

This page already has three green buttons ("Bulk DNA/RNA Assays", "Single Cell Genomics", "Spatial Technologies"). You'll add a fourth button that matches the existing style.

**Option A — Add via WordPress Block Editor:**

1. Edit the **Genomics and Molecular Biology** page
2. Find the row of three green buttons
3. Add another **Custom HTML** block in that same row (or below it)
4. Paste this HTML:

```html
<div style="text-align: center; margin: 20px auto;">
  <a href="/genomics-and-molecular-biology/genomics-cost-calculator"
     style="display: inline-block; min-width: 250px; height: 200px;
            background-color: #005338; color: #fff;
            font-family: National2WebBold, Arial, sans-serif;
            font-size: 1.5em; font-weight: bold;
            text-decoration: none; border-radius: 0px;
            line-height: 200px; text-align: center;
            transition: background-color 0.3s;"
     onmouseover="this.style.backgroundColor='#00281b'; this.style.textDecoration='underline'"
     onmouseout="this.style.backgroundColor='#005338'; this.style.textDecoration='none'">
     Cost Estimator
  </a>
</div>
```

**Option B — If the buttons are in a row of WordPress "Buttons" blocks:**

1. Click into the existing button row
2. Use the "+" button to add a fourth Button block
3. Set the text to: `Cost Estimator`
4. Set the link to: `/genomics-and-molecular-biology/genomics-cost-calculator`
5. Match the style settings: Background `#005338`, text white, min-width 250px, no border-radius

---

## Step 3: Add a Button on the GSR Homepage (geiselmed.dartmouth.edu/gsr)

The GSR homepage has a "Quick Links" section with links to Genomics Services, Dartmouse, and Data Analysis. Add the Cost Estimator as a new quick link or a prominent button.

**Option A — Add as a Quick Link button (matches existing style):**

1. Edit the GSR homepage in WordPress
2. Find the Quick Links section (or wherever you'd like the button)
3. Add a **Custom HTML** block and paste:

```html
<div style="text-align: center; margin: 15px 0;">
  <a href="https://omics.dartmouth.edu/genomics-and-molecular-biology/genomics-cost-calculator"
     style="display: inline-block; padding: 14px 32px;
            background-color: #006845; color: #fff;
            font-family: Arial, sans-serif;
            font-size: 16px; font-weight: 700;
            text-decoration: none; border-radius: 6px;
            transition: background-color 0.3s;"
     onmouseover="this.style.backgroundColor='#004d33'"
     onmouseout="this.style.backgroundColor='#006845'">
     Cost Estimator
  </a>
</div>
```

**Option B — Add in the sidebar/widget area:**

1. Go to **Appearance → Widgets**
2. Find the sidebar used on the GSR homepage
3. Add a **Custom HTML** widget with the same HTML from Option A above

---

## Notes

- The `gsr-estimator-wp.html` file is the WordPress-compatible version — it uses a `<style>` block and inline `<script>` without the `<!DOCTYPE>`, `<html>`, `<head>`, or `<body>` wrappers, so it works inside a WordPress Custom HTML block.
- The calculator is entirely self-contained (no external dependencies). All CSS, HTML, and JavaScript are in the single file.
- FY27 internal Dartmouth rates are hardcoded in the JavaScript `P` object at the top of the script. When rates change, update those values directly in the Custom HTML block.
- The calculator uses Dartmouth green (`#006845`) as its primary color, which closely matches both sites' branding.
