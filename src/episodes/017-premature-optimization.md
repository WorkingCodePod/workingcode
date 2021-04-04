---
title: '017: Premature Optimization'
description: This week, the crew talks about "premature optimization". As Ben explained it to his wife, this is when you "solve problems that you don't have yet". But, what kind of problems are we talking about? Missing features? Missing methodologies? Missing performance characteristics?
date: 2021-04-07
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/1e04850f-0572-4cd7-a2be-d49595f964f7"></script><div class="redcirclePlayer-1e04850f-0572-4cd7-a2be-d49595f964f7"></div>

This week, the crew talks about "premature optimization". As Ben explained it to his wife, this is when you _"solve problems that you don't have yet"_. But, what kind of problems are we talking about? Missing features? Missing methodologies? Missing performance characteristics? It seems that every aspect of the development life-cycle offers up potential pitfalls in which we may chase "perfection" needlessly when all we really needed was something that was "good enough." In the best case scenario, premature optimization is a waste of time. But, in the worst case scenario, premature optimization can kill a project before it ever gets off the ground.

### Triumphs &amp; Failures

* **Adam's Triumph** - For a long time, he and his team have been correcting a recurring data corruption issue by manually opening a record in their administrative user interface (UI) and then re-saving that record. It's easy to do; but it's tedious and frustrating. After recently completing some of his high-priority work, however, Adam was _finally_ able to locate and _fix the underlying cause_ (a race condition between two asynchronous API calls). This removed a small point of friction; but, it had an outside effect on the team morale!

* **Ben's Triumph** - After feeling gut-punched over the poor performance of his HTML Email DSL (Domain Specific Language) when running inside of a Docker container, he deployed a sanity-check experiment to production and found that ColdFusion custom tags ran _68-times faster_ in production when compared to his local development environment. This completely removed his fear of using ColdFusion custom tags to generate HTML emails; and meant that it was totally _game on_!

* **Carol's N/A** - Unfortunately, Carol was out sick. Feel better Carol! We miss you and we hope you feel better soon!

* **Tim's Triumph** - He's been working hard to find common ground with his customers during the ideation phase of Product development. And although he sometimes feels like a marriage counselor, he knows that the best way to achieve success is to include and consult with his customers, even if he suspects that the final outcome will be the same. Ultimately, customers just want to _feel heard_; and to feel like their needs are being addressed in some form or fashion.

### Notes &amp; Links

* [Go Time: Episode 172](https://changelog.com/gotime/172) - An interview with Bill Kennedy discussing best practices around the design of Go software.
* [Meme: Science vs Engineering](https://imgur.com/gallery/KkUB0dL) - A meme that pits the elegance of science against the brute-force pragmatism of engineering.
* [Sandi Metz: The Wrong Abstraction](https://sandimetz.com/blog/2016/1/20/the-wrong-abstraction) - a blog post in which the cost of a little duplication is compared to the cost of the wrong abstraction.
* [Rule of Three](https://en.wikipedia.org/wiki/Rule_of_three_\(computer_programming\)) - a code refactoring rule-of-thumb that states an abstraction should be created only on the third time duplicate code is needed.
* [Kent C. Dodds: AHA Programming](https://kentcdodds.com/blog/aha-programming) - DRY vs. WET vs. AHA - several different rules-of-thumb for refactoring code.
* [Adam Tuttle: Errors Are Best When Emailed... Said Nobody Ever](https://adamtuttle.codes/blog/2013/errors-are-best-when-emailed-said-nobody-ever/) - a presentation on how to effectively monitor errors within your web application.
* [MongoDB is Web Scale](https://www.youtube.com/watch?v=b2F-DItXtZs) - a meme poking fun at the web scale fanatics that showed up after Document Databases were first introduced.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].


[working-code]: https://workingcode.dev/

[working-code-instagram]: https://www.instagram.com/workingcodepod/

[working-code-patreon]: https://www.patreon.com/workingcodepod

[working-code-twitter]: https://twitter.com/WorkingCodePod
