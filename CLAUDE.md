# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static website for SO MECHANIC, an automotive garage located in Cornebarrieu, France. This is a single-page application built with vanilla HTML, TailwindCSS, and Font Awesome icons, hosted on Netlify.

**Site URL**: https://somechanic.netlify.app/
**Business Location**: 45 bis route d'Aussonne, Cornebarrieu 31700

## Architecture

### Core Files
- **index.html**: Main landing page with all sections (hero, services, pricing, reviews, contact form)
- **sucess.html**: Form submission confirmation page (note: filename has typo - should be "success.html" but keep as-is for URL consistency)
- **sitemap.xml**: SEO sitemap for search engines
- **robots.txt**: Search engine crawler configuration
- **_headers**: Netlify headers configuration for content types

### Technology Stack
- Pure HTML5 (no build process)
- TailwindCSS via CDN (https://cdn.tailwindcss.com)
- Font Awesome 6.4.0 via CDN
- Google Fonts (Inter family)
- Netlify Forms for contact form handling
- Schema.org structured data for local business SEO

### Design System
- **Color Scheme**: Dark theme with blue accents
  - Background: gray-900, gray-800
  - Primary: blue-600, blue-400
  - Text: white, gray-300, gray-400
- **Typography**: Inter font family (300, 400, 600, 700, 800 weights)
- **Components**: Service cards, pricing cards, testimonial cards, contact form
- **Layout**: Responsive grid system using Tailwind's breakpoints (md, lg)

## Key Features

### SEO Implementation
- Comprehensive meta tags (title, description, keywords)
- Open Graph tags for social media
- Twitter Card metadata
- Google Site Verification tag in head (index.html:16)
- Schema.org LocalBusiness structured data (AutoRepair type) with:
  - Business hours
  - Location coordinates
  - Contact information
  - Aggregate rating (5/5, 22 reviews)
- Canonical URL
- Proper sitemap.xml with priority levels

### Contact Form
- Netlify Forms integration (index.html:666)
- Honeypot spam protection (bot-field)
- Form fields: name, email, phone, service selection, message
- Redirects to /success.html on submission
- All fields are required

### Google Maps Integration
- Embedded map iframe (index.html:570-574)
- Coordinates: 43.657949, 1.3216458
- Direct link to Google Maps location

### Customer Reviews Section
- Displays 6 real Google reviews
- 4.3/5 star rating visualization
- Links to full Google Reviews page

## Sections Structure (index.html)

1. **Navigation** (line 132): Fixed header with logo, nav links, call button
2. **Hero Section** (line 155): Main headline, CTAs, business info cards
3. **Services Section** (line 216): 4 service cards (mechanics, oil change, diagnostics, inspection)
4. **Pricing Section** (line 289): 3 pricing tiers with feature lists
5. **Why Choose Us** (line 349): 4 value propositions
6. **Google Reviews** (line 393): Customer testimonials
7. **Map Section** (line 562): Location finder with embedded map
8. **Contact Section** (line 588): Contact info + form
9. **Footer** (line 723): Links, hours, copyright

## Development Notes

### No Build Process
This is a static site with no build step. All changes are direct edits to HTML files. Deploy by pushing to the main branch - Netlify handles deployment automatically.

### Styling Approach
- Uses Tailwind utility classes directly in HTML
- Custom CSS in `<style>` tags in head:
  - `.hero-gradient`: Dark gradient background
  - `.service-card`: Hover effects for service cards
  - `.btn-primary`: Primary button gradient with hover scale
  - `html`: Smooth scroll behavior

### Important Business Information
- **Phone**: 06 21 97 77 82 (+33621977782)
- **Email**: somechanic31@gmail.com
- **Hours**:
  - Mon-Thu: 9:30-18:30
  - Friday: 9:30-13:30, 14:30-18:30 (lunch break)
  - Saturday: 9:30-18:30
  - Sunday: Closed

### Deployment
- Hosted on Netlify
- Automatic deployment from main branch
- Custom headers configured via _headers file
- Forms handled by Netlify Forms (no backend required)

## Making Changes

### Updating Content
- Service descriptions: Edit service cards in index.html:224-284
- Pricing: Edit pricing cards in index.html:296-337
- Reviews: Update testimonials in index.html:412-548
- Contact info: Update in multiple locations (hero section, contact section, footer)
- Business hours: Update in hero info card, footer, and Schema.org data

### SEO Updates
- Meta tags: Head section of index.html (lines 8-31)
- Schema.org data: JSON-LD script in head (lines 34-89)
- Sitemap: Edit sitemap.xml (update lastmod dates when making significant changes)

### Form Configuration
The form uses Netlify Forms attributes (index.html:666):
- `data-netlify="true"`: Enables Netlify form handling
- `data-netlify-honeypot="bot-field"`: Spam protection
- `action="/success.html"`: Redirect after submission
