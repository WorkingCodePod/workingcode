---
title: "127: How Tech Interviewing is Broken with Sean Corfield"
description: "On today's show, we talk to Sean Corfield about his take on the 'Tech Interview' process."
date: 2023-05-17
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/127-how-tech-interviewing-is-broken-with-sean-corfield/id1544142288?i=1000613363693"></iframe>

On today's show, we talk to [Sean Corfield][sean-corfield] about his take on the "Tech Interview" process. With over 40 years of experience at companies like Macromedia, Adobe, and World Singles, Sean has been on both sides of the interview table; and, has been personally responsible for hiring countless engineers. His perspective that most tech interviews are "broken" might be taken with some apprehension if it weren't for the fact that, in 30-years of hiring, Sean has _never once_ had to fire an engineer for lack of ability. So, he's clearly figured out how to hire the _right people_ using a _proven and repeatable process_.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[sean-corfield]: https://corfield.org/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/127-how-tech-interview-is-broken-with-sean-corfield.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Sean Corfield:** They seemed nice people. but gradually the interview process throughout the day devolved into this sort of harassment with trick questions. and then the final straw was they literally locked me in a room with a Windows PC and visual c plus plus, and a specification, and said, we'll be back in 45 minutes to see how much of it you've coded up.

[00:00:20] **Sean Corfield:** and I, a didn't use Windows B, didn't use visual c plus plus because of that. And c by that point I was like, I'm, I'm not ensure I, I want to be treated this way by you people.

## [00:00:51] Intro

[00:00:51] **Adam:** okay, here we go. It is show number 127 and on today's show we are going to be speaking with a guest as promised. Last week for like the first time ever, we knew what we were gonna be doing this week. So, today on the show joining us, we have a special guest, Sean Corfield. Say Hi, Sean.

[00:01:05] **Sean Corfield:** Hey folks.

[00:01:07] **Adam:** And we're gonna be talking about how tech interviewing is broken. I invited Sean to, to join us because, he's a member of our Discord and a patron of the show. And, he said something to the effect of, tech interviewing is broken in the discord. And I was like, Ooh, that's a nice inflammatory statement.

[00:01:21] **Adam:** Let's, let's build a show on that. so, Sean, Sean is originally from the uk, now lives in California. He's been a professional programmer for more than 40 years. he worked at Macia and I guess briefly at Adobe. started, web development, you know, a little more than halfway through his career circa 1997.

[00:01:40] **Adam:** So, like, you know, around the time the rest of us got started programming, at least the, the other four of us here on the podcast,

[00:01:46] **Carol:** Not I.

[00:01:48] **Adam:** JavaScript just this year, if you can believe it, like made it all through web development this long without really diving deep into JavaScript. So that'll be interesting.

[00:01:56] **Adam:** And you're well known in many different programming circles, including C F M L and closure. you know, man of many frameworks and, conference talks, and most importantly, a man of many strong opinions.

[00:02:07] **Sean Corfield:** Oh yes, I have opinions.

[00:02:09] **Adam:** So, Sean, welcome to the show.

[00:02:12] **Sean Corfield:** It's, it's great to be on the show. It's great to, to kind of hang out with you folks. It's been a long time since I got to hang out in anything close to real life with you folks, so,

[00:02:22] **Tim:** It's been a while.

[00:02:23] **Carol:** Excited to have you.

[00:02:24] **Adam:** yeah. So, I guess let's start as we usually do with our tramps and fails. And Tim, it's your turn to go first, ma'am.

## [00:02:31] Tim's Triumph

[00:02:31] **Tim:** Okay. Well, I'm starting out with a triumph. you know, I, I love doing my prototyping work and so I was working this week on a, on a, a new prototype for a company that we're trying to partner with to, you know, get some new customers and things. But man, and I, I got it working, but I gotta tell you their documentation, it was pretty awful.

[00:02:51] **Tim:** really, really, I mean, a lot of documentation, but you know, I think every company needs to, like every six months review their, their documentation or have someone newbie review it for them. Because it was really hard just figuring out how to get started. Like, okay, I see all these endpoints. I know I want to use these five particular endpoints, but I really don't know how to get started.

[00:03:13] **Tim:** Right. You know, doing the authentication and all that was not easily explained. So actually what I wound up doing, I hired a, A consultant company that that works with them and I'm, you know, I'm like, listen, build me some postman, endpoints to, to do this and kind of demo, you know, how it works. So they did that.

[00:03:32] **Tim:** We had like a one hour meeting. We went to the Postman Endpoints and then, past couple days I took those postman endpoints, converted it to server side architecture and got it working. So that was, that was pretty good. So that was worth a few thousand dollars of not having to spend a couple weeks trying to figure out their god awful, a p I docs, so,

[00:03:50] **Adam:** Yeah.

[00:03:51] **Carol:** feel like I would do so much better if every, documentation I read came with a link to like a postman collection and a set of variables that explain just what I'm trying to use for inputs that can be changed for what I'm testing with. Oh, it would just go so much smoother.

[00:04:07] **Tim:** Yeah, that, that'd be great if they had something like that. And that's basically what we wound up paying this consultant company. I'm like, you know, they built a, an environments file for Postman and then they built all the endpoints that I was interested in and they demoed how it worked. I was like, okay, this makes sense.

[00:04:21] **Tim:** And I just went and looked at the Java script code behind the scenes for it and converted it. So yeah, it was def

[00:04:26] **Carol:** learned that way so well. Yeah.

[00:04:28] **Tim:** definitely worth a few thousand bucks to have someone get that initial hard stuff out of the way. So, but I was super happy I got it working and, yeah, looking to, looking to build a product out of this and make some money there.

[00:04:40] **Carol:** Keep us posted on the product.

[00:04:42] **Tim:** Hmm.

[00:04:43] **Carol:** Keep us posted on the product you're building.

[00:04:45] **Tim:** will do. So that's me. How about you, Adam?

## [00:04:48] Adam's Triumph

[00:04:48] **Adam:** I'm gonna say that I'm going with the triumph as well. my compliance work that I've been talking about for far too long, is coming along nicely actually. So the, the big thing that I've been working on for far too many weeks at this point is, access key rotation for our AWS accounts and all the little applications and things that use those things and trying to move those applications to, to, you know, do things the right way where possible, or at least, you know, use updated keys if they still have to use the old, you know, embedded key or, or environment variables or, you know, pulling it outta config, whatever.

[00:05:20] **Adam:** So that's all, all coming along nicely. I had a lot of customers I had to talk to to get them to, to use rotated keys and to prepare them for, updating their keys quarterly and like, you know, building tools to help them automate looking up their new key. That sort of thing. So like, you know, it's one thing to be able to say, okay, go to this, protected page in the application to get your new key.

[00:05:41] **Adam:** But that's very manual, right? So we had to build an API resource that was, comfortably secure for them to be able to like say, okay, here's the old key and I want the new keys. I have to really prove that they should have access to the key, not just have like any old API key. so that's coming along nicely.

[00:06:00] **Adam:** Most of the pieces of that are, you know, 90 plus percent there. the big thing, sort of looming in the, in the distance for me would be, everything else for pci, right? So, we started this process and I, the first thing that I started tackling was like this list of problems and I'm nearing the end of that list.

[00:06:19] **Adam:** And then after that, it's all of the process of getting all the documentation together for completing the PCI process. So, it's, it's. A little, intimidating, but I'm sure I'll get through it. And yeah, so that's me.

[00:06:35] **Ben:** But how will you celebrate?

[00:06:38] **Adam:** I will probably celebrate by taking a day off and on something completely unrelated. Honestly, I'll probably like spend the entire day writing's spell. All right, so, how about you, Ben? What do you get going on?

## [00:06:51] Ben's Failure

[00:06:51] **Ben:** I'm gonna go with a soft failure, which is that, as I've talked about on the show previously, I've been digging into the hot wire framework from the base cam people. And I, I've been enjoying migrating my ColdFusion blog to use Hotwire on the front end and some of the integration with the backend stuff.

[00:07:08] **Ben:** And as I've been digging into it, I've had this plan in the back of my head that once I feel comfortable with how Hotwire works, I want to actually build an app with it. Like not just a, a public website, but an but an app. You know, that you would log into and interact with. And, I'm, I'm just not sure that I wanna do that anymore, meaning I'm not sure that I wanna do it with Hotwire.

