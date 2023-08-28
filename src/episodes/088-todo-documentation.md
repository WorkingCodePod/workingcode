---
title: "088: //todo: documentation"
description: "This week on the show, the crew talks about documentation."
date: 2022-08-17
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/088-todo-documentation/id1544142288?i=1000576356354"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, the crew talks about documentation. Yay! As developers, there's no doubt that we all love consuming great documentation - especially for APIs. But, nary a one of us enjoys the process of creating documentation. Except maybe Adam, who's oddly passionate about communication. For the rest of us, however, documenting our choices and our subsequent outcomes feels a bit of a slog. It's never clear when we should be writing documentation; it's never clear what we should be documenting; and, it's never clear just how much detail we need to include. Sometimes, ironically, it seems that the more thoroughly we document a topic, the more likely it is to be misunderstood. So, that's awesome!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/088-todo-documentation.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I'm just saying keeping the barrier to entry super low for documentation feels like the right way to do it. As opposed

[00:00:08] **Carol:** I agree.

[00:00:09] **Ben:** everybody has to use these new tools in order to document text, you're like, oh,

[00:00:14] **Tim:** just put it in word and email it to your technical writer.

[00:00:17] **Ben:** I'll put in word and I'll export it as a PDF and I'll attach

[00:00:20] **Ben:** it in an email.

[00:00:21] **Adam:** Oh, my God. That's how we used to get screenshots for everything. It emailed word document with a screenshot in it, like.

[00:00:28] **Carol:** Good luck searching for that.

## [00:00:49] Intro

[00:00:49] **Adam:** Okay, here we go. It is show number 88 and on today's show, we're going to discuss documentation, which if you continue to listen, I applaud you, but, we're gonna try to make it interesting. but as usual, we'll start with our triumphs and fails. Carol, why don't you go first?

## [00:01:05] Carol's Triumph

[00:01:05] **Carol:** Yeah, I'm gonna go with a big, giant triumph because I'm not letting any failure stop me this week. So I think that is winning because it's failing around me. Everywhere. last week I told you guys, I had like this panic attack, anxiety attack, and ended up, needing to see a doctor. And it was great this week.

[00:01:24] **Carol:** My dog decided to eat a rope and a rope. She decided a rope. She ate it. It's gone it well, it's not now because the vet had to take it out of her. so, so she ended up in the hospital, two nights ago and needed two ENMs to get said rope out of her stomach because she decided to eat it. So it had her all blocked up and she was miserable.

[00:01:49] **Carol:** And today she's back to herself, but that, and then I'm working on some code at work for the second. I've been working on this on and off because I have a lot on my plate and every solution I have ends me back in the same problem. And I want to stab my eyeballs out because I don't wanna deal with this code anymore.

[00:02:10] **Carol:** So I finally got with some guys today and I'm like, do you guys see this problem? Do you see why this will never work? It'll never work because we didn't design it right at front, which happens sometimes you don't think of how to grow something and you don't think it's good to need multiple solutions.

[00:02:25] **Carol:** So it's either I hack it and it's going to look pretty bad or I rewrite it, which means now there's like four ways of doing this. So weighing it out. There's no good solution. And it hurts. It just hurts trying to figure out the ugly way or the ugliest way. Which one do I go with? You know, so

[00:02:46] **Tim:** lipstick on a pig.

[00:02:47] **Carol:** yeah.

[00:02:48] **Ben:** Can you tell us at all what the code's trying to.

[00:02:52] **Carol:** Yeah, sure. So we have, this mapping service ultimately is what it is. So we have this mapping service that tries to figure out how I want to match, two of these transactions together. So basically they can have a parent child relationship. So if you have the parent order, then you wanna get some of the information from the child, because that means they've already done the work.

[00:03:15] **Carol:** So let's go ahead and get it all moved over while everyone assumed upfront that we would only look up parent child based off of one look up condition. So you send through depending on what type of order it is. I wanna look up by a number or I wanna look up by this other value. No one ever assumed that I would wanna look up by the first value.

[00:03:38] **Carol:** Or the second value, if that didn't match, let's look at the third option. So since everything was written to be a one-to-one lookup for matching

[00:03:47] **Carol:** Mm.and everywhere calls it, it's not super easy to get back in there and go, well now let's just run it again, cuz ultimately that's what I'm gonna have to do is go, okay, look it up this way.

[00:03:58] **Carol:** Oh, you didn't find it. Run it again. But since everything's coded to be one to one with this new look up value that I'm gonna have to manually override to say, now look it up by the second, because I assume since it's this type, it's always gonna be the first value. So it's a terrible situation of poorly designed upfront.

[00:04:18] **Carol:** Well, I, I shouldn't say poorly designed just without an a thought of it needing to grow past where it was. So I, I couldn't find a good way around it. So yeah.

[00:04:28] **Ben:** Yeah, that happens. Sometimes you gotta just chalk it up as a prototype, essentially for how you want it to be built and then build it right. The second.

[00:04:37] **Carol:** yep. Or the best way possible without causing too much damage. I can't guarantee it's going to be built the best way the second time, because it would require dry overhaul. So I'm gonna do it the least of the ugly ways and get through it. I hope, but Hey, the dog's healthy. She's doing good. The code will get written and everything will match and it's okay.

[00:05:01] **Carol:** Cuz it's not softing me. It's still good. so that's me. I'm winning. I'm winning you guys.

[00:05:08] **Tim:** Winning.

[00:05:09] **Carol:** winning on it. What about you, Adam?

## [00:05:12] Adam's Triumph

[00:05:12] **Adam:** mine is pretty much the same thing. So last week, I'm pretty sure it was last week. I had just said like, I just got back from vacation and, I was kind of crushing it and, making lots of little changes and just, building tons of inertia and momentum. And I feel like this week, is trying to slap me back for that, you know, just trying to like beat me down and say, okay, that's how you think things are gonna go well, I'll show you.

[00:05:36] **Adam:** and, very similarly, I'm just choosing to, to make it a good week anyway.

[00:05:40] **Carol:** heck yeah.

[00:05:41] **Adam:** Yeah, it's been tough. there have been days that like the minute that the, my five o'clock alarm goes off, I'm like, okay, I'm done with work for the day. And I walk downstairs and I'm like, put me to work, have me take the dog for a walk, have me cook part of dinner, have me, do whatever, cuz I need to be done with work, which means I need to occupy my brain with something else.

[00:06:00] **Adam:** and I just need to like the. I'm turning that page on the day, that's a new chapter of the day. and,that's, been very useful and helpful in maintaining my sanity this week. and you know what, To its credit, today went much better than previously this week. So it was Thursday.

[00:06:17] **Adam:** We've had a couple of days of like really reactive work. Like, you come in, you have this plan for it. You're gonna do in the morning. And by the end of the day, you're lucky if you've even thought about the plan, you're always just putting out fires and dealing with production bugs and data that got messed up.

[00:06:33] **Adam:** And yeah, it's just

[00:06:34] **Adam:** rough days.

[00:06:35] **Adam:** is summer like a pretty quiet, it's not the right word, but I assume during the academic year, there's a lot of reacting to client needs. And then during the summer, is it, can you guys go a little bit more heads down and just do feature development?

[00:06:51] **Adam:** I can understand why you would think that

[00:06:52] **Adam:** since we

[00:06:53] **Adam:** do work in, in higher education. Yeah. I. Admit, I had similar thoughts coming into this and unfortunately, no, that's just not the way it works. There's always too much to do. And it's just a matter of getting it scheduled, getting it done in time for when it needs to be done.

