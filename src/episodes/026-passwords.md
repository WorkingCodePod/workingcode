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

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/026-passwords.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Carol:** So, Ben, what's your password?

[00:00:03] **Adam:** One, two, three, four, five. Sounds like the combination a d hole would have on his luggage. That's

[00:00:14] **Ben:** a, I know Carol doesn't get all the movie references.

[00:00:17] **Carol:** Oh, those were, there were movie references in there? Yeah, I didn't

[00:00:20] **Ben:** get any of that. That's a reference to Spaceballs.

[00:00:35] **Adam:** It is show number 26 for June the 9th and on today's show we're going to be talking about passwords and it's probably one of those topics where it seems like we couldn't possibly have enough content to fill a whole podcast and yet... Here we are. Swordfish. It's always swordfish. Hunter 2. First, as usual, we're going to do our triumphs and fails.

[00:00:58] **Adam:** And Ben, it's your turn to go first. What do you got this week?

[00:01:00] **Ben:** I'm going to turn it around. I've had a couple of failures in a row, so I'm going to flip over to triumph for this week. Me and my team have been working hard trying to find a, uh, an issue in our system where people are occasionally getting logged out from a plugin that we have in the Sketch graphics program.

[00:01:18] **Ben:** And, uh, probably it took about two weeks to figure out what was happening. We were sharing, uh, some web tokens between the web session and the plug in session, which the plug in session was supposed to have its own tokens. So what was happening is every time someone got logged out of their web session, it would invalidate those tokens, which would inadvertently log them out of their plug in within craft.

[00:01:42] **Ben:** And, uh, it just, it felt really good to be able to figure out what was going on. And, uh, even though it took a while, and even though I hate to say this, I'm the one who wrote the original problematic code, which, uh, you know, nobody wants that scenario, but, uh, I do feel good having solved it. That said, we're now trying to figure out why some of these users are getting 502s, uh, bad gateways.

[00:02:07] **Ben:** And, uh, that's becoming a much more challenging problem because we have a distributed system. So we have our, uh, external layer of application code. I think it runs on Amazon's application load balancer. And then we have Kubernetes ingress controllers and then those, uh, forward requests to ColdFusion pods.

[00:02:27] **Ben:** But then the ColdFusion pods have an NGINX. Uh, service running in front of the, the ColdFusion port. So it's just trying to figure out where the request is dying and which, which network cop can't talk to the network, next network, which network cop can't talk to the next network point. It's just, uh, it's very challenging because it's hard to know if something's dying inside of an application code or if it's not getting to the application in the first place, and I don't really know anything about Kubernetes and it's hard to go to our.

[00:02:56] **Ben:** Platform people and have them help us because sometimes they'll just say like, Oh, 502s happen sometimes. Distributed systems are challenging, but that's not the, yeah, it's not, it's not a satisfying answer.

[00:03:10] **Tim:** I, I saw you posting about how you could put something in the ELB load balancer, so you can track that.

[00:03:18] **Tim:** Was that, was that similar to what

[00:03:20] **Ben:** you were? That's, so that's, we're trying to figure out where these 502 bad gateways are coming from. So essentially, we have a request that originates on a user's computer. And that request ends in a, in a bad gateway, but we don't know where in the network stack the failure is happening.

[00:03:37] **Ben:** So we've been trying to add tracing headers all over the place, trying to see where those tracing headers, headers stop showing up in the logs. But it's, it's been challenging because we don't have control over where all the logging happens. So, but, so most of the triumph, but some failure.

[00:03:54] **Tim:** And what feature was it that, that you added to the ELB for Amazon to, to trust in the

[00:04:00] **Ben:** header?

[00:04:01] **Ben:** Yeah. So if you initiate a request with a header, that's like X Amazon X dash Amazon dash trace dash ID, it will include that value in its own logs when it's logging the, uh, I guess the access logs for the ALB.

[00:04:16] **Adam:** Okay. I thought

[00:04:17] **Carol:** you have to enable that in AWS though. Like you have to have it as part of your account in order for that to work.

[00:04:24] **Ben:** It's possible because

[00:04:25] **Adam:** logging is, I guess,

[00:04:26] **Carol:** expensive. It is, yeah. Yeah, you may not be able to just put it in, you may not be able to just put it in a header and turn it on. You may actually have to have like your DevOps or your team actually enable it for your account before it works.

[00:04:38] **Ben:** And this is, I mean, this is so much of what the debugging looks like right now.

[00:04:42] **Ben:** We just look in the logs to see what shows up and we notice that there is a trace ID header showing up and we're like, oh, that's interesting. What does that mean? And that's when we found the logs and said you could modify that as part of your original request. So a lot of it is just searching, hunting and pecking almost for what might be meaningful information in the logs.

[00:05:01] **Ben:** It's very frustrating. How about

[00:05:05] **Adam:** you, Adam? What do you got? Um, well, unfortunately, I'm going to break the streak. This week I got a fail. Um, he's only human. Yeah, yeah, it had to happen eventually. I have been on this kick lately, um, very much thanks to, um, some inspiration from Adam Cameron and from, uh, Clean Code.

[00:05:26] **Adam:** But I've been trying to do a lot more testing and so this week I thought it would be fun to I was starting the some work on a project to refactor out a computationally expensive process from one service into its own service so that when the when this one drowns in work, it doesn't take down the other ones.

[00:05:45] **Adam:** Or the other pieces running in its existing home. And, um, so I was like, okay, well, it's, this is going to be a small thing. It's JavaScript, so I know that the testing tooling I'm using Jest is, uh, pretty good. So I'm going to take this opportunity to try and TDD this thing and, you know, write the test first and, and try to do that whole thing.

[00:06:05] **Adam:** Well. I made it maybe 20 minutes before I was like, legit stuck. So when I say that I spent like 20 minutes on this before I got stuck, really, that means that like, I made some forward progress for 20 minutes and then I got stuck and I spent the next like. Four and a half hours spinning my wheels, making literally zero progress, just trying to figure out why I was stuck and how I can get past it.

[00:06:28] **Adam:** Yes. I did use it as an opportunity to produce some content for my blog. Not a total loss. So I wrote up, you know, that story. Well, so we touched briefly recently on the concept of learning in public. And, uh, you know, that also sort of struck a nerve with me. So I'm, I'm just trying to, um, continue to be productive and grow and, and expand.

[00:06:51] **Adam:** Um. Heck yeah. Uh, you know, just get, become a better developer in every way that I possibly can. And so, you know, I, I basically what I'm hoping it is, is I turned, I started a series of blog posts that are going to be like, Here's the problem that I had and, you know, this is what I was thinking. And over time, it'll show, um, you know, why I, why I was wrong and, you know, in what ways I was wrong and how to do it the right way.

[00:07:18] **Adam:** Um, but like I said, it's a fail. I spent like half a day on the stupidest possible problem. I'm past it now. Um, but yeah, it was, it was just awful. I felt like a total failure, right? I've, I've been programming professionally for like 20 years and. Uh, I know testing concepts pretty well, but then like 20 minutes into this TDD effort, I just like totally bombed.

[00:07:44] **Adam:** I felt like a failure all day that day. So that's my failure. So Tim, how about you, man? What do you got going on? I, well, I got a

