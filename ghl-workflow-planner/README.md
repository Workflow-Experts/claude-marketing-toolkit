# 🔄 GHL Workflow Planner - Claude Skill

Describe a business process in plain English and get a buildable GHL workflow back. Triggers, actions, conditions, wait steps, the lot. Claude maps the logic so you can build it in GoHighLevel without guessing.

> Part of the [Claude Marketing Toolkit](../README.md) by [Workflow Experts](https://github.com/Workflow-Experts)

---

## What's Included

```
ghl-workflow-planner/
├── SKILL.md                           ← the skill itself
└── references/
    ├── triggers-and-actions.md        ← every available trigger and action in GHL workflows
    └── workflow-templates.md          ← common patterns: lead follow-up, appointment reminders, review requests, etc.
```

Upload the skill and Claude loads it automatically whenever you're talking about GHL workflows, automations, or business processes you want to automate.

---

## What It Does

You describe what you want to happen ("when someone books an appointment, send a confirmation email, then remind them the day before and an hour before"). Claude maps that into a step-by-step workflow with the right trigger, the right actions, proper wait step timing, and If/Else branches where needed.

It sticks to what GHL can actually do. The skill includes a reference list of every available trigger and action, so Claude won't send you hunting for features that don't exist.

It also flags things you might not think of. What happens if someone enters the workflow twice? What if they cancel their appointment halfway through the reminder sequence? Should this workflow remove them from another one? That kind of thing.

---

## Quick Start

### Install the Skill (2 minutes)
1. Download this `ghl-workflow-planner` folder
2. Zip the folder
3. Open [claude.ai](https://claude.ai) and go to Settings > Customize > Skills
4. Upload the zip file
5. Done. Claude loads it when it detects you're working on GHL workflows.

**Note:** You need Code Execution enabled for skills to work. Check Settings > Capabilities if the skill isn't triggering.

---

## Example Prompts

**Simple sequence**
```
I run a cleaning business. When someone fills in my quote request form,
I want to send them a confirmation email straight away, then a text 
5 minutes later, then follow up after 2 days if they haven't booked.
```

**Appointment reminders**
```
Map out an appointment reminder workflow. I want a confirmation email 
when they book, a reminder 24 hours before, and a text 1 hour before. 
If they cancel at any point, stop sending reminders.
```

**Review request**
```
After I complete a job and move the opportunity to "completed" in my 
pipeline, I want to wait 2 hours then ask for a Google review via text. 
Follow up by email 3 days later if they haven't left one.
```

**Pipeline automation**
```
When a deal moves to "proposal sent", create a follow-up task if it's 
still there after 3 days. When it moves to "won", tag them as a client 
and start the onboarding sequence. When it moves to "lost", wait 30 
days then start a re-engagement sequence.
```

**Troubleshooting**
```
My follow-up emails are going out at the wrong times. Here's my workflow:
[describe or paste workflow]. Can you check the wait step timing?
```

---

## Wait Step Timing

This is the thing that catches most people out. Wait steps in GHL are relative to the previous step, not the start of the workflow.

If you want emails sent at day 1, day 3, and day 7:
- First wait: **1 day** (from workflow entry)
- Second wait: **2 days** (from the day 1 email, because 3 minus 1 is 2)
- Third wait: **4 days** (from the day 3 email, because 7 minus 3 is 4)

If you set the third wait to 7 days, the email actually goes out on day 10. The skill always calculates this correctly and shows the working, so you can double check it when building.

---

## Common Workflow Patterns

The skill includes templates for the most common use cases:

- **New lead follow-up** with conversion checks at each stage
- **Appointment reminders** with cancellation handling
- **Post-service review requests** with follow-up
- **Pipeline stage automations** for internal task management
- **Client onboarding** with progress tracking
- **Re-engagement sequences** for cold leads and lost deals

These aren't rigid scripts. Claude uses them as starting points and adapts based on your specific business, timing, and messaging.

---

## Tips for Getting Better Results

Give Claude context about your business. "I'm a personal trainer" produces a very different workflow to "I run a B2B SaaS company." The more Claude knows about your sales process and customer journey, the better the workflow maps to reality.

Describe the outcome you want, not just the steps. "I want to reduce no-shows" gives Claude room to suggest a proper reminder sequence. "Send an email then a text" doesn't.

Ask about edge cases. "What happens if they book while they're in the nurture sequence?" is the kind of question that catches problems before you build them.

If you already have a workflow that isn't working, describe it or paste the steps and ask Claude to review it. Timing issues and missing conditions are usually the culprit.

---

## Coming Soon

- 🎥 Video walkthrough on YouTube showing this skill in action
- 📦 More skills: GHL API Assistant, Marketing Funnel Architect

---

## About Workflow Experts

Tutorials, tools, and templates for workflow automation and marketing.

- 🎬 [YouTube](https://youtube.com/@WorkflowExperts) - Tutorials and walkthroughs
- 💬 [Community](https://www.facebook.com/groups/workflowexperts/) - Get help and share what you build
- 🔧 [GHL Snapshots](https://workflow-experts.com) - Pre-built automation workflows

---

## Licence

MIT - use it, modify it, share it. Attribution appreciated but not required.
