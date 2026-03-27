# GHL Workflow Triggers and Actions

This is the list of triggers and actions available in GHL workflows. **Only recommend items from this list.** Do not invent actions, conditions, or features that are not listed here.

---

## Triggers

A workflow has exactly one trigger. This is the event that starts the workflow.

### Contact Triggers
- **Contact Created** - fires when a new contact is added to the CRM
- **Contact Tag Added** - fires when a specific tag is added to a contact
- **Contact Tag Removed** - fires when a specific tag is removed from a contact
- **Contact Changed** - fires when a contact field is updated
- **Custom Field Changed** - fires when a specific custom field value changes
- **Contact DND** - fires when a contact's Do Not Disturb status changes

### Form and Survey Triggers
- **Form Submitted** - fires when a contact submits a specific form
- **Survey Submitted** - fires when a contact submits a specific survey

### Pipeline Triggers
- **Pipeline Stage Changed** - fires when a contact/opportunity moves to a different pipeline stage
- **Opportunity Status Changed** - fires when an opportunity status changes (open, won, lost, abandoned)

### Appointment Triggers
- **Appointment Status Changed** - fires when an appointment status changes (booked, confirmed, showed, no-showed, cancelled, rescheduled)

### Communication Triggers
- **Customer Replied** - fires when a contact replies via any channel
- **Inbound Webhook** - fires when an external system sends data to the workflow webhook URL

### Invoice Triggers
- **Invoice Status Changed** - fires when an invoice status changes (sent, viewed, paid, void)

### Membership Triggers
- **Membership New Signup** - fires when someone signs up for a membership
- **Membership Category Completed** - fires when a member completes a category

---

## Actions

These are the steps you can add to a workflow after the trigger.

### Communication Actions
- **Send Email** - send an email to the contact (use a template or custom content)
- **Send SMS** - send an SMS to the contact
- **Send Internal Notification** - notify a team member via email or in-app notification
- **Send to Voicemail** - send a ringless voicemail to the contact

### Contact Management Actions
- **Add Tag** - add a tag to the contact
- **Remove Tag** - remove a tag from the contact
- **Set Contact Field** - update a standard or custom field value on the contact
- **Remove from Workflow** - remove the contact from a specific workflow
- **Add to Workflow** - add the contact to another workflow
- **Assign to User** - assign the contact to a specific team member or round-robin

### Pipeline Actions
- **Create Opportunity** - create a new opportunity in a pipeline
- **Update Opportunity** - change the value, status, or pipeline stage of an existing opportunity
- **Move to Pipeline Stage** - move the contact's opportunity to a specific stage

### Task Actions
- **Create Task** - create a task assigned to a team member

### Webhook Actions
- **Send Webhook** - send data to an external URL (use for integrations and API calls)

### Logic Actions
- **Wait** - pause the workflow for a set duration (minutes, hours, days) or until a condition is met (e.g., wait until a tag is added, wait until a specific date/time)
- **If/Else** - branch the workflow based on a condition. Conditions can check contact fields, tags, appointment status, opportunity status, email open/click activity, and more.
- **Go To** - jump to another step in the workflow

### Other Actions
- **Math Operation** - perform a calculation and store the result in a custom field
- **Manual Call** - prompt a team member to make a phone call to the contact

---

## Important Notes

### Wait Step Timing
Wait steps are relative to the previous step, not the workflow entry. Always calculate backwards:
- If you want something to happen 3 days after entry and 5 days after entry, the second wait is 2 days (5 minus 3), not 5 days.

### If/Else Conditions
If/Else can check:
- Contact field values (standard or custom)
- Whether a tag is present or absent
- Appointment status
- Opportunity status and pipeline stage
- Email activity (opened, clicked, replied)
- Time-based conditions (day of week, time of day)

### Trigger Filters
Most triggers support filters so the workflow only fires for specific cases. For example:
- Form Submitted can filter by which form
- Tag Added can filter by which tag
- Pipeline Stage Changed can filter by which pipeline and which stage
- Appointment Status can filter by which calendar and which status

### What Doesn't Exist
Common things users ask for that are **not** available as workflow actions:
- Sending messages via WhatsApp directly from a workflow action (this requires a third party integration or webhook)
- Automatically creating invoices (invoices are created manually or via API)
- Directly updating Google Sheets or external databases (use Send Webhook to push data out)
- Conditional waits based on payment status without using tags or custom fields as intermediaries