[00:07:30] **Ben:** I've, I've spent like the last three months or four months digging into this and every time I feel like I take a step forward, I then hit a hurdle and I feel like I have to take a step backward. And it's getting to the point where I'm just not sure I'm gonna be able to answer those questions in a way that makes me confident that I'm gonna be able to wire a, like a, a robust app together.

[00:07:54] **Ben:** Cuz as I'm looking into this, I'm also thinking in my head, I know how to do this in Angular and I, I'm having trouble finding the parallel answers. Even, even something as simple as all of the requests are made via the Fetch API in the browser, so you don't make a full page load and, at a, at the top level page, if that fails, like it just silently fails.

[00:08:15] **Ben:** Like your navigation just doesn't do anything. And you can hook into some error handling events, but it's very unclear about how you might try something like,an exponential retry or something. Something where in Angular, because it's everything is so programmatic, you have all the hooks. And because hot wire is like more magic, so to speak, it's, it's a lot less straightforward how you might answer some of these.

[00:08:41] **Ben:** So my, my soft fail is that, I think maybe I invested more time than I'm actually gonna get value out of, but I'm gonna flip that and call it a triumph because I'm not gonna give into the sun cost fallacy.

[00:08:54] **Adam:** Okay,

[00:08:55] **Ben:** so that's

[00:08:56] **Adam:** do you, are, are, does that mean that you are happy, having learned something, you just don't feel like it's maybe the most versatile tool on your belt? Is that what I'm hearing?

[00:09:04] **Ben:** Yes, I am happy and I'm gonna keep it on my, on my blog. I do think that it, it makes sense for a more. Content oriented site. Like, because, because of the way it, it, it progressively enhances the site and makes it a little snappier and a little less data loading and there's some interesting, lazy loading aspects to it.

[00:09:23] **Ben:** I think there is value there. It's just, I just don't think that I know how to take it and make it into something that is, I hate, I hate to draw a line between content site and app, but I don't think I can use it to build an app yet with my know-how.

[00:09:41] **Adam:** Hmm.

[00:09:41] **Ben:** anyway, that's me. Carol, what do you got going on?

## [00:09:44] Carol's Triumph

[00:09:44] **Carol:** I'm gonna call this week a big giant win. I did not hurt myself. I did not break anything in my house and nobody's car is, well I didn't break my car, my son's air went out on his car, but that's his own problem. I'm not dealing with it. He can go deal with that. So I feel like it's giant win that did things and nothing went bad.

[00:10:04] **Carol:** And that's just great cause I've had some failures. And then, a second thing is I keep getting put into these like weird situations with trying to pick up work where companies. Go into, I'm glad we're talking about interviewing tonight cuz this, you know, maybe something we could talk about a little bit, Sean, but, I keep getting put into these weird situations where companies are like, oh, I really wanna talk to you.

[00:10:27] **Carol:** I wanna talk to you. And then we go through this process and they're like, this is going to be the easiest interview ever. Here's what we want from you, we want to hire you. And I'm like, I don't wanna be hired. I want you to do a like corp de corp. Like, I want to partner with you, I want to run my own thing.

[00:10:44] **Carol:** And they're like, oh yeah, well we can't do that. Sorry. There's no way. It's not possible. But if you wanna be a W2 and be hired all day long. So those were some setbacks this week cause I'm just getting frustrated with the, you'll hire me without even looking at anything I do, but you will not hire me as a contractor.

[00:11:03] **Carol:** So, frustration there, but nothing's broke. So that's good news. So I'm gonna win with all this. Yip. Yep.

[00:11:11] **Ben:** Quick question. Is that a Datadog T-shirt?

[00:11:14] **Carol:** But this's, a taser dog, T-shirt,

[00:11:15] **Ben:** Yo, Datadog's such an awesome company. Well, their product

[00:11:19] **Carol:** So soft. Good notice. Good notice. But yes, that's me. What about you, Sean? You got something for us? You gotta win.

## [00:11:29] Sean's Triumph

[00:11:29] **Sean Corfield:** Yeah, I'm definitely gonna call this a triumph. I've just come back from my first in-person conference in three and a half years.

[00:11:37] **Ben:** It's awesome.

[00:11:38] **Sean Corfield:** so I have been, I spent several days around 400 geeks talking tech, and some mind blowing talks. I'm, to give you some idea, the, the opening talk of the conference was called, vector Symbolic Architectures, and it was about sort of AI and some of the stuff you can, actually do.

[00:11:58] **Sean Corfield:** Kind of yourself with the right libraries.

[00:12:01] **Tim:** Oh, Sean, talk dirty to me

[00:12:02] **Sean Corfield:** yeah, and

[00:12:04] **Ben:** what? What conference was this?

[00:12:05] **Sean Corfield:** this was Closure Conj,

[00:12:07] **Ben:** Mm.

[00:12:07] **Sean Corfield:** and it's the 11th Closure Conj, and it's the 10th one I've attended. and this opening talk was about hyperdimensional vectors. And Hyperdimensional vectors are vectors that have at least 10,000 dimensions and often up to a million dimensions.

[00:12:26] **Sean Corfield:** And they, the way it works is you essentially pick a point in NDI dimensional space that's represented by the vector, and that represents some thing that you're modeling in your ai. And then you can combine things and shift them around and do all sorts of stuff with it, and still retain all of the data in a single vector, which is what absolutely blew me away.

[00:12:53] **Sean Corfield:** and so the speaker was showing examples of how to represent multiple things, combine them together, and still be able to pull apart and answer questions about any part of the, the data. So, and that kind of kicked off the whole tone of the conference. I mean, there was a, a lot of amazing stuff. and so I've, I've just really enjoyed that.

[00:13:14] **Sean Corfield:** And of course it was in Durham, North Carolina, which has fantastic food.

[00:13:19] **Tim:** Yeah, they do.

[00:13:19] **Sean Corfield:** And I got to hang out with a couple of, old CF friends, Dan Skaggs and Dan Wilson, cuz they lived just down the road. So we spent an evening in, Paul, which is a self-service tap room. Highly recommended if you're in Durham.

[00:13:32] **Carol:** And the weather's great down here this year, this time of year.

[00:13:35] **Sean Corfield:** It rained most of the days we were in Durham, but, you

[00:13:39] **Carol:** I lied.

[00:13:40] **Sean Corfield:** yeah, you know what, it's funny cuz one of the locals said, oh yeah, you know, when it rains it doesn't persist. It's just, you know, brief rain showers and then it just rains solidly for most of the conference.

[00:13:50] **Carol:** no.

[00:13:50] **Sean Corfield:** Um,and they were like, ah, made a liar of me.

[00:13:53] **Sean Corfield:** But no, the, the weather did not detract from my enjoyment of Durham. it's, it's a lovely city and has phenomenal food. So

[00:14:02] **Tim:** It does.

[00:14:03] **Adam:** How does a self-service tap room work? Like,

[00:14:06] **Sean Corfield:** you go in, you give them your credit card and do you give them the credit card that we didn't get? I guess you do. and they give you a little wristband with an R F I D tag in it. And then all of the taps are up on the wall and you touch the R F I D tab, tag two, whichever one you want to drink. And it measures how much you pour.

[00:14:26] **Sean Corfield:** And it's all recorded on the, the little wristband. And at the end of the evening, you give them back your wristband and they charge however much to your credit card.

[00:14:35] **Tim:** Hmm.

[00:14:36] **Carol:** like froyo. It's like froyo, but for beer.

[00:14:40] **Sean Corfield:** yeah. And it's, it's awesome because, you know, you can go, well, I don't know if I'm gonna like this. We'll have an ounce of it

[00:14:46] **Carol:** Yeah. The sample.

[00:14:47] **Sean Corfield:** have a full glass. Yeah. So you can, you can have as much beer or as little beer as you like, you can, they've got them all organized right across the wall with like laggers and pilsners and then sours.

[00:15:00] **Sean Corfield:** So I had a couple of goers, and then it goes into light hails and then darker rails. And then they have IPAs. They have ridiculous selection of IPAs and then stouts and porters and, and stuff like that. And then they actually have wine and cocktails you can pour as well.

[00:15:17] **Carol:** That's cool.

[00:15:19] **Sean Corfield:** So,

[00:15:19] **Adam:** Sounds very dangerous.

[00:15:20] **Sean Corfield:** Yeah,

[00:15:21] **Carol:** Very dangerous.

