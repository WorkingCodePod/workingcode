---
title: "091: Side Project Therapy"
description: "On last week's show, we talked about Side Hustles. On this week's show, we want to talk about the flip-side to that coin: the coding that we do on the side because we freakin' love coding!"
date: 2022-09-07
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/091-side-project-therapy/id1544142288?i=1000578687549"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

On last week's show, we talked about "Side Hustles" - those extracurricular activities that we do in order to earn a little extra income. On this week's show, we want to talk about the flip-side to that coin: the coding that we do on the side because we **freakin' love coding**! Carol celebrates the WordPress site that she's built and now maintains for her son's band, including the ability to accept payments and donations. And, Ben talks about trying to build a feature flag system using Lucee CFML and Angular. He also confesses that his blog has historically had a negative impact on his resolution to do more exploratory work. We also get to argue a bit about _just how sexy_ TypeScript actually is.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/091-side-project-therapy.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** It's interesting that you say that because I actually used to have an ask Ben form on the.

[00:00:05] **Carol:** Mm-hmm

[00:00:06] **Ben:** And I did get quite a number of submissions and it honestly was just overwhelming.

[00:00:10] **Carol:** oh yeah.

[00:00:10] **Ben:** I felt like I was drowning under it and you know, but likelots of stuff make me feel like I'm drowning. if I get an email from somebody that I have to respond to, like, I feel like I'm drowning.

[00:00:22] **Ben:** So it's, it's a very low bar

## [00:00:45] Intro

[00:00:45] **Ben:** Hello everybody. And welcome to episode 90, one of the working code podcast. On today's episode, we're gonna be talking about side projects, but first let's get into our triumphs and fails. Unfortunately, Adam and Tim cannot be with us today, so it's just gonna be us and Carol kicking it duo style, and I'm gonna throw it over to Carol for her triumph for fail.

[00:01:07] **Carol:** Let me just go back a second. You should have said fortunately. Adam and Tim aren't here today. So you're gonna hear a lot of Ben and Carol. that's what you meant to say. I'm pretty

[00:01:18] **Ben:** get to see us shine today, which is nice.

## [00:01:21] Carol's Triumph

[00:01:21] **Carol:** all right. Well, I'm gonna start us off with a Trium last week, actually, it's been going on for a couple weeks. I was kicking off this project, doing all the. For it had starting build had started building out the tech doc. my design buddy went on vacation for two weeks, so woo, woo. Congrats to him.

[00:01:38] **Carol:** Right. So he took some time off and I was gonna have this tech doc done when he got back, have the majority of the answer of the questions answered and starting tomorrow, we were gonna be probably pretty close to hands on keyboard to code this project. Well, I've had a few things going on and, It just kind of got away from me a little bit.

[00:01:59] **Carol:** I got everything done, but I decided that rather than being selfish and coding this project that I really, really wanna do, cuz it's so much fun and it's gonna be exciting to work on. I gave my work to another engineer, so him and another engineer are gonna be the ones actually coding it. So I gave away my fun project.

[00:02:18] **Carol:** I'm still gonna get to work on it a little as far as. I built out the tech doc. So I know all the questions and answers. So we'll also be meeting with them and going over what they're doing. That's so fun and I'm not gonna be coding, but I don't feel bad about it. Like at first I had a little bit of, I don't wanna give this away.

[00:02:34] **Carol:** Like I wanna keep this baby to myself. Like. The fun project, right? Like the good one wanna do it. And I was like, all right, well, I'm gonna give it to the new guy and he's gonna work on it with a senior engineer and they're gonna get to pair up on this and they're gonna learn a lot and they're gonna have fun doing it and I'll go do something else.

[00:02:53] **Carol:** So no resentment actually feel great about giving it away. And that made me proud of myself that I gave away some fun work without feeling bad.

[00:03:01] **Ben:** That's a very emotionally mature. And, uh,I know you're wearing the manager hat and the engineering hat, so it's nice that you're doing, I don't wanna say what's best for the team, but you're thinking about the team and, that's a, that takes a lot of work. I'm someone who is very emotionally invested in myself and my own code.

[00:03:21] **Ben:** And, to me it feels like giving away a baby.

[00:03:23] **Carol:** it did a little, because I was like, I really wanted to do this project because it's one of the first ones that we actually are gonna spin off of legacy. So it's something that we could keep in the legacy app, but why put it in there? Like, let's go ahead and spec everything out and let's take it off and have it be standalone because it really doesn't fit with another service that we're doing already.

[00:03:44] **Carol:** It's new. So I could put it with legacy or I could go ahead and. Spinoff. So I was super excited to be doing the first big spinoff that we are gonna be using on legacy and the new app. And yeah, I got excited. And then I was like, look, it's not fair for me to only be able to code 30 or 40% of the time and then have this other engineer relying on me when I'm not even like gonna be around to help as much.

[00:04:08] **Carol:** So yeah, the way, yeah, my thing that's me. What you got Ben.

## [00:04:15] Ben's Triumph

[00:04:15] **Ben:** I'm also gonna go with a triumph and that is that I feel like lately I have been on a roll. Doing the simplest possible thing to solve a problem. and it's hard to do. It sounds like you should always want to do the simplest thing because it's the least amount of effort, theoretically, but there is something so alluring about building the robust solution that solves the problems I don't even have yet because you start to think about the future and how things might evolve or how things might need to adapt.

[00:04:49] **Ben:** And because of that, you start to add a lot. Infrastructure and mechanisms that account for those future changes before you even have them. And, I think I've gotten really good and I'm hoping this is a side effect of maturity and experience, but I just feel like I've gotten really good at telling myself you don't need this.

[00:05:08] **Ben:** You don't have this problem. Do the simplest thing that works. And maybe in the future, you'll have to change it, but you don't have to change it today.

[00:05:16] **Carol:** Yep. It's that whole, keep it simple, stupid, right? Like, just keep whatever you're doing. As simple as possible, get it out then, you know, iterate on it, then grow it. Then find what your challenges are because whenever we start solving that big problem, that might have never been a big problem.

[00:05:34] **Carol:** We just added so much more complexity to you that we've now introduced, like introduced, introduced like the potential for even more problems. So yeah, I get it.

[00:05:44] **Ben:** and I think there's always a fear in the back of my head that I'm gonna run into a problem that I'm not gonna be able to adapt to.

[00:05:52] **Carol:** Yeah,

