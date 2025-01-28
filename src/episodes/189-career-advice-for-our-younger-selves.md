---
title: "189: Career Advice For Our Younger Selves"
description: "In this episode, Tim and Adam discuss career advice for their younger selves, including the importance of job changes for salary increases, focusing on programming tasks rather than managerial roles, and the hazards of tying one's identity to a specific programming language."
date: 2024-07-31
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/189-career-advice-for-our-younger-selves/id1544142288?i=1000663957002"></iframe>

In this episode, Tim and Adam discuss career advice for their younger selves, including the importance of job changes for salary increases, focusing on programming tasks rather than managerial roles, and the hazards of tying one's identity to a specific programming language.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/189-career-advice-for-our-younger-selves.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** The biggest raises you'll get throughout your career is by changing jobs.

[00:00:04] **Tim:** Which I always admire about Carol. She's, she's done that throughout her career. She, she, she left the company that. That I used to work at and then went somewhere and then came back to our company and got a big pay raise for what she is. So,

## [00:00:38] Intro

[00:00:38] **Adam:** Okay, here we go. It is show number 189 and on today's show, Tim and I are going to talk about career advice for our younger selves.but first we'll start with our triumphs and fails. if it wasn't already obvious, Carol and Ben couldn't make it tonight to, through a series of conflicts and, other circumstances.

[00:00:54] **Tim:** But apparently they're going to do a show together. So you got, you got a twofer this week. You got me and Adam and you got Ben and Carol next week. Maybe they, maybe they can talk about the same thing and we can like, compare notes.

[00:01:04] **Adam:** Haha, maybe. cool. So, I think you went first last week, Tim. so I'll go first this week.

## [00:01:09] Adam's Triumph

[00:01:09] **Adam:** I'm going to go with a triumph, and that is that I've actually been able to do some like real honest to goodness product work, for the last like week or so.

[00:01:18] **Tim:** No, no SOC compliance.

[00:01:20] **Adam:** I've been doing that as well, but, we're, starting to get to pretty close to steady state at this point.

[00:01:26] **Adam:** You know, once you get your ducks in a row, it's more just about keeping them in a row, right? And, that's less demanding on your time. So I'm, I'm, I'm not saying, I'm not saying they're fully in a row yet, but they're much closer. And so it demands less of my time to do that stuff. And the stuff that is urgent is all done.

[00:01:45] **Adam:** So, I'm kind of taking some time to, to refocus on the product. Cause you know, if you spend all of your time making business possible, then you can't work on your business and, and then you have nothing to sell. So.it's a little bit of a catch 22. So, yeah, there's two sort of like product things that have been hot on my mind and, and are going to be important for us in the coming year.

[00:02:07] **Adam:** I mean, there's more than that, but the two that I'm working on are a payment service provider, hybridization, which I'll talk about more in a second here. And then A B testing. So a couple of weeks ago, Ben and I had a nice chat about A B testing stuff. And that is going to be one of my projects in the upcoming, weeks.

[00:02:23] **Adam:** But The one that I'm working on now is this payment service provider hybridization, which is, you know, buzzword bingo. But, basically, you know, I've talked in the past about how we use, a service called Spreedly and they, for lack of a better word, aggregate,gateways, right? So we can use, you know, Authorize.

[00:02:41] **Adam:** net or, CashNet or, or whoever threw them and it's all through one single API, which is fine.and there was a period of several years where they did not offer any like digital wallet stuff. Like if you're using Spreedly, you can use that and you can select, you can accept, you know, Visa, MasterCard, Discover, American Express, all those, but you can't do Venmo or PayPal or Any of those things, Apple Pay, Google Pay.

[00:03:09] **Adam:** and so our industry got to be in their bonnet, you know, higher education got to be in their bonnet about, Oh, we have to be able to accept Venmo. Our, our graduating seniors, they're, you know, they're the new, generation and they, they, if they can't pay with their Apple Pay, then they're not going to make a donation.

[00:03:25] **Adam:** so we had to jump through some hoops and, add support for Braintree so that we could get, Easier,

[00:03:31] **Tim:** by the way. Yeah. So in your,

[00:03:34] **Adam:** and, and so now via Braintree, we can accept all of those things, which is great.however, one thing that we never really anticipated when I made those changes to add support for Braintree was that potentially customers are going to want to switch, gateways, right? We might have somebody currently using, Authorize.

[00:03:51] **Adam:** net and they want to switch to Braintree. and that's all fine and dandy. You can just change the configuration, but what that does is. The way that it's written right now, it's like kind of just for lack of a better word, let's call it hard coded, right? It's written with the assumption that you're only ever going to have one gateway.

[00:04:09] **Adam:** And so if you have like recurring gifts or if you have an event going on and you need to make a refund, because somebody, you know, whatever the, they have a legitimate need for refund. If you in the middle of that have changed your gateway, then the vaulted cards are no longer available. You can't make refunds.

[00:04:25] **Adam:** You can't charge, those recurring gifts. So. We need the ability to run multiple gateways in parallel to support that use case of being able to switch gateways. But also in theory, it's conceivable that somebody might just want to use multiple gateways. And so we're, we're coming at this from the angle of, it's not just a temporary situation.

[00:04:48] **Adam:** It's all, we're going to be able to support it in perpetuity, right? So maybe you want to use, Braintree for your online giving, but then, you know, somebody else. for your event registrations or whatever, for whatever reason, you know, we're not here to dictate the, the business rules. We're just here to make the software work.

[00:05:06] **Adam:** So, I'm starting down the path of making that possible, which sounds like a big undertaking. And I, I guess it kind of is, but, fortunately our younger selves had just enough foresight to, you know, put some in, some, some columns on the necessary tables to say, okay, this transaction ties to this specific gateway, because we do already have support for multiple gateways, A for like dev, QA, and production, but then B, You know, you might have sub accounts of those or sub merchants of those different merchant accounts.

[00:05:38] **Adam:** and so there, we, we just listed them all as gateways. And so every transaction ties back to a specific gateway so that you can do the refunds and the recurring charges and all that. And so, in theory, we should just need to be able to support multiple types of gateways in that gateway table. And then, you know, Bob's your uncle, basically, right?

[00:05:57] **Adam:** You can just, if you need to refund, just go look at the original transaction. Which gateway was that on? Refund through that gateway.

[00:06:06] **Tim:** merchant account with Braintree or whoever, and then they just put in their credentials into your system. And that's

