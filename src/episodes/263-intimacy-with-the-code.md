---
title: "263: Intimacy with the Code"
description: "This week is a conversation about what software craftsmanship even means anymore, when the tools are happy to do the caring for you."
date: 2026-06-11
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/c1f79016-9b2a-4467-8708-fcb6014dfbd3"></script>
<div class="redcirclePlayer-c1f79016-9b2a-4467-8708-fcb6014dfbd3"></div>

Getting unstuck has gotten so cheap that Ben can't remember the last time he actually learned something at work — and the struggle he's skipping was where knowing the code, and caring about it, used to come from. This week is a conversation about what software craftsmanship even means anymore, when the tools are happy to do the caring for you.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/263-intimacy-with-the-code.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Ben:** Throughput doesn't feel like it should ever be the North Star, 'cause

[00:00:02] **Adam:** No

[00:00:03] the North

[00:00:03] **Ben:** Star, then I feel like we just start making a lot of sacrifices.

[00:00:06] **Adam:** Well, it's like min-maxing in a video game, right? Like, in order to increase your charisma, you have to lose intelligence or dexterity or whatever, right?

[00:00:13] Like, so

[00:00:15] **Ben:** That is a really fun example

[00:00:16]

## [00:00:36] Intro

[00:00:36] **Adam:** Okay, here we go to show number 263. And on today's show, it's just Ben and myself, and we are going to get into software craftsmanship in 2026. What does it mean? What does it look like? What does it smell like? What does it taste like? Um,

[00:00:51] Yummy

[00:00:52] but first, as usual, let's start with our Triumphs and Fails. I did say, uh, it's just myself and Ben.

[00:00:56] Carol and Tim both had scheduling conflicts. But we figured, hey, you know, maybe, you know, 57th try is the charm. We'll aim for the oft-promised, ne'er delivered short show.

[00:01:07] Yeah

[00:01:10] and we'll probably fail once again, but, you know, might as well try. Ben, I'm gonna come to you first. What's going on,

## [00:01:14] Ben's Fail

[00:01:14] **Adam:** man?

[00:01:16] **Ben:** I'm gonna start with a failure, and this is not a, like,

[00:01:19] **Adam:** something

[00:01:20] **Ben:** I failed at recently per se, I'm sure listeners are familiar with the term gamification, I think was like peak hype, know, mid to late aughts

[00:01:33] **Adam:** Yeah, like

[00:01:34] **Ben:** People were like, "Oh, you can use game mechanics to make applications more engaging and, and drive behavioral changes." I think on the web it felt very new and exciting to have these ways to help boost the, don't know, success of a product. And I definitely bought in. I, I think I read some books on gamification. I took some, a course or two on gamification, almost certainly. You know, followed some people's presentations about gamification. I've referred several times to Mental Notes, which is a deck of cards. I think actually just a couple of episodes ago I referred to

[00:02:11] **Adam:** it

[00:02:11] **Ben:** And you know, you don't have to squint very hard to think of that as like a deck of cards about gamification of software. to paint it with like that brush strictly, but it is about how do we use human psychology to drive engagement more or less.

[00:02:27] **Adam:** Sure, yeah. Which is, that is what gamification is. It's, it's, it's appealing to those things. It's like a, it's a, it's a layer down

[00:02:36] **Ben:** So, so gamification was really popular for a while, and then at some point, the, the idea of dark patterns started to become part of the, the conversation about web stuff. You know, like automatically opting people into newsletters instead of allowing them to opt in.

[00:02:56] **Adam:** Hmm.

[00:02:57] **Ben:** whether they're opted out by default or,

[00:02:59] **Adam:** Yeah

[00:03:00] **Ben:** giving someone a free trial but then automatically charging them,

[00:03:04] **Adam:** you

[00:03:04] Right. Require your credit card in order to take a free trial, yeah

[00:03:07] and

[00:03:08] **Ben:** and so a lot of people started thinking about like, well, here's the stuff that's just like straight up, like not illegal, but you're definitely not thinking right about the user,

[00:03:16] **Adam:** Mm-hmm.

[00:03:17] **Ben:** started to point stuff like that out. Anyway, the wake of society basically saying, "Hey, social media is kind of terrible for all of us," and even kids are like, "I wish I could get rid of my Instagram, but I feel like I can't because the other kids are on Instagram, and if I'm not on Instagram, what do I do about it?" And, I feel like I've done a whole 180 in my mind, and I've only maybe like just recently thought more deeply about it, that gamification's probably terrible.

[00:03:45] **Adam:** Mm-hmm.

[00:03:47] **Ben:** what seemed like an exciting and, and I think genuinely, let's call it like-don't think anyone was ever trying to do anything nefarious with gamification.

[00:03:56] I think people were genuinely excited about just making better applications. I, I

[00:04:01] **Adam:** I can speak for

[00:04:01] **Ben:** myself. Like, it-- I'm like, "Oh, if I can make an application more engaging, doesn't that mean that the application is better?" Like, that's what I thought in my head. And now I feel like that's probably the exact opposite, Uh, l- I, I will, I will caveat it to say that

[00:04:14] **Adam:** gamification

[00:04:17] **Ben:** strictly being used to drive engagement just a, I think that's just a dark pattern, and I think I probably did a lot of things that I hoped would be good but probably weren't good in retrospect.

[00:04:30] And umI guess the failure is that I didn't quite see that in the beginning.

[00:04:34] I guess you could call it a failiumph

[00:04:36] **Adam:** in that

[00:04:36] **Ben:** I now see a little bit the error of my ways

[00:04:40] **Adam:** So I think that I, I, I want to agree and disagree with you.I, I, and I think that, in spirit, you're, you're on the right track here, at least in my opinion.

[00:04:51] and I wanna, you know, again, as we always do, reference Goodhart's law, which is what? Uh,once you start measuring something, it ceases to be a good measure. Once you start, once it becomes a, a, a metric that you're graded on, it ceases to become a useful measure.

[00:05:03] and, and like, I think that gamification as a technique has zero wrong with it. It is, it is a tool. It's like saying a hammer is a bad tool. A hammer's not a bad tool, it's just a, it's a bad screwdriver, right? so, I think, A, the lesson of the, the 2020s for me is engagement is, like, the worst possible thing that you could focus on and incentivize, like, Goodhart's law-wise, right?

[00:05:32] They, like, they were like, "Oh, we could make more money if we increase engagement." It's like the, the money machine. Engagement goes up, money goes up. But that has been terrible for society.and so,using gamification to increase engagement together has been terrible, and I agree with you on that. but I think that you could equally apply gamification to things that are, that would be a positive on society, and that would be a good thing, right?

[00:05:59] So, like, gamification... the, for me, the classic UI that I see for gamification is, on Stack Overflow, like, on my profile, there was a page, and I haven't been there for maybe a decade at this point. But there was a page where it was like, "This is how many points you are away from gaining this moderator ability," right?

[00:06:16] It's a little progress bar, and it's like, oh, if you leave, three more upvotes on ticket... O- on questions that should be closed because they're duplicates, then you gain this extra ability. And that really incentivizes my personality to, like, go spend an hour reading questions. And that, it, yeah

[00:06:34] **Ben:** ago, I was on a, a I think it was... It may have been called bodybuilding.com. This is like an old, old fitness forum,

[00:06:42] **Adam:** Mm-hmm.

[00:06:42] they

[00:06:42] **Ben:** had something where you couldn't have an avatar until you had left a

[00:06:47] **Adam:** certain

[00:06:47] **Ben:** number of comments.

[00:06:48] **Adam:** Oh, God

[00:06:49] **Ben:** So like, of

[00:06:50] **Adam:** course you're just

[00:06:50] **Ben:** leaving crap comments all over

[00:06:52] **Adam:** the place

[00:06:52] **Ben:** so you can have an avatar.

[00:06:53] you know,

[00:06:53] **Adam:** s

[00:06:53] Yeah.

[00:06:54] **Ben:** kind of idea

[00:06:55] **Adam:** Yeah.

[00:06:56] It, it's

[00:06:56] interesting

[00:06:57] **Ben:** 'cause, you know, gamification comes from presumably. I don't, I don't know the whole background, but I think

[00:07:04] **Adam:** about okay if

