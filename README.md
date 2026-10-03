# Field Service Cloud Workflows for Claude

Ask Claude about your landscape maintenance company's Field Service Cloud records, and have it prepare a manager's Morning Brief, an internal Manager Operations Review, or a customer-ready Monthly Client Report.

This plugin connects Claude to the Field Service Cloud MCP server (`https://www.janmarsystems.com/mcp`) and includes two skills: **Operations** and **Monthly Client Report**. It requires a Field Service Cloud account from [Janmar Systems](https://www.janmarsystems.com/fieldservicecloud).

## What you can do

**Operations** (internal use by owners, managers, and office staff)
- **Morning Brief:** one manager's daily handoff. What each crew has planned today, whether each crew covered its scheduled jobsites on the prior workday, which customers can be updated now, and what needs follow-up and why.
- **Manager Operations Review:** a look back at one manager's crews over an exact period of up to 31 days, comparing the route schedule, recorded visits, and task records.
- **Property questions:** recent visits, open tasks, forms and inspections, irrigation, pesticide records, and materials used at a jobsite.

**Monthly Client Report** (for the landscape company's office to review before sending to a property manager or HOA)
- A client-ready monthly service update for one jobsite: services completed and what each was for, inspections and irrigation or enhancement work, site observations, and relevant follow-up.
- Works from a short request and produces an editable Word report, a matching PDF, and a separate office note for items the customer should not see.
- Uses verified photos with supported or neutral captions.

## Example requests

- "Give me my morning brief for today." (Claude will ask for your local date if it is not clear.)
- "Review last week for [manager name]."
- "What needs follow-up at [jobsite name]?"
- "Please prepare the August 2026 monthly client report for [client or jobsite name]."

Select a skill with `/` or **+** in the message box, or describe the task and Claude loads the matching skill.

## What the connector can see

The connector is **read-only**. It cannot create, change, or delete anything in Field Service Cloud, and it cannot send email or reports for you. Within the permissions of the signed-in user, it can read:

- Customers and jobsites (property details and visit history)
- Tasks, checklists, estimates and items used
- Forms and inspections, irrigation history, pesticide application records, and inventory material use
- Crew visits, service exceptions, contracted-service completions, and operating summaries
- Selected task photos, returned through the authenticated connection

Each user sees only what their own Field Service Cloud account is permitted to see.

## Requirements

- A Field Service Cloud account, and a company Admin who has enabled MCP access (step 1 below).
- A paid Claude plan that supports plugins, with **Code execution and file creation** turned on in Claude's settings. The Monthly Client Report creates Word and PDF files.
- Each person who uses the connector signs in with their own Field Service Cloud account and approves access.

## Install, connect, and verify

Complete these steps in order:

1. Ask a Field Service Cloud company Admin to enable MCP access under **Company
   Settings > Manage company AI connectors**.
2. In Claude, open **Customize > Plugins**, add **Field Service Cloud
   Workflows**, and enable the plugin.
3. Open the bundled **Field Service Cloud** connector, select **Connect**,
   sign in with your own Field Service Cloud account, confirm the intended
   company, and approve read-only access. In **Tool permissions**, choose
   **Always allow** for the **Read-only tools** group when your workspace
   policy permits it so report lookups do not prompt one at a time; write
   tools remain gated.
4. If a client report must include photos, keep the connector's read-only
   access enabled and let the report skill call the advertised
   `get_attachments` operation with selected attachment IDs.
   The connector returns original photo bytes as image content through the
   authenticated MCP connection; the skill handles saving and embedding them. Do not add
   S3 or local-attachment hosts to Claude's network allowlist and do not expect
   direct attachment URLs in the business-data response.
5. Start a new Chat or Cowork task. Use `/` or **+** to select **Operations**
   for a Morning Brief or internal review. For a Monthly Client Report,
   select **Monthly Client Report** only; it works independently.
6. Run one small single-manager Operations brief test with an exact local date,
   then a separate jobsite-and-month Monthly Client Report test before regular
   use. Review the returned manager scope, today's activity, recent qualifying
   activity, follow-up coverage, facts, service purposes, photos, captions, and
   every generated page.

If the plugin is enabled but the connector is missing or disconnected, check
the company Admin toggle, reconnect with the intended Field Service Cloud
account, and start a new task. A 401/403 normally means the OAuth session or
company/user permission is wrong; it is not fixed by reinstalling the plugin.
Keep only one Field Service Cloud connection enabled. If a manual connector is
already present, keep it and upload the two individual skills instead of using
the bundled connector.

## Your data and privacy

Installing this plugin does not grant access by itself. A company Admin must first enable MCP access in Field Service Cloud, and each user must sign in and authorize the named application with their own account. This company permission covers all compatible MCP applications; no separate Claude approval or switch is required.

When you approve an application, the records it requests are sent to that application at your direction. Anthropic handles that information under its own terms and privacy policy. A company Admin can turn off AI connections for the whole company in Company Settings, and any user can disconnect the connector in Claude at any time.

Read the Janmar Systems [Privacy Policy](https://www.janmarsystems.com/fieldservicecloud/privacy).

## Customizing the skills

The included skills are starting points. You may customize a copy for your company's headings, branding, ordering, and emphasis. Preserve the read-only connector, factual and date safeguards, verified-photo rules, and office review before sharing client-facing reports. Review the proposed changes and test a customized copy on one jobsite before regular use.

## Support

Questions or problems: [support@janmarsystems.com](mailto:support@janmarsystems.com). We typically reply within one business day. Product information: [Field Service Cloud](https://www.janmarsystems.com/fieldservicecloud).

## License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE). Copyright Janmar Systems.