[00:15:22] **Sean Corfield:** it's only opened, up in the last couple years at the unscripted hotel.

[00:15:26] **Carol:** That's really cool. I have to look it up.

[00:15:28] **Adam:** So, Sean, did you, prepare a triumph for a fail for us?

[00:15:30] **Tim:** He just did it.

[00:15:31] **Adam:** Oh I'm sorry.

[00:15:33] **Tim:** Pay attention, dude.

[00:15:35] **Adam:** I, and I was listening and everything. I'm, I just totally messed that up.

[00:15:39] **Sean Corfield:** I, I, I, I think it's a triumph, the

[00:15:41] **Ben:** you were putting him

[00:15:42] **Ben:** on

[00:15:42] **Sean Corfield:** know, if, if you're gonna put me on the spot for another triumph. Um, I have actually, I've been seconded to the front end team, lately at work, which as we were sort of joking pre-recording about the fact that I've managed to survive through a lot of web without actually doing JavaScript.

[00:15:57] **Sean Corfield:** And so now I am doing quite a bit of JavaScript and I've

[00:16:01] **Carol:** A lot of it.

[00:16:03] **Sean Corfield:** yeah, I've spent the whole day today, working with Jess and

[00:16:07] **Carol:** Ooh.

[00:16:08] **Sean Corfield:** and,

[00:16:08] **Sean Corfield:** doing a lot of t d d

[00:16:10] **Ben:** Hmm. So all of the not fun stuff

[00:16:12] **Sean Corfield:** No, the, the stuff that I absolutely love.

[00:16:16] **Ben:** I'm, I'm surprised that you haven't done JavaScript because I have a distinct memory of a conversation that we had online like 12 years ago, and I was, this was like back when ColdFusion was just about to introduce closures, and I was going on about like, oh, they're so awesome.

[00:16:34] **Ben:** Like, you don't have to name functions. And you were like, closures is not just about not naming functions. There's a whole lot more that goes into it. And I just assumed that was you talking about JavaScript, but I guess not. I guess other languages had closures.

[00:16:47] **Sean Corfield:** yeah, and I mean, I, my background is in functional programming. I mean, when I was at university, I did lisp and I did a p l and I did three years PhD research on the design of functional programming languages.

[00:17:01] **Ben:** Hmm.

[00:17:01] **Sean Corfield:** so, you know, closures and higher order functions and all sorts of stuff like that is, is. Was not new to me.

[00:17:08] **Sean Corfield:** And it's kind of nice that it's gone mainstream and all the languages have it. And I am really enjoying working with, we use Lodash very heavily at work and immutable js and so, you know, I can really let my functional flag fly free and, and I'm really kind of enjoying that. So,

[00:17:26] **Ben:** Very nice.

[00:17:27] **Sean Corfield:** but I have opinions about JavaScript, although I will say that it is not, it is not the JavaScript that I first encountered and hated. There's a lot of stuff in modern JavaScript that's sort of almost acceptable.

[00:17:44] **Tim:** Maybe save that for the after show.

## [00:17:45] How is Tech Interviewing Broken?

[00:17:45] **Adam:** Cool. Well, so Sean, you had said tech interviewing is broken. How is tech interviewing broken?

[00:17:52] **Sean Corfield:** Well, I think a lot of us have heard of sort of like the big tech interview process where they, they're very long interviews. You're interviewed by a lot of people. You get grilled on a lot of stuff. There's often these kind of gotcha questions, and usually, you know, technical tests where it's like, okay, right, we're all gonna focus on you while you write code.

[00:18:12] **Sean Corfield:** and

[00:18:13] **Adam:** Cause that's not terrifying.

[00:18:15] **Sean Corfield:** this is not how any of us work. I mean, the whole interview process that a lot of these big tech companies go through is just not at all reflective of how any of us are going to work, should we get through this brutal hazing process. Um, I mean, and it's been like this for a long time.

[00:18:31] **Sean Corfield:** It's not just big tech. in the nineties while I was still living in London. a company flew me out to Dallas for an interview.

[00:18:41] **Ben:** Dang.

[00:18:41] **Sean Corfield:** and you know, the, I was very excited. They were a company whose products I just loved. They did these amazing object-oriented libraries. and I got there and, you know, initially it seemed pretty nice.

[00:18:53] **Sean Corfield:** They seemed nice people. but gradually the interview process throughout the day devolved into this sort of harassment with trick questions. and then the final straw was they literally locked me in a room with a Windows PC and visual c plus plus, and a specification, and said, we'll be back in 45 minutes to see how much of it you've coded up.

[00:19:16] **Sean Corfield:** and I, a didn't use Windows B, didn't use visual c plus plus because of that. And c by that point I was like, I'm, I'm not ensure I, I want to be treated this way by you people.

[00:19:28] **Adam:** Yeah.

[00:19:29] **Sean Corfield:** I actually got up and left and the receptionist said, oh, you know what, shall I tell the manager? I said, tell him that the interview sucks and I'm flying home. And so I went to the airport early, flew home a couple of days later, they called me up and said, really sorry, the, you didn't like the interview process, we'd like to hire you anyway.

[00:19:50] **Carol:** Oh my

[00:19:50] **Carol:** goodness.

[00:19:51] **Sean Corfield:** no. Cuz if you treat people like that in an interview, how are you treating people once they're hired?

[00:19:56] **Carol:** Pass. Yeah, that's a hard pass.

[00:19:59] **Sean Corfield:** And I, I think what's frustrated me a lot is that, particularly with the sort of the rise of the elite code stuff and, you know, we've even got a book, you know, passing the, the big tech interview type stuff.

[00:20:13] **Sean Corfield:** a lot of other companies have taken it up because that must work because why would these big tech companies do this if it didn't work?

[00:20:20] **Sean Corfield:** but it does not work. And they occasionally have released studies that have admitted as much where they've said, yeah, you know, we've looked at the quality of candidates and clearly our, you know, abusive indi interview process. they don't call it, extensive interview process doesn't really help and correlate to good candidates.

[00:20:43] **Sean Corfield:** and so, you know, I've been a hiring manager for about 30 years at different places, and I don't do technical tests because I don't think that they, they work, I don't think they tell you what candidate's like,

[00:20:57] **Carol:** Like period. You do no technical assessment of someone before you hire them.

[00:21:01] **Sean Corfield:** I do no, no technical test. I do not make them code. I do not set them technical problems to solve. I don't make them do whiteboarding stuff. I talk

[00:21:12] **Adam:** Sounds like you don't do riddles. Yeah.

[00:21:14] **Sean Corfield:** No, and I don't do riddles. I mean, what I actually try and do, and I've got a mind map that guides my interview process that actually hasn't changed in years because it's, it's pretty abstract and not related to the text specifically.

[00:21:26] **Sean Corfield:** I get them to talk about past projects and, you know, by just giving them a few prompts and kind of letting them, them run off on past projects. and in particular, any issues that cropped up problems with tech, problems with the people. And you just sort of guide them into this and let them talk. You will learn what they're going to be like as a team member, and you will learn from that whether or not they're actually able to solve problems.

[00:21:53] **Sean Corfield:** because someone who isn't able to solve problems, once you get them talking, they'll soon tell you that they

[00:21:58] **Carol:** Oh yeah.

[00:21:59] **Sean Corfield:** problems with this. And you'll see, you know, what level of person they are, whether they're junior, whether they're senior, whether they think they're senior, and just have junior experience repeated over and over again.

[00:22:10] **Sean Corfield:** and that's what I'd love to see other companies do. and it really frustrates me that, you know, online I see a lot of people going, oh, I've got an interview coming up. You know, how should I prepare for this interview? Should I be doing these, you know, elite code problems? Should I be doing this?

[00:22:24] **Sean Corfield:** Should I be doing that? And, you know, some people say, oh yes, well, at my company, here's what we do. And it's that same sort of nasty process.

[00:22:33] **Carol:** Yep.

[00:22:33] **Sean Corfield:** And even when I push back on it, people are like, well, we've got to do some sort of technical test. I mean, you've gotta give people some sort of coding test. How else do you know whether they can code? and it's, it's like, you know, you can teach people a programming language. You can mentor them to work with your coding style and your structure. And every company's gonna be different in terms of architecture and code organization and the majority of what you need to know to work effectively at that company. You've gotta be able to solve problems and you've gotta be able to communicate about the scale of those problems. so it's sort of been my, my decades long campaign to sort of, you know, rattle, you know, shake my cane and get off my lawn and, and start doing interviews properly. now, I mean, I'm sure, I don't know when the last time any of y'all did interviews, but, you know, tell us about some of the pros and cons of some of the stuff you've been going through.

