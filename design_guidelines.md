# Southern Circuit Co. - Design Guidelines

## Design Approach
**Hybrid Approach**: Drawing inspiration from professional service industry leaders (ServiceTitan, HomeAdvisor) combined with distinctive southwestern/western brand identity. The design balances rugged authenticity with modern electrical service credibility, ensuring trust while standing out in the local market.

## Core Design Principles
1. **Western Authenticity**: Embrace southwestern aesthetics without compromising professionalism
2. **Trust-First Design**: Clean, organized layouts that inspire confidence in electrical expertise
3. **Conversion-Focused**: Clear pathways to contact and quote requests throughout
4. **Local Pride**: Showcase Queen Creek, AZ roots prominently

## Typography System

**Primary Headings (H1, Brand Elements)**
- Font: "Bebas Neue" or "Oswald" (Google Fonts) - bold, condensed western-style
- Weights: 700
- Transform: Uppercase for major headings
- Usage: Hero headline, section titles, major CTAs

**Secondary Headings (H2, H3)**
- Font: "Montserrat" (Google Fonts)
- Weights: 600, 700
- Usage: Service cards, subsections, feature highlights

**Body Text & UI Elements**
- Font: "Inter" (Google Fonts)
- Weights: 400, 500, 600
- Usage: Descriptions, forms, navigation, all readable content

**Hierarchy Scale**
- Hero Headline: text-5xl md:text-6xl lg:text-7xl
- Section Headings: text-3xl md:text-4xl lg:text-5xl
- Card Titles: text-xl md:text-2xl
- Body: text-base md:text-lg
- Small Print: text-sm

## Layout System

**Spacing Primitives**: Use Tailwind units of **4, 8, 12, and 16** consistently
- Micro spacing (within components): p-4, gap-4, space-y-4
- Component padding: p-8 or p-12
- Section spacing: py-16 md:py-20 lg:py-24
- Container margins: px-4 md:px-8

**Grid System**
- Container: max-w-7xl mx-auto
- Content sections: max-w-6xl
- Text-heavy content: max-w-4xl
- Two-column splits: grid-cols-1 md:grid-cols-2 gap-8 or gap-12

**Responsive Breakpoints**
- Mobile-first approach
- Tablet: md: (768px)
- Desktop: lg: (1024px)
- Wide: xl: (1280px)

## Component Library

### Navigation
**Desktop Header**
- Fixed/sticky top navigation
- Logo (longhorn) left-aligned, height h-12 to h-16
- Navigation links center or right-aligned
- Primary CTA button (blurred background): "Get Free Quote"
- Background: Subtle backdrop-blur-md with slight opacity

**Mobile Navigation**
- Hamburger menu icon
- Full-screen or slide-in menu overlay
- Stacked navigation links with generous tap targets (min-height: 48px)

### Hero Section
**Layout**: Full viewport height (min-h-screen) with background image
- Background: Southwestern landscape, electrical work imagery, or longhorn brand aesthetic
- Overlay: Dark gradient overlay (from-black/60 to-transparent) for text contrast
- Content structure:
  - Longhorn logo: w-20 md:w-24 lg:w-32, centered or top-center
  - Main headline: Centered, uppercase, maximum 10 words
  - Subheadline: 1-2 sentences, max-w-2xl centered
  - CTA buttons: Primary "Schedule Service" + Secondary "View Services" side-by-side
  - Trust indicators below CTAs: "Licensed • Bonded • Insured • Queen Creek, AZ"

**CTA Buttons on Hero**
- Background: backdrop-blur-lg with bg-white/10 or bg-black/20
- Border: border border-white/30
- Text: text-white
- Padding: px-8 py-4
- No custom hover states (use default button component behavior)

### Services Section
**Layout**: 3-column grid on desktop, 2-column tablet, 1-column mobile
- Service Cards:
  - Icon or small image at top (electrical bolt, home, building icons)
  - Service title: text-xl font-semibold
  - 2-3 sentence description
  - "Learn More" link
  - Padding: p-8
  - Border or subtle shadow for definition
  
**Services to Include**:
1. Residential Electrical
2. Commercial Electrical
3. Panel Upgrades
4. Generator Installation
5. Lighting Solutions
6. Emergency Repairs