[00:07:56] **Tim:** question. What is... In between a triumph and a failure.

[00:08:02] **Adam:** Yeah, there we go. Fair enough.

[00:08:04] **Tim:** Because I, I can't, I mean, nothing I think rose to the level of a triumph this week and nothing fell to the floor as a failure.

[00:08:13] **Tim:** It was very much steady state this week. Um, lots of waiting for stuff. Um, I, I get the feeling that a lot of people at our company have gotten vaccinated and now they're going doing stuff and they're kind of engaged in personal stuff and it's like, I spend a lot of time waiting. I'm waiting on legal. I'm waiting on, you know, corporate.

[00:08:36] **Tim:** I just, and I'm in sort of in between projects right now. And I've got other people working on projects that I'm not involved in. I'm just sort of like overseeing. So it's like, yeah, nothing really. Shook my world this week, so. All right. I don't know if it's a triumphant

[00:08:53] **Carol:** affair. So we, uh, we had the meeting today and we actually talked about our bandwidth for the next few months.

[00:09:00] **Carol:** And it's pretty much like, and you have to take into account that everybody who hasn't been able to travel or do anything is now taking PTO. So we're going to be like way understaffed from where we were, so don't expect much work to come out because you've siloed off these people for these big projects and now our actual.

[00:09:17] **Carol:** Team supporting this is a lot less, plus people now are actually taking summer PTO because they're vaccinated. And several people were like, yeah, we're taking long, like longer than normal vacations and we are not going to be working. We're going to enjoy our time off

[00:09:31] **Adam:** finally. Yeah, I think

[00:09:33] **Tim:** we're kind of falling into that because it's, um, we just did finish up.

[00:09:37] **Tim:** A huge PCI audit and I always

[00:09:40] **Adam:** cordon off a lot of my time to the

[00:09:42] **Carol:** audit. And those kind of just suck the life out of your whole team. They are exhausting. They are exhausting. If you've never been through a PCI audit and tried to be compliant, it's, it's tedious and

[00:09:54] **Adam:** nerve wracking. I

[00:09:56] **Tim:** mean, everything went fine and there was no, there was no issues.

[00:09:58] **Tim:** It's just, it's a lot of anticipation and documentation and, and having meetings for things that really, every year you say the same thing. You just, you just hope someone doesn't ask you a new question. You're like, Gotcha! You've been lying all these years.

[00:10:13] **Adam:** Because you feel like that's what they're doing.

[00:10:15] **Adam:** Yeah, yeah, but

[00:10:16] **Tim:** uh, yeah, that's all, yeah, I don't know. That, that's, it is what it is. Sorry guys, it's neither here nor there. Carol,

[00:10:23] **Adam:** how about you?

[00:10:23] **Carol:** So I am pretty much where Adam is. We don't plan any of this, right? We just kind of jot down our notes and he was still typing when I type mine up. But this week I have found myself spending way too much time stuck on things because I refuse to walk away from it.

[00:10:41] **Carol:** So small things that could be resolved if I had a clear head are now taking hours because I keep finding another post about how to fix this and you could do it this way and then I go try it. Well, I don't like that way. So I go find another way and then I want to try it half and half. I want. And I'm going to put it all together and see what piece of it I'm missing.

[00:10:59] **Carol:** So where I could have spent, you know, an hour working on a problem, I spend half a day working on it because I refuse to let myself go think about anything else. So I've got to get back to where I walk away, I pick up some tiny little. You know, bug out of the backlog, go work it, and then come back to the problem as opposed to just trying to like tread my way through this and brute force my way in that door and make it work.

[00:11:25] **Carol:** So yeah, I'm going to walk away. I'm going to not be so hardheaded and keep reading. I'm going to do better.

[00:11:33] **Ben:** I think it's really nice to be able to step away and work on small things. I find that to be hugely helpful with clearing my head.

[00:11:42] **Carol:** Oh, it is. It is. Because then, you know, I kind of, in the back of my head, I'm still thinking about what's going on, but it's not my total focus.

[00:11:50] **Carol:** Where the other way, I'm just stuck. And I'm not getting anywhere. And I'm still stuck. I'm not getting any better. So, yeah. It's been a little bit of a failure this past

[00:11:59] **Adam:** week with that. Okay. Well, I said it earlier, you guys, this is episode number 26. Do you know what that means? Um, if you reverse

[00:12:10] **Carol:** it, it's 62.

[00:12:12] **Adam:** It's a significant number. That means it's been a half a year. We've been doing this for six months. Holy guacamole. I know, right? That can't be right. Yeah.

[00:12:22] **Carol:** Did you do your math right? We've talked about this. You can't do date math very well.

[00:12:27] **Adam:** I just went off of 52 weeks divided by two is 26. That one's a little easier for me.

[00:12:31] **Adam:** We've been

[00:12:31] **Ben:** pretty consistent,

[00:12:32] **Adam:** I believe. We have been, uh, extremely consistent. Am I the

[00:12:36] **Carol:** only one who's missed episodes?

[00:12:39] **Adam:** Yeah. Yes, I think so. No,

[00:12:40] **Carol:** no, no. No, Adam. We cut Adam out of

[00:12:42] **Adam:** one. Yeah. We did, uh, reschedule one for my benefit. Ah. Cool. So today we wanted to talk about passwords, and this was my idea for our show topic, so I guess I'll kind of lay out sort of some high points, some things that I hope we talk about, and we'll see where it goes.

[00:12:57] **Adam:** I guess the reason that I brought it up is because I see so often a couple of things. I see websites doing it wrong and like very clear, obvious red flags that they're storing passwords incorrectly. Yes. And then it's less common, but I still also see Developers asking questions that indicate that they are doing a poor job of storing passwords well.

[00:13:20] **Adam:** So I wanted to talk about the basics of storing passwords safely, and specifically why you bcrypt instead of something like MD5 or other earlier hashes, hashing algorithms. And then when you should reach for a third party service, and exactly what are those red flags that I was talking about. That screen, this website is going to store my password insecurely.

[00:13:46] **Adam:** And I like to talk about

[00:13:47] **Tim:** going passwordless.

[00:13:50] **Adam:** Yeah, let's do it.

[00:13:51] **Ben:** Well, can we just touch on the idea of things leaking? Because I think that's, that might be a framing that people don't initially think about because when you think about why I should even hash a password, people might look at their own infrastructure and be like, well, I store every other piece of data and clear text in my database.

[00:14:09] **Ben:** And a lot of that is important information. Like what makes passwords so special? And I think the idea here is that. You have to operate under the assumption that your password will be stolen, or that the persistence for your password will be stolen, or one day. So, the reason for the hashing of passwords...

[00:14:28] **Ben:** is to prevent someone who has already maliciously gained access to that data from being able to, to interpret or to be able to understand what the original password was. Yes.

[00:14:39] **Adam:** And the benefit that they gain by being able to see what your password is, is that, you know, generally, if we have your password stored in the database, we're going to have probably an email address.

[00:14:52] **Adam:** That's become pretty much universal for user ID. So if I have your email address and the password that you used on my website, there is a reasonable chance. Because people are lazy that that email address and password will work on some other websites, whether it's Facebook or your Gmail or your corporate VPN.

