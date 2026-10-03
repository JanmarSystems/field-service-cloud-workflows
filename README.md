# Field Service Cloud Workflows for Claude

This plugin connects Claude to the Field Service Cloud MCP server (`https://www.janmarsystems.com/mcp`) and includes Janmar's Operations and Monthly Client Report skills. It requires a Field Service Cloud account from Janmar Systems.

The connector is read-only. Installing this plugin does not grant access by itself: a company Admin must first enable MCP access in Field Service Cloud, and each user must sign in and authorize the named application with their own Field Service Cloud account. This company permission covers all compatible MCP applications; no separate Claude approval or switch is required. Retrieved data is shared with the application you authorize.

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

The included skills are starting points. You may customize a copy for your company's headings, branding, ordering, and emphasis. Preserve the read-only connector, factual and date safeguards, verified-photo rules, and office review before sharing client-facing reports. Review the proposed changes and test a customized copy on one jobsite before regular use.

## License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE). Copyright Janmar Systems.
