---
title: "176: Triumph and Fail Safe Space"
description: "On today's show, we cover a variety of topics. Tim had to build an internal CAPTCHA system in order to protect his web-based payment forms. Adam created an open-source JavaScript library for mocking ES modules. And Ben falls back in love with ColdFusion."
date: 2024-05-01
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/176-triumph-and-fail-safe-space/id1544142288?i=1000654156199"></iframe>

On today's show, we cover a variety of topics. Tim was suffering from a "carding" attack (aka, a "credit card stuffing" attack) and had to build an internal CAPTCHA system in order to protect his web-based payment forms from bad actors. Adam created an open-source JavaScript library for mocking ES modules (see [Mockable][mockable]) that makes it possible to swap implementation details at runtime. And Ben falls back in love with ColdFusion&mdash;again&mdash;continuing to find that even the small language details bring him great joy.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[mockable]: https://github.com/atuttle/mockable
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/176-triumph-and-fail-safe-space.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** But it used to be that I could actually remote into our, our servers.

[00:00:03] **Ben:** you would remote in and there was a little pop up window that said, you shouldn't be here. Your IP address has been logged and reported.

[00:00:09] **Adam:** it's just a notepad doc.

[00:00:11] **Ben:** And I, and I reached out to support. I'm like, yo, I don't know what's going on. I don't know if this is a problem, but the server's telling me I'm not supposed to be there.

[00:00:17] **Ben:** And they're like, oh no, we just always put that in to freak people out. Uh, that's, you can just totally ignore that.

## [00:00:44] Intro

[00:00:44] **Adam:** Okay, here we go, it is show number 176. and as usual, we're gonna start with our triumphs and fails. We don't have Carol with us tonight. She had a deadline coming up that she's trying to work toward and being a West Coast ish person, she's still at work while the rest of us are playing and recording a podcast, so. Uh, Carol has an excused absence, so, Tim, she would normally get to go first, so, Tim, why don't you get to go first instead?

## [00:01:07] Tim's Triumph - CAPTCHA

[00:01:07] **Tim:** Yeah, I get to go first. All right. So, I'm starting with a fail that parlayed into a later triumph.

[00:01:16] **Ben:** All right.

[00:01:17] **Tim:** So, so the fail was, last week I got contacted that, our, our, one of our back end pro

[00:01:24] **Adam:** you didn't.

[00:01:25] **Tim:** Yeah, Tom, Tom Cruise got the part. Yeah. Yeah, for Saturday Night Live, movie that's filming. Oh, they're also filming the new James Gunn's Superman movie here in, actually in Macon, Georgia, not too far from where I live.

[00:01:37] **Tim:** But anyway, that's, sorry, digress. I got a, I got a call saying that, there was Some bad actors on one of our page, hosted pages that were doing card testing and what they were doing is we had a

[00:01:51] **Adam:** Five?

[00:01:51] **Tim:** corrupt Senator number four, probably my longtime rival. He, uh, another bad actor. Wow. You just, you just determined to throw me off the rails today, aren't you?

[00:02:00] **Adam:** trying. Are you,

[00:02:04] **Tim:** so someone, someone was hitting one of our pages that wasn't a secured page. It was just kind of a page that was out there that had our. are embedded, credit card form and they were just putting numbers in. I guess they had like the algorithm. So the algorithm that, that you, that card numbers are generated is called the LUHN, L U H N algorithm.

[00:02:23] **Tim:** And so they were generating LUHN compatible cards and then putting in Information to try to see if they could get it. So they were like every second just hitting the page and over and over again. And some, most of them were getting declined because they were bad cards, but a few of them, they turned out to be good numbers, all for a dollar, all for the same person's name, everything.

[00:02:43] **Tim:** So we quickly kind of shut that page off, but put a, a basic auth page in front of it so that they couldn't keep hitting it. and then. It was recommended that maybe we just put a Captcha page in there. So I started working out, actually, I asked you on the code help section, our discord Ben, but you never responded.

[00:03:04] **Ben:** funny. So I'm terrible at discord. It, it, to me, it looks like a really funny version of Slack and I have trouble finding stuff and then I'll see notifications come in, in, in my phone or my desktop window, and then I have trouble finding them if I don't click on them fast enough. I don't know.

[00:03:21] **Ben:** So I apologize. I saw it come in and then I kept checking the channels to try and find it. And I couldn't find it.

[00:03:27] **Tim:** well, what happened was I found your blog article about using Google Recaptcha, right? So I was using Google Recaptcha. And I took your code examples and I couldn't figure out, you're like, you know, you need to validate this. And I was like, I don't know what this is. And you know, you validate this on the server.

[00:03:44] **Tim:** But anyway, I found a Stack Overflow answer that did it all in sort of one page rather than you were being a lot more educational than I wanted. I just wanted a quick copy and paste solution. So I copied and pasted that and I figured, oh, okay, I see what you got to do here. And I got that working, locally.

[00:04:00] **Tim:** And then I contacted our, when we, when we try to, I couldn't do it on production because we had to open our firewall out. So our payment environment, everything has to be whitelisted to go out. So everything's denied by default. If you put it on the whitelist, you can go out. So unfortunately it was google.

[00:04:18] **Tim:** com and our sec. Security operation officers basically said, yeah, that's way too big of an IP range to open up to. That's just, you know, you might as well just have it wide open if you're going to open it up to the huge number of IPs that Google. com covers. So had to pivot and instead we set up our own Our own CAPTCHA service locally, or not locally, yeah, internally.

[00:04:43] **Tim:** So we have, we build our own internal CAPTCHA service. It's not as cool as reCAPTCHA, because reCAPTCHA doesn't even like, you don't even enter anything.

[00:04:51] **Ben:** Yeah.

[00:04:51] **Tim:** It just, it just monitors how you interact with the form, and it figures out, gives you a human score. mine is sort of the ugly letters and a bunch of squiggly lines and, You got to figure that out, but, that worked and was able to get that Friday.

[00:05:06] **Tim:** We found out about it. And then I think Tuesday we stood up the CAPTCHA service. And then Tuesday afternoon we had it working in production so that they could get back to taking payments. So it was a fail because, you know, we really should have had that locked down in the first place, but this a triumph because we're able to get it, get it resolved rather quickly.