[00:15:10] **Adam:** And that is a certainly a best practice that I would advocate is use different passwords for everything. And yes, that makes it hard. And so that is why you should use the password manager to do that for you. And I think I want to head off at the pass as well. People who might be thinking at that moment, well, I'm just making this dinky little web game.

[00:15:27] **Adam:** Yes, you know, you have to have an account and sign into it, but who cares? Like, you know, if my data leaks, they're not going to get anything sensitive. Well, the thing that they're getting is an email address and password combination, right? And that could be useful elsewhere. Even if you've done everything else other than storing that password poorly.

[00:15:43] **Adam:** Correct. And there's nothing of use in your data. That combination is useful. Yeah.

[00:15:49] **Tim:** So someone, someone hacks your site and they're going to take that data. It might not mean much to you, but they're going to put it in a database, you know, give it to ScriptKitties and they're just going to brute force. Yep.

[00:15:59] **Tim:** Run on every system that they can get a hold of your, your username and your password. If you were one of those people that use your same username and password for everything, you're going to get hacked in a system that

[00:16:11] **Adam:** you do care about.

[00:16:12] **Carol:** Right, and you, I mean, I don't want to reference it as like you are going to be the one, but your users are going to be the one.

[00:16:18] **Carol:** So it's not you're going to get hacked, it's going to be everyone who trusted you with their information is going to be the ones

[00:16:23] **Adam:** who get hacked. Well,

[00:16:23] **Tim:** I mean, if they got it out of you, they,

[00:16:25] **Adam:** you got hacked. Yeah, well, you did, but yeah. Well, there was a leak. Yeah, it was Hexum. So, um, and I know that we're kind of making this sound very nefarious and, and it almost sounds like something you can go, yeah, but does that really happen?

[00:16:40] **Adam:** And I'm telling, I'm here to tell you that absolutely happens. There's a website, haveibeenpwned. com. That's p w n e d. com. I get, I mean, it's run by a very well known at this point security researcher, and this is pretty much his job now is running this website. I get emails from this website a couple of times a year saying such and such website uh, was breached and the information that they had, your email address, was in the breach, was found in a Uh, a data set available for sale on the dark web somewhere.

[00:17:13] **Adam:** Mm hmm. Nice. Your email address, and whether it was hashed or not or whatever, was in this, uh, set of data that's for sale.

[00:17:21] **Ben:** I don't know if, uh, 1Password, which is a password manager, I don't know if it pulls from the same data set, but I have old logins stored in 1Password. When I view them, I get a big banner across the top that says this login's been identified in a breach.

[00:17:35] **Ben:** Mm hmm. Yep,

[00:17:35] **Adam:** it does. They

[00:17:36] **Carol:** use, um, they use Hightower, I think. I think, isn't that what they use? I'd have

[00:17:40] **Adam:** to Hightower pull from

[00:17:41] **Carol:** here? I don't know. It might. I don't remember. I know that, yeah, I thought that it used Hightower when I had looked before. But I love that because I'll get notification even if I use the same password twice.

[00:17:51] **Carol:** One password's like, you've used this on another, like, login that you have saved, so are you really sure you want to use this again? Because now you've duplicated

[00:18:01] **Adam:** it. I think the feature in 1Password is called Watchtower, maybe that's what you're thinking of. Yeah, maybe Watchtower. I think Hightower might be like a Git client or something.

[00:18:08] **Adam:** Anyway, we're kind of off track here. We're kind of off track. Ugh, even when I tried to correct it, I couldn't get it right. We're kind of off track here, so let's get back to... What's up? Sorry,

[00:18:19] **Ben:** Tim keeps trying to talk and I think he's muted.

[00:18:23] **Tim:** Yeah, I was just saying that Chrome does the same thing, right? So if you save a password to Chrome, it'll tell you, you know, your secure, your past, this password you used is, has been leaked on the web.

[00:18:33] **Tim:** Yep.

[00:18:34] **Adam:** I think they all probably come back to this. Probably. Yeah. And I'm looking

[00:18:38] **Tim:** at, I'm looking at, have I been pwned right now? I've got, uh, what about 19 data breaches that affected me? I need to clean that up.

[00:18:48] **Adam:** Well, that's one of the things I love about 1Password. It tells me which ones are bad and I just go and I've changed those passwords on those websites and it's easy.

[00:18:55] **Adam:** Cool. So, basics of password security. Anybody have something you want to throw out there, or should I just go for it? Always use password. The actual word, password. Yeah, just password. Okay, so storing passwords, right? If you, if you are not going passwordless, if you're not using single sign on, then, um, how do you store passwords well?

[00:19:16] **Adam:** So the, the basics are you need to be able, you need to be using a one way encryption or hashing algorithm to store that. You need to salt. The password before you hash it, and What else? Is it really that simple?

[00:19:31] **Carol:** This sounds like something you should put like in a frying pan and eat. Like your hash and your salt and let's get it all together.

[00:19:36] **Adam:** Yeah, I mean, we'll go through the details of these things, but I feel like there was more that I wanted to mention. Okay, so what's the worst thing you can do? You can store the password in plain text in the database right there. Where you see it. When your password is password, we just see the word password in that database column.

[00:19:52] **Adam:** That's terrible. A step up from that, but still also terrible, would be to run. That password, actually, let's, let's kind of take some middle steps here. If you were to like base64 encode that password and throw it in that database column, that's also terrible in part because that's not encryption at all.

[00:20:11] **Adam:** That's just changing the encoding. So easily decoded back and super fast. Um, so if that data were to leak, then it's trivial for somebody to convert that back to the plain text. Very quickly. MD5. Not decodable, so you can't, like, put in the hash that you get from an MD5, uh, hashed password and get the clear text password back, but, um, MD5 runs fast enough on modern hardware that most, uh, frequently used passwords, most of the passwords that are common for people to use.

[00:20:48] **Adam:** are well known what their MD5 hashes are. Ah, so they're

[00:20:51] **Carol:** not unique.

[00:20:52] **Adam:** Yes, you'd be able to figure out what it was. So, so while, while I can't say, you know, hash ABC123 equals password God, I can say, oh, I recognize that hash and it is God. That, yeah. For example. Right. Um, and that's what's called rainbow tables if you ever hear, um, that term.

[00:21:12] **Adam:** It's basically somebody has that sort of master list of known MD5 hashes. And So that kind of brings me on to the next thing, which is, um, iterating your hashes. So, proposed or recommended at times is to hash it and then hash it again and hash it again, however many times you want to do. Um, you take the output of the first hash and put it in as the input to the second hash and so on down the line.

[00:21:36] **Adam:** Um, and that way, so for example, if that first, um, hash of your password God is a known hash, In theory, you're making it harder to get to it by going the second time. Well, Rainbow Tables, there's like multiple layers, right? So you can go 11 layers deep or whatever, however many are readily available. Okay, so that's that.

[00:21:54] **Adam:** So we talked about hashing. So the next thing you would do is salt your passwords before you hash them. So salting is just adding some random content to the beginning or the end of the string before you hash it so that you are

[00:22:08] **Carol:** So basically it'd be like God Carol, then let's go hash that. Does it make it harder?