[00:05:53] **Ben:** and so far that has not happened. I have definitely gotten midway through a project and realized I didn't account for something

[00:06:00] **Carol:** sure.

[00:06:01] **Ben:** new evidence came to light. And now I have to pivot slightly on how I'm doing something.

[00:06:05] **Ben:** You know, the biggest shift is always what happens if I have to run a database migration. And now I have columns that I would've liked to have had previously, and I don't have them now, but you know what? You just, you deal with it and you, I have default values. Yeah. You figure it out. And, uh,and it's never the end of the world.

[00:06:20] **Ben:** And, leaning into that acceptance of the unknown, I think has just been really helpful. Actually. I was listening to a podcast the other day. I wish I could remember what podcast it was. I wanna say maybe it was the change log. I don't think it was though. Anyway, they were interviewing a guy who is a programmer today, but used to actually be a professional orchestra musician.

[00:06:44] **Ben:** And he was talking about mastery and, and he was saying something I thought was. Fascinating. and like, I didn't think it felt obvious at the time, but it, but the more I think about it, the more it hits home for me, he said, mastery is not about not making mistakes. He said in every professional performance he's had just about, he's made a mistake.

[00:07:02] **Ben:** Everybody makes mistakes all the time. He said, mastery is about not panicking when a mistake happens and being able to adapt and be agile in the moment.

[00:07:12] **Ben:** and I feel like. That's obviously something you have to practice and that comes from practice. and I feel like this using the simplest solution first, and then just adapting when needs arise, I feel like is helping me become a better programmer.

[00:07:28] **Carol:** I could see that I used to start every project with, at the bottom of our tear sheets of like, Hey, this is kind of what we're thinking about doing. They give us a high level of here's the problem. Here's what we think we kind of need to solve it. Tell us what you think we need to solve it and how like you can help with some of these points.

[00:07:47] **Carol:** Right? So at the very bottom of these sheets are like a question section for the product owner. I used to start every one of those. What about this? What about this? What about this? Like just listing out every possible question. Now I find myself starting to do that and then pulling back and going, you know what?

[00:08:05] **Carol:** I'm gonna ask the obvious ones. There is another product that touches this. Like, how is this workflow gonna change? That's one thing, but needing to understand every possible outcome is no longer a requirement for me up front. I am able to kind of go, okay. When we find that this thing happened, we'll ask and we'll have the conversation, but I don't start with 20 questions at the bottom of the tear sheet.

[00:08:31] **Carol:** Now that are. What about, what about, what about cause I'm like, all right, let's try to go smaller and let's just get it out and let's iterate on it.

[00:08:39] **Ben:** a thousand percent. And that really hits home for me because I used to. it's almost like I didn't ask questions. it was like, I was trying to find reasons that something wouldn't work

[00:08:50] **Carol:** Me too. That's my thing.

[00:08:51] **Ben:** oh, and like, But I just feel like I used to be such an about it.

[00:08:56] **Ben:** Like, I'd be like, oh, well, yeah. I'd be like, oh, well, that's interesting. But it doesn't work for this type of user in this specific edge case. So clearly none of this is gonna work.

[00:09:08] **Carol:** Not possible.

[00:09:09] **Ben:** Right. and I just, oh my God, it, I feel so embarrassed that I used to have conversations like that because today I'm so much the opposite direction where I'm like, this looks like now.

[00:09:22] **Ben:** And I don't know what it's gonna look like in the future, but let's just get it out there and see what happens.

[00:09:26] **Carol:** Let's try it. And I do think that's maturity and it's becoming more comfortable in yourself. And in your ability to handle those crisis right early in my career, I couldn't handle the crisis. I would have been like,

[00:09:39] **Carol:** Everything's on fire. I don't know what to do. I would be like wailing around probably like, just not certain of myself. Now when things break, when they go out, I'm like, cool. Is this a candidate for rolling it back? And letting me take a look or you wanna give me a couple hours to debug it in production?

[00:09:56] **Carol:** Like what route do we think we need to do? And here's throughout. I think we need to do. And I'm just more calm in the emergencies than I ever was. So I do think that plays into it as well.

[00:10:07] **Ben:** Yeah. and I feel like, I feel like I was pushed into this. I, in that, so as I've talked about many times on the show, I'm on the legacy team, all of my managers have quit. All of the designers have gone to the new platform. I have no oversight, but I also really have no help. I don't have anyone who can jump in and say like, actually let me help you with that design.

[00:10:26] **Ben:** And so, because of my. Lack of ability when it comes to some of these more peripheral, coding, adjacent responsibility, like design, like user interaction, like information architecture. I'm like, What you get is what you get, because this, like, I'm at the, I'm at the top end of my abilities right now.

[00:10:43] **Ben:** So, I'm maxing out here, so you get what you pay for essentially. And, but, but, but Ithink like, because of that constraint, because of that forced, lack of resources, it's like it's forced me to adapt and that's, uh, I just feel, I feel so much stronger for it.

[00:10:57] **Carol:** yeah. Well, great job. Will you trying

[00:11:00] **Ben:** Yeah. Yeah.

[00:11:01] **Carol:** from it? Yeah.

[00:11:02] **Ben:** Indeed. All right. So, so side projects. So, so in our last episode, we talked about side hustles, which I think was more about, paid. Kinds of things, but I, we wanted to kind of extend that conversation and have a side project, which is not necessarily a paid concept. This is just what we do in our free time.

[00:11:21] **Ben:** Cause I think a lot of programmers though, not all, do like to do some sort of coding in our spare time. And and we thought that'd be worth an additional conversation.

[00:11:30] **Carol:** Yeah, I think that's a great one to chat about. Do you me to kick us off

[00:11:33] **Carol:** with

[00:11:33] **Ben:** let's do it. Go.

## [00:11:34] Carol's High School Band Website

[00:11:34] **Carol:** So a few years ago, my son was starting high school and joined the band because, as a nerd, you raise nerds and that's what you're supposed to do. And mine are great nerds. So I got involved then became the best man, like band mom in the world.

[00:11:49] **Carol:** Right. So his second year into band, I realized real quick that they lacked any ability to communicate with people. If it wasn't through a Facebook post. And I'm sorry, I hate Facebook. Like I try to stay away from it the minute my kids graduate, I'm deleting my Facebook account. Cause I have no use for it.

[00:12:05] **Carol:** Like right now. It's great for sharing pictures with family and seeing nieces and nephews, but it's not gonna be a thing that sticks. So I realized that they lacked the ability to communicate and for that communication to be at the fingertips of anyone. So I started by creating a website it's HoCo band.org.

