# MM Content Migration Brief — May 2026

## Summary

Migrated real WP staging copy to all static HTML pages. Applied on `main` branch, 2026-05-01.

## Pages Updated

### index.html
- Hero CTA 2 link updated to `/case-studies/` (label: "View case studies")
- Case study BB Garage badge corrected: `800%+ ROAS` (was 850%)
- Case study Busselton badge corrected: `Under $30 CPL` (was $29 CPL)
- Final CTA subhead updated; added second CTA button linking to `/pricing.html`
- Footer updated to 4-column layout: Brand / Services / Industries / Resources
- Footer tagline: "Built for the pit lane." / Copyright: "© 2026 Mechanic Marketing. All rights reserved."
- **Preserved:** ticker bar values (5000 / $38 / 3× / 100% Transparency), How It Works section

### about.html
- Full rewrite: new hero (eyebrow, H1 "WE'RE IN YOUR CORNER", body, CTA)
- Team section: Josh + Teddi cards with photo placeholders (`team-photo-placeholder` class)
- Testimonial: Bodie Geck quote
- 2-up case study mini grid: BB Garage + Accelerate Automotive
- CTA section: "Ready to grow?"
- Updated 4-column footer

### pricing.html
- Full rewrite: hero ("Simple pricing"), pricing cards (Ignite $1,500/m, Accelerate $2,500/m)
- Comparison table (id: what-is-included) with col-mm and check-mm classes
- Testimonial: Bodie Geck quote
- FAQ accordion (4 items, first open by default)
- Updated 4-column footer

### contact.html
- Full rewrite: hero ("Need more cars in your workshop?")
- Left column: trust signals, Calendly placeholder, email
- Right column: contact form (id: contact-form, action: __CONTACT_FORM_ENDPOINT__)
- Form fields: Full Name, Email, Phone, Workshop Name, Website URL, Monthly Revenue (select), Message
- FAQ section (5 items)
- Updated 4-column footer

### case-studies/index.html
- H1: "REAL RESULTS FOR REAL WORKSHOPS"
- 4 case study cards with updated stats, types, descriptions
- Testimonial: Bodie Geck (alternate quote)
- Final CTA with two buttons: Book a Call + View Pricing
- Updated 4-column footer

### case-studies/bb-garage.html
- Eyebrow: DIESEL WORKSHOP · CASE STUDY
- H1: BB GARAGE / Stat: 800%+ ROAS
- Full Background / Challenge / What We Did / Results copy
- Sidebar stats: 800%+, Best month, 100% tracked

### case-studies/accelerate-automotive.html
- Eyebrow: GENERAL REPAIRER · CASE STUDY
- H1: ACCELERATE AUTOMOTIVE / Stat: 312 LEADS
- Full copy

### case-studies/busselton-automotive.html
- Eyebrow: SUSPENSION SPECIALIST · CASE STUDY
- H1: BUSSELTON AUTOMOTIVE / Stat: Under $30 CPL
- Full copy

### case-studies/core-diesel.html
- Eyebrow: PERFORMANCE SHOP · CASE STUDY
- H1: CORE DIESEL / Stat: 2,147 LEADS
- Full copy

### services/google-ads.html
- H1: "Ads That Drive Results, Not Just Traffic"
- H2: "Google Ads Management for Auto Repair Shops"
- Pain paragraph + 3 feature cards + bottom CTA strip "QUIET BAYS?"

### services/seo.html
- H1: "Get Found First When Locals Search for Repairs"
- H2: "Expert Auto Repair SEO Services"
- Pain paragraph + 3-step process + 3 feature cards + bottom CTA strip

### services/lead-generation.html
- H1: "An Empty Shop Won't Pay the Bills. Let's Fix That."
- H2: "Auto Repair Lead Generation"
- Pain + 3 feature cards + bottom CTA strip

### services/consultant.html
- H1: "Drive More Customers to Your Workshop with Expert Marketing Strategies"
- H2: "Mechanic Marketing Consultant"
- Pain + 3 feature cards + bottom CTA strip

### industries/diesel.html
- H1: "Fill your workshop with high-value diesel jobs..."
- H2: "Marketing for Diesel Mechanics"
- Specific pain + 3 feature cards

### industries/european.html
- H1: "Get more bookings from Audi, BMW, VW..."
- H2: "Marketing for European Car Specialists"

### industries/4x4.html
- H1: "Reach touring and off-road customers..."
- H2: "Marketing for 4x4 Mechanics"

### industries/american-trucks.html
- H1: "Get found by Silverado, RAM & F-Truck owners..."
- H2: "Marketing for American Truck Mechanics"

### industries/mobile-mechanic.html
- H1: "Get more mobile mechanic bookings..."
- H2: "Mobile Mechanic Marketing"

### industries/heavy-vehicle.html
- H1: "Fill your schedule with heavy vehicle repair..."
- H2: "Heavy Vehicle Mechanic Marketing"

### industries/auto-ac.html
- H1: "Get more A/C repair and regas bookings..."
- H2: "Automotive Air Conditioning Marketing"

### blog/index.html
- Footer updated to 4-column layout only (content preserved)

## Structural Decisions

- Industry pages retain the existing 3-column service-card section from the scaffold but with updated hero and pain content. The placeholder "results" section was removed in favour of cleaner pages.
- All pages now use the 4-column footer: Brand / Services / Industries / Resources.
- Service pages added an H2 subheading below H1 using inline style to maintain the existing page-hero structure without modifying CSS.
- contact.html form uses `__CONTACT_FORM_ENDPOINT__` and `__BOOKING_URL__` as literal placeholders pending integration.
- `team-photo-placeholder` CSS added inline in about.html `<style>` block (real photos to follow).
- admin/index.html not updated (outside scope of public content migration).