[00:06:11] **Adam:** Pretty much. Yeah. Yeah. So there's a, I've just had to deal with this with a bunch of customers. So basically we need like a public and a private key, the mid, the merchant account or merchant ID, the sub account label, if you're going to do that and like, we need a label to display it as, and I think that's it.

[00:06:29] **Adam:** Like, I think that the bits that tie it together are just the mid and the public and private key, the sub account name. So, yeah. So yeah, it feels good to be like. You know, making substantive changes and not just pushing ducks across the road.

[00:06:48] **Tim:** That wasn't a cursing. That was just,

[00:06:51] **Adam:** If you couldn't tell the difference.

[00:06:52] **Tim:** it was me simulating the duck going across the road. So what about the AB testing? I

[00:06:57] **Adam:** So, I don't know if you'd listen to that episode. Um, listen to any of them, but okay.

[00:07:01] **Adam:** You don't listen to our podcast or any other, except the ones that you do listen to. the, so basically, you know, we've, I've talked at length about our mail product, or mail module in our product and,

[00:07:15] **Tim:** Oh, like email, not like mail, not, not like the gender.

[00:07:19] **Adam:** correct. Email. and, you know, our customers for years have been clamoring for AB testing.

[00:07:26] **Adam:** And, you know, if it's

[00:07:27] **Tim:** they can sit, they can send an email, like two different emails and see which one performs best.

[00:07:32] **Adam:** actually even a little bit more than that. So we're going to do it as like, AB test automation, right? So they're going to build sort of two very similar messages with some differences between them. and like, so pick a list of say 300, 000 people build their two message variants, and it will automatically pick like, you know, 10 percent of the messages.

[00:07:52] **Adam:** Gets this email, 10% gets this other email saving the other 80%, and then we'll, we'll set up some success criteria, whether it's like whichever one is better in a certain amount of time, or first one to reach a certain goal sort of thing.and then when that success criteria is met, we will automatically take that winning message content and send it to the remaining 80%.

[00:08:15] **Tim:** Gotcha. That's

[00:08:16] **Adam:** it's, yeah, it's not just AB testing, but it's like AB testing and then, automatically applying the learning

[00:08:22] **Tim:** It's like a stage release, stage release of the email to see which one does better on in smaller doses, and then whichever one wins, send it to the big group, rather than just doing a total hundred percent of your audience, 50 percent get this, 50 percent get that and go, which one does better? Well, now you've already, you already sent the email, right?

[00:08:40] **Adam:** Yeah. And I mean,

[00:08:41] **Tim:** so 50 percent were suboptimal.

[00:08:43] **Adam:** yeah, we're, we're, you know, already collecting and exposing a lot of the information that it would take to kind of manually do this, right? We show them their open count and their click count and, they can trace back GIFs to specific messages if, if the message, you know, led to the donation sort of thing.

[00:09:04] **Adam:** but it's extremely manual. And like you said, you know, there's no. it, it, it would be, I, I guess it's just extremely manual, right? So they, they would have to be very intentional about like, okay, these are two our two variants of the message. Send them and try to like grok the learning from the, the difference in the way they perform, they perform.

[00:09:23] **Adam:** And then, apply that learning, whereas what we're doing is saying, okay, like make your two variants, define your success criteria, and we'll take care of the rest. And also something that we're going to put on that is, you know, when you set up, we're, I think we're going to call it an experiment, right?

[00:09:39] **Adam:** So you're, an experiment contains the list of people that you're sending to, the percentage breakdowns, how you want to do your test, the success criteria. And then we're going to say like, okay, if, if message A wins, then what does that tell you? Like define the lesson from this and if message B wins, then what is the lesson, right?

[00:09:59] **Adam:** Is it too many emojis in the subject line turns people off? Or is it, you know what I mean? Like, or is it all caps means this or whatever, like be very intentional about what is the difference between the messages and, and defining success criteria. And over time you'll automatically build up a list of like best practices for your particular audience.

[00:10:17] **Tim:** That's cool. And that is interesting, the AB testing stuff. Cause we do. That with our ad campaigns, like we put ads to try to sell our product online. It's like, we'll do an A B test. And the only thing we change is like the thumbnail graphic of the ad. Like the exact same color scheme, same message. It's just one guy is holding a coffee and the other guy's looking at a computer and you're like the coffee guy beat the The other guy, but like 40%, like this, I don't know.

[00:10:52] **Tim:** I, you know, it's like, like, there's no, you learn a lesson from it, but I don't really know what that lesson was. It's like, people like coffee,

[00:10:58] **Adam:** right. Mm-Hmm.

[00:11:00] **Tim:** So it's, and then sometimes like with, with ads, it's probably not this was with their gift emails, but with ads, like they'll do really, really well. And then over time people just stop seeing them.

[00:11:11] **Tim:** Right. So you're doing the test and it's like coffee guy is now like he's tanking and now you got to like, change it, you know, put it, you know, Girl knitting or something, you know, girl, girl shopping. And now she's beating coffee guy because people just got blind to that ad. They've seen it so much they're done.

[00:11:28] **Tim:** So yeah, it's, definitely, I don't, definitely a dark art. this whole thing of just trying to figure out why sometimes things get more traction than

[00:11:39] **Adam:** Yeah. And I, I think that it's gonna take a skilled practitioner to really make the most of it. Right. Somebody's gonna have to be extremely intentional about the differences that they put in their, in their messages. And something Ben and I talked about too is it doesn't just have to be such a. A granular difference, right?

[00:11:57] **Adam:** It doesn't have to be like the shade of blue of the call to action button is the difference, right? Darker blue wins or something. It could be something totally like, okay, an appeal to emotion versus an appeal to facts, right? Like totally different message content. But if you, if you're building the message with the, that dichotomy in mind and, and trying to learn from that, like there's, there's possible, you know, lessons to take from that.

[00:12:23] **Adam:** It'll be interesting.you know, there's definitely going to be some people that just will not use it to the it's potential, but I think that we do have some really smart, customers who are, I think they're excited about it. And we're excited about putting the tools in their hands because we know based on what we've seen them do in the past, that they're going to do really cool things with it. That's me. What about you? What do you got going on?

## [00:12:48] Tim's Fail

[00:12:48] **Tim:** Well, I got a failure, failure. beginning to wonder if I Peter principle, Peter principled myself.