[00:23:31] **Sean Corfield:** Carol, it sounds like you've really been going through it.

[00:23:34] **Carol:** Yeah, I've

[00:23:35] **Tim:** over 20 years for me, so yeah, go ahead, Carol.

[00:23:37] **Carol:** oh yeah, I flip all the time. You guys know this. I don't hold anything too long. You know, these millennials and their problems. So let's go back to being on the side of the hiring manager. So I know you said you don't do any type of technical exercise with your candidates, but for me, I enjoy sending out a very simple question.

[00:23:59] **Carol:** And one example is, I give you a file, you tell me you know, how many times, like if you need to loop through it and tell me how many lines are in that file. Just, you know, write something very simple, something small. And I just wanna see that there's initiative to try. I wanna see that they know how to put something on paper and that they know how to ask questions.

[00:24:19] **Carol:** So if they go back to the hiring manager, to our recruiter and go, Hey, I really don't know how to write this in, you know, ColdFusion, but I do know how to write something in, in like a JavaScript type language. Is, is that okay? Like, just show me that you have the ability to ask questions that you're willing to take a stab at it and that you can admit when you're wrong.

[00:24:41] **Carol:** Or, you know, we've saw people submit senior level code that come in super cocky and it doesn't work at all and it won't even run. Like there's just errors all over the place. Like how do you spell variables wrong, like when you had it in the, A line above it. So, you know, I do enjoy seeing those because I feel like it does often weed out candidates and it also gives me a chance to see the very.

[00:25:06] **Carol:** eager people who want to know more and are willing to, to like ask the questions upfront. And I don't know if you missed some of that by not asking any technical question or if you know, you just don't even have to worry about it cuz you've got some process that works great for you. But I love that part of the interview.

[00:25:23] **Carol:** It, it's a good talking point with candidates.

[00:25:27] **Sean Corfield:** Yeah, I, what I tend to find is that that sort of falls organically out of some of the discussions because you can see if they get excited about something and so you can ask them for details and you can tell if they're or if, you know, they really enjoyed it and really dug into it. and I mean, you know, We had a round of interviews.

[00:25:46] **Sean Corfield:** We were hiring for a JavaScript developer, which is very different to hiring for a closure developer. we got 150 applications, I think for the, the open JavaScript role. and a lot of the resumes were just clearly just stamped out of some resume site.

[00:26:05] **Sean Corfield:** Um, but even amongst the people we interviewed whose resumes looked good, there were a couple of people that, you know, within five minutes I was ready to shut down the interview because it was just painful.

[00:26:17] **Sean Corfield:** so I mean, one thing I will say is as engineers, we are not taught how to interview people.

[00:26:25] **Ben:** Yep.

[00:26:26] **Sean Corfield:** the industry as a whole doesn't seem to value that as a skill. and yet hiring people who are going to fit with the team, be able to do their job and stay with the company. Is really very important.

## [00:26:41] Amount of Interviews

[00:26:41] **Ben:** Let me ask you a question. One thing that always struck me as strange when I hear other people talk about it, cuz this has not actually happened to me, but I'll hear someone say something like, oh, the interview process is going real well. I have my fifth interview at this company scheduled for Friday and I'm like, five interviews and they don't know if they wanna hire you yet.

[00:27:00] **Ben:** Like, that seems really weird. I feel like one interview should basically get it done, but like where, where do you stand on that?

[00:27:08] **Sean Corfield:** Well, I, I work for a very small company, so you know, you're going to interact with a relatively small number of people once you're hired. So, we do an HR interview first. and that's mostly to try and ensure that, you know, you are, you're going to be okay working with a pretty diverse crew. I mean, we do ethnic dating sites, so we have a pretty diverse set of ethnicities in the company.

[00:27:34] **Sean Corfield:** So the HR folks talk to them, try and get a sense of, you know, what they're looking for in the job, what they're like to interact with, and, you know, basic communication stuff. And then if they pass that, I will do a technical, well, a technical interview with them. I will talk to them about past projects and get them chatting about what excites them about software and what doesn't excite them.

[00:27:58] **Sean Corfield:** and that will run at most one hour, but often only has to run about 30 minutes before I've got a really good sense of how good they're, if they pass that, they then do a final interview with business team. because all the engineers here have to interact with the business team. And that again, is mostly can we get on well together?

[00:28:18] **Sean Corfield:** Can you communicate with the business people? Can you explain ideas? You know, they'll, they'll sort of say, well, you know, we've been thinking about doing this sort of thing in the dating app. You know, do you have any thoughts on that? And it's, it's really like, you know, what are you going to contribute to the process?

[00:28:35] **Sean Corfield:** Cuz the engineers are expected to contribute ideas to the business as well. And if they pass that and the salary expectations all line up, they'll get an offer. And if they accept it, they're hired. So, you know, at most three hours, often one and a half hours over spread over three interviews. But when you are dealing with a much larger company, particularly where you've got much more touchpoints, I can understand why you will either have an entire day of interviews or you will have to come back multiple times. you know, when I joined Macromedia, as I recall, that was an entire afternoon of interviews with the technical team. And it was like one after another, or you know, two at a time, occasionally. and there was also an interview with the department head. And I think someone else, so there were three separate days of interviews that had up to about four hours of interviews in, and that didn't seem too bad for me.

[00:29:34] **Sean Corfield:** It was a bit intense on that one day. But you know, if you are working at a company that's got thousand people and you are expected to be working in a department of a hundred people across multiple teams, those teams ought to get a chance to talk to the new hire and see whether you know you're gonna be okay to interact with, unless it's a low level position and you know you're not going to be doing that sort of interaction.

[00:29:59] **Adam:** Right. had a really interesting experience on the hiring side, but I wasn't in charge of it. one of the pla past places that I worked was a pretty big organization and the hiring manager had like, I think it was like six or eight applicants all come in at the same time for like an entire afternoon.

[00:30:19] **Adam:** And then there were like maybe five or six different teams of two to three people that all worked at the, the organization. and, and we basically did like speed dating, right? So like each team of people that already worked there would like camp out in one of the conference rooms, and then the candidates would just sort of like a half hour, 45 minutes at a time, like rotate through each team.

[00:30:39] **Adam:** And each team was assigned like, okay, you are interviewing for culture fit, or you are interviewing for technical chops, or, or whatever. They all were. I, I, I'm, I'm kind of of two minds about it. I felt like it was a pretty outside of the box, innovative way to think about the process and try to streamline it, get it done quickly.

[00:30:57] **Adam:** But I, I like, it's just so different that I'm not sure if it's a good thing or a bad thing.

[00:31:03] **Sean Corfield:** I think that's gonna depend on the culture of the company and how they work. I mean, if you've got teams that are all, once you know they're set up and running are all pretty isolated and they don't generally interact with each other, then it's kind of weird to do that to new hires. but if you've got teams that are very collaborative and essentially very social in their level of interaction, then, then it's pretty reasonable to expect the candidates to be pretty interactive and social and collaborative as well.

[00:31:32] **Ben:** I, I'd like to say that if Sean's company goes and now spins off a dating site for engineers, you heard it here first, and Adam should get a cut of that.

[00:31:41] **Adam:** Yeah. I'll take it.

[00:31:43] **Sean Corfield:** Yeah. That, that's, that's something we get asked a lot. It's like, oh, well, you know, why don't you do dating for x, y, z group of people?

## [00:31:52] Shutting Interviews Down

[00:31:52] **Adam:** So you had mentioned earlier that like, sometimes you can feel like you wanna shut down. You can tell within the first minute, five minutes that you want to shut down the interview. I've been in that situation, and I just gutted it out because I felt too awkward to try and shut it down. Like,

[00:32:07] **Carol:** Same. That's exact

[00:32:08] **Adam:** you,

[00:32:08] **Sean Corfield:** Yeah.

[00:32:09] **Adam:** should you shut it down?

[00:32:11] **Sean Corfield:** It's awkward. I mean, you know, for a candidate to essentially have the interview curtailed after five minutes, that's, that's gonna be a little brutal. so, you know, I, I do tend to let it sort of go on a little bit longer.

