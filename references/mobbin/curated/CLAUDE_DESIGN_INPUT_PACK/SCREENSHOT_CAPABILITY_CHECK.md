# Mobbin MCP — Screenshot / Capture Capability Check

**Date:** 2026-06-15
**Method:** Live inspection of the actual Mobbin MCP tools, resources, and JSON-Schemas in this Claude Code session (`claude mcp list`, `ToolSearch` schema load, `ListMcpResourcesTool`, and one live `search_screens` call). **Not** from memory or prior prose.
**Mobbin MCP transport:** `https://api.mobbin.com/mcp` (HTTP) — `✔ Connected`.

## Verdict (one line)

**No screenshot / capture / export / download / save-to-file function exists in the Mobbin MCP.** The server exposes 2 search tools and 2 HTML-gallery resources. Both tools return **inline preview images** (viewable in the conversation) plus metadata containing a **proprietary, auth-gated `image_url`**. Neither returns a file path, base64 payload, or a downloadable asset that Claude Code can materially write to disk under the task rules.

## Capability table

| tool_or_resource | type | args_schema_summary | returns | can_save_file_directly | notes |
|---|---|---|---|---|---|
| `mcp__mobbin__search_screens` | tool | `query`*, `platform`* (ios\|web), `exclude_screen_ids[]`, `image_format` (webp\|jpg, default webp), `limit` (1–30, default 20), `mode` (deep\|standard\|fast) | Inline preview image(s) + JSON `screens[]{ id, image_url, mobbin_url, app_name, platform }` | **NO** | `image_format` only picks the encoding of the **inline** preview shown in-conversation — it is not a file export. `image_url` is a proprietary `https://mobbin.com/api/mcp/short/…` short link (auth-gated). No file path, no base64, no `download`/`export`/`save` field. |
| `mcp__mobbin__search_flows` | tool | `query`*, `platform`* (ios\|web), `image_format` (webp\|jpg), `limit` (1–10, default 5), `page` (1–20) | Inline evenly-spaced preview images + metadata incl. per-screen previews | **NO** | Same shape as `search_screens`; inline-view only. No export/download/save. |
| `ui://mobbin/search-screens.html` | resource | read by URI (`ReadMcpResourceTool`) | `text/html;profile=mcp-app` — "Gallery of screen search results, rendered inline" | **NO** | An MCP-App HTML shell rendered inline, **not** an image file. References images via the same proprietary URLs; reading it yields HTML, not a savable PNG/JPG/WebP. |
| `ui://mobbin/search-flows.html` | resource | read by URI | `text/html;profile=mcp-app` — flow gallery | **NO** | Same — HTML app shell, not an image asset. |

\* = required parameter.

## Exact inventory

**Mobbin MCP tools available (exact, 2):**
1. `mcp__mobbin__search_screens`
2. `mcp__mobbin__search_flows`

**Mobbin MCP resources available (exact, 2):**
1. `ui://mobbin/search-screens.html` — `text/html;profile=mcp-app`
2. `ui://mobbin/search-flows.html` — `text/html;profile=mcp-app`

**Does a screenshot / capture / export / download / render-to-file function exist?** **NO.**

Searched the loaded schemas + resource list for every requested keyword — `screenshot`, `capture`, `image`, `preview`, `export`, `download`, `screen`, `flow`, `open`, `view`, `render`, `file`, `asset`:
- The only matches are `search_screens` / `search_flows` (the word "screen"/"flow" in their names) and the `image_format` enum + inline `image_url` field.
- **None** of them is a capture/export/download/file-writing operation. `image_format` selects webp-vs-jpg encoding of the **inline** preview only. `image_url` is a reference link, not a file the tool hands back.

## Can the `image_url` output be materially used to write a local file?

**No — not under the task rules, and not safely.**

- `image_url` = `https://mobbin.com/api/mcp/short/<token>` — a **proprietary, auth-gated** Mobbin short link, not a public CDN asset.
- Fetching it (curl / WebFetch / browser) to save the bytes would require: hitting an authenticated proprietary endpoint, and writing a **Mobbin-owned screenshot of a competitor app** to disk.
- That is barred three ways: task hard rules ("do not scrape unauthenticated pages", "do not use Playwright as a bypass", "do not store cookies/tokens/credentials"), and the standing CosFan guardrail ("never save Mobbin's proprietary `api/mcp/short` images — proprietary-asset copy").
- `WebFetch` additionally returns model-summarized **text**, not a binary file, so it cannot produce a PNG even if allowed.

## Can the inline preview images be saved?

**No.** The tool returns them as **rendered image content blocks** in the tool result (visible to me, e.g. the Patreon tier screens above). Claude Code exposes **no tool that writes a tool-result image to disk** — there is no byte/base64 handle for them, and `Write` only persists text content I supply. So the inline previews are view-only by construction.

## Conclusion

Mobbin MCP is **view-only by design**: it lets an agent *look at* screens inline and *cite* their `mobbin_url`, but provides **no mechanism to export a screenshot file**. Saving a real image from Mobbin therefore requires a path **outside** the Mobbin MCP (a manually-captured licensed screenshot, or an original Claude-generated board) — both out of scope for this capability probe. See `SCREENSHOT_PROBE_RESULT.md` for the probe attempt and exact failure reason.