[00:12:56] **Adam:** Oh, yeah.

[00:12:56] **Tim:** Yeah. So it's like, I, I'm just wearing too many hats right now. So we got, you know, we don't have our sales guy anymore. And so I'm, I'm handling his sales calls. And I, and I do actually really enjoy talking to, you know, potential clients and customers and, and learning about what their problems are and trying to solve it, but it's like in between that and my real job and my real job, you know, as.

[00:13:19] **Tim:** The programming, the thing I really enjoy about my job is when I get to code something like you're talking about doing some product work. I really, really love that doing product work, but it's like I do less and less that all the time because it's like I'm dealing with legal, I'm dealing with accounting, I'm dealing with, with all this other stuff that has nothing to do, you know, is with running the business.

[00:13:38] **Tim:** And now I'm also, You know, doing sales calls and, you know, taking meetings with, with potential clients and then trying to build the sales pipeline. I got too many hats on right now and I'm not enjoying, not enjoying having so many hats right now. And, the reason I say Peter Principal, it's like, you know, we'll talk about this and this is kind of one of my advice for my younger self is, you know, they talk about you, you fail upwards.

[00:14:03] **Tim:** Well, You know, you don't really fail upwards, but you, you basically get promoted into jobs that you really don't want to do and that aren't really cut out for. It's like, so, I'm not saying I got promoted into this, but not having a salesperson is a temporary thing. We're going to hire someone, you know, in 2025, but I just kind of let this ride for, for the rest of the year.

[00:14:23] **Tim:** But it's like, yeah, having too many hats on. It's like, I know stuff is slipping through the cracks. I know I owe people some. Some code updates and some things that I'm working on that have just gone slip by. I know there's just conversations I've had with customers or potential customers that I need to follow up on.

[00:14:44] **Tim:** It's just, I don't have time to follow up on them. And those are the ones I let go. It's cause it's like, you know, 98 percent of the sales calls you have probably don't end up in a contract being signed. It's like, you know, it's like, it's a very, it's a high volume, high turnover kind of thing. That's what I'm like. Talking to our sales too. We have like marketing help above us and I was just talking to them. Like, yeah, we got to find some way to help me out here to, to, so, cause I'm, I know I'm letting, I know I'm letting people slide through the crack. So it's just not a good feeling.

[00:15:18] **Adam:** Yeah. I mean, not everybody, I think, makes a good salesperson.

[00:15:22] **Tim:** Oh, I know. I don't, I don't,

[00:15:24] **Adam:** gotta, you gotta have the right disposition for it, for sure.

[00:15:27] **Tim:** I'm good at coming on the call, you know, helping, helping them understand what we do and get them excited about it, but I'm not the guy keep up with you and stay because you got to stay on these people, right? They got other they got their jobs too. Most people when they're in a buying mode That's sort of like an extra add to their job, right?

[00:15:47] **Tim:** And so they're not 100 focused on it either So if you're not constantly staying on them and going hey, you know, what do we need? Who do we need to talk to if you're not constantly on them? They're just gonna let it go and they'll either Not make a decision or just go with someone else who is a lot more attentive.

[00:16:04] **Tim:** So that's the part of sales I don't like. I do like the demos and the calls and solving the problems for them. That sort of thing. But yeah, the, the, the babysitting, that's not me.

[00:16:16] **Adam:** Yeah. And I mean, I've been through a good bit of vendor selection in the last couple of months, right? We switched our, compliance audit partner, our, our CPA firm, I guess, that's doing our audits and also the, the GRC governance risk or whatever, regulation and compliance. I don't know, whatever. risk management and compliance GRC.

[00:16:38] **Adam:** and so we switched our software for that. And it's funny, like, even though you can see your brain behaving this way, it doesn't stop it from happening. When I would reach out to somebody and, you know, request a demo and say like, please use this link to schedule on my calendar directly, the, the people that would have the attention to detail to like, do what I asked them to do.

[00:17:00] **Adam:** Like, I emailed your salespeople and I said, please here, you know, schedule with me on this, at this link and send me whatever demo you can in advance. And if they didn't do those two things, then I was already, they were at like, you know, 50 percent chance of getting it. Whereas the people who did, do those things already are at like, you know, 80 percent chance of moving on in the selection.

[00:17:22] **Adam:** It's like, That, that attention to detail and that first impression means so much. And it was, it's, it's like a weird bias thing. Like I kind of tried to talk myself out of it. Like, I don't want to completely dismiss a potentially good product because it has a lackluster salesperson at the same time, you know, like, is that indicative of the type of relationship that you're going to have overall?

[00:17:46] **Tim:** I mean, and that's, and that's natural, natural to think that way. It's like, yeah, if they're not gonna pay attention to me now, when I'm trying to get, get their business, give them my business, you know, how are they gonna treat me when I'm a customer? So yeah, and I'm aware of that. And it's like, that's what makes me hate this.

[00:17:59] **Tim:** It's like, who did I miss? And then it didn't help. I was technically working, but technically also on vacation most of the time in Ireland for a month. It's like, I took some sales calls there and like, I try to remember like, how did that one go? I guess that went okay. Fortunately, I have notes, but it's like, Yeah, I know somebody slipped into the cracks.

[00:18:19] **Tim:** So that's, that's, that's my failure.

[00:18:22] **Adam:** I hope you, Find your way back to enjoyable work, my

[00:18:25] **Tim:** Thanks. Appreciate it.

[00:18:26] **Adam:** Hire that salesperson. Cool, So our topic for

## [00:18:30] Career Advice For Our Younger Selves

[00:18:30] **Adam:** today was, like a career advice for our younger selves. You know, we're both, Toward the end of our, in the last half, I think, of our careers, right? Uh, even half for me. I got 10 years. I'm done

[00:18:43] **Adam:** don't rub it in. Um, I'm done.

[00:18:46] **Adam:** yeah, my best friend just retired. He's 60. and man, it's, it's so hard not to be jealous. But anyway, you know, we, we do have the benefit, I think, of a little bit of hindsight here. So we just thought it would be fun to take a minute and think about what advice we would give our younger selves if we could.

[00:19:05] **Tim:** Okay. Yeah, I like it.

[00:19:07] **Adam:** Why don't you go first?

[00:19:08] **Tim:** So how young we talking here?

