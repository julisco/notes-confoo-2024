# I deploy on fridays, and maybe you should too

by Michiel Rook

## Official Slides

[Slides](https://github.com/confooca/2024/blob/main/2024-02-22/i_deploy_on_fridays-michiel_rook.pdf)

## Why ?

Everywhere we see we should not, - tradition - fear - risk - control - confidence & trust - time to repair / recover - on-call stress

Logical conclusion would be DONT deploy on Friday.

## What about critical bugs ?

We do deploy and fix it on friday.

## Friday

- Friday is 20% of a week
- if competitors are not afraid but you are it can be an issue

## So, reduce risk

- release something in small batches
  - amount of risk is reduced
- continuous delivery, means code is always in a releasable state
- continuous deployments, it deploys automatically when all is OK

High performance teams deploy more and faster with more quality.

## ...But our code is old...

- what I build is tomorrow legacy

## So, dealing with legacy

- strangler pattern: make the client talk to the abstraction layer instread of the old module
- then we can replace the old by a new module

## Git conflicts

- integrate into master branch daily, because with branches we delay

## Decouple deployments from releases

- feature toggles

## Pull requests

- code reviews are useful, but it implies delay + context switching
  ... so ?
- pair programming
- MOD programming (in team)

## Pipelines

- automation, automate all what we can
- continuous testing
- monitoring ans alerting
- user feedback
