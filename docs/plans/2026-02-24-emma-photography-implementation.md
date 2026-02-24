# Emma Photography Site — Implementation Plan

> **For Claude:** REQUIRED SUB-SKILL: Use superpowers:executing-plans to implement this plan task-by-task.

**Goal:** Transform the existing static HTML template into Emma's freelance photography portfolio site with updated sections, Formspree contact form, and social media links.

**Architecture:** Single-page static HTML/CSS/JS site. Modify `index.html` in-place, add minimal CSS to `css/style.css` for the new Reviews section. No build tools, no framework changes.

**Tech Stack:** HTML5, CSS3, Bootstrap 3, jQuery 1.11, Isotope, FancyBox, WOW.js, Formspree

---

### Task 1: Add .gitignore and update page metadata

**Files:**
- Create: `.gitignore`
- Modify: `index.html:1-20` (head section)

**Step 1: Create .gitignore**

```
# OS files
.DS_Store
Thumbs.db

# Editor files
*.swp
*.swo
*~
.vscode/
.idea/
```

**Step 2: Update the `<head>` section of index.html**

Change the `<title>` tag (line 5) from:
```html
<title>Amaze Photography Bootstrap HTML5 Template | Webthemez</title>
```
to:
```html
<title>Emma Photography | Freelance Photographer</title>
```

**Step 3: Verify in browser**

Open `index.html` in browser. Confirm the browser tab shows "Emma Photography | Freelance Photographer".

**Step 4: Commit**

```bash
git add .gitignore index.html
git commit -m "chore: add .gitignore and update page title"
```

---

### Task 2: Update navigation links

**Files:**
- Modify: `index.html:51-73` (header/nav section)

**Step 1: Update nav items**

Replace the `<ul>` inside `#mainNav` (lines 61-68):

```html
<ul class="nav navbar-nav" id="mainNav">
  <li class="active"><a href="#carousel" class="scroll-link">Home</a></li>
  <li><a href="#aboutUs" class="scroll-link">About Me</a></li>
  <li><a href="#service" class="scroll-link">Experience</a></li>
  <li><a href="#Portfolio" class="scroll-link">Portfolio</a></li>
  <li><a href="#reviews" class="scroll-link">Reviews</a></li>
  <li><a href="#contact" class="scroll-link">Contact</a></li>
</ul>
```

Changes: "My Skills" becomes "Experience", "Awards" becomes "Reviews" (pointing to new `#reviews` section ID).

**Step 2: Update logo area**

Replace the commented-out logo div (line 55) with:
```html
<div class="logo"><a href="#">Emma Photography</a></div>
```

**Step 3: Verify in browser**

Open `index.html`. Confirm nav shows: Home | About Me | Experience | Portfolio | Reviews | Contact. The "Reviews" link won't scroll to the right place yet (that section doesn't exist yet) — that's expected.

**Step 4: Commit**

```bash
git add index.html
git commit -m "feat: update navigation to match Emma's site sections"
```

---

### Task 3: Update hero carousel text

**Files:**
- Modify: `index.html:22-49` (carousel section)

**Step 1: Update carousel slide captions**

Replace the three slide caption `<h2>` elements with Emma-appropriate placeholder taglines:

Slide 1 (line 32):
```html
<h2>EMMA PHOTOGRAPHY<br/><strong>Capturing Your Story</strong></h2>
```

Slide 2 (line 38):
```html
<h2>MOMENTS<br/><strong>That Last a Lifetime</strong></h2>
```

Slide 3 (line 43):
```html
<h2>YOUR VISION<br/><strong>Brought to Life</strong></h2>
```

**Step 2: Verify in browser**

Open `index.html`. Confirm the carousel cycles through the three new taglines. Images remain as placeholders.

**Step 3: Commit**

```bash
git add index.html
git commit -m "feat: update hero carousel taglines for Emma"
```

---

### Task 4: Update About Me section

**Files:**
- Modify: `index.html:76-102` (aboutUs section)

**Step 1: Replace the About Me section content**

Replace lines 76-102 with:

```html
<section id="aboutUs"><!--Aboutus-->
<div class="inner_wrapper about-us aboutUs-container fadeInLeft animated wow">
  <div class="container">
    <h2>About Me</h2>
    <h6>Freelance photographer with a passion for capturing life's moments</h6>
    <div class="inner_section">
      <div class="row">
        <div class="col-md-6"> <img class="img-responsive" src="img/about1.png" align=""> </div>
        <div class="col-md-6">
          <h3>Hi, I'm Emma</h3>
          <p>I'm a freelance photographer who loves capturing the beauty in everyday moments. From weddings and engagements to corporate events, product shoots, and family portraits — I bring a creative eye and a warm approach to every session.</p>
          <p>My goal is to make every client feel comfortable and natural in front of the camera, so the photos tell your real story. Whether it's your big day, a family milestone, or a professional headshot, I'm here to create images you'll treasure.</p>
          <ul class="about-us-list">
            <li class="points">Available for weddings, events, portraits, and commercial work</li>
            <li class="points">Serving the local area and available for travel</li>
            <li class="points">Flexible packages tailored to your needs</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</div>
</section>
<!--Aboutus-->
```

**Step 2: Verify in browser**

Open `index.html`. Scroll to About Me. Confirm placeholder image is on the left, bio text on the right with bullet points. Animation should still trigger on scroll.

**Step 3: Commit**

```bash
git add index.html
git commit -m "feat: update About Me section with Emma's placeholder bio"
```

---

### Task 5: Update Experience section (from Skills)

**Files:**
- Modify: `index.html:106-148` (service section)
- Modify: `css/style.css` (add style for 3-column grid)

**Step 1: Replace the Skills section content in index.html**

Replace lines 106-148 with 6 experience cards in 2 rows of 3:

```html
<!--Experience-->
<section id="service">
  <div class="container">
    <h2>Experience</h2>
    <h6>Specializing in a wide range of photography services</h6>
    <div class="service_wrapper">
      <div class="row">
        <div class="col-md-4">
          <div class="service_icon delay-03s animated wow zoomIn"> <span><i class="fa fa-heart"></i></span> </div>
          <div class="service_block">
            <h3 class="animated fadeInUp wow">Weddings & Engagements</h3>
            <p class="animated fadeInDown wow">From intimate ceremonies to grand celebrations, I capture every meaningful moment of your special day.</p>
          </div>
        </div>
        <div class="col-md-4">
          <div class="service_icon icon2 delay-03s animated wow zoomIn"> <span><i class="fa fa-users"></i></span> </div>
          <div class="service_block">
            <h3 class="animated fadeInUp wow">Portraits & Family</h3>
            <p class="animated fadeInDown wow">Natural, relaxed portraits that showcase your personality — from family sessions to senior photos.</p>
          </div>
        </div>
        <div class="col-md-4">
          <div class="service_icon icon3 delay-03s animated wow zoomIn"> <span><i class="fa fa-building-o"></i></span> </div>
          <div class="service_block">
            <h3 class="animated fadeInUp wow">Corporate Events</h3>
            <p class="animated fadeInDown wow">Professional event coverage for conferences, galas, team gatherings, and corporate milestones.</p>
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-md-4">
          <div class="service_icon delay-03s animated wow zoomIn"> <span><i class="fa fa-shopping-bag"></i></span> </div>
          <div class="service_block">
            <h3 class="animated fadeInUp wow">Product & Food</h3>
            <p class="animated fadeInDown wow">Eye-catching product and food photography for retail brands, restaurants, and online shops.</p>
          </div>
        </div>
        <div class="col-md-4">
          <div class="service_icon icon2 delay-03s animated wow zoomIn"> <span><i class="fa fa-paw"></i></span> </div>
          <div class="service_block">
            <h3 class="animated fadeInUp wow">Animals & Pets</h3>
            <p class="animated fadeInDown wow">Fun, lively pet portraits that capture the unique personality of your furry family members.</p>
          </div>
        </div>
        <div class="col-md-4">
          <div class="service_icon icon3 delay-03s animated wow zoomIn"> <span><i class="fa fa-user"></i></span> </div>
          <div class="service_block">
            <h3 class="animated fadeInUp wow">Headshots</h3>
            <p class="animated fadeInDown wow">Polished, professional headshots for LinkedIn, corporate bios, acting portfolios, and personal branding.</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
<!--Experience-->
```