[00:07:04] **Ben:** I go into an arcade, and some arcades still exist, and you go and you're looking at one of the, you know, the standing consoles, and there's the

[00:07:13] **Adam:** leaderboard you have the top 10

[00:07:14] Yeah

[00:07:15] **Ben:** And, like, I, I don't think there's anything nefarious about that. People

[00:07:19] **Adam:** love to be able to beat

[00:07:19] **Ben:** their chest. You came in one in, uh, Galactic Earth Defenders or, you know, whatever kind of game,

[00:07:25] **Adam:** Space Invaders, sure. Yeah.

[00:07:27] it's

[00:07:27] **Ben:** exciting. You wanna... brag.

[00:07:29] **Adam:** Not sponsored. By Space Invaders

[00:07:34] **Ben:** I, I think where it gets shady, and I think this is kind of where we get a lot of our darker patterns from, is imagine you walk away from that arcade game and then you get an alert on your phone any time you fall down in that leaderboard.

[00:07:47] **Adam:** Mm-hmm. Yeah. Yeah

[00:07:50] **Ben:** like, what's the goal there? Is the goal for

[00:07:52] **Adam:** me

[00:07:52] **Ben:** to just come back and spend more quarters?" feel like

[00:07:56] **Adam:** obviously

[00:07:56] **Ben:** absolutely that, that's

[00:07:57] **Adam:** what it is So it's

[00:07:59] **Ben:** like you can u- you can have something that is both, I think, genuinely fun and a, and a way to create a better experience, and then you just tweak that same thing very slightly and it

[00:08:11] **Adam:** becomes

[00:08:12] **Ben:** a really negative pattern

[00:08:13] **Adam:** Yeah. Well, a- and to bring it back to the Stack Overflow thing, I think that there is absolutely zero coincidence in, like, okay, there's this, this behavior that they were influencing with that page of your own personal stats and permissions and, you know, incentives on Stack Overflow, and the fact that it became known for Nazi-esque, you know, like people on a power trip, uh, you know, just being rude and, and the worst possible social interactions on what was originally a very helpful website.

[00:08:47] So, yeah

[00:08:48] **Ben:** Let me, let me throw this out there because I don't, I genuinely don't know how I feel about this.

[00:08:54] **Adam:** I

[00:08:54] **Ben:** was listening to an interview last weekend or the weekend before with the guy who created Wordle, had,

[00:09:01] **Adam:** which has since

[00:09:02] **Ben:** You know, this was a personal project the guy made, and then I- it was purchased by New York Times.

[00:09:07] Okay, so no, it wasn't made, it was an interview. It was an interview with the guy who's, like, the head of gaming at New York Times. That's what it

[00:09:13] **Adam:** Okay

[00:09:14] **Ben:** And he was talking about how the thing that made Wordle really take off when you could start sending the results of your game via emoji

[00:09:25] **Adam:** Mm-hmm. Mm-hmm

[00:09:26] **Ben:** And, and I was having this, th- you know, introspection about how I felt about gamification kind of around this time, and I started to think about that, and I didn't know... genuinely don't know if that is a good idea or a bad idea. It's a good idea in that it obviously drove, like, a tremendous amount of engagement, and I think

[00:09:46] **Adam:** Hmm?

[00:09:46] Like

[00:09:46] **Ben:** the guy was saying, like, that's really when Wordle took off.

[00:09:49] **Adam:** Yeah

[00:09:49] But this

[00:09:50] **Ben:** idea of just being able to broadcast your to other people,

[00:09:55] **Adam:** Mm-hmm.

[00:09:56] **Ben:** I,

[00:09:57] **Adam:** There's like a global leaderboard, yeah

[00:09:59] **Ben:** I don't know if I like it.

[00:10:01] **Adam:** It was, well, yeah, I mean, it's, and it's, it's an interesting thought because I don't know if that technically would count as gamification. I would say if anything, it's like, it's creating FOMO, right? We can see more and more of my friend circle is participating in this thing, and now I'm feeling left out, so

[00:10:22] **Ben:** I don't know.

[00:10:23] **Adam:** Yeah

[00:10:23] **Ben:** My family is

[00:10:24] **Adam:** big

[00:10:24] **Ben:** into, like, our, like, half the messages in our family chat are people just sharing their Wordle scores, which since none of them listen to this, drives me bonkers.

[00:10:35] **Adam:** I am so happy that my family Discord is usually pretty quiet

[00:10:39] **Ben:** so anyway, that's me kind of refining my thoughts about

[00:10:42] **Adam:** stuff time

[00:10:44] Social media is evil

[00:10:46] friends

[00:10:46] **Ben:** becoming enemies, enemies becoming friends, things like that. Adam, what do you got going

## [00:10:51] Adam's Fail

[00:10:51] **Ben:** on?

[00:10:51] **Adam:** Well, that happened fast. so I'm gonna go with a failiumph, and it all starts with a triumph, which is I, spent the weekend skydiving, and I had a really, really good weekend skydiving. So I, I can't remember the last time that I did no work skydiving. Like, I usually, you know, I'll go out and I'll work all day doing tandems, and then I'll do, like, one fun jump at the end of the day sort of thing.

[00:11:14] Or if we don't have that many tandems on the schedule, then I'll do two or three. But, we call it a fun jump when it's just, you know, me doing whatever I want for fun, not, not a work jump, right? This last weekend, I went out and did two full days of nothing but fun jumps. during that period, I hit my 1,300th skydive, 1,300th skydive, which was fun.

[00:11:34] Yeah. a buddy of mine who's, like, quickly become one of my best friends at the drop zone, I, I took him for his very first skydive. He was a tandem passenger, a, a year... not even a year ago, August of last year. and, he, you know, figured out that he loved the sport and has joined and has been, you know, out a lot.

[00:11:55] And, a week or two ago, I think it was about two weeks ago, he hit his 100th jump, and one of the things that we do to celebrate you when you hit your 100th jump is we surprise you and pie you. We hit you in the face with a pie. Um,and, normally we would let you, like, build anxiety, like, for, like, a month, right?

[00:12:17] We would do nothing. You know, we'd... People would be cracking jokes, "Oh, we're gonna get ya," but you never know when it's gonna come, right? And we intentionally let it go for, like, at least a month because you're... we want you to be, like, anxious about it, and then to finally start going like, "I wonder if they don't like me enough," or, "I wonder if, I wonder if they forgot maybe.

[00:12:35] maybe I should tell somebody." And then boom, pie to the face when you're not expecting it, right? Well, this guy is moving, to another state in a couple of weeks. he's going to med school. So, I had to pie him before he left. So I, I got to pie him this weekend as well, right? So this is, this is just, like, a tremendously good weekend for me.

[00:12:53] A lot of good stuff going on. It was great weather, just a lot of fun. and then so I said this is a failiumph, and that's because on Monday I had to come into work. And it, it's not just, yeah, not just work in general, but, like, the th- the, the next task on my to-do list, and it was extremely high importance and reasonably high urgency, was, basically writing API documentation.

[00:13:18] So I mentioned last week about, like, having AI generate OpenAPI specifications for our API, and that did a lot of the heavy lifting of, like, building out the skeleton and even hanging a little bit of meat on that skeleton, right? Like, types, data types, min and max values and lengths of strings and stuff, 'cause it can figure all that, that out from the database and the code.

[00:13:45] but what that can't do is explain stuff, right? So like if you're looking at an API response for gift data, right, somebody has given money to the school, and then one of the properties is source. What does that mean? Right? I have to... Th- th- so there's a place in the OpenAPI schema spec, I guess is what you'd call it, where you like, this is where you write notes about a, a property.

[00:14:09] You can say, "This is the description of it." So you say, "Okay, well, in this case, source means XYZ." And so we've got something like 150, possible responses that need documenting, and I don't know what the average... Yeah, I don't know what the average number of properties is in them. It's gonna take me fricking forever to get through 'em all.

[00:14:28] but I do have the list of like the top 10 that this particular customer wants. And, it's been two days, and I have done one file per day like staring at this one file, working on it all day, and it i- it's like, it's like leaving the water park and, and being forced to eat a turd sandwich. Like, that's

[00:14:50] Okay

[00:14:50] **Ben:** So For all the stuff that I hear you talk about using AI for,

[00:14:55] **Adam:** Yeah

[00:14:55] **Ben:** I feel like this is the, is the bread and butter. Like, just