[00:05:26] **Adam:** it, is it working well, this home rolled capture for you? I

[00:05:29] **Tim:** Seems to be so far.

[00:05:31] **Ben:** So we

[00:05:31] **Tim:** It's, it stopped the bad actors that are, they're not able to.

[00:05:35] **Adam:** in my experience, it's only a matter of time until they come back.

[00:05:38] **Tim:** For sure. We'll see. We'll see if they can figure out a way to get around the captcha.

[00:05:44] **Ben:** don't know. I don't know if I talked about this on the show previously, but we had a, we had a huge spam problem with our checkout form or our payment form. And it was the, so I don't, I don't know how all payment forms work, but this one, because we had to collect some sort of a local tax, I suppose, in certain areas.

[00:06:02] **Ben:** That before we actually even tried to charge the credit card, we have to make another API call to a different service that says the user lives in this area. Do we have to collect tax for them? And that's a paid service on our end. And so these people were trying thousands and thousands of credit cards and we were never actually charging the cards, but the service that was checking to see if that person required a tax that was charging us.

[00:06:27] **Ben:** And our finance person reached out and they were like, Hey, I don't know if you guys are doing anything weird, but, it's the third of the month and you've already consumed all of your payment operations for the entire month. I just want to make sure everything's okay. They had eaten through like 7, 000 worth of, of, tax checks and yeah.

[00:06:46] **Ben:** And so we, we ended up having to put a caption in place as well. And that, thankfully, you know, fingers crossed seems to have stopped the issue for now. Yeah.

[00:06:56] **Adam:** don't know how accurate this is, but what we refer to these types of things internally as is carding attacks. You know, it's a term I've heard before. I'm not 100 percent sure that we're using it correctly on our team. but you know, so the impression that we get is somebody is either generating like you're talking about, Tim, or just, you know, maybe purchased a list of credit card numbers and names or whatever.

[00:07:22] **Adam:** I'm not 100 percent sure. and they're just trying to find the ones that still work. So they're like putting through charges that are a dollar or five dollars or whatever the minimum is for that form. and until they find one that works, then they go off and they use that card to, to do the purchases that they actually want to do.

[00:07:37] **Adam:** Probably buying Bitcoin or whatever the and, man, I didn't expect myself to get quacked so early in the show. anyway, so yeah, I mean, we've been dealing with this off and on for years and the first thing that we did was put in, a module it's for brute force, like detection and prevention.

[00:07:56] **Adam:** So like, I think it was originally devised, for like preventing somebody from trying to, guess passwords, like rapid fire. And so it, it was, Like a, what do you call it? Middleware for Express. And it would detect the same person submitting multiple requests, you know, rapid fire and put in like an exponential back off for them.

[00:08:17] **Adam:** And that seemed to help, but then, like, eventually, somehow, somebody found a way around that, and also, it, yeah, as all, as these things always do, it ended up biting us in the butt with, like, legitimate uses too, right, you know, like, then somebody from the, our customer, they're like, oh, yeah, you know, yes, the giving form is supposed to be public facing, but for these particular situations where we're, like, are getting, you know, GIFs over the phone, we just have somebody like save up 10 of them and then they go and they charge all 10 at once.

[00:08:48] **Adam:** And so this, that, that one person is getting, not all at once, but you know what I mean? Like rapid fire with a, with a human at the keyboard. And so that person is getting caught and it's, it's like, you can't win, right? Everything that you do to try and get in the way hurts the good people and the bad people fighting the way around it.

[00:09:06] **Adam:** same thing with a captcha. Like we, we put a captcha on it. And I don't know how, but we have clear evidence that they're getting past it. and to the point now where we're like, we. I forget what the last thing we did was like, okay. I remember what I don't want to, I don't want to say because, you know, if we share that information, then somebody might help somebody get past it.

[00:09:25] **Adam:** But like, you know, we're being more intelligent about detecting, bad, bad gifts coming through and, and blocking them and putting them into sort of a weird pending state. It's, it sucks, man. It's, it's like a,

[00:09:37] **Tim:** arms

[00:09:38] **Adam:** a mole. Yeah.

[00:09:40] **Ben:** it's definitely an arms race. And well, and the tough part is, is you want to try to do the least amount of effort possible, really. Cause you've got so many other things, rate limiting on your checkout form is not what your product is differentiated by, right? So you don't want to, to splurge on, on the effort there, but it seems that the generic solutions inevitably hurt somebody and allow other people through accidentally.

[00:10:05] **Ben:** And then you have to start to pick apart user differences. You're like, well, you know, maybe like, when's the last time this made, this person made an alumni donation. And if we, if they had a successful and then, you know, more than three months ago, then we can say, Oh, that's, that's, that's a good user. We can probably let them through.

[00:10:22] **Ben:** I I'm, I don't know the rules of your system. I'm just, I'm just shooting from the hip here, but it's like, at some point, it's no longer a. One size fits all. You really got to start to think about how it integrates with your particular type of application, which is a huge pain.

[00:10:37] **Adam:** Yeah, for sure.

## [00:10:39] Where Should Things Live

[00:10:39] **Ben:** I always think about if I can go on a tangent for two seconds. And if we think about the, the clean code book with Robert Martin, and I think he talked about in this, talked about this in that book, that if you think about the application architecture, you have your application core, which is kind of where your business y rules live.

[00:10:58] **Ben:** And then you have your web delivery mechanism, which is the kind of a routing and controlling the routing and controller part of the web page. And I, and I think the idea is you could have a, like a clicky type web delivery mechanism that you can have an API type web delivery mechanism or a queuing mechanism, and they all can still eat out of this application core.

[00:11:22] **Ben:** And, I, I go back and forth on where I want rate limiting to be. You know, you talked about middleware and I think middleware is kind of considered the, the web delivery mechanism. Like it's not the application core, it's kind of the stuff around the core, but then that makes sense when it's a very generic thing, like users from this IP address can only make X number of requests per minute and, and, you know, or if a user is logged in, they can make.

[00:11:45] **Ben:** And request per minute. But then when you have to start getting specific, like anyone making requests to the, Harvard alumni donation page, we're going to have a different rate limiting for them. And anyone who's making a request for, Princeton, you know, we have different rate limiting. Like that's, that, I feel like you're starting to get into that application core, like that's not really a routing and controller layer decision anymore.

