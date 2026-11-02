---
expect:
  tripId: string
  expectedRevision: number
  idempotencyKey: string
---

{"revision":43,"id":"{{input.tripId}}","eventId":"evt_trip"}
