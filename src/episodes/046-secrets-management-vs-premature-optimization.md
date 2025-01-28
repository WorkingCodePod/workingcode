---
title: "046: Secrets Management vs. Premature Optimization"
description: A classic battle between doing things "the right way" and getting things done quickly and cost-effectively.
date: 2021-10-27
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/gb/podcast/046-secrets-management-vs-premature-optimization/id1544142288?i=1000539876635"></iframe>

When two systems have to communicate with each other, the security of transmitted messages is typically enforced through the use of shared secrets. Whether with encryption or one-way hashing, the receiving system can use a shared secret to verify that a producer's message has not been tampered with or spoofed. Rotating these shared secrets can be complicated; and, may even have to take place over an extended period of time depending on what's considered to be an acceptable window of backwards compatibility. This week, the crew talks about how they manage secrets, mistakes they've made in the past, and what best practices they'd like to put in place going forward.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/046-secrets-management-vs-premature-optimization.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** so. Th I believe, and I'm talking out of my depth here, but I believe at work, we have this like tiered environment variable system where there's a, there's like a set of global keys that any environment can share.

[00:00:14] **Ben:** And then you go down a low level and then there's like overrides for particular keys that you can have at individual levels. I didn't know. How are you dealing with secrets across your kind of multi-tenant single tenant distribution?

[00:00:30] **Adam:** I can tell you, but then I'd have to kill you

[00:00:33] **Ben:** Yeah,

[00:00:33] **Adam:** Okay. Here we go. It is show number 46 and on today's show, we're going to talk about secrets management versus premature optimization.

[00:00:58] **Adam:** There's a balance you have to strike there

[00:01:00] **Adam:** so before we get to our triumphs and fails today, a quick note, I'm in Washington, DC at the moment, preparing for an event. And so you might hear some car honks and train noises and sirens, and who knows what behind me.

[00:01:12] **Adam:** And if you do, I apologize, but Hey, at least you got a new episode, right? Okay. So.

[00:01:19] **Carol:** You all city folk.

## [00:01:21] Adam's Fail

[00:01:21] **Adam:** without out of the way, let's do our trams and fails and it looks like it's my turn to go first. So I'm going to start us off with a very tiny little fail that when coupled with some bad timing became a significantly bigger fail, like a really bad Vail makes you want to throw up type of thing.

[00:01:40] **Adam:** that I turned into a triumph that again, turned into a fail.

[00:01:46] **Tim:** As a journey.

[00:01:47] **Adam:** Yeah. Yeah. So we have a bunch of Lambda functions, a little microservices to do things. And because when you're developing these things, you're not sure if you're going to continue to change them or whatever. The first iteration of it, eventually it becomes production. And then if you're not careful, you find yourself without a QA environment, right.

[00:02:07] **Adam:** You just have production. And when you need to make a change, you deploy it up to production and there you go. You don't have a great way to test and QA because it's like integrated in your stack. that was our situation with something like eight or so of our Lambdas. and we've been doing, we've had that situation for the better part of like the last two or three years now.

[00:02:25] **Adam:** And we've survived, off hours deployments or whatever, that sort of thing, just being careful. Well, I did a Lambda deploy recently earlier this week and because of really, really, really bad timing, I made a really big mistake. For a really important email, basically the, so when we render an email, we have the text body and the HTML body.

[00:02:47] **Adam:** So if you have like a text only male client that shows you nicely formatted text instead of HTML, well, I swap the two. So if you, if you got, if you were an HTML reader, you just all like a plain text email, but even worse. If you were a text only male client, then you got whole bunch of HTML as the text of your email.

[00:03:08] **Adam:** And making it worse. This email was targeted at like the VIP's of VIP's of this audience. Right. It was like the board of trustees of the university. so that was, that's why I was like feeling I wanted to. And it was just a very bad day for me. Anyway, I turned it into a little bit of a triumph because I use this as motivation.

[00:03:29] **Adam:** I said, I'm not doing anything else until every single one of these things has a proper QA environment and at least some tests. Okay. So that was a triumphant. I did that. And then here's the last fail. we've had this situation for the better part of like two plus years. Now it took me one day to add QA and some testing for all of these things.

[00:03:49] **Tim:** Like, why were you waiting?

[00:03:51] **Adam:** Exactly.

[00:03:52] **Carol:** Yeah.

[00:03:52] **Adam:** Oh, so it's a rollercoaster of a week for me, but at least it's behind me

[00:03:58] **Carol:** Wait, what was the last fail? I don't know.

[00:04:01] **Adam:** that it only took a day to do something that we've been waiting on for you.

[00:04:06] **Carol:** Okay. So it was a long-term failure, but

[00:04:08] **Adam:** Yeah. Yeah. It was like, we've been kicking the can on it. Cause it just, it felt a little like, eh, we don't really need it, but yeah, we did.

[00:04:18] **Carol:** Ian needed it.

[00:04:19] **Adam:** Yeah. So

[00:04:21] **Carol:** Well, I'm so sorry. you.

[00:04:22] **Carol:** congratulations. And I'm so sorry.

[00:04:24] **Adam:** thank you.

[00:04:26] **Ben:** a is a text only email client these days. Does that

[00:04:31] **Carol:** I think you can configure Gmail to show you only text. And like, you can do that. Most of them, you can say like only show me text and it's probably for like accessibility reasons. So here's the other piece. We, so all that stuff I did, I pull out the,

[00:04:44] **Carol:** the part. So even though Gmail message actually. Parts is what it's called. Like, if you go look up the model for how they actually structure their emails, they have the parts. So each message has its part, and it has a plain text version of the HTML.

[00:05:01] **Carol:** So whenever I log everything that came through on the email, I don't log the HTML version. I logged the plain text version so that when I want to put this back out, I just have the texts from the email as opposed to all the HTML with it. So I go pull out the plain text for

[00:05:16] **Adam:** So, this is for your, this is for that service you were building, right?

