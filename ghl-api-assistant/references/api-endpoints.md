# Common GHL API Endpoints

Example requests for the most commonly used GHL API endpoints. All examples use curl with Private Integration Token authentication. Replace placeholder values (YOUR_TOKEN_HERE, LOCATION_ID, etc.) with real values.

These curl examples can be pasted directly into Postman's URL bar and it will auto-format the method, headers, and body for you. They also translate directly into HTTP module settings in Make/n8n.

Every request needs these headers:
```
Authorization: Bearer YOUR_TOKEN_HERE
Version: 2021-07-28
```

Most POST/PUT requests also need:
```
Content-Type: application/json
```

---

## Contacts

### Create a Contact

```bash
curl --request POST \
  --url 'https://services.leadconnectorhq.com/contacts/' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "firstName": "John",
    "lastName": "Doe",
    "email": "john@example.com",
    "phone": "+441234567890",
    "locationId": "LOCATION_ID"
  }'
```

`locationId` is required. Everything else is optional but you'll want at least a name and an email or phone.

### Upsert a Contact (Create or Update)

This is usually what you want instead of separate create/update calls. It creates the contact if they don't exist, or updates them if they do. Matching is based on your location's "Allow Duplicate Contact" settings (email, phone, or both).

```bash
curl --request POST \
  --url 'https://services.leadconnectorhq.com/contacts/upsert' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "firstName": "John",
    "lastName": "Doe",
    "email": "john@example.com",
    "phone": "+441234567890",
    "locationId": "LOCATION_ID"
  }'
```

### Get a Contact

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/contacts/CONTACT_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

### Search Contacts

The old "Get Contacts" endpoint (`GET /contacts/`) is deprecated. Use the advanced search endpoint instead:

```bash
curl --request POST \
  --url 'https://services.leadconnectorhq.com/contacts/search' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "locationId": "LOCATION_ID",
    "page": 1,
    "pageLimit": 20,
    "filters": [
      {
        "field": "email",
        "operator": "eq",
        "value": "john@example.com"
      }
    ]
  }'
```

This endpoint supports advanced filter combinations. Check the official docs for the full list of filterable fields and operators: https://marketplace.gohighlevel.com/docs/ghl/contacts/search-contacts-advanced/

**Note:** The older `GET /contacts/?locationId=X&query=Y` endpoint still works for simple lookups but is marked as deprecated. Use `POST /contacts/search` for anything new.

### Update a Contact

```bash
curl --request PUT \
  --url 'https://services.leadconnectorhq.com/contacts/CONTACT_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "firstName": "Jane",
    "tags": ["client-active", "vip"]
  }'
```

Only include the fields you want to change. Fields you don't include stay as they are.

### Delete a Contact

```bash
curl --request DELETE \
  --url 'https://services.leadconnectorhq.com/contacts/CONTACT_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

---

## Tags

### Add Tags to a Contact

```bash
curl --request POST \
  --url 'https://services.leadconnectorhq.com/contacts/CONTACT_ID/tags' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "tags": ["tag-name-1", "tag-name-2"]
  }'
```

### Remove a Tag from a Contact

```bash
curl --request DELETE \
  --url 'https://services.leadconnectorhq.com/contacts/CONTACT_ID/tags' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "tags": ["tag-to-remove"]
  }'
```

---

## Custom Fields

### Get Custom Fields for a Location

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/locations/LOCATION_ID/customFields' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

This returns all custom fields with their IDs, names, and types. You need the field **ID** (not the name) to set values on contacts.

### Set a Custom Field Value on a Contact

Custom field values are set through the contact update endpoint. You can use either the field ID or the field key. The key is easier to find because it's the part after `contact.` in the custom field reference. For example, if your custom field's merge tag is `{{contact.custom_field_for_testing}}`, the key is `custom_field_for_testing`.

```bash
curl --request PUT \
  --url 'https://services.leadconnectorhq.com/contacts/CONTACT_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "customFields": [
      {
        "key": "custom_field_for_testing",
        "value": "the value you want to set"
      }
    ]
  }'