Key changes: `col-md-3` (4 columns) becomes `col-md-4` (3 columns), 6 cards across 2 rows, Font Awesome icons matched to each category.

**Step 2: Verify in browser**

Open `index.html`. Scroll to Experience. Confirm 6 cards in 2 rows of 3, each with an icon, title, and description. Animations should still work.

**Step 3: Commit**

```bash
git add index.html
git commit -m "feat: replace Skills with 6-category Experience section"
```

---

### Task 6: Update Portfolio section filters and items

**Files:**
- Modify: `index.html:151-325` (Portfolio section)

**Step 1: Replace the portfolio filter buttons and items**

Replace the filter buttons (lines 173-191) with:

```html
<div id="filters" class="sixteen columns">
  <ul class="clearfix">
    <li><a id="all" href="#" data-filter="*" class="active"><h5>All</h5></a></li>
    <li><a class="" href="#" data-filter=".weddings"><h5>Weddings</h5></a></li>
    <li><a class="" href="#" data-filter=".portraits"><h5>Portraits</h5></a></li>
    <li><a class="" href="#" data-filter=".events"><h5>Events</h5></a></li>
    <li><a class="" href="#" data-filter=".products"><h5>Products</h5></a></li>
    <li><a class="" href="#" data-filter=".animals"><h5>Animals</h5></a></li>
    <li><a class="" href="#" data-filter=".headshots"><h5>Headshots</h5></a></li>
  </ul>
</div>
```

Replace the portfolio items (lines 195-308) with 8 items using the new categories. Each item uses existing placeholder images but with updated captions and category classes:

```html
<div class="isotope fadeInLeft animated wow grid" style="position: relative; overflow: hidden; height: 480px;" id="portfolio_wrapper">
  <figure class="portfolio-item one-four weddings isotope-item effect-oscar">
    <div class="portfolio_img"><img src="img/portfolio_pic1.jpg" alt="Wedding Photography"></div>
    <figcaption>
      <div>
        <a href="img/portfolio_pic1.jpg" class="fancybox">
          <h2>Wedding <span>Day</span></h2>
          <p>A beautiful ceremony captured in golden hour light.</p>
        </a>
      </div>
    </figcaption>
  </figure>

  <figure class="portfolio-item one-four portraits isotope-item effect-oscar">
    <div class="portfolio_img"><img src="img/portfolio_pic2.jpg" alt="Portrait Photography"></div>
    <figcaption>
      <div>
        <a href="img/portfolio_pic2.jpg" class="fancybox">
          <h2>Family <span>Portrait</span></h2>
          <p>Relaxed family session at the park.</p>
        </a>
      </div>
    </figcaption>
  </figure>

  <figure class="portfolio-item one-four events isotope-item effect-oscar">
    <div class="portfolio_img"><img src="img/portfolio_pic3.jpg" alt="Event Photography"></div>
    <figcaption>
      <div>
        <a href="img/portfolio_pic3.jpg" class="fancybox">
          <h2>Corporate <span>Gala</span></h2>
          <p>Annual fundraiser event coverage.</p>
        </a>
      </div>
    </figcaption>
  </figure>

  <figure class="portfolio-item one-four products isotope-item effect-oscar">
    <div class="portfolio_img"><img src="img/portfolio_pic4.jpg" alt="Product Photography"></div>
    <figcaption>
      <div>
        <a href="img/portfolio_pic4.jpg" class="fancybox">
          <h2>Product <span>Shoot</span></h2>
          <p>Clean product photography for an online boutique.</p>
        </a>
      </div>
    </figcaption>
  </figure>

  <figure class="portfolio-item one-four animals isotope-item effect-oscar">
    <div class="portfolio_img"><img src="img/portfolio_pic5.jpg" alt="Animal Photography"></div>
    <figcaption>
      <div>
        <a href="img/portfolio_pic5.jpg" class="fancybox">
          <h2>Pet <span>Portrait</span></h2>
          <p>Playful session with a golden retriever.</p>
        </a>
      </div>
    </figcaption>
  </figure>

  <figure class="portfolio-item one-four headshots isotope-item effect-oscar">
    <div class="portfolio_img"><img src="img/portfolio_pic6.jpg" alt="Headshot Photography"></div>
    <figcaption>
      <div>
        <a href="img/portfolio_pic6.jpg" class="fancybox">
          <h2>Professional <span>Headshot</span></h2>
          <p>Corporate headshot for a tech executive.</p>
        </a>
      </div>
    </figcaption>
  </figure>

  <figure class="portfolio-item one-four weddings portraits isotope-item effect-oscar">
    <div class="portfolio_img"><img src="img/portfolio_pic7.jpg" alt="Engagement Photography"></div>
    <figcaption>
      <div>
        <a href="img/portfolio_pic7.jpg" class="fancybox">
          <h2>Engagement <span>Session</span></h2>
          <p>Sunset engagement photos at the vineyard.</p>
        </a>
      </div>
    </figcaption>
  </figure>

  <figure class="portfolio-item one-four products events isotope-item effect-oscar">
    <div class="portfolio_img"><img src="img/portfolio_pic8.jpg" alt="Food Photography"></div>
    <figcaption>
      <div>
        <a href="img/portfolio_pic8.jpg" class="fancybox">
          <h2>Food <span>Photography</span></h2>
          <p>Menu photography for a local restaurant.</p>
        </a>
      </div>
    </figcaption>
  </figure>
</div>
```

