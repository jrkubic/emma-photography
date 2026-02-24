# Emma Photography Site — Design Document

## Overview

Transform the existing static HTML/CSS/JS photography portfolio template into Emma's freelance photography website. The site showcases her work, lists her services, displays client testimonials, and provides an inquiry form for potential clients.

**Approach:** Modify the existing template in-place. No framework changes, no build tools. Keep Bootstrap 3 + jQuery stack as-is for MVP.

**Hosting:** GitHub Pages (project site). Custom domain (www.emma-photography) to be configured later.

## Site Structure

Single-page site with smooth-scroll navigation. Sections in order:

1. **Hero Carousel** — Full-width image slider
2. **About Me** — Bio and headshot
3. **Experience** — Photography service categories
4. **Portfolio** — Filterable image gallery with lightbox
5. **Reviews** — Client testimonial carousel
6. **Contact** — Inquiry form (Formspree) + social media links

**Navigation bar:** Home | About Me | Experience | Portfolio | Reviews | Contact

Sticky black header with logo/brand name on the left, nav links on the right. Footer with social media icons and copyright.

## Section Details

### Hero Carousel

Keep the existing full-width Bootstrap carousel with fade transitions. Placeholder images stay until Emma provides her photos. Update overlay text with a placeholder tagline (e.g. "Capturing Your Story"). Keep carousel indicators and auto-advance.

### About Me

Two-column layout: image on one side, text on the other. Placeholder headshot and bio text. Remove any progress bars or counters from the template. Keep scroll-triggered fade-in animation.

### Experience (repurposed from Skills)

Section heading: "Experience". Grid of cards, each with a Font Awesome icon, category name, and short description.

Categories (6 cards, 2 rows of 3):
- Weddings & Engagements
- Portraits & Family
- Corporate Events
- Product & Food
- Animals & Pets
- Headshots

### Portfolio

Isotope masonry grid with filtering and FancyBox lightbox. Existing functionality stays.

Filter buttons: All | Weddings | Portraits | Events | Products | Animals | Headshots

Each item has: photo thumbnail, category tag(s) for filtering, hover overlay with caption, click-to-lightbox. Items can belong to multiple categories. Keep responsive column reflow (4 desktop, 2 tablet, 1 mobile). Placeholder images until Emma provides real photos.

### Reviews (replaces Awards/Timeline)

Testimonial carousel using Bootstrap carousel component. Each slide shows: quote text, client name, session type (e.g. "Wedding, June 2025"). Placeholder testimonials for now.

### Contact (Formspree Inquiry Form)

Form fields:
- Name (required)
- Email (required)
- Phone (optional)
- Event type dropdown: Wedding, Portrait, Corporate, Product, Animals, Headshots, Other
- Preferred date (date picker, optional)
- Message / details (textarea, required)

Form submits via Formspree (POST). Placeholder action URL until Formspree endpoint is configured. Social media icon links (Instagram, Facebook, etc.) displayed below or beside the form using Font Awesome icons.

## Styling

Keep existing template styling for MVP. No color palette or typography changes. Future iteration may update to a warm editorial aesthetic (serif headings, warm gold accents, cream backgrounds).

## Technical Notes

- Static HTML/CSS/JS — no build step
- Bootstrap 3 + jQuery 1.11 + existing plugins (Isotope, FancyBox, WOW.js)
- Formspree for contact form (no backend needed)
- GitHub Pages deployment
- All content is placeholder — Emma will provide real photos, bio, testimonials