[00:12:24] **Carol:** If anyone wants to check it out, it was. Like from the 1996 timeframe when I picked it up, which was that awful. If you went to a page, it had the yellow, like a construction cone on it that said this page is under construction and it was awful. So I was like, you know, what do I leave there? Do I play with it?

[00:12:46] **Carol:** So I played with it. And at first I started coding something and I was like, oh, I could do this complex. And I could build my own content, like solution. I could code a hell out of this. And then I thought about the use case for it. So I need a band director to be able to share information to people. I need five or six people to be able to publish documents, to get information out about a trip, to show pictures of what we're doing to embed a stream of all of our Twitter post and of our Instagram post.

[00:13:19] **Carol:** And eventually I need a way to be able to take payments and, make orders for like band merchandise and stuff. So after spending a little of the time thinking about what I wanted to do. I just threw up,

[00:13:31] **Carol:** a WordPress account and put 'em on it and I just listed a domain and bought a template and changed the template to allow them to embed their own image.

[00:13:42] **Carol:** So it has the layout of everything you need, but we can manually change, the images to like match what we've taken recently. But I was able to take that and spend about two years working on it with the band and go, okay, what makes sense for you guys? Like me doing it all myself, just, okay. We added a calendar.

[00:14:01] **Carol:** What do you want the calendar to look like? And it was talking once a month. So after like we put it up immediately, like turned that thing on people were using it, it worked, it was fine, but over the next two years just spent time here and there just making it more efficient for them. So, now they're able to use PayPal and.

[00:14:19] **Carol:** Some other. Payment apps in there that are just embedded, that you just add the app that you wanna use and they can take payments. They can make orders. they can use Facebook marketplace on there to actually place orders that come from the group page. So I've been able to take that and teach people how to use it.

[00:14:37] **Carol:** And now all I do is if they have questions about things like, Hey, we want to do this new. Like email accounting thing, or we want to be able to have people subscribe to these like blog, like posts. How do we do that? Like, I'll go in and show them. But other than that, I just pay the domain registry fee each year and re up like subscriptions to make sure everything's there.

[00:15:03] **Carol:** And I have a reminder once a month to go in and make sure all the apps have been updated because they don't remember to do that. But, I mean, it just took a couple years to kind of get this project going and then get it done. And now they have a way to communicate. And I feel really, really good about that because after doing that, they were able to get their 5 0 1 C.

[00:15:21] **Carol:** and they are, considered a nonprofit and now they can take donations on there. So it's just given them the ability to achieve more than they had before.

[00:15:32] **Ben:** So one thing that strikes me as impressive is you did not fall into what is, I think the traditional developer conundrum, which is, should I just build this all by myself from scratch?

[00:15:43] **Carol:** Well, so I started there, right? So that's what I did initial like initially. But then I realized I only have a couple years with this program and I don't want them calling me monthly to figure out how to put new dates on the calendar, or I don't want them calling me going. We need to take payments.

[00:16:00] **Carol:** What do we do? Something isn't working. I don't wanna be your help desk. If you can't take payments, call PayPal and ask them why you can't take payments. Like don't ask me, like, let's call the vendor who we've set you up. So it was hard upfront because. The one thing I did do that was a little like, oh, my ego hit me was you have to pay more to have a business account and not have built on WordPress on the bottom of every page.

[00:16:26] **Carol:** And for the first couple years, I refused to have that logo on the bottom of it. Because I'm an engineer and I write code and I didn't want anyone that was associated like with me and knew what I did to know that I use WordPress to build this that went away real quick. Cuz I realized my ego was not. I had no reason to be like E about this, because the fact was that it's a smart solution for what needs to happen.

[00:16:51] **Carol:** Like they need the way to manage their content and they need the way to get the information out to all of these band parents. And we are not talking about like 90 kids in the band. We have 280 marching, so it's a lot of people to communicate with.

[00:17:07] **Ben:** it's interesting. you think that web development is just this general bag of skills, but there's so many different types of applications that you can build. and, the idea of building anything that takes payments, for example, It's like, if you don't, if you don't have that as something you've done before, that feels like totally new and kind of intimidating work.

[00:17:31] **Carol:** And I'm sorry, but if you're not scared by that process, you shouldn't be writing code, doing it. Like if you don't have this fear, when you're taking someone's credit card of, did I share everything up? is this possible for someone to capture the information as it's being submitted? Like, how am I storing this?

[00:17:48] **Carol:** If you aren't concerned, please don't write credit card payment software, like. Plug in an app and let someone else handle that for you. I hate when my credit card gets breached.

[00:18:01] **Ben:** Oh, my God. Yeah, I've gotten like six new credit cards over the years, just from, home. And target

[00:18:08] **Carol:** silly things. Yeah.

[00:18:09] **Ben:** get hacked. it's so interesting. when you're a young developer and you're really just starting out, you don't know anything. so everything that you have to do is new and you have to figure it out

[00:18:19] **Carol:** And exciting,

[00:18:20] **Ben:** it's exciting.

[00:18:21] **Ben:** and part of me and this also relates to the idea of side projects. Part of me is so used to knowing answers because I've worked in a particular area for so long and I've done a particular type of thing for so long that trying to solve a completely new type of problem. it's not exciting the way it used to be.

[00:18:42] **Ben:** It's daunting. It's scary. and like, it's so counterintuitive, you think, oh, well, part of getting good at this is getting good at learning. So you. Diving into something new would be even more exhilarating because like, oh, of course I can learn this, but everyone's gonna be unique here and this is just me, and my perspective, but I'm so used to having so many answers.

[00:19:04] **Ben:** and I don't mean that in any egotistic way. I mean, like, because I do a lot of the same stuff over and over again. That if someone was like, Hey, can you build me an e-commerce site? Or just a site where I could take donations? I'd be like, oh, that's very sounds.

[00:19:26] **Carol:** Yeah, I will say when we were doing, like, when I was doing the initial research for this project at work that I was talking about in triumphs and belts, whenever I've read the tear sheet for it, I immediately started Googling. I was like, this problem has already been solved. Like people are able to schedule appointments.

[00:19:43] **Carol:** Like, I don't need to write something in house to allow you to schedule an appointment. Like we should be able to buy this. And then when I start looking at the cost and I start looking at the use case for everything I'm. There's way too much stuff in these other software. Like, I don't want any of this.