Also update the section subtitle (line 160):
```html
<h6>A selection of my recent work across all photography services</h6>
```

**Step 2: Verify in browser**

Open `index.html`. Scroll to Portfolio. Confirm:
- 7 filter buttons: All, Weddings, Portraits, Events, Products, Animals, Headshots
- Clicking each filter shows only matching items
- Items with multiple categories (e.g. pic7 has `weddings portraits`) show up under both filters
- Lightbox opens when clicking an item
- Responsive grid still works

**Step 3: Commit**

```bash
git add index.html
git commit -m "feat: update portfolio filters and items to match Emma's categories"
```

---

### Task 7: Replace Awards/Timeline with Reviews section

**Files:**
- Modify: `index.html:327-399` (experience/awards section)
- Modify: `css/style.css` (add reviews carousel styles)

**Step 1: Replace the Awards section HTML**

Replace lines 327-399 with:

```html
<section id="reviews">
  <div class="container">
    <div class="section-title">
      <h2>What Clients Say</h2>
      <h6>Hear from some of the wonderful people I've worked with</h6>
    </div>
    <div class="row">
      <div class="col-md-8 col-md-offset-2">
        <div id="reviewCarousel" class="carousel slide" data-ride="carousel" data-interval="6000">
          <ol class="carousel-indicators review-indicators">
            <li data-target="#reviewCarousel" data-slide-to="0" class="active"></li>
            <li data-target="#reviewCarousel" data-slide-to="1"></li>
            <li data-target="#reviewCarousel" data-slide-to="2"></li>
          </ol>
          <div class="carousel-inner review-carousel-inner">
            <div class="item active">
              <div class="review-item">
                <i class="fa fa-quote-left review-quote-icon"></i>
                <p class="review-text">Emma captured our wedding day perfectly. Every emotion, every detail — she has an incredible eye for the moments that matter most. We couldn't be happier with our photos!</p>
                <h4 class="review-author">Sarah & James</h4>
                <span class="review-detail">Wedding, September 2025</span>
              </div>
            </div>
            <div class="item">
              <div class="review-item">
                <i class="fa fa-quote-left review-quote-icon"></i>
                <p class="review-text">We hired Emma for our family portraits and she was amazing with our kids. She made the whole session fun and relaxed, and the photos turned out beautifully.</p>
                <h4 class="review-author">The Martinez Family</h4>
                <span class="review-detail">Family Portrait, July 2025</span>
              </div>
            </div>
            <div class="item">
              <div class="review-item">
                <i class="fa fa-quote-left review-quote-icon"></i>
                <p class="review-text">Emma did our corporate headshots and event photography for our annual conference. Professional, efficient, and the results exceeded our expectations.</p>
                <h4 class="review-author">David Chen</h4>
                <span class="review-detail">Corporate Event, November 2025</span>
              </div>
            </div>
          </div>
          <a class="left carousel-control review-control" href="#reviewCarousel" data-slide="prev">
            <span class="fa fa-chevron-left"></span>
          </a>
          <a class="right carousel-control review-control" href="#reviewCarousel" data-slide="next">
            <span class="fa fa-chevron-right"></span>
          </a>
        </div>
      </div>
    </div>
  </div>
</section>
```