[00:22:13] **Adam:** Well, so this is not something that the user should do. Right. Yeah, I was just clarifying. Yeah. Um, so me as the developer, I should generate some random characters to throw at the beginning or end of the clear text password before I hash it. So that, that also helps change what the, right, so if your password was God and I salted it, then the hash is now going to be different.

[00:22:39] **Adam:** And it's going to be vastly different because that's the way MD5 works, is small changes on the input produce large changes on the output. So

[00:22:45] **Carol:** if your salt is generated, do you store your salt?

[00:22:47] **Adam:** Good question. So, um, the sort of the first level of salting is just have a single hard coded salt in your application, right?

[00:22:54] **Adam:** So it's always, you know, my app. Carol. Yeah. Um, and I haven't done it before.

[00:23:00] **Carol:** Stop laughing, Ben.

[00:23:02] **Adam:** The, the next level up from that would be to generate a unique salt for each Uh, user and store that like on their database record as well. So that, okay. Um, that way, for example, if your database were to leak, uh, and so not only do they have your hashed passwords, if, if you have a, if you have the same salt for every user, then they can compute those.

[00:23:28] **Adam:** known hashes pretty easily as well. But by having a different salt for every user, they would basically have to recompute the entire rainbow table set for each user. Yeah. Yeah. To try and figure out if they have matching data. And then, so there's, yeah, there's hashing, there's salting, and there's, uh, iteration or repetition.

[00:23:45] **Adam:** I think that's it. That's all that's immediately coming to mind. That's pretty much the basics of it. Yeah. Right. So then I actually kind of had this realization a little while ago, maybe a year or two ago. I know that bcrypt uses a different algorithm for hashing. It's not MD5. It's another, you know, whatever super secure algorithm.

[00:24:06] **Adam:** Oh, it's Blowfish. It's one of the Blowfish algorithms. But what I think is sort of the genius thing about bcrypt, there's a couple of really smart things about it, but the, you, you run your bcrypt on the input password when you're like creating the account and it generates a random salt for you. And, uh, it'll do the repetitions of hashing for you.

[00:24:29] **Adam:** You tell it how many repetitions you want to do. And the output... is the encrypted password. Not encrypted. I don't want to use the word encrypted because it's not encryption. You can't decrypt it. But, so the output is the hashed password. One way hash. Right. Still one way hash. But the output is a hashed password, but also it's a, it's basically like a delimited string.

[00:24:50] **Adam:** It has the, it includes the salt and the number of repetitions of hashing and the final hash all in that same string in a way so that Given that value with the salt, the repetitions, and the hashed string as input plus the attempted login password, um, it will repeat the same thing and do the comparison so that you know they are, uh, the same inputs so that the, the, the login was successful, right?

[00:25:20] **Adam:** And, and so what by,

[00:25:21] **Tim:** what I guess that buys you is so if I do use the same password over and over again and you are encrypting it and, or hashing it and salting it even, even though it's the same password, it's not going to be the same hash. So if someone gets a hold of that hash. They can't use it as a known thing because it's, it's a randomly iterative generative thing that it's kind of going to be unique to your site.

[00:25:45] **Tim:** It's not going to match anybody

[00:25:46] **Adam:** else's. Yes, but that's all true for salting in general, right? If you, if you were to do unique salts for every user, then and do it manually, that would be... Also true in that situation. I guess I'm kind of building up to what make, what I think personally makes bcrypt pretty genius for me.

[00:26:03] **Adam:** Okay. So it does this whole thing for you. It does the repetitions for you. You plug in. Okay. Um, these are the number of repetitions I want to use. Um, and it does all that for you, and then you just pass in like, okay, here's the known password with, and it has the salt and the repetitions built in, and here's the value I want to test.

[00:26:19] **Adam:** Do these, is this the same password? And it just computes the, uses the same algorithm, that salt and known repetitions from the previously saved password on the test value, and if they generate the same hash, then they're the same password. That's how you can do a comparison without being able to decrypt it.

[00:26:35] **Adam:** Oh, that's genius. Okay, now. Get this, so one of the awesome things about Bcrypt is because it's got that repetition count built in. The whole point of repetitions is so that the algorithm can grow with you as hardware gets better, right? So part of the reason that we have to change the algorithms, the hashing algorithms that we're using for these things over time is because the hardware gets better at computing those hashes, and so computing those rainbow tables or whatever becomes easier or just brute forcing.

[00:27:03] **Adam:** Trying to crack a password becomes so much easier. So with bcrypt, you can say, you can just increase the number of repetitions. You can go up by orders of magnitude, right? Just add a couple of zeros on the end and now all of a sudden it takes a lot longer, a lot more compute power to, uh, to compute that hash.

[00:27:19] **Adam:** Keeping it at a reasonable level for a single login, but at an expensive level for somebody that's trying to brute force it. And because that repetition count is baked into the password as it was saved, when the person, you know, the legitimate user set their password, it can be used to decrypt that, and then when you, when you want to increase your repetition count, the next time that the user logs in, You can say, okay, well, they just logged in.

[00:27:44] **Adam:** This is successful. They were on 50 repetitions and now we're at 5, 000 repetitions. So while I have their clear text password here in memory, I'm going to recompute their hash and update the database as well. So now their password is more secure. That's pretty cool. And it's all baked right into the algorithm, except for that part about, like, re computing

[00:28:05] **Carol:** it.

[00:28:05] **Carol:** So it pretty much, like, just slows down anyone's ability to actually compute over it, so once you're, or to search over it, so once, you know, like you said, like, if the hardware gets better, then now it just becomes slower for them to try to

[00:28:16] **Adam:** get it. Yep, and as If I don't log into your website for a year and in that year you've increased your password repetition, your hashing repetition a couple of times, I'm still able to log in because my saved password has the number of repetitions as part of that saved password.

[00:28:35] **Adam:** So it doesn't do it too many times and then try to compare and get the wrong hash. Right. So just to

[00:28:41] **Ben:** put a finer point of clarity on what I think you're saying is that in a single database of users and passwords, You can have individual records actually stored at different hashing strengths and then individual records can be evolved over time.

[00:28:58] **Adam:** you would choose to do, to be clear. Right, but

[00:29:00] **Ben:** it just happens. Because you cannot decrypt the password because you can only re save it at a stronger encryption level, stronger hashing level. At the time you have it. At the moment you have that clear text password, which is only at the time of login. You can't just...

[00:29:18] **Ben:** Update an entire swath of records. You actually have to do it at a particular point in time based on a user action. It's

[00:29:25] **Adam:** very cool. Yeah, perfectly put, I think. Yeah, you're right. It is very cool. So, Tim, the thing that you had suggested we talk about, um, going no password, I think is kind of similar to this other thing, other point I wanted to make about using a third party service.

[00:29:37] **Adam:** Like, when should you reach for it? And when you do, what are the implications of that? Is that, would you agree? Uh, no,

[00:29:43] **Tim:** actually, uh, we're doing it without a third party service.

[00:29:47] **Adam:** Oh, okay. Well, let me hear about that.

[00:29:49] **Tim:** Okay, so what we're doing for one of our products, it's a new product we're launching. The way the process works, it's kind of a one off.

[00:29:56] **Tim:** It's not a site that you're going to go to often. It's going to be a very transactional sort of site. So rather than having a password situation, what we do is we send, we collect their email address and we collect their mobile phone number. If you don't have either of those things, you're not going to be able to use the service.

