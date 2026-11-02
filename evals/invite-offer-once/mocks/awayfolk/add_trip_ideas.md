---
expect:
  tripId: string
  items: array
  expectedRevision: number
  idempotencyKey: string
---

{"revision":43,"eventIds":["evt_i1","evt_i2","evt_i3"],"ids":["rec_i1","rec_i2","rec_i3"],"url":"https://awayfolk.app/trip/{{input.tripId}}/ideas","next":{"members":1,"joinedOthers":0,"unseenIdeas":3,"inviteSuggested":true}}