[00:05:20] **Carol:** yeah.

[00:05:20] **Carol:** For the autoresponder. Yep. Because I don't want all of the embedded stuff. I don't want to know where the dibs, where I don't care about all the blocks. I just want the body of the message.

[00:05:28] **Adam:** Right. And if this is an email, I know I've kind of wondered that if you write an email on your phone and you put in some hyperlinks or whatever, cause you're a power email user on your phone. does that sense? I mean, it's got to send it as an HTML email because then you get the email and it's got links in it.

[00:05:44] **Adam:** Does that also send a plain text version of that and like, I'll have to try that and see what it looks like.

[00:05:50] **Carol:** Yeah. I mean, everything I've found said it shows that it all gets stripped out. So all my testing showed it very pretty. It's just plain text.

[00:05:57] **Adam:** Yeah. Yeah. I'm sure that it does something. The question is just how

[00:06:00] **Carol:** Oh yeah. Gmail is amazing. And just as things magically to make it? work, don't question it.

[00:06:06] **Carol:** Yeah,

[00:06:06] **Ben:** you all handcrafting the text version of the emails that go out or is it, or are they somehow generated from the HTML version?

[00:06:13] **Adam:** Bespoke emails.

[00:06:15] **Adam:** I mean, our, yeah, our tool is very much for email marketing professionals and so they want that fine grain control. They have, they might send slightly different content in a text version than a HTML version. So, yeah. So that's me. how about you, Ben? What do you think.

## [00:06:33] Ben's Fail

[00:06:33] **Ben:** I'm going to go with a fail and this is sort of a theme of mine. This is not ex, not exactly imposter syndrome. I'm just going to categorize this under envy and, lately things have just felt challenging, professionally at work, just programming, not with work itself. Just the work itself seems hard.

[00:06:53] **Ben:** And. I've been doing this for a fairly long time. And a lot of it just doesn't seem to get easier. And, and I look at people who from the outside, and I know this is definitely a skewed perspective, but from the outside it looks like a, some people, just things happen more easily for them. Uh, just, I don't know it and I'm envious.

[00:07:15] **Ben:** I wish things happened to easier for me. Sometimes. I wish didn't always feel like such a great. but so I know that's just an emotional situation and not the reality, but,the fail there is, I'm not able to fend off the feelings.

[00:07:31] **Carol:** I'm on the opposite side of you. I tend to feel guilty because things just happen and I feel really lucky all the time that things just kind of work out and things just go great. And unlike, yeah, I get it. I get being on the other side though. Cause it just feels lucky. Like I just feel like I land in the right spot at the right time for it to just go.

[00:07:51] **Carol:** Right. So.

[00:07:53] **Tim:** Wow. I didn't make them feel bad.

[00:07:55] **Carol:** Sorry, Ben, I wasn't trying to make you so bad. I mean, it's not that I'm any better. It's not, it's just, I do feel like lucky, overall, this as a

[00:08:03] **Tim:** I'm with you, Ben. I feel you, it's like, there's stuff like I've written and it's like worked great for years and all of a sudden stuff stops working. Right? It's like, there's these new challenges. And I don't know. my stuff hasn't really changed significantly. And so why is it so hard?

[00:08:17] **Tim:** why can't it just like run and just be okay. Cause now I got to stop, cause I'm off to other stuff now. I'm like, why do I have to come back to this? This has been great for years, And now all of a sudden I'm having to troubleshoot stuff and I don't understand why now?

[00:08:29] **Tim:** why.

[00:08:29] **Carol:** nothing changed.

[00:08:30] **Tim:** Nothing. Why is it breaking now? Right. And,it just frustrates me. It's like, I feel like I can't get ahead because it's like, all right. I wrote this two years ago, it's been working fine. And all of a sudden it's pulling me back in this pit of despair. And, I don't want to be working on this.

[00:08:44] **Tim:** I want to be working on new stuff that makes money. so yeah,I feel that it's just that level of complexity, it's no software, you write doesn't live in a vacuum.

[00:08:53] **Ben:** Yeah. and not necessarily dovetail with what you're saying, but just in terms of passage of time, I also find that the more I learn, the more I'm aware of how little I know and how badly I've built things in the past. So it's almost like.

[00:09:10] **Ben:** Yeah.

[00:09:11] **Ben:** the more knowledge I mass and I try to amass a lot of knowledge, it feels like all it does is illustrate in the grand scheme of things, how little I actually know and how much more can be learned and that it will never be possible.

[00:09:25] **Ben:** And that in the, in this world of expanding technology, it's only going to become harder and harder.

[00:09:31] **Carol:** Oh, I will totally second that. I met lucky, like I find shoes on sell, not my codes. Great. So let's just be clear here on I'm lucky. Okay. Things Just go right

[00:09:45] **Adam:** Just the important stuff.

[00:09:46] **Carol:** shoes.

[00:09:47] **Ben:** That's awesome. Hey Tim, what about you?

## [00:09:50] Tim's Fail

[00:09:50] **Tim:** so I don't vacation. Well, it's a fail. I mean, I had this whole week off, so this week is a. It's a spring or fall break for the kids. So I, long in advance, I'm like, gonna take the week off. I'm coming off a week in Vegas last week for work. And I know this is really like, first-world whining here, but I can't. It's like, I just can't unplug. I worked, I keep working probably like four hours every day, just cause I can't. everyone is sick in our house and they don't have COVID, but they do have like bad Coles. So it was like, we were going to go somewhere. We didn't really have definite plans. It's probably, and that's probably a good thing, but it's like, everyone got sick.

[00:10:30] **Tim:** I came back from Vegas and everyone's coughing and sneezing and they sound terrible. And like, even though they don't have COVID, I don't want to take some coughing children into a public space and people look at me funny. So it's like, we're not going anywhere. I'm staying home. The best thing I did today was I took a nap before the show.