[00:30:15] **Tim:** So, send them an email, email says, click this link here and we know both those items, we know those things. So, they click the link, they come in, they have to verify their phone number and enter it and when they verify their phone number and it matches, then they also, they get a text message with the code and then they verify the code.

[00:30:32] **Tim:** And so, we never actually have them create a password ever, they just, that is going to always be the login

[00:30:39] **Adam:** procedure. It's almost like

[00:30:41] **Carol:** you skip the password and go straight to like the multi factor authentication, right? You're like, oh, I'm just going to skip your password. You told me your phone number's right.

[00:30:50] **Carol:** So just go verify it the other way, which is, you know, like with the Authenticator app or with the phone

[00:30:55] **Adam:** number text. Yep. So

[00:30:57] **Tim:** not super sophisticated, but it, and it does, it is a little longer than someone just remembering a username and a password. But I mean, honestly, People, I think, have gotten a lot more used to checking their email, clicking a link, and then using their phone, right, so.

[00:31:13] **Carol:** So I just signed up for a NomadList and that's how their authentication works. Really? So basically, yeah, I just did like the paid account there and I don't have a password and I was like waiting for it to give me my password so I could, you know, share my account, you know, with someone who I will be traveling with, I hope, so that we don't have to subscribe to two.

[00:31:32] **Carol:** So nobody told them we'd... You know, we're going to do that, but, um,

[00:31:35] **Adam:** uh, He's going to have to check with

[00:31:36] **Tim:** you every time he logs in for the, Hey, what's the, what's the code

[00:31:38] **Adam:** number?

[00:31:39] **Carol:** Yeah, that's the thing. So now it sends it to me. It's like, Hey, and to she, by the way, not a he, but you were close. Uh, so it's one of my best friends.

[00:31:48] **Carol:** Yeah, with me, it's either way, whatever. Um, so, uh, basically it was like, oh, I never can get a passport. It just keeps texting me every time I want to log in. And I was like. I started looking at the profile settings. It's like, Oh, they don't do passwords. And I started researching it and I was like, this is interesting.

[00:32:04] **Carol:** I've never thought about it this way.

[00:32:06] **Adam:** Yeah, I've seen some websites that work similarly, uh, in particular Egghead, which is like a video tutorial thing. Their login is very similar. And I know of at least one other similar, you know, courseware sort of thing that's actually built on top of Egghead technology.

[00:32:21] **Adam:** So it's not surprising that it also does the same thing. I wonder

[00:32:24] **Carol:** if it's for the same reason. I bet it is. We don't want to share accounts. So it makes

[00:32:28] **Adam:** it a little hard. I mean, our, our business

[00:32:30] **Tim:** reason for doing it. So the product is, is sending. money to, so you get a claims payment from an insurance company and they're going to send you money, right?

[00:32:39] **Tim:** And we don't want, and they could send you multiple payments. We don't want someone just getting a hold of your username and password and then redirecting that money away from you to someone else. So, you know, unless, unless they have your phone in hand and they have your, you know, they have your email access to your email, um, they're not going to be able to get the money.

[00:33:01] **Adam:** That's actually pretty cool. Okay, so then you're right, that wasn't at all like what I had in mind for using SSO or OAuth sort of thing. So I guess, so I guess I talked a bunch around password stuff. Somebody else want to talk about third party login OAuth and single sign on with other services?

[00:33:19] **Adam:** Shibboleth, if you know it. What?

[00:33:22] **Ben:** What was that last

[00:33:23] **Adam:** thing? Shibboleth. last word you said? You've never heard of it. No. Shibboleth. Is that,

[00:33:28] **Ben:** is that, I don't know if that's an exclamation or if that's a service. Like, I don't know if you're saying, like, kablamo or kabow.

[00:33:36] **Adam:** No. Shibboleth. No. It's S H I B B O L E T H.

[00:33:43] **Carol:** Shibboleth. If you start Googling it, the very first search in mind is shibboleth. Shibboleth versus OAuth.

[00:33:49] **Adam:** It's a,

[00:33:50] **Tim:** it's a, it's a biblical name too.

[00:33:52] **Adam:** Oh. Yeah, it's a, um, very, I guess let's enterprise y, uh, single sign on system.

[00:33:59] **Ben:** Now, is it a, is, is it a protocol? Because I think OAuth is more of a protocol, right?

[00:34:04] **Ben:** It's not a, it's not a service per se. Right. Like, like Auth0 or Octa.

[00:34:09] **Adam:** Right, no, I mean, it's, hmm, I don't know it all that well. Like, we've used it and I have avoided it because it's a pain in the rear end to get working and keep working. Um, I have the, the feeling that it is a, it's like a product and it has its own protocol sort of thing.

[00:34:29] **Adam:** It works very similarly to OAuth, but It is its own thing. It's a plug in for Apache and you can, or it doesn't, I think you can use it with like Nginx or something if you really wanted to, but there is a plug in for Apache and you can say, okay, anything inside this quote unquote directory, right, like a path in the URL that looks like a directory, um, needs to be secured and this is the realm for that.

[00:34:55] **Carol:** So, so OAuth and SAML are different, right? So OAuth is a protocol and SAML, is that how you say it right, is another? Correct,

[00:35:02] **Adam:** S A M L, SAML. And you know what, now that you mention it, I think that Shibboleth does use SAML. Yeah, it

[00:35:07] **Carol:** uses SAML, basically. And it uses OpenSAML to actually do their authentication versus OAuth.

[00:35:14] **Adam:** Right. I don't know

[00:35:16] **Tim:** what we use. I know at work, we, we create our own single sign on service, which I guess is okay. I mean, you could use, I mean, if you want to, you can just use Facebook's, you know, login or, or, or Google's. Yep. I'm always scared of that because you, you think, well, they're big companies and you know, they're, they're obviously safer than we are, but you know, I saw an article and I've, I've, I've posted it in our, our chat here that.

[00:35:41] **Tim:** You know, Google suite was storing passwords, uh, since, in plain text, since 2005.

[00:35:49] **Adam:** I saw you shared that link. Please tell me it's been corrected.

[00:35:52] **Tim:** Yeah, it has, it has been corrected, but I mean, yeah, so it's like, yeah, they, they did it. I mean, Twitter had a similar problem. Uh, Facebook had it in the past. So, I mean, it's like, you can't assume just because someone's a big company that they're going to be doing everything safely.

[00:36:07] **Tim:** Right. You're kind of shifting the burden to another company, but your users don't care if they, you know, there's a breach and they get hacked, you know, using their password. So we created our own, which means that, I mean, ours might not be that secure either, but I know we're, I know we're encrypted, hashing it and doing all that stuff.

[00:36:30] **Tim:** We're, we're a smaller target than Google. So if someone wants to get. Lots of people's info. They're going to go after a Google and a Facebook, not a smaller company like us. But then, and then when we're not using the single sign on, we do the, the no passwords, which, you know, I, I think is, is pretty secure.

[00:36:47] **Adam:** I would say it's pretty secure, but it's also an extra level of annoying, right? So. I don't have my password manager to make it a two second process to sign in. I have to like click the button, go check my email and get the text and enter the code. Yeah, yeah. There is a little more friction there. I do agree.

