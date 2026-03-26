# 🔍 SEO & AEO Specialist — Claude Skill

Get Claude to actually think about SEO and AEO (answer engine optimisation) when you're working on content. Instead of generic advice, it'll give you specific recommendations for ranking in traditional search *and* getting cited by AI answer engines like Google AI Overviews, ChatGPT Search, and Perplexity.

> Part of the [Claude Marketing Toolkit](../README.md) by [Workflow Experts](https://github.com/Workflow-Experts)

---

## What's Included

```
seo-aeo-specialist/
├── SKILL.md                           ← the skill itself
├── project-instructions.md            ← for dedicated Claude projects
└── references/
    ├── content-templates.md           ← blog post, landing page, and local SEO frameworks
    ├── schema-examples.md             ← ready-made JSON-LD for all common schema types
    └── faq-guide.md                   ← FAQ creation, formatting, schema, and AEO optimisation
```

**Two ways to use this:**

The **skill** is what you want most of the time. Upload it once, and Claude loads it automatically whenever you're doing something SEO-related — writing a blog post, building a landing page, creating FAQ content. You don't need to tell it to use SEO knowledge; it just does.

The **project instructions** are for when you want a dedicated SEO workspace. Create a project, paste them in, and every conversation in that project is geared toward SEO from the start. Good for keyword research sessions and content audits.

---

## What It Covers

**Written SEO & AEO strategy** — a layered approach that works through intent, structure, semantics, and AEO optimisation. Keyword analysis with intent classification, SERP feature breakdowns, and AEO opportunity scoring. Content plans for blog posts, landing pages, and local businesses.

**FAQ content creation** — how to research the right questions, structure answers for AI engine extraction, group and organise FAQ pages, and implement FAQPage schema markup. FAQ content is where SEO and AEO overlap most, so the guide goes deep here.

**Technical SEO implementation** — actual code, not theory. Copy-paste JSON-LD templates for LocalBusiness, FAQPage, HowTo, Article, Product, Service, BreadcrumbList, and Organization. Meta tags, canonical tags, and robots directives with exact HTML. Core Web Vitals diagnostics and fixes. Site architecture and internal linking strategy.

---

## Quick Start

### Install the Skill (2 minutes)
1. Download this `seo-aeo-specialist` folder
2. Zip the folder
3. Open [claude.ai](https://claude.ai) and go to Settings > Customize > Skills
4. Upload the zip file
5. Done. Claude loads the skill automatically when it detects SEO-related tasks.

**Note:** You need Code Execution enabled for skills to work. Check Settings > Capabilities if the skill isn't triggering.

### Or Use as a Project (5 minutes)
1. Open [claude.ai](https://claude.ai)
2. Click Projects > Create Project
3. Name it something like "SEO & AEO Workspace"
4. Paste the contents of `project-instructions.md` into the Project Instructions field
5. Start a conversation and try one of the prompts below

---

## Example Prompts

**Keyword Analysis**
```
Analyse these keywords for a plumbing business in Manchester:
- emergency plumber Manchester
- boiler repair near me
- how to fix a leaking tap
- best plumber Manchester reviews
```

**Content Planning**
```
Plan a blog post targeting "how to choose a CRM for small business" — 
I want to rank for the featured snippet and get cited in AI Overviews.
```

**FAQ Page Creation**
```
I run a personal training business. Create an FAQ page with 10 questions 
targeting People Also Ask results. Include the FAQPage schema markup.
```

**Schema Markup**
```
I need LocalBusiness schema markup for a plumbing company in Leeds 
that covers 5 service areas. Give me the full JSON-LD.
```

**AEO Optimisation**
```
Here's my existing blog post about email marketing automation. 
How can I optimise it so AI answer engines cite it when people ask 
about email automation?

[paste your content]
```

**Local SEO**
```
I run a dental practice in Leeds. Create a local SEO action plan 
covering Google Business Profile, local schema, and content strategy.
```

---

## How AEO Works (Quick Primer)

Traditional SEO gets you ranking in search results. AEO is about getting your content cited by AI answer engines — Google AI Overviews, ChatGPT Search, Perplexity, and the rest. These tools are giving users answers directly now, and they're pulling that information from somewhere.

The factors that seem to matter most for getting cited:

- **Authority** — does your domain have trust and depth on this topic?
- **Clarity** — are your answers direct and unambiguous?
- **Structure** — do you use schema markup, tables, numbered steps, clear headings?
- **Freshness** — when was this published or last updated?
- **Specificity** — are you using concrete data, or just vague statements?

FAQ pages are particularly strong for AEO because each Q&A pair is a self-contained, citable answer. Combine that with FAQPage schema and you've got content that both Google and AI engines can easily parse and reference.

---

## Tips for Getting More Out of It

Tell Claude about your niche upfront. "I run a SaaS company selling project management tools" gets you much better output than a vague request.

Paste in existing content and ask Claude to optimise it. You'll get more value from improving what you've already got than starting from scratch.

Ask Claude to prioritise. It'll give you a lot of recommendations, so have it tell you what to tackle first.

If you're using the project, keep it for ongoing work. Context carries across conversations, so the more you use it the more useful it gets.

Bring in data from your other tools. Export keyword data from Ahrefs or SEMrush and paste it in for analysis.

---

## Coming Soon

- 🎥 Video walkthrough on YouTube showing how to install and use this skill
- 📦 More skills: GHL Workflow Planner, GHL API Assistant, Marketing Funnel Architect

---

## About Workflow Experts

Tutorials, tools, and templates for workflow automation and marketing.

- 🎬 [YouTube](https://youtube.com/@WorkflowExperts) — Tutorials and walkthroughs
- 💬 [Community](https://www.facebook.com/groups/workflowexperts/) — Get help and share what you build
- 🔧 [GHL Snapshots](https://workflow-experts.com) — Pre-built automation workflows

---

## Licence

MIT — use it, modify it, share it. Attribution appreciated but not required.