[00:12:08] **Ben:** And I never feel good about having rate limiting in two different places. Well, two different layers. So I tend to err on the side of putting it almost all inside the application core and just eating the fact that basically everything's getting called from the web anyway, so I can squint my eyes and it doesn't really matter where it is, but it's, it's one of those things I've never felt good about.

[00:12:30] **Adam:** I mean, I think you're right that like, it just doesn't feel good. And, and. The way I look at that sort of scenario is the rules are there to help you when you don't know what else to do. But if you, if you feel like this is the best solution available to me and it still has like this nasty smell to it, that's okay, right?

[00:12:52] **Adam:** Like it's okay to break the rules as long as you know, you're breaking the rules and you're doing it intentionally. And it's because there's not a better option available.

[00:13:00] **Ben:** Yeah. Yeah. And then sometimes one of my litmus tests for, for the kind of where does the, where does the garbage live kind of a test What happens if I have an internal customer support personnel who has to do this thing? And, you know, if you have a, let's say you have a method somewhere that exposes an operation, let's say, um, I'm having trouble coming up with a good example for, for AlumniQ, like with, let's just say, submit a refund request. And maybe the user can do that. And if the user is going to do it, they have to be rate limited because there could be a vulnerability there. But if the customer support person is doing it through an admin panel, like you don't want to rate limit them because they're internal and they've already gone through a trusted login mechanism.

[00:13:48] **Ben:** So if I then have to turn around and say, well, The user and the customer support are both calling the same thing to do this thing. And I don't want the rate limiting one place, but I do want it in the other. Like either I have to move the rate limiting so that it doesn't feel garbage that the customer support person has to deal with it, or they should actually just be calling two different things.

[00:14:10] **Ben:** And then internally, maybe there's some shared logic.

[00:14:14] **Adam:** I think I could find a way to do it with composition, but I get you, I get your point, you know,

[00:14:18] **Ben:** just saying in terms of like the, the, the, how you like the rules that you can use to help make the decisions when you're not exactly sure. That's one of my tests is. In the back of my mind, what if an admin needed to do this? Or, you know, what if customer support needed to do this

[00:14:33] **Adam:** Yeah. No, I mean, that's,

[00:14:34] **Ben:** figure out where to put stuff,

[00:14:36] **Adam:** yeah. And I mean, you, you've kind of hit the nail on the head there. So like, you know, there's a lot of stuff that. You know, rules that we enforce in our public facing application stuff that are just not at all enforced in customer service. It's like, you know, if you have, if you have the keys to play in the customer service sandbox, then all bets are off.

[00:14:55] **Adam:** Now everything is audited and logged and you know, your name is attached to it. And to the point where. In a lot of places, you know, it's like a little, you're trying to do something, you're doing a refund and it pops up and it's like, okay, well, you know, which transaction are you refunding? How much do you want to refund?

[00:15:11] **Adam:** And then it shows a little thing under there and it's like refund authorized by, it just shows your name. It's not a dropdown. It's not a text input or anything. It just says, Ben is authorizing this refund to kind of drive home that point that we know you're doing it and we are logging the fact that you are doing it.

[00:15:26] **Adam:** And, and, you know, all the other details there, whatever, but

[00:15:30] **Tim:** Cause Ben is a bad actor.

[00:15:33] **Adam:** it was corrupt Senator, number one.

[00:15:35] **Tim:** Yep. He was.

[00:15:36] **Ben:** That's like, I think I used to have, we used to have hosting in a VPS where we could still log in, like now I don't have any access to any of our servers. Cause they're all driven by Kubernetes and, and I don't have permission for that kind of

[00:15:48] **Adam:** That's the way it should be,

[00:15:49] **Ben:** Yeah. Yeah. Yeah. But it used to be that I could actually remote into our, our servers.

[00:15:53] **Ben:** And when we did, there was a pop up window that said, you would remote in and there was a little pop up window that said, you shouldn't be here. Your IP address has been logged and reported.

[00:16:03] **Adam:** it's just a notepad doc.

[00:16:05] **Ben:** And I, and I reached out to support. I'm like, yo, I don't know what's going on. I don't know if this is a problem, but the server's telling me I'm not supposed to be there.

[00:16:11] **Ben:** And they're like, oh no, we just always put that in to freak people out. Uh, that's, you can just totally ignore that.

[00:16:18] **Adam:** That reminds me, like talking about those good old days when you would just remote into stuff, like the production server, you just changed the background wallpaper to be like a, a solid red color. And then, you know, like QA servers would be blue or something.

[00:16:30] **Ben:** You know, that's cool. I like that idea.

[00:16:32] **Tim:** So that way everyone knows you're in, you're in production, red screen.

[00:16:37] **Ben:** As an aside, I know that we've talked about this on previous shows. I'm pretty sure, but it would be fun to talk more in depth about audit logs and how you do that kind of stuff, because that's, I've dabbled, but I've never had a good solution as an aside. It'd be fun to talk about that

[00:16:51] **Adam:** I'll let, I'll put it on the

[00:16:52] **Ben:** Yeah. Put

[00:16:53] **Tim:** So anyway, that that's me. My fail parlayed into a somewhat of a triumph, although it sounds to me like you're saying it's only a triumph for a little while, so we'll see what happens.

[00:17:04] **Adam:** Hey, I mean, I wish you the best of luck, my friend.

[00:17:07] **Ben:** Yep. So that's me. And, how about you, Adam? What you got?

[00:17:10]

## [00:17:10] Adam's Triumph - Mocking ESM

[00:17:10] **Adam:** Well, I'm going to go with a double secret triumph, this week.

[00:17:14] **Tim:** Double secret.

[00:17:15] **Adam:** the first one is, I wrote a new JavaScript library. So I'm living up to the, the show intro there. and it, the, the JavaScript library kind of is a, is. Piggybacking on, my other triumph, which is that I figured out how to make mocking, ES modules for testing purposes not suck.

