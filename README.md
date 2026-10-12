# Field Service Cloud Workflows

For Claude, open Customize > Plugins, upload the ZIP and enable it, then connect the bundled Field Service Cloud connector with your own account and approve read-only access. In a fresh Chat or Cowork task, choose a skill using / or +. If a manual connection is already present, keep it and import the individual skills instead of adding a duplicate connection. The report skills preserve Claude's file-workspace prerequisite before selected-photo retrieval. Directory submission/publication is separate.

The read-only connector accesses records authorized for the signed-in Field Service Cloud account. A company Admin must enable MCP access first, and each person connects with their own account. Installing this package does not grant access or deploy the hosted server or workspace.

Four sample skills are included:

- **Connector Instructions** guides everyday questions about saved records and follow-up.
- **Workspace** opens manager-portfolio Operations or single-jobsite Property when the connection advertises workspace tools. Choose the period, records and photos before drafting. Expand a record to request Original and Translation in your chosen language; the saved text stays unchanged.
- **Operations** prepares a server-current Operations Brief for the returned authorized scope, an intentionally dated Morning Brief or an exact-period Manager Operations Review, separating recorded work from current follow-up.
- **Monthly Client Report** prepares Word/PDF client reports and separate office notes for one jobsite and calendar month. It works independently of Operations.

Each report workflow loads its included connector guidance. Keep office wording, source selections and photo captions through refinement. Inspect selected images and every requested report page before sharing files. Report preparation does not approve or send a report. If workspace tools are unavailable, ordinary read-only questions and report skills remain usable.

Example requests:

- "Open the Field Service Cloud workspace and wait for my manager, property and period choices."
- "Give me the current operations brief for [manager]."
- "Prepare an intentionally dated morning brief for [manager] for [local date]."
- "Review operations for [manager] from [start date] through [end date]."
- "Prepare the monthly client report for [jobsite] for [month/year], with selected photos."

Clarify ambiguous properties and managers, and missing or relative dates for intentionally dated requests. Current briefs use the returned company date, capture time and time zone without a date question. Missing records do not prove no work occurred. Manager selection does not broaden account permissions. Connect only one Field Service Cloud connection in a conversation and replace older copies of these skills when updating. If connection fails, check company MCP access, the intended account/company and OAuth connection, then start a fresh conversation.

The production server address is `https://www.janmarsystems.com/mcp`. Private development test connections are separate and are not included. These instructions match portable source 6.19.0 and Claude distribution 1.37.0. Manager Operations Reports lead with customer updates, property follow-up, meaningful completed work and established upcoming dates; period service results remain distinct from present-day follow-up. Bundled installation, production reviewer and directory acceptance require separate verification. The hosted workspace requires its corresponding server release. This archive alone does not establish production deployment or directory acceptance.

Publisher: [Janmar Systems](https://www.janmarsystems.com/fieldservicecloud/solutions). [Support](https://www.janmarsystems.com/Help/ContactUs), [Privacy](https://www.janmarsystems.com/fieldservicecloud/privacy), [Terms](https://www.janmarsystems.com/fieldservicecloud/terms). Source: https://github.com/JanmarSystems/field-service-cloud-workflows. Repository visibility and provider submission are separate release steps. Licensed under Apache-2.0; see LICENSE.