[00:20:00] **Carol:** Like none of this applies to me. I just want them to pick times and me relay that to my people. So, okay. It makes sense for me to build it, but at front I was like, there's no way I will, I'm gonna build this. Like, I'm buying this, like this problem's already been solved by someone else. I'm not re resolving it.

[00:20:16] **Carol:** And then that changed my mind. I get it. I'm re resolving it.

[00:20:23] **Carol:** just to keep it simple though. It's just to keep it simple. That's why I'm re resolving it.

[00:20:27] **Ben:** There you go.

## [00:20:28] Effort / ROI Matrix

[00:20:28] **Ben:** I was listening to a podcast for the, code pen guys, Chris Coyer and, his co-founder and I don't remember his co-founder's name off hand and they, I guess recently passed their 10 year mark as a company.

[00:20:38] **Ben:** And they wanted to do a little retrospective on the, it was like the 10 things, the top 10 things that they've learned over the last years.

[00:20:45] **Carol:** Oh, that would be hard. Hard to build that list.

[00:20:47] **Ben:** and one of the things that they said, which I thought was super interesting, they talked about this, kind of effort versus payoff matrix. So if you think, if you have like a two by two square, one side is low effort and high effort.

[00:21:01] **Ben:** And then the other side is, like low return and high return on investment. And, they were saying that. Last 10 years. What they learned is that their sweet spot is the low effort, low return and the high effort high return. and that any kind of anything in the middle, they just wanna buy. They're like, it'd be kind of too hard to build by ourselves.

[00:21:23] **Ben:** And it's like a decent amount of payoff, but not a huge amount of payoff. it's not a good use of their time.

[00:21:28] **Carol:** Yeah.

[00:21:28] **Ben:** and I can understand the high effort high. Reward high payoff as being something like that's, maybe that's the core competency of the company. But what I thought was very interesting was that they included the, things that were low return on investment, but also very low effort to build like, just bang those out.

[00:21:46] **Ben:** And, I dunno, I just, it was, they

[00:21:48] **Carol:** I would like to know what some of those were. I would like to know what some of the products were or some of the projects that they considered low effort and low return, but that they justified doing. And some of the things that they were like, no, like we're gonna do this middle layer thing.

[00:22:02] **Ben:** I dunno, I guess at some point you, it takes more time to research something maybe and figure out what product, and then you have to integrate that product into your product. And sometimes just building it's easier.

[00:22:13] **Carol:** Yeah. A couple years ago we had that whole project going on with our autoresponder. I spent 30 days of work, probably just researching what solutions were out there and if it made sense to use those, it does take a lot of time to research when you're looking at things to buy. And I think at some point people give up and just start building and then you're in the bigger.

[00:22:35] **Carol:** Situation then, cuz the solution was already out there. You just didn't spend the time looking for it.

[00:22:40] **Ben:** autoresponders are really hard, especially just because I, I, I think in English, I'm a native English speaker. I don't speak any of their languages. And so if I have to write code that looks at the content of an email to say, is this an auto notification? It's like, there's certain patterns, but then if you check your email logs, you're like, oh wow, we got a lot of stuff coming through in German and in Spanish and in French.

[00:23:04] **Ben:** And they all have different language and that's a big problem. Any kind of text analysis is a big.

[00:23:10] **Carol:** Oh, huge. And that's why we didn't build that part. Right. So we use comprehend from Amazon. So we're using that to actually give us results of the content of email. So we're like, Hey. You tell us what you think this content is, and then we'll play with it from there.

[00:23:26] **Ben:** Yeah, I had to. So at the, at work, one of the things that you can do. Is,you can go online, you can post comments and then those comments get sent out as emails to other people that are working on your projects. And then those people can reply directly to those emails. And it'll post a comment in the comment thread online.

[00:23:45] **Ben:** And I have so much code that tries to pick out people's signatures from their emails. it's just like, I,

[00:23:53] **Carol:** hard to get a signature block out.

[00:23:55] **Ben:** Oh, my God. It's so hard. And there's so much variety and people put the craziest stuff in their signatures.

[00:24:02] **Carol:** Oh yeah. And then you'll have people who will respond from like an iPhone or from some other like non. None like desktop interface, like device or something. Anyways, point being it'll then change it all to just like plain text and good luck finding any encoding or any like deviation there between like, what was and what wasn't cuz now it all is identical and you're like F at this thing's no longer respondable it's now called manual.

[00:24:30] **Carol:** You go figure it out. yeah. And email seems so simple. It seems so simple because when you're in Gmail, You have a signature block inserted, right? Why can't they just put tags around that says signature block? Like, why is it that hard? Like that should be the norm. And I guess it's because people type in their signature block, but mine's save mine's inserted the same way.

[00:24:55] **Carol:** Every time I compose. And every time I reply that block should be so easy to grab and they don't make it easy for you.

[00:25:01] **Ben:** absolutely. I actually Googled for that specifically. Cause I, because when I was doing this email parsing, I was like, there's gotta be

[00:25:07] **Ben:** some sort of standard.

[00:25:09] **Carol:** there should be

[00:25:11] **Ben:** was like, there were like Gmail actually does do something, but it's not, it's like, it's not specific cross versions over time. And then it depends on how people do it.

[00:25:19] **Ben:** And sometimes it's a class and sometimes it's an attribute on a diviv kind of a thing.

[00:25:24] **Ben:** And,

[00:25:25] **Ben:** so are you still working on this, band site?

[00:25:28] **Carol:** Yeah. Yeah. if you go there now, it's still it's up and running and I've more so just trained new people on it. And whenever they have problems, like, a girl was trying to figure out just how to use the HTML, like editor.

[00:25:42] **Carol:** For posting, a blog post, ultimately it just kind of posts on the homepage. So she called and was like, I just don't understand what I'm doing. And I'm like, yeah, I'm like, cool. I'll either jump on a call with you or just come over to my house tomorrow night and I'll walk you through how to do this. So you have an understanding for it because me doing it doesn't fix anything.

[00:26:00] **Carol:** It just keeps it, just, it just delays, getting the answer. Right. So I do still work on it. I don't have to do as much tech things I don't have to do as many, like. Jobs for it, unless they want to add something new or if they wanna do a redesign, like they don't like the template structure anymore, then I would go through and help them.

[00:26:19] **Carol:** Re-skin it, I guess. And make the pages look different. But other than that, they mostly manage it themselves now.

[00:26:25] **Ben:** Nice mark of a good product.