[00:15:00] **Adam:** No. It, it's, it's institutional knowledge, right? It's like, I'm trying to think of a g- a good example. So like, there's a... We have a transaction table that logs financial transactions, right? And, okay, transaction ID, easy enough. Amount, easy enough. Date, time created, easy enough. These are easy things to write.

[00:15:19] But then you get like auth code and, we have a column, I, I forget what it's... there's a better name for it, but I forget what it is, but it's PNREF is what we call it, P-N-R-E-F.

[00:15:29] this like the thing

[00:15:29] **Ben:** that comes back from the

[00:15:30] **Adam:** processor

[00:15:31] right. We get two res- two, uh, useful codes. One of them is the authorization code, and the other is some other confirmation code of some sort, back when we make a, a, a credit card charge, right?

[00:15:43] We collect some money. We get those two codes back. We're supposed to hold onto them in case we need them for confirmation purposes, whatever. Okay. Well, I could, I can just tell you this is... I, I mean, the proper name is auth code and PNREF, and you could maybe sort of figure that out, but like, you know, there's not a whole lot to go on, right?

[00:15:59] And it's, there's a lot of little stuff like that. and, and it's... There's a lot of like, just basically you're documenting the way the application works in the data model is effectively what it works out to be. not entirely, but enough that, you know, th- somebody who doesn't really understand what your application does but has to integrate it with...

[00:16:21] Like you, you're just working on the, the glue layer, right? I'm, I'm not a user of the application. I'm not a user of the data once we ingest it. I just have to take the data from the developers and bring it to the other people. and so I have to document all that, which is no fun. It needs to be done. And I am, I am, uh, using AI to sort of fill in the gaps, but it's, it's a lot of, like I was saying, institutional knowledge and, personal discretion about like, okay, clearly I don't need to put a description on home_address1 and home_city, right?

[00:16:57] Like these are pretty obvious. But,uh... So there's discretion, there's, there's like figuring it out there, and then there's just like sometime... There's been like one field a day that I've had to take to my teammates and be like, "I think I know what this is.

[00:17:09] Here's the description I've written so far. Did I miss anything? Could it be better stated?" That sort of thing. So it's work that needs to be done, and that's what work is. That's why they pay you, right? 'Cause otherwise it wouldn't get done. Nobody wants to do it for free

[00:17:30] **Ben:** Well, hopefully it gets easier.

[00:17:34] **Adam:** That's okay. The... It will end, and then there will eventually be something more fun to do, I'm sure

[00:17:39] **Ben:** It'll be end and then it's time for your SOC 2 compliance

[00:17:42] **Adam:** certification

[00:17:43] God, you son of a

## [00:17:44] What Is Software Craftsmanship?

[00:17:44] **Adam:** Oh, all right. Well, on that note, let's, change gears and talk about software craftsmanship. What is software craftsmanship, Ben?

[00:17:55] **Ben:** All right. Well, I think this is a great question to start with because this is something that I think both you and Tim have brought up to paint a picture. Are we woodworkers or are we building a furniture company? I bring that up because in my mind, software craftsmanship has sort of been

[00:18:18] **Adam:** things coincidentally

[00:18:20] Right

[00:18:21] **Ben:** It has been I'm getting good at my craft I am building a product.

[00:18:27] **Adam:** Mm-hmm.

[00:18:27] **Ben:** for the last 20 whatever years, those have had a pretty large overlap. It was

[00:18:33] **Adam:** hard

[00:18:33] **Ben:** to do one without the other. And where we are now, it's m- a little bit more of a question mark about in order to build a successful company that produces software, do I have to be a software craftsmanship the way that I used to think about it?

[00:18:53] **Adam:** Yeah. I like that you immediately went to the woodworking metaphor because, like, there's different layers to it, and I don't wanna be derogatory at all, but I will just, like, kind of throw this out there, which is, like, there's carpentry, r- which is like, you know, somebody's building cabinets to throw into a house or they're, they're framing up the doorways of the house, that sort of thing.

[00:19:14] And then there is what people refer to as, quote-unquote, "fine woodworking," which is like, I wanna make something that has visible dovetails on it, and they have to be

[00:19:25] **Ben:** lathe.

[00:19:26] **Adam:** right. They have to be perfectly gapless and, and crisp corners and, you know, just aesthetically pleasing. And that has nothing to do, very little to do with utilitarianism.

[00:19:38] That's very much like I needed a coffee table, and I could've, yeah, I could've spent 20 bucks and gotten a, a rectangle from IKEA with a Swedish name, but I j- instead I chose to spend $600 on, on materials and $6,000 on tools to build something that I feel like looks pretty and that I-- it brings me joy to have in my home

[00:20:00] **Ben:** Now,

[00:20:00] here's an interesting thing because woodworking is an interesting industry in so much as price and quality,

[00:20:10] **Adam:** Mm-hmm.

[00:20:10] **Ben:** tend to go more hand in hand.

[00:20:13] **Adam:** Okay

[00:20:14] **Ben:** the IKEA example, you might spend $100 on an IKEA bookshelf,

[00:20:19] **Adam:** Yeah

[00:20:20] **Ben:** and, like, that baby's never moving 'cause the moment you try to take it apart, it's like the wood starts to

[00:20:25] **Adam:** Mm.

[00:20:25] **Ben:** wooden dowels don't squeak in as well anymore.

[00:20:28] Like, you're not moving from apartment to apartment with a small IKEA bookshelf. if you went to, like, a-- none of these names are gonna make any sense, but, like,

[00:20:38] **Adam:** A Room & Board

[00:20:39] **Ben:** or, like, a Jensen-Lewis or a, like not a big chain

[00:20:43] **Adam:** A handmade or something, yeah

[00:20:44] you

[00:20:44] **Ben:** spend, know, $700 on a bookshelf, like, that baby's coming with you to every apartment you

[00:20:51] **Adam:** ever live in

[00:20:52] That is now heirloom furniture

[00:20:55] **Ben:** Whereas in something like electronics, I-- there's not necessarily a guarantee that the $100 piece of whatever is that much worse than the $700 piece of whatever. Like, it probably is not as good, but not like IKEA versus handmade furniture

[00:21:15] **Adam:** Right. Yeah, well, so to, to I guess bring it back to a point on what is software craftsmanship, I think that ultimately what we're talking about is caring about leaving the code... I guess it's, it's caring about the craft of, writing the code and maintaining the code and all the things that go into working with code that aren't just producing the desired output.

[00:21:43] Would you agree? Yeah

[00:21:44] would

[00:21:45] **Ben:** agree with the caveat that

[00:21:49] I'm, I've... And I think this is the heart of the struggle is

[00:21:54] **Adam:** can

[00:21:54] **Ben:** you sacrifice on that thing and still care about

[00:21:58] **Adam:** what

[00:21:58] **Ben:** the output is?

[00:22:00] **Adam:** like

[00:22:00] You find

[00:22:01] **Ben:** to, to some degree, I, I feel like they're interlocked and maybe they're not as interlocked as they

[00:22:07] **Adam:** used

[00:22:07] **Ben:** to be, but they're still... You know, if you wanna build quality software, I still believe you have to have a respect for the of it as well

[00:22:18] **Adam:** Well, it's an interesting take because, so quality is really the k- is doing a lot of heavy lifting in that sentence, right? So quality software could just be software that produces a desired output, or it's a black box, I put in the thing and I get the r- the correct answer out, then it's a calculator. And who cares if it's a jumble of spaghetti code wires between who...

[00:22:39] You know, if it's, it's is it an if statement that's like, "If, if the requested calculation is one plus one, then print two." "If it's one plus two, print three." Not a good calculator, but it's a calculator. versus, you know, something that is actually well implemented and efficient and easily maintainable and extensible and, future-proof, right?

[00:23:00] These are things that go into craftsmanship in general

[00:23:04] **Ben:** I mean, look, if you think

[00:23:05] about when we did Clean Code as a book club book,

[00:23:10] **Adam:** Mm-hmm.

[00:23:10] just

[00:23:10] **Ben:** so much of what we've talked about over the years, no matter what you call it, it all, it sort of all comes down to maintenance. How easy can I maintain this thing that I'm writing?

[00:23:20] **Adam:** Oh, yeah

