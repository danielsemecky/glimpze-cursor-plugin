# Glimpze for Cursor

Connect Cursor to your [Glimpze](https://www.glimpze.io/) support workspace. Glimpze brings website chat, AI assistance and live video calls into one customer conversation. This plugin lets you review authorized conversations and call history, find recurring customer questions, and work with your support knowledge and widgets from Cursor.

## Connect

1. Install this plugin in Cursor and enable its **glimpze** MCP server.
2. Choose **Connect** to open Glimpze's existing sign-in and consent flow.
3. Sign in to your own Glimpze account. Select the projects and capabilities you want to share. Start with read permissions if you only want to review information.
4. Return to Cursor and confirm that the server is connected.

You need a Glimpze account and access to a project. Available tools depend on the permissions you approve and your current role. Installing this plugin alone does not grant access to any workspace. Account-wide capabilities require separate consent.

For a manual connection, add this configuration to Cursor's MCP settings and connect:

```json
{
  "mcpServers": {
    "glimpze": {
      "url": "https://api.glimpze.io/functions/v1/mcp"
    }
  }
}
```

No API key, shared credential or local server process is included. The connection uses Glimpze's existing OAuth authorization and hosted Streamable HTTP endpoint.

## Things to try

- “Summarize the unresolved conversations in my selected Glimpze project and link to the relevant conversations.”
- “Find recurring customer questions in this project's recent conversations.”
- “Show the available call history for this conversation and summarize any available transcript.”
- “Review this project's knowledge sources and identify questions that need better answers.”

Call history, recordings and transcripts depend on the selected project's configuration, permissions and available data. This plugin does not join or initiate a live call. Use the Glimpze dashboard and website widget for the interactive call experience.

## Permissions and data

Your Glimpze permissions remain authoritative. Read tools retrieve only information available to your connection. If you approve write capabilities, some tools can change settings, maintain knowledge sources or send messages; request only the operations you intend to perform and review their effects before proceeding.

Requested information, including customer messages, visitor details and available call content, can be returned to Cursor. Use the connection only for projects whose information you are authorized to share with your AI assistant. The plugin does not upload local source code or files by itself. It contains no scripts, hooks, background tasks or telemetry.

You can revoke the connection from Glimpze's **Integrations → AI agents (MCP)** settings. Removing the plugin from Cursor also removes its configuration; revoke the Glimpze connection when you want to end its authorization.

## Troubleshooting

- **No tools or missing tools:** confirm the connection is enabled, sign in again if needed, and check the selected project, granted capabilities and your current Glimpze role.
- **Permission denied:** request the relevant capability only if you need it and are authorized to use it. Installing the plugin does not bypass project membership.
- **Connection blocked by your organization:** ask your Cursor administrator to allow the Glimpze MCP endpoint according to your organization's policy.

## Documentation and support

- [Glimpze MCP documentation](https://www.glimpze.io/docs/mcp)
- [Glimpze help](https://www.glimpze.io/faq)
- [Pricing](https://www.glimpze.io/pricing)
- [Privacy policy](https://www.glimpze.io/privacy)
- [Terms of service](https://www.glimpze.io/terms)
- Support and security reports: [support@glimpze.io](mailto:support@glimpze.io)

## Package contents and license

This repository contains only the Cursor plugin manifest, remote connection configuration, documentation and public brand asset. Glimpze's hosted application and MCP server implementation are separate services and are not included.

The files in this repository are licensed under the [MIT License](LICENSE). That license does not grant rights to Glimpze's trademarks or to the separate hosted service.