[00:26:27] **Carol:** Yeah. I mean, it feels like I've done something that helped a lot of people and it's easy to use, so that's great.

[00:26:33] **Ben:** Very cool.

[00:26:34] **Carol:** Yeah. So what about you? What kinda side project you've got going on?

## [00:26:39] Ben's Feature Flags Project

[00:26:39] **Ben:** Well, I hesitate to call this a side project, but I think it, it is in a way it's just for me more or less, but, I've been working on my blog for the last like 15 years

[00:26:50] **Carol:** But

[00:26:50] **Carol:** you've made some big changes over the past

[00:26:52] **Ben:** Yeah, I get to, I get to grow it and I get to evolve it. and I upgrade the languages and I upgrade the JavaScript compiler and that kind of stuff.

[00:27:00] **Ben:** and I use it as a sort of playground that I can try out new techniques or experiment with new techniques or take things that I learned at work and then apply them here. And it's just try and keep things growing and modernizing. but it's, it has. A strange gravity to it. Meaning I've developed a rhythm where it used to be in the early days when I knew nothing.

[00:27:23] **Ben:** It was easy to write every day, because every day I discovered something new about programming and I'm like, oh, this is crazy. I can't believe it works this way. And over time, the cadence of that has necessarily slowed down a. and there's a weird, emotional reaction to that where I start to feel bad about not being able to write as much on the blog and it's like, I feel to some degree, like I'm letting myself down, I feel to some degree, like I'm letting other people down who, who might frequent the blog for information and.

[00:27:59] **Ben:** Because of that weird emotional life cycle, I've been much more hesitant than I would like to be in starting up other side projects because there's this opportunity cost where if I start to work on something else, then I know I won't be able to write as much because there's only so many hours in the day,

[00:28:18] **Carol:** Yep.

[00:28:19] **Ben:** but.

[00:28:21] **Ben:** I have recently started to work on a little side project for feature flags and just an exploration of feature flags and confusion. Heck yeah. and because of that, I've really done almost no writing on my blog in the last, I mean probably in the last like month and a half, I've done very little writing comparatively.

[00:28:37] **Ben:** And, that's a little terrifying and I'm still racked with guilt and I wake up in the morning and I'm morning is my quiet time. Like that's where my that's my alone time. And that's my,

[00:28:48] **Carol:** Like your reflection time.

[00:28:49] **Ben:** my, my R and D time, my coding time before people are awake, it's still dark out. I love it. and I still wake up every morning and think to myself, what can I write about today?

[00:28:58] **Ben:** And it's, and it's like. It's empty. My head is empty. I don't have, I don't have, a bunch of ideas ready to go. Or if I do have ideas ready to go, they're not simple.

[00:29:08] **Carol:** yeah. It's not a quick little post, right? It's gonna take some time to work that out. Yeah.

[00:29:12] **Ben:** So I like the fact that just recently I've been digging into this, feature flag stuff, cuz it, it has been a lot of fun and it has pushed me into that discomfort.

[00:29:24] **Ben:** Of not contributing to the blog and also not being able to bang something out quickly that I might then be able to write about

[00:29:31] **Carol:** Yeah. So I wanna know more about this feature flags project. what are you doing?

[00:29:36] **Ben:** So I, and this actually ties back to my triumph and that I'm, I've been trying to do the simplest thing possible. Mostly, I just want to do it as a thought experiment where I designed a, I started with a data type or a data structure of what a feature flag is. And if you can think about a feature flag is, it's a set of variants that get assigned.

[00:29:55] **Ben:** Whether it's like a true false variant or a numeric variant, or like a, any kind of JSON object. so there's a set of variants. And then there, those get assigned to a particular request and they do that because you pass an information to this feature flag system, and it runs that information through a bunch of rules.

[00:30:14] **Ben:** Those rules have tests like I'm testing this user identifier, I'm testing this property on the user and if those tests pass, then the user gets one of these variants. So that's significantly, honestly, more complicated than. Most things like program at work, most things at program at work are, here's a set of simple properties on an object, a user updates it, and I do some validation and save it to the database.

[00:30:39] **Ben:** there's no like business rules associated with a lot of this stuff. If there's business rules, it's mostly like, does this person have permissions to do this? And if they do have permissions, like, are there any just kind of database constraints that I need to keep in mind, but it's like, it is complicated.

[00:30:54] **Carol:** No,

[00:30:56] **Ben:** this is a much richer data structure that I'm used to. so I wanted to try and explore what that could look like in ColdFusion. So I'm doing it in a Lucy CFML and, and so I started with the simplest thing possible, which is. I'm just storing this to a text file. It's a JSON file that this data gets stored to.

[00:31:15] **Ben:** And, I built just a very simple, ColdFusion data access layer that reads and writes to this text file. And I built a very simple kind of old school. You make a request to the server. It does some things, and it renders a page. and I did a crud workflow, create, read, update, delete for that kind of stuff.

[00:31:34] **Ben:** And, and now what I'm going back and doing is. Trying to build a richer client side application with angular.

[00:31:44] **Carol:** Oh,

[00:31:44] **Ben:** so instead of having multiple pages for editing and changing, targeting, and deleting and lists, like it's just now gonna be a single page application or a spa. And, and the angular will make API requests back to the co fusion server to get the information and to change the information. And,

[00:32:02] **Carol:** the,

[00:32:02] **Carol:** the angular page that you're writing is gonna be, what is controlling setting the feature flags. Is that what you mean? Like, this is gonna be the interface for, okay. Okay. I didn't

[00:32:10] **Ben:** This. Yeah. Yeah. So this would be mostly the administrative.

[00:32:13] **Carol:** Yep. So your admin portal love it. Yeah.

[00:32:15] **Ben:** Yes, exactly. And,it's so weird. So I use angular JS at work, which is an old version of angular,

[00:32:22] **Carol:** Which is what a lot of CF engineers use. Honestly, they're like we know angular. I'm like, angular JS buddy, but it's okay. You'll learn one day.

[00:32:31] **Ben:** And it's so interesting because I feel super proficient with angular JS at work because I've been doing it for 10 years, literally 10

[00:32:40] **Carol:** it's nonstop. Yeah, I get it.

[00:32:43] **Ben:** and angular JS for people who are listening to the show here is end of life. Like it's not supported anymore. It's it? Doesn't like, they're not even, I don't even think they're releasing security patches for it at this point.

[00:32:53] **Ben:** It's.

