---
title: "015: Potluck #1"
description: "This week, we're trying something new: each host has brought with them a topic for the crew to discuss."
date: 2021-03-24
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/015-potluck-1/id1544142288?i=1000514205704"></iframe>

This week, we're trying something new: each host has brought with them a topic for the crew to discuss. Topics range from considerations about data-context; what does and _does not_ make for a good manager; code that we're proud to have written; and, what it looks like when a team develops a strong bias for action. One particularly thought-provoking matter is the fact that 20% of Tim's clients prefer to make payments over the phone even when given a web-based option. This is a great reminder of the "bubble" that we can live in, often forgetting that what seems like an odd, archaic choice to us can actually be the "preferred choice" for others.

### Triumphs &amp; Failures

- **Adam's Triumph** - His desk is normally an obstacle course of empty Mountain Dew cans, thumb drives, pens, papers, and whatever else piles up and refuses to be thrown away over time. But, he finally cleaned up his office and even _vacuumed the floor_. And, heck if it doesn't feel good; well, at least for the next 6-hours.

- **Ben's Triumph** - He fixed some bugs! On a small team, there's always a _tension_ between new feature development and fixing bugs. And, unfortunately, building the "newness" tends to win out. In the last few weeks, however, he's really focused on allocating time to grooming the backlog and fixing long-standing issues, each one of which represents a real user that's experiencing real frictions.

- **Carol's Triumph** - Her communication style can be a bit too curt. In a professional setting, she tends not to mince her words, which can ruffle feathers. Lately, however, she's been making an effort to "people" better, pushing back against inaccuracies with _questions_ instead of just showing people where they went wrong.

- **Tim's Triumph** - Building a successful software product is far more than just _writing the code_. As Tim puts it, you have to be a "bridge builder". Which means, spending time getting everyone else on board: finance, legal, engineers, and the leadership within the corporate hierarchy. Everyone needs to understand why something is being created; and, why it's worth the time, money, and investment. Historically, Tim has not felt very effective at this consensus building. But lately, he's been really crushing it. He can't share too many details at the moment; but, when the time comes, we won't be able to shut-him-up!

### Notes &amp; Links

