# Field Service Cloud Workflows

Skills and a read-only connection that let Claude work with your [Field Service Cloud](https://www.janmarsystems.com/fieldservicecloud/solutions) records. Field Service Cloud is Janmar Systems' software for landscape maintenance companies. With this plugin, managers and office staff can review crews, routes, recorded visits, tasks, inspections and jobsite photos, prepare operations briefs and manager reviews, and produce monthly client reports as Word and PDF files with separate office notes.

## Before you start

- You need a Field Service Cloud account.
- A company Admin must enable MCP access for your company first.
- Word/PDF reports and selected-photo reports require Claude file tools that can create, download and view the files. The skills check those capabilities before retrieving selected photos.
- Each person connects with their own account and approves read-only access. The connection only returns records that account is already allowed to see; selecting a manager does not widen those permissions.
- Installing the plugin does not grant access to any data.

## Install

1. Add **Field Service Cloud Workflows** from the Claude directory and enable it. To install manually instead, download this repository as a ZIP and upload it under Customize > Plugins.
2. Connect the Field Service Cloud connector with your own account and approve read-only access.
3. In a new Chat or Cowork task, choose a skill using `/` or `+`.

If you already added a Field Service Cloud connection by hand, keep it and use the plugin's skills with it. Use only one Field Service Cloud connection in a conversation. When you update the plugin, replace older copies of these skills.

## Skills

- **Connector Instructions** helps with everyday questions about saved jobsite, task, service and follow-up records.
- **Workspace** opens an interactive workspace for a manager's portfolio (Operations) or a single jobsite (Property) when the connection offers it. Choose the period, records and photos before drafting. Expand a record to see the saved text in its original wording and in a translation into your chosen language; the saved record is not changed.
- **Operations** prepares a current Operations Brief for the manager's authorized crews, a Morning Brief for a date you choose, or a Manager Operations Review for an exact period. Each separates recorded work from current follow-up.
- **Estimate Proposal** creates a customer proposal from an existing Extra with saved scope/pricing and a standard or attached template. Workspace adds an independent Estimates tab for its selections.
- **Monthly Client Report** prepares a Word and/or PDF client report and separate office notes for one jobsite and one calendar month. It works independently of Operations.

If the workspace is not available on your connection, the other skills still work for ordinary read-only questions and reports.

## Example requests

- "Open the Field Service Cloud workspace and wait for my manager, property and period choices."
- "Give me the current operations brief for [manager]."
- "Prepare the morning brief for [manager] for [date]."
- "Review operations for [manager] from [start date] through [end date]."
- "Prepare the monthly client report for [jobsite] for [month/year], with selected photos."

## How the skills behave

- Claude asks for a missing or ambiguous jobsite, manager or date instead of guessing. A current brief uses the company date and time returned by Field Service Cloud and does not ask for a date.
- Missing records are reported as missing; they are not treated as proof that no work happened.
- Reports keep your wording, record selections and photo captions through refinement. Claude checks the selected images and every page of the Word and PDF files before offering them.
- Report preparation does not approve or send anything. Files are for your office to review before you share them with a client.

## Data handling and privacy

- This plugin contains five instruction-based skills and one remote MCP connection setting. It has no bundled executables, hooks or local servers.
- The only remote MCP server configured by this plugin is Field Service Cloud at `https://www.janmarsystems.com/mcp`. Claude uses its built-in file tools to prepare reports and save selected photo bytes returned by Field Service Cloud.
- The connection is read-only. It cannot change Field Service Cloud records, schedule work, or send reports or email.
- Records returned to Claude can include customer and contact names, jobsite addresses, crew names, task notes, estimate selling prices, inspection answers and selected photos. They are handled inside your Claude conversation under your Claude settings. Report files are created in Claude's own file workspace with Claude's built-in file tools.
- A company Admin can turn off MCP access, and each person can disconnect the connector at any time. Removing the plugin does not delete Field Service Cloud records or files in your Claude conversations.
- Field Service Cloud keeps your account data under its [Privacy Policy](https://www.janmarsystems.com/fieldservicecloud/privacy).

## Troubleshooting

If the connection fails, check that your company Admin has enabled MCP access, that you signed in with the intended account and company, and that the connector is authorized. Then start a new conversation.

## About

Publisher: [Janmar Systems](https://www.janmarsystems.com/fieldservicecloud/solutions). [Support](https://www.janmarsystems.com/Help/ContactUs), [Privacy](https://www.janmarsystems.com/fieldservicecloud/privacy), [Terms](https://www.janmarsystems.com/fieldservicecloud/terms). Source: https://github.com/JanmarSystems/field-service-cloud-workflows. Licensed under Apache-2.0; see LICENSE.

## Customer estimates

Ask: "Create a customer proposal from Extra [number] at [jobsite]." Or open Workspace, choose Estimates, select the jobsite and load an Extra. Review the saved pricing, choose what to include, and request Word, PDF or both. To use your own template, attach it in the conversation and enter its filename in Estimates. The assistant must open the attachment before using it. Review generated pages and unresolved currency, tax, prices and terms before sharing. This workflow does not save or send estimates.
