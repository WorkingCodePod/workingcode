---
title: '018: Feature Flags (Finally!)'
description: Feature flags allow software engineers to separate the "deployment" of code from the "releasing" of code. Which means safer deployments; instantaneous roll-backs; smaller Pull Requests (PRs); incremental feature development; load-testing with real-world traffic; and - generally speaking - a big bowl of awesome sauce that you didn't even know you needed!
date: 2021-04-14
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/4744bc75-9c60-40cd-98ee-a3eb9683c895"></script><div class="redcirclePlayer-4744bc75-9c60-40cd-98ee-a3eb9683c895"></div>

For Ben and his team, few things have _fundamentally changed_ the product development life-cycle as much as [LaunchDarkly][launchdarkly], a feature flag management platform. Feature flags allow software engineers to separate the "deployment" of code from the "releasing" of code. Which means safer deployments; instantaneous roll-backs; smaller Pull Requests (PRs); incremental feature development; load-testing with real-world traffic; and - _generally speaking_ - a big bowl of awesome sauce that you didn't even know you needed! And, once you have it, you realize that you can't live without it.

_Mic drop!_

But, while Feature Flags may seem magical, _they aren't magic_. And, moving feature flags through a product development life-cycle requires a certain degree of discipline. Because if you leave feature flags in your code for too long, your application logic can quickly devolve into an unclear, unpredictable maze of control-flow spaghetti.

In other news, the Working Code crew is also about to embark on their fist book club adventure, starting with [Clean Code by Robert Martin][clean-code] (aka, "Uncle Bob"). We intend to review this book in the May 12th episode. Feel free to follow along!

And just when you thought things couldn't get any better, the Working Code Podcast now has a _party line_! Just kidding; but, we do have an **answering service at (512) 253-2633 (That's 512-253-CODE!)**. Please leave us a message with with your comments, questions, and anything else you feel like sharing. We miss hearing your voices!

### Triumphs &amp; Failures

* **Adam's Triumph** - Historically, when his team needed to host a private npm module, they've stored it in a private GitHub repository and then used git URLs within the `package.json` file. And, this worked _most of the time_. But, it was wonky and there were lots of quirks and edge-cases and they've been on the lookout for a better solution. Enter stage left: [GitHub Packages][github-packages]. These allow you to "officially" store npm modules right alongside the rest of your GitHub hosted code - no hacks, no troubles.

* **Ben's Failure** - He's generally very regimented about the hours that he keeps. But, in the wake of losing both his Project Manger (PM) and his Engineering Manager (EM), he's been struggling to properly prioritize all the work on his plate. And, instead of being smarter, he's opted to work _harder_ by putting in a few extra hours here-and-there. He understands that it's a _slippery slope_; and, not the life-style that he wants to live; but, if he can _just get ahead of it_, he's confident that he'll get back on the right track.

* **Carol's Triumph** - She's been wanting to build something with React as means to level-up on her front-end skills. And she finally finished going through a [Udemy][udemy] course on React! Next step: React side project (possibly to track her water intake).

* **Tim's Triumph** - He's launching a skunk works project that is based on a previous skunk works project. It feels a little bit rogue; and a little bit cowboy; but, it also feels kind of amazing and is something that Tim recommends to everyone (assuming that they have some free time to commit).

> **ASIDE**: A "skunks work project" is a secret project that the rest of (or most of) your company doesn't know about until there's a big reveal. These types of projects may _or may not_ be authorized by the company itself.

### Notes &amp; Links

* [LaunchDarkly][launchdarkly] - an amazing platform for feature flag based application development.
* [Flagsmith](https://www.flagsmith.com/) - a feature flag service that has hosted, cloud, and on-premise solutions.
* [Split IO](https://www.split.io/) - a feature flag service with a free tier option.
* [Ben Nadel: My Personal Best Practices For Using LaunchDarkly Feature Flags](https://www.bennadel.com/blog/3766-my-personal-best-practices-for-using-launchdarkly-feature-flags.htm) - on opus on how Ben's team uses LaunchDarkly and feature flags.
* [Ben Nadel: Viewing The LaunchDarkly Feature Flag Evaluation Process As A Pure Function](https://www.bennadel.com/blog/3612-viewing-the-launchdarkly-feature-flag-evaluation-process-as-a-pure-function.htm) - a helpful analogy for understanding how user targeting works in LaunchDarkly.
* [Adil Aijaz: Managing Feature Flags](https://www.oreilly.com/library/view/managing-feature-flags/9781492028598/) - an O'Reilly book on feature flag management.
* [StatsD](https://github.com/statsd/statsd) - the de facto standard for recording application metrics in web development.
* [FusionReactor](https://www.fusion-reactor.com/) - an application performance monitoring (APM) solution for the JVM.
* [Loggly](https://www.loggly.com/) - a log aggregation service that requires no proprietary agents.
* [Datadog](https://www.datadoghq.com/) - a modern (and totally awesome) platform for monitoring, logging, and StatsD metrics.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].


[clean-code]: https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM

[github-packages]: https://github.com/features/packages

[launchdarkly]: https://launchdarkly.com/

[udemy]: https://www.udemy.com/

[working-code]: https://workingcode.dev/

[working-code-instagram]: https://www.instagram.com/workingcodepod/

[working-code-patreon]: https://www.patreon.com/workingcodepod

[working-code-twitter]: https://twitter.com/WorkingCodePod
