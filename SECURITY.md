# Security

The Yoloco MCP server is a hosted remote server at `https://mcp.yoloco.io/platform/mcp`.
This page describes what an AI client gets when a person connects it.

## Authentication

* OAuth 2.1 authorization code flow with PKCE and dynamic client registration. No API keys and no
  shared secrets.
* Consent happens on `https://app.yoloco.io/mcp/consent`, inside the person's own Yoloco session.
  The page names the requesting client and where the authorization code will be delivered.
* Authorization codes are delivered only to HTTPS callbacks of supported AI clients, to plain-HTTP
  loopback addresses used by local clients, and to the registered app scheme of supported desktop
  clients. Plain HTTP off loopback, look-alike hosts, other schemes, user info and fragments are refused.
* Access tokens are short-lived and rotated together with refresh tokens on every refresh. Of two
  refreshes racing with one token exactly one succeeds. A refresh token presented again after it was
  rotated is treated as stolen: the whole connection is revoked and the event is audited.
* A password change or account deactivation ends every connection. Any connection can be revoked in the
  app: Settings → Integrations → AI assistant.

## Authorization

* Scopes: `platform:read`, `platform:write`, `platform:spend`. A connection granted only `platform:read` works for every free
  read; writes and spends then answer `forbidden_scope` instead of acting.
* Every tool call re-checks the account, its subscription and plan. The assistant can do what the person
  can do in the app, within the same limits and team, and nothing else.
* Identity comes only from the OAuth token. No tool accepts a user or subscription as an argument.

## Spending

* Every paid action (full reports, paid search pages, media plan additions, overlaps, segments, competitor
  reports, campaigns, bulk exports, list refreshes) first returns a summary with the price and a single-use
  confirmation token. The action runs only when the client calls again with that token, and only for the
  same request and price.
* The limit is enforced where coins are deducted, not only in the tools: during an assistant's call the
  billing refuses any charge above the confirmed price, so a price that moved in the meantime charges
  nothing and is quoted again.
* Spending requires the `platform:spend` scope; a connection without it cannot spend at all.
* Work that continues in the background after a confirmation (adding to a media plan, refreshing a list,
  building a segment) carries the confirmed price as a cap: the job stops before charging past it.
* Reports and search pages the team already paid for are reused instead of bought again.

## Failures

* Errors come back as a code and a plain message. Internal details (database, provider or host messages)
  are never returned to the AI client; the person gets an `incident_id` to quote to support instead.

## Data

* The server returns only data the account already has access to in Yoloco.
* Tool calls are logged for the account owner's audit with arguments shortened and free text omitted.
* What the AI provider stores from the conversation follows that provider's policy.

## Reporting a vulnerability

Please do not open a public issue. Write to **security@yoloco.io** with the subject "MCP security",
the steps to reproduce and the impact you see, or use GitHub's private vulnerability reporting on
this repository. We acknowledge reports within two business days and keep you informed until the
fix is deployed; the hosted server is updated by Yoloco, so there is nothing for you to upgrade.