[00:10:46] **Tim:** That's why I was late for the show. Sorry guys. I was, I just was napping. It's like, that's the most exciting, it's the most pathetic vacation ever. I took a week of PTO and all I can say I really done differently is I've napped more than usual. So yeah. I feel like a real failure when it comes to vacationing.

[00:11:02] **Carol:** No, it's a staycation. You need it,

[00:11:05] **Tim:** I

[00:11:06] **Carol:** but not with six family though. That's yeah,

[00:11:08] **Tim:** bored. I really want to do

[00:11:09] **Carol:** I mean, you're working so that's not good.

[00:11:12] **Adam:** This

[00:11:12] **Adam:** is safe for me. That's when I would spend time like learning a new technology or catching up on other hobbies.

[00:11:17] **Carol:** Sometimes the motivations out there napping is way better.

[00:11:20] **Tim:** yeah. Now things way better. Yeah.

[00:11:22] **Carol:** you that.

[00:11:22] **Tim:** Having is way better. Yeah. We had plans like, my son was like, we're going to do some more blacksmithing. We're going to get better our blacksmith thing. And of course he's not feeling good, so we're not doing that. So it's was, yeah. I just feel bad.

[00:11:31] **Tim:** I just feel like it's been a waste of a week.

[00:11:33] **Carol:** well I hope you guys get better.

[00:11:35] **Tim:** I'm fine.

[00:11:36] **Carol:** I hope the family gets better than.

[00:11:37] **Tim:** absolutely. Yeah. Oh no. I've been wearing a mask in the house spring, Lysol everywhere. I don't want to get whatever they have. They sound terrible. So

[00:11:45] **Ben:** Ah,

[00:11:45] **Carol:** yeah. it must have what I had. Cause I'm just getting over it and I was sick for two and a half weeks with that.

[00:11:51] **Tim:** yeah. It's yeah. it's been bad. So, anyway, that's my failure. How about you, Carol?

## [00:11:56] Carol's Triumph

[00:11:56] **Carol:** Well, I have a trial. I'm going to a conference. Yes. I found out this week I get to go to, re-invent to AWS. So I will be out there November 29th through December 3rd. And the best part is I'll be back a week and then the following week, I'm going back for my birthday.

[00:12:17] **Carol:** So I'm going to be in Vegas.

[00:12:18] **Carol:** for two weeks.

[00:12:19] **Carol:** Yeah. Yeah. So I'm excited about the conference. This is going to be so much fun.

[00:12:25] **Ben:** my understanding is that it's a massive conference, like 50,000 people or something. I mean,

[00:12:31] **Tim:** at like

[00:12:32] **Carol:** Yeah.

[00:12:33] **Ben:** how do you prepare for something like that?

[00:12:35] **Carol:** well, I'm going to go ahead and reserve my seats and everything because they want you to reserve seats in this. They don't want anyone kind of walking around. so I'm going to do that? So I'll already have a game plan of what I plan on learning. So I'm going to, pre-study what I want to learn to make sure it has a good understanding of it.

[00:12:49] **Carol:** So when I go into it, I know what I'm going to be doing. And then they are requiring everyone vaccinated. So that's really good.

[00:12:55] **Carol:** Yeah.

[00:12:55] **Tim:** Yeah, Vegas has, was really strict about vaccination and masks.

[00:12:59] **Carol:** And ask it. Yeah.

[00:13:01] **Ben:** Are you going with a group of people from work or just you?

[00:13:04] **Carol:** Yeah, it's a four, I think there's four of us going or five of us, oddly enough, people didn't sign up. Like they were like, who wants to go put in? We'll talk about it. And only a couple peoples that I want to. It's we kind of have this, a little issue of people not wanting to learn new things and kind of not willing to venture outside what they know.

[00:13:24] **Carol:** They like being in their comfort zone. So we have a handful of people who are constantly like challenging the status quo and wanting to do better and wanting to change what's going on. And those are the people who are like, I want to go, let's go do this thing. So, yeah.

[00:13:39] **Tim:** I can't imagine an Amazon conference. I mean, do they have like multiple tracks for all 5,000 of their services? content.

[00:13:48] **Carol:** Oh, you can't imagine. Yeah. I'm excited about some of the leadership stuff. Like that's some of the more, interesting tracks. I want to go sit in on

[00:13:56] **Tim:** What do you mean by that?

[00:13:57] **Carol:** like a lot of their big leader. People are going to be there just talking about general leadership stuff, like, leading teams, managing teams, building, your client base, those kinds of things.

[00:14:08] **Tim:** Cool.

[00:14:09] **Carol:** better person be a better person.

[00:14:12] **Ben:** Yeah, good luck.

[00:14:13] **Carol:** Yeah.

[00:14:14] **Adam:** like fun. I've never been to reinvent.

[00:14:15] **Carol:** Yeah. Yeah.

[00:14:17] **Ben:** I think there, I think I heard that it's a hybrid model this year, which they may have not done before, where you can be in person. And I think maybe watch live online. I'm not.

[00:14:26] **Carol:** Yeah, the live didn't seem to have everything. It had the keynotes, it had breakout sessions. It had the leadership track and it had a couple of other things, but I don't think everything is going to be is going to be online. But yeah, a lot of it is online and it's free if you want to do it online. So where if you go, it's kind of expensive.

[00:14:45] **Carol:** It's like $1,700.

[00:14:47] **Carol:** No,

## [00:14:47] Ben's Hard-Coded Secrets

[00:14:47] **Adam:** All right. Well, who wants to kick off this week's topic? Ben, was that kind of your ballpark here?

[00:14:54] **Ben:** So, we have we're in the middle of a penetration test at work

[00:14:59] **Ben:** and unlike previous penetration tests where people have been given sandbox environments and they can basically try to attack the system in any way that they want, this penetration test involved us actually giving source code to certain parts of the application over to the people who are testing so that they.