[00:32:54] **Carol:** No, I think it's done. Yeah.

[00:32:55] **Ben:** Yeah. so I'm building the, this angular front end for the feature flag system in angular 14, which is the latest release of modern angular. And it's all built in type script as angular has been. And, it, I it's like, it's such an uphill battle and I've done a lot of R and D in angular.

[00:33:16] **Ben:** over the years. and really in the last, like two years, I've been very focused on ColdFusion on the back end and much less focused on the front end because. I was doing a lot of angular, R and D when I was on ColdFusion, 10 and ColdFusion, 10, like wasn't very exciting. And, and then we modernized our ColdFusion platform at work and suddenly it was like ColdFusion was so sexy again.

[00:33:39] **Ben:** And,and I had to go and I was just like, I was do, I was just exploring and trying all this new stuff. And it just, it really, reinvigorated my love of the language and my desire to explore the back end stuff. and I kind of just stopped doing all front end R and D in my free time, and really just did more co fusion stuff.

[00:33:56] **Ben:** So

[00:33:56] **Carol:** Yeah,

[00:33:57] **Ben:** I'm definitely quite a bit rusty and, and type script is it's so

[00:34:02] **Ben:** interesting. Do you have you

[00:34:04] **Carol:** sexy. That's what's sexy been yeah, the, the autoresponder. I wrote it in type script.

[00:34:12] **Ben:** Type script is so interesting because you really, you just have to be so explicit about everything and,and I like it and I get that and it's, and it makes everything a lot safer and,

[00:34:25] **Carol:** oh yeah.

[00:34:26] **Ben:** it makes everything much more explicit.

[00:34:28] **Carol:** when I, so coming from CF, I was like, I didn't realize how naive I was to typing. Like I had no idea like how naive I was like, I understand, like in. Whenever I'm creating functions in CF. Like if I'm saying it's an array, it's gonna be an array. Like if I'm saying it's a struck, I can't return back a string.

[00:34:47] **Carol:** Like that is fine, but I didn't realize like how granular you could get outside of it until I started writing in type script. And it just kind of opened my mind cuz I mean, I knew what types were I understood types, but until you've written it you're like, It literally wants to know everything.

[00:35:03] **Carol:** Like I could lay. I created an email type and I told it what this type was. Like I said, you have to have a two, you have to have a from, and it's like, your email type does not have a two with string. And I'm like, it knows I didn't actually pass that through I was like, I'm in love with this thing. It keeps me from breaking my own code.

[00:35:26] **Ben:** Well, so it keeps you from breaking your own code and when you're working with a team, especially, I think it's really nice because

[00:35:31] **Carol:** break my code either.

[00:35:33] **Ben:** can't break your code either. But so I get, I get torn now because I'm doing this for myself in a side

[00:35:39] **Carol:** Sure.

[00:35:40] **Ben:** and angular JS in general. I mean, JavaScript in general, I'd just say not even English, JavaScript in general allows you to be so sloppy is not the right word, but.

[00:35:50] **Carol:** Lucy goosey

[00:35:51] **Ben:** You get to be so loosey goosey. So, so for example, right. I have a lot of components that are based on the state of the route, the URL. And so if I'm gonna go to a detail page for a particular feature flag in the route is gonna be the key for that.

[00:36:08] **Carol:** Yeah.

[00:36:08] **Carol:** Yep, yep.

[00:36:09] **Ben:** And so the problem is when a component for the detailed renders.

[00:36:13] **Ben:** I can get the key out of the URL, but I don't have any of the data yet. I have to go back to the server to get the data. So I know that for some period of time, all of my data properties are basically gonna be null because I don't have

[00:36:26] **Carol:** yeah. Nothing. Yep.

[00:36:28] **Ben:** But then I know that once I have that data, I have all of it.

[00:36:32] **Ben:** The problem is like TypeScript says, well, you can't reference this without checking because sometimes it's known and sometimes it's defined. I'm like, yeah, theoretically. But like at this point in the life cycle of the component, I know that it's gonna

[00:36:44] **Carol:** It will be. Yeah.

[00:36:46] **Ben:** Ah, and it's, it doesn't feel like there's a, it doesn't feel like there's a good.

[00:36:52] **Ben:** At least on the angular side of how to deal with that. there's, there are approaches that deal with it, but to me it's like, it just adds so much complexity and, and it's weird. So now I'm kind of caught between this safety and complex versus not safe, but also significantly more straightforward and

[00:37:12] **Carol:** Less complex. Yeah. Yep.

[00:37:14] **Ben:** Ah, it's a really hard place to be. I actually, I hate to say this because I'm quite an angular fanboy, but it makes me wanna play around with view or, or something else or, or like, uh, Adam's talked about

[00:37:26] **Carol:** I guess I'm pretty sure Adam used you at one point. Maybe I'm wrong there,

[00:37:30] **Ben:** I'm curious to try something that's a little bit more streamlined and with the intent that I'm giving up some of that type safety.

[00:37:39] **Carol:** Yeah, but you're the only one using it right now. Do you plan on this project being something that you could put out for other people to use? I hope so. Cuz you know it's

[00:37:48] **Ben:** I, you know,it's in a GitHub repository, so it's available. But, I mean, I have no intention of

[00:37:52] **Ben:** doing

[00:37:53] **Carol:** to take your code all the time. Have I told you about that, about finding your code in their old software?

[00:37:58] **Ben:** no, I don't think so.

[00:38:00] **Carol:** Yeah, I was in, this is when I worked for another company. I was looking around for how to do something. And at the top of the file, no joke. It was just your whole file. And I was. Well, at least it had the reference to the website. So I could go look at the full post for it, cuz it was just copied and pasted in.

[00:38:18] **Carol:** I was like, Ben's been writing. I'm like, no, Ben's I've been writing. They sold this from Ben. I'm like, well he put it out there. I guess he doesn't care if someone uses it,

[00:38:27] **Carol:** yeah, yeah, yeah, of course. It's credited him.

[00:38:30] **Ben:** Joy of learning in

[00:38:31] **Ben:** public.

[00:38:32] **Carol:** So your name's probably in several repos that you have no idea about because you put the knowledge out.

[00:38:40] **Ben:** So, so not to rabbit hole down type script for a second, but, and this is not a type script specific thing, but so angular is very heavy into RX JS, which is the reactive extensions for JavaScript. It's all about this observable stuff and streams of data, as opposed to just one time chunks of data.