[00:07:08] **Adam:** there, there are demands on my time that are time sensitive, like going and working at events and that sort of thing. and those. Kind of scheduled around the academic year, but not so much. they're scheduled around the academic year because a lot of these schools, most of them use their own campus facilities for their events.

[00:07:27] **Adam:** So they want to do it like in the summer or in spring when nobody's on campus. And, and so that also happens to align with decent weather, which you know, is plus for doing stuff outside. Yeah. So there's like those things, there's, there's preparation and they're showing up and getting it done on site.

[00:07:41] **Adam:** and that there's travel, and that, tends to be like, okay, well, this is what you have to do. And this is when you have to do it. And then everything else is kind of squeezed in around then. And when it first started, when we first started doing that side of the business,we only had maybe a dozen customers doing that sort of thing.

[00:07:56] **Adam:** And so it was, there was a season to that part of the business, it was like, okay, reunion season is starting and then reunion season ended. and then there was the rest of the year. And now there's just so many events for so many schools across the country. It seems like it never ends like there's a, there is definitely a heavy period, but the rest of the year is just still this like background roar of stuff going on.

[00:08:17] **Adam:** Gotcha.

[00:08:18] **Adam:** Yeah. So, and then, yeah, and it's like, the, this other stuff that we support is. Not very academic focused, right? Like we work for schools, but we work for the part of the school that is primarily concerned with generating revenue for the school, which,

[00:08:35] **Ben:** That never stops.

[00:08:37] **Adam:** tuition. Yeah. And tuition plays a small role in, I mean, it's, I'm sure it's different from school to school, but,the majority of their revenue comes from other sources, donations and events and all these other little things.

[00:08:50] **Ben:** Gotcha.

[00:08:51] **Carol:** expensive.

[00:08:52] **Ben:** it reminds me, I used to work at this place. Eh, I think I worked there for like six years. And every single year from the first year that I got there, they'd always talk about, oh, December's gonna be so nice. It's such a quiet time of the year. Like all of our clients are on holiday and without fail every December, January period would be like the busiest time of the year because of emergencies or tight deadlines.

[00:09:16] **Ben:** Or I just felt like I was getting lied to every single year and they never stopped with the messaging. It was always like, oh, don't worry in December. It's gonna be super quiet.

[00:09:26] **Adam:** It was just gas lighting. You.

[00:09:29] **Tim:** Yeah.

[00:09:30] **Adam:** Cool. Well, that's gonna do it for me. how about you, Ben?

## [00:09:33] Ben's Failure

[00:09:33] **Ben:** I'm gonna go with failure and,I'm feeling good right now, as you can tell for my, but since we last met I've, I've just been underwater. And it I'm a super effective person in like a really narrow band of operation. And when I'm pushed outside of that comfort zone, like my whole world collapses and,and it's silly things like, so we just moved and we're an hour and a half away from where we were before, which means all of my doctors are now far away.

[00:10:05] **Ben:** So I have to find a new dentist and I'm overdue for a cleaning. And I have to find a new primary care physician and I'm due for a physical. And,I just got the results from my MRI and the doctor thinks I have like chronic tendonitis and my niece now I have to find a physical therapist and we've had, I've had internet connection problems.

[00:10:22] **Ben:** So I gotta deal with that. And it's just, and we're moved into the new house and there's all the stuff that goes on with that. And we've had this wasp infestation, and it's just like,

[00:10:30] **Carol:** Oh, my gosh.

[00:10:31] **Ben:** I don't know how to, I'm not a good, I'm not good at just like making a list of things I have to do and attacking it one at a time.

[00:10:37] **Ben:** It's like I spend three weeks feeling overwhelmed by the amount of stuff that I have to do. And then I make that list. and I don't know how to do that earlier. Even saying it out loud. I don't like, it would make sense for me to get off this call and then make a list of the things I have to do, but I'm not gonna, like, I'm not gonna do that.

[00:10:53] **Ben:** I'm just gonna feel overwhelmed at least through the weekend. and then, and then we'll go from there. But so it's just, life and work. There's just been a lot going on and I'm not someone who copes with a lot of pressures. I'm I cope very well with one strong pressure, which is usually work, but the, their moment, like pressure comes from other directions.

[00:11:11] **Ben:** I'm I very quickly crumble

[00:11:14] **Carol:** I get it.

[00:11:17] **Carol:** I completely

[00:11:18] **Tim:** you got it.

[00:11:19] **Ben:** I can do

[00:11:19] **Tim:** You can do it.

[00:11:20] **Ben:** I can do it. like I feel better today. Because I was struggling with some code at work and it felt like after days of struggling that work, the code started to come together and things were in the file organization, like the organization of the code and the files like suddenly started to make a little bit more sense.

[00:11:37] **Ben:** And I felt like I was on the right path there. And the balming power of good code is so intense that it's like, it makes everything else just feel so much better.

[00:11:46] **Tim:** Doesn't

[00:11:46] **Ben:** so a solve.

[00:11:48] **Tim:** Mm-hmm

[00:11:49] **Carol:** can make day. Great.

[00:11:51] **Tim:** for sure.

[00:11:52] **Carol:** So that's me, Tim, what are you gotta close us out with?

## [00:11:58] Tim's Triumph

[00:11:58] **Tim:** Well, sorry, Ben, I'm gonna go with the triumph. You're the only one. The failure today. Sorry, bud.

[00:12:03] **Adam:** Well, I mean, Carol and mine were like masked failures in, in triumph

[00:12:07] **Tim:** Yeah. Yeah.

[00:12:09] **Carol:** Refusal to admit failure.

[00:12:11] **Tim:** But,but I will say this is my, this is a failure, a long term failure of mine that I've finally decided has now become a triumph. So in the history of my career, like, starting out a small company I was the firefighter guy, right. So I was the guy that, that was my job.

[00:12:29] **Tim:** That was my department. The department I ran is like, was just put the fires out. Right. And so every day was nonstop. Walk in the door, check your emails and just fix stuff until you go home. And so that's kind of became my baseline. and to be honest, when you're in that mode, it's a actually a bit addictive.

[00:12:49] **Tim:** yep. I know. a bit addictive. It's you're fixing stuff. this stuff is broke. It's like the worst stuff that could possibly happen. Your customers are like dying on the vine and you come in and, you and your team figure it out and fix it. Right. And then you're like, all right, you have an S

[00:13:04] **Carol:** Is it a yeah. It's that big rush?

[00:13:07] **Tim:** Yeah. So it's a rush.

[00:13:08] **Adam:** to be a hero.

[00:13:09] **Tim:** you get to be the hero and then you move on to the next fire. Right. So it's constantly putting out fires, saving lives. these aren't fires that you started, but you put 'em out and that's sort of been my career. And then I'm, I, I moved over, the, they readjusted things and I moved over and, to the payment side.

[00:13:27] **Tim:** And I was actually really the only person that was the only coder, honestly. And. Lot wasn't broken because it was a pretty solid product already. And then when I came over, we totally refactored it and it got even better. And so there, a lot of it was the beginning was just learning it. And then, but just because I was the only person, like there was a pretty good volume of stuff to do.

[00:13:52] **Tim:** And so that kept me happy. But now it's like, I got more people because we've been very profitable and we've had very decent growth. when you have profit and you have growth in our company, you get more resources. So it's like, I have more resources now. So I have a bigger team. And, so there's not a whole lot to do sometimes.

