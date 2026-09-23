# Awayfolk for Claude

**Make more of going away.** Awayfolk brings the people, places, plans and memories of a trip together. This plugin lets Claude read and update the trips you share from [Awayfolk](https://awayfolk.app).

You can ask Claude to:

- find ideas that suit you, and save the ones you pick to the trip's ideas list;
- suggest ideas for particular days, which you then confirm in the app with one tap;
- add what things typically cost, clearly marked as estimates;
- keep packing, bookings and checklists up to date.

Everything Claude saves shows up for the whole travel party on awayfolk.app.

## Install

**Claude (web and desktop):** go to Customize → Plugins → Add marketplace, enter `GardiBoy95/awayfolk-plugin`, and install **Awayfolk**.

**Claude Code:**

```
/plugin marketplace add GardiBoy95/awayfolk-plugin
/plugin install awayfolk@awayfolk
```

The first time Claude uses Awayfolk, you sign in with the Google account you use on awayfolk.app and approve access. You can also connect without the plugin: [awayfolk.app/ai](https://awayfolk.app/ai) has a *Connect Claude* button.

## What the plugin contains

- A connection to the Awayfolk MCP server at `https://awayfolk.app/mcp`. Sign-in is OAuth through Awayfolk's sign-in page.
- The **plan-a-trip** skill, which teaches Claude how to work with a trip: read it first, suggest rather than book, confirm before anything is marked paid or planned, and leave room for spontaneity.

## Privacy

The plugin collects nothing itself. When Claude uses Awayfolk, its requests go to `awayfolk.app` over HTTPS, and Awayfolk stores the trips, cards and travellers you create there. Claude can only reach the trips you have shared with it. You can take access back at any time under AI on awayfolk.app. What Awayfolk collects, how long it keeps it and who processes it is in the [privacy policy](https://awayfolk.app/privacy).

## Support

Questions and problems: [awayfolk.app](https://awayfolk.app), using the support link at the bottom of the page.

## Licence

MIT. See [LICENSE](LICENSE).