[00:23:21] **Ben:** And that to me is where a lot of the conversations about AI down, not so much in that they're wrong, like, they're untested.

[00:23:34] **Adam:** Sure

[00:23:34] Oh

[00:23:34] **Ben:** can you build good software that was built with AI?" I'm like, "I don't know. Ask me in six years when I'm

[00:23:40] **Adam:** still maintaining that piece

[00:23:42] Yeah. W- before we get to AI stuff, you, you, I think had a really interesting point there, which was...

[00:23:49] you know, you said it's all about maintenance, and I think that to rephrase that, I would say code has to...

[00:23:58] You have to understand it to write it, and that's an important part of writing it. But good code is code that will be easy to understand and read and, you know, uh, it's properly, yeah, and modified, but, like, it's properly abstracted so that in the right situation you can skim past it and understand, okay, this is what happens in that abstracted layer, right?

[00:24:18] that sort of thing. Like, and I think that when you make that jump from I know how to write code that can do this thing to I can write good code because it's properly abstracted, because it's maintainable and readable, that sort of thing, like that's the moment that you are graduating from like apprentice craftsman to like journeyman or whatever the next level is, right?

[00:24:39] **Ben:** And I think that, again, historically, we've kind of gotten have our cake and eat it too, that we get

[00:24:48] **Adam:** I hate that phrase. It, it needs to be the other way. It should be I get to eat my cake and have it too. I think it makes so much more sense that way

[00:24:58] **Ben:** That's true.but like historically, we as people who love the craft gotten to enjoy building the right abstractions, got to enjoy finding the correct seams, finding the way to organize the code that feels elegant and easy to maintain. all of those things also unlocked the ability to create successful products.

[00:25:23] 'Cause ultimately, you build something that you can't maintain and you can't extend, it becomes harder and harder to add to it over time, which means over time you can't respond to customer requests, you can't evolve the ideas behind the product, and the product begins to suffer.

[00:25:40] **Adam:** we've had

[00:25:41] **Ben:** this sort of vast overlapping Venn diagram where the stuff that I love to get better at also happened to be the stuff that drove successful products. You know, with exception, but mostly with And I s-still think that's true.

[00:26:01] **Adam:** I still

[00:26:01] **Ben:** wanna be a craftsman. I still wanna get better at my code. I still wanna find better patterns. and that... I know we don't wanna make this about AI, but just to say that e-everything that I use when I'm doing AI today is based on all of the craftsmanship learning that I've done in the past

[00:26:23] **Adam:** Absolutely. Yeah, I mean, that's what we're talking about when we say like the, the real work of working with AI is taste, right? That taste is lessons learned over a career of doing this without AI

[00:26:34] **Ben:** Right

[00:26:35] Right, right, Exactly. So I still

[00:26:38] strongly believe That maybe I don't have to have my hands on the code all the time. But when I'm involved in an area of an application that is tricky or involves an area outside of my comfort zone or outside of my depth of knowledge, still want to be involved in the low-level details so that I can continue to build up perspective that gives me the taste, so that the next time I deal with that kind of a situation, then I can just say to the AI, "Oh, I know this.

[00:27:11] Use XYZ patterns and put the files here and follow this other example over here," and Bob's your uncle, as

[00:27:19] **Adam:** they say

[00:27:21] Another phrase I don't like. Anyway.

[00:27:23] I

[00:27:23] Yeah,

[00:27:23] understand all

[00:27:25] it doesn't make a whole lot of sense.okay, so I think we've done a pretty thorough job of explaining what

## [00:27:31] Getting Unstuck vs. Getting Your Hands Dirty

[00:27:31] **Adam:** craftsmanship is, so let's move on from that. Like, what... Why is this an important topic, right? So what, what makes softsw- software craftsmanship in particular more difficult right now?

[00:27:42] I'm sure we have opinions.

[00:27:45] **Ben:** I've-- To me, the

[00:27:47] difficulty isn't so much a change in anything except expectation.

[00:27:55] **Adam:** Okay

[00:27:55] **Ben:** continue... If,

[00:27:56] **Adam:** if

[00:27:56] **Ben:** anything, it's easier to be a craftsman now than it has ever been before because are so many opportunities to get unstuck. You know, it used to be you're hitting a dead end, there doesn't seem to be any blog posts written about it,

[00:28:13] **Adam:** Mm-hmm.

[00:28:13] about

[00:28:14] **Ben:** it, and you're sort of like stuck

[00:28:18] **Adam:** That is the worst feeling in the world

[00:28:19] it's the

[00:28:19] **Ben:** worst.

[00:28:20] And now the reality is, if you get hit a dead end, you could probably ask Claude or whatever kind of agent model you're using, and it'll, you know, in my experience, more often than not, it'll tell you to get unblocked, whether or

[00:28:36] **Adam:** not

[00:28:36] **Ben:** it can point you in the right direction or just give you, you know, a verbatim solution

[00:28:41] **Adam:** I do think that that is a superpower of AI. Like, the, it, that is, definitely something that has been unlocked with the LLM coding model stuff. Like, okay, you hit one of those problems. There are zero blog posts. There's, like, one person asked about it on Stack Overflow nine years ago. There-- And maybe if you're lucky, there's a comment where he says, "Oh, never mind, I figured it out," and doesn't give the answer.

[00:29:04] Right

[00:29:04] Um

[00:29:05] it's

[00:29:05] **Ben:** like, a... Or, or, or you'll find

[00:29:07] **Adam:** like the

[00:29:07] **Ben:** only comment to it is you from 10 years ago saying

[00:29:10] **Adam:** Yeah.

[00:29:11] **Ben:** here for other solutions."

[00:29:13] **Adam:** Yeah. so, in the, if you happen to be in the circumstance where the, the code that you're struggling with is open source, right? If you're trying to do... I, the, the quintessential memory that I have in this where I got stuck in this situation was like a Visual Studio, I think it was like a C\# library I was working with, and I, you know, I'm not as, not a regular C\# user, and so I was struggling, and it was like Microsoft objects working with Outlook and, like, super sort of arcane knowledge.

[00:29:42] and I don't think it was open source. But basically, if you get into one of those situations and it happens to be like, "Oh, I'm, what do I do with this library? I don't understand, but it's an open source library," you can point the agent at it and say, "Here's the source code. Here's what I'm trying to do.

[00:29:54] This is the problem I'm having. what am I doing wrong?" A- and it will probably within minutes, like read the s- the source code, understand how it works, understand what you're doing, figure out what you're doing wrong, and possibly give you the answer or a couple of things to try at least, like next steps for debugging that you couldn't have thought of yourself

[00:30:13] **Ben:** Right. So the,

[00:30:15] the depth that you go into understanding the thing that it's telling you, I think is the point of tension these days,

[00:30:23] **Adam:** Okay

[00:30:24] **Ben:** right? Because Claude has the information. It, it is a matter of how important is it for you to take the thing that it is showing you and make it frictional enough so that you remember it.

[00:30:39] You know, like how hands-on do I need to get? How much do I wanna not copy-paste, but actually just look at your code, your being Claude's code, and maybe try to type it out on my own. Again, just to like develop that sense of intimacy with the code, to develop that sense of muscle memory, to kind of drive the pattern into your head. how much do you say like, "Oh, this is... What I'm doing here is just mechanical."

[00:31:04] **Adam:** Mm-hmm.

[00:31:05] **Ben:** it's a very low-level implementation detail, and it's not really gonna pay itself forward, and maybe that's an area where I do just wanna have Claude Code hammered out. I just don't care. And I'm not, I'm not saying that either of those is better or worse.

[00:31:17] I think that both of those can exist, and deciding which things are important is part of the software craftsmanship. You know, figuring out, you know, which, you know, which... Like when do you wanna get your hands dirty? When do you not wanna get your hands dirty? And I think the, the biggest point of contention is this idea that no one should ever be getting their hands dirty anymore.

[00:31:40] **Adam:** And I think

[00:31:40] **Ben:** that's the problem, is, is that mentality

[00:31:44] **Adam:** Yeah, I would agree with that

[00:31:47] **Ben:** Like

[00:31:47] I'm using Parcel.js, it's a JavaScript bundler, and I was trying to

[00:31:51] **Adam:** I'm pretty sure you mentioned that in, like, the first 15 episodes of this show. You've been using that thing forever

