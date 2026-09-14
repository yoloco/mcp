# Tool catalogue

55 tools and 11 slash commands, as the server reports them on `tools/list` and `prompts/list`. Names are stable; descriptions here are the first line of what the assistant sees.

Every tool that spends coins returns the price first and runs only after you confirm it in the chat; search parameters, dictionaries and product rules are served on demand (`search_guide`, `dictionary_lookup`, `product_guide`) instead of living in every tool schema.

## Getting started (5)

| Tool | What it does | Effect |
|---|---|---|
| `yoloco_whoami` | Who you act for in Yoloco: account, subscription, balance, what the team built. FREE. Call first in every session. | Free, read-only |
| `yoloco_menu` | What the person can do here, as a numbered menu with live counts. FREE. | Free, read-only |
| `account_info` | The subscription's balance, the price of every paid action, plan limits and spending. FREE. | Free, read-only |
| `search_guide` | How to search one network: the policy, every search parameter with its type and units, the dictionaries. FREE. | Free, read-only |
| `product_guide` | What an audience overlap, segment, campaign or competitor report gives, when to propose it, its price and limits on this plan. FREE. | Free, read-only |

## Briefs and search (9)

| Tool | What it does | Effect |
|---|---|---|
| `search_strategy` | A search plan across networks for a brief, with what reaching the target costs. FREE. Call before searching. | Free, read-only |
| `dictionary_lookup` | Ids for search filters: geos, languages, topics, categories, interests, relevant tags, universities, users. FREE. | Free, read-only |
| `search_run` | Search one network's bloggers with the team's status on each row. FREE: never spends coins. | Free, read-only |
| `search_pages` | Open several search pages at once, paid ones after the person confirms the price, and optionally put them into a list. | Spends coins after you confirm the price |
| `search_saved` | The person's saved searches (shared with the app): list them, or save the current filters under a name. FREE. | Free, changes your workspace |
| `discover_similar` | Bloggers similar to 1–5 the person already likes, on any network. FREE. | Free, read-only |
| `blogger_lookup` | Resolve a profile link, @handle or name to bloggers with their doc_id and the team's status. FREE. | Free, read-only |
| `brief_get` | A campaign brief with its answers and the next question; the questions to ask; or the team's briefs. FREE. | Free, read-only |
| `brief_save` | Save one or more answers to a brief; without brief_id, start a new one; archive=true puts it away. FREE. | Free, changes your workspace |

## Vetting creators (6)

| Tool | What it does | Effect |
|---|---|---|
| `blogger_status` | For up to 100 bloggers: report already opened (free to reopen), lists, media plans, likes, comments. FREE. | Free, read-only |
| `report_cost` | What opening full reports would cost, before anything is opened. FREE. | Free, read-only |
| `report_get` | A blogger's full report, compact: profile, KPIs, growth, audience, posts, contacts, quality and ads, benchmark. COSTS COINS unless already opened. | Spends coins after you confirm the price |
| `creator_compare` | Up to 10 bloggers side by side: ER, views, audience, quality, growth, CPM at the media plan price. FREE, spends nothing. | Free, read-only |
| `team_activity` | What colleagues already did: reports opened recently, likes, discussed bloggers, comments. FREE. | Free, read-only |
| `blogger_note` | Mark a blogger as liked for the whole team (idempotent), remove the mark, or leave a comment colleagues see in the app. FREE. | Free, changes your workspace |

## Lists (6)

| Tool | What it does | Effect |
|---|---|---|
| `list_tree` | Every list of the team, by folder, with its size and networks. FREE. | Free, read-only |
| `list_items` | The bloggers in a list as compact cards, newest first. FREE. | Free, read-only |
| `list_create` | Create a list for candidates, or a folder to group lists. FREE. | Free, changes your workspace |
| `list_add` | Put bloggers into a list on the server, from ids or straight from a search, look-alikes, a segment or a competitor report. FREE. | Free, changes your workspace |
| `list_remove` | Remove up to 100 bloggers from a list. FREE. Other lists and media plans are untouched. | Free, changes your workspace |
| `list_refresh` | Refresh the stored data of every blogger in a list, in the background. COSTS COINS on Instagram, TikTok, YouTube. | Spends coins after you confirm the price |

## Media plans (6)

| Tool | What it does | Effect |
|---|---|---|
| `mediaplan_list` | The team's media plans with their size and status. FREE. | Free, read-only |
| `mediaplan_get` | A media plan: totals and charts, its bloggers with prices and planned CPM, or the progress of a background add. FREE. | Free, read-only |
| `mediaplan_add_cost` | What adding the next batch (up to 50 bloggers) to a media plan would cost, before anything starts. FREE. | Free, read-only |
| `mediaplan_add` | Add up to 50 bloggers to a media plan in the background. COSTS COINS: one report per blogger not opened in 30 days. | Spends coins after you confirm the price |
| `mediaplan_create` | Create an empty media plan. FREE. Fill it with mediaplan_add. | Free, changes your workspace |
| `mediaplan_item` | Record the negotiated price of a blogger in a media plan (null clears it), or remove the blogger. FREE. | Free, changes your workspace |

