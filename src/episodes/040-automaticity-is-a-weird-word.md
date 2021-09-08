---
title: "040: Automaticity Is a Weird Word"
description: "On today's episode, the crew talks about how they use databases; the role of atomic transactions in the reduction of application complexity; and, whether or not they've ever felt "held back" by the limitations of a relational database management system. Full disclosure, all of the hosts have far more experience with traditional databases when compared to NoSQL databases."
date: 2021-09-15
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/9689f695-0027-414b-b322-a7cda2650c6b"></script><div class="redcirclePlayer-9689f695-0027-414b-b322-a7cda2650c6b"></div>

The other day, Ben was listening to an [episode of the MongoDB podcast in which Mat Keep][mongodb-67] shared a story about the adding of **atomic transactions** into the MongoDB product. Mat said that the engineer who spearheaded the effort used to joke about the fact that his team was spending a huge amount of time working on a feature that **90% of developers would never need**. For Ben - who leans heavily on transactions for referential integrity - this sounded like an crazy statement. But is it? Are database transactions overrated? Or, is it more so that the _type of use-cases_ that work best in a document database are also the type of uses-cases that don't really need transactions?

On today's episode, the crew talks about how they use databases; the role of atomic transactions in the reduction of application complexity; and, whether or not they've ever felt "held back" by the limitations of a relational database management system. Full disclosure, all of the hosts have far more experience with traditional databases when compared to NoSQL databases.

> **NOTE**: In the show, Ben mentioned that a document database like MongoDB can't enforce schemas like a relational database. And while this was true in earlier versions of the MongoDB product, it is no longer true. In recent updates, MongoDB has added [schema validation and enforcement][mongodb-schema].

## Notes &amp; Links

- [MongoDB Podcast: Episode 67 - MongoDB Evolved with Mat Keep][mongodb-67]

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[mongodb-67]: https://mongodb.libsyn.com/67-mongodb-evolved-with-mat-keep
[mongodb-schema]: https://docs.mongodb.com/realm/mongodb/enforce-a-document-schema/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[editor]: https://www.zcross.media/