```

You can also use `"id"` instead of `"key"` if you have the field ID, but the key is usually quicker to find.

---

## Opportunities (Pipeline)

### Get Pipelines

Run this first to find your pipeline IDs and stage IDs:

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/opportunities/pipelines?locationId=LOCATION_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

### Search Opportunities

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/opportunities/search?location_id=LOCATION_ID&pipeline_id=PIPELINE_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

### Create an Opportunity

```bash
curl --request POST \
  --url 'https://services.leadconnectorhq.com/opportunities/' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "pipelineId": "PIPELINE_ID",
    "locationId": "LOCATION_ID",
    "name": "Deal name",
    "pipelineStageId": "STAGE_ID",
    "status": "open",
    "contactId": "CONTACT_ID",
    "monetaryValue": 1500
  }'
```

### Update an Opportunity

```bash
curl --request PUT \
  --url 'https://services.leadconnectorhq.com/opportunities/OPPORTUNITY_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "status": "won",
    "monetaryValue": 2000
  }'
```

---

## Conversations

### Search Conversations

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/conversations/search?locationId=LOCATION_ID&contactId=CONTACT_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

### Send a Message

```bash
curl --request POST \
  --url 'https://services.leadconnectorhq.com/conversations/messages' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Content-Type: application/json' \
  --header 'Version: 2021-07-28' \
  --data '{
    "type": "SMS",
    "contactId": "CONTACT_ID",
    "message": "Hi, this is a test message"
  }'
```

Change `type` to `"Email"` for email. Email messages also need `subject` and `html` fields.

---

## Calendars and Appointments

### Get Calendars

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/calendars/?locationId=LOCATION_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

### Get Appointments

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/calendars/events?locationId=LOCATION_ID&calendarId=CALENDAR_ID&startTime=1700000000000&endTime=1700604800000' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

`startTime` and `endTime` are Unix timestamps in milliseconds.

---

## Locations (Sub-accounts)

### Get a Location

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/locations/LOCATION_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

### Search Locations (Agency Level)

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/locations/search?companyId=COMPANY_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

---

## Users

### Get Users for a Location

```bash
curl --request GET \
  --url 'https://services.leadconnectorhq.com/users/?locationId=LOCATION_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

---

## Workflows

### Add a Contact to a Workflow

```bash
curl --request POST \
  --url 'https://services.leadconnectorhq.com/contacts/CONTACT_ID/workflow/WORKFLOW_ID' \
  --header 'Authorization: Bearer YOUR_TOKEN_HERE' \
  --header 'Version: 2021-07-28'
```

---

## Finding IDs

Most operations require IDs. Here's where to find them:

- **locationId**: In GHL, go to Settings > Business Profile. Also visible in the URL when you're inside a sub-account. Or use the Search Locations endpoint.
- **contactId**: Visible in the URL when you're viewing a contact in GHL (e.g. `contacts/detail/CONTACT_ID`). You can also search via the API by email or phone.
- **pipelineId and stageId**: Visible in the URL when you're viewing a pipeline in GHL. Or use the Get Pipelines endpoint.
- **custom fields**: Use the field key rather than the ID when updating contacts. The key is the part after `contact.` in the merge tag (e.g. `{{contact.my_custom_field}}` means the key is `my_custom_field`). If you do need the ID, use the Get Custom Fields endpoint.
- **workflowId**: Go to Automation > Workflows in GHL, click on the workflow, and the ID is in the URL.

---

## Pagination

Different endpoints use different pagination approaches:

**POST /contacts/search** uses page-based pagination. Set `page` and `pageLimit` in the request body. Increment `page` to get the next batch.

**Older GET endpoints** (like `GET /contacts/`) use cursor-based pagination with `startAfter` (a Unix timestamp in milliseconds) and `startAfterId` (the contact ID) as query parameters. These values come back in the response metadata. Pass them into your next request to get the next page. Keep going until the response returns fewer results than your limit.

Default results per page is typically 20. Maximum is usually 100. Check the specific endpoint docs for exact limits.

---

## Full API Reference

This covers the most common endpoints. The full API includes many more (forms, surveys, invoices, payments, courses, social planner, funnels, and more).

For anything not listed here, check the official docs: https://marketplace.gohighlevel.com/docs/
