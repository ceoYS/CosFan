# Mobbin MCP — Screenshot Probe Result

**Date:** 2026-06-15
**Goal:** Save ≥1 real image file from Mobbin MCP to `visual-local/_probe-mobbin-capture.png` as a capability probe.

- **capture_attempted:** yes
- **target_reference:** Patreon membership tier picker / "Tiers" screen (Patreon, iOS) — screen ids `85cc6f2b-3570-4509-90d3-576a8c5459cf` and `ba71a92f-38ac-4bd2-a524-f1ce106fd8c6` (already in the curated pack).
- **mcp_tool_used:** `mcp__mobbin__search_screens` (the only image-returning Mobbin tool); plus `ListMcpResourcesTool` (server=`mobbin`) and `ToolSearch` schema load to confirm no capture/export tool exists.
- **exact_input_summary:** `search_screens{ query: "Patreon membership tier picker screen with subscription tiers and prices", platform: "ios", limit: 2 }`.
- **output_received:** 2 inline `<output_image>` preview blocks (rendered in-conversation, viewable) + JSON:
  `screens[0] = { id: 85cc6f2b-…, image_url: https://mobbin.com/api/mcp/short/nWSyb17q, mobbin_url: https://mobbin.com/screens/85cc6f2b-…, app_name: "Patreon", platform: "ios" }`,
  `screens[1] = { id: ba71a92f-…, image_url: https://mobbin.com/api/mcp/short/xt1DHajq, mobbin_url: …, app_name: "Patreon", platform: "ios" }`.
  **No** file path, **no** base64 payload, **no** `download`/`export` field in the output.
- **local_file_created:** no
- **local_file_path:** none (intended `references/mobbin/curated/CLAUDE_DESIGN_INPUT_PACK/visual-local/_probe-mobbin-capture.png` — not created)
- **file_type_check:** n/a — no file was produced.
- **image_count_after:** 0
- **if_failed_exact_reason:** **Tool limitation (missing export capability)** — the Mobbin MCP exposes only 2 search tools and 2 HTML-gallery resources; **none** provides a screenshot/capture/export/download/save-to-file operation. The only file-bearing handle in the output is `image_url = https://mobbin.com/api/mcp/short/<token>`, a **proprietary, auth-gated** Mobbin link; fetching and saving it is barred by the task hard rules (no scraping unauthenticated/proprietary pages, no Playwright bypass, no storing credentials/cookies) and by the CosFan guardrail against saving Mobbin's proprietary assets. The inline preview images returned in the tool result expose **no byte/base64 handle**, and Claude Code has **no tool to write a tool-result image to disk**, so they cannot be saved either. This is **not** an auth failure, **not** an args failure, and **not** a permissions failure on our side — the capability simply does not exist in the MCP surface.
- **next_step (failed):** Exact missing capability = a Mobbin MCP tool that returns a **downloadable image** (file path or base64) or that **writes a screenshot to a caller-specified path**. No such tool exists, so no rule-compliant Mobbin-MCP capture is possible. Per task rules: stop — no fallback queue. (Out of scope for this probe, but the only legitimate ways to get real pixels into `visual-local/` remain a **manually-captured licensed screenshot** or a **Claude-generated original board** — neither is a Mobbin-MCP capture.)