### About Section
**Layout**: 2-column split (60/40 or symmetric)
- Left: Compelling brand story
  - Headline: "Your Queen Creek Electrical Experts"
  - Emphasis on 2024 establishment (fresh, modern approach)
  - Southwestern values: reliability, craftsmanship, community
  - 3-4 paragraphs, max-w-prose
- Right: Image placeholder or brand elements
  - Longhorn logo showcase
  - Team photo placeholder
  - License/certification badges

### Portfolio/Work Gallery
**Layout**: Masonry grid or 3-column equal-height grid
- Photo cards from Instagram work
- Hover overlay: Project type label
- Click to expand or link to Instagram
- 6-9 photos displayed

### Testimonials/Social Proof
**Layout**: 3-column grid or carousel
- Customer quote
- Star rating (5 stars)
- Name and service type
- Optional: Small customer photo
- Padding: p-8
- Background: Subtle contrast from main background

### Contact/Quote Section
**Layout**: 2-column split
- Left column (60%): Quote request form
  - Fields: Name, Email, Phone, Service Type (dropdown), Message
  - All fields required
  - Submit button: "Request Free Quote"
  - Form padding: p-8
- Right column (40%): Business information
  - Phone number (large, clickable)
  - Email address
  - Service area: "Queen Creek & Surrounding Areas"
  - Hours of operation
  - Emergency service notice
  - Social media links

### Footer
**Layout**: 3-column on desktop, stacked mobile
- Column 1: Logo + tagline + brief description
- Column 2: Quick links (Services, About, Contact, Instagram)
- Column 3: Contact info + service area
- Bottom bar: Copyright, License #, "Designed in Queen Creek, AZ"
- Background: Darker than main content for visual grounding

## Images

**Hero Background Image**
- Description: Wide panoramic shot of southwestern landscape (desert, mountains) during golden hour OR electrical work in progress with southwestern architectural elements
- Treatment: Slightly desaturated, dark overlay gradient
- Placement: Full-width background, background-size: cover, background-position: center
- Dimensions: Minimum 1920x1080px

**About Section Image**
- Description: Professional photo of electrician at work OR longhorn logo in artistic southwestern setting OR team photo with work truck
- Placement: Right column of About section
- Dimensions: Square or 4:3 ratio, minimum 800x800px

**Portfolio Gallery Images (6-9 images)**
- Description: Completed electrical projects - panel installations, lighting setups, commercial work, residential upgrades
- Treatment: Consistent cropping, subtle border or shadow
- Placement: Grid layout in Portfolio section
- Dimensions: Square format, minimum 600x600px each

**Service Icons/Images**
- Description: Simple electrical-themed icons or small photos representing each service category
- Placement: Top of each service card
- Style: Line icons or filled icons in brand-compatible aesthetic

**Large Hero Image**: YES - Full-width, full-height background image with overlay in hero section

## Animations & Interactions

**Minimal Animation Strategy**
- Smooth scroll behavior on anchor links
- Fade-in on scroll for section headings only (no complex scroll animations)
- Button hover states: Default component behavior
- Form focus states: Subtle border highlight
- No parallax, no complex scroll-triggered animations
- Mobile: Reduce/remove animations for performance

## Special Considerations

**Western/Southwestern Aesthetic Elements**
- Longhorn logo prominently featured in header and footer
- Consider subtle texture overlays (leather, wood grain) used sparingly
- Rope or border accent elements in dividers (optional, use tastefully)
- Sunrise/sunset imagery reflecting Arizona landscape

**Trust & Credibility Indicators**
- License and certification badges visible
- "Licensed • Bonded • Insured" prominently displayed
- Years of experience or "Established 2024" as fresh approach
- Emergency service availability highlighted
- Local emphasis: "Proudly Serving Queen Creek"

**Conversion Optimization**
- Phone number clickable and visible on every section
- "Get Free Quote" CTA appears at least 3 times: header, hero, dedicated section
- Service area clearly defined
- Response time expectations set
- Emergency service path clearly marked

This comprehensive design creates a professional, conversion-focused electrical services website that honors Southern Circuit Co.'s distinctive southwestern brand while building trust and driving quote requests.