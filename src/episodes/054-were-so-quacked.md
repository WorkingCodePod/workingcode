---
title: "054: We're So Quacked!"
description: "At 3:30 AM the day before Thanksgiving, Ben received an emergency page about a failing API end-point. Rushing to his desk, groggy-eyed and in various states of undress, he jumped into the #incident channel on Slack to see what was happening. What unfolded over the next 30-hours was the manifestation of Ben's worst nightmare."
date: 2021-12-22
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/eee65117-e7f1-49db-9ada-b41229a8469a"></script><div class="redcirclePlayer-eee65117-e7f1-49db-9ada-b41229a8469a"></div>

At 3:30 AM the day before Thanksgiving, Ben received an emergency page about a failing API end-point. Rushing to his desk, groggy-eyed and in various states of undress, he jumped into the `#incident` channel on Slack to see what was happening. What unfolded over the next 30-hours was the manifestation of Ben's worst nightmare. The moment he had been dreading for the last 4-years had finally come to pass: **two of his database columns had run out of storage space**! Using feature flags, emergency hot-fixes, shadow tables, and a database migration being performed over a transient and unstable terminal session, he and his team somehow made it through to the other side just in time to enjoy Thanksgiving turkey and pumpkin pie!

> "Hug your data engineers - they are amazing people!" &mdash; **Ben Nadel**

## Notes &amp; Links

- [Liquibase](https://www.liquibase.org/)
- [Percona Tooklit](https://www.percona.com/software/database-tools/percona-toolkit)
- [MySQL's Information Schema](https://dev.mysql.com/doc/refman/8.0/en/information-schema.html)
- [Datadog](https://www.datadoghq.com/)
- [CFSearching: CFQueryparam Matrix for MySQL 5](http://cfsearching.blogspot.com/2010/01/cfqueryparam-matrix-for-mysql-5.html)
- [Ben Nadel: CAUTION: Silent Value Truncation In CFQueryParam Tag In Lucee CFML 5.3.7.47](https://www.bennadel.com/blog/4157-caution-silent-value-truncation-in-cfqueryparam-tag-in-lucee-cfml-5-3-7-47.htm)
- [Ben Nadel: Recording Datadog / StatsD Gauges For Database Key Utilization](https://www.bennadel.com/blog/4166-recording-datadog-statsd-gauges-for-database-key-utilization-in-lucee-cfml-5-3-7-47.htm)
- [Ben Nadel: Inspecting Primary And Secondary Index Key Utilization For MySQL](https://www.bennadel.com/blog/4165-inspecting-primary-and-secondary-index-key-utilization-for-mysql-5-7-32-in-lucee-cfml-5-3-7-47.htm)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633 (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).
