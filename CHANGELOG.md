# Changelog

## [1.1.0] - 2026-09-15

* A menu of nine jobs: find creators, build a media plan, check creators' quality, audience overlap,
  campaign manager, audience segments, team activity, daily briefing, quick competitor research. Each
  job hands the assistant its steps. Slash commands go from 11 to 14: `/yoloco_quality`,
  `/yoloco_tracking`, `/yoloco_team` and `/yoloco_daily`, which replaces `/yoloco_campaign_daily`.
* Smart creator search: a search plan across networks from the brief, strategies sized and previewed
  for free, one ranked list with the reasons each creator fits and flags for doubtful metrics, public
  pages and shops (`search_plan_run`, `niche_lookup`, `search_feedback`). 58 tools.
* The market comes first and is never guessed: a region, a market or a country (7 regions, 29
  markets, 199 countries); a region is searched as its countries in one filter.
* One shape for creators and posts in every answer, each with a link. Post fields in competitor and
  campaign results are now `published_at`, `text`, `er_percent` and an `author` object.
* Competitor research: repeat placements and creators working with several of the report's brands;
  several brands described in one call.
* Pasted links resolved in one call (up to 50); a list of picked creators in one call; creators added
  to a list arrive with their numbers, and refreshing a list's data is free.
* Team activity per colleague: reports, coins, creators opened, searches, idle members.

## [1.0.0] - 2026-09-14

First public release of the hosted server at `https://mcp.yoloco.io/platform/mcp`.

* OAuth 2.1 with PKCE and dynamic client registration; consent page in the Yoloco app.
* 55 tools and 11 slash commands: creator search, look-alikes, reports and comparison on
  Instagram, TikTok, YouTube and Telegram; lists and folders; media plans with planned CPM;
  audience overlaps and the best set; segments; competitor ads; campaigns from media plans,
  plan against fact and a morning brief; team notes. Search parameters and dictionaries are
  served on demand, so the tool list stays small for the assistant.
* Price quoted and confirmed in the chat before any paid action, paid search pages included;
  the billing refuses anything above the confirmed price.
* Refresh-token rotation with replay detection; callbacks checked by scheme and host.
* Connections list, revocation and 30-day spend report in Settings → Integrations →
  AI assistant.