[00:31:57] Yeah

[00:31:57] **Ben:** I've been using it for a bit.and I'm trying to get it to play nicely with ColdFusion, l- like the work that I do is not about JavaScript bundling.

[00:32:08] **Adam:** It is

[00:32:08] **Ben:** a tool that I'm using to try to get some stuff done efficiently, and the other day I tried to include a variable a path that Parcel was gonna output, and I didn't think it had any mechanical impact.

[00:32:24] I thought it was like literally Parcel was just gonna do a string replacement and such

[00:32:28] **Adam:** and such and

[00:32:28] **Ben:** and I'd be done. Parcel complained that, oh, it couldn't resolve the file because it wasn't a valid URL because it had pound signs in it for my ColdFusion variable sign, you know, interpolation. And so this is a, this is a case where I just need it to work.

[00:32:43] I don't

[00:32:43] **Adam:** actually care about

[00:32:44] **Ben:** how Parcel works. It's just doing a thing. I ask Claude. Claude says, "Oh, because it's actually doing some sort of file path resolution, so it can't have such and such in it, but you can get around it by doing a plugin to Parcel that'll run after the code has been generated, and then you can manipulate the code."

[00:32:59] I'm like,

[00:32:59] Great."

[00:33:00] Like, I, I'm, I'm glad that I know that that works, but like that's not the thing I wanted to learn.

[00:33:06] **Adam:** Mm-hmm.

[00:33:07] unblocked

[00:33:07] **Ben:** me to do the rest of the stuff that was more important, I thought. A- and that's just a judgment

[00:33:12] **Adam:** call

[00:33:12] **Ben:** You know, I could've spent more time digging into it, but I just... It wasn't the thing that I thought was gonna be adding value to how I looked at the software. So, think it's healthy to be able to make judgment calls like that. What I think becomes problematic is when people feel so much pressure to 10X or 100X productivity even if they're interested in something from a craftsmanship standpoint, they feel like they can't do that anymore because that's just not how software's built.

[00:33:44] **Adam:** Hmm. It's an interesting thought,

## [00:33:46] Two Worlds of AI Use

[00:33:46] **Adam:** yeah

[00:33:47] I wanna take us on a little bit of a tangent, and I'm hoping it will sort of naturally bring itself back to this conversation of software craftsmanship. So I had lunch today with a friend of mine and listener of the show. Hi, Chuck. and, he specifically was kind of asking me and, and contributing to a, a discussion on the differences between the way that you use AI and, and describe your use of AI here on the show versus how I describe my use of AI here on the show.

[00:34:17] And I didn't have a lot of thought about that in the moment, but I think w- ultimately for me, what it comes down to is I th- I think the, the majority of what's driving us in different directions, there's probably two things. There's probably, like, our personalities and the way we think about them, but also I'm primarily using it to work on a code base that is, like, in the vicinity of 15 years old, that is almost entirely hand-coded, that I personally had my hands on for at least 10, like, or let's say at least, you know, 80, 75, 80% of all of that code, right?

[00:34:59] Was, at least went through my hands with code review, if not being written by me.versus, and please correct me where I'm wrong here, but, the sense I get is that where you're... When you're at work right now, you are working primarily on a stack where you really don't understand all the bits and bobs, right?

[00:35:18] It's not CFML, it's, it's React and some other, like, not, it's not, MySQL.

[00:35:23] and CockroachDB

[00:35:25] Yeah. Which is

[00:35:26] used

[00:35:27] name three things that Ben has never used or never, never understood.

[00:35:31] I'm

[00:35:31] **Ben:** pretty sure it's also using Tailwind,

[00:35:33] **Adam:** Oh, yeah.

[00:35:34] **Ben:** not used

[00:35:35] **Adam:** Right. And so I think that that's hugely going to affect how you think about working with AI because you, you kind of have to ask it to carry a little bit more weight, right?

[00:35:45] You have to lean on it to do more of the understanding of h- of the syntactical part at least

[00:35:51] **Ben:** I mean, it's fascinating because I, I'm at both extremes, meaning at work it's, I hate to say vibe coded 'cause I, I know that term has like kind of come in

[00:36:03] **Adam:** and now fallen out

[00:36:04] yeah

[00:36:05] **Ben:** favor. but it's basically vibe coding. And then on the extreme opposite end, I work on my blog architecture, is 100% hand-rolled, you know, for 20 years.

[00:36:18] **Adam:** Mm-hmm.

[00:36:19] **Ben:** and I'm using AI there, but I'm still writing, hand writing probably like 90 to 95% of the code. And it's not like I'm making large, massive changes. You know,

[00:36:32] **Adam:** a

[00:36:33] Sure

[00:36:33] **Ben:** is very old, and it's incremental,

[00:36:37] **Adam:** And

[00:36:38] stable

[00:36:39] **Ben:** and, it's stable. And, and I find where I'm getting the most value out of Claude in that context

[00:36:47] **Adam:** is

[00:36:48] **Ben:** conversational, talking through a problem, understanding where maybe my sticking points are, or if I'm having trouble finding the right shape of something. I, you know, I'll, I'll, I'll literally say, "Cool, like, I'm having trouble coming up with a name for something, and I feel like that means that I'm not landing on the right pattern. Help me think through like why I might be struggling." And, and it'll come up with really, really good and insightful feedback about, "Oh, you're close, but you're, you're having something do double duty, and really this is supposed to be out here because it's a different concern." And so I have like these actually really productive, effective conversations.

[00:37:27] **Adam:** And then

[00:37:27] **Ben:** if it's low-level stuff, go and hand implement it, and then I'll have Claude at it. I say, "Hey, look at the unstaged changes in this, in this branch. let me know if v- if I'm making any obvious or, you know, not obvious mistakes here, or edge cases I haven't considered, or did I deviate from the plan?" And it gives really good feedback. Where I have it just jam out a bunch of code is usually like we've talked about a bunch of stuff. I wanna move a bunch of files around to shift the way some sort of pattern works, kinda like

[00:38:00] **Adam:** with your ORM

[00:38:01] **Ben:** stuff.

[00:38:02] **Adam:** Yeah

[00:38:02] **Ben:** And I'm like, there's no magic here. It's just, you know, like I just don't wanna do all of the file moving and then going and updating all of the path references.

[00:38:12] Like that stuff, it's actually really, really, really good at, it seems. So I'll say, you know, "We have a plan. Do it." And it moves around 60 files, and it's flawless, you know. Or like it makes one mistake,

[00:38:24] **Adam:** Yeah

[00:38:25] **Ben:** and, like that is also really valuable because none of that is really part of my learning process.

[00:38:30] That was just the kinda chorey,

[00:38:33] **Adam:** Yeah

[00:38:34] **Ben:** part of it that's not... Like I already have the idea in my head of what I wanna do. I just need it to get done.

[00:38:39] **Adam:** You, so you are, it sounds like you're using the LLM to learn, and then you're just letting it handle the tedium of like, okay, I've learned the thing. I, I learned this new pattern, I learned what, you know, improve how I'm implementing this pattern or whatever. That was the part that I cared about, and now the part that I don't care about is making the files, you know,

[00:39:02] **Ben:** If I'm

[00:39:03] **Adam:** the organization

[00:39:04] **Ben:** net new files, I will often still hand code them I want that intimacy with the

[00:39:14] **Adam:** code

[00:39:15] **Ben:** like, I want it to be something that I remember. Like, it's a sense memory. I wrote it. I can kind of visualize it in

[00:39:21] **Adam:** my head

[00:39:23] **Ben:** Where I let Claude really write a bunch of code is, is one, if it's like a... Going back to Parcel.js, like if it has to write a plugin for Parcel.js, I just want it to take the first shot at that because it's, it's not that important to me, and it's gonna do a good job, and it's JavaScript, so I'll be able to read it anyway. And then probably what I'll do is I'll go in and delete like half the comments that it put in because the comments, even for someone who loves comments, the comments that Claude puts in are just a bit much.

[00:39:55] **Adam:** Man, I have like the exact opposite experience. I have code, I have code that's been around for a really long time that has good comments in it. You know, it's not saying this, what is it? You know, it's not s- it's not saying like, "Add audit row to database." It's like, "This is why we need to audit this," or whatever, right?