[00:14:13] **Tim:** And like today was, it was kind of quiet and. Actually the entire week's been kind of quiet. And I think last week, my, my Noum was, was kind of status quo. I had my Noum, cuz I'm kind of feeling guilty. I'm like, what's going on here? I've I'm not needed.

[00:14:30] **Tim:** Right. But I've accepted that no fires and having a quiet week, an entire quiet week with no, pull the fire alarm or emergencies and just steady progress, building new products and new features and stuff that are constantly getting implemented. that's just a sign of well crafted code.

[00:14:49] **Carol:** It

[00:14:49] **Tim:** good thing. It's not a bad thing. If to me it feels to me it feels like a bad thing because I personally am like, I'm not jumping in here and getting my hands dirty, but it's like, I don't need to

[00:14:59] **Carol:** Mm-hmm

[00:15:00] **Tim:** did stuff. Right.

[00:15:01] **Carol:** right. You have

[00:15:02] **Tim:** It, it works. It just works. So

[00:15:06] **Adam:** I'll trade you.

[00:15:10] **Tim:** It just works. Now me saying this is probably jinxed it and tomorrow everything will fall apart and next, my next week will be a failure. But I mean, as of right now, it's like, we built this thing. It's solid. It works. Our customers are happy. And I got an email that it's making money. It's profitable.

[00:15:29] **Tim:** We're growing. I got an email today from a customer, who she sent me a little picture of a,of a ticking bomb. She, because she said, you're at a bomb. I'm like, oh,

[00:15:38] **Carol:** oh, I was like, where are we going with about to hit the fan

[00:15:41] **Tim:** she's like, you're at a bomb.

[00:15:43] **Carol:** Aw,

[00:15:44] **Tim:** so yeah. So I, but it's like, it was a struggle to get there cuz I was really just feeling awkward for a good while there, because there weren't fires to put

[00:15:54] **Carol:** right. Yeah.

[00:15:55] **Tim:** for a long part of my career, I was the firefighter.

[00:15:57] **Tim:** So I guess I gotta figure out what I am now.

[00:16:01] **Tim:** So.

[00:16:01] **Carol:** I definitely got a big ego boost with the constantly hearing. Go ask Carol, go see what Carol's doing. See if Carol's available. Have you called Carol yet? And when I switched jobs, that didn't happen, right? It was, you're gonna spend time planning. We're gonna get documentation. We're gonna make sure everything's right.

[00:16:19] **Carol:** And then we're gonna code it. They're like, you're coding things way too fast. You shouldn't be like, even putting your fingers on the keyboard yet. Hold on. We're not ready. I'm like, what do you mean? It says code let's code. They're like no step back plan. And now we put out quality product and that's pretty impressive when you're like, wow.

[00:16:37] **Carol:** it works every time when you go out with it.

[00:16:40] **Tim:** Yeah. I mean, I told a customer today was push me in a deadline. They're like, can we have this? I'm like, you'll have this. When it is quality,

[00:16:48] **Carol:** Yeah. Yep.

[00:16:50] **Tim:** you'll have this one as quality. I'm not gonna commit to doing this tomorrow for. Because

[00:16:55] **Tim:** you.

[00:16:56] **Tim:** you know you know what, you've gone without it for six months and you can go without it for a little bit longer.

[00:17:02] **Tim:** You'll have it when it's quality.

[00:17:03] **Carol:** yeah. Good for you. Way to stand up for your product and for your team. That's great. Yep.

## [00:17:08] Who Should Write The Documentation?

[00:17:08] **Tim:** you mentioned documentation. So let's talk about

[00:17:12] **Adam:** Every everybody's favorite topic. Yeah.

[00:17:14] **Carol:** jump back into like a few episodes ago. I mentioned how much I hate even creating Jared tickets so much so that I copy and paste messages from people and just put screenshots in the messages because I hate writing out things. So documentation is not my thing.

[00:17:33] **Adam:** See, I'm the guy that, when I read documentation in our Wiki and it there's like I read it and I'm going okay. I don't fully understand it. And I take the time to figure out what it means. Then I'll go and I'll edit the docs to make it more clear. Communicating is like a passion of mine, which is a weird thing to say, although, I mean, look at where I am now.

[00:17:51] **Carol:** not. Yeah.

[00:17:52] **Adam:** and, so like, it's weird to think that like, I might actually enjoy being a technical writer, but I don't think I would. I don't think I would be good at it or enjoy it long term. Right. Like I enjoy knowing a system and being able to describe it and teach it

[00:18:11] **Carol:** You're well rounded.

[00:18:13] **Adam:** Yeah.

[00:18:13] **Carol:** Yeah,

[00:18:14] **Tim:** Yeah. I struggle with documentation as well. I completely understand the importance of it because I, we have some decent documentation. It's not great, but I just love whenever someone sends me a question, I just send 'em a link to the documentation and go check this section. Right. But at the same time, it's like, I know what my hourly bill rate is.

[00:18:36] **Carol:** I know my worth.

[00:18:38] **Tim:** Right. And it's like, and I don't mean this. It's gonna sound arrogant. And I don't mean it that way, but it's like, it is beneath me to spend time writing good documentation because I, it takes a long time. Right. it takes a good long time. And if you, I could be earning better money doing coding or other, administrative things. documentation, but at the same time, many times, I'm the subject matter expert

[00:19:04] **Tim:** on the product. So how do I get that info from me to them in a way that also doesn't waste my time and, but yet results in good documentation,

[00:19:17] **Carol:** hello interns? No, I'm kidding. I'm kidding.

[00:19:19] **Adam:** Yeah. I mean, I, that was kind of my thought. I wasn't thinking interns, but you know, if you can have, if there's somebody that you can identify that is, capable of becoming a backups me subject matter expert, then you know, then they're probably not far from having that expertise to begin with.

[00:19:36] **Adam:** And so it would be easy for you to take them that last mile or two to understanding it at the level that you do. And then they can rate it for less per hour than what they pay you.

[00:19:46] **Tim:** And unfortunately we have someone now she, and I don't mean this any sexist way, but a lot of times people who do this job well, are females. I don't know why that is. It's just

[00:19:58] **Carol:** engineers, you mean?

[00:20:00] **Tim:** engineers. Yeah.

[00:20:01] **Tim:** Yeah.

[00:20:01] **Carol:** female engineers are the best.

[00:20:03] **Tim:** they're a lot more detail oriented cuz I, so we have, she's very good at writing.

[00:20:08] **Tim:** The first thing she did when she came on our team, she started writing, read MES for all the stuff that I never wrote a read me for

[00:20:15] **Carol:** I love that. I appreciate someone doing it, but I'm not gonna take it on and just do it myself.

[00:20:21] **Tim:** right. Yeah, for sure. and what's funny is actually she, at one point she was my boss in a former time and and she made a comment, one of our. One on one review, things like, so like we have our teams chat and she mentioned that one of the things she told me to work on was that, whenever I would send, messages to like the group or to her, a lot of times there would be missing words or, misspelled words or things like that.

[00:20:50] **Tim:** And I was like, I was taking it back. I'm like, what, why does that matter at all? I mean, to me, like having a teams chat is just a conversation, right? It's like the point is, did you get the, did you get the information? But she's like, no, you use that, for documentation and like, proof of stuff.

[00:21:06] **Tim:** and so to her grammar, spelling, understanding was extremely important to me. It was like, I just wanted to answer as fast as possible and get back to what I was getting to. Right. Which is why I should not be the person I documentation.

[00:21:18] **Carol:** Right. I get it.

## [00:21:20] When Should You Write Documentation?

