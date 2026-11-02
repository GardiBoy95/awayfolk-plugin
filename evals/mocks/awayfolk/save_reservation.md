---
expect:
  tripId: string
  recordId: string
  reservation: object
  expectedRevision: number
  idempotencyKey: string
---

{"revision":43,"id":"{{input.recordId}}","eventId":"evt_reservation","url":"https://awayfolk.app/trip/{{input.tripId}}/card/{{input.recordId}}","next":{"members":2,"joinedOthers":1,"unseenIdeas":0,"inviteSuggested":false}}