[00:15:18] **Ben:** Try to find lower level vulnerabilities that, that they might not have been able to stumble across. And one of the things that they flagged in a couple of really old parts of the application are some hard-coded secrets that, two services would use to authenticate against each other or, sign a request so that it can't be manipulated.

[00:15:37] **Ben:** Best practices is now to not keep that in your source code, obviously.

[00:15:42] **Carol:** Duh.

[00:15:42] **Ben:** it in something like an environment variable or something that can be loaded on the fly, but wouldn't necessarily be exposed to the source code was, seen by a malicious actor. So I've spent the better part of the week rotating some of these legacy secrets that are in really old parts of the. And it's been really frustrating because it's not as simple as just taking a value, putting it into an environment, variable, and then reading it from the environment or an environment variable instead, because these are used to communicate across services. So, because I can't deploy multiple services at the exact same moment, I can't change the value that I use to sign a request on one side and not change it, to validate the request on the other side.

[00:16:25] **Ben:** Otherwise the communication was.

[00:16:27] **Adam:** Right.

[00:16:27] **Ben:** So, what I've had to do is take these single values and turn them into an array or like a, to tubal where the first value is the old hard-coded token. And then the new value is an environment based token, so that now the receiving service can check multiple tokens. Then I can get that into production that can go to the calling service, have it updated, to use a new environment, variable for the new token.

[00:16:54] **Ben:** And then I can go back to the old service and then deep provision, the old token, that was part of the array. And it's just been a very frustrating experience. And it makes me think about best practices in terms of how I would organize tokens going forward. And part of it. I always, again, I get stuck between this premature optimization mindset and then they just get it done mindset where, so to step back like the easiest possible thing to do, if two services have to communicate is having environment variable.

[00:17:30] **Ben:** It literally both of those services have access to so that when the services combine, they can share it. The problem with that is that they have direct access to the same environment, variable, like they're pulling it out of the same shared space. Which then couples those services fairly tightly together.

[00:17:48] **Ben:** So then the next thing would be to be, have each service have its own environment. That happened to coincidentally have the same values in them so that you can independently change those to token values, which decouples the systems in terms of where they're accessing their data. But so it keeps them coupled because now they have to communicate then like the next level of complexity would be to have multiple tokens that each service can use so that it can, I guess, multiple tokens that the receiving service can use so that it can rotate tokens without breaking the.

[00:18:18] **Ben:** And then we can do the dance of kind of incrementally changing the tokens across the various service relationships. And then like the ultimate level of complexity is actually not even having hard

[00:18:29] **Adam:** It's just used Kubernetes.

[00:18:30] **Carol:** Hmm.

[00:18:32] **Ben:** Well, to have something where instead of hard coding, these values almost treat your service like. like, like a software as a service where you could actually maybe even expose a dashboard where people could come in and register, provision tokens, and then could then be responsible for de provisioning and provisioning new tokens like you would do if you were using like a Twilio API or a Stripe API, we have to go and actually manage your tokens. And I like, part of me wants to go. Super complicated and be like, yeah, if anybody wants to call my service, I should be able to give them a dashboard where they can provision stuff, but that's wicked amount of work. And then would probably be really frustrating for anyone who needs to come consumer services.

[00:19:13] **Ben:** So.

[00:19:13] **Adam:** What'd you need to do.

[00:19:14] **Carol:** Because they're not used to it.

[00:19:15] **Adam:** Create a new microservice that just exists for the purpose of key management and application can just like announce, Hey, I exist and I need a key and I need you to create like, keep this running list of my last three keys and I, okay. I'll generate a new one.

[00:19:31] **Ben:** I feel like something like that exists though. Isn't that? What,

[00:19:33] **Adam:** I dunno, but why would you use an existing thing? Why not write it yourself? Joking.

[00:19:42] **Carol:** Oh, my goodness.

[00:19:44] **Ben:** I guess, there's not a, there's not a specific thought or question in my rambling there. Apologies, but I guess it's more just general. Secret management and like the levels of complexity. And where is that right balance between this is easy enough to use, but also secure, but not terribly flexible.

[00:20:04] **Ben:** I don't know. I don't know how you guys approach this kind of stuff.

## [00:20:08] Managing Secrets

[00:20:08] **Adam:** dinged for a secret that's in the code in a pull request this week, when I was doing all those QA environments for our Lambda functions. And. My response was like, yeah, but we have a bunch of these Lambdas and they all do. It's like the exact same SDK using the exact same key and they're all doing the exact same thing.

[00:20:25] **Adam:** And so like, you're not wrong, but also like look over there.

[00:20:30] **Carol:** So you said there Lambdas using it, Right.

[00:20:33] **Adam:** so we could do environment variables. Absolutely. and

[00:20:37] **Carol:** store or, put it in secret And, then just pull it in and

[00:20:40] **Carol:** this never.

[00:20:41] **Tim:** Okay.

[00:20:41] **Carol:** It's stored in AWS.

[00:20:43] **Adam:** again, you're not wrong. And. so it's like the, like that conversation we were having about the Twitch code leak, where, like I see there's a siren. I don't know if you guys can hear that.

[00:20:52] **Carol:** Yeah. We were talking about the Twitch cuddly before we started recording. So we should step back. Yeah.

[00:20:57] **Adam:** I mean the long and short of it is twitches code leaked. And there was some people like tearing it apart, online and critiquing the code. And, the, there was some conversation about that in a pair. I guess the person kind of leading the conversation with saying like, yeah, but no code is perfect code.

[00:21:12] **Adam:** And there's always constraints for, we have a business to run, right? we have to balance doing things the right way and doing them perfectly with getting things done in a profitable. Um, so I mean, long-term absolutely, I think that we'll be pulling those secrets out of that code. And probably the first stop we'll do is environment variables.

[00:21:33] **Adam:** And when that becomes problematic, then we'll do something more significant, like using a secrets manager situation. But I mean, we have other things, we have lots of things that use environment variables. So that would be the first place that I would think to look if I was going to rotate keys and I would be

[00:21:48] **Adam:** confused

