---
title: "025: Breaking Up With Your Stack"
description: ""
date: 2021-06-02
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/025-breaking-up-with-your-stack/id1544142288?i=1000523905989"></iframe>

There's no _one reason_ that companies _move away_ from or _onto_ a technology stack. Sometimes a given technology is no longer actively updated; sometimes the pool of developers that uses a technology shrinks, making it hard to hire new engineers or find community support; sometimes people just like the _new hawtness_; sometimes licensing costs become prohibitively expensive; sometimes there's a leadership change at your company; and, sometimes a team just _believes_ that a new technology will solve all of their problems (**spoiler alert**: _it won't_). This week, the crew meets to talk about reasons that they've move on from or stuck with a set of chosen technologies.

## Triumphs &amp; Failures

- **Adam's Triumph** - All of our recent talk of testing and "clean code" has had a _very positive impact_ on how Adam is writing his own code. He's become much more cognizant of his application's boundaries and modularity; which, has enabled him to organize dependencies in order to make them more testable (and mockable). In fact, he's been so motivated by this new-found perspective that he's even gone back and refactored a mission critical portion of a legacy application that didn't have any tests at all.

- **Ben's Failure** - He fancies himself quite good at debugging software. And yet, for the last 2-weeks, he's been _completely baffled_ by a bug in a portion of his application. No one on his team can reproduce the issue. So, all he's been able to do so far is add new logging statements and then comb through his log aggregator looking for clues. **It's maddening!**

- **Carol's Triumph** - In episode 020 - ["Carol Needs A Consult"][working-code-020] - Carol laid-out her plans to build an email-based integration with her company's ticketing system. Now, only a month-and-a-half later, she's thrilled to see this product really coming to life. It hasn't always been easy; and, they've hit some significant bumps along the way; but, so far, they haven't faced anything that they couldn't conquer together as a team. She's feeling lucky to be working with so many wonderful people!

- **Tim's Failure** - He created a Pull-Request titled, _"OMG, I can't believe I left this in the code"_. Apparently, while writing code for a new API-workflow, Tim hard-coded a failure-response into a network request so that he could test the "sad path" control-flow logic. And then, he **forgot to remove it**. For 3-days, he had production API calls all hard-coded to return failures. Fortunately, the code would fall-back to returning the _correct result_ on a subsequent retry. But, he's definitely feeling some acute Shame over this turn of events.

## Notes &amp; Links

- [Semaphore](https://adamtuttle.codes/blog/2021/introducing-semaphore/) - A minimalist Feature Flag engine for CFML apps.
- [Strangler Pattern](https://martinfowler.com/bliki/StranglerFigApplication.html) - A technique in which a new implementation slowly takes traffic from an existing implementation.
- [JAM Stack](https://jamstack.org/) - JavaScript, APIs, and Markup stand as the pillars in this newly-coined architectural approach.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-020]: https://workingcode.dev/episodes/020-carol-needs-a-consult/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
