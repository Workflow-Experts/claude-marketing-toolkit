# Content Templates Reference

Use these templates when the user asks you to plan content. Pick the relevant template and fill it in based on their topic, niche, and goals.

---

## Blog Post / Article Plan

When asked to plan a blog post or article, provide all of the following:

### 1. Title and Meta
- **Recommended title**: 2-3 options with character count (aim for 50-60 characters)
- **Meta description**: 2-3 options with character count (aim for 140-155 characters)
- **Target keyword**: primary keyword
- **Secondary keywords**: 3-5 supporting terms
- **Search intent**: Informational / Navigational / Transactional / Commercial Investigation

### 2. AEO Answer
Write the 40-60 word summary that should appear in the opening of the article. This is what AI engines are most likely to extract. It should:
- Directly answer the core question
- Use clear, factual, citation-worthy language
- Include the primary keyword naturally
- Work as a standalone statement if pulled out of context

### 3. Content Structure
Provide a full outline:

```
H1: [Title]

[AEO answer paragraph — 40-60 words, direct answer]

H2: What Is [Topic]?
[Definition section — 80-120 words. Clear, concise, entity-focused]

H2: [Main section 1]
  H3: [Subsection]
  H3: [Subsection]
[Word count guidance: XXX words]

H2: [Main section 2]
  H3: [Subsection]
  H3: [Subsection]
[Word count guidance: XXX words]

H2: [People Also Ask section 1 — phrased as a question]
[Direct answer first, then supporting detail — 100-150 words]

H2: [People Also Ask section 2 — phrased as a question]
[Direct answer first, then supporting detail — 100-150 words]

H2: [People Also Ask section 3 — phrased as a question]
[Direct answer first, then supporting detail — 100-150 words]

H2: [Summary / Key Takeaways]
[Brief wrap-up — 50-80 words]
```

### 4. Schema Markup
Recommend the appropriate schema type and provide the JSON-LD. For blog posts this is typically Article or BlogPosting. If the post contains how-to steps, recommend HowTo schema. If it contains Q&A sections, recommend adding FAQPage schema for those sections.

### 5. Internal Linking
Suggest 3-5 types of pages to link to and from. Be specific about where in the content the links should appear and what anchor text to use.

### 6. Featured Snippet Strategy
Identify the best opportunity for snippet capture and recommend how to format:
- **Paragraph snippet**: Lead with a concise 40-60 word answer directly below the target H2
- **List snippet**: Use an ordered or unordered list immediately after the H2
- **Table snippet**: Use a comparison or data table

---

## Landing Page / Funnel Page SEO

When optimising a landing or funnel page:

### Above the Fold
- H1 should contain the primary keyword and communicate the core offer
- Opening paragraph should include the AEO answer (40-60 words) if the page targets informational queries
- For transactional pages, lead with the value proposition and primary CTA

### Content Priorities
- Focus on commercial and transactional intent
- Include trust signals: testimonials, reviews, case study references, certifications, years in business
- Add E-E-A-T elements: author credentials, company background, relevant experience
- Use comparison tables if the page positions against alternatives
- Include an FAQ section at the bottom targeting People Also Ask queries related to the offer

### Technical Elements
- Recommend appropriate schema: Product, Service, LocalBusiness, or Organization depending on the page type
- Open Graph tags for social sharing
- Fast load time is critical for conversion pages — flag any obvious performance concerns
- Canonical tag pointing to the preferred URL version

### Conversion vs SEO Balance
- Don't sacrifice conversion elements for SEO. The primary goal is conversion.
- Place SEO-focused content (longer form, PAA sections, FAQ) below the main conversion area
- Use internal links from blog content to drive authority to the landing page

---

## Local SEO Action Plan

When the user needs local SEO guidance, provide a structured plan:

### Google Business Profile
- Complete every field: business name, category, description, hours, service areas, attributes
- Add photos regularly (exterior, interior, team, products/services)
- Post updates weekly using Google Business Profile posts
- Respond to every review (positive and negative)
- Use the Q&A feature to pre-populate common questions

### Local Schema Markup
- Recommend LocalBusiness schema (or the more specific subtype like Dentist, Plumber, Restaurant)
- Include all NAP details, opening hours, service area, and geo coordinates
- See `schema-examples.md` for the full LocalBusiness JSON-LD template

### NAP Consistency
- Name, Address, and Phone number must be identical everywhere: website, GBP, directories, social profiles
- Audit the main directories: Yell.com, Thomson Local, Yelp, Facebook, industry-specific directories
- Fix any inconsistencies — even small differences (Ltd vs Limited, St vs Street) can cause issues

### Service Area Pages
- Create a dedicated page for each main service area or location served
- Each page needs unique content (not just the location name swapped out)
- Include local landmarks, references, and area-specific information
- Add LocalBusiness schema with the specific service area

### Content Strategy
- Blog about locally relevant topics
- Create guides related to the local area and the business's expertise
- Target "[service] in [location]" keywords with dedicated pages
- Build FAQ content targeting local People Also Ask queries

### Review Strategy
- Ask for reviews at the point of highest satisfaction (after a completed job, positive interaction)
- Make it easy: provide a direct link to the Google review page
- Never incentivise reviews — it violates Google's guidelines
- Respond to all reviews promptly and professionally