[00:32:26] **Sean Corfield:** Um,

[00:32:26] **Carol:** Yeah. We all have, I guess,

[00:32:28] **Sean Corfield:** it, it generally won't go on much more than about 15 to 20 minutes.

[00:32:33] **Tim:**

[00:32:33] **Sean Corfield:** But yeah, I hate those interviews where you get someone who on paper looks good and then you get them talking and it's just like, oh, this is not gonna work.

[00:32:41] **Carol:** Yeah,

[00:32:42] **Sean Corfield:** and there's, there's all sorts of reasons why these things don't work. Sometimes it's, it's a complete lack of engagement with the, the candidate in the interview.

[00:32:52] **Sean Corfield:** and you feel like you're just pulling teeth to get anything out of them.

[00:32:55] **Tim:** Yeah.

[00:32:56] **Sean Corfield:** so you know.

[00:32:57] **Carol:** but I've also met super brilliant people who were able to code circles around me, but having a conversation face-to-face wasn't something they were really capable of doing. And I feel like if you can't make a conversation happen, you know, in 30 minutes, how long do you go? Like where is that point where you go?

[00:33:15] **Carol:** Okay. Am I talking to a brilliant person who I need to give another 30 minutes to and keep pulling at it, or do I just stop? Because you don't wanna lose that great person cuz they don't like humans, like they're still good at being an engineer.

[00:33:29] **Sean Corfield:** But, you know, and, and that's, that's a good point. but what's the team environment like? I mean, if you've got a team of people who are all like that, no one's gonna talk to each other and everyone wants to work individually and, you know, I much as I'm not a giant fan of people, that's not a team I would want to work on.

[00:33:49] **Sean Corfield:** I mean, for us, we, we have a very small team, but we have to work very collaboratively.

[00:33:55] **Sean Corfield:** So we're expected to chat and interact with each other a lot. We pair program from time to time. you know, it, it's, you've got to be able to communicate. And so for us, that's the key thing. I think there are companies that have, you know, cubicles full of, of nine to five programmers who they mostly don't care, you know, whether they interact at all as long as they do what they're told and produce code at the end of the day.

[00:34:21] **Carol:** Is, is CodeMonkey a bad term? Is that like sad, like bad to say? Because that's like what I've always like heard it called like someone who literally just sits at a computer, just codes and then just walks away, like doesn't take stress home with them, doesn't care about a project, doesn't wanna solve any big problem, just wants you to say, I need A, B, and C.

[00:34:42] **Carol:** Done. They write A, B, and C and then they walk away at five. Like at five they're done at eight, they come in. That's it. Like all they want to do is just write code. And some teams need those people that. Don't do anything else. Literally just put out code.

[00:34:57] **Sean Corfield:** Yeah. Yeah. I mean I've, I've certainly seen it in larger companies where there's an expectation that, you know, people will churn out solutions to problems day after day and, you know, they're never bothered outside hours and they don't expect people to get excited about what they do or anything, but that's

[00:35:15] **Carol:** It's not me. It's not how I work. Let's be clear. I get excited. I love what I do. Yeah, it would be terrible.

[00:35:23] **Tim:** I, I think the whole tech interview thing where we, the horror stories that we hear about the, the impossible puzzles and the, the, you know, the, the code test. But I, I think that writing code is really, I mean, it's an important part of everyone's job, but it's a, it's not the entire job,

[00:35:40] **Sean Corfield:** Right.

[00:35:41] **Carol:** agree.

[00:35:42] **Tim:** right?

[00:35:42] **Tim:** It's not the entire job. And so one thing I've always looked for in hiring. Is you have to have a mix of, of people on a team, right? So someone might be really qualified, but if I just have a team of people that all they wanna do, they, they wanna be told exactly what to do. And when they run into any sort of interference, like dealing with another department, they immediately throw up their hands and they wait for someone to fix it.

[00:36:05] **Tim:** You know, move this roadblock outta my way and so I can get back on the keyboard. And you can't, I mean, it's fine to have a few people like that, but if that's all your team, that's, yeah. You gotta have some people that can make build bridges, you know, who, who reach out. So I think, Sean, what you're talking about, having the conversation about, you know, tell me about a time you're on a project and you ran into maybe having to deal with another department and you weren't getting what you, you know, how did you solve that?

[00:36:32] **Tim:** And if they're like, well, I just told so and so and they fixed it for me, you're like, okay,

[00:36:35] **Tim:** well, Yeah, here we go. Or if they're like, you know what I, I, I, I called them personally and you know, I didn't, you know, it wasn't an email. I just actually picked up the phone, talked to them and, or maybe walked over to their office and explained, and then we got it done.

[00:36:48] **Tim:** Now you're like, okay, now we got a, now we got a bridge builder here. May, you know, we maybe need a couple of those more on our team. So it's kind of plugging and playing the different, you know, you can't have just all running backs on a football team. You gotta have, you gotta have different roles.

[00:37:01] **Sean Corfield:** Yeah. And you definitely, that's something you need to find out in an interview. Is, is, I mean, what I do is, the opening question I ask essentially is, of all the projects you've worked on, what was your favorite and why? So it's very open-ended. and then depending on what they start to talk about, I'll say, oh, that's interesting.

[00:37:17] **Sean Corfield:** Tell me a bit more about that. Or, you know, or how, how did that interaction go? And then when we've gone through that, I will say, okay, now the flip side of that is, you know, which was the worst project you worked on? You know, maybe it was tech issues, maybe it was people issues. Tell me about that. And just from those two questions alone, you would be amazed what people are willing to spill and

[00:37:40] **Carol:** All the beans, all the beans come out.

[00:37:43] **Sean Corfield:** yeah, just how much insight you will get into how they are going to be as a team player.

[00:37:48] **Sean Corfield:** How much innovation they show, how they interact with structure in an organization. and of course, you can find out a lot about their problem solving ability by finding the things that they either hated doing or loved doing, and drilling into them a little bit and saying, well, you know, tell me a bit more about that.

[00:38:04] **Sean Corfield:** How did you actually solve that problem?

[00:38:07] **Sean Corfield:** And so they can just talk about it.

[00:38:09] **Tim:** Yeah, because if they have any, any resume of, of coding and they've been, you know, they're not hopping around every three months and they've stuck around at least, you know, a couple places you're like, they can most likely code. So we don't need to check for that. Let's, let's figure out, like you said, how they solve problems both.

[00:38:25] **Tim:** Technical problems, but also, you know, organizational and interpersonal problems. And you figure that out. You figure out who they are and you're like, okay, do they fit?

## [00:38:34] Solving Problems, Google, ChatGPT

[00:38:34] **Carol:** I don't, I don't know if you remember this, Tim, but my very first tech interview was with Tim. Tim interviewed me for an internship at, at the time, I D M I, and that's where my career started at. So he asked me in that interview, you know, he's like, do you have this problem? You know, how are you gonna fix it?

[00:38:49] **Carol:** I'm like, I don't know. I don't even know what this problem is, right? He was like, okay, so what are you gonna do? I'm like, I'm gonna give it my best effort. He goes, what if that doesn't work? I was like, someone here has to know how to solve it, so I'm gonna ask for help. He goes, well, what if no one here knows how to solve it?

[00:39:04] **Carol:** I was like, well, there's Google, and my, at the time, my husband, my ex-husband now, I was like, he's an electrical engineer, and all of his friends are nerds, so I'll call him and ask him if any of them know how to solve it. I was like, I'll keep going until someone I know knows how to solve this, and we'll figure it out.

[00:39:20] **Carol:** And if it's unsolvable, then what the hell did we get ourselves into? You know? Like, we should have no unsolvable problems in our software right now.

[00:39:29] **Tim:** And, and, and do you know what word I was waiting for you to say?

[00:39:32] **Carol:** No. What? What was it,

[00:39:33] **Tim:** Google.

[00:39:34] **Carol:** Google? I was like, I'll Google it. I literally, we'll just Google it, you know?

[00:39:38] **Tim:** Yeah. I just, yeah. No one wants to, no one wants to admit that in an, in an interview that I'll just Google it. Honestly, you dunno how to do it. I'll just Google it. But it's like, cuz I was living in this, this world where people come to my office, oh, Tim, you're the subject matter expert on this.

[00:39:52] **Tim:** And ask me a question. They literally could Google

[00:39:55] **Sean Corfield:** Mm-hmm.