[00:37:04] **Adam:** It is a trade off.

[00:37:05] **Ben:** Yeah. Speaking of friction, I have found that one thing that has changed the way that I think about certain passwords. It's having to log into smart TVs or other computer devices. Cause when I'm on my computer, I'm using one password. I honestly don't even know what most of my passwords are because they're just random 64 characters of gibberish when I have to use a TV remote.

[00:37:30] **Ben:** Like up, up, down, down, over, over, up, up. I'm like, I'm not about to do that 64 times.

[00:37:38] **Adam:** I

[00:37:38] **Carol:** am. I actually spend way too much time trying to get my phone to connect to the device just so I can put in like something from one password, whereas if I would have just Sat there with the remote putting in the numbers, like in letters.

[00:37:52] **Carol:** I would've been done already, but instead, like I'm 20 minutes in, I'm still trying to like connect my phone to the device so that I don't have to deal with it

[00:37:59] **Adam:** ever again. Yeah. So for things that have a keyboard, I, I really like, there's a, a scheme for passwords called dice words, which is a list. You can look it up online.

[00:38:10] **Adam:** There's multiple of them, but you just Google dice words. And it's lists of words, and they have random, or not, not random, but sequential numbers next to them. And so what they, the concept is you take a number of dice, I think it's like six dice, and you roll them, and then you just grab them in a random order, and whatever the number is that, that adds, that adds, not that that adds up to, but that is, so right, so each one of those is like one through six, you're rolling these six dice.

[00:38:34] **Adam:** So if you end up with like 6, 3, 1, 3, 2, 4, whatever, you find the words 2, 4, whatever I said, and that's the first word of your password, and then you put a dash or space or whatever you want between them. And that gives you sufficiently random words because it's not something you chose, it's something that Dice chose, but it's also easy for you to type in and not so much memorable, but memorable long enough to be able to type it in, right?

[00:38:59] **Adam:** So like, what's the XKCD one? It's like correct horse tooth bucket or something. I think there's a staple in there. Oh yeah, yeah. Um. Anyway, uh, you know, a sequence of words you can remember long enough to type. You know, you look it up once, it sticks in your memory for the 30 seconds that it takes you to type it, and then it's gone.

[00:39:20] **Adam:** So I really like that system, and 1Password will generate them. Yeah,

[00:39:24] **Ben:** I first saw that, I had seen the XKCD comic a while back, I mean, a couple years ago, but then when we... Got our local router updated, like Verizon came and gave us a new router and the password, you know, it's on the bottom of the router, which is funny to me, but, um, they use that sort of scheme.

[00:39:41] **Ben:** It was like, uh, you know, train track 39 sunset 52. And it's pretty long. But it's really only like six things, which is, you know, just a years ago, not, not that many years ago, just a handful of years ago, the, what was considered best practices around security was having things like every password has to have, you know, at least one uppercase character and one lowercase character and one special character.

[00:40:10] **Ben:** The word NIST sticks out in my mind, but I can't remember what NIST stands for. I think it's some sort of National Institute of Security,

[00:40:16] **Adam:** science and technology. Yeah. Standards

[00:40:19] **Tim:** in technology? Let's Google that. We're gonna get, we're gonna get corrected

[00:40:22] **Adam:** on the internet.

[00:40:24] **Ben:** So I believe they have come out with a, uh, a newer recommendation that has nothing to do with random uppercase, lowercase characters.

[00:40:33] **Ben:** It's, it's all about. Uh, and just having enough characters to make something easy enough to remember if you're not using something like a phrase,

[00:40:42] **Adam:** yeah.

[00:40:42] **Carol:** The National Institute of Standards and Technology. Thank you,

[00:40:46] **Adam:** girl. Nailed it, Tim.

[00:40:48] **Carol:** You're good. Good, good, good. Yeah, so I will say the one thing that you'll hit, though, is if you're not careful is that if you have server side requirements, so like if you are, um, You know, putting in, this isn't really front facing, but say you're creating your passwords for like Oracle or for SQL and the server config is set to require a special character, well, then your users on there have to have a special character too, or they're not going to work.

[00:41:14] **Carol:** So then you do have to sometimes require those special characters in order for them to work. If that user has to be granted access to like tables for things when they're writing from your application.

[00:41:27] **Tim:** But that's only if, if you're creating SQL users using a password for the access. If you don't have that problem, then you can

[00:41:35] **Adam:** do whatever you want.

[00:41:37] **Adam:** All right. So let's get back to, to sort of, uh, where we wanted to go with discussing password security here. What are, what criteria would you use to username

[00:41:48] **Adam:** and password combination. I want to use something else, whether that's OAuth or Shibboleth or. Single sign on or something. Does that word make you laugh? It does. It's a very funny sounding word. Shib. Shib. That's what we call it at work. Shib. And so for me, uh, I guess where I draw that line is, A, if my user base already has, uh, accounts somewhere that, that offers single sign on using their account system, right?

[00:42:15] **Adam:** So like, for example, if you're, if you, well, if you are creating a service that integrates with GitHub, then you might as well you offer, at least, if not primarily use GitHub as your Sign in provider because your user users already have GitHub and GitHub offers OAuth authentication, right? So then your users don't need any extra accounts.

[00:42:38] **Adam:** They don't need an extra password, etc. They can just use their GitHub login to log into your service. And yes, you can get your, you can get an email address and some information about them through that OAuth integration so that you can email them when there's, you know, important news or whatever.

[00:42:55] **Carol:** Not gonna lie, I didn't fully understand what your question meant when you asked it.

[00:42:59] **Carol:** Okay. Now it's making more sense. I'm like, okay.

[00:43:03] **Ben:** Another possibility is when you're working in the JAMstack, which I think we touched on in an earlier episode, which is JavaScript APIs and markup, uh, but essentially boils down at least somewhat broadly, I built a JavaScript app and then I hosted somewhere like on a CDN, which I know it's evolving beyond that, but you might not have a quote unquote user database to even work with.

[00:43:30] **Ben:** Because you're building a front end that connects to APIs, so you need to offload that user management to another system. Very good point. Um, I, I think a lot of the Jamstacky type systems now also come with some sort of user management. I think Netlify has user management, Auth0. I'm pretty sure Firebase has their own sort of user

[00:43:49] **Adam:** management at this point.

[00:43:50] **Adam:** Oh, sure. Yeah. Okay. Well, then the last thing on my list that I wanted to talk about under passwords was like, what are red flags that websites are doing it wrong? Oh, when you get it wrong

[00:43:59] **Carol:** and then it clearly throws an error. Yeah. That shows you what the SQL look like going into it.

[00:44:05] **Adam:** Oh, yeah. That's a huge red flag about many things.

[00:44:08] **Adam:** That's bad. I guess what I really wanted to go toward though is like, Maybe by, if I give an example, it'll help. When I go to create an account for somebody and it says your password must be between 18 and 24 characters long. Oh, I hate that. That tells me that you are very likely not hashing that password.

[00:44:29] **Adam:** Because if you're hashing it, I could write a freaking book in there. It wouldn't matter. And it wouldn't matter. Not gonna care. If you require... For me to choose a special character from a list of like your 10 special characters that you've ordained is okay because maybe dollar sign and backslash means that special things to whatever, you know, however you're getting the data into the database.