[00:40:15] And I'll, I'll be making a change, and it's, not even, it doesn't even change the code. It just is like, it seems like it arbitrarily decides like, "Oh, this comment is unnecessary. Delete." And it has nothing to do with the change that we're also making to this file. And I have so many times cursed at various LLMs.

[00:40:32] Like, don't delete comments, e- especially if they have nothing to do with what we're working on

[00:40:38] **Ben:** Yeah. The thing that drives me crazy is it'll leave parts of the comments and it'll reference things that have nothing to do with the code itself.

[00:40:45] **Adam:** Mm-hmm

[00:40:46] **Ben:** it'll say like, "Oh, we're doing this here because

[00:40:48] **Adam:** some

[00:40:48] **Ben:** of our decision-making has been deferred to phase 10 of the plan." And

[00:40:51] **Adam:** Yeah. Yeah.

[00:40:53] plan

[00:40:54] right

[00:40:54] **Ben:** I I, did have a plan, but it has nothing to do with

[00:40:57] **Adam:** what's actually code ticket somewhere

[00:41:01] Yeah, I see that, that kind of artifact leaking through from time to time too

[00:41:05] **Ben:** So, you know, again, like I'm, I'm, I'm... I have my foot on both sides of this fence where I

[00:41:12] a whole bunch in one place and a whole bunch of very different type of work in another

## [00:41:17] Responsible Vibe Coding

[00:41:17] **Ben:** place

[00:41:17] **Adam:** Yeah. So you, you actually said earlier, you know, for lack of a better word, the, the work that you're doing on the clock at your job is kind of vibe coded stuff because it's, because it's not a stack that you're familiar with, and I guess maybe we should responsibly disclose here, like, your company knows this, right?

[00:41:35] They, they knew what your skills were when they hired you. Yeah, yeah. But they, they knew, they knew what they were getting into when they hired you. They knew you weren't a Python CockroachDB React Tailwind developer, and they were like, "Okay, well, this is the stack, so figure it out, make it work," right? And so that's what you're doing.

[00:41:51] and I would say, like I, I would still call it vibe coding, but like maybe like let's call it responsible vibe coding, right? You're like, I think the vibe in vibe coding comes from, "I don't know how it works, I just want it to work," right? Like I... "This is the outcome, give me the outcome," right? And I think that the responsible part comes from, "Okay, it...

[00:42:13] I asked it to do a thing, it did something, and now I'm going to read that code. I'm gonna code review it and like try to understand." The look on your face.

[00:42:25] I

[00:42:25] I uh I

[00:42:26] Should I finish my sentence or do you just wanna cut that off right there?

[00:42:29] **Ben:** look, I'll say this. I am trying to be as responsible as I can given the way that we're building this software,

[00:42:38] **Adam:** Okay

[00:42:39] is

[00:42:39] **Ben:** that I'm trying to have conversations with Claude to make sure that we understand what it is we're trying to do.

[00:42:47] **Adam:** Mm-hmm.

[00:42:48] **Ben:** have conversations with Claude where I have it try to find issues with the code that it's written, which, you know, watches the watchers kind of a

[00:42:56] **Adam:** situation

[00:42:57] Mm-hmm.

[00:42:58] **Ben:** and I will say that we did

[00:43:02] it just seems to have stopped working yesterday, were having Claude Code review bot on GitHub run every time you pushed a pull request, which inevitably found issues.and Claude is writing tests,

[00:43:18] **Adam:** and

[00:43:18] **Ben:** I am obviously using the application, and I will add things to the CLAUDE.md file about security

[00:43:28] **Adam:** assertions

[00:43:28] **Ben:** and not like, "Don't make mistakes."

[00:43:30] **Adam:** More like

[00:43:32] **Ben:** you know, every route should pass through the currently authenticated user using this mechanic, and routes should be secure by default, and any route that doesn't adhere to this has to explicitly opt out by doing such and such. Like, it's not like I did that from day one.

[00:43:47] **Adam:** That was

[00:43:48] **Ben:** That was, like, "Oh, see if you can find any issues with the code," and Claude comes back with like, "Oh yeah, 80 of your routes have no security whatsoever."

[00:43:55] You're like, "Oh, that sucks.

[00:43:57] **Adam:** Yeah

[00:43:57] fix

[00:43:58] **Ben:** that."

[00:43:59] **Adam:** And then

[00:43:59] **Ben:** how do we make sure that doesn't happen again? so I'm trying to be responsible. I have not looked at the code.will say if you say, "Is this responsible?"

[00:44:10] **Adam:** in

[00:44:10] **Ben:** the same way that we were talking about maintenance earlier, I'm like, "Ask me in five years."

[00:44:14] **Adam:** Yeah, sure. Well, you know, honestly, as long as the tooling is still around, like, the, that's one nice thing about LLMs is you can feed them bad code and they will understand it and they won't complain about it

[00:44:28] Mmhmm

[00:44:29] as input, right? Like,so e- e- e- even, like, even if you're... Okay, so you're vibe coding this thing now, maybe it's not the cleanest code, but it's getting the job done, right?

[00:44:41] for some, for some degree of success, you're hitting success, or for some measurement of success, you're hitting success. and if in five years, you know, newer models have come around and you are, you're still working on it, you can be like, "Okay, well, you know, let's refactor this part of the app," and, you know, try to find areas where the code could be improved for efficiency or security or, you know, whatever, organization.

[00:45:07] there's gotta be, you know, a, a future there, right? Like, just because it's, just because it could generate trash today doesn't mean it, it will always be trash, I guess is kind of what I'm getting to.

[00:45:17] **Ben:** And I don't think that the code it's writing is trash. I don't mean to insinuate that at all. And based on the issues that come up in the conversations that I'm having with Claude, it is thinking through pretty deeply about the flow of data and how conditions work and, and like it, it does seem to have a very solid grasp of the extent of it all.But like

[00:45:46] **Adam:** if

[00:45:46] **Ben:** I was a betting man, and I'm not a betting man, but if you were like, "Would you be willing to bet $1,000 that there'll be no unfortunate errors that make its way to production in the next year?" I'm like, I don't wanna take that bet."

[00:46:00] **Adam:** Sure. I wouldn't do that for the code that I'm handwriting.

[00:46:03] Right. But like at I'd have

[00:46:05] **Ben:** I'd have, some basis for that bet if I wrote the code.

[00:46:10] **Adam:** Right Yeah

[00:46:10] Then

[00:46:11] **Ben:** it's like at least it's an educated decision, whereas now it's... I

[00:46:15] **Adam:** It's a vibe decision

[00:46:16] Yeah it's a decision

[00:46:18] Exactly

[00:46:19] **Ben:**

[00:46:19] **Adam:** So I, I actually like the, where this discussion went. So, you know, where I started was you are doing responsible vibe coding, and I was trying to get to like, okay, yes, you're vibe coding it, but it's... You're then reviewing the output and, at least applying your taste in terms of patterns and, you know, whatever you can pick up from...

[00:46:41] 'Cause it-- these are all, descendants of C, right? Whether we're talking Python or CFML or whatever. Like, basically they look the same. JavaScript. They all come really close to looking like the same language. So we can kind of read it and understand it like, okay, the function definition syntax is different, but it's, it's a function, uh, and it has arguments.

[00:47:00] and you're telling me you're not doing that. But what you did say is, instead of that, you're spending what sounds to me like potentially hours prior to writing the code, like having these philosophical discussions, trying to get to the nitty-gritty of like, oh, there could be a race condition here versus, you know, like, the, the database write efficiency of this particular thing is super important or, or we need to have super resiliency for this piece because there's a, a possibility of data loss if we lose power in that moment or something.

[00:47:30] Like, that, that forethought going into it, I think helps steer in a lot of the same ways that you would as an afterthought from code review

[00:47:42] **Ben:** I think you're probably giving me too much credit.

[00:47:45] **Adam:** I tried.

[00:47:46] but that is but but that is intent meaning that

[00:47:49] **Ben:** I'm Okay, so this, this application was written in phases, and the first phase was very much

[00:47:55] **Adam:** a

[00:47:56] **Ben:** just shotgun, here's 25 product requirements documents, make the application. Go,

[00:48:04] **Adam:** go go

[00:48:05] Mm.

[00:48:06] **Ben:** and I'll be straight up honest with you, the plans that Claude was creating were so freaking long and so

