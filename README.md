# Awayfolk: a shared trip planner for Claude and ChatGPT

**Make more of going away.** Awayfolk is a shared trip planner with a remote MCP server at `https://awayfolk.app/mcp`. Connect it to Claude or ChatGPT and plan in the conversation: your AI saves ideas from links, suggests them for days, files flights and hotels from booking confirmations, keeps the packing list and adds price estimates. Everything lands in one trip on [awayfolk.app](https://awayfolk.app) that up to six travellers share on their phones, before and during the trip.

This repository contains the Awayfolk plugin for Claude and OpenAI-compatible hosts. You can ask your AI to:

- find ideas that suit you, and save the ones you pick to the trip's ideas list;
- suggest ideas for particular days, which you then confirm in the app with one tap;
- add what things typically cost, clearly marked as estimates;
- keep packing, bookings and checklists up to date;
- save a flight or hotel confirmation you paste as a booking;
- give you an invite link for your travel party.

Shared changes appear for the whole travel party on awayfolk.app. Personal packing stays personal.

## Install

**Claude (web and desktop):** go to Customize → Plugins → Add marketplace, enter `GardiBoy95/awayfolk-plugin`, and install **Awayfolk**.

**Claude Code:**

```
/plugin marketplace add GardiBoy95/awayfolk-plugin
/plugin install awayfolk@awayfolk
```

The first time Claude uses Awayfolk, you sign in with the Google account you use on awayfolk.app and approve access. You can also connect without the plugin: [awayfolk.app/ai](https://awayfolk.app/ai) has a *Connect Claude* button.

**ChatGPT:** start at [awayfolk.app/ai](https://awayfolk.app/ai) and choose ChatGPT. If Awayfolk is not already connected, enable Developer mode in Settings → Security and login, open [Plugins](https://chatgpt.com/plugins), and add `https://awayfolk.app/mcp` with OAuth. Sign in with the same Google account. A public directory listing is not yet available.

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

## Privacy

The plugin collects nothing itself. When your AI uses Awayfolk, its requests go to `awayfolk.app` over HTTPS, and Awayfolk stores the trips, cards and travellers you create there. It can only reach the trips you have shared with it. Under AI on awayfolk.app, you can disconnect one connection or change the trip selection shared by all your AI connections. Reconnecting preserves the trips you selected. What Awayfolk collects, how long it keeps it and who processes it is in the [privacy policy](https://awayfolk.app/privacy).

## Support

Questions and problems: [awayfolk.app](https://awayfolk.app), using the support link at the bottom of the page.

## Licence

MIT. See [LICENSE](LICENSE).