[00:19:10] **Adam:** you know, I dunno, like for me, I'm just thinking like, okay, I started my career pretty much right out of high school. I was fortunate enough to, while I was in high school, kind of get my foot in the door with web development and I, and I got some internships and some jobs while I was in college to, continue down the development and, and in some cases web development paths.

[00:19:30] **Adam:** So for me, I'm, I'm thinking about then, so kind of the

[00:19:33]

## [00:19:33] Play Videogames, Don't Make Them

[00:19:33] **Tim:** So, So like when I was young, I thought, you know, video games were amazing and every kid, you know, loves video games.

[00:19:39] **Tim:** Most all of adults. I still love video games. I thought this is what I want to do with my, I'm going to build video games. And, you know, back then video games were pretty simple. They weren't too, I mean, what they are today, but I thought, yeah, that'd be so cool, like to have a job where you just, you're building video games.

[00:19:57] **Tim:** And I would tell my younger self, the idea sounds great. But building video games is not the same as playing video games.

[00:20:06] **Adam:** for sure.

[00:20:07] **Tim:** And, and the, and knowing what I know about the industry now and how reportedly, I mean, I've never worked in the video game industry. it's, it's grueling, right? The hours are ridiculous.

[00:20:19] **Tim:** It's crunched, you know, whenever you're close to release time, it's like you're, you're not getting any sleep. You're getting pushed to work, you know, way, way too much overtime and you're always under the gun. it seems like pretty bad industry where they're making a lot of money now.

[00:20:37] **Tim:** I mean, they're making more money than the film industry and yet they, that those riches are not translating into really good pay for the developers.

[00:20:50] **Adam:** I was sitting here thinking like, is it, wasn't it like some bombshell? Like, I feel like it was on Blogger or something like, post many years ago. But, that's like where we got the term one percenter, right? Like somebody was talking about her husband worked in the gaming industry and he's doing all these hours and, and, you know, meanwhile, the, the the very top of the company are like the one percent.

[00:21:14] **Adam:** Wealthiest people in the world. And he's making 50, 000 a year or something, which is like,

[00:21:20] **Tim:** So, yeah, I would tell myself, of course, I obviously didn't go into it, but I really, you know, if my young self knew I was going to be working at a, at a video game company or making, starting my own or, you know, whatever, never panned out. It's always, always seems easier than it is when you're young and naive, but I would tell myself, you know, do, do something boring, but lucrative.

[00:21:42] **Adam:** Oh, really? I

[00:21:43] **Tim:** Yeah, do something boring but lucrative. Don't, you know, the coding is fun enough in itself. It doesn't matter what you're coding. The coding itself is funny. If you're coding a video game, if you're coding a, you know, content management system or something, that's the fun bit. Building the thing is fun.

[00:22:01] **Tim:** It doesn't matter really what you're building. So if you're going to build something, build something that is fun. You know, you can make a good amount of money off of.

[00:22:09] **Adam:** mean,

[00:22:10] **Tim:** insurance is very lucrative, it's very, very, very boring.

[00:22:13] **Adam:** yeah,

[00:22:15] **Tim:** In fact, I went to, you know, when the kids were in school and they would have, in middle school, they'd have these career day, I'd go to the career day, and I'd give this like, big rousing speech about, you know, I dreamt to be a video game, and I, I worked really hard and I went to school and I learned about coding and I worked by myself, but guess what I do now?

[00:22:32] **Tim:** And they all yell, you write video games. Like, no, I write software for insurance companies, one of the most boring industries in the world. But you know what I like about it? I make a lot of money.

[00:22:44] **Adam:** yeah,

[00:22:45] **Tim:** So, Timmy, just play the video games. You don't have to write them.

[00:22:50] **Adam:** right. Yeah. You don't have to, I mean, that's advice for myself too. there's not one that I wrote down, but you don't have to turn every hobby into,an opportunity to make money.

[00:22:58] **Tim:** about you?

## [00:22:59] Don't Be Afraid to Change Jobs

[00:22:59] **Adam:** Oh, hmm. I think that, the first thing that comes to mind is, that I shouldn't have been as afraid to change jobs more often, right? So, for some reason, I think it was kind of carryover from our parents generation where, you know, you would work at the same company for 40 years, then you'd retire and they'd give you a gold watch or something and, and that was life.

[00:23:22] **Adam:** And I, I don't know, just something about that felt natural and, and right. And so I, I probably held on too long at a lot of jobs, stayed there too long. And with the benefit of hindsight, I would say like, if I had tried, when I had the, when I have the, freedom to take on more risk, like before I got married and had kids, if I had tried to work at like a, a fang company, Facebook, Apple, Amazon, Netflix, Google, that, that type of company, then I guess it would be Manga now, right?

[00:23:54] **Adam:** Meta, Apple, Netflix, Google, Amazon. yeah, if I had

[00:23:59] **Tim:** Mang just sounds really, it sounds like a British swear word for something.

[00:24:03] **Adam:** Manga,

[00:24:04] **Tim:** Manga.

[00:24:05] **Adam:** yeah. Apple and Amazon are both in there.

[00:24:08] **Tim:** Oh, okay. Well, I thought you were just taking the F from fang and just dropping an M's or mang, but you said manga. All right. That makes sense.

[00:24:15] **Adam:** but yeah, like, you know, when you're younger, you have that, that freedom where, you know, it's not as devastating if you get laid off, right? You can live on ramen noodles for pretty cheap by yourself, for a while while you look for another job. You can't ask that of your family, right? So, you know, I think like you were talking about making a lot of money, this, all of this stuff kind of just like interweaves in and on itself, but like, you know, the, I think the best way to make a lot of money is to get some experience and parlay that into a better job and parlay that into a better job and parlay that into a better job.

[00:24:49] **Adam:** The biggest raises you'll get throughout your career is by changing jobs.

[00:24:54] **Tim:** Which I always admire about Carol. She's, she's done that throughout her career. She, she, she left the company that. That I used to work at and then went somewhere and then came back to our company and got a big pay raise for what she is. So, that, that I agree with you. I'm sort of the same way I've been same place with 20 coming up on 25 years.

[00:25:15] **Tim:** So, but that's, I started working there when I got married and had kids. And so that's what stuck me there is like that fear that your kids are going to go hungry and you're not going to have a place to live that kind of motivates you to stay in the same place unless something just lands in your lap and says, Hey, here's a guaranteed thing and we're going to raise your, you know, like 25 percent or something.

[00:25:39] **Tim:** And you're like, yeah, that doesn't happen to a lot of people