[00:39:02] **Ben:** And it's,it's angular has embraced this RX JS lifestyle. if you make a request, for example, to get data from the server, you don't get an HDP response back, you get a subscription to an, or you get an observable that you then have to subscribe to. And, and

[00:39:20] **Carol:** like that.

[00:39:20] **Ben:** I don't like it either.

[00:39:21] **Ben:** and I feel like, I don't know if I'm. I don't wanna say dumb and I, and like, I don't wanna say old, it's like, you know how you look at the old people and they like don't understand technology sometimes. And you're just like, you'll, you're just old. You'll never get it. Like I am. I, is I like I'm am I that way about streams of data?

[00:39:43] **Ben:** I don't know.

[00:39:43] **Carol:** no, I think it's that it's a simpler way to use it. Why add this other layer that I now have to do? I already know how to get to what I need and it was working fine. What did adding an observable for it? What, what happens when I'm now having to. Like, I should just be able to get to whatever my HB request was and the results of it.

[00:40:03] **Carol:** I shouldn't have to have another layer to make it work. I just like it simple. And it was simple before. What does it have to be complex now? What did that.

[00:40:11] **Ben:** I feel. and I, and there are people who really love reactive code and it's, and it feels like it's turtles all the way down. It's you can't just have like a little sprinkling of reactive code to keep things simple. It's like everything has to be reactive and then streams have to get piped into streams and you combine things and you're mapping stuff.

[00:40:32] **Ben:** I look at code like that sometimes, and it's so hard to follow and I know part of that is experience,

[00:40:38] **Carol:** Sure. Yeah.

[00:40:39] **Ben:** but I think part of it is not experience. I think part of it is

[00:40:41] **Carol:** just

[00:40:41] **Carol:** being able to read it and know what it's doing and understanding it. Yeah. Yeah. Over complex. Doesn't. And again, that goes back to when I was young. I would've been all for it. Right. And I'm gonna say it's because I'm older now and I'm more mature and I'm more wiser and I can see how, what I've done before didn't work.

[00:41:00] **Carol:** So adding the extra layers and the extra complexity didn't solve my problems. I need it to be able to be used and to be understood. So.

[00:41:10] **Ben:** and then I wonder though, is that, am I so, averse to trying to think in a new way that I've sort of cut myself off from the ability to learn this new thing, but

[00:41:18] **Carol:** I don't

[00:41:18] **Carol:** think that's true because you'll go research it and you'll go read about it and learn it just because you don't implement it doesn't mean that you're avoiding it.

[00:41:27] **Ben:** I, I tend to agree with you, but,when I agree with you there, it only enforces my own perspective. and the only reason that I think maybe that's true is because there are times in the past where I have not understood something. And then there's a light bulb moment and you're like, oh, I get it.

[00:41:42] **Ben:** I see how that makes my life easier and how it makes my better. I just, I have not had that light bulb moment

[00:41:49] **Ben:** yet for reactive code. And I don't know, people talk about spreadsheets and how reactive spreadsheets are. you can have formulas where like this cell is that cell divided by this other cell plus this other cell.

[00:42:02] **Ben:** And so you change any of them. And then this thing changes and you're

[00:42:04] **Carol:** whole thing.

[00:42:05] **Ben:** that's really amazing. But it's also really amazing for a very specific type of application, which is a

[00:42:11] **Carol:** For a use case for that use case, it makes sense. That's also really easy to break though. You typed the wrong value in the wrong

[00:42:20] **Carol:** field one

[00:42:20] **Ben:** exclamation mark error.

[00:42:23] **Carol:** done now the whole sheet's broken. So

[00:42:28] **Ben:** oh, man.

[00:42:29] **Carol:** take it back simple. Don't let me break it anyways.

## [00:42:33] Ben's Blog

[00:42:33] **Carol:** So, I would ask you something about your blog. You said that you were having a hard time kind of disconnecting some of the emotional feelings from not writing so much. Have you considered like putting a post up? That's like a, ask me anything and letting people just send you some random questions.

[00:42:52] **Carol:** And from that you could pick out. 15 minute, write up so that you have your once a week post that may give you the good feels back. So you don't feel like you're neglecting something, which then may not cause you anxiety working on the new project.

[00:43:07] **Ben:** It's interesting that you say that because I actually used to have an ask Ben form on the.

[00:43:12] **Carol:** Mm-hmm

[00:43:13] **Ben:** And I did get quite a number of submissions and it honestly was just overwhelming.

[00:43:17] **Carol:** oh yeah.

[00:43:18] **Ben:** it, I felt like I was drowning under it and you know, but likelots of stuff make me feel like I'm drowning. if I get an email from somebody that I have to respond to, like, I feel like I'm drowning.

[00:43:29] **Ben:** So it's, it's a very low bar.

[00:43:35] **Carol:** You should just like hit when you're feeling this way, you could always go hit up stack overflow too, and be like, let me find a Lucy unanswered question and answer it. There you go. Now I have, I have given the world something, maybe it wasn't on my blog, but I've given the world something back and I can go do my thing and feel better. So there's an option for.

## [00:43:57] Therapy Session

[00:43:57] **Ben:** I constantly feel like I. Racing from thing to thing. And that's part of why I get such an overwhelmed sensation. and I don't know what to do about that. So for example, in the morning, So that's my quiet time. And that's where I do my research and my writing. And that ends at a very specific time when I start work.

[00:44:16] **Ben:** So I feel like I'm racing to get stuff done before work can start. And then when work starts, I feel like I'm racing to get stuff done before meetings happen. And then, because I'm on the legacy platform, I know that the legacy platform is going away. So I constantly feel like I'm racing to, to beat the

[00:44:33] **Carol:** To death, like you're trying to get it done before dying.

[00:44:36] **Ben:** and and then, you know, then workends and I've gotta get to dinner and then I gotta finish dinner and then we gotta, brush our teeth so that we can get into bed so that we can watch TV. And then we gotta find something interesting. Cause I go to bed at a certain time and it's like, I just am constantly feeling like I'm out of time and it's a terrible.

[00:44:54] **Carol:** It's awful. It put me into a spiral for a while. I'm going to, therapy you for a minute, cuz this helped me. And I think I've said it before is you have to stop being a human doing and start being a human being.

[00:45:08] **Ben:** I

[00:45:08] **Ben:** like.

[00:45:09] **Carol:** You have to realize that your time is valuable. It is valuable for your health, like for your brain, for all of it.