[00:17:35] **Adam:** so, ES modules, if you're not familiar, that's the like import and export instead of like module. exports and using require. So the, the latter, module. exports and require, that's called CommonJS or CJS. And if you're using import and export. in your JavaScript, and that's called ESModules or ESM. And, one of the benefits of ESM is that it can be statically analyzed and I believe it is, like, statically loaded, when you start your application.

[00:18:02] **Adam:** but the downside of that is that you can't then do runtime replacement of that stuff, right? Which is kind of how mocking works, right? You're just monkey patching over the original implementation. For the purposes of running the tests with some mock implementation, and then hopefully you restore it when you're when you're done testing or you just kill the process, whatever, but, so it can be kind of weird and awkward to try and mock ES module stuff to the point where, I was never able to get it work with any of the like, Solutions that I had found online with one exception, and I turned that exception into my new JavaScript module. So, basically, I found a couple of libraries. One's called ESMock, the other's called Mockingbird, and they try to I don't know exactly what they do. They, they're supposedly Making it work. I, one of them looked way too complex. It was like using decorators and stuff in the examples. And I'm just like, that is not the way I write JavaScript.

[00:18:55] **Adam:** It's just, it's only going to make things worse. And the other one seemed like simple enough, but the docs were just not. clear enough, not, not thorough enough for me. I, I am the first to admit I am no genius. Uh, so, you know, it's, it was a little difficult and I was, you know, I spent half a day going, okay, is this the product or is this me?

[00:19:18] **Adam:** Like, which one of us is dumb here? And I don't know, I still don't know which, which one of us was dumb, but I decided to abandon that effort. And I kept on my searching and I found a blog post with somebody, just like wrote out this, like, you know, it doesn't have to be this hard. Like, all you have to do is set your code up to be mockable, when you're creating the code, or you can create like a mockable proxy.

[00:19:42] **Adam:** So basically you just like wrap a function, you know, you've got a function that you want to mock, right? And so you just wrap it in another function that, that has some properties on it, like a override and clear, so that'll allow you to change the implementation, right? You call mock, or in my case, it's mockable, and you pass it the original implementation function.

[00:19:59] **Adam:** And if you do nothing else, then it just returns the, the original implementation, but then like during your testing, you can say, give me the function, right? My get database function.

[00:20:12] **Ben:** Sorry, just just to make it concrete, because I'm losing you a little bit here, let's, let's as an example say that you have a module that is a Stripe, API client.

[00:20:21] **Adam:** Can we, let me use the thing that I

[00:20:24] **Ben:** Okay. Yeah, yeah. Sure, sure, sure. You know, I didn't wanna step on any,

[00:20:26] **Adam:** yeah, no, no, that's fine, and that way it'll be more concrete in my brain too. So, the very first one that I wanted to mock was our database access module, right, so we, I've talked before about, we have this TSDB. module for my team. It's like, you just, you get an instance of it or it's a, it's a function that you call, right?

[00:20:43] **Adam:** And you say, okay, I want to do this connection for this customer, this environment, and I want it to be read or write connection,

[00:20:49] **Ben:** But sorry, just to be painfully clear, at the top of your JavaScript file, you're doing import TSDB from, you know,

[00:20:59] **Adam:** add alumni queue slash TSDB, yes, exactly. And that alumni queue, that's a, that's a private organization on our GitHub repository. yeah. And so, what I did was, you know, I wrote this new JavaScript module. You can look it up on NPM. It's at @atcodes/mockable. and we'll put it in the show notes.

[00:21:17] **Adam:** And, basically you can use it two ways. You can, as the module author, you can provide a module that is ready to be mocked, which is what I did. So I just made some changes to my, TSDB module and then basically import it, import mockable from at @atcodes/mockable, right? Import that function.

[00:21:38] **Adam:** And then where I previously had like export async function, get DB. Now I am, I'm just wrapping that basically. I've got like, uh, async function, getDB underscore, because it got to have a different name. And then I've got to export const, getDB equals mockable, getDB underscore.

[00:21:57] **Ben:** gotcha. So you are, When, when you're testing, when you're the test version of your application is bootstrapping, you essentially have to have some code that calls that first

[00:22:08] **Adam:** Not necessarily. No, no, so the, the, I'm going to, I'm going to send you the link so that you can look at it while we talk about it. But, So I just sent you the link. and you can kind of see, right, so in the first code block, you know, your import mockable from @atcodes/mockable, and then, it's exporting a variable called getDBConnection, which is also being set to mockable and passing it the original getDBConnection function. And then if we, if you look at the code, so if you like open up index.

[00:22:40] **Adam:** ts, you can see like the, like the first three lines of the mockable function are if process. env. nodeenv equals production, then return the original implementation. Like, so if you're in production, this is just a function that returns the original function.

[00:22:55] **Ben:** Gotcha.

[00:22:55] **Adam:** So mockable does nothing in production. It just like skips.

[00:22:58] **Adam:** And then if you're not in production, then it returns a wrapper for your function that has some properties on it that you can say, okay, if you do nothing, then you still get the original implementation, but if you call override on it, then you can like update the implementation, you can pass it a mock implementation. and that way you can, at runtime, overwrite the implementation of a dependency, right? And so just by wrapping my code in that, you know, export some variable equals mockable original function, right? then it makes that function overwritable at runtime, which you can then do in your tests, which is pretty neat.

[00:23:42] **Tim:** Yeah, that is pretty cool.

[00:23:44] **Adam:** The one problem that I found so far is like, it only works for functions the way I have it written. And this is all based on a blog post that I found. Right. So the guy basically gave me the code. I just took his stuff, made it TypeScript instead of JavaScript. I fixed a const that should have been a let, you know, from his, from his code in his blog, but, that sort of thing and changed some variable names and stuff.

[00:24:02] **Adam:** But, and it's working great for me so far. You know, I've got a bunch of tests written with it. The, the one problem is it's only, it only works as written for functions. I have some ideas to like make it work for maybe something that exports a, a, what you call it? like an object. I don't know. I, you know, when I get there, if I ever need that, then I'll worry about it.

[00:24:20] **Adam:** But in the meantime, not too worried about it. And then,

[00:24:23] **Tim:** So could you use this to, to, to mock like remote calls to something? If that, if that remote calls inside a function?