[00:25:43] **Adam:** Yeah, that's a pretty rare experience, I think. But yeah, so, you know, I guess that's the first piece of advice I would give myself is like, take the risks while you can, while it's easy to take them. because, you know, getting that higher, well, I guess it's a little bit of a double edged sword, right? So getting that higher salary earlier in your life will give you.

[00:26:02] **Adam:** More opportunity to put it in the bank and, and start earning compounding interest on it. But

[00:26:08] **Tim:** low, low expenses.

[00:26:10] **Adam:** right. And at the same time though, you know, I feel like I've seen some stuff where more recently some people have kind of gotten like, do they call it golden handcuffs, right? In your job where like you, you can't leave because nobody will pay you more than what you're making now.

[00:26:28] **Adam:** Right. and so you get stuck because you, you have gotten accustomed to making. You know, whatever, 200, 000 a year. Cause you're working at Amazon and, you know, you'd like to move because you don't like your job, but nobody's going to pay you 220, 000. you know, you'll be lucky to get 170, 000, right? Like, so that's a, that's a big pay cut,

[00:26:51] **Tim:** But you built your life on the fact that you're making that sort of income. and that's one thing that kind of scares like as you get older, it's like, you know, there is a bit of elder bias, you know, or prejudice, right? So it's like you got a company looking at a resume and you got a guy who's got 25 years experience.

[00:27:08] **Tim:** You would think, well, that's, that's valuable. But at the same time, they see a younger person who's got a little bit of experience and you can pay that guy half,

[00:27:15] **Adam:** Mm hmm.

[00:27:16] **Tim:** right? And they're like, well, and this other guy, this person might be here for, you know, 10 years, and then you have this older person, you know, they're going to retire in five to 10 years.

[00:27:25] **Tim:** So what are we, So they're technically not supposed to age discriminate, but, you know, you know, that's part of the calculus when they're looking to hire people.

[00:27:35] **Adam:** So, what's your next one?

## [00:27:36] Do Market Research

[00:27:36] **Tim:** so this, this is a big one. This is actually the first one when we came up with this topic that I thought of is, is, you know, engineers, we'd like to build cool stuff, right? Regardless of its usefulness. And I can't tell you the number of times where we've added a feature or a function or built, you know, a whole new product from scratch and said, you know, this is going to be the best thing ever.

[00:27:58] **Tim:** And everyone's going to buy it. And then you launch it and it's like crickets.

[00:28:04] **Adam:** Yeah. Mm

[00:28:04] **Tim:** Right. Or you, you demo it and they're like, people are like, Oh, that's pretty cool. But yeah, I don't know how I'd use this or, Oh, that's pretty cool. But there's, you know, there's no way we can pay what you're asking for. And so I would tell, you know, my younger self being my younger self in my actual job.

[00:28:20] **Tim:** So I'm, I'm now younger, but I'm employed and, you know, in charge of like helping build the product roadmap, I would say, go get a market assessment. So market assessment, you know, there's companies that will go out and look at, you know, what's on the market now. What are the features that are out there?

[00:28:37] **Tim:** What are people buying and what are they willing to pay for it? And, and how saturated is that market? because I had, today I had a meeting with one of our, leading, marketing guys and he had a good analogy. He says, you know, your, your company is kind of like, Your company, your product offering is kind of like a party, right?

[00:28:57] **Tim:** So you're having a party and, you know, you have a party theme. And so in order to, you need to know, are there people who are actually kind of interested in the party? That you're throwing, right? So you're doing a pirate themed party. So how many people out there who are like into pirates and want to dress up like pirates and come to your party?

[00:29:17] **Tim:** You know, if that, if that is huge, that's awesome. And then that's, so that's kind of like, you know, your product and then, but then once you get to the party, you know, how good is the, is the DJ really good? Well, that's kind of like your customer service. So they come to your party, then you also need invitations.

[00:29:34] **Tim:** So that's kind of like your marketing. You have to have a really good invitation that explains, Hey, this is a pirate party and here's what we're doing and here's what we're going to do. And, and then it's going to happen. So it's like a market assessment kind of help. Once you have those things, you have something that, that people actually want, they can actually pay a fair price for that you can accept.

[00:29:53] **Tim:** And then once they have it, you know, it's actually good enough that they want to stay with it. Then you have all the pieces. But so many times, and I think Google does this a lot, you know, particularly when they were really heavy into doing the 20 percent thing where people would just work on something that people would be like, engineers like, you know what?

[00:30:12] **Tim:** This sounds cool. I'm going to build this thing. And they build it and they launch it and it's cool. People use it. But then, you know, people don't want to pay for it or pay for it. You know, other, whatever reasons and they just kill it. There's so many things that Google kills. And I think that's the reason it's like, they don't really know if there's a market for it.

[00:30:27] **Tim:** They just build it because it's interesting. We've done that as well. So I tell my younger self, go, go spend the money. You're going to, what you're going to throw away sales and marketing dollars, trying to sell this product that may not have an audience or may not fill their needs or, or may not be the price point that you think it's worth.

[00:30:48] **Tim:** So do that first, spend that money there. And once you know that you have all those things, then put a whole lot of money in sales and marketing.

[00:30:56] **Adam:** Or get you a sugar daddy like Google to pay you to, to build that stuff so that you can just try it out. And,

[00:31:02] **Tim:** That's nice. If you have one product as a cash cow that can like, you know, fund all these other little side projects, that's great. But yeah, I don't have that luxury.

[00:31:10] **Adam:** that's an interesting perspective. Like kind of Google is like their own, VC, right? They just make small bets on a thousand different little products. And if two or three of them hit, then they end up making money. In like net.

[00:31:24] **Tim:** But I can't try to think what product other than their advertising really has done that. It's the same thing with AWS. It's, it's their, it's, or Amazon, it's their hosting. That's their, it's their data stuff that, that makes all the money. Even like the TV shows and all that, it's all being funded by that side of the house.

[00:31:45] **Tim:** A lot of other stuff just loses money. So. Don't be like them.

[00:31:50]

## [00:31:50] Don't Tie Your Identity to a Programming Langauge

[00:31:50] **Adam:** So here's another don't. I, this is a mistake that I made pretty early on in my career just because it was comfortable. And I think one of the lessons, let me just say it before I get too far off on topic here. don't, don't tie your identity to a programming language, right?

