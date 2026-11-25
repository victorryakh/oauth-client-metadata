# OAuth Client ID Metadata Document

Public client metadata for the ZenMoney MCP server (`https://api.zenmoney.app/mcp`).

ZenMoney's authorization server does not implement dynamic client registration
(RFC 7591). It accepts clients that identify themselves by a URL pointing to
this document instead (OAuth Client ID Metadata Document).

Consumers of this document:

- `client_id` must equal the URL the document is served from.
- `redirect_uris` must list the exact OAuth callback used by the client.
- `token_endpoint_auth_method: none` — public client, PKCE only.

Used by the `zenmoney` entry in `~/.mcporter/mcporter.json`:

    "zenmoney": {
      "baseUrl": "https://api.zenmoney.app/mcp",
      "oauthClientMetadataUrl": "https://victorryakh.github.io/oauth-client-metadata/oauth-client.json",
      "oauthRedirectUrl": "http://127.0.0.1:8989/callback"
    }
