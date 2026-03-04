# Kaaya Skin & Hair Studio — Elementor Rebuild Guide

This guide helps you recreate the provided one-page design in **WordPress + Elementor** with high visual fidelity.

## 1) Required Stack

- WordPress (latest)
- Elementor Pro (recommended for Theme Builder, Forms, Loop/Grid flexibility)
- Theme: Hello Elementor
- Optional plugins:
  - Premium Addons for Elementor (extra carousel/testimonial widgets)
  - WPForms/Fluent Forms (if not using Elementor Form)
  - Smush or Imagify (image optimization)
  - LiteSpeed Cache / WP Rocket (performance)

## 2) Global Site Setup (Do this first)

In **Elementor → Site Settings**:

### Global Colors
Use a palette close to the screenshot:

- `Primary Dark`: `#1F1F1F`
- `Accent Brown`: `#A66A3E`
- `Warm Beige`: `#E7D0BF`
- `Light Background`: `#F7F3EF`
- `White`: `#FFFFFF`

### Global Fonts
Suggested match:

- Headings: `Playfair Display` (or Cormorant Garamond)
- Body/UI: `Poppins` or `Lato`

Suggested sizes:

- H1: 56 / 1.1 line-height
- H2: 44 / 1.2
- H3: 30 / 1.2
- Body: 16 / 1.7
- Small UI text: 13–14

### Container Widths
- Main content max width: `1200px`
- Hero section: full-width
- Section vertical spacing: `80–110px`

## 3) Header (Sticky, Transparent over Hero)

Create in **Theme Builder → Header**.

### Structure
- One container (full width), with inner container max width 1200.
- Left: logo image + brand text lockup.
- Center/right: nav menu (`HOME`, `ABOUT US`, `OUR SERVICES`, `GALLERY`, `CONTACT US`).
- Rightmost CTAs/social: tiny social buttons + `BOOK APPOINTMENT` button.

### Style
- Initial state: translucent white (`rgba(255,255,255,0.8)`) over hero.
- Sticky state: solid white + subtle shadow.
- Menu item typography: uppercase, 12–13px, letter spacing 0.5.

## 4) Page Sections (Top to Bottom)

Create one Elementor page using full-width containers.

## Section A — Hero Banner with Overlay Card

- Full-width background image (spa treatment image).
- Height: 650–760px desktop.
- Dark overlay: 20–30%.
- Left overlay card:
  - Heading: “Advanced Skin Care & Rejuvenation”
  - Body paragraph
  - Button: `Book Appointment Today`
- Add subtle arrow nav icons if using a slider.

**Widget suggestions:**
- Container with background + Overlay
- Heading + Text Editor + Button
- Optional Slides widget if you want a carousel

## Section B — Services Intro Grid (3 cards)

Background color: warm beige (`#E7D0BF`).

- Small badge text: “Our Services”
- Heading centered: “Premium Skin, Hair & Waxing Services in London, Ontario”
- Three equal cards with rounded corners (16–20px):
  - Skin Care Treatments
  - Hair Care Services
  - Waxing Services

Card style:
- Image ratio roughly 4:5
- Title centered under image
- Hover: lift (`translateY(-6px)`), slight shadow

## Section C — About Studio Split Layout

Background: white with faint curved decorative lines (as background SVG/png).

- Left column: large rounded image.
- Right column:
  - Eyebrow badge label
  - H2 title
  - Intro paragraph
  - Bullet list with minimalist icons/check marks
  - CTA button (`MORE ABOUT US`)
  - Founder mini profile row (avatar + name + subtitle)

## Section D — Dark CTA Strip

- Short horizontal strip with dark background image overlay.
- Text: “Book Your Consultation Today” + brief subtext.
- Right-aligned button: `SCHEDULE CONSULTATION`.

## Section E — Why Choose Us (Text + Image)

Background: light beige.

- Left: heading + descriptive paragraph + bullet points.
- Right: rounded image.
- Add botanical/leaf decoration at section bottom to mimic screenshot.

## Section F — Before & After Gallery

Background: light gray (`#EFEFEF`).

- Badge: “Portfolio”
- Heading: “BEFORE & AFTER Gallery”
- Subtitle text centered
- Row of 5–6 narrow before/after images
- CTA button: `VIEW ALL RESULTS`

Use either:
- Image Gallery widget with custom CSS for equal heights, or
- Loop Grid with custom post type `portfolio`

## Section G — Reviews Block

Background: warm beige.

- Badge: “Reviews”
- Heading: “What Our Clients Say”
- 3 testimonial cards in a row
- Each card: icon row, excerpt text, author avatar/name/date

Use Elementor Testimonial Carousel set to 3 columns on desktop.

## Section H — Appointment Form + Contact Details

Background image darkened.

- Left column:
  - Badge: “Trusted Beauty Experts”
  - Heading: “Book Your Skin & Hair Specialist Appointment”
  - Short process steps list
  - Opening hours block
- Right column (white rounded card):
  - Name, Email, Phone, Date, Treatment, Service, Message, Captcha, Submit

Use Elementor Pro Form widget; enable required validation and email notifications.