[00:32:05] **Adam:** That was a mistake that I made early on in my career. I, and as a matter of fact, if you go back to episode one of this podcast, that's exactly what I was talking about. I tied my identity to ColdFusion, CFML programming language. And I was, I, I boxed myself in as a CFML developer for like over 10 years, which was fine.

[00:32:23] **Adam:** you know, I couldn't see it at first, but CFML was sort of on the decline at the time and. it kind of meant that like, I was a little bit specialized and I could, you know, if I could make myself one of the, you know, top 10 percent or top 20 percent of developers doing CFML, then I could demand a little bit more of a premium in my salary, right?

[00:32:44] **Adam:** and be in a little bit more demand, which is cool. You know, I mean, there's still people doing that right now with like COBOL, right? Like, COBOL developers are laughing all the way to the bank, and also waiting for their retirement to come. But,

[00:32:57] **Tim:** surprised that's still alive. Honestly,

[00:32:58] **Adam:** yeah, but, it, I do think that it kind of held me back, in, in my career and my growth.

[00:33:05] **Adam:** Right. I, I think, I feel like if I hadn't, Identified myself as a ColdFusion developer. And if I, if my identity was more just like, I'm a web developer, then I would have,

[00:33:14] **Tim:** a little more general, not, not a complete generalist, but you know, not so laser focused on one particular thing

[00:33:22] **Adam:** Right. I feel like if I had just had that slightly broader worldview, I would have picked up on things earlier and I, I would have had more opportunities, right? Different jobs would have become available to me. and I don't know, it feels like there is an unexplored, or a missed opportunity.

[00:33:40] **Tim:** and I think a lot of people, and you know, I met you at ColdFusion conferences and Adobe conferences and things like that. And, and several, I think there's many people who kind of fell into that, you know, bin, you know, for all his, you know, ColdFusionFanboying, at least he named his blog Ben Nadel.

[00:33:59] **Adam:** Yeah.

[00:34:00] **Tim:** But I think about like Ray Camden, who was, who worked for Adobe for, it was an evangelist for them.

[00:34:06] **Tim:** He, he, he was, he, his website was blog was, ColdFusionJedi or the CFJedi. And then one day I noticed he changed it. It was RayCamden. com. I'm like, or RaymondCamden. com. I'm like, why'd you change it? And it's the same thing. He's like, you know, I focused too much on that one. I need to be more broad, a little more, I don't want to pigeonhole myself into one particular product.

[00:34:27] **Adam:** Yeah, mine was the exact same situation, right? I was, my, my blog was at Fusion Grokker,

[00:34:32] **Tim:** yeah, I remember that fusion. Yeah,

[00:34:34] **Adam:** you know, and I moved it to AtomTuttleCodes.

[00:34:36] **Tim:** I was, I was the same. I had, cfmumbojumbo. com. That was my, yeah. But now I just have timothycunningham. com. It's just cooking, cooking videos on there. So yeah, that's good advice because, you know, kind of one of the other things both of us put on our topics of, advice, bet on JavaScript, put tying yourself to one particular technology. You never know when that thing's going to fall out. Like, think about the poor people who did Flash and did, what was the other thing? Silverlight. Yeah, those, those technologies. Like they, people who really tied their, their star to that, that, tied their wagon to that star, if that's the phrase. yeah, those are, those are dead, completely dead.

[00:35:17] **Tim:** So they had to move on to other stuff. So if you maybe be a little bit more general and you happen to mention those other things

[00:35:24] **Adam:** right.

[00:35:25] **Tim:** or whatever it is you're doing as part of your identity, It's easier to move away from that when it dies.

## [00:35:32] Bet on Javascript

[00:35:32] **Adam:** Yeah, for sure. Yeah. I mean, and that, it's funny how, you know, this one kind of, in some ways goes directly against, the last. One, you know, instead of don't tie your identity to a programming language, we're saying bet on JavaScript, which is like the exact opposite, right? I think now, a callback to a previous episode, JavaScript of the web, right?

[00:35:54] **Adam:** Like, you Even if you're going to, there are other options, right? You can write in Rust or Clojure or whatever, and it compiles down to JavaScript, but at the end of the day, it's still JavaScript running in the browser. And I think, you know, maybe in the next 10 years, we'll probably see Wasm, making it possible to skip the JavaScript step and just go sort of straight to like a, a browser binary bundle.

[00:36:16] **Tim:** I think the, the bet on JavaScript is kind of just the joke of the fact that, you know, we're giving our younger selves the inside information rather than just general career advice. Right. We're just, we're, we're, Marty McFly with the, with

[00:36:29] **Adam:** The Almanac.

[00:36:30] **Tim:** it was, yeah, with all of the sports book and then, you know, Biff getting it and becoming rich, it's that kind of thing. Don't tie yourself to a language, even if it's JavaScript, because, you know, 10 years from now, it might be something else.

[00:36:42] **Adam:** For sure.

## [00:36:43] The Peter Principle

[00:36:43] **Tim:** so I would tell myself, so, and it just kind of ties into my failure, the whole Peter Principle thing, and where you, you know, when you're young, you just, you really want to kind of keep moving up the ladder, right? You want to see progression. You want to level up in your career.

[00:36:59] **Tim:** And unfortunately there's a bias in pretty much every industry. So like, let's say you're a sales guy, you know, selling vacuums. And you're the best sales guy in the region. And you know, the company's like, you're the best. You're awesome. We're going to promote you. We're going to put you over all the sales people in, you know, the North America division.

[00:37:20] **Tim:** Well, now you're no longer really a sales guy. You're a manager of sales guys, and you may not be a very good manager. So, so that's the Peter principle in a nutshell. It's not that you're incompetent and you got promoted and everyone now knows your dirty secret that you're incompetent. It's the fact that. You got promoted to do a job which doesn't really fit your skill set. And so now you're incompetent at your job because you're not a people manager.

[00:37:47] **Tim:** And that seems to be companies look to promote people. It's like, okay, well, you're a really good sales guy. We're going to put you over 15 salespeople and things are going to be good. And that's just not how it works. Like typically you move a person in that position and all the salespeople do worse.

[00:38:04] **Tim:** Because, and that, so I would tell myself. Is C-level aspirations, trying to be in the C-suite and being in the CFO or the CTO or the CEO particularly. It's probably not the job you think it is, it's probably not the job you really, really want.

[00:38:23] **Adam:** Yeah. I feel attacked.