[00:39:57] **Tim:** and I would say, well, what have you done to try to solve this? Well, I came and asked you. I'm like, all right, go Google this. And then they c, they would come back and go, I found an answer on Stack Overflow and it was your answer. I'm like, yes, thank you.

[00:40:09] **Carol:** Ding, ding, ding.

[00:40:12] **Sean Corfield:** I, I will admit, I mean, since I've just sort of moved into the JavaScript world and my knowledge of JavaScript is, is next to zero, I have been using ChatGPT to

[00:40:21] **Carol:** Oh yeah.

[00:40:21] **Tim:** you go.

[00:40:22] **Sean Corfield:** I have a sidebar open in the browser cuz I use Edge and it has a bing sidebar that's now the AI chat thing. And so I'll say to it things like, you know, oh, ingest, how would I test the following?

[00:40:35] **Sean Corfield:** Or, you know, in, in JavaScript if I want to re-export most of a module for testing purposes and mocking, you know, show me some code to do that.

[00:40:45] **Carol:** It's taking our jobs. You guys.

[00:40:48] **Sean Corfield:** will I, I mean, it, it gives me enough pointers to go, ah, okay. So that's sort of roughly the syntax. And, and then I can. Either ask Bing specifically, or I can try it out and see what works.

[00:41:02] **Sean Corfield:** And then my colleague, the lead JavaScript guy can go, oh no, that's kind of an old way to do that. We do it like this now. And I'm like, okay, cool. Thank you. So

[00:41:11] **Carol:** So in your interview process, if someone were to say like, oh, I'm gonna go Google that, or I'm going to check G p t it, like, are those acceptable answers for you for how we go solve a problem? Like what does, what does your gut say when someone says that?

[00:41:25] **Sean Corfield:** it depends on the, the question. I mean, if you're asking how do you solve a particular problem, which is what it sounded like Tim was asking, then yeah. You know, that's gonna be a reasonable answer. I interviewed with Google at one point and they, the, and I, I put them off, they'd been asking me to interview for a couple of years and I said, no, no, no, no.

[00:41:46] **Sean Corfield:** I've heard bad things about the interview process. I, I don't wanna do it. And eventually I was like, oh, alright, alright, alright, I'll do it. And the guy who interviewed me, he focused on, you know, how you deal with very, very, very large files, far too large to fit in memory, you know, these massive multi terabyte files.

[00:42:08] **Sean Corfield:** And I was like, I don't know, I haven't had to do that. And he goes, why would you solve it? And I said, well, Google's full of really smart people that work on massive scale problems. So I would go and find people who work on very large files and talk to them about it and get some ideas and, and then go and build it.

[00:42:24] **Sean Corfield:** And he goes, no, no. How would you do it? How would you solve this problem? And after about five minutes of going round and round and round on this, I said, you know, this is exactly why I didn't want to interview with

[00:42:35] **Carol:** Yep. Pass.

[00:42:36] **Sean Corfield:** this, this is one of those kind of gotcha questions. I'm sure there are great solutions.

[00:42:42] **Sean Corfield:** I don't know what they are. If you are hiring me to work on very large files, I'm not a good candidate.

[00:42:48] **Carol:** Agree.

[00:42:49] **Sean Corfield:** and so then we, we drifted onto actual interview technique. And I think we ended up chatting for about another 20 minutes about the interview process in general. And they would be like, oh, that's very interesting.

[00:43:03] **Sean Corfield:** That's just not how we do interviews here. And I'm like, I know that I, that

[00:43:07] **Carol:** But you should maybe.

[00:43:09] **Sean Corfield:** maybe you should. And I think it was Google that did release a study saying, you know, they'd looked at the various things they've done in interviews and the lifetime of people that they've hired and the quality and said, you know, we are not actually convinced that this brutal interview process is better than anything else.

[00:43:31] **Sean Corfield:** So.

## [00:43:32] Educational Background, Filtering

[00:43:32] **Ben:** I think maybe they've also released a study on, on educational background. I think like educational background ends up having no real impact on on longevity at a company

[00:43:43] **Sean Corfield:** And that, that actually brings me to another battle that I've had with HR departments of pretty much every company I've ever worked at. They pretty much all insist, oh, you have to have a degree

[00:43:53] **Adam:** Hmm.

[00:43:54] **Sean Corfield:** this role. And

[00:43:55] **Sean Corfield:** I'm

[00:43:55] **Ben:** theater.

[00:43:57] **Sean Corfield:** no, Why do you need degree for this? Oh, well, you know, it's way weed out candidates, but it's a useless way to weed

[00:44:03] **Carol:** Is a terrible way. Yeah.

[00:44:05] **Adam:** You have to have brown hair.

[00:44:07] **Sean Corfield:** one of the best programmers I ever hired was a, a hotshot young kid who had dropped out of college and gone on to become a, a games programmer. And when I interviewed him, you know, soon as I, I touched on the, the education issue, he's like, oh yeah, I get this in all the interviews. You're just gonna say, I don't have the qualifications you need, aren't you?

[00:44:28] **Sean Corfield:** I said, whoa, dial it back. I said, no, no. I said, I'm just very curious as to why you decided to, you know, go get a job and not complete the education. I said, I don't have a problem with it. And so he started to tell me, and I mean, he was earning good money as a games pro. and he clearly knew his stuff and you know, he kind of had the same attitude to it that I have, which is once you have, say, five years of experience, it doesn't matter whether you have a degree.

[00:45:01] **Sean Corfield:** And it doesn't matter what that degree was in. and I just, I wish we didn't have this blanket sort of approach where candidate must have a bachelor's degree in, you know, science, so stupid. But of course, HR are trying to filter candidates and they've gotta filter candidates somewhere

[00:45:23] **Tim:** Hrs trying to justify their jobs.

[00:45:25] **Sean Corfield:** Yeah.

[00:45:25] **Sean Corfield:** And, and, and you know, when you get a hundred to 200 applicants for a role, I mean, you've gotta filter them somehow,

[00:45:33] **Tim:** Yeah.

[00:45:34] **Sean Corfield:** so,

[00:45:35] **Adam:** Do you or should you just rank them

[00:45:38] **Sean Corfield:** Someone's gonna rank them. I mean, who's gonna rank them? This is one of the, the problems with this. I mean, companies are now trying to outsource to these third party sites. And I actually had a little conversation with someone about this, was it earlier today or yesterday? And they were talking about a site which sprung up and was originally focused on outsourcing the sort of live interview filtering.

[00:46:04] **Sean Corfield:** And so they would do screening interviews for people. It was all very people in intensive. And in order for them to scale their services, they began to switch to more tests. And then finally they became purely online tests and then they switched to just being a job board. Cause it was the only way they could scale the traffic.

[00:46:25] **Sean Corfield:** And I think that speaks to how tempting it is to try to sort of automate this and. Get rid of the people part of it when you know, it really is all about people.

[00:46:40] **Tim:** Hmm.

[00:46:42] **Ben:** Let me ask you a question. So I, I've heard the phrase, I'm sure we've all heard the phrase, hire quickly and fire quickly. It, it sounds like you're good on the hiring Quickly. What, what do you do about the firing quickly? How, how do you identify a problem and realize either this person needs to be put on a performance improvement plan?

[00:47:02] **Ben:** I don't know if those things ever work out or like, let's, let's just cut it off now so that we can find a better candidate.

[00:47:09] **Sean Corfield:** Okay. In, in 30 years of hiring, I have never, not once ever had to fire someone for inability to do their job.

[00:47:18] **Ben:** That's pretty amazing actually.

[00:47:20] **Sean Corfield:** I have had to have people interview with HR about things because they were inappropriate.

[00:47:28] **Ben:** Hmm.

[00:47:29] **Sean Corfield:** Um, and there are a couple of people who I've dealt with who have lost their jobs for inappropriate interactions in the workplace. you know, and there's that side of it. But no, in terms of technical ability, I've never had to fire anyone for not being able to do their

[00:47:45] **Ben:** That's, I'm, I'm kind of blown away. That's

[00:47:48] **Adam:** That's, that's impressive.

[00:47:50] **Sean Corfield:** Well,

[00:47:50] **Tim:** is pretty impressive

[00:47:52] **Sean Corfield:** there are a lot of companies that will just hire, oh yeah, you seem good enough, we'll hire you. And then three months, six months down the line that, oh, well you're not, you know, productive enough, we're gonna let you go.

