# Common Workflow Templates

These are patterns for the most common GHL workflows. Use them as starting points and adapt to the user's specific needs. Don't copy them blindly. Ask the user about their specific timing, messaging, and conditions before finalising.

---

## New Lead Follow-Up

**Purpose:** Respond to a new lead quickly, then nurture them toward booking or buying.

**Typical trigger:** Form Submitted or Contact Created

```
Step 1: Send Email (immediate)
  Config: Welcome/confirmation email. Acknowledge what they signed up for.

Step 2: Add Tag ("lead-nurture-active")
  Reason: Marks the contact as being in this sequence. Useful for excluding them from other workflows.

Step 3: Wait 5 minutes

Step 4: Send SMS
  Config: Short personal message. "Hi [first name], just saw your enquiry about [topic]. Any questions I can help with?"

Step 5: Wait 1 day (from Step 4, not from entry)

Step 6: If/Else - has tag "appointment-booked"?
  YES: Remove Tag ("lead-nurture-active"), end workflow
  NO: Continue

Step 7: Send Email
  Config: Value-add email. Useful information related to their enquiry, not a hard sell.

Step 8: Wait 2 days (from Step 7)

Step 9: If/Else - has tag "appointment-booked"?
  YES: Remove Tag ("lead-nurture-active"), end workflow
  NO: Continue

Step 10: Send SMS
  Config: Gentle follow-up. "Hi [first name], just checking in. Still interested in [topic]?"

Step 11: Wait 3 days (from Step 10)

Step 12: Send Email
  Config: Final follow-up with clear CTA. This is the last touchpoint.

Step 13: Remove Tag ("lead-nurture-active")
```

**Notes:**
- Check for booking/conversion at each stage so contacts who convert stop getting follow-ups
- Adjust timing based on the industry. Shorter gaps for urgent services (plumbing, emergency), longer for considered purchases (coaching, consulting)
- The user should exit contacts from this workflow if they convert via another route

---

## Appointment Reminder Sequence

**Purpose:** Reduce no-shows by reminding contacts about upcoming appointments.

**Typical trigger:** Appointment Status Changed (filtered to "booked" or "confirmed")

```
Step 1: Add Tag ("appointment-booked")
  Reason: Lets other workflows know this contact has an appointment.

Step 2: Send Email (immediate)
  Config: Appointment confirmation with date, time, location/link, and any preparation instructions.

Step 3: Wait until 24 hours before appointment
  Config: Use "wait until event" set to 24 hours before the appointment date.

Step 4: If/Else - appointment status is still "confirmed"?
  YES: Continue
  NO: End workflow (they've already cancelled or rescheduled)

Step 5: Send SMS
  Config: "Hi [first name], just a reminder about your appointment tomorrow at [time]. See you then!"

Step 6: Wait until 1 hour before appointment

Step 7: If/Else - appointment status is still "confirmed"?
  YES: Continue
  NO: End workflow

Step 8: Send SMS
  Config: "Hi [first name], your appointment is in 1 hour. [Location/link details]"
```

**Notes:**
- The If/Else checks before each reminder prevent messages going out to people who've cancelled
- Some users prefer email for the 24-hour reminder and SMS for the 1-hour one
- For virtual appointments, include the meeting link in every reminder

---

## Post-Service Review Request

**Purpose:** Ask for a Google review after a service is completed.

**Typical trigger:** Pipeline Stage Changed (filtered to "completed" or "service delivered") or Appointment Status Changed (filtered to "showed")

```
Step 1: Wait 2 hours
  Reason: Give the contact time after the service. Don't ask for a review immediately.

Step 2: Send SMS
  Config: "Hi [first name], thanks for choosing [business name]. If you had a good experience, we'd really appreciate a quick Google review: [review link]"

Step 3: Wait 3 days (from Step 2)

Step 4: If/Else - has tag "review-left"?
  YES: Send Email (thank you message), end workflow
  NO: Continue

Step 5: Send Email
  Config: Friendly follow-up asking for the review. Include the direct review link. Keep it short.

Step 6: Add Tag ("review-requested")
  Reason: Prevents this contact being asked again if they enter the workflow a second time.
```

**Notes:**
- The "review-left" tag check at Step 4 requires a separate process to tag contacts who've left reviews (manual or via integration)
- Include the direct Google review link, not a link to the Google Business Profile page
- Only one follow-up. Two review requests is enough. More than that is annoying.
- Consider adding an If/Else at the start to check for "review-requested" tag to prevent repeat requests