[00:38:24] **Tim:** I'm sorry, I, I'm talking to myself here. I don't, I'm not talking to young Adam. I'm talking to young Tim.

[00:38:30] **Adam:** all right. I was just making a joke.

[00:38:31] **Tim:** Yeah. So I mean, you, you wanna be important, you wanna be respected, you wanna be recognized for your job, and you think, well, the only way to do that is to get to that. That's the top of that mountain and you're the boss of everybody.

[00:38:44] **Tim:** But for certain type of people, and I think I'm one of them, that's not very fulfilling.

[00:38:49] **Adam:** Yeah. I think that's a failure of career laddering, right? Like it's just a, it's a bad ladder when you are kind of forcing somebody into a job that they are unprepared for and not necessarily interested in.

[00:39:03] **Tim:** Yeah. And I think it's a fair just sort of, because so many companies do this, that's the only way to so, you know, so called progress is to move from being an individual contributor who's really, really effective to being a manager of individual contributors. And that is a completely different skill set.

[00:39:24] **Tim:** So,

[00:39:25] **Adam:** Yeah. I want to, so I, on my pre prepared list, I'm out of items here, pieces of advice, but I do want to go back to one that you brought up earlier. You had said. you know, kind of to rephrase it, I feel like what I heard was, Pay more attention to what you're getting out of the job. Like whether that be total compensation or, or something like that, not so much like what is the company that I'm working for producing, but like, what am I getting from the company, whether that's, you know, the fun projects or whatever to work on, in some ways I can relate to that, like, you know,

[00:39:59] **Tim:** I mean, you should still completely believe in the product you're

[00:40:01] **Adam:** sure.

[00:40:02] **Adam:** Right, right. Don't, don't go work for the political party that you, is like on the exact opposite end of your spectrum, just because they're gonna pay you more, because you'll, it'll crush your soul. But, you know, maybe, work at Facebook because they'll pay you more, even though your heart is really in a particular political campaign that just can't afford to pay you whatever, right?

[00:40:24] **Adam:** There's a certain amount of truth to that. And I, I can relate to it because like, you know, I work in higher ed, my heart is not in higher ed the same way that Steve's is, you know, Steve started this company because he was, an alumni volunteer, you know, with his alma mater and he saw the software that they were using, failing them, like the, the staffers that were coordinating with the alumni volunteer people and all that.

[00:40:50] **Adam:** And he just saw an opportunity to like, Let's make these staff people's lives better and also make money in the process. And so that's, you know, it was, it was very much like born out of his own experiences and his needs. And for me, that's fine. I have absolutely nothing against that. And I, you know, I guess I, I.

[00:41:09] **Adam:** Find a little bit of like satisfaction in knowing that those people's lives are better. The part that, you know, makes me for lack of a better word, tingly, that tickles my brain in the right way to make me happy with my job is the, the technical challenges that I get to solve, the scaling problems and the, the different, you know, just problems in general, whether it's scaling or something else, you know,

[00:41:34] **Tim:** And that was sort of what I was trying to say is like, so young Tim really thought video games, because I love video games so much, I wanted to do that, but really, I figured it out that really, I love the coding actually more than the gaming. So there was like old, old game called Ultima Online.

[00:41:50] **Tim:** It was one of the first like massively multiplayer MO, yeah. Right. And so it started to kind of wane. And then they started building these emulators where you could actually get a computer hosted and you had to have people come online and play with you. And so me and a friend got together and we like built this online server called FallenAshes.

[00:42:12] **Tim:** com. Might still be out there, but anyway, it's probably on the Wayback Machine. And so I thought it was, Oh, this is great. I'm going to, so I programmed, you know, it was a sort of like a framework where you could program it and start building stuff. And I found, I spent more time just kind of programming than actually playing the game.

[00:42:29] **Tim:** And it kind of taught me, it's like, you know what, it's the programming I like. It doesn't really matter what I'm programming. You know, in that case, I kind of was programming a game. I was, I was programming an emulator, but I wasn't building it from scratch. I was kind of using a toolkit that already existed.

[00:42:43] **Tim:** And, so, so that's kind of what I would say is that, that the enjoyment, if you're a programmer is not necessarily the thing you're building for Steve. Maybe it is, you know, he enjoys like solving the problems of the. Alumni issues. Cause he really loves that. But for you and me, like if we were working, you know, we're working for him.

[00:43:03] **Tim:** It's like, we're just trying to solve the problem of scaling of, you know, making it look good, making sure that, you know, it's, it, it doesn't break every time you change things.

[00:43:13] **Adam:** mm. Yeah, the, the challenge of making the software, flexible enough to support the business needs for 10 plus years, like, you know, the working on multi tenant stuff that I talked about in the past and all of that, like that's just been, you know, the, that's been the cherry on top for me, right? Like those are the things that make me excited to get out of bed in the morning.

[00:43:38] **Tim:** yeah. So you went on the Wayback Machine and found it. Yeah, that, that's the site I designed. That was one of the first sites I was really proud of designing. It's kind of cheesy looking now, but that's great.

## [00:43:51] You Don't Have to be The First To Answer

[00:43:51] **Tim:** So. I got two more, two more that I'm going to tell myself because, you know, I made a lot of mistakes as a young person. Number one is you don't have to be the first to answer every time.

[00:44:03] **Tim:** It's a character flaw that I have. I like to be, I have a very quick, or at least I did, I'm getting a little slower on my pace as I got older, but I had a very quick wit and response time when it comes to hearing a question and answering it. I love quiz bowls and stuff like that where you have to answer something very, very fast.

[00:44:21] **Tim:** And I, I was that way in everything in my life, like if I heard a problem, I didn't stop and think about it. I just immediately, you know, from the gut, shooting from the hip, just said, I gave an answer. And sometimes it was right and, you know, but a lot of times it was wrong. And, and, but I always just kind of focused on the times I was right.

[00:44:41] **Tim:** And, and so, and then a lot of times I found that because, and I learned this later in life, that because I was so quick with an answer that sounded good. People who were not as ready to jump out there and, you know, give their opinion or, you know, their two cents worth would withhold their thoughts.

[00:45:05] **Tim:** They're like, well, Tim already answered that. And a lot of times the thing that they had to say was actually much better than mine and more well thought out because they had actually been thinking about it. And I was just trying to hit the buzzer first. So I'd tell myself, you know what, you don't have to be the first to answer every single time.

