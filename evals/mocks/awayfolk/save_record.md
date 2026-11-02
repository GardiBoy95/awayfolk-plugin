---
expect:
  tripId: string
  kind: [idea, activity, packing, outfit, booking, memory, checklist, expense, settlement]
  title: string
  expectedRevision: number
  idempotencyKey: string
---

{"revision":43,"id":"rec_{{input.idempotencyKey}}","eventId":"evt_{{input.idempotencyKey}}","next":{"members":2,"joinedOthers":1,"unseenIdeas":0,"inviteSuggested":false}}