[00:21:20] **Ben:** Well, what do you think about the dry principle applied to documentation? Dry being don't repeat yourself. And, and this is kind of coupled there's another one called wet, which is right. Everything twice. The idea that you should find duplication in your code several times before you feel like you have a good sense of what the refactored abstraction should be.

[00:21:44] **Ben:** And I'm wondering if. Would it make sense to apply the same kind of thinking to documentation, meaning don't document anything until a couple of people have asked you for it. And then you're like, okay, this is clearly something that needs to be documented or do you think everything should just be documented upfront?

[00:22:02] **Adam:** I don't think you should document everything up front because then you're wasting a ton of time, know, just like

[00:22:06] **Carol:** changes.

[00:22:07] **Adam:** Yeah. And just like, you don't go through and write a thousand features that could potentially be useful off of the one main thing. you gotta figure out what is what's needed.

[00:22:17] **Carol:** We do iterations of things. So I think once we have a final product and we see that it's been adopted well, that's when you want the good documentation on it, that shows what the process is, why we went that route with it and what the, like what we are connecting to, like what's talking to it. What APIs is it hitting?

[00:22:35] **Carol:** Like all of that should be there.

[00:22:37] **Ben:** But ju just to make it very concrete. Right. So Adam was working on the, that nightly data ingestion from

[00:22:44] **Ben:** the universities.

[00:22:46] **Ben:** It pulls the giant file and splits it up into stuff and SQS and all that

[00:22:52] **Carol:** a table. Yeah.

[00:22:54] **Ben:** So I, I assume initially Adam's the only one touching that. I don't know if that's true, but let's just say for the sake of argument, that's true.

[00:23:01] **Ben:** You could theoretically document how that works and how someone could get it working locally. Cuz maybe. Sam local is involved in setting up cues and there's a readme, there's a contributing doc, or should like Adam, just knock that out. And then when someone says, Hey, Adam, I need to make a change there.

[00:23:20] **Ben:** Can you walk me through how to do it then? Like, okay, now let's document it. Now that it's not just me and my brainchild

[00:23:27] **Adam:** So, to answer the question, head on, it was, this one is an interesting case because it's based heavily on code that existed. It just needed to be extracted out of the monolith. To help it like separate processing time from a, an HDP request to that processing time and the processing time to actually complete the request needed to be separated.

[00:23:48] **Adam:** and, so a lot of the understanding of the process was already there and shared institutional knowledge. The only thing that was new is orchestrating it all together over here. I guess I did rewrite it from CFML to node JS. So there was, the code is different, but it's all doing sort of the same thing.

[00:24:07] **Adam:** and so the part that needed to be shared that was new was the infrastructure bits. Right. Okay. Now it's on,Docker containers running on Fargate scaled up on down automatically using cloud watch alarms based on SQLs Q depth. And,it, I know that sounds daunting, but when you, like, when I, if I were to give you a tour of it and show you how it works now, you'd be like, oh, okay.

[00:24:27] **Adam:** That's. That's cake easy.

[00:24:29] **Carol:** enough. Yeah.

[00:24:30] **Adam:** The hard part is like, was figuring out how to automate the deployments of all of those things so that, you check in a piece of code and it's like, okay, well you modified this. So now I need to deploy this and this. And I need to update these alarms. And,and it's just, it was kind of nuts, but, that's the cloud, right?

[00:24:45] **Adam:** Everything. It is you have so much power at your fingertips, but you have to pay in orchestration and mental bandwidth.

[00:24:53] **Carol:** yep.

[00:24:54] **Tim:** For sure. And to, I mean, to your question, Ben, about, do you try to document everything or just, document the minimum and then when people need more, you add to it, I'll say the biggest issue that I've seen with our documentation. My personal experience is. People misunderstand the documentation you have.

[00:25:14] **Ben:** Mm-hmm

[00:25:15] **Tim:** And so the more you have, the more they're gonna misunderstand.

[00:25:19] **Ben:** Yeah.

[00:25:19] **Adam:** And they don't wanna read anything. Like if it's not two sentences that answers their question directly. They're not gonna read.

[00:25:24] **Tim:** Right. Yeah. So I mean, there's a lot of, so like the most misunderstood part is there's so there's a complete edge case in our system where, sometimes, and this happens sometimes the credit card processors do not give you an answer. You call them, you say, Hey, is this card good?

[00:25:42] **Carol:** Can we pay this? And they're like, they don't call back. And, it's an asynchronous system and it's, it tries to get it, but it's like, at some point you just gotta come back with a dead letter and say, Couldn't get it. Couldn't do

[00:25:55] **Tim:** get it.

[00:25:56] **Tim:** Yeah, couldn't get it. And so we just kinda leave that status and active.

[00:26:00] **Tim:** And our thing is to, Hey, recheck this right. And so we documented this edge case and put it in our documents. And that is the thing that like, we spend 99% of our time with implementations with our customers ex you know, and they're like, they're all worried about this. And we're like, seriously, dude, this is really this is gonna happen two, two times a year to you.

[00:26:20] **Tim:** this is probably not a big deal and I wish we almost never documented it and just call it a bug and just fix it after the fact, cuz we can just refund their money and whatever, but yeah, but we have it documented. And so it's like, yeah, I agree with the principle of give them the minimal documentation they need to get going. And then anything after that is a support ticket.

[00:26:44] **Adam:** See, I think the thing that inspires me and I think this kind of goes back to one of your earlier questions. Ben, the thing that inspires me to create a new document, you were talking about drive versus wet and stuff.

[00:26:52] **Ben:** Mm-hmm

[00:26:53] **Adam:** I get a support ticket and the, my gut reaction is let me go find the docs page that answers this so that I can send you the link and like the passive aggressive here.

[00:27:02] **Adam:** This answers your. and, and that page doesn't exist. It, when that page doesn't exist, that is when I will go write it so that I can then paste a link like, oh, here.

## [00:27:17] Single Page Docs

[00:27:17] **Ben:** yo, so, so here's a spicy take that I had at work one time, and I tried to sell people on this, but it did not go over. I wanted all of our documentation to be on a single page in confluence, like one giant monster size page, because hear me out. I think people getpeople get drunk with organization and they see that they can have all different kinds of folders and spaces and,and they're gonna break things out and they're gonna link to all kinds of different tools.

[00:27:44] **Ben:** And then half the time they're documenting stuff. And they don't even know that there's a previous version of that documentation somewhere else in the system that is now out of date. And, and the search on these things is also not great. And so what I wanted to get out of it was the power of constraints.

[00:28:01] **Ben:** Meaning if we had a single page for documentation, everybody had to see all the documentation all the time, which meant that you had to be really. Intentful in what you wanted to add there. this is like this document's already 87 pages long is the thing that I'm about to add to it really worth it.

[00:28:21] **Ben:** And if it is worth it, what's the least amount I can actually say about it and deliver that value. And like, honestly, more than anything else, I wanted to be able to just command F and find some stuff on

[00:28:32] **Carol:** And find anything right. There was one I was looking at, I think it's the post office. Don't hold me to that, but I think it's the USPS one. Like I'd have to go find it again. But I was recently on one looking at their API docs and it's like that the left hand has the nav bar that scrolls with you.

[00:28:49] **Carol:** But everything is one. Like one page. So when I was looking for like what actual special characters they allow and address, like, it was easy to find anywhere that had like an at sign and just look for keyword and just find where I was in the documentation based off of what my left nav bar had highlighted.