[00:24:30] **Adam:** yes, yeah, if it's inside of a function, you can. So like, for example, one of the things that we're using it for is tsdb. The other one is like ts redis. Right. So I'm making that mockable. you could use it for, you know, anything like if you have a function that's going to use fetch, you could, you know, override that function, and have it not call fetch.

[00:24:48] **Tim:** Now, typically what I would do in that situation is use MSW mock service worker, which like stands up a in memory server that intercepts the, the fetch call, and then allows you to like return an HTTP response. So you're getting a little bit more of an end to end test. You're just kind of. Putting up this like wall, simulation at the network layer. It's very neat. It sounds very smart.

[00:25:13] **Adam:** I can't take 100 percent credit, but when I read that blog post, I was like, Oh, duh. Why hasn't anybody else thought of this? and so there was that, and then like I do have another example in the readme is like, you know, so that's great if you're trying to mock something that you have control over, because, you know, I'm just taking my module and I'm saying, instead of exporting function A, I'm exporting a wrapped, you know, you're wrapping that exported A in mockable.

[00:25:38] **Adam:** Right? that's great if you have control of that code, but it doesn't help you if you want to mock, you know, some third party library that you can't control. and so, I thought about it and I was like, all you have to do really is like, import and re export as mockable, right? You just make a proxy for that third party module in your own code.

[00:25:56] **Adam:** And wrap the, the, the function in mockable before you re export it. So, so far this is working really well for us. It's like, you know, mental overhead, basically zero. Functional overhead in production, basically zero. So I'm super happy with it.

[00:26:14] **Ben:** Very cool. the whole, so part of what is the challenge here is the fact that there is no built in mechanism or really even any clear thing for inversion of control and dependency. Injection, you know, in, in, super mature languages like ColdFusion, right?

[00:26:33] **Adam:** You best.

[00:26:35] **Ben:** No, but you know, because we have

[00:26:38] **Adam:** mature like ColdFusion.

[00:26:39] **Ben:** yeah, yeah. So, you know, we could have the property tag,

[00:26:42] **Adam:** because you're old doesn't make you mature.

[00:26:45] **Tim:** Hey.

[00:26:46] **Ben:** here's the thing that I don't quite understand. and I'm painting with a super broad brush here, so I'm sure I'm going to offend people and, and, and, in certain ways. but I'm, I'm always surprised at how many people in the JavaScript world, especially on the server side, JavaScript world, don't seem to even be bothered by the fact that there's no inversion of control.

[00:27:09] **Ben:** Like if you say, you know, if someone imports, a module, like I'm going to import my DB connections. And they don't have any control over how that gets instantiated. So they have to kind of put all the instantiation logic inside of that DBConnections class in order for it to be instantiated properly.

[00:27:26] **Ben:** It doesn't bother them and I don't know how it doesn't bother them. And you could say to me, like we don't actually need dependency injection because you don't do a lot of testing. And that's really where dependency injection shines, case in point, everything you're talking about with, with being able to mock stuff for your tests. but I don't know, I just, it seems really strange to me. That the JavaScript world, generally speaking, doesn't seem to be bothered by the fact that this is like a huge functional gap in how you wire applications together.

[00:27:58] **Adam:** I totally see what you're talking about. And I mean, I, I know we've talked about this on the show before a little bit, but

[00:28:04] **Ben:** I've even seen people come from other languages that have dependency injection and then go into JavaScript. And I swear, like they spent six months in JavaScript and they just sort of convinced themselves that dependency injection actually really wasn't a big deal. And I feel like it's like, you're just learning to not care anymore.

[00:28:23] **Ben:** I don't know. It's very bizarre to me.

[00:28:25] **Adam:** well, I don't know. I, I think that it's all, it's like a little column, a little column B, right? So, On one hand, Node does a really good job of, it doesn't matter what file you're in, it doesn't matter, you know, what version of the runtime you're on or anything like that, require just works the way it works, right?

[00:28:43] **Adam:** So you've got a node modules folder, and if you require something, it will pull it out of there, unless you give it like a relative path, right? Whatever will, will go off the current path. And, and I've seen a lot of code where people do require, you know, dot slash, four folders, or they'll do require dot dot dot, dot dot slash, dot dot slash, dot dot slash, dot dot slash, common, slash, you know, whatever.

[00:29:07] **Adam:** And that's super annoying to me. and, and so that's a real problem. And in that case, I 100 percent agree with you. Like, that seems like a problem that dependency injection would solve. And then I play with something like SvelteKit, where, you know, I think that enough people got burned by that or, or annoyed by it or realized that it was an important enough problem that like, they found ways to do, I don't know exactly what they call them, like loaders or aliases or something where like you do, You know, require lib slash whatever, right?

[00:29:41] **Adam:** And then you've got some config file that says, okay, well, lib is this folder, right?

[00:29:46] **Ben:** Well,

[00:29:47] **Adam:** And so it kind of gives you like a second node modules, but it's only stuff that you're writing in your app.

[00:29:51] **Ben:** so going back to the idea of testing, I've seen people in the node world do that thing for testing, where instead of. Instead of changing the way, TSDB, I don't remember what it's called off the top of my head. Instead of changing the way TSDB is actually authored, they will instead like hijack the TSDB module resolution in their like webpack config file.

[00:30:20] **Ben:** And that when you're running tests, it'll actually load a different module that might then turn around and, and, you know, pull the TSD DB thing in internally. so I've seen that kind of approach, but I don't know. I never, the idea of messing with the file path always, it's one of those things that like, just didn't sit right with me,

[00:30:38] **Adam:** I, yeah, I agree. I mean, you're kind of getting at some stuff that I didn't talk about before that, like, It's very similar,

[00:30:45] **Ben:** get it off your chest, dude.

[00:30:48] **Tim:** It's a safe space.

[00:30:49] **Ben:** It's just us

[00:30:51] **Adam:** so part of the motivation for me, like wanting to go down this path is like, we've been telling, we've been told for years that ESM is the future of JavaScript, right? So like, if you want your code to be, to live longer, you should be writing ESM instead of common JS. Okay. That, I believe that to some extent, just as like an out of hand comment.

