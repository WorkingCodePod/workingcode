---
title: '009: Testing'
description: This week, the crew talks about their own views and experience with testing; and, how they currently implement testing at work.
date: 2021-02-10
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/549813fe-c15f-421b-935a-9b2804125d1e"></script><div class="redcirclePlayer-549813fe-c15f-421b-935a-9b2804125d1e"></div>

There are very few people in the programming world who will argue against the idea of _testing software_. But, when it comes to the **mechanisms though which code is tested**, the conversation starts to get interesting. There are those who feel that TDD - Test Driven Development - is "the way"; and, that any divergence from TDD is not only laziness but is, in fact, borderline malfeasance. At the other end of the spectrum are the people who perform all their testing manually; often, relying on QA (Quality Assurance) teams and smoke tests to find regressions before each deployment.

Most people sit somewhere in the middle of these extremes. This week, the crew talks about their own views and experience with testing; and, how they currently implement testing at work. Ben swings heavily towards the manual testing end of the spectrum; Adam and Carol swing heavily towards the automated end of the spectrum; and Tim, who often feels very hypocritical, sits somewhere in the middle.

## Your hosts
- Adam Tuttle -- [Twitter](https://twitter.com/adamtuttle), [Website](https://adamtuttle.codes)
- Ben Nadel -- [Twitter](https://twitter.com/bennadel), [Website](https://www.bennadel.com/)
- Carol Hamilton -- [Twitter](https://twitter.com/k_Roll242)
- Tim Cunningham -- [Twitter](https://twitter.com/timcunningham71)

Follow the show! Our website is [workingcode.dev](https://workingcode.dev) and we're **@WorkingCodePod** on [Twitter](https://twitter.com/workingcodepod) & [Instagram](https://instagram.com/workingcodepod). New episodes weekly on Wednesday.

## Triumphs & Fails

* **Adam's Triumph:** He's been working hard to get his company's application migrated over to a new open-source software stack. And, as of this recording, he's successfully moved 9 of his 13 production servers over to the new setup; and, everything seems to be running smoothly! He's feeling very strong on hitting his goals of migrating the rest of the servers by the end of January.

* **Ben's Failure:** This week has been _kicking his butt_! He hasn't been sleeping well, he can't get comfortable in his chair, and everything seems to hurt. He's carrying a boat-load of tension in his neck and shoulders and he just can't seem to get past it. The only saving grace is that he can use his "standing desk" controls to select the perfect height for _sitting_.

* **Carol's Failure:** She's also having a tough time getting comfortable! Her body hurts from her tail-bone up to her head; and, the heating pad she's using just ain't doing it. She's currently on the hunt for a new chair that might help offer some relief. But, being the Amazonian warrior that she is makes things a bit more challenging. As she says:

  > I can't help it - I have six feet of legs and they have to go somewhere!

  And, as the icing on the cake, she accidentally deleted the configuration settings for _all seven of her home networks_. She had automatic backups configured; but, she accidentally turned them off 3-months ago.

* **Tim's Triumph:** It's been a while since he was able to get into a groove; but, this week, he finally achieved **flow state**: that moment when the world disappears, time loses meaning, and all you can see is the code in front of you as it appears to pour out of your hands without effort or thought. He summed this feeling up quite nicely:

  > I feel less like I'm pushing a stone uphill and more like there's a river just flowing through me.

  I mean, come on, he even wrote a Regular Expression!

## Notes & Links

* [Pure Function](https://en.wikipedia.org/wiki/Pure_function) - a function that produced no side-effects; and, whose outputs are determined entirely by its inputs.
* [CFML](https://www.lucee.org/) - ColdFusion Markup Language, a language specification for one of the most powerful web application runtimes.
* [Jest](https://jestjs.io/) - a popular JavaScript testing framework.
* [Unit testing](https://en.wikipedia.org/wiki/Unit_testing) - a low-level test of an individual unit of code.
* [Integration testing](https://en.wikipedia.org/wiki/Integration_testing) - a mid-level test of a group of software units running together.
* End-to-End / Functional testing - a high-level test of an entire software system, typically looking at happy paths through an application.
* Manual testing - using human to run tests on a piece of software.
* Automated testing - using computers to run tests on a piece of software.
* Static testing - evaluation of code without having to execute it (think linters and strongly typed languages).
* Testing budget - a concept in which the tests that can block a deployment have to run within a certain time window.
* [Rich Hickey: YouTube](https://www.youtube.com/results?search_query=rich+hickey) - please, just go watch all of his videos.
* [Software regression](https://en.wikipedia.org/wiki/Software_regression) - a bug that appears, and often breaks, a previously-working piece of code.
* [Guillermo Rauch](https://rauchg.com/) - CEO of [Vercel](https://vercel.com/).
* [REST Assured](https://rest-assured.io/) - a testing framework for application APIs.
* [Gatling](https://gatling.io/) - load testing software.
* [Feature flags](https://launchdarkly.com/features/feature-flags/) - tooling that allows you to turn parts of an application on or off without having to redeploy it.
* Strangler pattern
* [Ben Nadel: My Personal Best Practices For Using LaunchDarkly Feature Flags](https://www.bennadel.com/blog/3766-my-personal-best-practices-for-using-launchdarkly-feature-flags.htm) - a tome that Ben wrote on how he uses feature flags.
* [Kent C Dodds: Testing JavaScript](https://testingjavascript.com/) - a popular online course about about testing JavaScript.
* [EggHead.io](https://egghead.io/) - a popular subscription service that provides tutorials on web application development.
* [MockBox](https://testbox.ortusbooks.com/mocking/mockbox) - a module within TestBox that allows the internal execution of a software module to be observed.

If you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