**Step 2: Add CSS for the reviews section**

Append to the end of `css/style.css` (before any media queries at the very bottom, or at the end of file):

```css
/* Reviews Section
---------------------------------*/
#reviews {
    padding: 60px 0;
    background: #f9f9f9;
}

#reviews h2 {
    font-size: 38px;
    color: #222222;
    font-family: 'Raleway', sans-serif;
    font-weight: normal;
    text-align: center;
    text-transform: uppercase;
}

#reviews h6 {
    color: #888;
    text-align: center;
    margin-bottom: 40px;
}

.review-item {
    text-align: center;
    padding: 30px 40px 60px;
}

.review-quote-icon {
    font-size: 40px;
    color: #ED5441;
    margin-bottom: 20px;
    display: block;
}

.review-text {
    font-size: 18px;
    line-height: 1.8;
    color: #555;
    font-style: italic;
    margin-bottom: 25px;
}

.review-author {
    font-family: 'Raleway', sans-serif;
    font-weight: 700;
    font-size: 18px;
    color: #222;
    margin-bottom: 5px;
}

.review-detail {
    font-size: 14px;
    color: #999;
}

.review-indicators {
    bottom: 0;
}

.review-indicators li {
    background-color: #ccc;
    border: none;
}

.review-indicators .active {
    background-color: #ED5441;
}

.review-control {
    color: #999;
    background: none !important;
    background-image: none !important;
    width: 40px;
    top: 40%;
}

.review-control:hover {
    color: #ED5441;
}

.review-carousel-inner {
    min-height: 250px;
}
```

**Step 3: Verify in browser**

Open `index.html`. Scroll to the Reviews section (between Portfolio and Contact). Confirm:
- Section heading "What Clients Say" appears
- Testimonial carousel cycles through 3 reviews
- Left/right arrows work to navigate
- Indicator dots show current slide
- Quote icon, text, author name, and session detail all display

**Step 4: Commit**

```bash
git add index.html css/style.css
git commit -m "feat: replace Awards section with client Reviews carousel"
```

---

### Task 8: Update Contact section with Formspree form

**Files:**
- Modify: `index.html:400-449` (footer/contact section)

**Step 1: Replace the contact section HTML**

Replace lines 400-449 with:

```html
<!--Footer-->
<footer class="footer_wrapper" id="contact">
  <div class="container">
    <section class="page_section contact">
      <div class="contact_section">
        <h2>Get In Touch</h2>
        <h6>Have a project in mind? I'd love to hear from you!</h6>
      </div>
      <div class="row">
        <div class="col-lg-4 wow fadeInLeft">
          <div class="contact_info">
            <div class="detail">
              <h4>Emma Photography</h4>
              <p>Freelance Photographer</p>
            </div>
            <div class="detail">
              <h4>Email</h4>
              <p>hello@emma-photography.com</p>
            </div>
          </div>

          <ul class="social_links">
            <li class="instagram animated bounceIn wow delay-02s"><a href="https://instagram.com/" target="_blank" rel="noopener"><i class="fa fa-instagram"></i></a></li>
            <li class="facebook animated bounceIn wow delay-03s"><a href="https://facebook.com/" target="_blank" rel="noopener"><i class="fa fa-facebook"></i></a></li>
            <li class="twitter animated bounceIn wow delay-04s"><a href="https://twitter.com/" target="_blank" rel="noopener"><i class="fa fa-twitter"></i></a></li>
            <li class="pinterest animated bounceIn wow delay-05s"><a href="https://pinterest.com/" target="_blank" rel="noopener"><i class="fa fa-pinterest"></i></a></li>
          </ul>
        </div>
        <div class="col-lg-8 wow fadeInLeft delay-06s">
          <form class="form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
            <div class="row">
              <div class="col-md-6">
                <input class="input-text" type="text" name="name" placeholder="Your Name *" required>
              </div>
              <div class="col-md-6">
                <input class="input-text" type="email" name="email" placeholder="Your Email *" required>
              </div>
            </div>
            <div class="row">
              <div class="col-md-6">
                <input class="input-text" type="tel" name="phone" placeholder="Phone Number">
              </div>
              <div class="col-md-6">
                <select class="input-text" name="event_type">
                  <option value="" disabled selected>Event Type</option>
                  <option value="Wedding">Wedding</option>
                  <option value="Portrait">Portrait</option>
                  <option value="Corporate">Corporate</option>
                  <option value="Product">Product</option>
                  <option value="Animals">Animals</option>
                  <option value="Headshots">Headshots</option>
                  <option value="Other">Other</option>
                </select>
              </div>
            </div>
            <div class="row">
              <div class="col-md-6">
                <input class="input-text" type="date" name="preferred_date" placeholder="Preferred Date">
              </div>
              <div class="col-md-6"></div>
            </div>
            <textarea class="input-text text-area" name="message" placeholder="Tell me about your project *" rows="5" required></textarea>
            <input type="hidden" name="_subject" value="New Inquiry from Emma Photography Site">
            <input class="input-btn" type="submit" value="Send Inquiry">
          </form>
        </div>
      </div>
    </section>
  </div>
  <div class="container">
    <div class="footer_bottom">
      <span>Copyright &copy; 2026 Emma Photography. Template by <a href="http://webthemez.com">WebThemez.com</a>.</span>
    </div>
  </div>
</footer>
```

Key changes:
- Form wrapped in `<form>` tag with Formspree action (placeholder `YOUR_FORM_ID`)
- Proper `name` attributes and `placeholder` instead of `value` + onfocus/onblur hacks
- Added phone, event type dropdown, and preferred date fields
- `required` on name, email, message
- Hidden `_subject` field for Formspree email subject line
- Social links updated: Instagram replaces Google+, all links get `target="_blank"` and `rel="noopener"`
- Contact info updated for Emma
- Copyright updated
- Removed duplicate `id="contact"` from inner section

**Step 2: Add CSS for the select dropdown and date input**

Append to `css/style.css`:

```css
/* Contact Form Enhancements
---------------------------------*/
.form select.input-text {
    height: 45px;
    color: #999;
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    background: url("data:image/svg+xml;charset=utf-8,%3Csvg xmlns='http://www.w3.org/2000/svg' width='12' height='6'%3E%3Cpath d='M0 0l6 6 6-6z' fill='%23999'/%3E%3C/svg%3E") no-repeat right 15px center;
    padding-right: 35px;
    cursor: pointer;
}

.form select.input-text option {
    color: #333;
}

.form input[type="date"].input-text {
    color: #999;
    height: 45px;
}

.form input[type="date"].input-text:valid {
    color: #333;
}
```

**Step 3: Verify in browser**

