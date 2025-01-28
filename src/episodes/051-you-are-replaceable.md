---
title: "051: You Are Replaceable"
description: This week on the show, the crew talks about their own relationship to the notion of being replaced. On one hand, it can be very humbling. But, on the other hand...
date: 2021-12-01
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/051-you-are-replaceable/id1544142288?i=1000543611448"></iframe>

Engineers like to believe that they are non-fungible. That is, that they are not replaceable - that they are special and bring a unique set of skills and perspectives to the table. And, for some engineers at early-stage companies, this may be true. However, as companies grow and evolve and become more sophisticated, the cold truth sets in: we are all replaceable. Even Apple - at this point in its trajectory - continues to innovate without the iconic Steve Jobs.

This week on the show, the crew talks about their own relationship to the notion of being replaced. On one hand, it can be very humbling. But, on the other hand, it can be very freeing, allowing us to do crazy things like "take vacation" and not have to deal with every single emergency that crops up at work.

## Notes &amp; Links

- [The Phoenix Project: A Novel about IT, DevOps, and Helping Your Business Win](https://amzn.to/3E2rvkq)
- [The Unicorn Project: A Novel about Developers, Digital Disruption, and Thriving in the Age of Data](https://amzn.to/3D1kjDy)
- [Soft Skills Engineering Podcast](https://softskills.audio/)
- [Amy Hoy](https://twitter.com/amyhoy)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633 (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/051-you-are-replaceable.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Carol:** I get the whole Yukon, they built this baby, and now it's kind of like my kid going off to college. I don't, he doesn't need me to survive anymore. If I weren't here anymore, he would be fine. And he would move on with his life and things will be good. And that makes me, it makes me sad a little

[00:00:15] **Adam:** Yeah. that's a really good metaphor. it shows that you've done your job as a parent, right? You.

[00:00:20] **Ben:** Created this being and gave it the skills to survive without you.

[00:00:24] **Adam:** And the same is true for a company or an application or can be true.

## [00:00:49] Intro

[00:00:49] **Adam:** Hey Friends, it's episode number 51. And on today's show, we are going to talk about how you and you and I, and we are all replacing. And in our jobs, but first we're gonna start with our triumphs and fails.

[00:01:01] **Adam:** And Ben, what's going on with you, man?

## [00:01:03] Ben's Triumph

[00:01:03] **Ben:** I'm going triumph, as I've talked about in the last couple of shows, I've been dedicating some time to improving and modernizing my blogging infrastructure. And, as of this morning or yesterday morning, maybe I have removed all inline database queries and emails and anything else that was typically old school in the early ColdFusion communities.

[00:01:28] **Ben:** A lot of pages were formatted where the top part of the page was the query and the logic. And then the bottom part was the view that, that render the data, but I've taken all those queries and I've moved them into data access gateways. And those data access gateways are accessed by either. Services or a different kind of service are referred to as a partial.

[00:01:50] **Ben:** and then business logic is wrapped up in these, workflow components. So I'm pretty excited about that. It, it took me about two to three weeks to really clean everything up. But, I don't know. I feel like it's actually kind of respectable code at this point, which three weeks ago it was terrifying code.

[00:02:08] **Ben:** So, I'm super excited about that. Yeah.

[00:02:10] **Carol:** it's actually not a long time. Cause I mean, you've been working during the day at work, not working on this. So, I mean, this is just going to like extra free time you were doing it, right?

[00:02:20] **Ben:** Yeah. I mean, to be fair, it's a blog, so it doesn't do a whole lot. It was mostly rendering data. There's very little actual, you can create comments and I have some short URL kind of tiny URL things, but for the most part, it's all just, pulling data out of the database, caching it and then render.

[00:02:39] **Ben:** but it's interesting. Sowhat I realized is that in my early days of my career, I was super sensitive to trying to be very graceful in how I handled errors. where if let's say you were posting a comment and as part of the comment payload, you had to have the blog post ID that you were commenting to and your name and your email address and the comment itself.

[00:02:59] **Ben:** And if the ID of the blog post didn't exist, I'd have an error message. I'd have a collection of error messages. And the first error message would be like, oh, by the way, the blog you're trying to post to it doesn't exist. And then if you didn't have an author name, I'd say, please enter your author name.

[00:03:13] **Ben:** And if you didn't have an email to say, please enter an email. And it would all be in a collection of errors. And I would render the whole collection to the. And as I've been modernizing it, I just, the first time anybody sends me anything, that's not supposed to be there. I just throw an error. I'm just like no bad

[00:03:27] **Ben:** data.

[00:03:28] **Carol:** and just generic, better.

[00:03:30] **Ben:** well, it,it, it still sends a reasonable error message, but I no longer try to collect a number of error messages before return to the user. I basically, your inputs are bad. Here's why, like, here's the first input that I hit that was bad. And then I exit out of the processing. I don't know why I was so focused early on in, in like trying to validate every part of the post before telling the user something was wrong.

[00:03:54] **Adam:** I think there's a valid use case for doing that, like in an enterprise app and you've got a screen with a whole bunch of fields on it. You don't want somebody to have to go through a submit 20 times before they can finally get it right. But I don't know, blog like to leave a comment or to create a post it's not that big.

[00:04:12] **Ben:** Plus, I feel like a lot of that stuff has moved to the client side these days where the client side will have some logic about, Hey, you have to enter your name or you have to enter your comment before you can actually submit. So that by the time it gets to the server, all of the validation should have already been done.

[00:04:28] **Ben:** And now my job on the server is just to stop bad data. Like I'm preventing malicious behavior. So if you have anything that's bad, I'm just like Nope. Rejected. And it simplifies the code a whole lot.

[00:04:41] **Carol:** Oh yeah.

[00:04:42] **Ben:** So I don't know. So it's, I'm pretty excited about that. My, as my next step, I want to start to maybe address some of the actual layout and CSS a bit.

[00:04:50] **Ben:** That's all, it's not like table based anymore, but it's, I think it's float based and I want that sweet Flexbox action to start coming into play.

[00:05:00] **Carol:** Did you ever do the Frogger thing with Flexbox the little demo.

[00:05:05] **Ben:** I've heard people talking about nursing and myself.

[00:05:07] **Carol:** really cool. Like it's super like nifty, if you're trying to learn Flexbox so you can check it

[00:05:12] **Ben:** is great.

[00:05:13] **Carol:** Oh yeah.

[00:05:14] **Adam:** I like grid

[00:05:15] **Carol:** You don't

[00:05:15] **Carol:** like it.

[00:05:20] **Adam:** Flexbox is fine. If I'm just doing something really simple, like I want, I have two things in a row and I want to just want them to be like centered with a certain gap or whatever flex is fine for that. But I feel like when you get into any sort of complex layout at all, a grid is just so much easier.

[00:05:38] **Carol:** Yeah. I haven't used grid.

[00:05:39] **Ben:** I haven't. So I use Flexbox today a lot because at work we still have to support IE 11 on the legacy platform. And I 11 has some albeit a little bit buggy, but it has Flexbox support. Whereas I 11 has no grid support whatsoever. So if you wanted to use grid, you'd still have to have grid, but then it would have to gracefully, degrade into something that was probably Flexbox based.

[00:06:05] **Ben:** And it just gets complicated.

[00:06:06] **Adam:** even Google search doesn't support 11 anymore.

[00:06:09] **Ben:** Um, so I'm so dying for the day that we don't have to support it anymore. The new platform doesn't support it, but, but yeah, I think Flexbox is one of the best things since sliced bread and, yeah, that's me. Carol, what about you? What are you guys.

## [00:06:25] Carol's Triumph

[00:06:25] **Carol:** So I'm going to go with the TRIA. it's a company triumphs, non me triumph, but it's for my company and it's for women in tech. So I'm just really happy about this. We announced internally today that we have. Our new executive vice president of engineering. And it is M can't name it yet named her yet because it's not like public yet, but it is a female and she is also minority.

[00:06:49] **Carol:** So it just makes me super happy to see someone step into a role that historically has been male driven and male across the board. So I'm just excited for some different insight and, some different personalities up there. So it's going to be fun, fun to see what she

[00:07:05] **Adam:** see so many companies that are obviously suffering from a lack of female leadership. Like you, you see a product comes out or a press release or something, and it's like, did you not have a single woman look at this?

[00:07:21] **Adam:** There's something obviously sexist about it or whatever. And it's like, how are you, how did you, how did this get out of

[00:07:26] **Carol:** How did they get So far? Yeah. Yep. I know. Believe me solos before.

[00:07:33] **Adam:** heck

[00:07:33] **Ben:** I'll tell you I've had in my life. I think I've only had two female managers and they've been great. I am oftentimes more comfortable talking to female managers than I am to male managers. I don't know why that is. I feel like I can be less guarded. Maybe that's like some weird. Male machismo or, I dunno, like, I don't know.

[00:07:57] **Ben:** I just,

[00:07:58] **Ben:** I, yeah, psychology is definitely weird. I feel like I can be more natural when my manager is female.

[00:08:06] **Carol:** Yeah. I used to tell people all the time, I wasn't hired just to be an engineer. I was hired to be a mom because so many times I feel like I'm working with my kids. Not that the engineers are like children, but it's like, your kid comes to you and is like, where are my socks? Well did you look in your drawer?

[00:08:22] **Carol:** Like, did you look in the basket? Did you look in the laundry room? it's just the ability to problem solve the smallest things and to like a solution that makes sense, like to people and to me, that's what a mom does. So I'm an engineer and mom to lots of people. Me. Yeah. That's me. What about you Adam?

## [00:08:43] Adam's Triumph

[00:08:43] **Adam:** Well now I see now you're making me wish that you had a blog triumph, because then it would be not only three triumphs, but three

[00:08:50] **Carol:** blog related?

[00:08:51] **Adam:** is also blog related. that's okay. I forgive you. So it's not published at this moment while we're recording, but I'm like on the verge, I just drafted like a blog post to go with my blog sort of redesign kind of moving to more of like a digital garden.

[00:09:06] **Adam:** And I made some, somewhat significant changes to it. Like I'm dropping, discuss for comments, I'm using something called web mentions instead, which is basically like if you tweet and link the post it'll automatically show up as if it were a comment on the blog, that sort of thing. So I'm pretty excited about all that.

[00:09:22] **Adam:** And one of the cool things that I got to play with, it was super easy to do, but it was just something I'd never done before. I was like, let me do this. I support dark mode on there. So now,if your system is set to dark mode, then you get a nice, very well-designed color scheme and everything.

[00:09:36] **Adam:** And the code samples look good in both light and dark mode. And it's just,dumb as it is, I'm kind of proud of it all.

[00:09:42] **Ben:** Yo it, cause it's hard to do that kind of stuff, but a dark mode is on my list of things that I want to explore. but, it's like you have to unlock a bunch of things before that for dark mode even work. I mean, your classes need to make sense and whether or not you're using classes or CSS, custom properties to drive the dark mode.

[00:10:00] **Ben:** And then you talking about the code, all the code snippets, also looking good and dark mode. that's not super easy.

[00:10:05] **Carol:** it's not just flip it on.

[00:10:07] **Carol:** Yeah.

[00:10:08] **Carol:** So, so,yeah, that'll be, I expect even before this goes out to our early access patrons, that I'll be, publishing that. So, Cool.

[00:10:17] **Ben:** Yo, how much spelt is in it?

[00:10:18] **Adam:** none and that's one of the thing.

[00:10:20] **Carol:** oh

[00:10:21] **Adam:** I mean, you're not wrong, you're not wrong because, I, so I kind of fell for lack of a better word. Let's just say I fell in love with felt, eh, two weeks ago. this has, this redesign has been going on for like three months. just, little bits here and there.

[00:10:33] **Adam:** And then of course in like the last week or two, it's really like, okay, I'm so close. I just gotta, I've been kind of burning the candle at both ends going to bed at midnight or 1:00 AM or whatever. just to try and like, cram as much work onto it as I possibly could and fix little things here and there.

[00:10:47] **Adam:** And, a couple of days ago I was like, spelt would probably do most of this pretty good. And the rest of it, I'm sure it could be figured out. So I did take like one evening and it just started with felt and, there's like a, so have you heard of MDX? It's like markdown, but you can do

[00:11:01] **Adam:** react in

[00:11:02] **Ben:** but we can do react.

[00:11:03] **Adam:** Yeah. So there's an MD specs. Everything is spelled as like SV, something. So there's an MD specs. and, so I tried to put together a blog using all of that. and it's, 99% fine, but then there's just a couple of little things that I was having some trouble with. So I set it aside, I'll come back to it.

[00:11:21] **Adam:** Maybe that'll be in the future. And that's one of the things that I really like about these things that we're talking about is, having a blog not only gives you the opportunity to write, but it gives you the opportunity and a project that you can tinker on

[00:11:33] **Adam:** continuously.

[00:11:35] **Adam:** one of the things that we talk about or that some people talk about is, I, I want to work on something, I need a side project, but I don't know what to build.

[00:11:42] **Adam:** Well, write your own blog. And it's not something you should do because, It's a good use of your time to like put another blogging platform out in the world, but it is something that it's good for you to do, because it gives you an opportunity to,flex those muscles practice and try new things.

[00:11:57] **Adam:** And it's like a playground where you can learn stuff.

[00:12:00] **Carol:** Absolutely.

[00:12:01] **Ben:** Yeah. for example, as part of the refactoring that I've been doing, I, I was using the less CSS command line tool to compile my last. And, I wanted to start playing around with Autoprefixer, which is a post CSS plugin, which essentially for things that have vendor prefixes, where you might have say have dot MAs or dot web.

[00:12:23] **Ben:** Before your CSS property to get them to work, right? You can just write vanilla CSS. And then after the CSS compiles, the post CSS, Autoprefixer evaluate your CSS and injects those prefixes were needed. And I couldn't figure out how to do with just the less CSS compiler. So I ended up moving over to parcel, JS to do the last compilation.

[00:12:44] **Ben:** And then that like automatically has post CSS I think, built into it. And I, all I had to do was just install. Autoprefixer just like worked. and yeah, so you just get to experiment with all these little things, really fun.

[00:12:56] **Carol:** Yep.

[00:12:57] **Adam:** Cool. Cool. All right. So, who are we going to replace first?

[00:13:01] **Carol:** Well, while we're talking about replaceable, if anyone's looking for a job we're hiring, we can go there. Yeah. Yeah. So

[00:13:09] **Adam:** a VP of engineering. I hope

[00:13:10] **Carol:** Nope, Nope. That one's taken now, but we Do have several engineering roles open right now and one of them is react. So yeah, if you want

[00:13:18] **Carol:** to go do some react, we're open for you,

[00:13:20] **Carol:** I'm

[00:13:21] **Adam:** so. How

[00:13:21] **Carol:** but yeah, it's a,

[00:13:23] **Adam:** they wanted to apply?

[00:13:24] **Carol:** it's clear capitol.com.

[00:13:26] **Carol:** And over on the right hand side, there is a join us. And then just go to corporate jobs and look for engineering.

[00:13:32] **Adam:** Cool.

[00:13:33] **Carol:** all of the engineering roles are now available remote that are currently listed. So that's been a new change in our company.

[00:13:39] **Adam:** And is there any specific, like, is this open to people who live outside the United States? Are there specific times zones you're looking for or avoiding?

[00:13:47] **Carol:** Nope. I mean, as far as I know, it's open to anyone, we are looking for talent. So yeah.

[00:13:53] **Adam:** That's the way to do it.

[00:13:55] **Carol:** So if you're wanting, to jump over, let me know.

[00:13:58] **Adam:** Well, good luck. and actually before we jump into the topic for today, I wanted to mention last week. Obviously, if you listened, we didn't have Tim on the show with us and you've probably realized he's not on the show with us again, does evening. and that's just a scheduling thing, nothing going on.

[00:14:13] **Adam:** We're not replacing Tim. but, yeah, I don't know.

[00:14:15] **Adam:** He's got some stuff going on.

[00:14:16] **Carol:** don't

[00:14:16] **Adam:** it.

[00:14:18] **Adam:** Yeah. I guess we'll find out next week.

[00:14:19] **Carol:** tuned.

[00:14:21] **Adam:** yeah, so, yeah, so, okay, cool. everybody's replaceable

[00:14:25] **Carol:** Everyone is replaceable

[00:14:27] **Adam:** and they should be.

[00:14:29] **Carol:** Yeah.

## [00:14:29] Having A Critical Role

[00:14:29] **Ben:** it's so hard though. It's so hard. I remember going on vacation and I don't take a lot of vacation. It just doesn't. I dunno. I don't know how to relax. So I remember going on vacation for like a week and a half, one time, a couple of years ago. And, I'm one of those people who, even when I'm on vacation, I'm just occasionally checking my slack mostly because I like to know that what's going on.

[00:14:51] **Ben:** Like, I just like to have my finger on the pulse of the company and the people on my team and who's doing what, and I find it very interesting. but when I came back, it's like, everything was fine. There were no fires. There weren't any huge incidents or there was my absence did not cause a problem.

[00:15:07] **Ben:** So, yeah, so that was kind of sad for me. A part of me always wants to feel like the work that I do is indispensable that even though there are other people who can do the things that I do, I like to think that I can do them in an extra special way, or I can, or I bring a combination of skills together and I apply them to problem solving in a way that maybe other people can't do.

[00:15:31] **Ben:** and that may be true, but it's not true to the point that work stops when I leave. And, it's very.

[00:15:39] **Adam:** Yeah. I mean, you're not wrong. I mean, like you and I both started as early stage employees at a really small company and the companies are growing at different rates, but they're growing. and I think that your feelings that you're expressing there are very much influenced by. The those years where you like in the early days and the first year, if you had walked away, there's probably a really good chance that would have had a significant negative impact on the company if not killed it.

[00:16:06] **Adam:** Right. Like, I don't know how long it was before you guys, got funding and really staffed up. But,

[00:16:12] **Ben:** That's a great point in none of my self evaluation. Did it occur to me that I was maybe actually super critical at one point, and now I'm no longer that. that's that's a great point. If I had come into a larger company that was very established. Yeah. What I feel this way after time. I'd like to think that I feel this way, but I think you're right.

[00:16:33] **Ben:** I think my early experience at a tiny startup where everybody was to some degree critical because, we were always understaffed and overburdened and everything was on fire all the time. It's like, you just need people to show up. You need bodies there to get the stuff done. but right now, people can take vacations.

[00:16:49] **Ben:** And even if something explodes, like there's people there. Interesting.

[00:16:56] **Adam:** Yeah. And then there's, it's also a little freeing. Like I can understand how it's, it kind of maybe hurts your pride or something. It would hurt my pride. And it does hurt my pride to think about how I used to be mission critical Keystone sort of player. And now I've had to sort of relinquish some of that status for lack of a better word.

[00:17:17] **Adam:** but at the same time, it's a little bit freeing, right? So it's, that's a stressful state of mind to be in, to, to know I have to do this or this company that I don't have anything against is going to crumble without me. I mean, it's, that I think is a little bit of a hubris or,like maybe it's true.

[00:17:35] **Adam:** Maybe it's not, maybe it's true to an extent, that sort of thing, but I'm sure there's at least an element of truth to it in the beginning there. And,to lose that or to give it up willingly is a big change and a lot to change the way you think and feel about

[00:17:52] **Carol:** I mean, I had brought it up the last episode. I believe it was when we were talking about, promotions and responsibilities and stuff. I've been in a spot where it felt like if I walked away, things were going to crumble and it was not a good feeling like that is very stressful. And you carry that home with you every night.

[00:18:12] **Carol:** And when I finally did leave, I mean, customers were calling me personally and begging me to not leave because they were worried about the, like the state of their systems after I left. And I'm like, okay. I can't play this card on me. Right. I have to make these decisions for myself, but now to be able to take a week vacation and not even have the urge to check slack, I love that.

[00:18:35] **Carol:** I want no responsibility. You got.

[00:18:37] **Adam:** Yeah,

[00:18:38] **Carol:** just easier that way, but I get what you're saying. I get the whole Yukon, they built this baby, and now it's kind of like my kid going off to college. I don't, he doesn't need me to survive anymore. I don't have to make sure that he has his four-course male and he's eating a balanced breakfast.

[00:18:55] **Carol:** He's doing it himself. And sometimes that does make me sad that he doesn't have a need for me anymore. If I weren't here anymore, he would be fine. And he would move on with his life and things will be good. And that makes me, it makes me sad a little

[00:19:07] **Adam:** Yeah. that's a really good metaphor. it shows that you've done your job as a parent, right? You.

[00:19:11] **Ben:** Created this being and gave it the skills to survive without you.

[00:19:16] **Adam:** And the same is true for a company or an application or can be true.

[00:19:21] **Carol:** No, I believe So, I mean, if you think of it like that, Ben, you took your baby and you set it up well, and it's doing okay now.

[00:19:29] **Ben:** Yeah. I mean, what you're saying makes total sense. and actually I read a book maybe a year ago called the unicorn project or no, was it the Phoenix project, their sequels one's the Phoenix project. And once the unicorn project, it really good books, by the way, it's fiction based on good programming practices at a company.

[00:19:47] **Adam:** Okay. I'll have to

[00:19:49] **Adam:** check this out. it's sounds

[00:19:50] **Ben:** basically, I mean, I listened to them as audio books and, it's essentially a company that's really struggling and they bring in this consultant to help figure out why nobody's hitting their deadlines and why products aren't shipping. And they look at the team organization and the responsibilities.

[00:20:08] **Ben:** And anyway, like one of the things that they talk about is there's this one guy who's critical, super, super critical, and he does things that no one else can do. So he basically becomes a bottleneck for a lot of the work. I it's like part of me wants to be that guy, but then part of me also understands how destructive that is actually for getting things done as a company is scaling

[00:20:32] **Adam:** Yup.

[00:20:33] **Ben:** But then I think also, maybe I can find a sweet spot where I'm not, don't have to worry about being replaceable per se, as an engineer, but I can still have a persona and a way of interacting with other teams that makes me, let's say more valuable than a common engineer. I don't, I'm not choosing my words there properly, but I think, I don't know.

[00:20:57] **Ben:** I guess I just have this need there's some like carnal need for me to be special in some

[00:21:03] **Ben:** way

[00:21:04] **Carol:** be needed.

[00:21:05] **Ben:** to be needed.

[00:21:06] **Carol:** You have a need to be needed.

[00:21:08] **Ben:** Yeah. it's very, It's very alluring this idea that there is something that I do that is critical.

[00:21:14] **Adam:** Yeah. I mean, at the same time, you and I are, I think, especially Ben, I'm looking at this from the perspective of like a startup business, and

[00:21:23] **Carol:** And

[00:21:23] **Carol:** I

[00:21:23] **Carol:** definitely don't have that. So

[00:21:25] **Adam:** Yeah. You're working at a really big company, but I think part of that job when you work for a startup, yes. You're building the application and the business, but you're also building.

[00:21:35] **Adam:** Th the job should be to build yourself out of that critical role. Right.

[00:21:41] **Adam:** and so it's a measure of success.

## [00:21:44] Insecurity

[00:21:44] **Ben:** And I think there's also definitely a degree of insecurity that fuels this fear. Because we talked about this a little bit last episode, where, when I look at other people at the company who are doing things that I can't do, whether it's sales or marketing or interacting with humans,I validate my own feeling.

[00:22:03] **Ben:** Not validate is not the right word, but I feel comfortable in my own skin by thinking that I'm also doing things that other people can't do now, that's not necessarily geared towards engineers, but the fact that I'm doing engineering, stuff that other non-engineers can't do is underscored when there's few engineers.

[00:22:23] **Ben:** But when there's a lot of engineers that can do the things that I do, even though I'm doing stuff that other people can't do, there's still a lot of people that can do the stuff that I do. So I think it makes me feel a little insecure from a broader scope in the company.

[00:22:37] **Carol:** But a lot of the people

[00:22:38] **Carol:** can't bridge the

[00:22:39] **Adam:** Um, then dry for all of those

[00:22:40] **Carol:** Well, me, if I take it right, like I think you're saying, okay, I can write code, but I can also go dig in to say something with dev ops. Like I could work. I can be a bridge in between multiple things where other engineers may only be able to just write code and not understand the other side of what's happening with this application.

[00:22:57] **Ben:** Well, I think that's definitely part of it. Like that's how that's how I see myself, for sure. But just going back to Adam, you're saying you didn't, you weren't quite understanding what I was saying. It's like, if I can lead a team, for example, right? Let's say I don't feel comfortable as a director or a CTO or something.

[00:23:13] **Ben:** I can still write code and maybe someone who's in a managerial position, can't write the code that I can write. So that's, I feel good about myself, but if I'm standing next to a whole bunch of other people who can also write code the same way that the director can write code like that, I'm not really that.

[00:23:31] **Ben:**

[00:23:31] **Ben:** I'm not saying this is a healthy perspective to be clear.

## [00:23:34] Not Replaceable, Not Promotable

[00:23:34] **Carol:** Well, Okay. So my other point of view on it though, is if you're not replaceable, you're also not promotable. You are stuck in this position forever, because if you can't be replaced, you can't go anywhere. You have nowhere to grow. You have nowhere to move on to, and you always have the same type of responsibility on your play forever, because eventually they're going to stop giving you new things to do and new things to learn, because you already have so much that nobody else can do that.

[00:24:05] **Carol:** They're not going to want you doing anything else new. So you can't go up. You're stuck completely stale where you're at in the same spot.

[00:24:13] **Adam:** that's a really good point.

[00:24:14] **Carol:** you should mentor people to do what you're doing so that you can keep growing and what you want to be doing.

[00:24:20] **Ben:** Yeah.

[00:24:21] **Ben:** it's really interesting that you say that. Cause I think I've actually run into some flavor of that in the past where, when the company was very small and everybody was scrambling trying to get their work done, we had this, it was almost a running joke for a while where we would hire somebody new and then immediately put them on some new mission, critical part of the software before they really even understood the culture or the way the code work.

[00:24:47] **Ben:** But we had to do that because everybody else was super busy. So there was nobody that we could sort of hire up internally in the company.

[00:24:55] **Carol:** And that's why, yep.

[00:24:57] **Ben:** it's really

[00:24:57] **Ben:** interesting

[00:24:58] **Ben:** to say that.

[00:24:59] **Carol:** You can't promote

## [00:25:00] Replacing Your Employer

[00:25:00] **Adam:** yeah. Okay, well, if I may, I'd like to kind of look at this from the inverse angle, from our perspective as the employees, I think that we should view our employers as replaceable,

[00:25:15] **Carol:** Oh, yeah, you guys know? I

[00:25:17] **Carol:**

[00:25:17] **Carol:** Yeah.

[00:25:19] **Adam:** Right. That's just a healthy thing that I think we should encourage. Like I think there are people who know this and demonstrate it by changing jobs every couple of years.

[00:25:29] **Adam:** And I think that there's another segment of the population out there who feel trapped because maybe this is their first job and they don't understand the mobility that they have. Right. Like once you've proven that you're capable of keeping a job in this industry for a year or two, that pretty much shows that it's worth taking a chance on you.

[00:25:49] **Adam:** So that's not to say that you can get a job anywhere, but it is going to bump you ahead of somebody who's never had a programming job, probably in most cases. So, now I'm wouldn't advocate for somebody to quit their job without having another job lined up.

[00:26:04] **Carol:** Oh, I agree with that. Unless

[00:26:06] **Carol:** you're financially sound. Yes.

[00:26:08] **Adam:** doesn't hurt to look. Yeah. I wish we could all be that lucky.

[00:26:10] **Ben:** it's interesting. So one of the podcasts I listen to is soft skills engineering radio, or maybe just soft skills engineering

[00:26:17] **Adam:** Yup.

[00:26:18] **Ben:** and their patented advice as quit your job. It's basically a Q and a show and everyone who calls up or everyone who writes in the advices, you should quit your job. But, one of the things that they point out is that engineers often have this, overstated assumption that the company will be devastated if they leave.

[00:26:37] **Ben:** So there's all this tension around going to your boss and telling them that you're going to want to move on. And they're always like, dude, there'll be fine. You're going to tell them and they're going to be okay.

[00:26:46] **Adam:** Yeah.

[00:26:47] **Adam:** I mean, there may be, if you developed friendships and relationships with the people at that company, there's going to be some disappointment between you, but, you got to look at it from the company's perspective. If they don't have enough money to pay everybody. One of the things that they're going to be looking to do is cut expenses.

[00:27:02] **Adam:** And one of the ways they can cut expenses by laying people off and they might feel bad about it, but that's not going to stop them from doing it right. Like the company has to survive. And so in, even in that most basis to forms, everybody's expendable.

[00:27:17] **Carol:** Yeah.

[00:27:17] **Carol:** My thought is that I put in a lot of heart and a lot of really hard work into the application that I'm writing. I go out of my way to make sure things are done, right. I care a lot about quality. And if I'm going to put that much effort into what I'm doing and into a job that, or into a system that this overhead is making a lot of money on, they should be putting the same amount of effort into me as an employee and into my team and into the application that we're writing.

[00:27:42] **Carol:** And if they're not able to do that, then I'm totally okay. Bailing and finding someone who is.

## [00:27:47] Having Options, Contract Work

[00:27:47] **Adam:** Yeah. You know, I was just sitting here thinking there's a, I've mentioned in the past, Amy Hoyt, who's like an entrepreneur. and also like a business coach type person. I don't know what she would describe herself as, but that's how I think of her. And, she teaches people how to start businesses and how to do it right.

[00:28:03] **Adam:** And do it well. And one of the things that she likes to say is that, when you are working for a company, you've basically got all your eggs in that basket. If they fire you, then you're kind of screwed and you have to go find another job and you may not get any new. but if you choose to work for yourself and there's a zillion different ways, you could do that, but let's just say consulting, right.

[00:28:22] **Adam:** and you go and you hire 20 to 30, or not hire, but you know what I mean? Like sign contracts with 20 to 30 different companies to, to give them part of your time or whatever it is that you're doing. And one of them chooses to let you go. It's like, okay, that's fine. I've got, 19 or 29 other companies here, I'm going to survive, and maybe I'll have a down week or two here or there, but I'll find somebody to fill in that gap. And I think that makes a lot of sense, right? It, it diversifies your livelihood, which is a good thing. And it makes me wonder too. I don't know. There's definitely benefits to working for a single company, but I think that those benefits are. put there by the companies because they want that loyalty.

[00:29:02] **Adam:** They want you to give them that much of your time. What if it was normal to work for three or four companies, right. To work for four companies for 10 hours a week. Right? Like if that was the norm, and let's just say here in America, and if you didn't have to get health insurance from your employer and your employer didn't have to pay for that sort of thing.

[00:29:24] **Adam:** Right. Like the idea of, I feel like so much workplace angsty is because people feel tied to their jobs because they know, I've got a rent check coming due at the beginning of the month or whatever. And like, I don't have time to find another job and I have to work 60 hours a week at this job sort of thing.

[00:29:40] **Adam:** I feel like if we normalized working for more than one place, it would relieve a lot of that pressure.

[00:29:48] **Carol:** And I think you would see a lot more startups happen because startups don't have the funding to do full-time people, but people need full-time jobs in order to, provide for their families where they might be able to afford me for 10 hours a week. If this were more common,

[00:30:04] **Adam:** Right. And I think to some degree side hustles play this role for a large portion of people, right? Like I have some side hustles, I have my book and we've been talking about this workshop that I'm going to do. And,

[00:30:17] **Carol:** yeah, but up until the last, few months of my life, I've not had time for side hustle. I mean, my time has been dedicated to family. So if this were Monday through Friday, that'd be great. That'd be on board for that.

[00:30:30] **Ben:** It's a really interesting idea. You'd be exposed to different kinds of things too, which

[00:30:34] **Ben:** is nice. One of the drawbacks that I have of not only working at the same company for a long time, but working on the same project within that company for a really long time is it's always the same and I can find ways to improve it and to modernize it and to refactor it.

[00:30:51] **Ben:** But fundamentally it's the same problem. and if I were working at multiple places, it could be all different kinds of exciting things. I mean, I guess this is, people talk about working at a, an agency where the agency then contracts with a lot of companies. So even though you're working for the agency all the time, The agency then contracts you out essentially to a bunch of different companies.

[00:31:12] **Ben:** And people will say that they really enjoy that. Getting to start something new every eight months.

[00:31:17] **Carol:** But did they do that with engineers? Like with software engineers?

[00:31:21] **Adam:** Yeah, I did that

[00:31:22] **Adam:** for awhile.

[00:31:23] **Carol:** I didn't even know. That was a thing in our field. Like I've seen it

[00:31:26] **Carol:** with nurses and like office staff, people.

[00:31:30] **Adam:** Yeah. I mean, I think you use those types of resources differently. Right? So when I did it, I was a consultant and I would get hired most of the time. It was like they would bring in four to six of us for a big project that they didn't have the resources to do. In-house and,the project would last anywhere from eight weeks to eight months.

[00:31:51] **Adam:** And, it was just kind of like a way to burn down that backlog really fast. And then the project would end and we'd go and we'd move on to another project for another customer they might have us back or might not. But, yeah, I mean, and for us, we were very specifically targeting, like our stack.

[00:32:10] **Adam:** So we would, it was a ColdFusion shop or my team was a ColdFusion consulting team. and, so we would like find customers who had ColdFusion and needed somebody to, do some maintenance on their site or build new features or whatever. And do that work for them. One of my first jobs at this place was, updating all the security practices, for a, like a big e-commerce shop that this particular shop ended up getting bought by 1-800-FLOWERS.

[00:32:36] **Adam:** It's a big, big,business. And, they had all of that. passwords in clear text in the database. And so that was like, the first thing that I did fixed that.

[00:32:50] **Adam:** So

[00:32:52] **Carol:** those were the days

[00:32:54] **Adam:** yeah,

[00:32:56] **Carol:** that actually is that it gives me a little bit of anxiety, the thought of having to step into a project that I know nothing about the system work for them per se, eight weeks, and then just walk away.

[00:33:10] **Carol:** I think it

[00:33:11] **Carol:** would, I don't know that I can just let go and be, like, dude, sorry, goons something else. Like

[00:33:16] **Carol:** I would want to know the outcome of it.

[00:33:18] **Adam:** don't think it's just eight weeks because that's all they can afford. I think it's more like eight weeks because that's all it takes to do it. Right. An eight week engagement would be like, the project is really small or. I mean, I guess in that case, it would have to be really small anyway, but there's a couple of different ways that could happen.

[00:33:31] **Adam:** Like you could be starting it from scratch or you could be finishing something somebody else started in which case you need more time to figure out what's

[00:33:37] **Adam:** already there, but

[00:33:38] **Carol:** there, Yeah.

[00:33:40] **Adam:** ButI don't remember ever doing a project and not seeing it to completion as a consultant.

[00:33:46] **Carol:** All right. That's a little better. That's a little better. Yeah.

[00:33:49] **Adam:** Yeah.

[00:33:49] **Ben:** do think there is something very valuable to being on the same project for a long time. I mean, as much as it's appealing to jump from project to project, you learn different lessons from having to live with your mistakes for a long time.

[00:34:02] **Adam:** It also encourages clean code and, like paying down your own technical.

[00:34:08] **Carol:** yeah, cause you're going to have to live with this.

[00:34:10] **Ben:** Yeah,

[00:34:11] **Carol:** Yep. Oh yeah. Yeah, I love when we're in story time and we're going through, like what's coming up, in the next week's work or whatever, and someone will bring up, a random thing that's in work and we're like, none of us have any idea. And there are two or three guys on the team where they're like, well, back in the day, here's the story for it.

[00:34:32] **Carol:** And I'm like, I'm so glad we have the historians, because if you don't have that history of it, you don't know. And you spend all this time trying to figure out why it didn't work or why we wrote it that way. And they can just jump in and give you that information. it's amazing. When you have that history on your team,

[00:34:47] **Ben:** Yeah, a hundred percent.

## [00:34:49] Patreon

[00:34:49] **Carol:** well, this episode of Working Code is brought to you by non fungible developers. That's MFDs, and listeners like you, if you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod. And you can do that for as little as $4 a month. And all of our patrons get access to our after show and they get that early, as soon as it's done being edited, which is fun for us and fun for you.

[00:35:14] **Adam:** of course we need to thank our top patrons, Monte and Peter. Thank you guys so much for your support

## [00:35:18] Thanks For Listening!

[00:35:18] **Adam:** and if patronizing podcasts, isn't your thing. No worries. We appreciate that. You just take the time to listen. it would also really help us out if you left us a rating and review on apple.

[00:35:27] **Adam:** please send us your questions and show topics on Twitter or Instagram @WorkingCodePod. Or leave us a message at 512-253-2633 that's 512-253-CODE or join our Discord, which you can do by going to workingcode.dev/discord. And, you can not only ask us questions and give us topic ideas, but you can interact with the rest of the listening community.

[00:35:48] **Adam:** There

[00:35:48] **Adam:** has been a lot of people joining and a lot of fun conversations going on in there. So you might want to get in on that. We'll catch you next week then.

[00:35:56] **Carol:** Your heart matters and that's not replaceable.

[00:35:59] **Ben:** But apparently Tim is.

[00:36:03] **Adam:** We'll see.