[00:48:02] **Adam:** Have you ever been in a situation where you feel like you're, you're just not getting enough applicants or not getting the right applicants, and you just kind of have to like,

[00:48:10] **Tim:** work with what you got.

[00:48:12] **Adam:** well, that's a choice you have to make, right? You either have to work with what you've got, or you've gotta figure out how to get to the right people.

[00:48:18] **Sean Corfield:** yeah. And. It, it can happen. I mean, you know, we've had open recs where we just haven't had any good candidates and we've had to decide, well, do we just want to fill the role or do we want to put it aside for a while and rethink how we're we're going to deal with this? in fact, even on the closure side, we had a, a role open.

[00:48:37] **Sean Corfield:** We were gonna hire a junior closure developer. And, you know, we interviewed a bunch of people and didn't really find anyone who felt right for us. and in fact, I had someone come up to me at a conference and say, you know, oh, I saw you had the open rec for the junior developer. I'm interested. And I said, oh, you're far too senior.

[00:48:58] **Sean Corfield:** I mean, I already know you from your reputation and your work online and you're way too senior for it. And they were like, oh, okay. we never managed to find anyone for that role. So we, we decided, well, we'll close it down, we'll rethink. And a while later we said, well, Maybe what we can actually do here is hire someone more senior.

[00:49:18] **Sean Corfield:** and, you know, we'll pay more, but we'll have someone come up to speed faster and then we'll essentially treat them as, you know, tech, lead on, on various parts of the product. And so we put that rack out there and the same person came up to me at the next conference and said, so, you got another job open now.

[00:49:35] **Sean Corfield:** And it's, you know, a more senior closure person. am I suitable for this one? And I was like, you want this job? And they were like, yeah. And I'm like, okay, we'll do some sort of interviews, but you're pretty much hired. and they're still with, with us today,

[00:49:51] **Carol:** Oh wow.

[00:49:52] **Sean Corfield:** so, you know, which is, which is great. yeah, I mean for the JavaScript role, we, we had, I don't, like I say 150 candidates.

[00:50:01] **Sean Corfield:** I think we ended up talking, finalizing that to. Only maybe with three candidates did we get to salary discussions with, you know, it's, you have to go through a lot of candidates. You,

[00:50:15] **Sean Corfield:** you've gotta decide what are you prepared to put up with and are you willing to continue to operate without filling those roles.

## [00:50:24] Layoffs, Importance of Network

[00:50:24] **Ben:** This is, this is maybe a weird question, and maybe this is, maybe this is something you don't even know. About, or something you wouldn't be comfortable necessarily talking about. But with all of the layoffs that have happened recently on a lot of the podcasts, people have been talking about how do you find another job?

[00:50:39] **Ben:** How do you prepare to be more resilient in your career? And one of the topics that comes up quite often is work. Work your network. Like find your people, talk to your people. Find your meetup groups that a lot of jobs are found through people you knew who worked at a place, or people you met who worked at a place.

[00:50:58] **Ben:** How in reality, from your side of the table, how important is networking? How many, how many people do you think you find? Maybe like percentage wise based on network versus just resumes?

[00:51:14] **Sean Corfield:** Oh, it, it certainly can help you get into a lot of jobs there. There are certainly places where having the right connections is often enough, at least to get you in for an interview.

[00:51:26] **Ben:** Hmm.

[00:51:27] **Adam:** you know, you may not know the hiring manager, but maybe you know, one of the engineers and they'll recommend you. how many people have I actually hired purely through knowing them? Two, maybe. Joe and Brian and that whole crew?

[00:51:43] **Sean Corfield:** forgotten that. The whole broad choice thing.

[00:51:45] **Adam:** Yeah.

[00:51:46] **Sean Corfield:** No, I, I'd kind of, I'd try and, and forget about that startup Imploding. Yeah. I, I felt awful. I felt awful. I mean, you know, we, we had an interesting product. We hired friends, Joe Brand, Ray Camden, and we got on great. We were enjoying building stuff.

[00:52:10] **Sean Corfield:** Things were going great. the company had a meeting on the Monday and it was terrific news, you know, sales pipeline, all this and the other, and the very next day they called us all back together and said, well, one of the, the big customers has put off their order for, however long it was. And that's left us with the cashflow problem.

[00:52:29] **Sean Corfield:** And we can't pay you beyond tomorrow. So tomorrow's your last day.

[00:52:33] **Carol:** Whoa. Ouch.

[00:52:35] **Sean Corfield:** and you know, I. I've been in three startups. so I'm kind of, you know, I know how it can be, it can be very abrupt. the others hadn't. and I think Joe and Brian particularly had, had quit other jobs to come work with

[00:52:49] **Sean Corfield:** me.and so they were kind of like, you know what the f and I was like, well, startup life can be a bit like this.

[00:52:57] **Sean Corfield:** so, you know, that was pretty brutal. you know, hey, they, they did all right in the end.

[00:53:02] **Adam:** Yeah, they landed on their feet.

[00:53:03] **Sean Corfield:** they're smart guys.

[00:53:04] **Sean Corfield:** going back to your question about the, the tech layoffs though, I mean the numbers sound big, but I think most of the big companies that have laid off a bunch of people are still net positive in terms of the people that they've hired since 20.

[00:53:19] **Ben:** yeah, that's what I've heard.

[00:53:21] **Sean Corfield:** So, you know, it's a course correction. It's not, oh my God, the IT industry is crumbling and we're all gonna get let go. and most of the people who've been let go from the big tech companies have good severance. they often have a good network of people and, you know, they're experienced engineers. So finding new work, whilst yes, it's always horrendous if you suddenly lose your job and you've got a mortgage of kids and, and, you know, all your responsibilities.

[00:53:54] **Sean Corfield:** But for that sector, they are just about the most employable people there are out there.

[00:54:01] **Sean Corfield:** Um, and you know, anyone who's in a highly paid job should have the smarts to have some sort of buffer for that job going away. you know, if you are in a highly paid job and you don't have any savings, then Maybe

[00:54:20] **Adam:** Work

[00:54:20] **Sean Corfield:** getting laid off isn't,

[00:54:21] **Carol:** Yeah.

[00:54:22] **Sean Corfield:** the the worst thing that's happened to you because you've already made very bad decisions about what to do with your money? I don't, I don't wanna sound sort of casual and flippant about it. I mean, you know, I, I have been through layoffs that were sudden and unexpected.

[00:54:38] **Sean Corfield:** and certainly, you know, some of the startups that just kind of implode with no notice and your left egg, like, oh, well, okay, now I need to scramble and, and figure out how to pay my medical insurance. you know, the continuing benefits stuff, and you're suddenly like, whoa, that's expensive when I don't have a job. but yeah, it, I I view this just as a course correction. I mean, I was@macromediawhenthe.com bubble burst and we had like one day where I think overall it was like 25% of it got let go in one day. And managers were just coming through and tapping people on the shoulder, and then those people were not coming back to their desks.

[00:55:17] **Tim:** Duck Duck goose layoff.

[00:55:19] **Sean Corfield:** Yeah. It, it was brutal. I mean, by halfway through the day, we were all huddled over our computers just being really quiet. It's like, I'm, I'm working really hard here. Please ignore me. Please just

[00:55:29] **Sean Corfield:** ignore me. You know?

[00:55:31] **Tim:** I'll be a good boy. I'll be a

[00:55:32] **Tim:** good boy.

[00:55:33] **Sean Corfield:** Yeah.

## [00:55:33] Hiring for a Junior Role

[00:55:33] **Adam:** so Sean, a couple of minutes ago you mentioned, hiring juniors and it made me think that, actually I have in front of me. You also mentioned earlier your mind map, and you were so gracious to share that with us on the, the Discord for the podcast a while back. And I've saved it and I shared it with my coworkers and I'm eagerly waiting for the opportunity to use it.

[00:55:52] **Adam:** cuz it looks awesome. But, you know, again, looking at this, and, and from what you've said earlier, it sounds like your interviewing process leans very heavily into let's just talk about your experience. and so when you're hiring for a junior role, how do you modify that?

[00:56:08] **Sean Corfield:** That's true. That one's tricky. if you are hiring like a, a brand new entry level first job ever, they're not gonna have any experience. So what you can talk to them about is, Why they want to get into it, why they want to work for your company specifically. what do they think is going to be the most exciting part of working in the software industry?

