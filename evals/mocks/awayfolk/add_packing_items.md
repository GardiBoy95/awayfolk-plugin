---
expect:
  tripId: string
  items: array
  expectedRevision: number
  idempotencyKey: string
---

{"revision":43,"eventIds":["evt_pack_1"],"url":"https://awayfolk.app/trip/{{input.tripId}}/packing"}
