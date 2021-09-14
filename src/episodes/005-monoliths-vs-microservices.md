---
title: "005: Monoliths vs. Microservices"
description: This week, the crew talks about their own mistakes, feelings of fraud, insecurities, and how Impostor Syndrome manifests in their own careers.
date: 2021-01-13
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/005-monolith-vs-microservices/id1544142288?i=1000505212666"></iframe>

Monoliths are bad! Microservices are good! These are the "obvious" truths that many engineers hold close to heart. So, why is it that [Ben](https://www.bennadel.com/) has been slowly [merging some of his Microservices back into his Monolith](https://www.bennadel.com/blog/3944-why-ive-been-merging-microservices-back-into-the-monolith-at-invision.htm)? It turns out that a Monolith - _like a Microservice_ - is a valid architectural choice that carries its own set of pros and cons. And, for him, his team, and their particular set of skills, the Monolith is proving to contain the right set of trade-offs.

This week, the crew talks about Ben's journey; why [InVision](https://www.invisionapp.com/) started using Microservices in the first place; and, what made him realize that it was time to start pulling services back into the core Monolith. There are no hard truths here - only thoughtful, context-aware considerations.

## Your hosts

- Adam Tuttle -- [Twitter](https://twitter.com/adamtuttle), [Website](https://adamtuttle.codes)
- Ben Nadel -- [Twitter](https://twitter.com/bennadel), [Website](https://www.bennadel.com/)
- Carol Hamilton -- [Twitter](https://twitter.com/k_Roll242)
- Tim Cunningham -- [Twitter](https://twitter.com/timcunningham71)

Follow the show! Our website is [workingcode.dev](https://workingcode.dev) and we're **@WorkingCodePod** on [Twitter](https://twitter.com/workingcodepod) & [Instagram](https://instagram.com/workingcodepod). New episodes weekly on Wednesday.

## Triumphs & Fails

- **Adam's Triumph:** He took the week off! He's usually not that good about taking time off; so, taking a whole week off between Christmas and New Year's was actually quite relaxing.
- **Ben's Triumph:** He managed to stay production at work during the "deployment freeze" that takes place during the holidays! This meant creating lots of small, parallel git branches tied up in a bow, ready and waiting for the 2021 deployments to begin.
- **Carol's Triumph:** She stayed up until 3am writing Unit Tests! She doesn't often work in an environment that does much testing; so, this was a new and thrilling experience. Who knew that one could be so _happy_ thinking about the _unhappy path_!
- **Tim's Triumph:** He also took the week off (his company always takes Christmas week off)! But, he's not used to taking so much time off; and, he started to get bored by Thursday (such a classic engineer).

## Notes & Links

- [GitHub "Draft" pull-requests](https://github.blog/2019-02-14-introducing-draft-pull-requests/) - it's just like a regular Pull Request (PR); but, it's intended to be a "work in progress" (WIP).
- [Silento](https://www.youtube.com/watch?v=vjW8wmF5VWc) -Watch Me (Whip/Nae Nae) - official music video.
- [Archer](https://www.fxnetworks.com/shows/archer) -a wonderfully raunchy animated series about spies (for adults). _Sploosh!_
- [Microservices](https://martinfowler.com/articles/microservices.html) - an architectural choice, write-up by Martin Fowler
- [Monolithic application](https://en.wikipedia.org/wiki/Monolithic_application) - an architectural choice.
- [Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law) - how organizational structure relates to programming structure:
  > Any organization that designs a system (defined broadly) will produce a design whose structure is a copy of the organization's communication structure.
- Single-Tenant architecture - configuration in which one customer shares no resources with another customer.
- Multi-Tenant - configuration in which many customers share the same set of resources (such as all existing in the same database).
- [Single Page Application (SPA)](https://en.wikipedia.org/wiki/Single-page_application) - a common front-end application architecture in which the front-end dynamically re-renders the UI based on data-fetches.
- Distributed Monolith / Microlith - an architectural anti-pattern in which you combine the worst properties of both monoliths and microservices while reaping none / few of the rewards.
- [ColdFusion / Lucee CFML](https://www.lucee.org/) - a modern web programming language for dynamic server-side rendering.
- [Mark Richards - The Rise and Fall of Microservices](https://learning.oreilly.com/videos/oreilly-software-architecture/9781492050728/9781492050728-video328505) - presentation from O'Reilly Software Architecture Conference 2019.
- [Sam Newman - Building Microservices](https://samnewman.io/books/building_microservices/) - the canonical book on Microservices.
- [Sam Newman - Monolith To Microservices: Evolutionary Patterns To Transform Your Monolith](https://samnewman.io/books/monolith-to-microservices/) - Sam's follow-up book to Building Microservices - it should be required reading.
- [Simon Brown - Modular Monoliths](http://www.codingthearchitecture.com/presentations/devnexus2016-modular-monoliths) - presentation from DevNexus 2016 that famously had the slide:
- If you can't build a well-structured monolith, what makes you think microservices is the answer?
- [Amazon AWS Lambda](https://aws.amazon.com/lambda/) - serverless compute services.
- [Amazon AWS Fault-Injection Simulator](https://aws.amazon.com/fis/) - aka, Chaos Monkey as a Service.
- [Amazon Cloudwatch](https://docs.aws.amazon.com/cloudwatch) - a reliable, scalable, and flexible monitoring solution.
- [Kevin Conway](https://github.com/kevinconway) - Principal engineer at InVision and a strong proponent for microservices.
- [Chris Richardson](https://microservices.io/) - he was doing Microservices before there were Microservices. He's the maintainer of microservices.io.
- [Hype Cycle](https://www.gartner.com/en/research/methodologies/gartner-hype-cycle) - from the "Peak of Inflated Expectations" to the "Trough of Disillusionment" and every emotion in between, this is how the technology world experiences new technology.
- [Reactive Manifesto](https://www.reactivemanifesto.org/) - an approach to building robust applications.
- [Lagom Reactive Microservices framework](https://www.lagomframework.com/) - an opinionated microservices framework.