[00:31:12] **Adam:** but then. Things like, so Jest is probably, as far as I'm aware of, one of the most popular testing frameworks that's available, right? You've got Jest, and then there's some more modern, I mean, I guess there's like Mocha and Jasmine, some older stuff, but then, and then you've got more modern stuff like VTest, and I don't want to get into all of them, I could probably list a few more, but, That's not what we're here to

[00:31:33] **Ben:** testing libraries.

[00:31:34] **Adam:** Yeah. But, it feels like none of them and my, my experience is mostly with Jest. So I'll just talk about Jest. Jest does not play nice with ES modules out of the box. And it's probably a lot to do with the exact same thing that I was talking about, like that makes ES module mocking hard in the first place, right?

[00:31:53] **Adam:** You kind of have to have this like special loader thing, whatever. they have figured it out. There is a way to do ES module, like to, to write tests for your ES module code using Jest, but you have to use like a loader, right? You either have to use this like Babel based plugin or like ES build based plugin for Jest that compiles your code or translates your code into CJS so that your Jest test can then run on it.

[00:32:20] **Adam:** And that's just never sat right with me. You're like, But that's, it was fine for me when, you know, I was writing ESM and using Babel to translate that to CJS that would then run on the client or in Node, right? Because it's only a relatively recent, development that Node itself can run ESM, right? For a long time, we were writing ESM and you had to compile it to CJS so that Node could run it.

[00:32:46] **Adam:** Um,and so when you were,

[00:32:48] **Tim:** for it.

[00:32:50] **Adam:** so when you were doing that, then, then you're basically testing the same code that you're running in production, right? That that's fine. But when you are saying like, I have this code that's ES modules and I'm running this ES modules code in Node natively, but in order to run my tests, I have to first compile it to this

[00:33:07] **Adam:** other, very similar language,

[00:33:10] **Ben:** You're like, where's the bug, Ben?

[00:33:11] **Adam:** Right, exactly.

[00:33:12] **Adam:** That's, you're not testing apples to apples, and that just never sat right with me. So I don't like that. And then, there's just like, Node has, or I'm sorry, not Node, Jest has a bunch of dependencies, right? And so, and that's, that's before you add the ESM, you know, compatibility plugins and stuff. So, Node, I think it was version 18, like initially added and now more recently 20 and 22 just came out this week, is the, they added native test, tooling, right?

[00:33:44] **Adam:** So, test functions, assertion stuff, like describe and it, that sort of stuff built in you to like, you know, import, test or it, or describe from, node colon test, I think is what it is. it's actually right there in the readme of my example. So that was the other thing. It's like, you know, we're, we're, I was motivated.

[00:34:03] **Adam:** It's like, okay, Node can run my ESM. Node has built in testing. So that'll be able to run my ESM. And I won't have that like compilation step to run my tests. That sounds Ideal. That sounds choice. But then Node doesn't offer like a good, ESM mocking solution. And I, like, maybe something else I should address too is like, I know that there is at least one person in particular listening to this going, you know, you shouldn't be doing mocking.

[00:34:28] **Adam:** Mocking is not that big of a deal. You should just be, you know, doing your full end to end test. And to that person, I would say, generally, I agree with you. However, in certain situations, You know, mocking the boundaries is good, right? Like you don't want to have to hit the database. You don't actually, I wouldn't even mind if the test hit the database or hit a database in my CI pipeline, but I don't have the ability to.

[00:34:52] **Adam:** Or the desire really to let my GitHub actions, which is where we're running our CI, have access to my AWS VPC, where the database is, right? That's just not, that's not going to happen for a lot of reasons. and so like then mocking becomes useful because then you can just say, okay, I'm expecting this database query and I want to mock a successful response.

[00:35:13] **Adam:** And I want to mock a connection failure and I want to mock, you know, missing data or whatever. And it makes it real easy to get those without having to like muck around with fake data in tables sort of thing. And also it's much faster, right? You're not actually making network requests. I think there's a lot of good reasons to do mocking.

[00:35:31] **Adam:** And, and so when you add in, when you add all that up, right? Like Node has native test stuff. It all works with native ESM, basically zero dependencies. but then you're just missing that mocking thing, right? You've got that like one shortcoming. That's where I was like, okay, I can, I can write this like super simple module.

[00:35:51] **Ben:** It's like one, one line of, or I'm sorry, one file of actual functional code. And it's like 30, 31 lines long, not that big of a deal. plus, you know, the, the 75, you know, config files and YAML files and a readme and all that crap that has to come with every, every module. Classic.

[00:36:09] **Adam:** yeah, of course. but you know, That, to me, seemed very worth it and

[00:36:14] **Adam:** and

[00:36:14] **Adam:** I've been super happy with it.

[00:36:16] **Tim:** Well, sounds like you did good

[00:36:18] **Adam:** Thanks.

[00:36:19] **Ben:** Yeah. Very cool stuff.

[00:36:20] **Tim:** and you made it public. I

[00:36:21] **Adam:** It is. Yeah, yeah. So, that was another thing that was kind of frustrating for me is like, so I wanted to publish it on NPM. There was already something else called mockable and it's not for test mocking. It was for, I don't, I don't even remember, but there's already a node module called

[00:36:35] **Adam:** mockable.

[00:36:36] **Adam:** And I was like, I'm not going to sit here and wreck

[00:36:39] **Adam:** my brain for three hours or try and come up with some stupid name that is, you know, vaguely in the, the headspace where somebody, like a pun where somebody goes, Oh, okay. Yeah. Like I could probably come up with something there, but it's like, why, why bother?

[00:36:52] **Adam:** Right. So I have my NPM account and I was just like, okay, I know you can like namespace your own modules, right? I'll just do like at a title slash. whatever, well, as far as I could find out in the 10 minutes that I gave myself to do this, that's not allowed. You can't have your NPM username be an organization name on NPM for like, for, for public facing modules.

[00:37:17] **Adam:** So what I did was like, okay, fine. you know, my username is atuttle, I'll just go with AT codes, right? Cause my, that's where like a lot of my stuff is, is my, my blog is on adamtuttle. codes and my handle on a lot of things is AT codes. So.

[00:37:31] **Adam:** what it is. That's why it's atcode slash mockable on npm. Mm

[00:37:34] **Tim:** you