## Audience overlaps (4)

| Tool | What it does | Effect |
|---|---|---|
| `overlap_list` | The team's audience overlaps, newest first. FREE. | Free, read-only |
| `overlap_create` | Calculate how much the audiences of 2+ accounts overlap. COSTS COINS, takes 5–10 minutes. | Spends coins after you confirm the price |
| `overlap_result` | An overlap's status and, once complete, its compact result. FREE. | Free, read-only |
| `overlap_optimize` | From a complete overlap, the accounts that together reach the most unique people. FREE, computed locally. | Free, read-only |

## Segments (4)

| Tool | What it does | Effect |
|---|---|---|
| `segment_list` | The team's segments with their stage and progress, newest first. FREE. | Free, read-only |
| `segment_get` | One segment: its status with an ETA while it builds, or, once built, its bloggers a page at a time. FREE. | Free, read-only |
| `segment_keywords` | Where segment codes come from: curated audience presets, or codes suggested from a plain description. FREE. | Free, read-only |
| `segment_create` | Start building an Instagram segment in the background. COSTS COINS once the service accepts it. | Spends coins after you confirm the price |

## Campaigns (6)

| Tool | What it does | Effect |
|---|---|---|
| `campaign_list` | The team's campaigns, newest first. FREE. | Free, read-only |
| `campaign_get` | One campaign: its card, posts with metrics, one post's growth, authors with cost and CPM, or totals with the daily trend. FREE. | Free, read-only |
| `campaign_daily_brief` | What changed in running campaigns since yesterday and last week, and what needs attention. FREE. | Free, read-only |
| `campaign_vs_plan` | Plan against fact per blogger: the media plan's price and expected views against the campaign's views, cost and CPM. FREE. | Free, read-only |
| `campaign_create` | Start tracking published posts, optionally from a media plan with its prices. COSTS COINS once, at creation. | Spends coins after you confirm the price |
| `campaign_set_prices` | Set or correct post prices, which makes CPM appear. FREE. | Free, changes your workspace |

## Competitor ads (4)

| Tool | What it does | Effect |
|---|---|---|
| `competitor_advice` | Keywords and dictionary ids that find a brand's ads, or a search in one of the service's dictionaries. FREE. | Free, read-only |
| `competitor_list` | The team's competitor reports, newest first. FREE. | Free, read-only |
| `competitor_get` | One competitor report: its status, totals, trend, the posts it found, or the channels that ran them. FREE. | Free, read-only |
| `competitor_create` | Run a competitor report for one or more brands. COSTS COINS, takes 10–60 minutes. | Spends coins after you confirm the price |

## Files and exports (3)

| Tool | What it does | Effect |
|---|---|---|
| `export_file` | Start an Excel or PDF file of a list, media plan, segment, campaign, competitor posts or an opened report. No coins. | Free, changes your workspace |
| `bulk_export` | An Excel file of up to 10 000 bloggers matching a search, built in the background. COSTS COINS. | Spends coins after you confirm the price |
| `file_get` | One file's status and download link, or, without file_id, the team's latest exports. FREE. | Free, read-only |

## Workspace (2)

| Tool | What it does | Effect |
|---|---|---|
| `workspace_update` | Rename a list, folder, media plan, segment, campaign or competitor report, or change its description or colour. FREE. | Free, changes your workspace |
| `workspace_remove` | Delete a list, folder, media plan, overlap or segment, archive a campaign or competitor report, or stop a campaign. Asks for a yes first. | Asks first: cannot be undone |

## Slash commands (prompts)

| Command | What it does |
|---|---|
| `/yoloco_start` | Where to start: account, balance, an unfinished brief, the menu. |
| `/yoloco_menu` | The menu: what can be done here, with live counts. |
| `/yoloco_find` | Find bloggers: a brief one question at a time, a search plan, free previews, a list, finalists. |
| `/yoloco_pick` | Go through a list: whom to keep, whom to drop. |
| `/yoloco_mediaplan` | A media plan from a list: the price, adding in the background, totals, prices and CPM, export. |
| `/yoloco_overlap` | Audience overlap of finalists: whether it is worth it, the calculation, the best set. |
| `/yoloco_segment` | Bloggers by their audience's interests: codes, limits, building. |
| `/yoloco_campaign` | The whole cycle from a brief to a tracked campaign, with a checkpoint before every spend. |
| `/yoloco_campaign_daily` | The morning look at campaigns: what changed and what to do. |
| `/yoloco_competitors` | Who advertised a brand or its competitors: keywords, the report, posts, channels. |
| `/yoloco_balance` | Balance, a month of spending, and how to save coins. |
