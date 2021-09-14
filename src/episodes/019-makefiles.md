---
title: "019: Makefiles"
description: Today, the crew listens to Adam wax poetically about what makes makefiles so great.
date: 2021-04-21
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/019-makefiles/id1544142288?i=1000518032091"></iframe>

Adam Tuttle first came into contact with **makefiles** (pronounced "make files") back in high school when compiling code. But, at the time, he didn't really understand what they were or how they worked - he was just a consumer. And, after high school, years went by in which he never gave makefiles a second thought. That is, until, one fateful conversation with [Mark Mandel][mark-mandel].

Mark explained that he used makefiles to create aliases for complex Docker commands. This piqued Adam's curiosity; and soon, Adam went down the rabbit hole! Today, he uses makefiles extensively for complex shell commands that he shares across his entire team: building containers, deploying code, generating Pull Requests - and, he's only begun to scratch the surface!

Today, the crew listens to Adam wax poetically about what makes makefiles so great. And, we get to ask him all sort of questions like: can they be used to create `git` aliases? Can this be used with `npx` commands? Is this like npm run scripts? And, why are you still using "boring technology" that was built in the 70s?

This week's sponsored shout-out is **[Wonder Woman Tech][wonder-woman-tech]**, whose mission it is to highlight, celebrate, educate, and amplify Women, BIPOC, and the Underrepresented in Science, Technology, Engineering, the Arts, Math (STEAM), and Innovation.

And finally, don't forget that we are going to have our first book club episode on May 12th for [Clean Code by Robert Martin][clean-code] (aka, "Uncle Bob"). Feel free to read-up and follow along!

### Triumphs &amp; Failures

- **Adam's Failure** - In what can only be described as _unbridled enthusiasm_ for his team's switch to GitHub Packages, Adam tried to incorporate a few too many changes into what was originally supposed to be the simple swapping of URLs in various `package.json` files. In the end, the migration wound-up including a bunch of test automation and QA deployments which cost his team an additional day in person-hours. But, he did get it done!

- **Ben's Failure** - He feels like his muse has been on vacation for the last few weeks. Usually his brain is awash with a chaotic symphony of ideas; but, lately, it's just been quiet. These things run in cycles for him; so, he's confident that he'll be back to normal in the near future.

- **Carol's Triumph** - She just finished her first 2-week rotation on Zendesk duty. Her company rotates all engineers through the Support team twice a year in an effort to build customer empathy and to help educate the engineers on the full landscape of their product-suite. Carol walks away from her rotation with a _deep sense of gratitude_ for her team; and for her customers!

- **Tim's Triumph and Failure** - After months of mothering his "skunk works" project from ideation and development through to deployment and release, he's suddenly struck with a case of "coder's empty nest syndrome". Without any fires to put-out or customers to consult with, he's not exactly sure what to do with himself. That said, Tim is thrilled to have finally gotten his first _hater_! And while this shade is almost certainly being thrown in jest, it definitely made Tim's week - _his heart is overflowing_!

### Notes &amp; Links

- [`gh`](https://github.com/cli/cli) - GitHub's command-line interface (CLI).
- [`npx`](https://docs.npmjs.com/cli/v7/commands/npx) - Run local and remote binaries from the command-line in your Node application context.
- [npm Run Scripts](https://docs.npmjs.com/cli/v7/commands/npm-run-script) - Run arbitrary scripts from your `package.json` file.
- [Homebrew](https://brew.sh/) - A popular package manager for Mac and Linux.
- [`grep`](https://linux.die.net/man/1/grep) - A shell command for searching files and input streams.
- [`find`](https://linux.die.net/man/1/find) - A shell command for searching for a file within a file tree.
- [`awk`](https://linux.die.net/man/1/awk) - A shell command for pattern scanning and processing language.
- [`sed`](https://linux.die.net/man/1/sed) - A shell command for stream editing and text transformation.
- [`xargs`](https://linux.die.net/man/1/xargs) - A shell command for building other command-line executions using the input stream.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[clean-code]: https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship-ebook/dp/B001GSTOAM
[mark-mandel]: https://www.compoundtheory.com/
[wonder-woman-tech]: https://wonderwomentech.com/
[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
