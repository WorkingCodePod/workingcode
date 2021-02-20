---
title: '010: Scaling'
description: This week, the crew talks about their experience in scaling web application systems; what they have - and _haven't yet_ - had the need to consider; and, how they calculate the return on investment (ROI) when it comes to adding complexity to a potential solution ("innovation tokens", anyone?).
date: 2021-02-17
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/eba69652-fdd1-40eb-ab02-9ffe44841542"></script><div class="redcirclePlayer-eba69652-fdd1-40eb-ab02-9ffe44841542"></div>

An engineer at SquareSpace once referred to his company as "an overnight success, 7-years in the making." This cheeky insight pays homage to the _marathon of work_ that is often required when building a successful product and / or business. Which begs the question: when is it appropriate to start thinking about scale? Should you be taking it into account during early ideation and the construction of your MVP (Minimum Viable Product)? Or, should you kick the can down the road with the assumption that you can always throw money at the problem later (either by hiring smart people or by vertically scaling your existing compute resources)?

This week, the crew talks about their experience in scaling web application systems; what they have - and _haven't yet_ - had the need to consider; and, how they calculate the return on investment (ROI) when it comes to adding complexity to a potential solution ("innovation tokens", anyone?).

If you like this episode about scaling, you may also enjoy our previous episode on [Monoliths vs. Microservices][working-code-005].

### Triumphs &amp; Failures

* **Adam's Triumph** - After switching to a new platform, his ORM (Object-Relational Mapping) code stopped working for "reasons". And, instead of spending a whole week trying to figure it out, he just spent a single day replacing the problematic ORM queries with native SQL statements. This was a veritable "Master Class" in pragmatic problem solving.

* **Ben's Failure / Triumph** - This week has been _kicking his butt_! He's exhausted and stressed out - even his feet hurt. This is due, primarily, to the HTML emails that he's been crafting at work. That said, he's been able to take his "failure" and transform it into a "triumph" by channeling that frustration into an exciting new approach for building HTML emails that's powered by ColdFusion Custom Tags. It's still early, but he's hella stoked on the concept!

* **Carol's Triumph** - She wrote some rather complicated code that dealt with edge-cases in her application that weren't really ever going to happen. And, when her teammates discussed this with her, she did the honorable thing and removed her code, leaving in its place a much simpler solution. The real triumph here is that she was able to overcome the "sunk cost fallacy" we engineers often succumb to when having to confront the questionable value of our own solutions.

* **Tim's Failure** - What started out as a thrilling exploration of Redis has turned into a battle for sanity! For reasons that he has not yet been able to understand, the data that he's been writing to a Redis cache isn't always available for immediate read. This is in his local development environment and he's _the only one_ hitting the code. It just doesn't make any sense!

### Notes &amp; Links

* [Redis](https://redis.io/) - a blazing-fast in-memory data structure store.
* [CFRedis](https://github.com/MWers/cfredis) - a ColdFusion client for the Jedis Java driver for Redis.
* [Jedis](https://github.com/redis/jedis) - a blazingly small and sane Java client for Redis.
* [Mango Blog](https://www.mangoblog.org/) - an extensible blog engine released under the Apache license, built with ColdFusion.
* [CockroachDB](https://www.cockroachlabs.com/) - a distributed SQL database built on a transactional and strongly-consistent key-value store.
* [Dan McKinley: Boring Technology Club](http://boringtechnology.club/) - a spoken word version of Dan's essay, "Choose Boring Technology".
* [Ben Nadel: "Enterprise" is not a dirty word](https://www.bennadel.com/blog/3976-enterprise-is-not-a-dirty-word.htm) - a blog post discussing the merits of "enterprise" software.
* [FrameworkOne (FW/1)](http://framework-one.github.io/) - a light-weight conventions-over-configuration framework for ColdFusion web applications.
* Blocking-Request Budget - a concept in which serving a user's request can only entail a limited number of blocking requests.
* [AWS Fargate](https://aws.amazon.com/fargate/) - services compute for containers.
* [AWS Lambda](https://aws.amazon.com/lambda/) - a "functions as a service" (FaaS) platform.
* [Mailgun](https://www.mailgun.com/) - an email service provider (ESP) built for developers.
* [Let's Encrypt](https://letsencrypt.org/) - a nonprofit Certificate Authority that has brought free TLS certificates to the masses.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-005]: /episodes/005-monoliths-vs-microservices/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
