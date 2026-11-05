# Awayfolk: a shared trip planner for Claude and ChatGPT

**Make more of going away.** Awayfolk is a shared trip planner with a remote MCP server at `https://awayfolk.app/mcp`. Connect it to Claude or ChatGPT and plan in the conversation: your AI saves ideas from links, suggests them for days, files flights and hotels from booking confirmations, keeps the packing list and adds price estimates. Everything lands in one trip on [awayfolk.app](https://awayfolk.app) that the whole group shares on their phones, before and during the trip.

This repository contains the Awayfolk plugin for Claude and OpenAI-compatible hosts. You can ask your AI to:

- find ideas that suit you, and save the ones you pick to the trip's ideas list;
- compare destinations and dates in separate polls; people answer and the trip owner confirms in Awayfolk;
- suggest ideas for particular days, which you then confirm in the app with one tap;
- save researched or user-provided prices, clearly marked as estimates;
- keep packing, bookings and checklists up to date;
- save a flight or hotel confirmation you paste as a booking;
- tell you what the others have changed, and undo a change of yours;
- plan a blåtur, a surprise trip, without giving it away;
- give you an invite link for the people on your trip.

Shared changes appear for everyone on the trip on awayfolk.app. Personal packing stays personal. Core planning is free for the whole group, including undated trips and editing after the trip. Saving researched or user-provided estimates through these tools is free. Awayfolk's built-in price estimates and tailored packing have limited free allowances per trip; use the current allowance returned by the tools and enter details manually when it is exhausted. The connected AI service's own plan and limits apply. New Trip Pass sales are paused; existing paid benefits remain valid.

## Install

**Directory status, 5 November 2026:** [Awayfolk for ChatGPT](https://chatgpt.com/plugins/plugin_asdk_app_6ab76ed01ec8819190514d43cf689f25) is publicly published as version 1.0.2. The [Claude plugin](https://claude.ai/customize/plugins/id/4f3e01d3-5101-44b5-a419-6f1c13cd3404%40anthropic-plugin-directory) is publicly published as version 0.2.2. The separate Claude connector is still under review and is not yet published. This repository's package version can be newer than the Claude directory release; publishing a GitHub update does not publish that update in the directory.

**Claude (web and desktop):** open the [public Awayfolk plugin](https://claude.ai/customize/plugins/id/4f3e01d3-5101-44b5-a419-6f1c13cd3404%40anthropic-plugin-directory) and install it. Alternatively, go to Customize → Plugins → Add → Add marketplace and enter `GardiBoy95/awayfolk-plugin`, then open that marketplace and install **Awayfolk**. In the installed plugin's **Connectors** tab, use **Add** or **Connect** for Awayfolk and complete sign-in. Adding the marketplace, installing the plugin and approving its connection are separate steps; the slash commands below are for Claude Code.

To connect without the bundled skills, start at [awayfolk.app/ai](https://awayfolk.app/ai) and choose **Connect Claude**. If manual setup is needed, use Customize → Connectors → + → Add custom connector, with the name **Awayfolk** and address `https://awayfolk.app/mcp`.

**Claude Code:**

```
/plugin marketplace add GardiBoy95/awayfolk-plugin
/plugin install awayfolk@awayfolk
```

Complete Awayfolk authentication when Claude Code prompts you. In either Claude setup, use the same Google account as on awayfolk.app and approve the connection. Ask it to show your trip to verify that the connection works.

**ChatGPT:** open the [public Awayfolk plugin](https://chatgpt.com/plugins/plugin_asdk_app_6ab76ed01ec8819190514d43cf689f25), choose **Install plugin**, and complete the connection with the same Google account you use on awayfolk.app. Select Awayfolk in the conversation, paste the starter message from [awayfolk.app/ai](https://awayfolk.app/ai) and ask it to show your trip. The published listing is verified; a fresh installation on a separate account has not been verified. If you need manual setup and your account supports it, add `https://awayfolk.app/mcp` with OAuth through ChatGPT's developer-mode custom connection setup.

**Codex and compatible plugin hosts:** install this repository as a plugin using your host's plugin installer. The portable `plugin.json` and `mcp.json` describe the same remote connection; `.codex-plugin/plugin.json` supplies compatibility metadata. Authenticate Awayfolk when the host prompts you.

**Other MCP clients:** add `https://awayfolk.app/mcp` as a remote server (streamable HTTP, OAuth 2.1 with dynamic client registration). Awayfolk is listed in the [Official MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=app.awayfolk/awayfolk) as `app.awayfolk/awayfolk`.

## What the plugin contains

- A connection to the Awayfolk MCP server at `https://awayfolk.app/mcp`. Sign-in is OAuth through Awayfolk's sign-in page.
- **plan-a-trip**: read the right trip, compare sourced ideas and save what you choose.
- **save-bookings**: turn confirmations you provide into flights, hotels and other bookings, keeping local times and prices accurate.
- **pack-for-trip**: add missing packing items and mark only what you say is packed or bought.
- **trip-today**: show today's confirmed plan, useful booking details and recent changes.
- Interactive trip cards in hosts that support MCP Apps: select proposals, save them together, put an idea on a day, and Undo. Other hosts receive the same trip and receipts as text.

Start from a trip's AI button to carry its exact identity into the conversation. Your AI reads the latest trip before editing it. Writes include a receipt, and retrying the same operation does not create duplicate cards.

## Development

Check the manifest and run the skill's evals with Claude Code:

```
claude plugin validate .
claude plugin eval . --runs 1 --ablation none
```

The evals in `evals/` answer every Awayfolk call from a mock, so no real trip is touched. `evals/mocks/awayfolk/_tools.json` is a copy of the server's tool list: when the server changes, update it together with the skill. CI runs both on pull requests; the evals need an `ANTHROPIC_API_KEY` secret.

## Privacy

The plugin collects nothing itself. When your AI uses Awayfolk, its requests go to `awayfolk.app` over HTTPS, and Awayfolk stores the trips, cards and travellers you create there. It can only reach the trips you have shared with it. Under AI on awayfolk.app, you can disconnect one connection or change the trip selection shared by all your AI connections. Reconnecting preserves the trips you selected. What Awayfolk collects, how long it keeps it and who processes it is in the [privacy policy](https://awayfolk.app/privacy).

## Support

Questions and problems: [awayfolk.app](https://awayfolk.app), using the support link at the bottom of the page.

## Licence

MIT. See [LICENSE](LICENSE).