[00:29:09] **Carol:** So I was like, oh, well they have some of it included inside the API part. Some of it, they have included in like, address formatting. I was like, okay, so now I know where to look at too. I'm not lost in the context of where, like where do I even start searching for this? If I don't have a good search. So I get it, like at first I'm like, oh, one page.

[00:29:26] **Carol:** But then when you start saying I'm like, actually it does make sense. A lot of times whenever I'm on others, looking at it, if it's mine, I'm like, oh, one page, it's a lot of content. Right. But I have loved when other places have done it. I get it. I get it.

[00:29:42] **Ben:** it seems to be growing in popularity for API specifically. I'll see a lot. SAS vendors that have an API and their documentation for the API is exactly what you're saying. It's that left hand floating navigation, and then just a massive page. and I do love it because you can just do command F user and be like, how the heck do I get the user information?

[00:30:02] **Ben:** You're like command F address. And now I'm just jumping around, even if there's 87 matches in the document. Well, you know what, I just keep hitting

[00:30:08] **Carol:** doesn't take that

[00:30:09] **Ben:** the one. Yeah, exactly.

[00:30:11] **Carol:** Yep.

[00:30:11] **Tim:** Yeah. I mean, ours for our payment stuff is, and it's not, there's not a huge amount of endpoint. So it's pretty simple. It is a one pager. but I mean, I wanna shout out to Adam, I use his, his taffy API for other stuff, and I just use that taffy, it kind of self documents. Right. As long as I put hints and everything it shows up.

[00:30:33] **Tim:** And so, yeah, it's essentially a one pager cuz you can do a control F or command F and find what you're looking for and all of it. So, long as you just make sure you, you document, each endpoint and do whatever it's self documenting, which is pretty cool.

[00:30:47] **Adam:** well, thanks.

[00:30:48] **Tim:** Good. You did

[00:30:49] **Adam:** and good job.

[00:30:51] **Tim:** And you have good documentation on taffy. So.

[00:30:54] **Adam:** It does use the one pager thing that you guys were talking about, being able to search up and down. Although I do mine is one page for per version. So if you want, if you're on version 1.0 of the framework, then you can go to the docs for that version and that

[00:31:07] **Carol:** Oh, that's cool.

[00:31:07] **Adam:** cuz I, it always bugs me when I'm like, if I'm trying to use next JS, then it's, two or three versions behind you.

[00:31:14] **Adam:** It's like impossible to find the docs for that. Cuz they just like, oh, we released a new version. Here's the new docs and the old ones are gone. I'm like, but I'm not ready to upgrade yet. So you're stuck. And that, that always drove me nuts. So that became my, this like bug bear that I had that, I just that's the hill I chose to die on.

[00:31:31] **Adam:** At some point I was like, okay, I will solve this problem. And I found a way, which is, I just, I it's separate markdown files and each file becomes a page in the documentation website and yeah.

## [00:31:43] Who Should Write Documentation Part 2

[00:31:43] **Adam:** all right. So I have a question. I kind of talked about it a little bit earlier. It was derogatory in a manner of sense, but who should write documentation? Whose job is it?

[00:31:55] **Carol:** your job, my job.

[00:31:57] **Tim:** No, not me.

[00:31:58] **Carol:** I really think everyone, everyone should document to some extent, like whether you're just starting the process, get some bullet points out for someone who's gonna add to it for you, like get it going. So they know where to start because when you hand someone a blank piece of paper and say document this project and all of the steps to it that I did.

[00:32:19] **Carol:** Number one, they're probably gonna be scared to come ask you a hundred questions. They're gonna try reading the code and they're probably gonna get it wrong. However, if you can give them a few bullet points, like a few key things that says, Hey, go start with this then fine. They can take it, run with it and add to what you've done.

[00:32:32] **Carol:** So start the documentation, help them. Everyone should be responsible for documentation at some point, somehow help. It helps them. So help yourself by helping them.

[00:32:46] **Tim:** I'd just rather have a hundred questions.

[00:32:47] **Carol:** Oh,

[00:32:48] **Adam:** I mean it, I feel like this is one of those things where you can't put a little at one thread of yarn in this ball without finding two or three other like loose ends here. So, like I agree that everybody should write it, but I feel like maybe everybody should write, everybody should work on the documentation that would have helped them.

[00:33:06] **Adam:** Right? Like we're all constantly learning and getting better. and trying to figure things out that we don't understand about existing code. And when you learn something, you should be codifying that, so that it's easier for the next person to learn. And I think that, somebody mentioned read MES earlier.

[00:33:23] **Adam:** Like that's a great way to do it for,understanding decisions that were taken that were made, processes and understanding like the reasoning behind why the system works the way it works. Right. But that's not the documentation that you would give to your customers.

[00:33:38] **Carol:** no, they're completely different. I do not wanna write customer facing documentation. I wanna write what an engineer would pick up behind me to look.

[00:33:46] **Adam:** Yeah.

[00:33:46] **Carol:** I will tell you my favorite piece of documentation to write at work right now is our, onboarding docs. we are onboarding someone new right now.

[00:33:53] **Carol:** So the first thing I did was like, I went through opened that whole thing and was like, okay, what's not valid anymore. Let me make sure that whenever they start, they have everything we need. So I went and added like what slack channels they need to be in. I put in a few more little tips that I had figured out for some Mac builds and stuff.

[00:34:10] **Carol:** So that's my favorite documentation to actually contribute to is the things that people use when they're starting or when they're figuring out something that I know that's gonna help them onboarding docs. Yay.

[00:34:23] **Adam:** Yeah. I mean, that's just yet another type of documentation. That's like meta documentation for how to work at the company.

[00:34:28] **Carol:** Yeah.

[00:34:29] **Ben:** at work, we have technical writers for all of the customer facing support documentation. And because I, cuz I think, and I think that does make a lot of sense because. They interface with the engineers and the product people. And they get not just a technical sense of how things work, but a holistic sense of how everything is related.

[00:34:51] **Ben:** And then they use the public facing documentation to really tell a story using the right types of language that the customers can understand. And that to me feels like a very different type of gesture than documenting why we're using this database or how you make these API

[00:35:07] **Carol:** Yep. Yeah. At my government job, when I was doing it, our technical writers were psychologists. So not only, yeah, they actually had the mindset to understand how workflows related to human interaction. So they would make sure the documentation made sense to what people actually thought. So even if we didn't design it the way that it was laid out, they presented it in a way that people would understand how to use it. So. Tax money.

[00:35:36] **Tim:** Exactly as I was about to say,

[00:35:39] **Carol:** tax dollars, but Hey, it works. His documentation was amazing and easy to follow.

[00:35:45]

## [00:35:45] The Four Types Of Documentation

[00:35:46] **Adam:** so I, I don't, I've been kind of looking for the right spot to put this in here and I don't know that this necessarily is it, but I definitely wanna make sure that this makes it into the show. So there's this system for documenting things that I like. and it's been a little while since I've read through it all, and it's a whole thing.

[00:36:00] **Adam:** There's no way, like we could probably spend an entire show just on this system. and it's called the four types of documentation. and I said, we could spend a whole show on it and I don't think we would really get into the depth of it. but the, basically the four types are laid out on, in a grid system.

[00:36:17] **Adam:** So the grid is like on two perpendicular axes and across one access is like left side is most useful when you're studying right. Side is most useful when you're working. And then like the up and down access would be the top as like practical steps in the bottom is theoretical knowledge. Right. So that kind of gives you these four grid spots.

[00:36:36] **Adam:** And so like tutorials are learning oriented. They're useful when you're studying and they're practical. And then I guess working my way around the grid here. So practical when you're working is like how to guides they're problem oriented, useful when you're working and they're more theoretical, that's like reference information, it's information oriented.