[00:45:18] **Carol:** So you have to stop being a human doing and start being just a human being. So you have to start getting to where you can be. Like, I'm just gonna sit in my chair for 60 seconds. With no distractions and I'm just gonna, be in my head or just sit here, but I'm not gonna let myself do anything else.

[00:45:32] **Carol:** And eventually you get to where I can sit in my closet on my stool for five minutes and it feels not like, oh God, everything is gonna be so behind because I sat here for five minutes. So enjoy your coffee in the morning. Like walk the dog instead of, maybe researching or put in a podcast for a minute and take that time outside.

[00:45:53] **Carol:** Do something. So you don't feel like you're constantly a human doing and that you get to be your human being again.

[00:46:00] **Ben:** I it's really good advice. It's really hard.

[00:46:02] **Carol:** It's hard. It's hard. It took me a long time. I felt like if I wasn't being productive to everyone around me, I wasn't valuable. So if I wasn't picking up all the weight from being a mom, if I wasn't taking care of everything for the boys, if the band wasn't flowing correctly, if whatever sporting event they were over at the time, if I wasn't involved in selling tickets and doing everything I needed to do to make successful, I wasn't doing.

[00:46:26] **Carol:** And suddenly I realized most of the parents there, aren't doing. They're very happy just watching their kids. And it's because they're able to just be a human being and they don't have to be a human doing like their value to everything around them. Isn't determined by what they're doing. It's that they're sitting there watching their kid having a good time.

[00:46:46] **Carol:** So I've had to take a step back and go today. I'm gonna send the couch with Steve and we're gonna watch Netflix. And we're gonna cuddle and I'm not gonna feel bad about that. I'm not gonna feel bad that I'm not riding or that I'm not cleaning the house. It's okay. I'm going to be okay here.

[00:47:02] **Ben:** it's so good. It's so good. Watching movies, especially. It's so I, I love movies so much and I love watching television so much, honestly. and I know that I'm, my productivity is definitely front loaded in the day. I'm not someone who has a lot of mental capacity after like two o'clock.

[00:47:24] **Carol:** Yeah, mine dwindles off real

[00:47:26] **Ben:** yeah.

[00:47:26] **Ben:** Real

[00:47:27] **Carol:** wears off.

[00:47:27] **Ben:** And. So sometimes like on a Saturday or Sunday in the afternoon, I just wanna lay down and watch it and watch a movie. And I get so conflicted. Cause I'm like, I know this is overlapping with my productivity period and I know I'm not gonna have any juice left after this movie.

[00:47:45] **Carol:** And that's okay.

[00:47:46] **Ben:** know it's okay.

[00:47:47] **Ben:** But

[00:47:47] **Carol:** at, at both of our, at both of our houses, we put hammocks in the backyard because it helps us just kind of go, okay, sit down. Like, if you wanna look at your phone, fine, go sell, sign hammock, and look at your phone. Like, it's okay to just sit for a minute. Like, there's nothing wrong with that.

[00:48:02] **Carol:** I don't have to be doing everything. And I know I'm just repeating what you already know, but it's okay. Just find a little time for yourself. That's not doing

[00:48:11] **Ben:** having to walk, the dog has actually been really great because

[00:48:15] **Ben:** it's, it's a forcing factor and she has to be walked. That's not a discussion. So.

[00:48:20] **Carol:** Yeah.

[00:48:20] **Ben:** I know I have to do that. and it gives me time to listen to my podcast and sometimes just to stare off in a space.

[00:48:26] **Carol:** Yeah, that like mindless, just looking around. It's great. It feels amazing when you need it. I told my boss that, I, you guys didn't know this too. I used to just sit and code. I would sit down, start coding, and then all of a sudden the kids are home from school and I'm like, You guys had band practice.

[00:48:41] **Carol:** You're not home till five 30 or six tonight. Like I've had my one cup of coffee. I didn't even go get water through the day. I did nothing. Like I just sat here and stared into code all day and lost track of time. And with Ruby, I don't do that because after about two hours, she's in here laying a toy on my leg or she's licking my leg or she's whining to go outside.

[00:49:02] **Carol:** And I look at the clock and I'm like, oh man, I need to stand up. Like, I need to move around. Like this isn't healthy. So I feel like she's helped me a to. Get myself away from it and detached too. So she keeps me from getting in those moments and I appreciate it.

[00:49:17] **Ben:** I like it.

[00:49:19] **Carol:** Yep. Are we ready to bring it home?

[00:49:21] **Ben:** Yeah. I think, one piece of advice just for people who are listening is side projects are.

[00:49:27] **Carol:** Oh,

[00:49:27] **Ben:** I wish that I had the mental fortitude to do more side projects. and, but I don't mean like, just do more work in general. I mean, I choose, I wish I had the drive to choose more side projects instead of doing other things.

[00:49:41] **Ben:** and I think not doing that has held me back in a lot of ways.

[00:49:48] **Ben:** my advice to anyone listening, who's a programmer is. Don't be afraid to do side projects. I think lean into it. I think they're really valuable. And when I do them, it's super, it's always super satisfying.

[00:50:00] **Carol:** Yeah, I feel like I've given back and they don't have to be coding. They don't have to be technology. Like, I didn't even mention, like I run a scholarship pageant for girls, so it helps get them money for college. And it sounds silly like, oh, beauty pageants, but it is a scholarship. Like it's money to help you go to college.

[00:50:17] **Carol:** They have to write essays. Like they have to do community service and I'm there doing work with them. It's just a way to give back to the community. So it doesn't have to be a technology related side project. Pick up something that gives you some motivation and that you feel proud about.

[00:50:33] **Ben:** I like it.

[00:50:34] **Carol:** Cool.

[00:50:35] **Ben:** All right. So that's a good place to wrap it up.

## [00:50:37] Patreon

[00:50:37] **Ben:** This episode of Working Code is brought to you by ColdFusion is sexy as hell and listeners like you. If you're enjoying the show, please rate us on iTunes or wherever.

[00:50:47] **Ben:** Get your podcast and share this episode with a friend that really. Spread the word, our editing is due to our patrons. So thank you very much for your support and thank you, especially to our top patrons, Monte Gavin and Sean y'all are totes. Awesome. So thank you for that.

[00:51:06] **Ben:** All right, so we'll catch you all next week. And until then,

## [00:51:09] Thanks For Listening!

[00:51:09] **Carol:** Your heart matters. Even if your code doesn't have types.
