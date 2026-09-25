---
expect:
  tripId: string
  title: string
  destination: string
  startDate: string
  endDate: string
  expectedRevision: number
  idempotencyKey: string
---

{"revision":43,"id":"{{input.tripId}}","eventId":"evt_trip"}
