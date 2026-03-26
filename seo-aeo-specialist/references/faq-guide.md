# FAQ Page Creation Guide

This reference covers the full process of creating FAQ pages optimised for both SEO and AEO. Use this when the user wants to create FAQ content, optimise existing FAQ pages, or build FAQ sections into other pages.

---

## Question Research

### Finding the Right Questions

The best FAQ questions come from how people actually search, not how businesses think about their services. Sources to suggest:

- **People Also Ask** — search the user's target keywords in Google and note the PAA questions that appear. These are what Google already associates with the topic.
- **Google autocomplete** — type the user's topic into Google and see what suggestions appear. Try adding "how", "what", "why", "when", "does", "can", "is" before the topic.
- **Customer enquiries** — the questions their customers actually ask via email, phone, or chat are the most authentic source.
- **Competitor FAQ pages** — check what questions competitors are answering. Identify gaps they've missed.
- **Forum and community questions** — Reddit, Quora, Facebook groups, and industry forums where real people ask real questions.

### Question Formatting Rules

- Write questions in natural language, the way a person would type them into Google or ask a voice assistant
- Use first person where natural: "How do I..." not "How does one..."
- Be specific: "How much does a boiler replacement cost in the UK?" not "What are your prices?"
- Avoid internal jargon: "How do I book an appointment?" not "How do I utilise the scheduling portal?"
- Match the user's vocabulary: if their customers say "fix" not "repair", use "fix"

---

## Answer Structure

### The AEO-Optimised Answer Format

Each answer should follow this structure:

**Lead answer (40-80 words):** A direct, complete response to the question. This is the part AI engines will extract. It should make sense on its own without any surrounding context.

**Supporting detail (optional, 50-150 words):** Additional context, examples, caveats, or specifics that add value for someone reading the full page.

**Internal link (where relevant):** A natural link to a more detailed page on the topic. Use descriptive anchor text.

### Example

**Question:** How long does a boiler installation take?

**Lead answer:** A standard boiler installation typically takes 1-2 days. A straightforward swap where the new boiler goes in the same location usually takes 4-6 hours. If the boiler needs to be moved to a new position, or if there's pipework changes needed, it can take up to 2 full days.

**Supporting detail:** The timeline depends on the type of boiler (combi, system, or regular), whether you're changing fuel type, and the condition of existing pipework. We always carry out a survey first so you know exactly what to expect before any work starts.

**Internal link:** For a full breakdown of what's involved, see our [boiler installation guide](/services/boiler-installation).

---

## Page Structure

### Organising FAQ Content

For pages with more than 8-10 questions, group them by theme:

```
H1: Frequently Asked Questions About [Topic]

[Brief intro paragraph — 2-3 sentences explaining what this page covers]

H2: [Theme 1 — e.g., "Pricing and Costs"]

  H3: How much does [service] cost?
  [Answer]

  H3: Do you offer payment plans?
  [Answer]

  H3: Are there any hidden fees?
  [Answer]

H2: [Theme 2 — e.g., "The Process"]

  H3: How long does [service] take?
  [Answer]

  H3: What do I need to prepare?
  [Answer]

H2: [Theme 3 — e.g., "After the Service"]

  H3: What guarantee do you offer?
  [Answer]

  H3: What if something goes wrong?
  [Answer]
```

For shorter FAQ sections (3-6 questions) embedded within another page, H2 for the FAQ section header and H3 for each question is sufficient.

### Standalone vs Embedded FAQs

**Standalone FAQ page** — a dedicated /faq or /frequently-asked-questions page. Best when you have 10+ questions and want the page to rank for multiple question-based keywords.

**Embedded FAQ section** — a section at the bottom of a service page, product page, or landing page. Best for addressing buying objections and targeting PAA queries related to that specific page's topic.

Both can use FAQPage schema. For embedded sections, the schema only needs to include the Q&A pairs on that page, not every FAQ across the site.

---

## FAQPage Schema Implementation

### Basic Template

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Question text goes here exactly as shown on the page?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Answer text goes here. This should match the visible answer on the page. Keep it to the lead answer — you don't need to include every word of supporting detail."
      }
    },
    {
      "@type": "Question",
      "name": "Second question goes here?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Second answer goes here."
      }
    }
  ]
}
```

### Important Rules

- The question text in the schema **must match** the question as it appears on the page. Word for word.
- The answer text should match the visible answer. It can be a trimmed version (the lead answer) but must not contain information that isn't on the page.
- Do not add FAQ schema for questions that aren't visibly displayed on the page. Google will penalise this.
- You can include basic HTML in the answer text (links, bold, lists) using escaped HTML: `<a href=\"/page\">link text</a>`
- There is no official limit on the number of questions, but keep it to questions that genuinely appear on the page.

### Schema with HTML in Answers

When an answer contains a link or formatting:

```json
{
  "@type": "Question",
  "name": "Do you offer emergency callouts?",
  "acceptedAnswer": {
    "@type": "Answer",
    "text": "Yes, we offer 24/7 emergency callouts across Manchester and Salford. Call us on <a href=\"tel:+441234567890\">01onal 234 567890</a> for immediate assistance. See our <a href=\"/services/emergency\">emergency services page</a> for more details."
  }
}
```

---

## FAQ Content for AEO

### What Makes FAQ Content Work for AI Engines

AI answer engines look for:

1. **A clear question** that matches what someone might search
2. **A direct answer** in the first 1-2 sentences that fully addresses the question
3. **Structured markup** (FAQPage schema) that makes the Q&A pairs machine-readable
4. **Authority signals** — the page is on a site that has demonstrated expertise on this topic
5. **Freshness** — the page has been recently published or updated

### Optimisation Checklist

When creating or reviewing FAQ content for AEO:

- [ ] Each question uses natural, search-like language
- [ ] Each answer leads with a direct response (40-80 words)
- [ ] Answers use specific facts, numbers, and timeframes rather than vague qualifiers
- [ ] Entities are named explicitly (not "we" or "it" in the lead answer — name the business, the service, the product)
- [ ] FAQPage schema is implemented and matches visible content
- [ ] The page includes a "last updated" date
- [ ] Questions are grouped logically by theme
- [ ] Internal links connect to more detailed content where relevant
- [ ] The page is linked to from related service/product pages (not orphaned)

---

## Number of Questions

### How Many Questions to Include

**Standalone FAQ page:** 10-25 questions is a good range. Fewer than 10 and the page feels thin. More than 25 and it becomes overwhelming — consider splitting into topic-specific FAQ pages instead.

**Embedded FAQ section:** 3-8 questions. These should be directly relevant to the page they're on. A service page's FAQ section should answer buying questions about that specific service.

**FAQ hub with category pages:** For businesses with lots of questions, create a hub structure:
- /faq (overview linking to categories)
- /faq/pricing (pricing-related questions)
- /faq/getting-started (onboarding questions)
- /faq/technical (technical questions)

Each category page gets its own FAQPage schema covering its questions.