## Section I — Footer

Background: very dark with subtle texture.

4-column layout:
1. Brand summary + social buttons
2. Quick Links
3. Our Services list
4. Contact details

Bottom bar: copyright line.

## 5) Reusable Style Rules (Custom CSS)

Add in **Site Settings → Custom CSS** (or page-level where needed):

```css
/* Shared section spacing */
.section-pad { padding: 90px 0; }

/* Rounded image cards */
.rounded-media img {
  border-radius: 18px;
  display: block;
}

/* Soft card hover */
.hover-lift {
  transition: transform .25s ease, box-shadow .25s ease;
}
.hover-lift:hover {
  transform: translateY(-6px);
  box-shadow: 0 14px 30px rgba(0,0,0,.12);
}

/* Pill badge */
.pill-badge {
  display: inline-block;
  border: 1px solid #c8a58a;
  color: #8f5d39;
  border-radius: 999px;
  padding: 4px 12px;
  font-size: 12px;
  letter-spacing: .4px;
  background: #fff7f0;
}

/* Primary CTA */
.btn-brown .elementor-button {
  background: #a66a3e;
  border-radius: 999px;
  padding: 12px 22px;
}
```

## 6) Responsive Settings

### Tablet
- Reduce section padding to 70px.
- Hero title to ~42px.
- Services cards become 2 + 1 layout.

### Mobile
- Stack all split sections to single column.
- Hero height 520–580px.
- H1 around 32px.
- Keep form fields full width.
- Footer becomes single-column or accordion style.

## 7) Content/Asset Checklist

Prepare before building:

- High-res hero and section images (WebP preferred)
- Real service names and pricing pages
- Contact details, map URL, opening hours
- Social profile links
- Real testimonials (with consent)

## 8) Performance + SEO Basics

- Compress images and serve next-gen formats.
- Use caching + minification plugin.
- Add alt text to every image.
- Set one H1 on page, logical H2/H3 structure.
- Add LocalBusiness schema (plugin or custom JSON-LD).
- Connect form to SMTP (WP Mail SMTP) for reliable email delivery.

## 9) Build Order (Fastest Workflow)

1. Configure global colors/fonts.
2. Build Header and Footer in Theme Builder.
3. Build sections A→I on homepage with placeholder content.
4. Apply shared classes (`section-pad`, `hover-lift`, `pill-badge`, `btn-brown`).
5. Tune responsive breakpoints.
6. Replace placeholders with final media/text.
7. Optimize performance, then QA.

## 10) Final QA Checklist

- Header sticky behavior works on desktop/mobile.
- Buttons and form submit correctly.
- All sections visually match spacing/alignment from reference.
- No layout shifts; images sized consistently.
- Lighthouse mobile performance is acceptable.

---

If you want, I can generate a **ready-to-import Elementor JSON template structure** (containers + widgets + classes) so you can import and only replace images/text.

## 11) Ready-to-Import Template File Included

A starter Elementor JSON template has been added in this repo:

- `elementor-home-template.json`

### Import steps
1. In WordPress admin go to **Templates → Saved Templates**.
2. Click **Import Templates**.
3. Upload `elementor-home-template.json`.
4. Open your homepage with Elementor and insert the imported template.
5. Replace placeholder images/text and assign real links, menus, and form actions.

> Note: this template is a structural starter matching the screenshot layout order and spacing system. You should replace demo assets and fine-tune widget-level styling per your brand content.

## 12) Visual Preview Mockup (Included)

To help you quickly see the expected layout before importing into Elementor, a static preview file is included:

- `elementor-look-preview.html`

You can open it in any browser to view the section flow and style direction (hero, services, about, CTA strip, portfolio, reviews, booking form, and footer).

## 13) How to Download and Share a Downloadable Link

If you want to send your Elementor starter files (`elementor-home-template.json`, preview HTML, images, etc.) to someone else, use one of these methods.

### Option A — Share from WordPress Media Library (best for clients)
1. In WordPress admin, go to **Media → Add New**.
2. Upload the file (for example: `elementor-home-template.json` or a ZIP package).
3. Click the uploaded file and copy the **File URL** from the right panel.
4. Share that URL.

Example format:
`https://yourdomain.com/wp-content/uploads/2026/03/kaaya-elementor-pack.zip`

### Option B — Create one ZIP and share (recommended)
Package all required files first:

```bash
zip -r kaaya-elementor-pack.zip elementor-home-template.json elementor-look-preview.html elementor-rebuild-guide.md
```

Then upload the ZIP to:
- WordPress Media Library, or
- Google Drive / Dropbox / OneDrive

Set access to **Anyone with the link** and share.

### Option C — Send directly from hosting (cPanel / File Manager)
1. Upload ZIP to `public_html/downloads/`.
2. Share direct URL:
   `https://yourdomain.com/downloads/kaaya-elementor-pack.zip`
3. (Optional) Protect with password or expiry using your host tools.

### Important
- If sharing publicly, avoid exposing private credentials or client data in files.
- If you update the template later, either overwrite the same URL or version files (e.g., `kaaya-elementor-pack-v2.zip`).