[00:21:48] **Tim:** you say it, environment variable, H what, how has that work in practice?

[00:21:52] **Adam:** So when you configure a Lambda function or a windows server or whatever, there's a little config section where you can say, I want to add an environment variable. and this is just sort of a system variable. You give it a name and a value in both our strings. and so for example, you can say the environment itself, like the most common one for JavaScript is node underscore ENV.

[00:22:14] **Adam:** and so you'll see that to be development or QA, I guess test is more common than QA and production. but you can also, you could easily, make that your S3, access key and secret or whatever they call those things.

[00:22:26] **Carol:** still tech. This point, if you do it this way.

[00:22:29] **Adam:** Yep. Still plain text. Although I think I'm not positive. Don't quote me on this, but I'm almost sure that the environment variables that you configure in the Lambda dashboard in the AWS console are encrypted.

[00:22:42] **Adam:** When they're stored, they're decrypted to show you in the dashboard and encrypted. And then when they, when the function gets invoked, they get decrypted and sent to the function. So it's, I don't know.

[00:22:53] **Carol:** Sounds accurate, but still visible. Yeah.

[00:22:57] **Adam:** Yeah. So anybody who would have access to, edit the. In the case of Lambda, would it be able to see that secret? And that might be a problem, right? And like in my company has not because there's three of us and we all have the keys to the kingdom, but I can absolutely see plenty of companies out there that wouldn't want that, would want their developers to be able to.

[00:23:14] **Adam:** And so that actually reminds me of you have. get hub actions, right? So you can set up secrets in your GitHub organization at the organization level, and you can set them up at the repository level, and those are available to your GitHub actions so that you can do things like deploys or whatever else, call APIs for various things and the keys themselves.

[00:23:34] **Adam:** Like you can see what the, what secrets are available by name, but you can't see their value. And actually once you set it, you, there is no way to see what the value is. It's a. Only interface, you can override it and update it with a new value, but there is no way to see what the current value is.

[00:23:51] **Ben:** No, sorry. I, if I can interject there because you triggered me ha. We have to do this thing a while back at work, also involving token rotation, across different services. And I remember there was this one team where, they needed to be able to rotate across two different tokens. So they wanted to set up an environment variable.

[00:24:10] **Ben:** That was a common delimited list of tokens that they would check. And I, and my point to them was. Sounds really challenging because when you need to add a token later on, you essentially need to know the earlier tokens on that list. Cause there's no tooling at work where you can just say, add this value to an existing environment variable, but you can either set environment variables or create new ones in our platform dashboard. and so I'm like, you'd essentially have to keep stored locally your secrets that are in production so that when you need to add one later, At a new list item and then set the whole value and their Lego we'll know, we could just ask the platform, people to do that for us. And then we don't have to worry about it.

[00:24:50] **Ben:** And I'm like, yeah. Or you could just use two different variables. I wanted people to start using this one pattern that I learned about where you use essentially a current token and a future token. And you can know, you always check against either the current token and the future token. Then as you're rotating, eventually the future token gets moved into the current token and the future token can be changed or can be.

[00:25:11] **Adam:** Yup.

[00:25:12] **Ben:** And that way you're only ever setting whole values. You never need to know the value that previously existed. But my, I like, no matter how hard I argued and shook my fist, they were like, no common delimited list is easy.

[00:25:28] **Adam:** my lawn old.

[00:25:29] **Ben:** Yeah.

[00:25:31] **Tim:** So, so, I mean, maybe this is a bad practice that we're doing, so we don't put the secrets in source code, but it, we do, it is part of our deploy process. We don't use Lambda functions or anything like that, but when we deploy code, there is a config file that's outside of. The project, right? So it's somewhere else on the hard drive on the Linux machine and the system knows about, and it goes and looks it up there.

[00:25:55] **Tim:** I mean, and if you want to change it, you just, you change the config file as part of your deploy process. and is that bad practice or.

[00:26:01] **Ben:** it's. Yeah, I mean, I

[00:26:02] **Carol:** yeah, sure. Short answer. Yes. Because if they get you.

[00:26:06] **Ben:** it's a continuum. It's a continuum.

[00:26:08] **Carol:** like if someone

[00:26:09] **Adam:** it's closer to

[00:26:10] **Carol:** the machine and got the source code off, they're going to have that config path.

[00:26:15] **Tim:** Well, if they get on the machine, they got everything anyway.

[00:26:17] **Adam:** they could read the

[00:26:17] **Adam:** environment variables. And so I think where this one, this particular approach falls down is any, then anybody that has any access to your source code, repo, even an intern that you hire to work on a thing can sell your secrets

[00:26:31] **Carol:** no. I thought you said the source that's not Kevin source code not kept source. Yeah. It's not.

[00:26:36] **Carol:** checked in.

[00:26:37] **Adam:** It's not.

[00:26:37] **Carol:** it lives as a text that like an admin who has rights to RVPN

[00:26:42] **Tim:** So basically the deployment

[00:26:43] **Carol:** Yeah.

[00:26:44] **Adam:** Okay. It sounded like it was in your repo, but it's outside, like the

[00:26:46] **Adam:** web

[00:26:47] **Carol:** No it's outside the repo.

[00:26:48] **Carol:** Yeah. So

[00:26:49] **Carol:** a little better.

[00:26:50] **Ben:** where we're in the repository. You'll have something like a dot ENV dot template file, which gives you fake values, but shows you the data structure and then locally. And then you'll have a, in your get ignore file. You'll have a get ignored. the real. And then someone hard coats, a text file in production with the real values.

[00:27:13] **Ben:** And you have your development values locally, but they never get committed to there. Yeah. Yeah. I've done that for personal thing.

[00:27:18] **Carol:** Yeah.

[00:27:18] **Ben:** it's super easy.

## [00:27:20] AWS Secrets Manager