[00:45:22] **Tim:** Sometimes just, you know. Hit the brakes, listen to what has to be said, and then, you know, put your two cents worth in if you need to. Sometimes you don't need to, what you were thinking of got answered. And I would have, could have saved myself a bit of a headache through many points in my career.

[00:45:42] **Adam:** I agree. I, it's definitely, I, I feel like the type of person that is drawn to this job is the type of person that has that personality trait that like is excited to be able to share the knowledge that they have. And so they're, they're quick on the draw, right? They, they want to jump in and answer all the questions or, or point out when somebody's wrong.

[00:46:02] **Tim:** Right. Yeah.

## [00:46:02] Stay in Touch with People

[00:46:02] **Tim:** And then finally, keep up with your important contacts and relationships. There's been so many really cool people that I've met through the Throughout my career. And I'm just not, and this is just another personality. I'm not the kind of person to kind of like keep their name written down somewhere and like, you know, keep track of them.

[00:46:22] **Tim:** It's like, I deal with the people that are in my circle. And when my circle changes, I just, they, they don't exist. I mean, maybe I do have

[00:46:30] **Adam:** working memory.

[00:46:31] **Tim:** yeah, I have object permanence problems, I guess.

[00:46:35] **Adam:** People

[00:46:35] **Tim:** But there's, Yeah. People per minutes. It's like, but there's people it's like, after it's like, you know what? Someone points out, well, you know, so and so why don't you ask them?

[00:46:44] **Tim:** I'm like, Oh yeah, I didn't think about that. But it's like, it's been years since I talked to them and I don't want to be the person who's just like, anytime I need something, I keep in touch with, Hey, how you been? Hey, sorry to, sorry to, you know, it has been a while, but, can I ask you something? Could you do me a favor?

[00:46:59] **Tim:** Cause no one wants to be that person, but, but if I've been keeping up with them, And, you know, keeping track of their life and like, you know, just at least stopping in to say hi, I would feel better about it. I think Facebook has kind of helped with that because there's people that, you know, I follow on Facebook and comment when I talk to them, but it's like, I haven't done that very well in the industry.

[00:47:20] **Tim:** Facebook tends to be more my friends in the industry. It's like, there's people that I've met that have been really, really cool, you know, people in the industry who really have done some amazing stuff

[00:47:33] **Adam:** Thanks. That's very nice of you to say.

[00:47:35] **Tim:** Yeah, like Adam,

[00:47:36] **Adam:** I'm just

[00:47:37] **Tim:** like Adam and, and Ben and Carol. But it's like, you know, if you don't keep up with them, you know, you, you don't, you never know, you never know when someone like that is going to be able to come in and help you with, with something to like save your bacon. And you them, right? It's a two way street. Like you might find out that they're dealing with something you can help them with that. And so I would tell myself, just be a little more aware of the relationships with people and keep in touch with people. Don't burn. It's not even burning bridges. It's just neglecting, neglecting the bridge.

[00:48:12] **Adam:** Yeah. I mean, I agree, but at the same time, like there's only so many hours in a day and it feels like there's already more demands on our time than is reasonable. Like it just, I think society expects us to be on more than it did 20 years ago, right? We're expected to be productive. For a much larger percentage of our waking hours than we were, than it expected of us previously, and I think that that leaves us with less time to nurture those, you know, those bridges.

[00:48:49] **Tim:** Yeah. Yeah. I, I just know there's certain people that I'm like, man, I wish I had kept up with them

[00:48:54] **Adam:** Yeah,

[00:48:54] **Tim:** and I haven't. And it's like, I feel like it's just too late to, to rekindle. It may. Maybe that's my fear. Maybe I just need to hit them up and say, Hey, how's it been? And it might be like old times and it'd be great, but I don't wanna wait until I need them for something. But that being said, if someone calls me and they just need something, I, I have zero problem with that. I get it.

[00:49:15] **Adam:** somebody that you know. Of

[00:49:17] **Tim:** that we, we have a relationship, haven't talked to them in like six years and they're like, Hey, Tim, I have this payment problem. I really need your help. I will drop whatever I'm doing and help them.

[00:49:27] **Tim:** If not like, Oh, Joker, you, but some reason I feel that that's the way people would think about me if I did it.

[00:49:33] **Adam:** course, that's very human.

[00:49:36] **Tim:** and Tim, watch out for hot models. They're not worth the time. They

[00:49:41] **Adam:** That's not so much career advice as just life advice, but

[00:49:44] **Tim:** Yeah. Yeah. I just had to slip that little note into Tim before. Yeah,

[00:49:48] **Adam:** before the time machine brings us back.

[00:49:50] **Tim:** exactly.

[00:49:50]

[00:49:51] **Adam:**

## [00:49:51] Patreon

[00:49:51] **Adam:** All right, well then this episode of Working Code is brought to you by the lingua franca of the internet, JavaScript. Listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:50:03] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock. And Triumph. I didn't touch my glasses while I went through that paragraph tonight.

[00:50:19] **Tim:** Do you normally do that? I've never

[00:50:20] **Adam:** I always push them up my nose, like, at the bridge of my nose here, like, as I'm reading the second sentence or something. It's weird, these habits that I notice myself building. Anyway, after show tonight, I don't know that we necessarily have anything particular planned, but we'll figure something out.

[00:50:35] **Adam:** I'm sure it's going to be interesting and fun. so if you'd like to find out what's in the after show, you're just going to have to become a patron of the show. How do you do that? You go to patreon.com/workingcodepod, throw a few dollars our way every month, as little as 4 a month, or, or even less than that, if you're going to pay for a year at a time, we were really appreciate the support helps keep the lights on and the mics on, and.

[00:50:57] **Adam:** you know, we just, that's it. We, we appreciate it. We try to return the favor with, aftershows and we, it took me six months, but it did get the stickers out to everybody

[00:51:09] **Tim:** Good job.

## [00:51:10] Thanks For Listening!

[00:51:10] **Adam:** anyway. also, if you're interested in hanging out with our community, go to workingcode.dev/discord, join our discord server. It's like Slack, but more fun and better for communities.

[00:51:21] **Tim:** For sure.

[00:51:22] **Adam:** Love to have you, and that's going to do it for us this week. We'll catch you next week. And until then,

[00:51:26] **Tim:** Remember your heart matters. Your young heart matters. Your future heart matters. You just matter. Dammit.