[00:48:13] **Adam:** verbose

[00:48:14] Yeah

[00:48:15] **Ben:** I'm, I'm just not reviewing that.

[00:48:17] **Adam:** Yeah. No, in the days of like Opus 4.6, Opus 4.7, that's what it did. It spit out miles of plan documents

[00:48:25] **Ben:** Yeah. So that kind of got us to phase zero,

[00:48:31] **Adam:** Mm-hmm.

[00:48:31] which was like

[00:48:32] **Ben:** okay, now there's a lot of application that's been written. Do we know if any of it works? Do we know if it any, if any of it actually accomplishes what needs to be done for this application? then it was like, okay, now the real work begins,

[00:48:43] **Adam:** Mm-hmm.

[00:48:44] is

[00:48:44] **Ben:** how do we get this application to be something that people want to use internally? And I'll say that this is an internal app, so there's degree of protection there already.

[00:48:54] **Adam:** Mm-hmm.

[00:48:56] **Ben:** and now that we're in these later phases, I go much slower. Like, I still go faster than I'm comfortable with,

[00:49:05] **Adam:** Mm-hmm.

[00:49:05] **Ben:** but I do go much slower, and the discussions that I'm having with Claude are in a much more focused part of the application. And for anything that is broader, I will often have it come up with a multi-phase plan, and then I attack one phase at a time and say, "Okay, we're working on phase two. do a deep dive discussion about what this phase means." And then the plan that it comes up with is still verbose, but it's much more manageable. And it's like the first half is kind of the philosophical, and like broad, broad strokes, and then the last half of the plan is always like, "Here are the tables that I'm gonna create," and like, "Here are the tests that I'm gonna write." And like, I'll be honest with you, like I still don't really read that part of it.but I do read the top part, which is the... where I can push back and say, "Hey, I don't understand why you're doing it this way," and it'll explain, you know, oftentimes why it's doing it that way correctly, or, "Oh, it's a good point." And, you know, language that it uses is like, "Oh, you're right. I overstated some assumption that I had before, and your question really stressed the part where I was just making it up."

[00:50:13] Or like, "I was incorrectly relying on my memories instead of checking something against the code, and now that I've looked at the code, you're actually more correct." kind of stuff.

[00:50:22] **Adam:** Mm-hmm.

[00:50:22] **Ben:** So I'm, I'm trying to be more mindful now that we've slowed down. Which again, you know, like it brings back to the whole craftsmanship concept,

[00:50:31] **Adam:** Yeah

[00:50:32] **Ben:** I don't want throughput. Throughput doesn't feel like it should ever be the North Star, 'cause

[00:50:37] **Adam:** No

[00:50:37] the North

[00:50:38] **Ben:** Star, then I feel like we just start making a lot of sacrifices.

[00:50:41] **Adam:** For sure. Yeah. I mean, it, it... Whatever you pick as that North Star, that, like, primary metric, other things will be sacrificed to increase that number. It's the, it's like min-maxing, right? Like, yeah. Well, it's like min-maxing in a video game, right? Like, in order to increase your charisma, you have to lose intelligence or dexterity or whatever, right?

[00:51:01] Like, so

[00:51:03] **Ben:** That is a really fun example to

[00:51:05] **Adam:** be charismatic

[00:51:06] Yeah. So, you know, it is, it is what it is. Like, you know, you have to be mindful. And this also goes straight back to the gamification thing, right? Like, you know, you, you chose to focus on this one thing, and other things suffered because of it.

[00:51:22] **Ben:** Mm-hmm.

## [00:51:23] Keeping Your Craftsmanship in the AI Age

[00:51:23] **Adam:** So,let's, let's kind of try to, to steer more toward if you are trying to improve your software craftsmanship in this age that we live in now where we're, not only do we have AI tools available to us, but in some cases people are being, like, mandated you have to hit a minimum quota of AI usage, right?

[00:51:43] Like, what do you... What can you do to not let the laziness factor take your craftsmanship away from you?

[00:51:54] I'll start since you're thinking. and I, what I'll say is,code review your agent-generated code before you ask somebody else to code review it, right? Like, just because you generated it doesn't mean you wrote it, right? So like when you write it, you don't have to think about it because you already thought about it to write it.

[00:52:12] When you have something generated for you from a prompt, it, there's a good chance, like I'd say there's at least a 50/50 chance that something about it could be improved that you could see and, and trigger, right? So apply your own taste where- at whatever level it is before you ask for input from others

[00:52:34] **Ben:** I mean, look here, if I can be unguarded here If I'm at work

[00:52:41] and we're doing mostly vibe coding, I honestly don't feel like I'm learning anything at work.

[00:52:50] **Adam:** Meaning

[00:52:52] **Ben:** from a software craftsmanship standpoint. I learn a

[00:52:56] **Adam:** little

[00:52:56] **Ben:** bit, like I've talked about, in, in past episodes, that the whole idea of row-level locking at the database level, that was something that Claude introduced me to in the context of work because it

[00:53:08] **Adam:** kept making such

[00:53:09] **Ben:** a big deal about the race conditions. and that was something that it, that, that sent me off to learn about that on my own because I didn't quite understand what Claude was talking about. So from that perspective, that was interesting. From a day-to-day perspective, I don't feel like vibe coding is contributing to my craftsmanship really in any way whatsoever.

[00:53:37] I think it continues to be helpful when it comes to dealing with people and trying to build software it works for those people. Meaning still having the meetings with the customers, which is just other people at the company. taking requirements. I'm trying to refine those requirements, distill down their pain points into things that can be helpful in the application. I, I still think I am practicing the skill of product development, and I think that that's always been helpful and will continue to always be helpful. That's the, the people part of this stuff. But from a craftsman standpoint, I think all of that happens now

[00:54:25] in my personal time

[00:54:27] **Adam:** Hmm. I mean, that, I mean, think that's... It's unfortunate that that's where that has happened, right? 'Cause, like, we would say traditionally you should not be required to spend your personal time, as part of what makes you good for, like a, a good hire, right? Like, you don't want,

[00:54:46] right

[00:54:47] thinking about it from the perspective of hiring, it's not fair to require somebody to have a GitHub with a bunch of open source projects because that's not necessarily something that their previous employment could allow them to do.

[00:55:01] And, and it's, it's an interesting conundrum that you're pointing out here. Well, honestly, Ben, I'm gonna push back. I think that you are doing some things to improve your craftsmanship that maybe you're just not thinking of in this way. So, and I'm, I'm gonna say that as preface to what I was kinda w-waiting to add to the list here, which is, step one is definitely to improve your craftsmanship, care, right?

[00:55:29] Care about the quality of the code. Care about... We used to say, you know, "Write code like the person who's going to have to maintain it in 10 or 15 years knows where you live and has the, the key to your house and is gonna come over and beat you up in your sleep if you, if they don't like your code," right?

[00:55:45] Like, write code with that in mind. And, if you took the same approach to the code that I output has to be that good or should be pretty darn close to that good, then you're gonna review it differently after it's generated, that sort of thing. But caring i-is the, the key here. And that caring can manifest in a bunch of different ways.

[00:56:07] Part of it could be the code review that we're talking about. Part of it could be reading what's in the news and, and what, you know, what new tools and techniques are people using, right? So there's, like, the TLDR newsletter. There's a bunch of different things you can follow. There's just following articles that are being shared on Bluesky, Mastodon, and Hellsite.

[00:56:28] and

[00:56:29] **Ben:** What was that last one?

[00:56:29] **Adam:** Hellsite

[00:56:32] yes, I was wondering if you were gonna pick up on that. That's what I call Twitter now. UmYou

[00:56:40] **Ben:** know, I, I've sort of been, like,

[00:56:42] **Adam:** not following a lot of social media

[00:56:43] **Ben:** stuff, so I didn't know if that was, like the hot new thing all of a

[00:56:46] **Adam:** Yeah. th- that's another thing too is, like, social media has become, like we were talking about at the top of the show, it's become this very unhealthy thing to participate in, and, and yet is still also sort of like the location for the zeitgeist of the programming community, right? and it's unfortunate, but I do feel like the programming community, or at least the communities I can see, is like 60/40, maybe even 70/30 split between...