[00:36:54] **Adam:** and then the last one is, explanation docs. So it's like one you're studying, but it's more theoretical. and it's just, that's like on to help you understand things. and so if you can kind of think of like, you need to write four different types of documentation for any part of a system, depending on who the system is for, some of them might ne necessarily be necessary or, deemphasized, but, breaking it up, like this has really helped me, I think, write better documentation because it helps me understand the goal of that particular document.

[00:37:26] **Adam:** Right. if you're trying to write a tutorial and a reference in one document, you're like diametrically opposed. Right. So, you gotta understand the audience and the goal.

[00:37:35] **Carol:** Hm.

[00:37:35] **Tim:** Yeah. That's really good.

[00:37:37] **Carol:** Yeah. I'll have to look at.

[00:37:39] **Tim:** I typically only do the information oriented reference. Right. It's like email me if you have a question. but I imagine if, if you have a, if you have a much broader user base than I do, then the tutorials, how to guys an explanation would be super helpful to have.

[00:37:57] **Adam:** Yeah. So like when I was originally writing all the documentation for Taffi the two that I spent the most time on were the reference and the how to guides. Right? So the reference is like, here's a list of every method in the framework and where it is and,how it changes over different versions and what each method does versus the how to guide is like, okay, so now you want to enable cores cross or cross origin resource sharing,for requests.

[00:38:19] **Adam:** Here's how you do that. And here are the pitfalls that you can run into and how to deal with those. Like, those are two totally different types of documentation

[00:38:26] **Carol:** That's.

[00:38:27] **Adam:** useful. Yeah.

[00:38:27] **Ben:** I, I just remember back when I was reading more books, more technical books, the ones that I really enjoyed a lot were the cookbooks, which was to Adam's point like very. Problem focused, like here's a 400 page book and inside it is 172 basically frequently asked questions about some sort of

[00:38:51] **Carol:** Yeah, like recipes.

[00:38:52] **Ben:** yeah, exactly. And it's great because it, not only is it problem oriented, so it has a lot of overlap with what you're doing, but because it's problem oriented, you're also getting a lot more inspiration from problems that you don't necessarily even have, but you're like, oh, okay. This is kind of interesting to even approach it this way.

[00:39:09] **Ben:** Now I have that squirrel away in the back of my head.

[00:39:12] **Tim:** I also think, I mean, so a lot of the kind of APIs and things that consume that will also have a support form. And a lot of times when I can't figure out in the documentation how to solve something, the best thing is like finding like maybe it's typically an error message and I just goo, put the error message in their search on their form.

[00:39:35] **Tim:** And someone else had that exact same problem

[00:39:38] **Tim:** or, multiple people had the same problem. Right. And, And then just seeing what the response was. Those tend to, I mean, those tend to deal with the kind of like very granular level problems that you're dealing with. and those are extremely helpful, cuz a lot of times the exact same thing that I'm getting is what they got and I can fix it based off the response.

[00:40:01] **Tim:** So I think support forms actually are really a good source of documentation.

[00:40:07] **Adam:** Yeah, I agree. it's tough because you have to do it well. Right. I think that the best support forums that I come across tend to be the ones where they train the users to ask good questions, to provide a clear explanation of what they did try and what they yeah. and where the community

[00:40:25] **Adam:** helps helps either.

[00:40:27] **Tim:** how many of us owe half our salary to stack overflow? Come on. Let's be

[00:40:30] **Carol:** I raise, I raised my hand.

## [00:40:32] Documentation Tools

[00:40:32] **Adam:** So, I guess let's move on. So, when you're writing documentation, do you guys have any like favorite tools or like, how do you, what do you use to write your documentation? Where do you store it? How do.

[00:40:43] **Carol:** I mean, is it a favorite or is it just what we use? We use confluence the last hand product. I mean, it's totally fine. It's just a document storage system and it puts it all in there. You can search for it. I can search across all the projects. So all the projects in the company. So anywhere I wanna find, like where we're using modern appraisals, I can go find any documentation that anyone's written that every references, modern appraisals.

[00:41:05] **Carol:** So it's good for that for having all of it together, but I don't know if it's the best tool like it. To me. It's no different than like a notebook. Like it's just all there. It's not really organized very well unless the owner of that project actually takes the time to organize it. Well, and most of the time it's just a document that says how to , which doesn't really help all the time.

[00:41:26] **Ben:** Yeah, we use

[00:41:26] **Ben:** confluence at work.

[00:41:27] **Adam:** so, so three stars is what I'm hearing. Three outta five.

[00:41:32] **Carol:** Well, I mean, I think if it's used, right, it's great. Just it, we have some legacy stuff and it probably wasn't all set up. Correct. So we have like a folder that says how two articles. It's not all how two articles, just like the map build out process is inside the development folder rather than inside the onboarding folder.

[00:41:48] **Carol:** So I don't know why they're split out. Like

[00:41:52] **Tim:** Yeah. So I used to get her, read me for the developers is the super basic too long. Didn't read the TLDR. Right? So it's basically a recap of basically how to install it locally. Right. So that's just developer. You wanna, you pulling down this repo, you wanna install it and run it locally.

[00:42:15] **Tim:** Here's what you need to know. And then GitHub Wiki for more in depth, kind of understanding of, here's the Getches and gotchas about each part of this, project that you're doing, but for customers, I mean, customer, these are private repos. So obviously the customers can't get it. So we just have our own point of presence website that has the,how they implement cuz all of our stuff is API driven.

[00:42:40] **Tim:** So how do you implement this API? How do you, what are the endpoints? You can call what it can pass. What do you get when you get back? It's all swagger. so yeah, so it's really, it's kind of a combination of three things. We don't use conflicts.

[00:42:52] **Carol:** you?

[00:42:54] **Adam:** So, we have, we use a product called get book, which is basically, a get repo full of markdown files. And you can put them in folders, you can, include images and that sort of thing. And then, every time you make a commit and push it up to the GitHub repo, it triggers a rebuild of your doc site.

[00:43:13] **Adam:** So it's like a static site generator based off of markdown and folders and stuff. And it's got some nice features built in,occasionally we run into things that are frustrating, but, the way that we are using it is free for us, which is nice. And one thing that I don't think I could live without is, doing it in a get repo because like we have started using a GitHub Wiki for like internal documentation.

[00:43:37] **Adam:** for example, we are switching from om to, handwritten SQL in DAOs. And so in order to make that process easier, we have a new like base Dao that provides all the simple crud. You just like, you create a new, component that extends the base Dao and you tell, okay, this is the table name. This is the primary key name.

[00:43:59] **Adam:** These are, this is the list of all the fields. And I think that's like, that's the minimum of all you need is like, okay, it has a, this is the column name. This is the type, and this is the max length or whatever for each field and the default. And it will do all the crud for you. So then you get like,

[00:44:13] **Carol:** Oh,

[00:44:14] **Adam:** Create read.

[00:44:15] **Adam:** Yeah. Create, read, update, and delete methods for that. And it'll all of 'em return a query with one row in it, unless you request multiple. anyway, and,that sort of thing is great. And then it starts to like, oh, it would be great if it could do this too and do this too. And so it starts to grow.

[00:44:29] **Adam:** and so we started writing documentation for this based AO in our GitHub Wiki. And the thing that drives me nuts about the GitHub Wiki, you would think that the company and the people that work at GitHub would have a fond appreciation for what get can do for you, especially in terms of like, multiple people working on the same file at the same time,