[00:27:20] **Carol:** So the way that we do it with our land, as I was mentioning earlier, Adam is, we put it in secret manager or we put them in parameter store. So I'm like, for example, our service user that has access actually run this application that I have, which will have access to everyone's email.

[00:27:37] **Carol:** The private key for that, which is used authenticate into Gmail is stored in AWS, in the secrets man. and the way that gets generated is dev ops goes into GCP, creates the cert, which I can never see. Cause it's, once you pull it, it's a one-time pole and it's just there. Then they upload it and then that's it.

[00:27:58] **Carol:** So it only ever exists in one person's hand. And then in the secret man, So if any developer comes behind me, they can't see what the key is. They can only get the encrypted version of it and then read it. So they're just sitting there with it with no ability to change it or use it. So then production's the same way.

[00:28:15] **Carol:** So then you know that keys out there and it's being used, but nobody can ever touch it or change it. Only the one dev op.

[00:28:22] **Adam:** Is there like a SDK or something that you can connect to, to pull secrets out of the secrets manager at runtime to use them? Or does it get somehow like pushed in as an environment variable at runtime? Or like, how do you access those?

[00:28:35] **Carol:** Yeah, I just straight up go hit AWS, and say, Hey, go grab me the parameters or go get me the secrets. And I put it into, a whole nother class that I've created, which technically goes into like the environment variables. But yeah. So I don't know if it's at runtime by I'm assuming is I run time.

[00:28:52] **Adam:** Okay.

[00:28:53] **Tim:** But at what point is it being decrypted,

[00:28:55] **Carol:** oh, I

[00:28:56] **Adam:** sounds like at run

[00:28:56] **Carol:** look at that.

[00:28:57] **Adam:** it sounds like it's at runtime.

[00:28:59] **Tim:** but it can be decrypted.

[00:29:00] **Carol:** And I can't get the text of it

[00:29:02] **Tim:** You can, but obviously something can.

[00:29:05] **Carol:** and no mean, the service running it can't like the actual AWS STK isn't pulling in like the text version of it. It's just giving me something that's in the cross.

[00:29:14] **Adam:** And we're out of our depth

[00:29:17] **Tim:** Right. I don't follow somewhere. It's being

[00:29:20] **Carol:** Yeah. Maybe, but like, I can't see it. if I go console, log this out, I just get crap. Like there's nothing that I could use from that.

[00:29:28] **Ben:** how is that possible? Cause

[00:29:29] **Adam:** or maybe your secrets are all just a series of poop emojis.

[00:29:32] **Carol:** No, it just looks like encrypted. Like, it looks like jibberish on the screen. Like if you go down to the. Maybe I should go back and look and make sure I understand it a little bit better.

[00:29:42] **Carol:** I figured it out. It's with, I'm a role, as I say, I'm a, as I am, right. I is

[00:29:47] **Adam:** Aye. Aye. Aye. I either say I am, or I am

[00:29:51] **Adam:** either way. It's.

[00:29:51] **Carol:** I am. yeah, so I'm a role. I figured it out. So I had opened the code to see what was going on with it. So in dev you can see it, but in production, you don't have the ability to run decrypt, your role as a developer to the production. Whenever you pull it, you can't run decrypt on it. So you can't see the string version of it.

[00:30:08] **Carol:** So that's where I was off at.

[00:30:10] **Tim:** Okay,

[00:30:10] **Adam:** But then

[00:30:11] **Carol:** You can, you can, but all, you have to have the role to actually decrypt it yet.

[00:30:14] **Carol:**

[00:30:14] **Carol:** And we don't have any put rights, so we can't save anything.

[00:30:18] **Adam:** But when the code is executing, it uses a roll that can read it.

[00:30:21] **Carol:** Yeah. So it can't. and I can't execute the production Lambda in that role. I don't have access to the production Lambda. Like I can't see it. I can only go through Jenkins to deploy it.

[00:30:31] **Adam:** but in theory, you could write some code that decrypts the secret and emails it to yourself. It wouldn't give has code review,

[00:30:37] **Carol:** Yeah, we can give has COVID me, but yeah. I mean,

[00:30:39] **Adam:** but

[00:30:39] **Carol:** technically

[00:30:40] **Carol:** you could.

[00:30:41] **Carol:** Yeah,

[00:30:41] **Tim:** Jeff Bezos knows it.

[00:30:43] **Carol:** yeah. I guess technically, so, Yeah.

[00:30:45] **Carol:** so that's where it was. That's how it's working. Sorry about that.

[00:30:48] **Tim:** Nah, I

[00:30:48] **Carol:** be, can be decrypted.

[00:30:51] **Tim:** That's good to know.

## [00:30:53] Penetration Testing

[00:30:53] **Tim:** I was going to say bid. So one thing I found interesting is that you said that your pin test is a word I prefer than penetration. is, you gave your source code. So we've been, doing pen tests for decades and never once have we had to give her our source code, which. I think it's actually a good idea, to give it because, hackers, these days probably can think they can compromise your system.

[00:31:14] **Tim:** They can probably get a hold of your source code at some point and utilize that. But yet never once have we ever had to do that? It's always, they're doing important discovery. They're doing running, test kits, script kits against, known, known vectors, which is kind of traditionally where hackers are going to try to get you rather than actually having access to your source.

[00:31:32] **Ben:** It's funny because, so at work we have a wife, a web application firewall, and it's a complete black box. I mean, I have no idea how it works or how the rules work, but I can't tell you how many requests make it to the application. Where in the URL, people are requesting like seventeen.dot slashes passwords dot INI.

[00:31:54] **Ben:** And I'm like, how was the WEF let in this, through this will never be a valid request against the system. No one will ever ask for an INI file. Uh, password file. It's frustrating. as far as giving the source code, I don't have all the details, but I think maybe this is a prerequisite for some special type of certification for the system. but don't quote me on that.

[00:32:15] **Tim:** Oh, okay. Yeah, maybe it's coming down the road for me too.

## [00:32:19] Managing Secrets Over Many Environments