[00:56:32] **Sean Corfield:** You know, what other things did they consider working in, those sort of questions. And so you can still get a lot of information out of people, even if you can't specifically ask about past projects. But it might be that, you know, a candidate's done something like, I don't know, they, they've done stuff with jcs or, or, you know, whatever.

[00:56:52] **Adam:** What did jc

[00:56:53] **Sean Corfield:** I'm trying to think what that actually is. It's, it's, my wife talks about this a lot. It's like the, the local commerce organization, for students, I guess. I dunno, I'd have to go look it up. But

[00:57:05] **Sean Corfield:** anyway,

[00:57:05] **Adam:** a new one

[00:57:06] **Sean Corfield:** uh, sorry. Okay. but you know, they've probably done some sort of, Interactions, projects at school, college, some sort of

[00:57:14] **Sean Corfield:** teamwork, but anything that you can find that they've done as teamwork or project based work, you can ask them about, that's fair game.

[00:57:22] **Sean Corfield:** I mean, obviously not personal details since, you know, but there still should be usually enough to get some information out of them about that. I mean, if you have someone who's done no team work at all, they've never worked on a team project, not even at school, then you've gotta question how are they going to fit in with your team

[00:57:44] **Adam:** Yeah.

[00:57:44] **Sean Corfield:** and work well, you know, in a group where they're going to be both taking orders and giving feedback and, and suggesting things.

[00:57:53] **Sean Corfield:** So that's, that's definitely trickier. But the stakes are also lower with a junior hire because you've got a chance to really mold them and train them up on how your company works, how you like your code done. How you solve problems. you know, and sure. If that doesn't work out, then yeah, to Ben's point, you might have to let them go. and some of it will depend on how good your ability to mentor new developers is.

[00:58:19] **Adam:** And is that part of what you're thinking about when you're hiring for a junior role is like, can I mentor this person? Should like do, do we have the

[00:58:27] **Sean Corfield:** Yes. And in very specifically with our latest round of JavaScript interviews, we were hiring for a junior developer that we expected to sort of grow within the company. And so we were open to taking people for whom this was their first job. but preferably people who had done some JavaScript coding before, perhaps they'd gone through one of the boot camps or something like that.

[00:58:51] **Sean Corfield:** but there were several candidates who looked very promising for whom this would've been their first, commercial programming job.

[00:58:58] **Ben:** Can I just say it is awesome that you guys are hiring for more junior level engineers? Cuz the, the thing that I tend to see is companies that say we would love to hire juniors and train them up, but we just can't afford to. Right now because of X, Y, Z constraints. So kudos to you, sir.

[00:59:16] **Carol:** Yeah.

[00:59:16] **Sean Corfield:** Well, you know, we, to be fair, we didn't end up hiring anyone. you know, and

[00:59:22] **Sean Corfield:** irrelevant.

[00:59:22] **Ben:** you tried.

[00:59:24] **Sean Corfield:** but yeah, I mean, and you've gotta make that trade off. You've gotta decide, okay, you know, how much work is it going to take to bring someone up to speed? and it's, it's easier with some technologies than others.

[00:59:35] **Sean Corfield:** we looked at it with closure and that just, I think, potentially could have been more difficult for us, because it's more of a niche skill. but with JavaScript, there's a huge amount of material out there that

[00:59:48] **Carol:** Oh yeah. A big community to help teach.

[00:59:51] **Sean Corfield:** And you know, and I mean, I've found that. You know, as a newbie, JavaScript between some of the tutorials online, between ChatGPT, between my coworker who's been exceedingly patient with me, I've, I feel like I'm coming up to speed fairly quickly on this, even though it's radically different idiom and environment to what I've been working on for the last 10 years.

[01:00:16] **Adam:** So this maybe this is a fantastic question to end on. In my mind, but, is hiring a junior developer a an active community service? Like, is there a, any other reason to do it other than to just like, help the, the craft continue to grow and pass on to the next generation?

[01:00:33] **Sean Corfield:** Oh, I wish it were that. that sounds wonderfully altruistic. No, I, I think for a lot of companies, they, they're still very comfortable with, oh, let's hire a junior person and we don't have to pay them too much, and we can just kind of stick them at a desk and, and feed them simple requirements and get them to

[01:00:50] **Adam:** Hmm. So that sounds like something that would be made, by business people at a company who, it, it, they're not a technology company, right? They're, they're producing something that is, they're, it's a manufacturing company that has it not, we make a SaaS type thing. Right.

[01:01:06] **Tim:** Yeah. So I'll say this. So I mean, Carol talked about, you know, her first interview was with me as an intern. And the whole reason for that was we were having a hard time finding developers where we were. This is before everyone worked remotely. and so, you know, I was on the board of one of the local colleges, and so as part of that, we recruited from.

[01:01:26] **Tim:** Local colleges. And that's why we, we had an intern program that I, you know, I did for several years and became very successful. And I mean, Carol was a result of it and several other people were a result of it. so I, I didn't see it as altruistic other than it was, you know, it was solving a problem that we had at the time as finding local talent.

[01:01:45] **Tim:** And if we had to build that local talent, then we were willing to do that. And it, you know, we, we got something good out of it. We had, you know, interns are very, very cheap,

[01:01:54] **Carol:** Very cheap.

[01:01:55] **Tim:** but they turned into full-time employees, right. So, and then they, you know, got better salaries and everything,

[01:02:00] **Carol:** very impressionable, right? They need to be molded like they are eager, so they're like, you know, ready to take on whatever structure you have in place. And honestly, they don't know any better. So if you're doing something wrong, they're just gonna follow along and do it. So good or bad,

[01:02:15] **Tim:** Yeah. Then you wait, then you wait for her to get another job, and then she comes back to your job and says, here's everything you guys are doing wrong. So I, I altruism, I don't know. But yeah, for us it was solving a need

[01:02:27] **Sean Corfield:** Yeah. And I, I, I would love for us, for the company, I meant to, to have the bandwidth and budget to be able to say, you know, we'll, yeah, we'll take on more junior developers, we'll train them up. you know, the reality for us is that our team is very small and isn't gonna grow very big or very fast. So it's, it's kind of difficult to do that.

[01:02:48] **Sean Corfield:** but yeah.

[01:02:49] **Adam:** Okay. Well, Sean, thanks for coming on. do you have anything that you want to, promote or, or tell people where to find you and come bug you and talk about testing or interviewing or

[01:03:01] **Tim:** closure.

[01:03:02] **Adam:** closure?

[01:03:03] **Sean Corfield:** Well, yeah, I mean, I'm still in the cfml slack, for folks there. I'm most active these days in the closure community. I'm, I'm not very active on Twitter anymore. I've, I've abandoned it for master, but I'm Sean Corfield or one word pretty much everywhere, and anyone who searches for that will find me.

[01:03:21] **Adam:** All right, great. are you gonna stick around for the after show?

[01:03:24] **Sean Corfield:** Sure. Then Ben can ask me the, the inner questions about Macromedia.

[01:03:30] **Ben:** excellent.

[01:03:31] **Adam:** We'll, spill the tea leaves.

## [01:03:33] Patreon

[01:03:33] **Adam:** So,I mentioned the after show. we're gonna talk about that. Carol has a note here that she wants to talk about the book Project Hail Mary, which is, I think possibly my favorite book of all time. So that'll be a good discussion. if you're not familiar, the after show is, one of the perks of being a patron of the show.

[01:03:47] **Adam:** we provide all of our patrons early access to new episodes, and our after show. and so I guess this is the part of the show where I tell you that this episode of Working Code was brought to you by the reason that manhole covers are round and not square. And that's all I'm gonna say. I'm not gonna, you're gonna have to figure it out, one out on your own.

[01:04:04] **Adam:** And listeners like you. And if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing costs, and we couldn't do this every, without them.

[01:04:17] **Adam:** Special thanks to our top patrons, Monte and Giancarlo.

## [01:04:20] Thanks For Listening!

[01:04:20] **Adam:** your homework this week, what do you guys wanna do? Let's do, let's do, tell a friend, right, okay, cool. Tell a friend, or tell an enemy, you know, whichever, whichever suits your opinion of the show. as long as you're telling somebody. and That's gonna do it for us this week. We'll catch you next week. And until then,

[01:04:37] **Tim:** Remember, your heart matters and no test is required. Your heart gets the job.