[00:44:51] **Carol:** yeah. Versioning. Yeah.

[00:44:53] **Adam:** versioning, and merge conflicts and all that.

[00:44:56] **Adam:** And it, it blows my mind that GitHub has been around. Like, it's probably what a billion years now. And,

[00:45:02] **Carol:** it just hit 20.

[00:45:03] **Adam:** Yeah. And, and still the wikis don't have get, I think, honestly, I think there was a time early on when, like you could, there was like a special URL to get your Wiki as a get repo, but I don't think it's around anymore.

[00:45:16] **Adam:** I wish that it was because, yeah, I w I wish that it was because that would be great. because right now what happens is, I'm editing the, a page in the Wiki, and then it just a red message appears at the top that says, somebody else has updated this document. Please refresh the page and make your changes again.

[00:45:30] **Adam:** And I'm like, but I've been working for 25 minutes

[00:45:33] **Carol:** this is called emerge.

[00:45:35] **Adam:** Yeah. And I don't know what I changed you. I just started reading and fixing stuff. And it's so frustrating.

[00:45:43] **Carol:** super frustrating.

[00:45:44] **Adam:** So, and so because of that, what I've started doing, when I need to make changes in the Wiki, I ha I completely forego the like commit message that you put in at the bottom.

[00:45:53] **Adam:** I just, I try to make my changes fast as I can, like edit, click the edit button, find the section, make the change and hit save, because I don't want to get stuck in that situation where I've got a bunch of changes made and then somebody else made other changes and committed theirs.

[00:46:08] **Carol:** do you do it in the browser or are you doing that? Like in your ID? Okay. Yeah, I

[00:46:12] **Adam:** Yeah. Yeah. I mean, it has to be in the browser cuz

[00:46:13] **Carol:** you're like, whoa.

[00:46:14] **Adam:** no there, I mean, oh, I'm specifically talking about the GitHub Wiki. not get

[00:46:19] **Carol:** the Wiki. Oh, okay. Gotcha. I got 'em flipped in my head. Sorry.

[00:46:23] **Adam:** Yeah. Yeah. That's okay. yeah, so, yeah, the GitHub Wiki, you have to do it in the browser and yeah, there's like, it's easy to butt heads with other people and step on each other's toes and all the idioms. and It's so frustrating, but at the same time, like it's also so easy. So like if you're the only one working on the project, it's a great tool. If there's two of you, you can make it work. If there's five of you, that's when it starts to get frustrating. If there's 50 of you, you don't have a chance.

[00:46:51] **Carol:** It's not even possible. Then you have to task someone with that being their. You're only responsible for this cuz nobody else can touch it.

[00:47:00] **Adam:** So another tool that I wanted to bring up, I haven't got any experience with it, but I see it used a lot in open source stuff, probably because it's free for open source, but there's a great tool called read the docs.com, which I get the impression that it's a lot, like get book, like you get a GitHub, Wiki of markdown files.

[00:47:18] **Adam:** And it looks to me, at least with the current version that you can have like multiple versions. You know how I was saying this? Wasn't like my pet peeve, my bug bear for the taffy docks was being able to maintain documentation for different versions of the framework and allow you to browse the different version. It looks like that feature is supported here too, which would be nice.

[00:47:37] **Carol:** that's cool.

[00:47:38] **Adam:** And I think that it's otherwise somewhat similar to GitBook right? Like markdown files to generate a, static site.

[00:47:45] **Carol:** It says it does have version documentation.

[00:47:48] **Adam:** you go.

[00:47:49] **Carol:** There you go.

[00:47:50] **Adam:** Not sponsored.

[00:47:51] **Carol:** So I think the thing we struggle with is like keeping everything updated. So even when we write the documentation, nobody updates it when the process, or like, so say we write the documentation, like I'm only thinking of technical documentation, cuz I don't do any customer facing stuff. So I just think of the technical side.

[00:48:09] **Carol:** So we will write technical documentation inside for like how a process works. So we'll lay out like, the steps that are needed, like what it applies to you. So what you would need, if you wanted to go make edits to it, you'll understand kind of the whole flow without necessarily having to understand all the code.

[00:48:25] **Carol:** So, but when someone comes behind you and they have a story to make a change to it, if we don't add a story that says update the documentation. We forget to update the documentation. So then I have new people coming on board and I'm like, oh, you wanna know how you solicit new work or read the solicitation documentation?

[00:48:44] **Carol:** And then I open it and I'm like, don't read the solicitation documentation because that's not how we solicit work to anyone anymore. I'm so sorry, go watch this video. I'll make you

[00:48:55] **Adam:** Yeah.

[00:48:56] **Carol:** updating is hard.

[00:48:58] **Adam:** A lot of the docs that I write. Our customer facing. and I feel like the biggest frustration for me is screenshots. So in order to make things clear on like, okay, I want you to go to this screen and click this button. It's the clearest way I can think to communicate that aside from people with, vision based disabilities is a screenshot with an arrow on it, right?

[00:49:22] **Adam:** Like here's the thing, here's where the button is. This is the whole page. The button is in this corner and it points to it. and then, the UI changes and like that screenshot is instantly out of date and it's so frustrating.

[00:49:34] **Tim:** that's the thing I have a problem I have with Amazon's documentation, a lot of their stuff. You Google it it's like, it's old. They change their screens. Like every year

[00:49:44] **Carol:** I'm like this doesn't even look the same anymore.

[00:49:46] **Tim:** the same. I don't know why or click

[00:49:49] **Carol:** Cause I'm not reading it. I'm just looking at the images and following the steps based off what your images have arrows pointed to. Okay.

[00:49:56] **Tim:** yeah.

[00:49:56] **Adam:** our usage of AWS stuff I would say is,I don't mean this in a negative way, but like immature, right? We're not using cloud formation and, infrastructure as code stuff. We're mostly doing click ops, right. Going the AWS console, click around to you, do the things that you need. And so when we started, for example, when we very first started using Fargate, it's a complicated thing to set up.

[00:50:17] **Adam:** And so we would like write or read me with all the steps and then you go back the like three weeks later. Yeah. And the whole wizard that you have to go through has changed in different. And it's so frustrating because the things that you need to accomplish are the same, but the steps are in a different order.

[00:50:32] **Adam:** They've got different names. I don't envy them, cuz you want it to be, you want the tools to be constantly improving, but the documentation is an important part of.

## [00:50:41] Incident Logs

[00:50:41] **Adam:** so actually I do have one other thing that I wanna talk to you guys about, the, something that I'm not great at that I'm trying to get better at is, taking notes when things are happening rapidly, like there's an incident, like we've had a bunch of this week and you're dealing with things you're running SQL queries in production and you're, updating data and you just wanna, be able to roll back if you need to be able to answer questions about what you did.

[00:51:08] **Adam:** And so like, like I said, I'm not great at this, but I wanna get better at taking notes as I do those things. Do you guys have a, an approach that you use a tool that you use to, to just log that sort of stuff?

[00:51:21] **Tim:** So is this documentation or like after action?

[00:51:24] **Adam:** neither for me, what it is like there was a period where I was trying to just take notes, my entire Workday, and I had like a note file dedicated to each day. And, the thing, it started out as like a to-do list. But then as I finished up the, or as I went through my day, as I made decisions or as things were interesting, I would write down the details so that, in three weeks when somebody asks me about it, well, why'd you do it that way?

