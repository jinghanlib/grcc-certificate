# Graduate Research Core Competencies Certificate

A **self-paced, open certificate website** for UC Riverside graduate students, built with [Quarto](https://quarto.org) and deployable to [GitHub Pages](https://pages.github.com) — no server required.

![Certificate](images/certificate-thumbnail.jpg)

---

## 🗂️ What's Inside

| Module | Topic |
|---|---|
| 1 | Citation Management (Zotero, Paperpile, Biosketch) |
| 2 | Scholarly Communication (ORCID, Open Access, eScholarship) |
| 3 | Data Management (DMP, Dryad, file formats) |
| 4 | Literature Review Strategies (search methods, types of review) |
| 5 | Publish & Share Your Research (copyright, fair use, publishing path) |
| 6 | Graduate Academic Affairs (formatting, ProQuest, graduation) |
| 7 | Capstone: Research Plan |
| — | Interactive Knowledge Checks (from original Canvas quizzes) |

---

## 🚀 Deploying to GitHub Pages

### Option A — Automatic (Recommended): GitHub Actions

Every push to `main` automatically builds and publishes the site. Zero local setup required.

**Steps:**

1. **Fork or create a new repository** on GitHub and upload this folder's contents.

2. **Enable GitHub Pages with GitHub Actions:**
   - Go to your repo → **Settings** → **Pages**
   - Under *Source*, select **GitHub Actions**

3. **Push to `main`** — the workflow in `.github/workflows/publish.yml` will run automatically.

4. **Your site will be live** at:
   ```
   https://jinghanlib.github.io/grcc-certificate/
   ```

5. **Update the GitHub URL** in `_quarto.yml`:
   ```yaml
   href: https://github.com/jinghanlib/grcc-certificate
   ```

---

### Option B — Manual: Pre-rendered `docs/` folder

If you prefer not to use GitHub Actions, you can render locally and push the output.

**Prerequisites:** Install [Quarto CLI](https://quarto.org/docs/get-started/) (free).

```bash
# 1. Clone your repo
git clone https://github.com/jinghanlib/grcc-certificate.git
cd grcc-certificate

# 2. Render the site (outputs to docs/)
quarto render

# 3. Commit and push
git add .
git commit -m "Render site"
git push origin main
```

Then in GitHub → **Settings** → **Pages** → set Source to **Deploy from a branch** → `main` / `docs`.

---

### Option C — Quarto Publish (one command)

```bash
quarto publish gh-pages
```

This creates a `gh-pages` branch automatically. Select **Deploy from a branch** → `gh-pages` / `root` in GitHub Pages settings.

---

## 🛠️ Local Development

```bash
# Install Quarto: https://quarto.org/docs/get-started/

# Preview with live reload
quarto preview

# Render to docs/ without previewing
quarto render
```

The site will open at `http://localhost:4444` (or similar) with hot reload on file save.

---

## 📁 Project Structure

```
grcc-certificate/
├── _quarto.yml              # Site config, navigation, theme
├── index.qmd                # Homepage with module grid
├── about.qmd                # About the program
├── knowledge-checks.qmd     # Interactive quizzes
├── modules/
│   ├── 01-citation-management.qmd
│   ├── 02-scholarly-communication.qmd
│   ├── 03-data-management.qmd
│   ├── 04-literature-review.qmd
│   ├── 05-publish-share.qmd
│   ├── 06-graduate-academic-affairs.qmd
│   └── 07-capstone.qmd
├── assets/
│   └── custom.scss          # UCR Blue/Gold theme + module cards
├── images/                  # Course images from original export
│   ├── certificate-thumbnail.jpg
│   ├── image-2.png          # Open Access types diagram
│   └── image-4.png          # UC OA Policy coverage
├── docs/                    # Rendered output (GitHub Pages serves this)
└── .github/
    └── workflows/
        └── publish.yml      # Auto-deploy on push to main
```

---

## ✏️ Customizing Content

### Add or Edit a Module

Open any `.qmd` file in `modules/` and edit in plain Markdown + Quarto syntax. To add a new module:

1. Create `modules/08-new-topic.qmd`
2. Add it to the navbar in `_quarto.yml` under `website > navbar > left > menu`

### Change Branding Colors

Edit `assets/custom.scss`:
```scss
$primary: #003DA5;   // UCR Blue → change to your institution's color
$secondary: #FFB81C; // UCR Gold
```

### Update Contact Info

Search for `jingh@ucr.edu` across `.qmd` files to find and update librarian contact details.

---

## 📦 Updating from Canvas

If you export a new version of the Canvas course:

```bash
# Unzip the .imscc (it's a ZIP file)
unzip new-export.imscc -d course_extract/

# Key files to check for updates:
# - course_extract/course_settings/module_meta.xml  (module structure)
# - course_extract/wiki_content/*.html               (page content)
# - course_extract/non_cc_assessments/*.qti          (quiz questions)
```

---

## 📄 License

Course content © UC Riverside Library. Site template and code: [MIT License](LICENSE).

---

## 🙏 Acknowledgments

Original course developed in Canvas LMS by UCR Library. Converted to Quarto static site for open, accessible self-paced delivery.

Built with:
- [Quarto](https://quarto.org) — open source scientific publishing system
- [Bootstrap/Flatly](https://bootswatch.com/flatly/) — CSS framework
- [GitHub Pages](https://pages.github.com) — free static site hosting
