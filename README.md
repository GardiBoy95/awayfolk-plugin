# Awayfolk: a shared trip planner for Claude and ChatGPT

**Make more of going away.** Awayfolk is a shared trip planner with a remote MCP server at `https://awayfolk.app/mcp`. Connect it to Claude or ChatGPT and plan in the conversation: your AI saves ideas from links, suggests them for days, files flights and hotels from booking confirmations, keeps the packing list and adds price estimates. Everything lands in one trip on [awayfolk.app](https://awayfolk.app) that up to six travellers share on their phones, before and during the trip.

This repository is the Claude plugin. You can ask Claude to:

- find ideas that suit you, and save the ones you pick to the trip's ideas list;
- suggest ideas for particular days, which you then confirm in the app with one tap;
- add what things typically cost, clearly marked as estimates;
- keep packing, bookings and checklists up to date;
- save a flight or hotel confirmation you paste as a booking;
- give you an invite link for your travel party.

Everything Claude saves shows up for the whole travel party on awayfolk.app.

## Install

**Claude (web and desktop):** go to Customize → Plugins → Add marketplace, enter `GardiBoy95/awayfolk-plugin`, and install **Awayfolk**.

**Claude Code:**

```
/plugin marketplace add GardiBoy95/awayfolk-plugin
/plugin install awayfolk@awayfolk
```

The first time Claude uses Awayfolk, you sign in with the Google account you use on awayfolk.app and approve access. You can also connect without the plugin: [awayfolk.app/ai](https://awayfolk.app/ai) has a *Connect Claude* button.

**ChatGPT:** in Settings → Apps → Advanced settings, turn on Developer mode, create an app with the URL `https://awayfolk.app/mcp` and sign in with Google. A one-click listing in ChatGPT's app directory is on its way.

**Other MCP clients:** add `https://awayfolk.app/mcp` as a remote server (streamable HTTP, OAuth 2.1 with dynamic client registration). Awayfolk is listed in the [Official MCP Registry](https://registry.modelcontextprotocol.io/v0.1/servers?search=app.awayfolk/awayfolk) as `app.awayfolk/awayfolk`.

## What the plugin contains

- A connection to the Awayfolk MCP server at `https://awayfolk.app/mcp`. Sign-in is OAuth through Awayfolk's sign-in page.
- The **plan-a-trip** skill, which teaches Claude how to work with a trip: read it first, suggest rather than book, confirm before anything is marked paid or planned, and leave room for spontaneity.

## Privacy

The plugin collects nothing itself. When Claude uses Awayfolk, its requests go to `awayfolk.app` over HTTPS, and Awayfolk stores the trips, cards and travellers you create there. Claude can only reach the trips you have shared with it. You can take access back at any time under AI on awayfolk.app. What Awayfolk collects, how long it keeps it and who processes it is in the [privacy policy](https://awayfolk.app/privacy).

## Support

Questions and problems: [awayfolk.app](https://awayfolk.app), using the support link at the bottom of the page.

## Licence

MIT. See [LICENSE](LICENSE).
