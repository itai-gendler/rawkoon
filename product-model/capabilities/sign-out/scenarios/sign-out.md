---
kind: primary
routes:
  web: Web
  iphone: iPhone
steps:
- text: The Member chooses Logout
  kind: actor
  actor: member
  entities: []
  contexts:
    web:
      place: web::household
    iphone:
      place: iphone::household
- text: The Product ends the session
  kind: product
  actor: member
  entities: []
  contexts:
    web:
      place: web::household
    iphone:
      place: iphone::household
---

# Sign out

## Trigger

A person is done using the instance on this device.

## Outcome

The person is signed out and returned to the sign-in page.

## Edge cases

- Signing out of the iPhone app also forgets the instance address and the data the app cached.