Open `index.html`. Scroll to Contact section. Confirm:
- Name and email fields on first row
- Phone and event type dropdown on second row
- Preferred date on third row
- Message textarea below
- "Send Inquiry" button
- Social media icons (Instagram, Facebook, Twitter, Pinterest) below contact info
- Form submission goes to Formspree (will show "YOUR_FORM_ID" error — that's expected until the real ID is added)

**Step 4: Commit**

```bash
git add index.html css/style.css
git commit -m "feat: add Formspree inquiry form with event type, date, and social links"
```

---

### Task 9: Clean up stale references and fix JS

**Files:**
- Modify: `js/custom.js:134-141` (broken getElementById at end of file)
- Modify: `index.html` (remove any stale inline styles on portfolio items)

**Step 1: Fix broken JS at end of custom.js**

Remove lines 134-141 from `js/custom.js` — this code references `getElementById('')` with an empty string, which throws an error:

```javascript
// DELETE THIS BLOCK:
document.getElementById('').onclick = function() {
    var section = document.createElement('section');
    section.className = 'wow fadeInDown';
    section.className = 'wow shake';
    section.className = 'wow zoomIn';
    section.className = 'wow lightSpeedIn';
    this.parentNode.insertBefore(section, this);
};
```

**Step 2: Remove hardcoded inline positioning styles from portfolio items**

The portfolio `<figure>` elements have inline `style="position: absolute; left: 0px; top: 0px; transform: translate3d(...)` attributes. These are computed by Isotope at runtime. Remove all inline `style` attributes from the portfolio `<figure>` elements and the `#portfolio_wrapper` div — Isotope will recalculate them on page load.

On `#portfolio_wrapper`, change:
```html
<div class="isotope fadeInLeft animated wow grid" style="position: relative; overflow: hidden; height: 480px;" id="portfolio_wrapper">
```
to:
```html
<div class="isotope fadeInLeft animated wow grid" id="portfolio_wrapper">
```

On each `<figure>`, remove the `style="position: absolute; ..."` attribute. For example:
```html
<figure class="portfolio-item one-four weddings isotope-item effect-oscar">
```
(no style attribute)

**Step 3: Verify in browser**

Open `index.html`. Check browser console for JS errors — should be none. Portfolio grid should still lay out correctly (Isotope handles positioning).

**Step 4: Commit**

```bash
git add js/custom.js index.html
git commit -m "fix: remove broken JS and stale inline styles"
```

---

### Task 10: Final review and cleanup

**Files:**
- Modify: `index.html` (verify all sections flow correctly)

**Step 1: Full page walkthrough in browser**

Open `index.html` and verify each section top to bottom:
1. Hero carousel cycles with Emma's taglines
2. Sticky nav with correct labels: Home, About Me, Experience, Portfolio, Reviews, Contact
3. Clicking each nav item smooth-scrolls to the correct section
4. About Me has placeholder image + bio
5. Experience shows 6 cards in 2 rows of 3
6. Portfolio filters work — each button filters correctly
7. Portfolio lightbox opens on click
8. Reviews carousel cycles through 3 testimonials
9. Contact form has all fields, social links display
10. Footer shows copyright

**Step 2: Test mobile responsiveness**

Open browser dev tools, toggle device toolbar. Check at:
- 375px wide (mobile): hamburger menu works, sections stack vertically
- 768px wide (tablet): 2-column layouts
- 1200px wide (desktop): full layout

**Step 3: Check for any remaining template placeholder text**

Search `index.html` for "Lorem ipsum" — should find zero results. All placeholder text should be Emma-specific.

**Step 4: Commit if any fixes were needed**

```bash
git add -A
git commit -m "chore: final cleanup and verification"
```

---

## Summary

| Task | Description | Files |
|------|-------------|-------|
| 1 | .gitignore + page title | `.gitignore`, `index.html` |
| 2 | Navigation links + logo | `index.html` |
| 3 | Hero carousel taglines | `index.html` |
| 4 | About Me bio | `index.html` |
| 5 | Experience section (6 cards) | `index.html` |
| 6 | Portfolio filters + items | `index.html` |
| 7 | Reviews carousel | `index.html`, `css/style.css` |
| 8 | Formspree contact form + social links | `index.html`, `css/style.css` |
| 9 | JS cleanup + inline style removal | `js/custom.js`, `index.html` |
| 10 | Final review + mobile check | `index.html` |

**After completion:** Replace `YOUR_FORM_ID` in the Formspree action URL with Emma's actual Formspree endpoint. Replace placeholder images with Emma's real photos.
