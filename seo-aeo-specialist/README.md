# 🔍 SEO & AEO Specialist - Claude Configuration

Get Claude to actually think about SEO and AEO (answer engine optimisation) when you're working on content. Instead of generic advice, it'll give you specific recommendations for ranking in traditional search *and* getting cited by AI answer engines like Google AI Overviews, ChatGPT Search, and Perplexity.

> Part of the [Claude Marketing Toolkit](../README.md) by [Workflow Experts](https://github.com/Workflow-Experts)

---

## What's Included

| File | Where to Use It | Best For |
|------|-----------------|----------|
| `custom-instructions.md` | Settings > Customise Claude | Background SEO awareness in all your conversations |
| `project-instructions.md` | Create a Project > Project Instructions | A dedicated SEO workspace with structured frameworks |

---

## What It Does

### Custom Instructions
The lighter option. Drop this into your Customise Claude settings and it quietly shapes how Claude approaches any content discussion. It'll consider search intent, suggest schema markup, think about SERP features, and flag AEO opportunities without you having to ask.

### Project Instructions
This is the full setup. Create a dedicated project and Claude gets access to structured frameworks for keyword analysis, content planning, technical audits, and AEO optimisation.

In practice, that means you can throw it a list of keywords and get back intent classifications, difficulty estimates, SERP feature breakdowns, and AEO opportunity scores. Ask it to plan a blog post and it'll work through intent, structure, semantics, technical elements, and AEO in layers rather than just giving you a flat outline. It handles local SEO too, including Google Business Profile and local schema.

---

## Quick Start

### Option 1: Custom Instructions (2 minutes)
1. Open [claude.ai](https://claude.ai)
2. Go to Settings > Customise Claude > Custom Instructions
3. Copy the contents of `custom-instructions.md` and paste it in
4. Save. That's it.

### Option 2: Dedicated Project (5 minutes)
1. Open [claude.ai](https://claude.ai)
2. Click Projects > Create Project
3. Name it something like "SEO & AEO Workspace"
4. Paste the contents of `project-instructions.md` into the Project Instructions field
5. Start a conversation and try one of the prompts below

---

## Example Prompts

Here are some good ones to start with:

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
Plan a blog post targeting "how to choose a CRM for small business" - 
I want to rank for the featured snippet and get cited in AI Overviews.
```

**AEO Optimisation**
```
Here's my existing blog post about email marketing automation. 
How can I optimise it so AI answer engines cite it when people ask 
about email automation?

[paste your content]
```

**Technical SEO**
```
Review this page for technical SEO issues: [URL]
Focus on schema markup opportunities and Core Web Vitals.
```

**Local SEO**
```
I run a dental practice in Leeds. Create a local SEO action plan 
covering Google Business Profile, local schema, and content strategy.
```

---

## How AEO Works (Quick Primer)

Traditional SEO gets you ranking in search results. AEO is about getting your content cited by AI answer engines - Google AI Overviews, ChatGPT Search, Perplexity, and the rest. These tools are giving users answers directly now, and they're pulling that information from somewhere.

The factors that seem to matter most for getting cited:

- **Authority** - does your domain have trust and depth on this topic?
- **Clarity** - are your answers direct and unambiguous?
- **Structure** - do you use schema markup, tables, numbered steps, clear headings?
- **Freshness** - when was this published or last updated?
- **Specificity** - are you using concrete data, or just vague statements?

This config gets Claude thinking about all of these when it helps you with content.

---

## Tips for Getting More Out of It

Tell Claude about your niche upfront. "I run a SaaS company selling project management tools" gets you much better output than a vague request.

Paste in existing content and ask Claude to optimise it. You'll get more value from improving what you've already got than starting from scratch.

Ask Claude to prioritise. It'll give you a lot of recommendations, so have it tell you what to tackle first.

Use the project for ongoing work. Context carries across conversations, so the more you use it the more useful it gets.

Bring in data from your other tools. Export keyword data from Ahrefs or SEMrush and paste it in for analysis.

---

## Coming Soon

- 🎥 Video walkthrough on YouTube showing how to set this up and use it
- ⚡ Claude Code version with slash commands (`/seo-audit`, `/content-plan`, `/schema-generate`)
- 📦 More configs: GHL Workflow Planner, GHL API Assistant, Marketing Funnel Architect

---

## About Workflow Experts

Tutorials, tools, and templates for workflow automation and marketing.

- 🎬 [YouTube](https://youtube.com/@WorkflowExperts) - Tutorials and walkthroughs
- 💬 [Community](https://www.facebook.com/groups/workflowexperts/) - Get help and share what you build
- 🔧 [GHL Snapshots](https://workflow-experts.com) - Pre-built automation workflows

---

## Licence

MIT - use it, modify it, share it. Attribution appreciated but not required.