[00:37:35] **Ben:** I'll tell you, on a, two episodes ago, I think it was, I think it was you who told me that I could host NPM packages directly on GitHub and instead of having just a module name, I can do a GitHub URL and that like blew my mind and I don't know, I'm very enamored with that idea in general. I mean, it hurts obviously the whole discoverability concept where someone goes to NPMJS, they're not going to find your GitHub.

[00:38:01] **Adam:** Right. But if you're only doing something internal

[00:38:03] **Ben:** Yeah. If you're only doing something internal or, or just, even if

[00:38:06] **Ben:** it's

[00:38:06] **Ben:** not only internal, but just, you know,

[00:38:09] **Ben:** not,

[00:38:10] **Tim:** private little

[00:38:11] **Ben:** yeah, yeah. Like not a big deal. You just want to host it. I feel like I'm just, I was once I, figured out how it worked and I, that did take me a couple of, falling on my faces to figure out what exactly was going on, it was, it's really cool.

[00:38:23] **Ben:** It's a, it's, I don't know. I don't know. I'm just very excited. There's not like, I'm not a well articulated thought at the moment, but I just love the idea. I hate, I hate anytime I have to really give up control of code and, and somehow putting on an NPM feels a little bit like I'm giving up control in a way that I can't make very clear, you know, it's, it's, it's, it's 99 percent emotional and 1 percent something else and being able to put it on a GitHub repository that I own feels.

[00:38:55] **Ben:** If you squint, it's the same exact thing. I'm just putting it on someone else's server,

[00:39:00] **Adam:** Well, you know, you do have more control, right? Like the whole unpublished thing.

[00:39:03] **Ben:** yeah, yeah,

[00:39:04] **Adam:** not that long ago. Like you can still unpublish your own stuff. And that, I mean, honestly, In some ways that makes it worse.

[00:39:10] **Ben:** Yeah, yeah, yeah. No, totally. That's why I, you know, I, I love the idea of, of the GitHub hosting for things that I want to use, not necessarily for anything that I want other people to use, but anyway, I just, I, I don't know if I said it in the chat, Earlier or, or whenever, but I just wanted to say that that was a really cool

[00:39:26] **Ben:** thing that, that you had dropped and I learned.

[00:39:28] **Ben:** So that was great.

[00:39:30] **Tim:** You learned stuff from the

[00:39:31] **Ben:** There you go. Who knew?

[00:39:33] **Tim:** You should be, you should become a patron,

[00:39:35] **Adam:** All right, well, that's enough out of me. What do you got going on, Ben?

## [00:39:39] Ben's Triumph - ColdFusion, Tailwind

[00:39:39] **Ben:** I mean, compared to you two, my triumph here is

[00:39:41] **Ben:** pretty, not really great. I mean,

[00:39:44] **Tim:** but let's be clear compared to Adam. Tailwind.

[00:39:47] **Ben:** I, I, so I,

[00:39:49] **Ben:** was doing a

[00:39:49] **Ben:** bunch of blogging this last week or so. And, a couple of my blog posts were about custom tags, ColdFusion custom tags. And it's something I've been using forever. And I don't know, I was

[00:40:01] **Ben:** just, my, my triumph here is that, you know, 20 years deep in ColdFusion, and I still wake up in the morning and I'm excited by the language and I am feeling like there are still exciting things about it where I do something like, Oh, that's great.

[00:40:17] **Ben:** I can't believe it works that way. Or even if I knew it worked that way, I don't think I was necessarily conscious, explicitly conscious of the fact that it had some sort of particular mechanism. And when you stop to think about it, you're like, wow, that's really, it's really cool that it works this way.

[00:40:32] **Ben:** And, so my triumph is just that I love this language and, you know, last week's failure was that I was sad at the thought I might never get to use Lucy CFML professionally. You know, if I, if I never find another job that has it, but ColdFusion is still pretty great. And,and I'm thankful to be using it.

[00:40:54] **Ben:** that said I will, I will, I will temper my triumph with a small failure, which is that I had been doing some really good work in terms of trying to do some independent learning. And as I got sucked back into this sort of,amorous relationship with ColdFusion, I sort of fell off the learning bandwagon and, I was feeling kind of guilty about that.

[00:41:13] **Ben:** So yesterday I went to Udemy, which is an online learning platform, and I purchased a Tailwind CSS course. I have no real interest in Tailwind per se. But so many people love it. I know that there has to be something valuable in it for me to learn. So I'm excited to, try and hold back any judgment that I have and go into this course with an open mind and an open heart and, and see what kind of value I can extract from it.

[00:41:43] **Ben:** So I'm, I'm actually kind of excited about that.

[00:41:46] **Adam:** No

[00:41:46] **Tim:** Tailwind's been around a while. Hasn't it?

[00:41:49] **Ben:** Yeah. For years, I think

[00:41:51] **Adam:** Oh yeah, long

[00:41:51] **Ben:** like eight years or something, long time. And, and I mean, some of it seems, some of it seems like. You get a lot of value from using anything that has strong opinions about stuff because then you don't have to have those strong opinions and I completely understand and relate to that.

[00:42:10] **Ben:** So things like padding sort of being predefined and margins sort of being predefined and text and colors and all that stuff. It gives you a framework in which you are limited by the constraints of the choices. So you're kind of forced into making better looking things because you're not just going off the rails.

[00:42:28] **Ben:** Gonna do Tailwind's way, not Ben's way.

[00:42:31] **Ben:** well, I, I think I have a lot to learn from, from that set of constraints that I, I kind of go into every project from scratch and that doesn't always lead to great looking things. And so there is something nice to have in the guardrails. I don't necessarily want that to all be in inline classes in my HTML, but I do think that there are a bunch of utility classes that kind of do make sense.

[00:42:56] **Ben:** Like all of the, The layout stuff, the, the flex boxes and the gaps, and maybe some of that would, would be good from a utility classes perspective. I don't know. I'm on, I'm, I'm going through the fundamentals portion of the course right now, and I'm just learning what all the things kind of mean, but, I'm excited.

[00:43:13] **Adam:** I think one of the things that's really interesting to me about Tailwind is like, a lot of us end up kind of discovering utility classes for ourselves, right? So like, you know, as you're writing your application, you're like, you know, I do this often enough. Why don't I just create a class that's like margin underscore bottom underscore 10, right?

