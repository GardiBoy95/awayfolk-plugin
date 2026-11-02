---
expect:
  tripId: string
  expectedActor: string
  expectedTripRevision: number
  audience: [trip, planners]
  offer: object
  idempotencyKey: string
---

{"groupId":"grp_hotel","offerId":"off_{{input.idempotencyKey}}","revision":2,"url":"https://awayfolk.app/trip/{{input.tripId}}/choices/grp_hotel"}