[00:32:19] **Ben:** But one thing that we have a complexity at work is we have a. we call them private clouds, but essentially it's we have our multi-tenant environment where we have the majority of our customers, and then we have isolated copies of that environment that we call private cloud environments for specific, high contract customers.

[00:32:38] **Ben:** And I know Adam, you have, a number of clients based on good branches. I can't remember. I forget what your strategy was, but,

[00:32:47] **Adam:** PTSD. That's my strategy.

[00:32:48] **Ben:** so. Th I believe, and I'm talking out of my depth here, but I believe at work, we have this like tiered environment variable system where there's a, there's like a set of global keys that any environment can share.

[00:33:03] **Ben:** And then you go down a low level and then there's like overrides for particular keys that you can have at individual levels. I didn't know. How are you dealing with secrets across your kind of multi-tenant single tenant distribution?

[00:33:19] **Adam:** I can tell you, but then I'd have to kill you.

[00:33:22] **Ben:** Yeah, certainly. I don't want to, if it's sensitive, let's not talk about it, but, it's all very complicated on my end.

[00:33:29] **Adam:** I mean the long and the short of it is we are moving to an architecture where we will have far fewer secrets than we already do. And we already have very few, I mean, we're talking about like database passwords because we have customers, every customer has our own database, so they all have separate user account and password.

[00:33:50] **Adam:** Should one of those,applications get compromised, you can't then traverse across all of our databases. and then it's basically just, like IAM user accounts are not user accounts, but they have like user lists accounts where you can, like, you just have a key and secret that you can use to interact with APIs and SDKs to be able to use various services as three and whatever.

[00:34:12] **Adam:** and so we have. like I was mentioning before a few of those are still in the code. and, but by and large, we were moving those over to environment variables. and we are moving as much as possible. Everything over to be multi-tenant as far as I know, we have not offered anybody, a private cloud situation, and I don't expect that to come up because we are not targeting.

[00:34:33] **Adam:** And I don't see a future where we target. Like any government anywhere we are very strictly, only looking at higher education colleges and universities

[00:34:43] **Ben:** It's also very expensive to have duplicate copies

[00:34:46] **Adam:** it is. Yeah. So yeah, I mean, there, wasn't a very interesting answer. I don't think, but, that there you go.

[00:34:55] **Ben:** Oh, it's all good. It's all good. I environment variables are one of those things where early on in my career, I

[00:35:02] **Ben:** thought It was

[00:35:02] **Ben:** super

[00:35:03] **Adam:** It seemed like black magic.

[00:35:04] **Adam:** Yeah.

[00:35:05] **Ben:** And then once you realize that it's just a value being pulled from somewhere, you're like, oh, that's not so common. And I know you've been transitioning, over to Lucy, CFML away from Adobe ColdFusion for parts of your stuff, for parts, just parts.

[00:35:19] **Ben:** and one of the cool things about Lucy, is that you can actually just pull the environment variables right out of the server scope,

[00:35:25] **Ben:** which is, I mean, if you're coming from a node background, node is basically what it's processed at

[00:35:31] **Adam:** ID

[00:35:31] **Carol:** Yeah, you do. Yep.

[00:35:32] **Adam:** yep.

[00:35:33] **Ben:** So

[00:35:34] **Adam:** Um,

[00:35:35] **Ben:** little convenience.

[00:35:36] **Adam:** yep. Yep. And, so I mean, we took advantage, took full advantage of that. Right? So as we were making that transition, we were coming from. Holy,every single instance, every environment for every customer was a very bespoke right hand rolled, we'd log onto an ECE two instance, all right, you're going to be this go and configure the data source and go and configure this and that.

[00:35:58] **Adam:** and that just doesn't scale. Right? Once you get to a certain point, it's you spend your entire day just managing instances. So what we, where we. Like transition. This is like three or four steps down that road. But, now we have like a single AMI that we will deploy when we want to bring up a new customer and you just sign in and you fill in a couple of environment, variables in windows.

[00:36:19] **Adam:** and then Lucy and other things on that box, we'll pick those up and run with it. So, you're our production for this customer and here are some secrets sort of.

[00:36:28] **Ben:** Very nice. one thing that just occurred to me is earlier in the call, I was talking about having shared tokens, shared secrets in terms of one service, talking to another service, but we're also talking about email or. And you can almost think of email, like a service that calls back into your own system, because you might send out an email that contains links that have signed URLs somewhere inside of them.

[00:36:56] **Ben:** That then have to call back to your system. And that sign URL has to be validated. So if you were to, rotate a token that was used to sign an email that is now living in the wild in someone's email, client inbox. You would break their ability to use that URL, unless you had some sort of window of backwards compatibility for those kinds of tokens.

[00:37:19] **Ben:** So you're like, a token will exist for at least two weeks or something before it gets deep provisioned. That way any email that's gone out that has a signed URL that calls back into our system would continue to work.

[00:37:28] **Adam:** Yeah, we don't do a whole lot with sign URLs, but we do, send emails with like coded links. Right. You're sending an email. You want to be able to track when somebody clicks on a link. So that link basically has to work in perpetuity or have a decent fallback. and that is a particular, it's not that difficult of a challenge to solve, but it just results in a good amount of cruft and just unhappiness in, in my, database.

[00:37:53] **Ben:** Yeah. Yeah. I mean, now that I'm thinking about it, I going back to the, what is premature optimization versus what is just the right way to do things? I almost feel like any token that gets used to generate a value that leaves the boundaries of your system should always have a current value in a future value, because at some point in the future, you'll have to rotate it.

[00:38:18] **Ben:** And it's nice to just have that set up and have the logic in your application. Ready to. and it's really not a lot of overhead, especially if it's very, yeah. Especially if it's a, if it's a set number it's a current and a future, not an arbitrary array. Cause you can very easily just compare two values.

[00:38:37] **Ben:** It's not an open-ended amount of information to look at. Security has been.