[00:43:31] **Adam:** So that I can add, you know, easily add that margin bottom 10 to stuff. And that's basically what utility classes are. And then, the, I think the, the argument that I like to think about is like Tailwind and utility classes is kind of like bringing, style attributes back into our HTML, right? It's like just style everything right there, except there's stuff you cannot do in style attributes that you can do with CSS, like media queries, hover states, that sort of thing.

[00:44:01] **Adam:** and.

[00:44:02] **Ben:** So I think he's figured this all out. Yeah. Yeah. I guess I was going to say is I think he's figured he's, he's jumped through all the hoops and somehow gotten it all to work.

[00:44:12] **Adam:** and it's brilliant. And he's got it, you know, you can, the stuff that you can do with Tailwind is shockingly complex, right? You can, you can have like, you know, dark mode, hover state for, you know, something that's in a group, you know, like, you've got like four or five modifiers.

[00:44:31] **Adam:** And it's like, how, how does he do that? Because, right, it's all, it's all just colon, right? You do like dark, colon, hover, colon. you know, group, parentheses, whatever, for your group name. And then, and then you're like, okay, BG red 500 or whatever. Right. So, I think that there may be an element of. Just pre, determining all the possible class names, but like, that can't, that can't really be true because like, why would he bother writing a CSS file that has, you know, all five of those things in, in all five potential orders or probably not even five, it's probably more than five potential orders, right?

[00:45:11] **Adam:** If you've got five modifiers there.

[00:45:13] **Ben:** I think it compiles. It, it, it, yeah, yeah.

[00:45:16] **Adam:** a just in time compiler.

[00:45:17] **Ben:** I think he, in a podcast I listened to, I mean, maybe like three or four years ago,

[00:45:22] **Tim:** Who's, who's the he you're

[00:45:23] **Ben:** Oh, Oh, uh, Adam Watham

[00:45:26] **Tim:** Is he the,

[00:45:26] **Ben:** he's the creator of Tailwind and,

[00:45:29] **Adam:** ends with an N.

[00:45:30] **Ben:** Watham,

[00:45:32] **Adam:** Wathen. Wathen.

[00:45:32] **Ben:** Wathan. Well, okay. Watham. he said on the, in this interview that if you shipped, All of the pre compiled, like the pre computed CSS to the browser.

[00:45:41] **Ben:** It was like 14 megabytes of CSS or something ridiculous.

[00:45:44] **Adam:** probably even more than that. I believe now, just like, you know, he keeps adding all these features. I would bet it's over a gig now,

[00:45:50] **Ben:** So, okay. So, but as I'm, as I'm watching these videos on Udemy and I wish I could remember the, the name of the teacher off the top of my head, but I can't. he keeps talking about how you have these predefined class names like MX LG, which I think was like margin in the, in the inline plane LG meaning large.

[00:46:10] **Ben:** He said, Oh, you can redefine what that means in terms of the relative size. It's like, it's all based on root. M's, the REMs, but you can redefine it, which made me think about how it's sort of this, just like framework on top of CSS custom properties or AKA CSS variables. And then actually, if you look at the compiled code, it is all just VAR statements, and that reminded me of Adam Argyle, who co hosts the CSS podcast.

[00:46:38] **Ben:** He works, at Google, I think. He has a project called CSS Open Props. Which is I kind of like a framework of 300 predefined CSS custom properties for things like border radius and line colors and gap and all that stuff. And I'm, and I'm wondering if that is kind of the, the layer below tailwind, like if tailwind is all these variables, then here's open prop saying, and what if we just were explicit about what all these variables actually are?

[00:47:08] **Ben:** I'm curious to, after I'm done with the Tailwind course, I want to go and look into the OpenProps project. I knew of it for a couple of years now, but I've never actually looked at it.

[00:47:18] **Adam:** Yeah. No, I, I have also heard of that and it, I've had the same thoughts and I just don't have enough time in the

[00:47:23] **Ben:** Yeah, yeah, yeah, exactly.

[00:47:25] **Adam:** stuff.

[00:47:26] **Adam:** But it's, it

[00:47:28] **Ben:** I'll, I'll get right back to you. so yeah, that's my triumph and, and fail ish come triumph again.

[00:47:33] **Adam:** just

[00:47:35] **Ben:** Yeah.

[00:47:35] **Adam:** in a circle.

[00:47:37] **Ben:** all things of season.

[00:47:39] **Tim:** Yeah, it's a cycle.

[00:47:40] **Ben:** Dang 51 minutes in front of my triumphs and fails. Ew.

[00:47:47] **Adam:** I think we should just call it there. We did it. That was an interesting conversation. I thought that went well.

## [00:47:54] Patreon

[00:47:54] **Adam:** All right. Well, then this episode of Working Code is brought to you by 10 year old features of NPM, like, uh,get URLs and, and I think it doesn't exist anymore, but there used to be one I'll mention, it's NPM Xmas, right?

[00:48:05] **Adam:** If you just do NPM space XMAS.

[00:48:07] **Ben:** Is the ability to host on GitHub a really old feature and I've just never heard of it. Oh, shame, shameful. I thought this was like introduced in node 18 or something.

[00:48:19] **Adam:** No, no, I mean, I don't know exactly when it was introduced, but it's definitely Easily five years old, probably ten years old, if not more. anyway, uh, you.

[00:48:30] **Adam:** I'm not there yet! it used to be NPMXMSU. It would print out a little, ASCII Christmas tree, which was pretty cool. But it looks like they took it out, so that makes me sad.

[00:48:39] **Adam:** But anyway, and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, Then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[00:48:54] **Adam:** special thanks, of course, to our top patrons, You guys rock. If you'd like to help us out, you can go to Patreon.com/WorkingCodePod, and you too can be a listener of the After Show, which is just, we're gonna keep the mics on and keep talking about who knows what, you know, mocking each other in public or something like that.

[00:49:12] **Adam:** I don't know. and yeah, we would really appreciate your support. That's going to do it for us this week. We'll catch you next week and until then.

[00:49:19] **Tim:** I mock you not when I say your heart matters.

[00:49:22] **Adam:** Oh, that cute,
