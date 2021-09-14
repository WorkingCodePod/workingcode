---
title: "011: Listener Questions #1"
description: The crew responds to listener questions and a particularly scathing blog post in response to episode 9.
date: 2021-02-24
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/011-listener-questions-1/id1544142288?i=1000510459724"></iframe>

[Cunningham's Law][cunninghams-law] states:

> The best way to get the right answer on the internet is not to ask a question; it's to post the wrong answer.

The crew recently experienced a bit of this law _first hand_ in response to [their episode on Testing][working-code-009]. [Adam Cameron][adam-cameron] - friend of the show and long-time friend of the hosts - posted a [scathing (but loving) rebuttal][adam-cameron-post] of _basically_ everything that Ben said in episode 009. This week, the crew meets to discuss Adam's post; and, to dig more deeply into how testing gets applied in real world scenarios.

Thew crew also attempt to pick apart the relationship between DevOps and engineering - a [question posed by LD2][ld2]. Just don't ask us (or anyone) to define what exactly DevOps is; you ask 10 different people and you'll get 15 different answers.

Oh, and Adam totally built [a website for the show][working-code]! So, heck yeah! It's built on [Eleventy][11ty] and is generated based on Markdown files.

### Triumphs &amp; Failures

- **Adam's Triumph / Failure** - His application had a Cross-Site Scripting (XSS) vulnerability that was exploited. Which is definitely unfortunate. However, he was able to take a bad situation and _turn it into an opportunity_ to practice transparency, clear communication, and a sense of urgency with his customers. In fact, in the end, he was commended by his customers for how well he handled the situation.

- **Ben's Triumph** - He attached some analytics to a user interface (UI) within his application and suddenly a part of the application which has historically been a blackbox was transformed into a rich, emotional experience in which he could "see" users actually consuming the tools that he built. This recent adoption of analytics (into his workflow) has forever changed the way that he will think about what is and is not an important part of the application that he's building. It's amazing how powerful "user empathy" can be to an engineer's motivation.

- **Carol's Triumph** - Her company is over-committed in terms of the work that they have on their schedule. But, instead of making the engineers freak-out over this planning problem, her managers are _doing their job right_ and are protecting their reports from the organizational chaos. It's rare to see managers that understand how to manage _both up and down_ within a company hierarchy! As Adam says in the episode, a good manager is worth their weight in gold.

- **Tim's Triumph** - His frustration over debugging an issue in Redis had grown to the point where he was walking around his house angry. But, instead of trying to _"just muscling through it"_, he decided to step back, **be kind to himself**, and take a break.

  > **ASIDE**: You won't know this from the current recording but this break gave him the opportunity to rethink the problem and ultimately come back and figure out what was going wrong. Such is the magic of mental rest and relaxation!

### Notes &amp; Links

- [OWASP: XSS](https://owasp.org/www-community/attacks/xss/) - consistently on the Top 10 vulnerabilities outlined by the Open Web Application Security Project (OWASP).
- Data Breach Response Plan - an organizational play that outlines how a company responds to data breaches, how quickly they have to notify users, and what immediate and longer-term steps they have to take to mitigate such breaches in the future.
- [Shattered Glass](https://www.imdb.com/title/tt0323944) - a movie in which Hank Azaria's character demonstrates excellent managerial skills.
- [Segment](https://segment.com/) - a popular data pipeline and aggregation platform.
- [Amplitude](https://amplitude.com/) - a popular analytics platform for digital teams.
- [Eleventy][11ty] - a simpler static site generator.
- [Adam Cameron: Thoughts on Working Code podcast's Testing episode][adam-cameron-post] - the rebuttal that we discuss on the show.
- [Cunningham's Law][cunninghams-law] - states, "the best way to get the right answer on the internet is not to ask a question; it's to post the wrong answer."
- [Test-Driven Development](https://en.wikipedia.org/wiki/Test-driven_development) - a test-first methodology for software application development.
- [Singleton Pattern](https://en.wikipedia.org/wiki/Singleton_pattern) - a software design pattern that restricts the instantiation of a class to one "single" instance.
- [Cory Haines](https://articles.coreyhaines.com/) - a well known programmer in the Ruby and testing worlds.
- [Ben Nadel: Singleton vs. Single Instance And A Decade Of Unnecessary Guilt](https://www.bennadel.com/blog/3380-singleton-vs-single-instance-and-a-decade-of-unnecessary-guilt.htm) - the realization that everything he thought about the "Singleton Pattern" was wrong.
- DevOps - who the heck knows what it actually is - platform things mostly? Code++? A mindset? A job title?

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[adam-cameron]: http://blog.adamcameron.me/
[adam-cameron-post]: http://blog.adamcameron.me/2021/02/thoughts-on-working-code-podcasts.html
[cunninghams-law]: https://meta.wikimedia.org/wiki/Cunningham%27s_Law
[11ty]: https://www.11ty.dev/
[ld2]: https://twitter.com/LD2/status/1357493535088332801
[working-code]: https://workingcode.dev/
[working-code-009]: https://workingcode.dev/episodes/009-testing/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