[00:38:43] **Adam:** Security is.

[00:38:44] **Ben:** Yeah, it's

[00:38:45] **Adam:** like it's a whole profession to itself.

## [00:38:49] Security Audits

[00:38:49] **Ben:** Well, it's really interesting too, because in things and things like the pen test, we've done, SOC audits and other various types of words are escaping me.

[00:38:59] **Adam:** That's all right. You heard the last episode, right? I spent five minutes trying to come up with the name.

[00:39:06] **Ben:** That was funny, but, what's interesting was a lot of the security stuff is that you can push back against it. it's not like a company comes to you and here's the, here's a handout of everything you need to change. It's here. All of our suggestions, some are critical. Some are mild, some are low, and then you can push back and say, yeah, this is low, but we're not going to change it for X, Y, and Z reasons.

[00:39:26] **Ben:** And you can have a negotiation essentially with the company that's going to certify. it's all very interesting. And there's

[00:39:31] **Adam:** It's not, it's almost like it's subjective. Yeah.

[00:39:33] **Ben:** yeah, there's a lot of almost like political spin that gets put on some of these things, but,

[00:39:39] **Tim:** Yeah. And the, and that's why I don't think a lot of these, these people that have been compromised, they've all had security audits. Th they, they went completely and yeah, so, and the audits only as good as the information you feed them. It's like the auditors can't look at absolutely everything. They, they ask you for proof and you give them proof. And, but then, if you don't volunteer the ugly stuff, that they're never going to see it

[00:40:02] **Adam:** Yeah. I mean, an acceptable level of risk is I'm sure a phrase that gets tossed around a lot in those conversations.

[00:40:08] **Tim:** Yeah, for sure. So it's like, for instance, I don't know if I brought this up before, so like, we deal with a very big bank. I don't want to give their name out, but you know, their initials are WF and,they deal with credit cards and they do not do a PCI. They D they don't do PCI audits.

[00:40:24] **Tim:** You ask them for one, they refuse to give it to you. And, but they do. So what's interesting about that is according to the PCI, DSS audit. There's two things you have to know. You have to know what is their current PCI status. And so if they don't have one, you're like, well, their status is none.

[00:40:40] **Tim:** And then the second question is, do they acknowledge responsibility for the card holder information while it's in their possession? And they'll do that. They'll say, yeah, well, we, we do our own thing. It's a, it's even better than PCI. They say. And so they say, yeah, we may take responsibility so you can pass

[00:40:58] **Adam:** We've got this guy, Carl in the back

[00:40:59] **Tim:** Yeah. Everyone else in the world, I've got I've got to get, know, I need a copy of your PCI DSS, please. Like sure. Here it is. But you know, these big banks are like, Nope.

[00:41:07] **Adam:** Yep. Carl said it's okay.

[00:41:09] **Tim:** Yeah. Carl said

[00:41:09] **Tim:** he, I cross it out as we go. We even like list how long, we've been in business 180 years or whatever it's been.

[00:41:16] **Tim:** And, we have our own series of procedures that we follow that, secure the card information while it's in are like, okay, well I just pass the PCI. They're on my side. Cause you acknowledge it, you handle it, but you, your status is fail. So, and that's what.

[00:41:31] **Adam:** Is it though.

[00:41:33] **Tim:** I know, I don't think so. Particularly since, the years ago I saw visa was like storing their backups and all the credit card members was like, we're just in plain text, stored on an, on a drive. Someone dug it out. This is probably like 10 years ago. I hope they got better since then.

[00:41:50] **Tim:** Congratulations. Shatner, who finally went to space,

[00:41:52] **Carol:** Did it happen?

[00:41:52] **Tim:** Kirk.

[00:41:53] **Adam:** Yeah. Yo man, he was speechless when he came down. He ate, well, I don't know. I mean, he normally kind of talks that way. Doesn't he? Very stunted speed.

[00:42:03] **Tim:** I don't know, his Photoshop is hot pitcher holding up a little sign, a little piece of paper that says, suck it Picard.

[00:42:09] **Adam:** Oh,

[00:42:09] **Ben:** So fast.

[00:42:11] **Adam:** I did not see that.

## [00:42:12] Patreon

[00:42:12] **Adam:** Okay. Well, this is the part of the episode where I tell you that a working code was brought to you by 36 poop emojis. Definitely not the password to my email account. And listeners like you, if you like what we're doing here, you might want to consider supporting us on Patreon. And you can do that at patreon.com/WorkingCodePod.

[00:42:32] **Adam:** If you didn't already know, first of all, congratulations on being one of today's lucky 10002nd Patreon is a way where you can kick in a few dollars a month to support the things that you like. And it helps keep the lights on around. the entry-level tier starts at just $4 a month for us and all patrons get the after show and early access to new episodes as soon as they're ready.

[00:42:52] **Adam:** And we also host the occasional game night where we get together on video chat and play all kinds of different games with each other. of course we need to thank our top patrons, Monte and Peter. So thank you guys so much for your support

## [00:43:02] Thanks For Listening!

[00:43:02] **Adam:** and if patronizing podcast, isn't your thing. No worries. Just like Tim and Ted lasso with their haters.

[00:43:08] **Tim:** That's

[00:43:09] **Carol:** Yeah.

[00:43:09] **Adam:** if you enjoyed this episode, you should post about it on your social media of choice, those word of mouth referrals help more than you might think. Or you can leave us a rating and review on apple podcasts or wherever you get your pod. please send us your questions and your show topics on Twitter or Instagram @WorkingCodePod.

[00:43:24] **Adam:** Or leave us a message at 512-253-2633 that's 512-253-CODE or join our Discord, which is now public and share your ideas there. You can find the link to join our Discord at workingcode.dev/discord.

[00:43:38] **Tim:** come during the party eyes?

[00:43:40] **Adam:** we'll catch you next week and until then,

[00:43:43] **Tim:** Remember your heart matters. Even if it's an environment variable.
