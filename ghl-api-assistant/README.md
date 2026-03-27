# 🔌 GHL API Assistant - Claude Skill

Get help working with the GoHighLevel API without having to dig through the docs every time. This skill covers authentication setup (Private Integration Tokens and OAuth), constructing API requests, finding the right endpoints, and troubleshooting errors.

> Part of the [Claude Marketing Toolkit](../README.md) by [Workflow Experts](https://github.com/Workflow-Experts)

---

## What's Included

```
ghl-api-assistant/
├── SKILL.md                           ← the skill itself
└── references/
    └── api-endpoints.md               ← common endpoints with copy-paste curl examples
```

Upload the skill and Claude loads it whenever you're working with the GHL API or trying to connect GHL to something else.

---

## What It Does

The main thing most people need help with is authentication. There are two options in GHL and it's not always obvious which to use or how to set them up. The skill walks through Private Integration Tokens (the simpler option, good for connecting your own account) and OAuth 2.0 (for marketplace apps and multi-account setups). It explains when to use each one and how to get them working.

Beyond auth, it helps you construct proper API requests. The reference file has curl examples for the most common operations: creating and updating contacts, managing tags, working with custom fields, creating opportunities, sending messages, and pulling calendar data. Each example is copy-paste-ready with placeholders for your actual token and IDs.

When things go wrong, it helps you diagnose errors. 401s, 403s, 422s, rate limits. It knows the common mistakes (using a custom field name instead of the ID, forgetting the Version header, expired OAuth tokens) and can walk through what's happening.

---

## Quick Start

### Install the Skill (2 minutes)
1. Download this `ghl-api-assistant` folder
2. Zip the folder
3. Open [claude.ai](https://claude.ai) and go to Settings > Customize > Skills
4. Upload the zip file
5. Done. Claude loads it when you're working with the GHL API.

**Note:** You need Code Execution enabled for skills to work. Check Settings > Capabilities if the skill isn't triggering.

---

## Example Prompts

**Getting started**
```
I want to connect my GHL account to an external tool via the API. 
What's the easiest way to set up authentication?
```

**Building a request**
```
I need to create a contact in GHL via the API. Show me the full 
curl request with all the required fields.
```

**Custom fields**
```
How do I update a custom field value on a contact through the API? 
I keep getting errors.
```

**Troubleshooting**
```
I'm getting a 401 error when I try to call the GHL API. 
Here's my request: [paste request]. What's wrong?
```

**Finding IDs**
```
I need to find my locationId and pipelineId to use in API calls. 
How do I get these?
```

**Auth comparison**
```
What's the difference between a Private Integration Token 
and OAuth in GHL? Which one should I use?
```

---

## What's Covered

**Authentication:**
- Private Integration Tokens: setup, scopes, rotation, where to find them
- OAuth 2.0: the flow, access tokens, refresh tokens, when to use it
- How to pick between the two based on your situation

**API Endpoints (with examples):**
- Contacts: create, update, search, delete, manage tags
- Custom Fields: get field IDs, set values on contacts
- Opportunities: create, update, search, get pipeline and stage IDs
- Conversations: search, send SMS and email
- Calendars: get calendars, get appointments
- Locations: get location details, search sub-accounts
- Users: get users for a location

**Troubleshooting:**
- Common error codes and what they mean
- Auth issues (expired tokens, wrong scopes, header format)
- Request format problems (missing fields, wrong data types)
- Rate limit handling

---

## What This Skill Doesn't Cover

This skill is about making API calls to GHL. It doesn't cover:

- Webhook setup or inbound data handling (too many edge cases to cover reliably)
- Building complete applications. It'll help you understand the API and construct requests, but it's not going to write your whole integration.
- GHL workflow automation. That's the [GHL Workflow Planner](../ghl-workflow-planner/) skill.

Always verify endpoints against the official docs at https://marketplace.gohighlevel.com/docs/. The API changes and this skill may not reflect the very latest additions.

---

## Coming Soon

- 🎥 Video walkthrough on YouTube
- 📦 More skills: Marketing Funnel Architect, GHL Snapshot Documenter

---

## About Workflow Experts

Tutorials, tools, and templates for workflow automation and marketing.

- 🎬 [YouTube](https://youtube.com/@WorkflowExperts?sub_confirmation=1) - Tutorials and walkthroughs
- 💬 [Community](https://www.facebook.com/groups/workflowexperts/?ref=share) - Get help and share what you build
- 🔧 [GHL Snapshots](https://workflow-experts.com?utm_source=github&utm_medium=ghl-api-assistant-readme&utm_campaign=developer&utm_content=ghl-snapshots) - Pre-built automation workflows

---

## Licence

MIT - use it, modify it, share it. Attribution appreciated but not required.
