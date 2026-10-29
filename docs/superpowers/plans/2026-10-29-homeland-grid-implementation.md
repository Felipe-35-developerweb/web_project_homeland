# Projeto 6 — De Pátria para Pátria Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Expand the existing Homeland page with the photo grid, places, cover and responsive layouts shown in the Sprint 6 Figma design.

**Architecture:** Keep the existing BEM Flat structure. Add semantic HTML sections in `main`; each visual block receives styles only in its corresponding file under `blocks`. The same DOM adapts through CSS Grid and media queries at 1024px and 544px.

**Tech Stack:** HTML5, CSS3, CSS Grid, Flexbox, BEM Flat, Git and GitHub Pages.

**Spec:** `docs/superpowers/specs/2026-10-29-homeland-grid-design.md`

## Global Constraints

- Preserve the existing `header`, `lead`, `intro` and `footer`.
- Use CSS Grid for both `photo-grid` and `places`.
- Use local images only from `images/`; every image requires Portuguese `alt` text.
- Follow the Figma at 1280px, 768px and 320px without horizontal scrolling.
- Keep BEM class names and one CSS file per block; do not use `!important`, negative margins or fixed heights for text.
- Keep `normalize.css` first and `fonts.css` second in `pages/index.css`.

## Review Focus

- Check that each image `src` points to an existing local file and each `alt` describes that image in Portuguese.
- Check that `photo-grid` and `places` use `display: grid`, not Flexbox.
- Check that every new link has a valid `href` and a visible `:hover` state.
- Check 1280px, 768px and 320px for overflow or clipped text.
- Check that the page order remains: lead, intro, photo-grid, places, cover, footer.

---

### Task 1: Map and add the local image assets

**Files:**
- Create: descriptive image files in `images/`
- Modify: `index.html`

**Interfaces:**
- Consumes: exported images from the imported Sprint 6 Figma file.
- Produces: stable local paths used by all later `<img>` elements and the cover background.

- [ ] Export each image from the Figma design and save it in `images/` with a descriptive lowercase name.
- [ ] Add the `photo-grid` section after `intro`, using an unordered list with `photo-grid__item` and `photo-grid__image` classes.
- [ ] Confirm every new image has a meaningful Portuguese `alt` and a local relative `src`.
- [ ] Preview with Live Server at 1280px; images must load with no broken-image icon.
- [ ] Commit: `git add images index.html && git commit -m "Adicionar imagens e grade de fotos"`.

### Task 2: Build the responsive photo grid

**Files:**
- Modify: `blocks/photo-grid.css`

**Interfaces:**
- Consumes: `.photo-grid`, `.photo-grid__item` and `.photo-grid__image` from Task 1.
- Produces: a responsive CSS Grid photo layout.

- [ ] Add the desktop grid layout and spacing from the Figma.
- [ ] Add only the differing tablet and mobile grid rules in media queries.
- [ ] Test at 1280px, 768px and 320px; confirm no image overflows horizontally.
- [ ] Commit: `git add blocks/photo-grid.css && git commit -m "Estilizar grade de fotos"`.

### Task 3: Add the places articles

**Files:**
- Modify: `index.html`

**Interfaces:**
- Consumes: local city photos from Task 1 and BEM class names `places` and `place`.
- Produces: one semantic `<article class="place">` per location in the order defined by Figma.

- [ ] Add `<section class="places">` after `photo-grid`.
- [ ] Add each place as an article with title, artist/byline, descriptive paragraphs, link and image exactly in Figma order.
- [ ] Give every link an `href` and every photo a Portuguese `alt`.
- [ ] Preview the section at 1280px and confirm article order matches the design.
- [ ] Commit: `git add index.html && git commit -m "Adicionar seções de lugares"`.

### Task 4: Style the places layout with CSS Grid

**Files:**
- Modify: `blocks/places.css`
- Modify: `blocks/place.css`

**Interfaces:**
- Consumes: `.places` and `.place` article markup from Task 3.
- Produces: two-column desktop articles that reflow to the Figma tablet and mobile arrangements.

- [ ] Use Grid to position the text and city image in each desktop article.
- [ ] Use element and modifier classes only for intentional place variants.
- [ ] Add responsive rules at 1024px and 544px without duplicating unchanged desktop declarations.
- [ ] Test all three target widths; text must not overlap or leave the image outside its block.
- [ ] Commit: `git add blocks/places.css blocks/place.css && git commit -m "Estilizar seções de lugares"`.

### Task 5: Add and style the final cover section

**Files:**
- Modify: `index.html`
- Modify: `blocks/cover.css`

**Interfaces:**
- Consumes: the selected local cover image and existing `footer`.
- Produces: an accessible, clickable `cover` section before the footer.

- [ ] Add the `cover` section after `places` and before `footer`.
- [ ] Use an anchor for the full clickable overlay, with its hover state in `cover.css`.
- [ ] Match the cover title, overlay and image crop in the three Figma layouts.
- [ ] Commit: `git add index.html blocks/cover.css && git commit -m "Adicionar seção de capa"`.

### Task 6: Final responsive review and delivery

**Files:**
- Modify as needed: `blocks/*.css`, `README.md`

**Interfaces:**
- Consumes: all completed sections and existing GitHub Pages deployment.
- Produces: a clean, documented, deployed Sprint 6 project.

- [ ] Check 1280px, 768px and 320px with the browser device toolbar.
- [ ] Run the W3C HTML and CSS validators; correct any real validation errors.
- [ ] Confirm `README.md` still includes name, description, technologies and the GitHub Pages link.
- [ ] Run `git status`, commit remaining changes and `git push`.
- [ ] Open GitHub Pages and confirm that the deployed page includes the new sections.
