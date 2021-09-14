---
title: "026: Passwords"
description: "Web applications store a great deal of sensitive information. But, there is something categorically different about storing passwords."
date: 2021-06-09
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/026-passwords/id1544142288?i=1000524765068"></iframe>

This week, the crew talks about passwords. Web applications store a great deal of sensitive information. But, there is something _categorically different_ about storing passwords. Because—if compromised—a password from one application may grant a malicious actor access to another application. As such, it is essential that we store our customers' passwords using modern, one-way hashing algorithms that protect the underlying payload against increasingly powerful compute resources. And, that we have a way to evolve our password hashing strategies in order to stay a step ahead of potential attackers.

Of course, sometimes the best password hashing strategies is to _not store_ a password at all. Using a _"passwordless login"_ allows you to defer the responsibility of password storage off to another, trusted vendor.

Also, we've been doing this podcast for **half-a-year**! How awesome is that! Yay for us!

## Triumphs &amp; Failures

- **Adam's Failure** - While Adam has been quite keen on **Testing** code, he recently ran into a testing scenario that he found very challenging. And, he ended up taking half-a-day to refactor _already working code_ just so that he could add the tests. In the long run, it wasn't a waste of time; but, it was a very humbling experience in the moment.

- **Ben's Triumph** - After weeks of struggling to debug an authentication issue within a Sketch plug-in, Ben and his team finally figured out what was going wrong! As fate would often have it, Ben was the engineer that _originally wrote_ the problematic code - so, that was unfortunate. But, at least they figured out how to fix the user experience!

- **Carol's Failure** - Carol has been having trouble walking away from problems even when she feels stuck. So, instead of stepping back and clearing her head, she continues to beat it against the wall (often to no avail). She knows this is counterproductive; but, sometimes she gets lost in the details.

- **Tim's Triumph / Failure** - Tim finds himself coasting this week. Nothing has been all that note-worthy; either in triumph or in failure.

## Notes &amp; Links

- [OWASP Password Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Password_Storage_Cheat_Sheet.html) - industry standard best practices for storing passwords - covers Argon2, BCrypt, SCrypt, and PBKDF2.
- [Have I Been Pwned](https://haveibeenpwned.com/) - a service that tells you if your password has been exposed in a data breach.
- [1Password](https://1password.com/) - the world's most-loved password manager.
- [Authy](https://authy.com/) - a user-friendly two-factor authentication app.
- [Shibboleth](https://www.shibboleth.net/) - an identity provider solution.
- [OAuth](https://en.wikipedia.org/wiki/OAuth) - a standard for granting access to a website or application without having to provide it with your password.
- [SAML](https://en.wikipedia.org/wiki/Security_Assertion_Markup_Language) - a standard for exchanging authentication between parties.
- [Diceware](https://en.wikipedia.org/wiki/Diceware) - a method for generation secure, random passwords using playing dice.
- [NIST Password Guidelines](https://auth0.com/blog/dont-pass-on-the-new-nist-password-guidelines/) - Auth0 explains new passwords guidelines from NIST.
- [Single Sign-On (SSO)](https://en.wikipedia.org/wiki/Single_sign-on) - an authentication scheme in which one login grantes access to several, unrelated applications.
- [Netlify Identity Management](https://docs.netlify.com/visitor-access/identity/) - a solution for user management in a Netlify app.
- [Firebase Identity Management](https://firebase.google.com/docs/auth) - a solution for user management in a Firebase app.
- [XKCD: Password Strength](https://xkcd.com/936/) - A web comic about how we make passwords hard for people but easy for computers.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