[00:57:15] And the majority, the larger side when it's uneven, is on Twitter, and then the smaller side is, like, kind of maybe split between Bluesky and Mastodon. and I, at this point, I have completely severed ties from Twitter. I do have my account still. I haven't, like, deleted it or, or locked myself out, but I don't ever choose to go there other than, like, I have no way to reach a person I need to reach except through sending them a DM, right?

[00:57:37] That sort of thing, or following a link to a news story or something. But, so, caring is step one, and, and, and manifesting that as reading or participating in discussions or listening to podcasts or, you know, all these... I, I do think that you are doing a lot of things, Ben, that are improving you or, or, are making you better at your job, even if not making you better at understanding Python syntax and Tailwind

[00:58:07] **Ben:** trying. You know,

[00:58:08] **Adam:** I'm I'm trying to

[00:58:09] **Ben:** make the-- I need my brain keep working. and what I mean by that is, is the problem-solving was always the most exciting part of all of this, whether it was the problem-solving from the software craftsman side, you know, right abstractions, good seams, all that kind of stuff,

[00:58:29] **Adam:** Mm-hmm

[00:58:29] or

[00:58:30] **Ben:** the problem-solving from the product side. solving the right problem? How do we make our customers' lives easier? You know, what's the 20% effort that I can do to give them 80% of the value? All, that kind of problem-solving is the exciting part of it.so I am trying to do that as much as possible, and that, point, caring never goes out of style.

[00:58:53] Caring about the customer frictions, that is always front and center in my mind.so but Y- you know, to, to put myself in the shoes of someone else who's much more new to the industry, I was thinking just the other day about... It was, it was like, uh... So I went to school for computer science, and I remember my professor, I don't remember which one, telling me this story. I don't know if this is true or not, but this is what he was telling me. That there was some moon rover that the astronauts, the, you know, the, the NASA engineers were trying to come up with, or maybe it was like MIT engineers were trying to come up with. it was this robot on wheels, and it had cameras. And what they were doing was writing all the software that would do image analysis on what was coming back from the cameras and could figure out how to move in other, in, you know, in various directions effectively. so they spent, you know, months writing this software and months building this bot, and they're getting ready to try it in this public demo. they have this rocky terrain. They put the bot out, and they turn it on, and it doesn't do anything. they're sitting there, and they're waiting, and for like minutes go by, and it just doesn't do anything. And, what they realized when they did diagnostics later is, is that when they put the down in this new location, it had no cameras underneath, it had no idea where it was.

[01:00:27] And there was logic that basically said, if you can't... if you don't know where you are, you can't know where to go next.

[01:00:33] **Adam:** Hmm.

[01:00:34] **Ben:** And I feel like there's something very rich there that, like, the ability to move forward with a lot of these tools is based on the fact that I know where I'm coming from. But if you drop into this industry and, like, you don't know where you are, can you move forward with the tools that you're being given? And I, I, you know, I'm like, that, that's like saying something philosophical without having a lot of meat behind it, but

[01:01:02] **Adam:** Sounds pithy

[01:01:03] It's

[01:01:04] **Ben:** you know, g- it's like, again, this idea that craftsmanship is just will always be important because the reason I can be effective at anything right now is because of the craftsmanship that I've developed. And I have to imagine that in order for me to continue to be successful in the future, I will have to continue to evolve that craftsmanship. Otherwise, I will end up in a place that I don't know won't know how to move forward. I, I don't know if that's true. That's-- But that's

[01:01:34] how I feel

## [01:01:35] Building for Joy — and Responsibility

[01:01:35] **Adam:** I will say I was listening to an interview today, just, just this afternoon. I was on my lunch break, and, this guy was talking about if you enjoy writing software, you don't have to excuse that.

[01:01:48] Mm-hmm.

[01:01:48] **Ben:** like, if you have side projects and you wanna write them however you wanna write them because you enjoy it and because you want that software to exist in the world, that you don't have to explain that to anybody, you should build it however, however makes you the most happy. And like, as obvious as that is to say, it's nice to hear someone say it because it almost feels like antithetical to the current moment

[01:02:15] **Adam:** Hmm

[01:02:15] build

[01:02:15] **Ben:** something just for the joy

[01:02:17] of building it

[01:02:18] **Adam:** Well, yeah. I, I do agree as long as it's in that direction that you don't have to justify wanting to not use AI. I

[01:02:26] Yeah yeah

[01:02:27] do think that we have a responsibility, as an industry to build things that are secure and, and privacy maintaining. and so people like, you know, the, the example that always comes back to mind most easily for me is when Carol told us about her realtor like vibe coded a replacement for some software that he was previously paying a subscription for and it stopped working.

[01:02:52] And I have no problem with people building personal software, like through vibe coding, like, you know, build your kids a game that, that they're gonna enjoy, whatever. But like, if you're, especially if you're building something that's dealing with people's private information or s- something that needs to be kept secure and, and confidential, people's financial details, that sort of thing, you know, I think that then you have a responsibility to either have the skill or contract with somebody who has the skill to

[01:03:25] know that it's done properly

[01:03:29] **Ben:** Yeah. I think, I mean, it's all part of building a

[01:03:32] **Adam:** successful product

[01:03:33] Right. Well, I mean, and that's, I just, I wanted to add that asterisk on the it- y- it's okay to build it however you want. And it is okay to build it however you want, as long as you're not trying to make it a product that somebody is gonna pay you for or that could expose, you know, could ruin somebody's life

[01:03:52] **Ben:** Well, I mean, last year there was that huge debacle with... The site was called, like, Spill the Tea or something. It was, like, a site where women could go and, and post about terrible experiences they had with men as, like, a

[01:04:05] **Adam:** warning to other

[01:04:07] Sure

[01:04:07] **Ben:** it was. But, like, part of it was you had to upload a photo of

[01:04:11] **Adam:** your ID

[01:04:11] **Ben:** to prove who you were.

[01:04:13] **Adam:** Hmm.

[01:04:13] they

[01:04:14] **Ben:** were intending, I think, to do the right thing, but it was, I'm almost certain

[01:04:19] **Adam:** correctly

[01:04:19] **Ben:** it was a completely vibe coded application, then it was hacked,

[01:04:23] **Adam:** Right

[01:04:23] these

[01:04:24] **Ben:** women's IDs were leaked onto the internet, and all the things that they said about people were leaked onto the internet.

[01:04:28] You know, that's obviously terrible, and it's

[01:04:31] **Adam:** Yeah

[01:04:33] **Ben:** you know, if you handcraft a solution that you won't have issues, but you'll have an intimacy with the code that I think will be much more likely to prevent things like that from happening.

[01:04:46] **Adam:** Okay

[01:04:47] **Ben:** really you get the best of both worlds if you use both, right?

[01:04:50] Because having intimacy with the code gives you

[01:04:55] **Adam:** ownership a sense

[01:04:56] **Ben:** of ownership, a sense of holistic understanding. But then being able to lean on AI to say, "Hey," and also find as much, you know, issues, edge cases, bugs, whatever in this code, you know, that's like having the best of both worlds

[01:05:11] **Adam:** All right. And on that downer of a note, I think we should call it there

[01:05:17] **Ben:** Sounds good

## [01:05:18] Patreon

[01:05:18] **Adam:** All right, well then this episode of Working Code was brought to you by having intimacy with the code. Whatever you do behind closed doors is between you and Claude

[01:05:25] **Ben:** We're two consenting adults.

[01:05:29] **Adam:** Question mark. and listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[01:05:44] Special thanks to our top patrons, Monte and Giancarlo. You guys rock. We really appreciate

## [01:05:48] Thanks For Listening!

[01:05:55] **Ben:** ya. We're gonna go do the aftershow, and I have no idea what we're gonna talk about. It's gonna be even a surprise to me and to Ben. We're gonna do it live

[01:05:57] **Adam:** yeah. but, aftershow, as you, I'm sure, are well aware at this point, is more talking that that part is paid for.

[01:06:04] And if you would like to pay for it, you can do so by going to patreon.com/workingcodepod. Few dollars a month gets us, in your ear holes even longer. And as I said at the beginning of the show, we did once again fail to make a short show. So, sorry, not sorry, I guess. that's gonna do it for us this week.

[01:06:24] We'll catch you again next week, and until then,

[01:06:26] **Ben:** Whether you do it with Claude or with yourself, your heart matters
