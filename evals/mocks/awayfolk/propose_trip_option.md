---
expect:
  tripId: string
  kind: [destination, dates]
  expectedRevision: number
  idempotencyKey: string
---

{"optionId":"opt_new","revision":6,"url":"https://awayfolk.app/decisions/{{input.tripId}}"}