[00:44:50] **Adam:** And so it would cause problems like SQL injection type stuff. That's a deal breaker. And

[00:44:58] **Carol:** so, like, on that, like, I had played with Wireshark for a while and whenever you're working with Wireshark and with, like, Kali Linux, basically you use Hydra and the Hydra process basically says, tell me what you know about the password.

[00:45:11] **Carol:** So it's like, I know that it's one of these four special characters and that it has to have a lowercase and it has to have one number that basically gives it the ability to say, okay, I know now what I can exclude out of every password. I want to try basically cracking it. So don't set that information because you just basically open up everything when you

[00:45:33] **Adam:** do.

[00:45:33] **Adam:** Yeah.

[00:45:34] **Tim:** Can I just talk about pet peeves though when it comes to websites? That, with passwords. So it annoys the heck out of me when they have a list of like special characters, but it's not all special characters. There's like five special characters that you're allowed to have. Other than that, they're going to stop you.

[00:45:51] **Tim:** And they don't make it, they make it a little bit clear, but it's not evident, right? So you type in, you're like, Oh, I need a special character. Probably. Or they don't even tell you the rules up front.

[00:46:01] **Adam:** Oh my God. So many. That just annoys me. So keep guessing. Yeah. Yeah.

[00:46:08] **Tim:** You need a number. Okay. I had a number.

[00:46:10] **Tim:** You need a special character. Okay. Add a special character. You need at least one uppercase. Okay. Add an uppercase. What drives me nuts is I'm trying to reset my password and then I reset it and they say, Oh, you can't use the same password

[00:46:25] **Adam:** you just used. How did they get it wrong in the first place? Yeah.

[00:46:31] **Adam:** Or, or my favorite is, uh, I created an account. I provide a password. It accepts that. And then I can't log in with the password that I just created. And what I learned, and what I specifically, I can't remember where I saw this, but what I specifically have seen happen is the requirements on the reset password form are more strict than the requirements on the new password form.

[00:46:56] **Adam:** And the impression that I get is like, it's shorter. on the reset password. So they like truncated my password when I created or something like that. And I'm just like, I just want to reach through the internet and throttle them, like force choke them. Well,

[00:47:11] **Ben:** so I've been burned on max length, uh, attributes on an input because typically, again, I'm using one password.

[00:47:18] **Ben:** So when I go to sign up for an account, my workflow is. Create the login in one password, generate 64 characters, copy it out of one password, paste it into the signup form, but it's just, you know, a string of dots or a string of ASCII characters. So if it got, if there's a max length of, let's say 30 characters on that field, I don't notice that.

[00:47:40] **Ben:** It's just a giant string of characters. And then when I go to sign in, maybe they don't have the max length or for whatever reason, maybe the max length is different. Yup. And now it's like the password that I pasted in happens to be different only because the original one was truncated unbeknownst to me.

[00:47:55] **Ben:** So

[00:47:55] **Carol:** you need to do Adam's like motion. He just did stick your hand through the

[00:47:59] **Adam:** screen and shake someone. Force choke. Yeah. I'm waiting for that

[00:48:04] **Carol:** protocol. Those are the worst. And I hate when, um, sites disable right clicking on,

[00:48:09] **Adam:** um, the field.

[00:48:12] **Carol:** And I just need to right click and paste in here. Do you not know? I just copied my password from something.

[00:48:18] **Carol:** So then I spend, again, with my wasting time. I spend the time re enabling the paste functionality so that I can actually paste

[00:48:26] **Adam:** it in. F12 developer tools.

[00:48:27] **Carol:** F12 fix that, huh? I'm like, I will paste this. You will not tell me

[00:48:31] **Adam:** I can't. It's so annoying.

[00:48:34] **Ben:** Along with the idea of having to have one number and one uppercase character and one lowercase character, along with that being an outdated idea of password security, I think they have also now outdated the idea of having to rotate your passwords every three months or six months.

[00:48:49] **Ben:** Um, because I think, again, just as with having to do random stuff, all that really does is increase the chances that you'll end up writing it down. Yep. Or,

[00:48:58] **Adam:** or creating it. Yeah. You're going to go from Adam 1 to Adam 2. Yeah. As I was iterate. Yeah. Yeah. Okay, so I had one other, like, insanely frustrating red flag that I was thinking of when I came up with this list, which was...

[00:49:12] **Adam:** When I do, like, forgot my password, and I get an email that has my password in it. Oh my god, means they're

[00:49:17] **Tim:** not hashing it. Yeah.

[00:49:19] **Adam:** They're not hashing it. You got it! Yeah. If you're, if

[00:49:24] **Tim:** you're storing that, that, the, uh, the password phrase, and they hack that, they have all, they, they're gonna get your

[00:49:31] **Adam:** password.

[00:49:33] **Adam:** Not to mention sending emails is not secure. So now you've just sent my password in plain text across the internet. Thanks. Thank you. Appreciate it. Yeah, it drives me nuts. I just put a link

[00:49:43] **Carol:** in the show notes to, um, an article I had read the other day at work and it was, um, the, basically the guidelines that, you know, Ben was talking about,

[00:49:54] **Adam:** which was some of the NIST guidelines.

[00:49:56] **Adam:** Yeah. Yeah, I mean, a long phrase

[00:49:58] **Tim:** that you can remember is much better than some thing that computers are good at, but humans aren't. It's a human, it's a human, passwords are a human problem, they're not a computer

[00:50:07] **Adam:** problem. The XKCD comic that we were referencing earlier is basically, the whole point of that is like we've spent years now training people to create passwords that are easy for computers to brute force and difficult for people to remember.

[00:50:22] **Adam:** Yes. The exact opposite of what we should have been doing. And the, so the, to be clear, the better practice is to encourage length, period. That's it. Like minimum 30 characters. If that's your, if that's your strength requirement for your, for your passwords, that is a good place to start. Have you ever

[00:50:41] **Ben:** put an emoji into a password?

[00:50:43] **Ben:** All the time.

[00:50:45] **Adam:** So I haven't done

[00:50:46] **Carol:** it, but when I was, when I was learning about, um, all the JWT tokens and was kind of going through that, I read a post about like how you actually handle emojis. And I was like, I didn't know it would actually work.

[00:50:59] **Adam:** That's pretty cool. Yeah. I haven't even thought about that.

[00:51:02] **Adam:** So every year for work, we try not not every year, but you know, often we try to come up with an April Fool's prank for our products. And one that's on my list to maybe do someday is to ask people like to post an announcement in the app, asking people to update their passwords. You know, it's been a long time.

[00:51:21] **Adam:** Maybe you should update your password and suggesting that they use, um, all emojis as their password for security,

[00:51:29] **Tim:** which works great on a mobile phone, but not so much on a keyboard. Does it

[00:51:33] **Adam:** on a Mac? It's easy. All right. Really? Yeah. Yeah. They're just on control. Command space will bring up an emoji selector.

[00:51:41] **Adam:** Why doesn't Windows have that? Because Windows sucks. Windows is Windows.

[00:51:44] **Carol:** Uh, come on. I just, they pop up on my little, what is the bar on top of my keyboard called that's like digital? The touch bar. Yeah, the touch bar. They just pop up on there sometimes. I'm like, oh, there's emojis.