[00:51:48] **Adam:** Or what was that thing that you did that, that had this other effect? I can go back through my notes and say, okay, I did it on this day. And,this was why I did it and whatever. and I feel like, having that daily note would be really useful for, incident response type things, but.

[00:52:03] **Tim:** How often did you actually need to pull that out?

[00:52:06] **Adam:** I think that what that, that note is really good for is, just understanding all the steps that were necessary to put the fire out after it's out.

[00:52:15] **Adam:** So sometimes when the fire's really bad, you've got people screaming or whatever, it's like, there's a temptation to just push on it and solve the problem and solve the next problem, solve the next problem. And then you go at the end, you're like, okay, but what did I do?

[00:52:27] **Carol:** What

[00:52:28] **Carol:** actually fix this? Yeah. Yeah.

[00:52:31] **Tim:** Yeah.

[00:52:31] **Tim:** I don't, I mean, I get where you're coming from. I don't think I ever kept like a note file of it, like you did. I typically knew in general what I did to put the fire out back in when I was in my firefighting days. and there was two versions that right there was the internal one that was like, oh yeah, we screwed the pooch on this one.

[00:52:48] **Tim:** and there was the external one to the customer. I was like, so here's what happened,

[00:52:52] **Carol:** it's all fine.

[00:52:54] **Tim:** It's good now. And, yeah, there was a little bit of a problem.

[00:52:58] **Carol:** Yeah. But it, you don't divulge you

[00:53:00] **Adam:** swamp gas and cosmic

[00:53:01] **Adam:** rays.

[00:53:02] **Tim:** exactly. Right. Yeah. You don't just, yeah, but I mean, yeah, I never, yeah, it's interesting.

[00:53:09] **Tim:** I never kept an entire,

[00:53:10] **Tim:** log of it.

[00:53:11] **Ben:** At work when we're having an incident specifically, we have someone who is the dedicated, what we call the incident commander. And their whole job is to take the notes during the call.

[00:53:23] **Tim:** I'm sorry. I just thought of a pop culture reference. That's entirely inappropriate.

[00:53:30] **Ben:** show after show.

[00:53:31] **Tim:** show.

[00:53:31] **Ben:** yeah, so, because everyone is so mired in getting the fire put out, we have someone who's specifically there to get information from the people who are doing the firefighting and relay it to the rest of the team. And that's been pretty helpful cuz that person doesn't have to panic about figuring things out and the people who are figuring things out, don't have to panic about relaying information.

[00:53:52] **Ben:** So I'd say that's historically been very helpful.

[00:53:54] **Tim:** that's a good point. A lot of times we'll just jump on a call, right? So all of us are on a voice call together and one person is not necessarily hands on keyboard. They're just there to kind of monitor. And they're the ones who can remember,what the fix was and what.

[00:54:10] **Ben:** Another thing that I do that I've started doing in the last couple years. And I can't tell you how much I enjoy doing this. Every time is I put into the slack chat. We use slack at work. I put into the slack chat, or I put into a JIRA ticket, every single SQL query that I run. if I'm in the middle of trying to figure something out, I will say, this is the query that I'm running and I'll paste it somewhere.

[00:54:34] **Ben:** And I'll be like, and these are the results that I got often in a screenshot. And that way, weeks later I can come back and say, how did I do that? Oh, right. Here's that query, cuz oftentimes I'll then have to run that query again, but some variation of it and it's been so awesome. Having those queries documented.

[00:54:50] **Tim:** It's one thing I love about the Aqua data. The SQL tool I use is cuz it keeps a history like every single one you run. And so you can just

[00:54:59] **Carol:** all your queries.

[00:54:59] **Tim:** and pull the yeah. Pull those up and say, all right. Here's what I ran.

[00:55:03] **Carol:** Yep. Yeah. I would open up my logs or like my history folder and do a search. I'd be like product table. What was the last hundred queries that contained product table? I'm like, oh, okay. There was the one. That's the one I knew I need.

[00:55:17] **Tim:** Yep. It's pretty cool.

[00:55:18] **Carol:** So documentation's important, but, nobody likes to do it. So except Adam

[00:55:22] **Adam:** Except. Yeah, except me.

[00:55:24] **Ben:** one thing that drives me crazy is every now and then I'll be on a team where in order to do the documentation, I have to learn some totally new technology.

[00:55:35] **Ben:** Like, uh, like swagger or open API or something. And then it's like, and then it takes me like hours just to figure out how to document something that I could have just done a triple back tick and did a little JSON blob.

[00:55:49] **Ben:** But instead it's like this crazy referential API building, and I'm not saying that stuff is bad. I'm just saying keeping the barrier to entry super low for documentation feels like the right way to do it. As opposed

[00:56:03] **Carol:** I agree.

[00:56:04] **Ben:** everybody has to use these new tools in order to document text, you're like, oh,

[00:56:09] **Tim:** just put it in word and email it to your technical writer.

[00:56:12] **Ben:** I'll put in word and I'll export it as a PDF and I'll attach

[00:56:15] **Ben:** it in an email.

[00:56:16] **Adam:** Oh, my God. That's how we used to get screenshots for everything. It emailed word document with a screenshot in it, like.

[00:56:23] **Carol:** Good luck searching for that.

[00:56:25] **Adam:** All right, let's kill it there. Yeah.

## [00:56:28] Patreon

[00:56:28] **Adam:** So this episode of Working Code was brought you by confluence, the solidly three star documentation tool and listeners like you If you're enjoying the show and you wanna make sure that we can keep putting out more of whatever this is out into the universe than you should consider supporting us on Patreon, our patrons cover our recording and editing costs, and we couldn't do this every week without them.

[00:56:47] **Adam:** So special. Thanks to our top patrons, Monte, Gavin and Sean,

[00:56:51] **Ben:** Thank you.

[00:56:52] **Tim:** Three bagger.

[00:56:55] **Adam:** If you'd like to help us out, you can go to patreon.com/WorkingCodePod. All of our patrons get early access to new episodes. And our after show, tonight on the after show looks like from what I'm seeing here in the list, we're gonna talk about kids that don't know how to email, telling your kids, your telling your kids your salary.

[00:57:10] **Adam:** So they go to college and, yeah, we're gonna have to do the incident commander, what that

[00:57:15] **Carol:** Yeah, I need to know more.

## [00:57:16] Thanks For Listening!

[00:57:16] **Adam:** so, your homework this week, you know what, I wanna do it again. Let's do leave us a review. So if you would be so kind go to workingcode.dev/review, we've gotten a couple of nice reviews lately and, we want some more, you know what, honestly, I'm happy to say.

[00:57:28] **Adam:** out of all the reviews I've seen in there, they're all still five stars and I really appreciate each and every one of you who'd leave one in there. So thank you, uh, workingcode.dev/review

[00:57:37] **Tim:** me. I want more haters.

[00:57:38] **Tim:** I want more

[00:57:38] **Adam:** but don't leave it in the review. Tim's email addresses. we would, as always appreciate if you have any topics or questions that you'd like us to cover, you can send those to us on Twitter or Instagram @WorkingCodePod.

[00:57:52] **Adam:** You can join our Discord and chat along with the rest of our, listener communityat workingcode.dev/discord. you can email us at WorkingCodePod@gmail.com, or you can send your voice memo there. It's easy to record a voice memo on your phone. Email it to us, WorkingCodePod@gmail.com, and we'll play it on the show.

[00:58:09] **Adam:** That's it for this week. We'll catch next week. And until then.

[00:58:12] **Tim:** Remember your heart matters, even if you're an underpaid, technical writer.

[00:58:16] **Ben:** Oh, gosh.