- [Girls Who Code](https://girlswhocode.com/) - an organization focused on building the world's largest pipeline of future female engineers.
- [Go Time podcast](https://changelog.com/gotime) - a Changelog podcast focused on Golang.
- [BFF: Backends For Frontends](https://samnewman.io/patterns/architectural/bff/) - an architectural pattern in which backend APIs are built for specific frontend clients.
- [Tef: Write code that's easy to delete](https://programmingisterrible.com/post/139222674273/how-to-write-disposable-code-in-large-systems) - an article espousing the virtues of code that is written to be deleted.
- [Ward Bell](https://wardbell.me/) - co-host of the [Web Rush podcast](https://webrush.io/).
- Dark Matter Developers - the quiet majority of engineers that do their job but don't necessarily participate in the greater web development community.
- IGROW - Issue, Goal, Reality, Options, Way Forward: a model for mentoring and coaching.

Follow the show! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/015-potluck-1.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** I thought it would be kind of funny to have one of you guys, like, if you guys were to record without me, I'm curious to hear how that would sound. The intro and outro. Is

[00:00:07] **Carol:** it weird I actually thought about that? I was like, oh crap, we need to go back to listen to, like, everything Adam says, because all we do is just mock him when he's trying to

[00:00:14] **Adam:** do it.

[00:00:14] **Adam:** I

[00:00:16] **Ben:** wouldn't say that we mock.

[00:00:19] **Adam:** You just take shade and fruit in my suffering. That's Schoenfreude, that's exactly it. We're laughing with you.

[00:00:38] **Adam:** Okay, well, here we go.

[00:00:39] **Adam:** It is show number 15 for March the 24th and on today's show, we're going to have a potluck of topics. But first let's get to our triumphs and fails. And Tim, I'm coming to you first. What do you got? Okay,

[00:00:49] **Tim:** well, um, so I've been thinking a lot about. In coding, and not just necessarily coding as the act of coding, but the act of building software, how important it is to learn to be a bridge builder in championing your software.

[00:01:07] **Tim:** And let me, let me tell you what I'm talking about. So a lot of times, The features, first, the thing you want to build, you have to champion, right? So a lot of times my job is to be a product owner of a product. And so you have to A, justify its existence and that requires bridge building or B, explain why things need to be in it that other people might not believe belongs in it.

[00:01:35] **Tim:** And I've been doing a lot of bridge building lately. And that doesn't mean working on the product, that means building consensus with other people to explain why having this product and having the features in the product are important to them and their job and to the customers ultimately. And that's a lot harder than, uh, than you might think.

[00:01:58] **Tim:** And it's not something I'm always good at. Sometimes I'm like, obviously we should do this. Duh. Million dollar idea. Come on. Data? We don't need data. You know, why would you be concerned about that? So trying to look at your product through the eyes of not just necessarily the end user, but any person who's a stakeholder in it.

[00:02:21] **Tim:** And I feel good because I feel I've been doing that involving finance, involving legal, involving, you know, if you have like some corporate hierarchy that they might not fully understand how it could benefit them, just involving all the parties and Being a cheerleader for your product so that it can get built and get built right.

[00:02:43] **Tim:** So that's my trial. I can't be more specific than that, unfortunately, but, um. Yeah, I've been doing a lot of that. It's not something I've done well in the past. So I'm proud of myself for making the effort and, uh, I think I'm gonna get it done. We'll see. End results will tell the tale.

[00:03:02] **Carol:** When the end results are in, can you tell us more?

[00:03:04] **Carol:** Oh

[00:03:05] **Tim:** yeah, definitely. Sweet. You won't be able to stop me. I

[00:03:09] **Adam:** think maybe you can give us some, some juicy details for the after

[00:03:12] **Tim:** show. No.

[00:03:16] **Adam:** It's super secret. It's not exactly where I thought you were going with the building bridges thing. There was a, I wish I could find it. I did a quick search here and I can't find it.

[00:03:26] **Adam:** Um, there was a conference presentation that I saw and I want to say it was something like build as you climb. And the idea was like, you have to, when you're blazing new ground as a coder, when you're going somewhere that somebody hasn't been before. It's difficult, but if you, like, build bridges over those ravines as you're going through there and you make it easier for the person that comes behind you, then they can go farther than you, because they don't have to stop and build that bridge for themselves to get across.

[00:03:52] **Adam:** That's beautiful. Yeah, that is,

[00:03:54] **Tim:** that's, that's, I didn't think about that, but yeah, from an architectural standpoint, that, that is definitely, you gotta do that. But I'm thinking more just sort of getting a project off the ground. Right. Even before you hire a team of coders or, you know, join a team of coders, somebody laid the groundwork for you to get that built to even us to say that it is a worthwhile endeavor.

[00:04:15] **Tim:** Um, and, and that's, that's hard because it takes a technical skill to know that it can be done and it takes. Sort of an interpersonal skill to be able to, to sell it.

[00:04:25] **Adam:** Right. I think I was actually kind of mixing two phrases there. So there was the, the building bridges thing, but then the phrase I was thinking of was lift as you climb, like help other people up as you're improving your.

[00:04:36] **Carol:** Well, I liked your first one better. I mean, let's just go with it.

[00:04:40] **Ben:** One of my teammates, Sean, he likes to say the phrase. We'll burn that bridge when we're standing on it.

[00:04:47] **Adam:** I have heard

[00:04:48] **Carol:** that one before.

[00:04:49] **Adam:** That's

[00:04:49] **Tim:** a tomorrow me problem. Yeah. How about you, Carol? How has your

[00:04:55] **Adam:** week been? Oh,

[00:04:56] **Carol:** I've had a crazy week, but we won't go into that.

[00:04:59] **Carol:** Um, so I feel like I have a triumph over a failure or maybe a triumph from a personal failure of mine. I tend to be, um, a bit aggressive with people and can sometimes be a jerk. And, uh, yeah, you would never know it. I'm so sweet and southern and you just don't

[00:05:17] **Tim:** expect it, right? I don't. You've never been mean to

[00:05:20] **Carol:** me.

[00:05:20] **Carol:** Oh, you should put a pull request in to me or you should, you know, ask me for help on something that you've done terribly and me not be sarcastic about it. So I have, um, I've been doing a pretty good job at biting my tongue. And thinking through what I want to say before I say it. Because I'm working with people who don't know me, who don't know that when I say something, it's just very quick and very, yes, no, here it is.

[00:05:49] **Carol:** As a matter of fact, it was this, it wasn't this. And it tends to come across wrong. So I'm just, I'm doing a really good job at not needing to have the last word and just not being a jerk overall and kind of being a nice person.

[00:06:03] **Adam:** Which is such a huge change for you.

[00:06:05] **Carol:** Yeah, if you knew some of the things that I've said to people, you'd be like, damn.

[00:06:15] **Tim:** I don't want to be a jerk here on this one. Be a jerk, go ahead. Can I push back and say, let me ask, if you were a dude, doing the exact same things you're doing, do you think you would People will be considering you a jerk. If they

[00:06:31] **Carol:** were doing it to other men, no. If they were saying it to me, yes.

[00:06:38] **Tim:** So I, I

[00:06:39] **Carol:** don't follow.

[00:06:40] **Carol:** So like, if you, if some of the things I said, you said to Ben, no one would think a thing about it. If some of the things you said to Ben, you said to me, people would probably be like, Tim, you can't say that. So for me, maybe I'm saying it wrong, but for me, if I say it to Ben, it's fine. If you say it to Ben, it's fine.

[00:06:58] **Carol:** But if you say it to me, it's not okay.

[00:07:00] **Tim:** But you're the one saying it,

[00:07:02] **Carol:** so... Yeah, but I'm trying to not be that way. I'm trying to be nicer about things. So I'm like, hey, here is what is actually happening. And then the conversation goes, no, that's not really what it is. And I take a second, and I go, well... Here's everything I found.

[00:07:17] **Carol:** Do you mind taking a look at it? Which then turns into, okay, yeah, you're right. Where before I would have just been like, You're completely wrong. Here's the stuff I'm looking at. Like, Go figure this out yourself then, if you don't want to listen to me. Hmm. So, I'm just trying to be nice with my words. And I'm winning.

[00:07:33] **Carol:** Don't make me feel like not a winner, Tim.

[00:07:35] **Tim:** No, I'm not. I'm not. I just, I, I feel like there might be some sexual bias from the people you're talking to.

[00:07:42] **Carol:** It's, it's probably more me than from them. But isn't, I mean. I am probably overthinking it. Then they're not probably, I don't know, actually some of them did get offended.

[00:07:55] **Carol:** So yeah, it's probably both

[00:07:56] ways.

[00:07:56] **Adam:** I was

[00:07:59] **Ben:** listening on a podcast just recently and I, I cannot for the life of me remember what it was, but in it, they were saying that. People are not opposed to change, people are opposed to being told what to do. Oh yeah. And I think when you can pose things as informational, as opposed to, uh, telling them how something should be done, then I think they're much more likely to embrace it and then, and then use the changes you're suggesting.

[00:08:27] **Ben:** Hmm.

[00:08:29] **Tim:** That's a good point. Yeah. That

[00:08:30] **Adam:** makes sense.

[00:08:31] **Ben:** Which is, which is always how I feel about

[00:08:37] **Adam:** linting.

[00:08:38] **Ben:** I feel like if you can write code and that code can be beautiful and then someone else sees that code, they'll want to change just from having seen it. But if you make them follow a linter, I feel like that's like telling them what they have to do and they're going to, there's going to be a natural pushback.

[00:08:57] **Ben:** But I also find that sometimes you show people beautiful code and they don't care one way or the other. Yeah, yeah. They don't,

[00:09:02] **Carol:** I don't understand how you don't care. That's, that blows my mind. I need it to look pretty and function.

[00:09:08] **Adam:** I don't think I've ever seen code that was so beautiful. It like made me cry.

[00:09:11] **Adam:** but . But like there's been code that I was like, okay, yeah, this is, this is like super clean code. I've seen code. That's so bad. Bad cry. I aspire to that clean cry. Yeah. Oh God. Yeah. I've written code that's so bad. It made me cry.

[00:09:24] **Carol:** Like, when you have to open the file and format it before you can just do a code review on it, it's a bad day.

[00:09:29] **Carol:** It's not a good

[00:09:30] **Tim:** day. You look at it, you're like, no, I can't, I can't, we

[00:09:32] **Adam:** gotta Like,

[00:09:33] **Carol:** my brain can't even comprehend what it's doing because it's formatted so bad. Alright, that's me. That was mine. How about you, Ben?

[00:09:42] **Ben:** So, I fixed some bugs this week, which is Seems like something you should just be doing on an ongoing basis, but I'm on a very small team and there's always this natural tension between doing feature development, new feature development on one hand, and then going back and actually fixing things that are broken on the other hand.

[00:10:03] **Ben:** And it's typically easier to motivate, to build the newness. And it's much harder to motivate to go back and fix the things that are broken. Um, but I actually just set aside a bunch of time to go through our backlog and pick out some tickets and, uh, it was super satisfying and, uh, it, it's fulfilling in a different sort of way than it is to do a feature development.

[00:10:29] **Ben:** Bug fixes to me are much more about. Kind of user connection and user empathy and understanding that every bug is causing somebody somewhere some degree of friction and fixing that bug is making their life just, you know, some percentage

[00:10:43] **Tim:** better. So these are bugs. These are not to dos in the code, right?

[00:10:47] **Ben:** Correct. These are tickets that the support team has filed in our backlog. So they're associated with, uh, we use Zendesk as our customer support ticketing system. And then the engineers use Jira. So essentially the support team sees people filing stuff in Zendesk. They then create Jira tickets and associate the two together.

[00:11:08] **Ben:** And then when we close out our Jira tickets, it automatically notifies them to go check on, uh, the Zendesk incidents and then potentially communicate back to users that things have been fixed.

[00:11:19] **Adam:** We had

[00:11:19] **Tim:** the same setup. Yeah, I'm just ashamed by the number of to dos in my code that are dated, like, five years ago.

[00:11:26] **Tim:** And I still haven't done them.

[00:11:27] **Ben:** I do have a to do that's, that's literally five years old.

[00:11:30] **Adam:** But you know what? Like, I would say that's a good thing, right? You thought it was going to be necessary, but you've made it this far without it. Like, what does it matter?

[00:11:39] **Tim:** That's true. It's a bit of technical debt. It's like, you really should refactor that function.

[00:11:43] **Tim:** But you know what? I guess it depends on what the to do

[00:11:44] **Adam:** is. I don't want to

[00:11:45] **Tim:** create a bug. I don't want to create a bug. So, let's just leave, let sleeping dogs lie. Right.

[00:11:51] **Adam:** If it's, if it's like, oh, add this polish, add this new little micro feature, then that's probably not worth the effort at this point, but.

[00:11:58] **Adam:** If it, if it's a big refactor that will make things easier or cleaner or whatever, then that might be worth it. My

[00:12:03] **Tim:** pet peeve is, is nested ifs. If I ever see a nested, if I wanna go rewrite it every single time into a function,

[00:12:09] **Adam:** I, I just think everything should be nested. Aries

[00:12:14] **Ben:** I, I was listening to the the Go L podcast, uh, go time the other day. And they were talking about idiomatic code, which brings us back to our other episode, but, but they did mention something that I've always used as a rule of thumb, and I didn't realize that other people think about this. In Golang, apparently, the idiomatic approach is that the primary workflow is supposed to be on the left, and any exceptions are supposed to be tabbed in.

[00:12:39] **Ben:** So, instead of having something like nested ifs, and I don't know what the particular use case for a nested if is, but instead of having something like nested ifs, I think in Golang, they would have one if that was an exception case, and then maybe would return out, and then you come back to the first tab, and then maybe you have a second if.

[00:12:55] **Ben:** So they do a lot of guard statements. I, I, from what I understand in the podcast, which I've, I'm a huge fan of guard statements.

[00:13:03] **Adam:** Yeah. All day. That's interesting. I, I would, I've not taken the opportunity to look at any Go source code yet, but it sounds really interesting. And, uh, you know, I know it's got a lot of fans.

[00:13:15] **Adam:** And just things like that, talking about moving the exceptions off to the side, that just, it sounds bizarre to me. Like for me, code is a very vertical thing. So to talk about moving something off to the side, I can't quite picture it, but um, it makes me more interested to check it out. Well, how about you, Adam?

[00:13:31] **Adam:** What do you got going on? Um, I have a triumph. I am not a like a neat person. Uh, I'm a little bit of a pack rat, and you know, I see those pictures that people post of their super minimalist desk with like one monitor, keyboard, mouse, and like a glass of water or something. I'm like, man, that looks. Awesome.

[00:13:51] **Adam:** And meanwhile, I've got like three different pairs of headphones and chapstick and I have a tape measure here on my desk and, um, you know, a couple of glasses of water, a couple of pens, you know, like a box of tissues, some old credit cards, some coupons. Tin cans. Um, I'm just not, I'm not a minimalist, right?

[00:14:09] **Adam:** As much as I would love to be, I'm not, I can't do it. I've got a Google home and I've got a, like a little stack of. Thumb drives and crap over here. It's just, it's not me as much as I would love to be. And so, but like, one of the things that I did today, uh, was I cleaned my office, uh, including I vacuumed the floor, which it just feels good.

[00:14:32] **Tim:** I feel personally attacked by what you just said. Cause my desk is, I should send you a picture. It's a mess of... Yeah. Post it notes, notebooks, and family feud cards, and seed packages, and... Seeds, oh

[00:14:46] **Carol:** yeah, for gardening.

[00:14:47] **Adam:** And scobies. No scobies,

[00:14:50] **Tim:** that's pretty gross.

[00:14:54] **Adam:** I have little 3D printed things, and remote controls for the fire stick in my office, and notebooks, and yeah, it's awful.

[00:15:00] **Adam:** Um, but today I took some time, I cleaned my office. For the next, like, six hours, it will be nice in here.

[00:15:09] **Tim:** Exactly.

[00:15:10] **Carol:** I like that you said that, but you're picking up these things that are still cluttering your desk.

[00:15:15] **Adam:** Well, yeah, I mean there's... Clean enough, I mean, it never gets to that, like, minimalist, like, Instagram worthy desk picture.

[00:15:24] **Adam:** I've got battery chargers and a USB hub, and it's just, like, why, why, and I, my desk doesn't have drawers or anything, so I have to, like, put it

[00:15:32] **Carol:** all away. I was gonna say, we have sanding desk. Yeah. Yeah, I'm like, you have a standing desk, so I had to, I bought a little, like. Carriage thing. I don't even know what it is.

[00:15:40] **Carol:** It's like metal baskets from Ikea. And they stand next to my desk. And that's where I kind of put the junk at. Yeah. The things I kind of want to keep around, but don't want in between me and the monitor. Yeah.

[00:15:52] **Adam:** I need to get something like that. The, the, the standing desk setup is still relatively new here for me.

[00:15:56] **Adam:** So.

[00:15:57] **Tim:** So, so let me ask you, when you clean, do you actually just like, Organize everything and put it in the right place or you just go, you know what, it's been sitting here forever, I'm just gonna throw it away.

[00:16:07] **Adam:** Things that should be thrown away, I throw away. Good. I, so I'm like, I'm, I'm the type of person, I use something and then I set it down where I am and if I don't need it again for six weeks, then it stays where I set it down for six weeks until I need it and then I go get it and I move it to where I need it and I leave it there for six weeks.

[00:16:24] **Adam:** Um, I'm sure it drives my wife nuts. It would

[00:16:27] **Carol:** drive me crazy.

[00:16:29] **Tim:** Yeah, I'm just to throw it all away. So

[00:16:31] **Adam:** this is, but I only do this in like my personal spaces. Like my little corner of our bedroom is like, you know, the, the three different pairs of shoes I've been wearing for the last two weeks. And you know, a sweatshirt that I'm re wearing or whatever.

[00:16:43] **Adam:** And like my nightstand has a bunch of junk on it. I have like 20 different chapsticks on my nightstand. And yeah, I mean, it's just, I, I am not a neat, like put everything away all the time person. And, um, I wish I were, but I'm not. And, and so yeah, I declutter, but it never gets down to like perfect. Yeah. I wish I was cleaner.

[00:17:06] **Adam:** I feel good. I feel good about the amount of cleaning that I did today. Nice. Good job. All right. Well, are we ready to move on? Let's roll. Cool. Yeah. The idea for this week's episode was a potluck where basically we're each just going to bring something to the table and we'll share it around and see where it goes.

[00:17:22] **Adam:** Have some

[00:17:22] **Carol:** fun. You may all get baked beans. Because we didn't coordinate what

[00:17:26] we

[00:17:26] **Adam:** were bringing. Yeah, we all brought potato salad. Alright, who wants to bring your potluck topic up first?

[00:17:33] **Carol:** It

[00:17:33] **Adam:** was just going to order as I written. Okay, well Tim, you're

[00:17:36] **Tim:** up first. Alright, so I actually may be the potato salad person here in this potluck with, like, raisins and other unnecessary things in it.

[00:17:46] **Tim:** Apples. Karen's potluck potato salad. So, it's been bouncing around in my head, the importance of context for data. And I don't know how people will take that phrase, but let me explain to you. What I'm talking about. So I'm currently working with a team. I I've built an API that is an API layer to pull data from a system and they're using it to build several things, a mobile app, a web portal, and I'm using it also in addition to build an, an interactive voice, uh, system.

[00:18:21] **Tim:** And it just amazes me that how people consume their data. It's all the same data, honestly. It's using the same. API, right? They wrote an API because it like takes a bunch of disparate systems, creates a uniform interface to get data out of them so you can present basic information about an insurance policy and to make payments on it.

[00:18:45] **Tim:** And it's just, it's just, it strikes me as interesting that I've learned a lot because I've used it for a while just to feed an IVR system, you know, where you call in and you, And it still amazes me that people use IVRs, like 20% of our, uh, of our customers, clients use the IVR to make payments instead of the web.

[00:19:07] **Tim:** So what is

[00:19:08] **Adam:** IVR? Yeah, you

[00:19:09] **Tim:** need to explain that. IVR is interactive voice system. So you know when you call a phone number and they say, you know, press two to make a payment and you go to click two and it's like, you have to do, do, do, do, do, do, do, do on your phone. You punch in the, you know, your information and then it'll say, Hello, Adam Tuttle.

[00:19:27] **Tim:** Your balance due is 55. 95. To make a payment, press one. It's Tim's

[00:19:35] **Carol:** voice too on the system. Yeah.

[00:19:37] **Tim:** To make a payment by bank. Press 2, you know, anyway, so, and a surprisingly large number of people still use that as a way to make payments. Like in

[00:19:48] **Carol:** place of like an online click a button.

[00:19:50] **Tim:** Right, they have the options, they have the options of a mobile app, they have the options of just going online on a desktop computer or, you know, a web interface on your phone, but like 20% of these people And I don't know what the, I don't, I'd love to figure out what their ages are, or what their background is, but it's like 20% of people choose to call a phone number with their phone and press on a keypad to make a payment, uh, and to look up information about their policy.

[00:20:20] **Tim:** And so, it got me thinking a lot about the importance of, of how you deliver data for the context it's going to be used in. Because an IVR system, an interactive voice system, you want. To pretty much do the work for you, whereas like a web system, you can do, you have a lot more, you have a lot more flexibility.

[00:20:42] **Tim:** You can get some data and infer things from it using code. So, I don't know, it just, I just find it interesting that the context in which you choose to receive your information.

[00:20:59] **Adam:** So this is probably what you wanted to talk about with this topic, but two things immediately come to mind for me. The first is that, like you said, this IVR stuff is really commonplace and probably doesn't feel like it's going away anytime soon. And I think the reason for that, or one reason for that, is that it's much more accessible to people who don't have smartphones, maybe not have internet service at home, that sort of thing.

[00:21:22] **Adam:** So, um, you know, lower income people, whatever, can, can use a system like that. And the other thing is I absolutely hate with Every fiber of my being, multiplied by the nuclear power in every star in our galaxy. Telephone systems that require me to speak to them. I will use the push buttons all day long, but the moment it's like, please say, it doesn't matter what you're asking me to say, you say, please say, and my, my blood pressure just goes instantly.

[00:21:57] **Adam:** You know, my steam starts coming out my ears.

[00:22:00] **Ben:** Operator. Operator.

[00:22:03] **Adam:** Yeah, yeah. It's just, because, uh, like, chances of it misinterpreting me punching a button are very low. Chances of it misinterpreting me, uh, saying something, or if I have to cough or sneeze or somebody knocks on my door while I'm trying to do this, like, those are all things that are very common and mess that system up.

[00:22:24] **Adam:** And I

[00:22:25] **Tim:** hate them. I'm with you. I'm so glad you said that. Thank you. Honestly, I, because it's like, I had the option to build that in. I always try to steer our customers away from it because of what you just said. And they think, oh, that is so cool. You can talk and it replies, but it's not a conversation. No.

[00:22:43] **Tim:** And it's

[00:22:44] **Adam:** like slow,

[00:22:45] **Tim:** right? It is slow. I

[00:22:46] **Adam:** mean, it, it's like trying to talk to your, your, uh, digital assistant. I'm trying not to say the name. So it doesn't go off here on me. So

[00:22:53] **Tim:** stupid walking around the committee. Cause normally you're like. Sometimes you're on the phone for a while, and it's like you're hanging on, and you're walking, you know, so you get up in your pace, and all of a sudden...

[00:23:02] **Tim:** You know, you're walking around the house silent and then it's like, yes. And then someone goes, what? No, I'm talking to the, I'm talking to the automated system. I'm sorry. I did not understand that. Could you repeat your, shut up. I wasn't talking to you. I'm sorry. I didn't understand. And the thing is, so a lot of the systems that, that have this, what, what people might not know is that that's typically a feature you turn on.

[00:23:27] **Tim:** And so you have the choice of, of dial tone, dial tone. Modulation frequency, which is whenever you press a button on a phone. That's DTMF. That's one thing you turn on. Or you can turn on, uh, voice. Or you can turn on both. But if you turn on both, it's constantly listening for voice and for dial tone. So what, what that happens is, so even you choose just, let's just turn that on and someone decides they just want to press buttons, which I do.

[00:23:57] **Tim:** I do too. I feel stupid talking to it, but if, if the developer has turned on both, then it is constantly querying your phone sound system to hear for that. And anything like a cough or anything, it could interpret that and will mess up your keystrokes and now you're having to start over. So I, every time I greatly urge people, I'm like, look, if they want to use this, it's fine.

[00:24:17] **Tim:** Do not turn on voice recognition. It is a waste of time. Not because it doesn't understand it. In a perfect environment, it does reasonably good at figuring out what you're trying to say. Provided you've, uh, and Heidi Cody is typically you, you give it hints to say, all right, here's five things I'm expecting them to say in this scenario.

[00:24:38] **Tim:** You know, I want them to say, make a payment or pay a credit card or ACA. You know, you put all the things in there and then you build responses accordingly, but still. The fact it's even listening at the time can throw things out of whack and yeah, it just creates frustration. So I'm glad you said you, you, you verified my gut feel of like, don't, don't even bother turning that on.

[00:25:03] **Ben:** But going back to the idea of context for data, and I don't know if this is gonna be meaningful at all, but in, uh, in terms of software patterns, there's a pattern called the BFF, the back end for front end, which is where. You essentially have a backend that's tailor made for a specific type of client. So you might have a backend that's tailor made for a mobile device, and a backend that's tailor made for an IVR system, or a backend that's tailor made for web interactions.

[00:25:33] **Ben:** And then those BFFs, those backend for frontends, their whole responsibility is to aggregate calls to other systems. So that they can deliver data as efficiently as possible to the targeted client.

[00:25:46] **Tim:** That's cool. Yeah, now that you say that, I should have done that.

[00:25:50] **Ben:** Yeah. Well, it sounded a little bit like that's what you were building, which

[00:25:53] **Tim:** is what made me think of it.

[00:25:54] **Tim:** It's not. They're using the same, they're using the same API, and I'm not tailoring it based off the context it's coming in at. So there's so much overlap in these contexts that we're doing. I mean, they're seriously bringing in the same stuff that I just, if there's like something. that the, the IVR needs that the, um, the web or the mobile doesn't.

[00:26:18] **Tim:** I'll just add an extra data point inside the same node that that will use. And is it adding some bytes to the, to the communication? Yeah. Is it, is it going to be detrimental to the overall functioning of the program? I don't think so. Probably not. So if, if it got to the point where the data needs to be presented in a much different way, then yeah, I would, I would basically.

[00:26:44] **Tim:** Create different, um, different endpoints, or even, you

[00:26:48] **Ben:** know... Different endpoints is my personal... Move of choice. I find that to be super, super just really easy to maintain and to think about over time.

[00:27:00] **Tim:** Or, or the same end point with a different flag to say the context that it's coming from, right? So it's this, it's the, the.

[00:27:08] **Tim:** What is my, what is my payment do now? And then one of the flag is, you know, it's IVR or the flag is it's mobile. So that way it builds the response specifically for that one to give it only what it needs. Very great. I got to go read, I got to refactor now, Ben. Thanks.

[00:27:26] **Ben:** Well, I read an article maybe like, I want to say two years ago, and it really, really changed the way that I thought about how I wired things together.

[00:27:35] **Ben:** And historically, when I think about clean code, it's, it's typically about how can I make this code easy to maintain over time? But this one article posited this idea that if you make code easy to delete, then it will inherently be easy to maintain because making code that's easy to delete is code that is not tightly coupled to a lot of other things, which as a by product, I think tends to make it easy to maintain.

[00:28:01] **Ben:** So when we talk about Two endpoints versus one endpoint that has a special flag. I think to myself, if I wanted to delete one of those client pathways, now I'd have to understand how that flag works and I have to make sure no one else is using it. Whereas if it was a dedicated endpoint just for this API, I'm like, I'm just deleting that whole controller or whatever, you know, however it gets implemented.

[00:28:24] **Adam:** That's also kind of the, one of the primary justifications that I've seen and the one that I like for the whole CSS and JS movement. Keeping your style with the component that it's styling, so that when you're done with the component, you can throw the CSS away, too.

[00:28:38] **Carol:** It all stays together. And your testability to you, so when there's a failure, you have one to go to.

[00:28:43] **Carol:** You're not wondering if it's everywhere or you're not debugging as deep.

[00:28:47] **Tim:** Yeah, that's a good point. Thanks man, I'll take that

[00:28:49] **Adam:** on. I've been sitting here thinking, uh, IVR, like what else could it stand for that kind of goes back to that whole... The other thing, and I know that it's the other system, but the best I've come up with is infuriating voice recognition.

[00:29:05] **Adam:** Anyway, um, yeah, so the, before we leave this topic, uh, I feel like I might as well share this because I've had this idea. For a conference topic rattling around my brain for probably the last 10 years, and it's I've never been able to do anything other than, like, come up with sort of the concept and the title the title for the presentation.

[00:29:24] **Adam:** Would be, please listen carefully as our menu options have changed. And the, the idea is like thinking about usability and user experience from the perspective of the long term, right? Like, yes, this is new today, but is the recording going to change in five years when the menu options haven't changed recently sort of thing?

[00:29:49] **Adam:** Anyway, so anybody can have that. You can take the topic and run with it. Just, you know, maybe please credit the podcast and tell people they should listen to us. That's a good

[00:29:57] **Tim:** point because like so many times you, you know, that, that, that little caveat, the beginning has been there for years and it hasn't changed anything.

[00:30:07] **Ben:** Before we move on, I did just want to mention one thing that Tim's conversation made me think of, which is that I think as developers, we tend to live in this. And not even, let me rephrase, not even just developers, but developers who are, let's say, actively engaged in community facing things of some sort or another, that I think there are things that we take for granted, take for granted is wrong, there are things that we make assumptions about, like who would use a voice interactive system when you could just use A web payment system.

[00:30:42] **Ben:** Right. And we forget, um, uh, Ward Bell on the Adventures in Angular podcast, which is now, I think, WebRush, he used to say that there are, he called these dark matter developers, that there are these hordes of developers out there that don't go to conferences and don't participate in web forums and don't participate on Twitter and they just go and they get their jobs done, they work.

[00:31:05] **Ben:** You know, maybe in giant enterprise systems or so on and so forth. I guess it just is a reminder that there's so much out there that is not the kind of stuff that we do. I think about using Chrome browser. I'm like, I use Chrome. Why would it, to me, it's, it's such a fast, easy to use browser that I can't imagine anyone in the world ever uses Safari anymore.

[00:31:28] **Ben:** And then I watch people use Safari all the time.

[00:31:31] **Adam:** Do you hate yourself or?

[00:31:35] **Carol:** I forget. There is another browser.

[00:31:38] **Adam:** Is

[00:31:38] **Tim:** it iOS Safari or is it just. No, people,

[00:31:41] **Ben:** people like to opt into desktop Safari and they really like it. And I. And I'm not saying that they're wrong. I'm saying that I live in this little bubble where I have Chrome DevTools open all the time

[00:31:53] **Adam:** and that's my world.

[00:31:55] **Adam:** Safari is kind of the new IE. So in that sense, they're wrong.

[00:32:00] **Carol:** So I do use Mozilla on my phone. Firefox? Firefox. Yeah. I guess it's Firefox now, huh? So,

[00:32:09] **Adam:** I really, truly believe in the mission of Firefox and every now and then, maybe once or twice a year, I get a little bee in my bonnet about switching my primary browser to be Firefox and at least for like my personal usage and if I still want to use Chrome for development then I'll do that.

[00:32:26] **Adam:** And every time I do it. It's like two weeks or less and I come running back to Chrome because in my experience on my machines with the websites that I'm using, it's just slow and annoying. And you know, that's a relative term, right? If 10 years ago you showed me Firefox running on my machine today, I'd be like, Oh my God, that is so fast.

[00:32:46] **Adam:** I can't believe you have performance like that. But compared to sitting right next to Chrome, it's like night and day. And see,

[00:32:52] **Carol:** I only use it on mobile. That's it. I don't use it anywhere else.

[00:32:57] **Ben:** I use, I use Firefox for my personal email so that I can have during the day, I have my personal email open in Firefox and my Trello board in Firefox.

[00:33:05] **Ben:** And then I have all my work stuff in Chrome, basically everything else in Chrome. The rest of your life. I do find that the Firefox dev tools, which I know people rave about, I find the dev tools to be very slow compared to

[00:33:18] **Adam:** the Chrome dev tools. Some of them are better, like their, their CSS grid dev tools are better than Chrome's, but, you know, there's constant, like, shifting of the scales there, goes one way, then it goes the other.

[00:33:31] **Adam:** I only

[00:33:31] **Carol:** went back because I have a, used to, not anymore, had a crush on Dan that worked there.

[00:33:39] **Tim:** He's got, you, are we leaving that in?

[00:33:41] **Carol:** Yeah, you can leave it in, I don't care, he's hot.

[00:33:45] **Adam:** Can I forward this to him?

[00:33:47] **Carol:** Okay, let's not do that. You wouldn't be creepy stalker.

[00:33:50] **Adam:** Yeah, right.

[00:33:51] **Tim:** That's cool. Yeah, but to go back to your point, yeah, I think we as devs do make a lot of assumptions about what we consider normal behavior, but we have to realize that our behavior is not normal.

[00:34:02] **Tim:** Not by any means. Because we live, you know, we are, we are the early adopters of most things. So most people are, are, they haven't caught up with that yet. And so we shouldn't assume. Absolutely. That's my potato salad. Thanks for, uh, picking out the raisins.

[00:34:20] **Adam:** All right, well, I brought the bacon wrapped bacon, so.

[00:34:22] **Adam:** What? So, my topic for the day is, what is some code that you are proud of? Something that you've written. Doesn't have to be for the web, doesn't have to, you know, just something that you're proud of. Maybe it was the first thing you wrote or, and if you guys want a minute to think about it, I can go first.

[00:34:40] **Carol:** Yeah, go ahead. You do yours first.

[00:34:41] **Adam:** It's your topic. Okay. So, the first thing, I could probably think of a bunch of different things, but the first thing that came to my mind... was an app that I wrote. It was a desktop app and it was at my first full time programming gig. It was at a franchise, Pepsi Bottler. I mentioned this on my origin story.

[00:34:59] **Adam:** And, um, basically this, the problem that I was solving was that They, they used the, they had an algorithm that they used from the local newspapers lotto numbers to determine who on the staff was getting randomly drug tested. And when you got randomly drug tested, they also went through your email and alpha, your company email and your alpha page logs.

[00:35:22] **Adam:** Alpha page? Yeah, yeah. Back in the day of like... I don't know what that is. So it was like a pager, right? Beeper. Okay. But, um, it was like, you could send a text message to it. Oh, okay. Yeah, this was like, so the tail end of beepers before smartphones really became a thing. And so they had a couple of the, the alpha pages wasn't too bad.

[00:35:41] **Adam:** That was kind of already available in a database, but the emails, the only way they had to get those was they had like, um, our, I forget the name of the system, but they had like email log files and it was just one gigantic text file with a whole bunch of emails written into it. And it had every email you had sent or received.

[00:35:58] **Adam:** And so the job that they gave me was like, okay, take these giant log files, parse out individual email messages, and store them in a Microsoft Access database. Because this was like 1990, whatever, 2009, 2002, something like that. And, you know, I was like relatively fresh out of high school. I think I was like first or second year in college.

[00:36:17] **Adam:** And so this was difficult for me in part because I was relatively new to programming. And in part because parsing email is a fool's errand, really. It is. Um, the... The problem is that there are some, I don't know if there are conflicting specs or what, but basically nobody formats their emails the same way.

[00:36:43] **Adam:** Like if you get an email from Gmail and an email from Hotmail and an email from Yahoo all sent with basically equivalent content, the formatting of the headers and the line breaks and this and that is all going to be slightly different. That's right. And so I had to write this app that would parse these giant email log files, and we're talking about like a text file that was like five gigs.

[00:37:01] **Adam:** and rip out all each individual email and send it into a database and the things that stand out in my memory about it are a that it parses these giant log files down into the database records which was kind of cool but b i did um a double progress bar right so i had a progress bar for the entire file and then above that i had a progress bar for The, or no, it was, so we had, um, it was a double progress bar, but it was like, you would give it a, a folder full of these giant files, and it was like, okay, so there are 8 files in this folder, so the pro, the bottom progress bar was like 1 through 8 or whatever, and then the top progress bar was the number of records in the current file.

[00:37:39] **Adam:** A number of lines or something like that. And you know, when you're 19, 20, something like that, this was like, I felt, obviously I feel very strongly and proud of this application, but it was, you know, it was nothing special. It was visual basic and looping over lines of text and trying to find email messages and save them in a database.

[00:37:56] **Adam:** But it stands out in my mind. It was maybe, maybe like a formative project for me.

[00:38:02] **Carol:** I wish people could see us grinning right now. I'm just like that back in the day. That's

[00:38:07] **Adam:** nice.

[00:38:08] **Ben:** Yeah. I think there is something especially satisfying about data processing. Always. Right? I mean, the vast majority of the work that I think a lot of us do is just building forms and list pages and detail pages.

[00:38:24] **Ben:** And then every now and then you get a task where you have to transform data in a very low level sort of way, and it's satisfying in a totally different part of the brain, I think.

[00:38:37] **Carol:** My favorite code I've ever written, um, was a calculator, and it doesn't sound at all complex, because it's not. It literally is just a few operators, if you think about it, with some inputs.

[00:38:48] **Carol:** Um, so if you think of something basic, just a 1 plus 1, you only need to know what input. You had an operator, another input, and then equals, or we're going to keep changing these out together. Simple, simple code, but when you're learning it, you know, it's super complex to you. Well, I realized after, you know, being in software for a couple years that this is actually a really good way to teach someone just core functionality.

[00:39:14] **Carol:** So I've taken that and put it into different steps, and I've used this numerous times with girls who code. So with the organization, so here we have a couple local schools, like high schools, that have meets. So I'll go teach a class, go in, take pizza, take snacks, um, just hang out, but it's something that they're able to learn in one, one class.

[00:39:37] **Carol:** That's awesome. You know, so one two and a half hour session, chatting, asking me about becoming a developer, asking me about what I do. I'm able to take that code and then, you know, mentor females who are trying to get into what we do. So. It's code that is something that I'm passionate about because it's able to be used as an, like an outreach.

[00:39:58] **Tim:** So. I didn't know you did that. That's awesome.

[00:40:00] **Carol:** Yeah. I love doing it. It's fun. And like I said, it's super simple. If you think of trying to teach someone something, what's a better way to teach them operators and inputs and just some core functionality than with.

[00:40:12] **Adam:** Yeah. It's totally familiar and

[00:40:16] **Ben:** relatable.

[00:40:17] **Ben:** Although when I was in high school. There was a kid, we all had TI 82s. It was like kind of the standard graphing calculator when I was in high school. And then there was this other guy who had this really specialized calculator. And I think it was all based on LISP. So you didn't do things like do one plus one and then hit equals.

[00:40:37] **Ben:** You did open parentheses plus, which was the operator and then one and one close parentheses, and it took these lists of operations and he tried to show it to me. It was the craziest thing I'd ever seen in my life. Seems like you're just making math harder

[00:40:52] **Carol:** for no reason. Yeah, let's not do that. Hard

[00:40:56] **Adam:** enough as it is.

[00:40:58] **Tim:** That's cool, Carol. I, I, so how, how did the girls that you teach that? I mean, do they take to it pretty well?

[00:41:05] **Carol:** Yeah, typically because the girls that are in this, um, are girls who want to actually go into the industry. So it's girls who are looking at colleges, who are working on projects for, um, you know, contest entries.

[00:41:19] **Carol:** They're doing a lot, actually two of the colleges here participate as well. So Merck, the Mercer Engineering Program. And, um, the Georgia Tech campus here, the, over by your office, Tim, they actually do it as well. So there's several of us who come in and speak with them. Yeah, they, they take to it really well.

[00:41:38] **Carol:** They love seeing code. You put code in front of them, and they are just in awe. Even if you're not showing them something that they're able to understand or work with, they're just kind of big eyed and enjoying it. So, whenever you give them code, and they actually get to run it on their machines and see what's going on with it.

[00:41:55] **Carol:** They just, they eat it up. They love it. Plus there's always pizza. That's

[00:41:59] **Adam:** a good thing. How old are they? They're, these are like high schoolers. Okay. They're all high schoolers. So can I

[00:42:03] **Tim:** ask, so my experience, so I've done, I, I used to be a coach and mentor for Lego first. So Lego, you basically, it's a combination of, of programming and Lego.

[00:42:15] **Tim:** Yeah, building. And what I found was it, it was really, the boys always wanted to program and it was really hard to get. The girls just kind of, I, I felt that the girls could do it better, but the boys always jumped in and said, Oh, I didn't, you know, you're doing it wrong and kind of pushed them. And, you know, the last year I did it when, cause I only did it when my, my kids were in it.

[00:42:39] **Tim:** And I told the teacher, I said, you really need to break these out to a girl's team and a boy's team. Yeah. Um, so is in your experience, Do the girls tend to do better when there's not boys around and learning in that environment to learn coding? Because I found they kind of shied away from it, or is that just my experience because of the group of kids I had?

[00:42:59] **Tim:** So, I've

[00:43:00] **Carol:** only seen them in a mixed like, I've seen myself in school and I've seen kids, like, when I was in school, so I can tell you that way as well. But as far as current. I've only seen them in classroom settings. So when I would go in and actually work with the entire classroom. Everyone was just more standoffish though there was there wasn't.

[00:43:18] **Carol:** Anyone who jumped to help other than a few kids who the teacher had already said always are doing it, you know, like the kid with the calculator, like, those super nerdy who are in all of it. Um, but so the other setting I have is all the only girl, so I don't have a good comparison. I know when I was in school, I would, I would be more standoffish.

[00:43:39] **Carol:** Because I felt like I didn't have the knowledge that everyone else did, and I would be more timid. So I didn't answer first for a while, and I would just kind of let the guys go with it, and once they started it, then I would jump in. But I was always too terrified of getting it wrong from the beginning, so I just kind of hesitated a little more.

[00:43:57] **Carol:** And I don't know if that's a guy and girl thing, or if that's just a me thing.

[00:44:00] **Adam:** It's interesting

[00:44:00] **Tim:** because there, in some of these meets, we did have only girl teams. And they did really, really well at the meet. Yeah. Uh, and so it made me, made me really think that I, you know, I hope the teacher takes my advice and make to put that extra money, you know, because it costs money to have two teams.

[00:44:17] **Tim:** So thank

[00:44:19] **Carol:** you. I know I love girls who code and I mean, I love just the whole, um, ability to have them shine through what they're

[00:44:26] **Adam:** working on. So. Have you been able to do anything with them during the pandemic? I don't know if they're doing virtual or...

[00:44:32] **Carol:** The two teachers I know weren't doing virtual much of anything right now.

[00:44:36] **Carol:** They were overwhelmed just with adjusting to life and the schedule that they had. And they were already having issues with even getting the school to approve them to have the clubs. So they haven't done anything, but I'm going to reach back out probably in the next few weeks and see what their plan is for the summer.

[00:44:50] **Carol:** Cool.

[00:44:51] **Ben:** Tim, I think you were

[00:44:52] **Tim:** going to go. So... Let me caveat why this is my favorite. Okay. So this is, I feel it's kind of a culmination of many years of learning different technologies and combining them to one thing. The end result is not, it's not a multi million dollar idea. It is strictly something that I did to please myself and for my own benefit.

[00:45:17] **Tim:** So I hate building a new machine. I hate getting a new laptop. And I hate the bloat you get whenever you start installing tons of programs. So, the last time I got a laptop, and I may have mentioned this in, in, I don't know if it was the after show or what, but, of installing everything I have to install, building all the projects that I need to build for my code.

[00:45:39] **Tim:** So, I did through a combination of PowerShell scripts, Windows command line, BoxStarter, Chocolaty, WindowsSubsystemLinux, Vagrant, just, just general install stuff. I wrote a script that I could, if I, if my laptop completely was thrown in the trash right now, I could go to one GitHub repository, run a command, and it will pull down everything I need to build a brand new laptop with everything I need to do to get started.

[00:46:11] **Tim:** To do all my IDEs, all my, my Outlook, all my, uh, Social media, things that I need installed on it. Install everything that I like, set all my settings that I like, put my, um, bookmarks back in my browser. And do a hundred percent of everything. And it's, but it, what's cool about it, it's so, it was so cross disciplinary.

[00:46:35] **Tim:** It, it, it, I'm using Linux, I'm using Windows, I'm using PowerShell, I'm using batch scripts. I'm using so many disparate things, probably, you know, 15 to 20 different Types of, uh, scripting languages and stuff, but I can run it all from one script and, and then everything that's like, not install related or, you know, I have everything in the cloud so that all my password settings, everything I need, I can go grab and pull in.

[00:47:07] **Tim:** And so that was my, that was my proudest achievement because it's like, did I have to do it? No, but you know what? It worked.

[00:47:17] **Adam:** It worked.

[00:47:18] **Carol:** I think we talked about this on our very first episode. Yeah. When, uh, Ben was talking about his triumph as he backed up his laptop, finally. Our computer, yeah. And that's

[00:47:30] **Tim:** why I scoff at backups.

[00:47:31] **Tim:** Because it's like, I don't need to back my up. Back up what? If I lose it, it's like... Honestly, a clean OS reinstall and run a command to pull out all the new programs down and get all the latest patches and do, do all that, you know, if you can just hit a button and

[00:47:50] **Adam:** build. All right. So next time I see you at a conference, I'm drop kicking your laptop.

[00:47:54] **Tim:** Now, to be fair, it's going to take about 10 hours to run. It's not

[00:47:58] **Adam:** quick, but it does

[00:47:59] **Tim:** work. I've tested it.

[00:48:01] **Adam:** Adam,

[00:48:01] **Carol:** your progress bar just got a little less fancy. I'm sorry.

[00:48:06] **Adam:** That's all right. I still feel, I, it's, it's about how you feel inside, right? And, and for me it was more, it's just a, it's a fond memory.

[00:48:14] **Adam:** Yeah.

[00:48:15] **Carol:** That's really cool. I would love to see some of that one day. Just like, see it in action maybe. Like, let's just go see it run, play something.

[00:48:23] **Adam:** I

[00:48:23] **Tim:** mean, it, it just made me proud because it used so many Different disciplines that I think a lot of people don't necessarily have. If you're like in, just in a Windows only world, you, you don't really understand all the Linux stuff that I did.

[00:48:40] **Tim:** And if you're Linux only, or, you know, even like Mac, you probably don't know the PowerShell stuff. They're also very different. But I've been exposed to them over my life and I've used them bits and pieces. And I thought, you know what? I think I have everything I need to do what I need to do right here.

[00:48:56] **Tim:** And the Vagrant stuff, you know, Vagrant for me is relatively new. And I was really amazed with all the cool stuff you could do with scripting with Vagrant to get all my, uh, virtual machine, because I do all my development inside of VM because I, I just want to. Spin up a VM that has everything set exactly the way I know it is that every time I'm not having to debug configuration setting.

[00:49:17] **Tim:** So my VMs are scripted. So I know here's how things are. And then if there's a problem in another environment, I can compare what the environment differences are. Pretty cool.

[00:49:29] **Adam:** Very cool. So Ben, what, uh, what code are you proud of? Uh, one of

[00:49:36] **Ben:** the things that I've done recently that I'm proud of because it feels very clean to me is in the software that we build at work.

[00:49:44] **Ben:** There's an enterprise context, and within that enterprise context, there's various user roles, there's an administrator, a manager, a contributor, and a reviewer. And those different roles can do different things within the application. And historically, checking permissions has been very ad hoc and repetitive, where if you're, if you need to validate that someone can do something, we have a lot of places in the code where you actually say, like, is this person a reviewer, and this is what they're trying to do, then, you know, this branch or that branch.

[00:50:14] **Ben:** And I was doing that so many times that I finally created a separate method where you can get the user's role within the company, but then it also passes back this permissions object that has pre calculated essentially all the actions you can take within the application. So if a, if a reviewer say wanted to delete a project, historically in the delete project endpoint, I'd say like, if this is an enterprise context and this user is a reviewer, then throw, you know, forbidden error.

[00:50:45] **Ben:** But now I have this method where I can say, get me this user's membership within this company, and that returns this object, and inside it has like, can create project, can delete project, can rename project, can... View private comments, that kind of stuff. So now I can just say, does this person have the can delete project property enabled and if not throw a forbidden error and it just, I'm sure people who build complex security systems, this is like, how else would you do it?

[00:51:14] **Ben:** I can't believe you copied separate checks all over the place, but, um, I don't know, it felt like I was finally able to, uh, to refactor it in a way that felt, uh, A little bit cleaner.

[00:51:25] **Adam:** Yeah. I mean, sometimes you have to do something the wrong way or a wrong way long enough to understand the problem well, to, to really come up with a good solution to that problem.

[00:51:36] **Adam:** Yeah, I agree. A

[00:51:38] **Ben:** hundred percent. And to be fair, it's not like I went back and now refactored a whole lot of other code. There's still a lot of duplication. But at least going forward, as I create new endpoints and new workflows, I have this new object I can use to simplify a lot of the permissions checks.

[00:51:54] **Ben:** Yeah. Cool. Felt very mature.

[00:51:59] **Carol:** So grown up, Ben.

[00:52:01] **Adam:** Yeah.

[00:52:04] **Adam:** All right. I guess we're up for our next, uh, potluck. That was the Bacon Wrapped Bacon. What do you got, Carol? Um,

[00:52:10] **Carol:** I'm just gonna bring some watermelon, I guess. I'm a fruit person. So I have found, um, a lot of different skills that Team leads have had that have really changed how I was able to interact with the team.

[00:52:29] **Carol:** So I've seen terrible things and I've seen great things. And I kind of just wanted to talk to you guys about some of the better things, or even some of the worst things that you've seen in, you know, in your teams, whether it was from you personally. Or from, you know, someone you're working with or just past.

[00:52:47] **Carol:** Not, I'm not talking management, I'm not talking big people at the company. I'm talking like your individual team leads, the people you're working with every day who help drive you in what you're doing. So do you mean like throw out some things or? Do you want to jump in? me an example

[00:53:01] **Tim:** of what you're thinking about?

[00:53:03] **Carol:** Yeah, so, one great thing is whenever you have a team lead that is patient and has empathy. So, to me, they know you're struggling with what you're dealing with, but they don't jump in to immediately just solve it for you. And they don't expect you to know right off the bat what's going on. They have patience.

[00:53:24] **Carol:** They either talk it through with you 10 times while you're learning and new and you're not knowing what's going on, but at the end of the day, they're supportive and will help you get to the answer if you can't get there.

[00:53:35] **Ben:** On the flip side to that a little bit, one thing that I really appreciate in a leader is.

[00:53:42] **Ben:** Ben be able to understand when the right moment is to help you grow. Yeah. Versus when, when they just need to come in and start karate chopping some stuff.

[00:53:52] **Carol:** Yeah. Like I'm done dealing with this. I'm tired of waiting. I'm just gonna go do it. Yeah.

[00:53:56] **Ben:** I mean, like, like, let's say I'm frustrated with cross team communication.

[00:54:02] **Ben:** If I go and complain to my manager or say that I'm having trouble getting stuff done. In some contexts, they might be like, well, who can I put you in touch with so that we can get a better understanding of what needs to be done? Or, or how can I help you better communicate with the other teams? Right?

[00:54:16] **Ben:** This is like a personal growth opportunity. But then sometimes if I'm in a bad mood or I have a lot of stuff on my plate, I want to be able to go to my manager and say, Hey, I'm having trouble. Getting communication with this team going, I want them to just step in and be like, no problem. I got this. I'll be back in an hour.

[00:54:32] **Ben:** Yeah. Like, don't make me grow. I need to go back and do stuff in my corner. I need you to take care of this. Yeah.

[00:54:38] **Adam:** I can see both. When I think of things that a manager has done for me that stand out as something that I probably wouldn't have thought to do myself that, like, make me think, man, this person is really good at their job and they're really helping me.

[00:54:52] **Adam:** The things that they're doing are either falling on their sword and doing the thing that nobody wants to do, because, like, that clears the path for the rest of the team to focus on the thing that they either enjoy or... Uh, or are good at, or they are like subtly becoming like a force multiplier somehow, uh, helping me become more productive or I can't even, I can't even describe it.

[00:55:17] **Adam:** Like they know when to let me go down a hole and like research something and like, uh, get better at stuff versus like, no, you know, maybe we shouldn't spend an entire work day. Learning how, uh, the, the two different query languages for Elasticsearch. Maybe we should just write this 10 minute feature, you know, like.

[00:55:40] **Adam:** Yeah,

[00:55:40] **Carol:** completely get it.

[00:55:43] **Tim:** This is an interesting one. So, recently, I think I brought this up on a previous podcast, um, company I work for, they're making us all take a mentoring and coaching course. You mentioned that. Yeah. Last week. Yeah. Was it last week? Okay. One of the things that, uh, the company I'm working for made us learn, made us, they invested, you know, in us to, to learn.

[00:56:08] **Tim:** They call it the, the iGrow coaching model. And I, I don't know who necessarily sells this. It's, they hired some company to, to teach that. But it, it made a differentiation between coaching and mentoring. And coaching is helping a person through an immediate problem, right? So you have an issue. Uh, you're trying to solve it and someone's come to you or maybe you're frustrated because they haven't solved it and they're the only one who can really.

[00:56:40] **Tim:** So you try to help them and coach them through the issue. Uh, mentoring is different from the, it's more long term. It's more, you know, where do you want to go in your career? And you know, how do you grow as a person? Coaching is about solving an immediate issue. It's about winning the football game, not winning the Super Bowl.

[00:56:59] **Tim:** And so with the coaching and kind of having taken this, I've learned that there have been people who've tried to do this for me in the past and people I've tried to do it for, but I never really had a sort of a mental model of what that looks like. And so, you know, Carol, you and I worked together. You were never in my direct report.

[00:57:20] **Tim:** So, um, you know, I don't ever felt like I coached you or whatever, but one of the main things I took from the training was that as a coach, You may have a definite idea about what the person you're talking to should do, but you should never tell them what to do. They gotta get there. Yeah, you gotta, yeah, you have to help them get to that, get to a conclusion.

[00:57:44] **Tim:** It might not even be the conclusion you think is the right conclusion. But you have to let them, you have to be able to, um, help them identify the problem, what's going on, the goal of what they're trying to achieve. Um, help them see the reality of what's going on now, uh, and then explore options with them about what options they have moving forward, and then commit them to a way going forward.

[00:58:11] **Tim:** That's iGROW, so that's Issue, Goal, Reality, Options, Way Forward,

[00:58:15] **Adam:** iGROW. This is really interesting because you know what that sounds like to me is if you add, uh, like a confidentiality aspect to this, then you become a therapist. Yeah.

[00:58:26] **Tim:** So it's interesting. So the, the, the whole training did talk a lot about psychology and the amygdala hijack and just about how whenever we feel threatened, it was, it was quite interesting.

[00:58:36] **Tim:** It was, it was the, the main thing was trying to get people to move from, When people are stressed and, and facing challenges, they go into sort of fight or flight mode and getting them out of that into reflective data analysis mode. That's what this whole model did. So, uh, sorry, I didn't mean to take over your topic, Carol, but,

[00:58:59] **Carol:** uh.

[00:59:00] **Carol:** No, no, no. That's exactly what the topic was for. Yeah.

[00:59:02] **Adam:** So

[00:59:02] **Tim:** I, I, I think if people could learn how to do that, they would be better. And I, trust me, I'm not saying I'm good at it. I'm learning.

[00:59:13] **Carol:** No, but it seems like a great thing to learn. I'm gonna go read about it. And see, I've had the, I've had the leads. I've had the managers who have been like, you have a problem.

[00:59:23] **Carol:** Okay. I'm going to tell you, I would tell them about the issue and rather than see it fully resolved, it was, I'm going to go deal with this on the back end. And then we're just going to come back to you with an answer. So then I don't know what they did to get there. So then I'm going, how do I resolve this for myself in the future?

[00:59:38] **Carol:** Like, I feel like this is just a waste of my time now, because A, I'm never going to be able to resolve it on my own, because it's always going to take someone else and, like, someone else's intervention in order to make it successful, and I don't want to be in that. situation. And then B, I hate having to ask the same question twice.

[00:59:54] **Carol:** Like, I want to ask once and know the outcome and be done with it and be able to not have that happen again.

[01:00:02] **Ben:** I'm a huge fan of Grey's Anatomy, the TV show. I haven't, I haven't watched it in like the last, I don't know, six months or something, but, um, there's this character, Dr. Richard Weber. And one of the things that I have always admired about him is that he is both incredibly loving of all of the people that report to him, but he will also turn around and tell you the hard truth and tell you to suck it up and do your job.

[01:00:29] **Ben:** He's like a good parent. It's, it's, it's, I mean, I know it's a scripted reality show or a scripted drama, but watching his character behave, I've always found very inspiring. Yeah. I, I, I feel like I can be the compassionate part. I have a lot of trouble being the hard

[01:00:46] **Tim:** truth part.

[01:00:47] **Carol:** You're not going to karate chop

[01:00:48] **Tim:** anyone.

[01:00:49] **Tim:** I do find that all of us have things in our jobs that we love to do and we will do them in a heartbeat because we enjoy them and there's parts of our jobs that we have to do scare us and we don't like to do it so whenever we are stressed we avoid the parts of our jobs that scare us and go to the parts of our jobs that we love and a lot of times whenever we're having issues.

[01:01:18] **Tim:** In performance, it's because we have retreated to the parts of our jobs we love and we're busy. And that's our fallback. We're like, you know, I'm just so busy. I'm working so hard. You trust me. You have no idea how hard I'm working. Problem is we, we're working on the part of our job we love and avoiding the part of our job we really needed to do because it scares us.

[01:01:40] **Tim:** And I, I do it all the time.

[01:01:43] **Ben:** Let me ask you a question about that because I always feel like I have a good handle on the things at work that I'm not very good at, or the things that I'm insecure about. So typically when we have our reviews, like annual reviews or biannual reviews, I sort of know what the, what my manager or director is always going to say because I'm like, yeah, these are the things that I know I need to work on.

[01:02:08] **Ben:** And I've always sort of just assumed people have a pretty good understanding of what they're not good at. And I remember talking to one of the directors one time, And asking him if people were really getting blindsided by their annual reviews and he was like all the time people have no idea that you're going to tell them they're not good at something or they need to improve on something I'm just like how do you not know that I mean like isn't isn't I don't know I don't know how to relate to that but I was I was um I was shocked to hear that a lot of people Don't have good cognition over the things that they're not good at.

[01:02:45] **Ben:** I'm not saying like, I understand all of my biases and shortcomings, but from the, like, how do I get my work done? I feel like that's a much smaller scope of, of, of things. And I, and I, I know the things that I'm not good at because it's, it's the things that make me feel uncomfortable in my tummy, you know, it's like, uh, I don't want to do that.

[01:03:07] **Carol:** So, when you fill out your annual or biannual, do you have a, here's what I'm good at, and here's what I'm not so good at piece? Yeah. Do you struggle really hard with filling out the, this is what I'm good at piece, but can list the, this is what I'm not good at? Like, I could keep going on my list. I do. I

[01:03:26] **Ben:** absolutely do.

[01:03:27] **Ben:** I think I'm okay with both. Yeah.

[01:03:29] **Carol:** No, when, when it's like, okay, tell me what you did good. I'm like, I don't know. I did my job. Like, I did what you asked me to. Like, I do. Yeah. I mean, nobody told me it was bad, so I'm assuming everything is good. But when it goes bad, I'm like, okay, I procrastinated about PRs. I, you know.

[01:03:47] **Carol:** Need to write more unit tasks. Like, I could just keep going. I don't always document my tests very well, and SQA has a hard time sometimes figuring out what actually should be tested outside of the task, because I didn't tell them to test it. Like, I could keep going on my things I need to do better, but when it's like, what did you do outstanding?

[01:04:04] **Carol:** I'm like, I did my job. Like, I don't know what to put here. I'm okay ish.

[01:04:10] **Adam:** One strategy that I've developed over the years to be able to have something to put there is to keep like a folder in my email or a label in Gmail of praise that I've gotten, whether it's from customers or from other people in the company.

[01:04:24] **Adam:** Um, or if it's not something that came to me written, like if it wasn't an email, then I can write it down and just be like, yo, my, you know, my supervisor told me this. About this and just take some notes and toss them in there. And then, you know, if you're feeling down about something, you can go back and reflect on that and be like, actually, it's been a pretty decent year.

[01:04:40] **Carol:** Yeah, that's true too. I tend to just kind of blow those off and go, okay, I did my

[01:04:45] **Adam:** job. I'll

[01:04:46] **Tim:** say Ben, I do think you have a particular Spidey sense for things that make you uncomfortable and you're more keen to it than, I don't know, just from my experience of having, you know, talked to you over the years.

[01:05:04] **Tim:** Um, I will say I have been blindsided many times. Interesting. Maybe it's just my general overconfidence in my abilities. Um, I've been blindsided in, in reviews. Um, but that is also a 2A street, right? So if, if people aren't... Get, you know, giving you some sort of gauge along the way. In fact, one, one, one review, it's like, I, at the beginning of the year, I'm like, what do I need to accomplish?

[01:05:30] **Tim:** And he told me, I'm like, all right, cool. At the end of the year, I accomplished it. I went into that review thinking, uh, the bee's knees, man, crushed it, nailed it. And he, you know, basically strung me up because honestly, what he didn't tell me was he was having different pressures from what was expected of me than what he told me.

[01:05:53] **Tim:** Hmm. And my, my conversation with him was, I should not be sitting here being surprised, thinking I was a rockstar when I'm a failure. And that's on you. Yeah.

[01:06:04] **Ben:** Well, that doesn't, I mean, that sounds kind of shady. Harsh. I harsh mean. I, I, I think is, I think there's a difference between being blindsided by not understanding how you do your job versus being blindsided because.

[01:06:20] **Ben:** Expectations have not been managed down in the organization. Yes. I mean, that

[01:06:25] **Tim:** sucks. So when it comes to skills, it's like, yeah, I definitely, I know the things that scare me and I've gotten better, but what's, I think that the change for me in the past few years is I've become more vocal and explaining and not being afraid to say, look, if you expect me to do this, I'm probably not going to do a very good job at it.

[01:06:43] **Tim:** This is not. What I'm into and I don't excel at this. So I either need a help in coaching on this or you need to find someone else to do it because there's a lots of things I'm good at. This is not one of them. One

[01:06:56] **Ben:** place where I feel a lot of guilt is when I dodge a bullet in terms of task assignment.

[01:07:04] **Ben:** Sometimes there'll be a task or, you know, a meaty project just coming down the pipe. I'm like, oh, I don't want to work on that. That doesn't seem interesting to me. I think it's maybe a bad use of our time, et cetera, et cetera. And then it gets assigned to someone else on the team and I'm like, oh, thank God.

[01:07:21] **Ben:** But then on the, on the other hand, I'm like, oh, now I feel, I feel Bad? Like, I feel bad for the person it was assigned to, regardless of how they feel about it. They might be really excited to be working on it, but I just, I almost feel like I shirked responsibility. When you were talking, Tim, I don't know if it was last week or the week before, about how you don't like not understanding how things are built and how systems are put together.

[01:07:46] **Ben:** I also feel that way, but then at the same time, I almost feel guilty that I can depend on people to understand that stuff for me. It's, it's, it's a very, I can't even articulate it. It's like, it's a very, it's like, I don't want to learn it because it's too much for me to have to learn. But at the same time, I feel guilty.

[01:08:06] **Ben:** Like I should know it and I should be learning it. And now I'm not being responsible. 100%

[01:08:11] **Tim:** by making you know it. 100% get that. Ugh. Very uncomfortable.

[01:08:17] **Adam:** All right, let's uh, let's move on. We've been on this one for a while and it's It's 9 30. Good topic, Carol. Yeah, yeah, no, I'm not, I'm not blaming you for having a good topic, absolutely, but We're

[01:08:26] **Ben:** exploring the formatting here, you know, we're honing it.

[01:08:29] **Adam:** Yeah.

[01:08:29] **Carol:** Working on it. All right, so we've got potato salad with raisins, we have bacon on bacon, we have watermelon. Let's see what Ben brought for potluck. He

[01:08:39] **Adam:** brought

[01:08:39] **Tim:** milkshake. I brought the pudding.

[01:08:41] **Adam:** Protein shakes. Yeah, milkshake brings

[01:08:43] **Carol:** all the yard.

[01:08:46] **Ben:** So I have this phrase, when you lose a designer, you don't ship less product, you ship less design.

[01:08:53] **Ben:** And I like this as a phrase because I think it focuses the limiting factor in terms of getting stuff done. And I think enjoying this phrase is maybe a byproduct of being in an organization that has grown very quickly. And I think has not yet adapted to being the size that it is. And I think is also at the same time, maybe thinking that it is larger than it actually is and having more structure than it maybe needs and more process than it maybe needs and so on and so forth.

[01:09:28] **Ben:** And I think when you have a lot of organization, there's a lot of people who can. Whether on purpose or by way of indecision, stop things from happening. Like imagine you can't deploy something until you have to get approval from somebody and they just don't respond to you in Slack. Like they can essentially stop work.

[01:09:53] **Ben:** So this idea that if you lose a designer, you don't ship less product, you ship less design is essentially saying the train's leaving the station, right? Code is moving to production. So, the question is not, is code hitting production? The question is, do you want to step in and have some say in what that code looks like or how that product looks and feels?

[01:10:16] **Ben:** So, losing a designer, my team happened to have lost a designer, we had a dedicated designer for a brief period, and then my team, my team within the greater organization, then lost our dedicated designer. And this is what I said to my team, I said, look, What happens now is that we don't slow down, we just don't design things as well, because we don't have a design resource.

[01:10:37] **Ben:** Right. So what we can't do... is shelve our feature work and wait for a designer to be allocated to us. We just have to keep moving and do the best with what we have. See

[01:10:47] **Tim:** if form all day.

[01:10:51] **Ben:** See if div.

[01:10:55] **Adam:** I know who brought the salmonella.

[01:10:59] **Ben:** Sorry. And I think the idea of losing a designer and shipping less product, design is just the example that pops to mind. But. If you lose your product manager, you don't stop shipping product. You just don't prioritize as well. Or, you know, if you don't have, I don't know what the other good examples are, but like, if you lose a platform engineer, you don't ship less product.

[01:11:19] **Ben:** Maybe your product is just less robust or less resilient. And I'm not saying that these are all. Zero, like, these aren't all, um, these don't all have downsides. The focus is on shipping and a bias towards action that our team has to produce and we produce what we can with the resources we have available.

[01:11:44] **Ben:** But the train doesn't stop. The train keeps going. It's like a snowpiercer.

[01:11:50] **Adam:** Good show. I found another movie I haven't seen. TV show. It's

[01:11:52] **Ben:** not a good movie. That was a movie? Okay. It's kind of a terrible movie. It's a TV show right now on BBC. It's not a good TV show. I only watched the first episode,

[01:12:04] **Tim:** but I'm like...

[01:12:04] **Tim:** So can I challenge you, Ben, a little bit?

[01:12:07] **Ben:** Yes, PCI compliance world.

[01:12:10] **Tim:** No, I'm not telling you from that viewpoint. I don't have an opposite viewpoint. What I'm challenging is the motivation for always shipping. The

[01:12:22] **Ben:** motivation, I think, is more about

[01:12:29] **Ben:** a commitment to choosing a path forward. It's almost like you take the responsibility of making a decision off of your own shoulders, and it becomes a thing that no one can control. Like, hey, I'd love to not ship this product until we have a designer available, but product's going out, nothing I can do about it, except maybe try to make it the best I can.

[01:12:53] **Ben:** So it's, it frees you up from having to worry about Making decisions about whether or not something's going to get shipped because something's getting shipped. So now the responsibility is deciding how you can affect the outcome, not necessarily whether the outcome's happening.

[01:13:11] **Adam:** So is this about like clearing a mental roadblock or providing motivation when this losing a designer, you know, hypothetical situation happens?

[01:13:21] **Adam:** Or am I misreading this?

[01:13:26] **Ben:** I think it's, yes. Clearing, I think clearing a mental roadblock is, is the right, is the right analysis there because. I think you can, if you lose it, if you lose a leadership role, and I, you know, I like to think of design as leadership. If you think of engineering product and design as being these three pillars of leadership within an organization, if you lose your designer, it's easy for people to now think, oh, we can't move stuff forward because we don't have this leadership position.

[01:13:59] **Ben:** If you flip that table and say, well, stuff's going out, designer or no designer, then I don't even have to think about that anymore. Now what I can focus on is how do I make the work that I have to do as

[01:14:12] **Tim:** good as possible. It's weird for me because I don't come from a world where we have to ship constantly.

[01:14:19] **Tim:** I know what your shipping schedule is, but it's like ours is not very often. It's not,

[01:14:25] **Ben:** um, it's not based on any particular shipping schedule, which is why I think Adam is saying that it's more about clearing mental hurdles. That to me is... It forces you to not be able to just kick the can down the road indefinitely, right?

[01:14:45] **Ben:** There's no, there's no, you, you can't end a meeting with being like, well, let's circle back on this when we have more information.

[01:14:51] **Adam:** No, we're still moving.

[01:14:52] **Ben:** Right. Like if you want to put input into this, then you circle back sooner than later, because if you don't circle back.

[01:15:01] **Carol:** It's already going to be out there.

[01:15:02] **Carol:** Yeah,

[01:15:03] **Tim:** I guess I guess I can buy into that. I'm trying to think of an example in my world. Um, so, you know, dealing with credit card and financial stuff. There's a lot of functional stuff that I like to do for that. So it's like. You're adding new functionality to that. That's great. But you know what? I, I'm not a designer.

[01:15:24] **Tim:** If you want to make the, the new form look really super pretty and do lots of cool stuff, that ain't getting shipped. But some new really cool functionality is going to get shipped in the next, the next. So yeah, I, I can, I can buy that. Yeah. And when we hire a new designer, they'll do some cool stuff and we'll ship some cool design.

[01:15:42] **Tim:** But until then... Yeah, we're going to keep uploading new cool functions because that's what our current skill set can do. Is that kind of what you're saying?

[01:15:52] **Ben:** Yeah, I think so. And I think it also frees other people up in an organization to not feeling like they're being responsible for blocking productivity.

[01:16:03] **Carol:** Yeah,

[01:16:03] **Adam:** that would stress me out. Right, if

[01:16:05] **Ben:** there's someone who's a critical decision maker. that doesn't need to be a critical decision maker, but that's sort of where they are in the organization, then if you have a team would appreciate your input, but doesn't need your input, then I think to some degree it frees them up to be able to focus on things that are maybe more important.

[01:16:26] **Ben:** I mean, ultimately this all boils down to allowing teams to have more autonomy and to be able to make better independent decisions based on educated understanding of what needs to get done.

[01:16:40] **Tim:** I think it kind of ties back into The triumph I was talking about earlier was the trying to build consensus. I think we're kind of saying the same thing is like, so you might have people that are saying, well, we're not shipping new design features, right?

[01:16:56] **Tim:** So that's their, that's their roadblock. Um, but you got to build consensus for both your team and for the people who could block it and say, I get that. You know, we can't, you know, because of the situation, we can't be deploying new design features, but. We have to get consensus here that continuing to release new features is important.

[01:17:18] **Tim:** And here's what will happen if we don't. And here's how it's going to affect you personally. And here's how it will affect the organization as a whole. So can we get consensus that we're going to continue to ship? With the idea that, uh, you know, we'll be shipping less design.

[01:17:36] **Adam:** We can come back and improve the design later.

[01:17:37] **Adam:** Let's just get it functional now.

[01:17:39] **Tim:** And that's, that's the whole Or you might not even need to. Getting the consensus from, from parties that, that have a say, but might not get their way. Like it. Okay.

[01:17:49] **Adam:** Nice. Potluck number one in the books. I'm full. I enjoyed it. Well, let's hope this remains a constant and refreshing feature of the podcast, but we have another review to read here.

[01:18:01] **Adam:** So I'm going to go ahead and read our second review. Another review. Please be a hater. Is it good or bad? Okay, so this is by Heyowa. Uh, it's five stars and it says love listening and wait with anticipation for a new one. So I guess I will click yes on was this review helpful.

[01:18:20] **Tim:** Very helpful. Yes, yes, yes.

[01:18:21] **Tim:** Thank you. It's helpful to me.

[01:18:24] **Carol:** Help me. When we get a hater, I'm gonna be so mad.

[01:18:27] **Adam:** I'll be so happy.

[01:18:29] **Carol:** I'll be like, damn, what have you

[01:18:30] **Tim:** done? I co opt their hatred. I, I suck it in and spit it out as joy.

[01:18:37] **Carol:** One of my friends sent me a message and said he's been listening to it. Yeah. And his daughter is a freshman at Kinesol and is doing computer science and she's home from spring break, home for spring break this week, and she was listening with him.

[01:18:50] **Carol:** I was like, yay,

[01:18:52] **Adam:** that's

[01:18:52] **Tim:** awesome. All right, Kinesol State Owls. Yeah, that's it. Go Owls! Go

[01:18:56] **Adam:** Owls!

[01:18:56] **Carol:** Woo! Go Owls!

[01:18:59] **Adam:** Who?

[01:18:59] **Carol:** Can this all say? They're Owls. Yeah. Who? Oh. Damn.

[01:19:05] **Tim:** He got us twice. Wow. I would have kept going. He dragged us hard.

[01:19:11] **Adam:** That was good. That was really

[01:19:12] **Tim:** good.

[01:19:15] **Adam:** So let's talk about Patreon. We have a bunch of people that are supporting us on Patreon and something that I think we're going to start doing going forward is we're going to just say a special thank you to people when they join our Patreon and so that our Patreon.

[01:19:29] **Adam:** Uh, our OG patrons don't lose out. I'm going to go through now and read off all of their names. And going forward, when we have a new patron, we'll just say, you know, thanks for joining the team. Um, but so for starters for now, as of episode, what did I just say? This was 15. So as of episode 15, these are the people that are kicking in and helping keep the lights on.

[01:19:49] **Adam:** So thank you very much to Sean, Brian, Amy, Seb, James, Mingo, and our top patron. Monte Chan, who is gonna get a thank you every week. Monte Chan, you legend. Is a legend. Thank you, Monte. Thank you, everyone. Thank you for listening, of course, too. Yes. Yes. So if you think we've earned it, please consider supporting us on Patreon.

[01:20:09] **Adam:** If that's something that you're interested in, you can find us at patreon.com/WorkingCodePod. There's perks available at different support tiers, like an invite to our Discord server, early access to new episodes at our After Show, where we keep the mics running for about another 10 to 15 minutes.

[01:20:23] **Adam:** And like I said, for everybody else, thank you for listening. Without listeners, we'd just be a couple of weirdos recording our conversations for no reason. Don't forget to share the show with a friend, because there's no better support than a word of mouth referral. Tell the algorithms to boost our signal by leaving us a review and a rating on iTunes or wherever you get your podcasts.

[01:20:39] **Adam:** Send us your topic suggestions on Twitter or Instagram @WorkingCodePod. We'll catch you next week, and until then, your heart matters.

[01:21:08] **Carol:** I love, I love fixing bugs. I'm probably not one weirdo. So these are

[01:21:15] **Tim:** bugs, they're not to do's in your code, right? Sorry, I keep

[01:21:18] **Carol:** interrupting. Okay, I'm done.

[01:21:21] **Ben:** Uh, yes, thank you.

[01:21:24] **Tim:** Let me, let me re ask the question. Cut. But

[01:21:26] **Adam:** I feel good, I feel good about the amount of cleaning that I did today. Good job. Noice.

[01:21:31] **Tim:** Noice. Noice, noice,

[01:21:32] **Adam:** noice. How many more things are you guys going to say that I have to cut out?

[01:21:39] **Carol:** So few. How many cans are on your desk though? I want to know that.

[01:21:44] **Adam:** Uh, just this can that I'm drinking right now. Okay. And this empty water glass. Oh, that's not bad. Because I cleaned my office today.

[01:21:53] **Carol:** I wanted to know how many you've gotten on there since then though. That was my question. Uh, no. You may all get baked beans.

[01:22:00] **Carol:** Because we didn't coordinate

[01:22:01] **Adam:** what we were bringing. Yeah, we all brought potato salad. I will never bring potato salad. Okay. I don't eat potato salad.

[01:22:08] **Ben:** I'll never bring anything that has mayonnaise in it. Ugh. Mayonnaise

[01:22:11] **Adam:** is awesome. Salt is awesome. Salt is good. This is a weird conversation. Weird intro.

[01:22:19] **Carol:** Mayo bad.

[01:22:20] **Carol:** Salt

[01:22:21] **Adam:** good.