[00:51:58] **Adam:** They're just saying

[00:51:59] **Ben:** hi.

[00:52:00] **Ben:** Yeah. I think Adam had put something in our chat the other day that was some sort of, um, like global. Yeah. Something you

[00:52:07] **Adam:** install. Called Rocket. I like it a lot. I paid for it. What's it called? It's called Rocket. It's a, it's basically an emoji selector. So you can, it watches everywhere that you're typing across the entire system.

[00:52:19] **Adam:** And you can tell it, okay, don't pay attention in this app and this app. That's right. Like Slack and Discord have their own emoji selectors that are fine. So don't pay attention in there, but everywhere else or wherever you specify, it can watch whatever you're typing. And then you have a trigger character, which for me is plus.

[00:52:32] **Adam:** So I type plus, and then I start typing the name of an emoji, smile or rocket or fire or whatever. And it shows me like a, as I'm typing, it's auto, uh, like type ahead, searching for the ones that match. And then I can just hit up and down to select from the list, hit enter, and it replaces the text that I was typing with that emoji.

[00:52:50] **Adam:** And you can set your, if you pay for the pro version, you can set your own aliases and you can set. Uh, whatever, like text expander type stuff to replace specific keywords with your favorite GIFs or whatever. That's pretty cool. Cool. So I think that should probably do it for passwords. We gotta, you know, we're coming up on time.

[00:53:06] **Adam:** We gotta go record the after show. So any final closing thoughts on passwords?

[00:53:11] **Ben:** I think, uh, one thought that I would have just as a closing thought is that a lot of times on podcasts, I will hear people talk about password management as this. Terrifying third rail and I would never want to build my own password system.

[00:53:26] **Ben:** I should always just outsource it to some identity provider like Auth0 or Okta or Shiblu.

[00:53:34] **Tim:** Shiblu. Shibli. Shibli.

[00:53:39] **Ben:** Shibli. But I think, you know, if all you're going to do is provide very basic logins. Email and password, username and password. And you use a hashing algorithm with sufficient work factor and salting.

[00:53:53] **Ben:** Like, that's pretty good. I don't think people should be afraid to have passwords stored in their system.

[00:54:00] **Adam:** Yeah. Just

[00:54:00] **Carol:** don't store them in plain text.

[00:54:02] **Adam:** Yeah. Just

[00:54:03] **Ben:** don't store them in plain text.

[00:54:04] **Carol:** And make sure you are not vulnerable to SQL injections. Just do both.

[00:54:08] **Ben:** Yeah. Also, one thing that completely changed my life is when someone taught me that one password can actually set up time based.

[00:54:16] **Ben:** One time tokens, so something you might usually use a, an authentication app for. Uh, you can just have that set up in one password. And, uh, the reason that that's been so revolutionary for me is I used to use, it was like Google Authenticator or something on my phone, but when you upgrade your phone and you, even if you restore from like a complete backup, it will not bring over your one time password configurations.

[00:54:44] **Ben:** Authi does that

[00:54:44] **Adam:** though. Yeah,

[00:54:45] **Carol:** Authi gives you a QR code, right? You gotta scan from your own device.

[00:54:49] **Adam:** So you sign into Authi and it saves your tokens in there. Um, and one of the really nice things with that is if you have, if you're the type of person, and I am, that has multiple devices, then you can look them up on multiple devices.

[00:55:00] **Adam:** If you go back to like Google Authenticator, you can only have that active on one device. Oh, interesting. If you were to like scan the QR code to set it up as a token generator on your phone, then on your tablet it like invalidates it. Also, it like, backs that up when, and so when you sign in to that account on your new device, or when you store, you know, new OS or whatever, then it, they're all still there.

[00:55:21] **Adam:** And Authy has a nice desktop app.

[00:55:25] **Carol:** So the problem with 1Password's MFA is that whenever I have it running on the, uh, like my Chrome extension, I'm pointing to the top of my screen so everyone listening can know what I'm doing. Whenever I have it running in my Chrome extension and I have it running on my phone, they don't stay in sync, right?

[00:55:45] **Carol:** So I go and type in the code from my... Chrome extension and it won't work. I have to open my phone and get the code from there. So I stopped using the one password, um, code generator because I couldn't keep them in sync. I was like, nevermind. This is too much of a headache. And I went back to Authy for

[00:56:02] **Adam:** everything.

[00:56:02] **Adam:** Is

[00:56:03] **Tim:** Authy from Twilio?

[00:56:08] **Tim:** I to Google it, how do you spell

[00:56:10] **Adam:** it? A U T H Y. com.

[00:56:13] **Carol:** I don't know, it's an app. Yeah, it's by Twilio. It just popped up. I got it very quickly on the,

[00:56:18] **Adam:** um, home screen. Yeah, we'll put it in the show notes. Oh, I have one more thing

[00:56:23] **Ben:** for the show notes. Um, oh, so there's a project called OWASP, which is the, I think it stands for open,

[00:56:29] **Adam:** wait, web application security project.

[00:56:32] **Adam:** OWASP top 10.

[00:56:34] **Ben:** They have a password cheat sheet and earlier in the show, Adam had mentioned the number of iterations and the salt that you can have. They have in their cheat sheet, essentially current recommendations for the work factor that goes into the various algorithms. So if you're wondering how many iterations should I have in bcrypt, they have a recommendation for what you should use with today's hardware.

[00:56:58] **Ben:** Um, as, as they do for other hashing algorithms, like

[00:57:02] **Tim:** Aragon, Argon,

[00:57:05] **Ben:** 2ID, and script. And then there's one that's just like a bunch of letters.

[00:57:11] **Tim:** B B K, DF two, something like that. ,

[00:57:16] **Adam:** welcome to the Random Characters podcast, , right?

[00:57:18] **Tim:** I, I, I love, I love how these, uh, encryption guys have to name everything. Like really

[00:57:22] **Adam:** cryptically.

[00:57:24] **Adam:** Okay, moving on. So listen with that note, I have something important I wanna tell you. This podcast is made possible by listeners like you. I'm gonna keep this pitch short and sweet this week. You're smart people. You know how this works. We could really use your support. And so if that's something that you're interested in, you can find us at patreon.com/WorkingCodePod. We do have a new patron this week. So David, welcome to the team. Happy to have you. Uh, we have a top tier on Patreon and we have two top patrons right now. So a special thank you goes out to Peter. And to Monte, to everyone out there that just listens but isn't a patron, thank you for listening.

[00:58:00] **Adam:** It would help us out if you told your friends and co workers to listen to the show. You can tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts. We love getting your feedback and questions and you can send those to us on Twitter or Instagram at @WorkingCodePod.

[00:58:15] **Adam:** Or you can leave us a message at 512-253-2633, that's 512-253-CODE. We'll catch you next week. And until then, your heart really matters.

[00:58:37] **Carol:** So there apparently is a soccer, um, podcast. I need to get the link again from my coworker. She did their intro and outro. Yeah, he was like, where did you hire your person from? Cause I swear she did like the same one for this other podcast.

[00:58:58] **Carol:** I was like, Ooh, listen. I was like, she did, huh?

[00:59:01] **Adam:** I was like, hi there. I like her voice. Yeah, she did a good job.
