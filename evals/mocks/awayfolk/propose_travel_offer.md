---
expect:
  tripId: string
  expectedActor: string
  expectedTripRevision: number
  audience: [trip, planners]
  offer: object
  idempotencyKey: string
---

{"groupId":"grp_new","offerId":"off_{{input.idempotencyKey}}","revision":1,"url":"https://awayfolk.app/trip/{{input.tripId}}/choices/grp_new"}