---

## Pipeline Stage Automation

**Purpose:** Automate internal actions when an opportunity moves through pipeline stages.

**Typical trigger:** Pipeline Stage Changed

```
Step 1: If/Else - which stage?

  Stage = "New Lead":
    Step 1a: Assign to User (round-robin or specific)
    Step 1b: Create Task ("Follow up with new lead within 24 hours")
    Step 1c: Send Internal Notification

  Stage = "Proposal Sent":
    Step 1d: Wait 3 days
    Step 1e: If/Else - still in "Proposal Sent"?
      YES: Create Task ("Follow up on proposal")
      NO: End (they've moved to another stage)

  Stage = "Won":
    Step 1f: Add Tag ("client-active")
    Step 1g: Add to Workflow ("Client Onboarding Sequence")
    Step 1h: Send Internal Notification ("Deal won!")

  Stage = "Lost":
    Step 1i: Add Tag ("deal-lost")
    Step 1j: Wait 30 days
    Step 1k: Add to Workflow ("Re-engagement Sequence")
```

**Notes:**
- This is often better split into separate workflows per stage rather than one big branching workflow
- The "still in Proposal Sent?" check prevents follow-up tasks being created for deals that have already moved
- Won and Lost actions are where the user's other workflows get triggered, so tag naming matters here

---

## Client Onboarding Sequence

**Purpose:** Guide a new client through the onboarding process after they sign up or pay.

**Typical trigger:** Tag Added (filtered to "client-active") or Invoice Status Changed (filtered to "paid") or Opportunity Status Changed (filtered to "won")

```
Step 1: Send Email (immediate)
  Config: Welcome email with what to expect, next steps, and any forms they need to fill in.

Step 2: Create Task ("Set up client account")
  Config: Assign to the relevant team member.

Step 3: Send Internal Notification
  Config: Notify the team about the new client.

Step 4: Wait 1 day

Step 5: Send Email
  Config: Check-in email. "Have you had a chance to [complete the form / review the welcome pack]?"

Step 6: Wait 3 days (from Step 5)

Step 7: If/Else - has tag "onboarding-complete"?
  YES: Send Email (welcome to the team, here are your resources), end workflow
  NO: Continue

Step 8: Send SMS
  Config: "Hi [first name], just checking in on your onboarding. Need any help getting started?"

Step 9: Wait 4 days (from Step 8)

Step 10: If/Else - has tag "onboarding-complete"?
  YES: Send Email (welcome message), end workflow
  NO: Create Task ("Follow up with client - onboarding stalled"), Send Internal Notification
```

**Notes:**
- The "onboarding-complete" tag needs to be added manually or by another workflow when the client finishes the required steps
- Adjust the number of follow-ups based on how involved the onboarding process is
- For high-value clients, the SMS and email follow-ups might be replaced with tasks for personal phone calls

---

## Re-engagement / Win-Back Sequence

**Purpose:** Re-engage contacts who went cold or deals that were lost.

**Typical trigger:** Tag Added (filtered to "deal-lost" or "gone-cold") or custom timing

```
Step 1: Wait 30 days
  Reason: Give it enough time that the contact doesn't feel pestered.

Step 2: Send Email
  Config: Low-pressure check-in. Not a sales email. "Hi [first name], just wanted to see how things are going with [their original need]."

Step 3: Wait 7 days (from Step 2)

Step 4: If/Else - Customer Replied?
  YES: Create Task ("Respond to re-engaged lead"), end workflow
  NO: Continue

Step 5: Send Email
  Config: Value-add content. A useful resource, blog post, or tip related to their original interest.

Step 6: Wait 14 days (from Step 5)

Step 7: Send Email
  Config: Soft offer. "If you're still looking for help with [topic], we'd love to chat. Here's a link to book a call: [calendar link]"

Step 8: Remove Tag ("deal-lost" or "gone-cold")
Step 9: Add Tag ("re-engagement-complete")
```

**Notes:**
- Keep the tone helpful, not desperate
- Three touchpoints over about 7-8 weeks is usually enough
- If they don't re-engage, don't keep emailing. The "re-engagement-complete" tag prevents them entering this workflow again
- Consider adding them to a long-term newsletter or monthly update list instead of another direct sequence
