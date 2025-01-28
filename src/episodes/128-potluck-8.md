---
title: "128: Potluck #8"
description: "This week on the show, we discuss a variety of web and web-adjacent topics."
date: 2023-05-24
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/128-potluck-8/id1544142288?i=1000614292641"></iframe>

This week on the show, we discuss a variety of web and web-adjacent topics. Adam is feeling dubious about recommending a career in web development to his children (is it still worth it)? Ben legitimately wants to understand why we - the web development community - don't approach Testing with a YAGNI (You Ain't Gonna Need It) mindset. And, Tim wants to consider different ways to handle errors in a RESTful API.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/128-potluck-8.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I charged something on the credit card to make sure that it worked, and then I went into our administration system and I refunded that, that charge. Cause I'm like, oh, I'm just testing.

[00:00:08] **Ben:** I don't wanna actually pay for this, for this system. And, it was American Express and they immediately shut down our account

[00:00:15] **Adam:** Oh no.

[00:00:16] **Ben:** I was, I was doing something fraudulent and literally we couldn't use American Express for, I think it was like 12 months after that.

[00:00:24] **Adam:** Wow.

## [00:00:46] Intro

[00:00:46] **Adam:** okay, here we go. It is show number 128, and I'm coming at you live from yet another hotel room, this time in, university City, Philadelphia. Anyway, it's a episode 1 28. On today's show, we're going to do another potluck, a collection of small ideas that we wanted to get together and discuss.

[00:01:02] **Adam:** Unfortunately, Carol couldn't be with us tonight. She had another little family emergency to deal with, so hope everything's going okay, Carol. but in her stead, the show must go on.

[00:01:12] **Ben:** I just want to interject and say that isn't 1 28, that's an important computer science number, right? Isn't that the, amount of, that's the highest number in an, in a bite? No, no. not a bite. What's, what's the, what's the half a bite? A nipple. There's something, there's like a.

[00:01:28] **Adam:** I mean, it's two to the seven, so yes, it's, it's a, it's an exponential of two.

[00:01:34] **Tim:** It's double double 64.

[00:01:37] **Ben:** I don't know, 1 28 sticks out in my head as something.

[00:01:39] **Adam:** so five 12 is half a gig. So 2 56 is quarter, so 1 28 is an eighth of a gig of stuff.

[00:01:47] **Ben:** Anyway, good number. All that education paying off.

[00:01:54] **Tim:** Nerd numerology.

[00:01:56] **Adam:** let's start with our triumphs and fails. And since Carol's not here, how about you go first, Tim?

## [00:02:01] Tim's Triumph

[00:02:01] **Tim:** So I'm going with the triumph. I'm still enjoying, prototyping. I'm still still working on prototyping. Um,have access to a api, the A that I hired, you know, a consultant to help us figure out the api. And, and since then, just been building all sorts of cool things to, to consume the API and tools and stuff.

[00:02:20] **Tim:** So, yeah, it's going, going, I love that sort of open-ended kind of exploration of, all right, so I'm trying to figure out how to get this where I, you know, figure out, look at the doc stuff that they didn't really specifically tell me, but now that I sort of have a roadmap, I can figure it out. So just finding new cool things.

[00:02:38] **Tim:** It's kinda like a, kinda like a treasure hunt, find a little nugget, go, oh, okay, cool, I can do some of that. Building it and just kind of slapping it together. Not really. Super worried about, you know, how resilient it is and how, you know, fail safe it is, but just getting proof of concepts out the door. So still loving that and I'm probably doing that for the next couple weeks.

[00:02:58] **Ben:** Nice. Very cool.

[00:03:00] **Tim:** Yeah, enjoying that. And then today I finally finished a Daniel Fast. I don't know if you, have you guys ever heard of a Daniel Fast?

[00:03:06] **Ben:** No.

[00:03:07] **Adam:** No.

[00:03:08] **Tim:** do This

[00:03:09] **Adam:** It's like wax on, wax off.

[00:03:11] **Tim:** yeah, yeah, yeah, exactly. Sweep the leg. so Dan and the Bible, you know, the, the three Hebrew boys and Daniel, they got shipped off to Babylon and they didn't want to eat all the non kosher stuff.

[00:03:23] **Tim:** So they said, Hey, just, just give us, you know, vegetables and water, you know, for two to three weeks. And, and if, you know, we, you know, don't look, you know, healthier than everybody else, then, you know, we'll, you know. Do what you say. Of course, after two, they, they looked great and then ate all the veg and they were, their eyes shined better than the other.

[00:03:41] **Tim:** So it's, people do this, it's kind of a fast, where you just eat whole grains and fruits and water. So no caffeine, no alcohol, no like super complex. It's just pretty much just vegetables, fruit, whole grains, like, Pharaoh and quinoa, sometimes rice. I didn't do a whole lot of rice, but yeah, I've done that for over two weeks and feel good.

[00:04:05] **Ben:** Wait, wait, wait, wait,

[00:04:06] **Tim:** lost eight pounds.

[00:04:07] **Ben:** Hold on. You have not had caffeine in two weeks.

[00:04:10] **Tim:** I haven't had calf or well, caffeine. That's easy. It's, it's the booze. That's the one that got me.

[00:04:20] **Ben:** Nice. Nice.

[00:04:22] **Tim:** Yeah. So, yeah. But, uh,

[00:04:24] **Ben:** though. That's pretty

[00:04:24] **Tim:** yeah. Lost eight pounds and it's like, not like I didn't, I mean, I ate, I felt like I was eating all the time. I'd eat apples and pears and you know, just constantly eating, but I was just losing weight cuz it's like, that stuff is so bulky. It's like you don't, you know, doesn't really

[00:04:42] **Adam:** does it allow you to eat? like peanut butter? I don't know if I can eat an apple

[00:04:45] **Tim:** No, no, no, no. Pro no processed sugar. So nothing would processed sugar at all, so, no,

[00:04:50] **Adam:** it's like natural peanut butter, like just crushed peanuts?

[00:04:53] **Tim:** I could, but that stuff's nasty. So I, I did eat plain peanuts, occasionally and sunflowers eats and stuff like that, but yeah. But mostly I do it just for my cholesterol cuz it really, it helps my cholesterol, so,

[00:05:06] **Adam:** I was gonna say, is this another, is this an alternative to your water fasting that you were doing before? Is it just a different strategy? Okay.

[00:05:13] **Tim:** a different strategy, so,

[00:05:14] **Adam:** So, you know, I too would probably, I would probably lose 50 pounds in two weeks if all I could eat was fruits and vegetables, because I just don't like fruits and vegetables that much, so I wouldn't be eating.

[00:05:25] **Adam:** Mm-hmm.

[00:05:27] **Tim:** You learned to like it Eventually. My favorite thing was like spaghetti squash, and then like, someone gave me a whole bunch of tomatoes and I made like a tomato sauce. I just blended 'em up pretty much and added garlic. That was pretty much it. And just, so that was really, I really enjoyed that.

[00:05:42] **Adam:** Like tomato soup. That sounds good.

[00:05:44] **Tim:** yeah, so yeah, it's just like, it was, it was like eating pasta, but it was spaghetti squash.

[00:05:48] **Tim:** So,

[00:05:49] **Adam:** Hmm.

[00:05:50] **Tim:** but anyway, I feel, feel really good. But, I, I, you know, I had my blood test. I, I have my annual physical, so I have my blood test today. So I'm cel I celebrated with Popeye's chicken and now I'm, and now I'm, now I'm

[00:06:01] **Adam:** break it fast.

[00:06:02] **Tim:** Yeah. And now I'm drinking a little vodka. So

[00:06:04] **Ben:** Nice.

[00:06:06] **Adam:** The man knows how to celebrate.

[00:06:08] **Tim:** yeah, fried chicken and vodka. So, Anyway, as far as work goes, I'm, I'm, I'm enjoying the prototyping stuff and hopefully we'll have something out the door soon. So that's me. How about you, Adam?

## [00:06:19] Adam's Triumph

[00:06:19] **Adam:** I am also gonna go with the triumph. so very heavily inspired by the conversation that we had last week with Sean Corfield. I was just kind of thinking, ruminating on hiring, and I kind of decided that like, you know, as I, as my, as my career progresses, I am more and more interested in moving toward management.

[00:06:41] **Adam:** We're a very small team. so there's not really like a management role to fill, like, you know, there's very little management work that needs to be done. kind of everybody just reports to everybody. But to move in that direction, you know, like mentoring and leadership could be an important thing. And so, you know, again, just sort of brainstorming on that while I was driving and I decided to talk to my c e o about it.

[00:07:03] **Adam:** And I think this is still very tentative or what, I'm just kinda brainstorming, but I think that we're going to strongly consider hiring instead of like, so our usual approach is hire a really strong senior developer, strap on some cement shoes and throw 'em in the deep end. Like, here you go, figure it out.

[00:07:19] **Adam:** Like kick 'em in the nuts on the way down. but I think instead of that, we might like try to hire like maybe two junior developers and I will dedicate like a good chunk of my time to pairing with them or, you know, like dedicated mentoring time. and then, like the rest I was thinking like, you know, like half day, two days a week each of them.

[00:07:39] **Adam:** So that would take like half day, four days a week fr away from me, for or from my doing, you know, my own contributions. And then, you know, I, my hope would be like to kind of spend the rest of my time on. projects that are like, not a, a product thing that needs to be built, but like, how can we move the, the ball forward, right?

[00:07:57] **Adam:** What can we do to sort of take where we're at to the next level? What can we improve in monitoring or logging or, you know, whatever, sort of thing. so that's where my head is at, but it's just, it's kind of given me this whole new like, zeal for work, right? It's, it's made work exciting again, rather than this slog of compliance crap that I've been mired in.

[00:08:22] **Adam:** so it, it's, it feels good to be excited about work again. So I'm calling it a triumph.

[00:08:28] **Ben:** That's pretty cool. And again, referencing the conversation we have with Sean Corfield where you asked him the question about hiring junior developers as sort of a public good to help grow the next crop of engineers, I think, there is, you know, whether or not that has anything to do with it, it's a byproduct of hiring junior engineers and I think that's something I feel really good about.

[00:08:48] **Adam:** Yeah, and I've been starting to think too, like, okay, so if we were gonna pursue this, like how do I find the right junior developers? And I think I might take Tim's strategy of like, let's talk to some of the local universities, talk to the computer science people, like the department people there and say like, okay, we wanna, we're looking to hire somebody, we want your standout students.

[00:09:08] **Adam:** Like, send my way. So

[00:09:10] **Tim:** That's, that, that's what, that's what we do. You'd be surprised you go talk to computer science professor at local college and say, Hey, we're looking to hire, you know, like maybe an intern or part-time person while they're still going to school, or maybe full-time after they graduate and you know, send us, like, give us a name of two of your top people.

[00:09:27] **Tim:** And I mean, that's sort of how hired Carol and also someone else at the same time as well. So they, these names came through. So

[00:09:36] **Adam:** yeah.

[00:09:36] **Tim:** they turned out, they turned out good.

[00:09:38] **Adam:** Having somebody else already vet them by getting to know them and, you know, having them submit projects and stuff. Like, that's, I don't know that you can get a better recommendation or filtering process. Right. Like,

[00:09:48] **Tim:** Yep.

[00:09:49] **Adam:** cool. Well that's gonna be it for me, I guess. So, how about you, Ben?

## [00:09:51] Ben's Triumph

[00:09:51] **Ben:** I'm also gonna go with the triumphs. We'll have three triumphs this week. Very exciting. Mine's just gonna be small, which is that I removed Twitter and Facebook from my phone. And I've been kind of enjoying that. I wa I don't, I don't remember. What was the impetus, what was the moment of inspiration for me to do this?

[00:10:09] **Ben:** I think I was just randomly scrolling through Facebook and I saw something and it made me angry, or it wasn't that it made me angry. It was like, it just was pointless. And then I felt so angry at myself for just like, I just zoned out. I was just zoning out and scrolling, and I said, I, I don't, I feel like I could do some sort of thing, something better with my time. What, what is Adam

[00:10:33] **Adam:** I'm holding up my

[00:10:33] **Adam:** phone, I'm deleting Twitter from my phone right now.

[00:10:37] **Tim:** Yeah, you're not gonna miss it.

[00:10:39] **Adam:** I, I, unfortunately, I feel like I kind of have to keep Facebook cuz there's some social groups that I'm a part of that that is where the group is like it's the only way to, to communicate with them, but,

[00:10:48] **Ben:** So, so to be clear, I'm not intending to completely exercise Twitter and Facebook from my life. I will check it from my desktop computer. Someone, someone was like, wasn't that even more dangerous? But it's not because I barely check it on my desktop. It's, it was the phone where I was, I mean, I got to the point not to be t m i here for a second, but I will literally stand at the urinal and while I'm peeing I'm like, you know what?

[00:11:15] **Ben:** I got 20 seconds to kill.

[00:11:17] **Adam:** Yeah. I'm only using one hand.

[00:11:19] **Ben:** yeah, I'm only using one hand. I'll, I, I'll, I'll, I'll see if anybody mentioned me on Twitter

[00:11:24] **Tim:** try to get that dopamine hit.

[00:11:25] **Ben:** yeah. And, so I'm enjoying it. For the first couple of days, I did definitely reach into my pocket and grab my phone and go to do where the icon was on the screen and accidentally open some random app that is now in its place.

[00:11:38] **Ben:** but after doing that for a day or two, I, I, I, I no longer reach for it. Instinctually, sometimes I go to my pocket because I'm like, oh, what's interesting. And then I remember that there is nothing interesting in my pocket anymore. But, yeah, I'm feeling good about it. I'm, I'm, I'm interested to see what my screen time alert is gonna tell me.

[00:11:58] **Ben:** You know, the, I don't, I dunno

[00:12:00] **Adam:** been on your phone for 16 hours this

[00:12:02] **Ben:** Yeah, yeah, yeah. So we'll see if that's been impact.

[00:12:05] **Adam:** Cool. Good for you, man.

[00:12:07] **Ben:** Yeah.

[00:12:07] **Tim:** Yeah, I found that turning off the, the badge alert notifications, I, cause I hate seeing it like a badge number and I like, oh, I gotta, I gotta clear that. I don't even wanna read it. I just wanna clear it. So, turning that off, it's like, I, I don't, I almost never look at Twitter anymore.

[00:12:21] **Adam:** Did, did you make it so it's just like a dot, or did you get rid and and just get rid of the number or did you get rid of the badge entirely?

[00:12:29] **Tim:** It just turned off notifications in, in the iPhone, which you can do

[00:12:34] **Adam:** so like, but just for social apps or,

[00:12:37] **Tim:** yeah, you can per app, you can turn it off.

[00:12:39] **Adam:** Yeah,

[00:12:41] **Tim:** So

[00:12:41] **Adam:** that's a good idea. I might do that.

[00:12:43] **Tim:** that kind of helps cuz then if I, I don't see the two or the three and I'm like, oh, I don't see it. I, I'm not gonna go, I have to be, be thinking about, oh, I'm, lemme pull up Twitter, which I almost never do any Facebook, you know, lot, lot of groups that I'm part of that I like to keep

[00:12:57] **Adam:** Mm-hmm.

[00:12:57] **Tim:** of.

[00:12:57] **Tim:** But at Twitter, they just, they recommend the weirdest stuff to me. Lately, I don't even know.

[00:13:02] **Ben:** it's gone bonkers.

[00:13:04] **Tim:** I, I don't know how I got, and you know, if, if you're into this, that's fine, but it's like all of a sudden, like all these like really hairy men, like pictures of like these hairy men, like, I guess they call them bears.

[00:13:14] **Tim:** They, they were, they kept showing up on my feet. I'm like, how did I get on this list? I dunno. I mean, they're nice looking men but's really Not my thing. Sorry.

[00:13:24] **Adam:** the modern day equivalent of your friend, like pranks you by subscribing you to some weird magazine.

[00:13:28] **Tim:** yeah, exactly. Wow. I don't know. I don't know where to

[00:13:33] **Adam:** yeah, yeah. We're, it's a hard cut. There's no,

[00:13:36] **Tim:** Yeah.

[00:13:36] **Adam:** transition.

## [00:13:38] Would You Recommend Going Into Web Development

[00:13:38] **Adam:** So from there, potluck, who wants to go first? Okay, don't all jump at once. I'll go first. So would you, here's my question. Would you, if you had children, I know some of you listening and some of you whose faces I'm staring at right now don't have children.

[00:13:52] **Adam:** but if you had children or, or let's say, you know, a niece or nephew or just a, a close friend, you know, that you really care about, and if they were asking you should they pursue a career in web development specifically, not just coding, but web development, would you advise against it or for it and why or why not?

[00:14:10] **Ben:** I'd still go four. I mean,

[00:14:13] **Adam:** think so?

[00:14:14] **Ben:** it, it, it's just such an exciting space. I think so, let me caveat that though. It's like if you are, if you get the thrill out of having an idea in your head and then be able to manifest it into the world, And you think that doing that by typing is kind of exciting? I mean, there's still that there's, there's still that's such an exciting, just unlimited potential to see something become in the world that did not exist before.

[00:14:45] **Adam:** Yeah,

[00:14:46] **Tim:** Yeah.

[00:14:47] **Adam:** I, I agree. There's a, there's a lot of, rapid feedback for creative processes there. I think what scares me away from the idea of recommending, and I guess I'm, this is on my mind because I have a 14 year old, and so he's right on the cusp of, I think next year will be his freshman year of high school.

[00:15:04] **Adam:** And so, you know, he is starting to think like, okay, well if I do go to college, what do I wanna study? What kind of career path do I wanna put myself on? And, there's a lot of different ways that you can look at it. I think I went into coding because my dad was encoding and. He was very successful at it, and I got the opportunity to screw around with it at home and felt like I was pretty good at it.

[00:15:29] **Adam:** And I knew that there was money in it, and my dad told me that like, it was only going to grow in the future, right? And so it's like, okay, well there's gonna be demand for it. I seem to have some amount of natural talent for it, and I, and I enjoy learning about it, so sure, you know, I'll do that and, and potentially high earning.

[00:15:47] **Adam:** So that didn't hurt. I think what turns me off about it though is that, especially for web development, I feel like right now this stuff that you need to learn to be competent with, you know, the modern stacks that people are using is so huge. Like, if you, you know, if you're fresh outta college and they didn't teach you the specific frameworks and stuff that you're gonna be using, you know, you have so much to learn.

[00:16:13] **Adam:** and, and it can be daunting. And it maybe, again, maybe it's because my kids are easily overwhelmed. So like, you know, I, I wonder if it's just not a good fit for my kids or if it's, if we as an industry have work to do to make it easier to onboard, into the career path.

[00:16:31] **Adam:** That said, you know, I'm sure that there's a lot of people or some people, doing a lot of good work in that space, like onboarding bootcamps and things. I, I kind of want to just like audit a bootcamp or something, or audit a, a beginning web development class and just see what it's like, you know, what kind of stuff do they have to learn?

[00:16:51] **Adam:** What's the curriculum for Zero to web developer right now? Cause I, I, I don't know that I could put together a good one,

[00:16:58] **Tim:** Hmm. How old? How old are your kids again?

[00:17:01] **Adam:** 14 and 12 right now.

[00:17:03] **Tim:** Okay, so you haven't reached the age yet where everything you say is complete nonsense to them, so probably on the cusp.

[00:17:11] **Adam:** Well, When you say complete nonsense, you mean just like they don't care what I have to say?

[00:17:16] **Tim:** Exactly. Yeah.

[00:17:17] **Adam:** Yeah. We're, yeah. It's, it's weird. Most of my interactions with my 14 year old is consist of me telling him terrible dad jokes and him rolling his eyes and either saying, I'm not mood dad, or, or like grinning ear to ear and saying, I love you, dad.

[00:17:33] **Adam:** So

[00:17:33] **Tim:** yeah, yeah. Yeah. So one thing, I mean, with, with, with teenagers is, you know, advising anything to them is, is, is like, disarming an an i e D. Right? It, it's, it's one of those things that just the very fact that you are recommending something is like complete negative points against it.

[00:17:55] **Adam:** points against that. Yeah.

[00:17:56] **Tim:** Right. Or sometimes it's like, if they see you doing something, you're not really recommending it.

[00:18:02] **Tim:** But it's like, I mean, since I've been, you know, I work from home now, it's like they see what I do all day, which honestly doesn't look that exciting. I'm sitting in this exact same spot that I am right now.

[00:18:12] **Adam:** Yeah, they can actually like sit here and watch me get fatter.

[00:18:14] **Tim:** yeah. Right. So, you know, so I was always very careful. I didn't want to, I didn't want to like push.

[00:18:24] **Tim:** You know, particularly on my son, right? Because, you know, it's, he's a boy child. I tend to imprint my desires on him, but we're completely, he's very much an introvert. He's very much an introvert, and I don't want to, he's not me, right? He's not me 2.0, although he looks a lot like me. so I was very hesitant to push things on him, but he would see what I would do and I'd show him kind of what I was working on from time to time.

[00:18:44] **Tim:** And he, you know, some people recommended a class, it wasn't me. Someone found a Harvard class, which was, which was free about web development and programming. And he took that and it was like a full, like nine months. And he stuck with it. He stuck with it. So it's like, I, I think if the kid does not interested at all and you advise for it, there's no amount of pressure in the world.

[00:19:07] **Tim:** It's gonna make them do it. But if they do it and they enjoy it, it's like, and if they, if they do it again, so I mean, people like, they'll ask my son, what's he studying? College? He's taking computer science. And, and they're like, oh, just like your dad. And. He's like, yeah, kind of. But I don't think, I don't think it was because I ever told him to do it, that he did it.

[00:19:27] **Tim:** He's just, he did it and it's like, oh, this is pretty cool. And he f particularly in high school, he found use for it. He would take like his AP statistics class and, rather than he'd learn the statistics, but he figured out he could just pull up the browser and used JavaScript in the browser console to build routines and functions to figure out the statistics.

[00:19:47] **Tim:** So that's how he did all his statistics tests. You just pull up the browser and start,

[00:19:50] **Adam:** funny because they're doing it on a computer. That's funny.

[00:19:53] **Tim:** yeah.

[00:19:54] **Ben:** that's a really critical point too, that the more overwhelming a field is and the more ever expanding it is, which I think our industry definitely has that

[00:20:03] **Tim:** Yeah.

[00:20:04] **Ben:** the more important it is that you sort of land with some sort of an interest or, or I guess a way to connect with it.

[00:20:12] **Ben:** Like I remember back in high school when we were using the t i 82 as the Texas instrument calculators and, you know, you could do the graphing and the math and whatnot, but what was really exciting was being able to have it draw little pixels on a screener to take a couple of inputs and you, and you wired up a physics formula for, you know, whatever.

[00:20:33] **Ben:** I don't remember physics, but it, it was something where I was like, oh, this is so cool. And it, and it connected with something that I was interested in. And if you can get to that w you know, at work we, we often talk about sales processes, land and expand, that you just have to land in a company. With one person who will advocate for you, and then you get a foothold in the door and you can expand to the rest of the organization.

[00:20:56] **Ben:** And I think coding is very much the same way. If you can find one point of interest that you can connect with and see how it can be a meaningful change in your life, then you can, I think, have the, the enthusiasm to, to do that uphill battle for the rest of your life.

[00:21:13] **Tim:** I mean, the beauty about being young is that you can try something, spend some time on it, and then say, you know what? I don't like this, and do something else. And that's fine. That that's what being young's all about. Right? You don't wanna feel like you're stuck into something. So, you know, advise your kids.

[00:21:28] **Tim:** Sure. Give it a shot. You know, if someone says, Hey, should my kid do web program? Sure. Give, give it a try. If they, if they have a, they see that, they feel like it's fun, let 'em go for it. But if they don't find something else,

[00:21:40] **Adam:** Yeah, no, this all reminds me of a, a quote that I saw the other day. I wish I had written it down cause I'm gonna mangle it here. But it's like something like, As dads, we need to not direct our children's lives, but like, you know, guide them. Right? Like, help them figure out the problems that they're facing, not, okay, go do this.

[00:22:01] **Tim:** Yeah. Yeah, yeah. Don't, don't, don't tell 'em what to do. Give 'em the space to figure it out.

[00:22:07] **Adam:** Yeah. And the space to fail.

[00:22:09] **Tim:** Yeah. I, I, I saw something slight tangent, but is related. So I, I saw something interesting that, and I don't know how true, how true this is, but they're saying that the reason that from the age of like your early teens to like your, like early twenties, that teenagers tend to like feel that their parents are idiots. Right. It's like, it's like they're just at that age, you're like, oh, my, my mom and dad, they're just so clueless. They, they just, they've just, it's, it's sort of a generalization, but that is sort of the feeling that you have at that age, that you're so much smarter than them and that, you know, you don't really need them.

[00:22:43] **Tim:** And is that, you know, back in the early, early times of human beings when we're very small communities, that natural desire to just want to get as far away from your parents as possible was, beneficial because like, everyone around you was related. So you would like, like, oh, my dad's such an idiot, you know, he's making me hunt and skin deer.

[00:23:02] **Tim:** It's completely stupid, so I'm gonna, they run off to somewhere where the other adults seem so much smarter. That's true. You can, your teenagers can hear the exact same thing from a, from, like an aunt or an uncle or a distant cousin. That's your age. And, and they'll be like, oh, this is the smartest thing I ever heard.

[00:23:16] **Tim:** I literally said the same thing. But they'll hear it from another adult and it, it's super smart. And that's because, you know, they get them out of the local population to go breed in another population. So that, you know, and I was like, okay, that makes somewhat sense. I don't, maybe it's true, maybe it's not.

[00:23:34] **Tim:** But, yes. So I, I just, yeah, just giving your kids the space to figure stuff out on their own and with no pressure whatsoever. I try my best not to pressure them at all.

[00:23:47] **Adam:** Yeah. My, my predicament that I find myself in is like, the one thing that I don't wanna see happen is for my kids to become like destitute and depressed and, you know, like fall into alcoholism and that sort of thing. Like my, my oldest right now,

[00:24:02] **Ben:** that escalated.

[00:24:03] **Adam:** Yeah. Oh yeah. That's, that's my brain, man. That's the way it works.

[00:24:06] **Adam:** my oldest is, has always been super into reptiles. Like, just ask him a, ask him to name four different, Latin names of, of lizards, that are, are mostly blue. Right. And he could do it right. yeah, he's super into reptiles and, we, we went on a camping trip to this like place in middle of nowhere Pennsylvania, called Clyde Peeling's Reptile Land.

[00:24:30] **Adam:** It's like a reptile specific zoo. And ever since then, like with the exception of like maybe the last six months up, up until then, if you asked him what he wanted to do with his life, it was, I want to go be a zoo zookeeper at Clyde Peelings.

[00:24:44] **Tim:** Wow.

[00:24:44] **Adam:** yeah. And it's not even that big of a zoo. Like, you know, you can see the whole thing in an hour and a half. So, like, okay. You know, if you can make a living at it Sure, go for it. But like you're not exactly reaching for the stars there.

[00:24:59] **Tim:** But longs, he is happy.

[00:25:00] **Adam:** Yeah.

[00:25:01] **Tim:** I, I, I, but I do kind of agree with you. The thing I really liked about when I was in my teens that I liked about computers at the time is like, I, even then I knew it was early days,

[00:25:11] **Adam:** Mm-hmm.

[00:25:12] **Tim:** right? Even then, I'm like, you know, this is, this is kind of pretty early. I feel like I was, I felt like I was getting in on something Niche, niche and like, you know, edge and, but now it's, it's mainstream and it's become so much more complex back, you know, back in the days of basic and, you know, turbo Pascal compilers, and it was somewhat pretty simple.

[00:25:33] **Tim:** People thought you were a super genius and it, you know, as a kid you're like, really? You knew? Like, that's not as hard as you think it is. You just, you just don't know it. But nowadays it, it's gotten so complex and I just think there's other areas of l of learning that are kind of cutting edge that I would be more into if I were younger now.

[00:25:53] **Tim:** Like, like, well I guess it's not that. Simple, but like bioengineering, I mean, that whole area seems like that's sort of like where the new cutting edge is. New cutting edge. Right. But, it's not like you can just go buy a buy. Well, actually you can buy these bioengineering kits and

[00:26:10] **Adam:** Hey, they have CRISPR on the shelf at Walmart now.

[00:26:12] **Tim:** Yeah, they, they do. Yeah. I mean, you can buy kits these days. So I, I mean, I think those are areas that are super interesting that I, I probably would be into rather the computers if I were a teenager. Again,

[00:26:23] **Ben:** Well, one thing that I've always felt very lucky with is the fact that I did want to do programming from fairly early on. I mean, I was in high school when I knew that this was the thing that I probably wanted to do, aside from my minor, you know, mid twenties crisis where I was like, oh, I should have been a Parks Ranger.

[00:26:42] **Ben:** But whatever. Uh,other, I, I, I, I have, I've just been very lucky that I've had an interest in something, anything. And I, I feel bad for people who. Are drifting through the, through the world and like not really sure what they want to do and not quite sure what's interesting to them. And I never know what advice to give to people like that because I never had to deal with it.

[00:27:08] **Ben:** Having a direction was just always, always came naturally to me.

[00:27:11] **Tim:** I agree with you. I, I sort of felt the same way. Like I knew from like 13, like, I'm always gonna do something with computers. I just, I, I could not get enough of it. So it's like when people are like, I don't know what I wanna do. I, I don't, I don't, I feel sorry for them because it's like, I never, I never not knew that this is exactly the field I was gonna be in.

[00:27:34] **Ben:** Yeah, a hundred percent. Plus, let's be fair, there's not as many good computer hacker movies these days,

[00:27:40] **Tim:** True. Very

[00:27:41] **Ben:** are the kids even getting inspired by?

[00:27:43] **Tim:** Yeah.

[00:27:44] **Adam:** I want to be the next Sam Bankman Freed. All right, well that seems like a good place to wrap that one up. So, uh,who wants to go next?

## [00:27:53] &quot;You Ain't Gonna Need It&quot; and Testing

[00:27:53] **Ben:** All right, so l I wanna preface this with saying that this is a, an, this is a, an earnest conversation. I'm, I'm not trolling. This is something I legitimately have been thinking about and I wanna talk about Y GNI for a second in the computer world. Yag, y a g y a g n I,

[00:28:15] **Adam:** You ain't gonna need it.

[00:28:16] **Ben:** you ain't gonna need it.

[00:28:17] **Tim:** Oh, I thought it was like, like yoni or something, like female part. So I, I don't know what, I don't know what that was.

[00:28:24] **Ben:** Just as interesting. so, so in the programming world, I, I, I'm sure this exists elsewhere, but this is where I'm familiar with it. This concept of yag, you ain't gonna need it, which essentially is solving the problem in front of you and not worrying about problems you don't have yet. People will talk often about how, how do I build a system that scales to have a million users and they don't have any users?

[00:28:47] **Ben:** And you're like, whoa, just worry about getting some customers. Don't worry about your scale. Or when people are like, how do I completely abstract away my database layer so that one day I can seamlessly switch from MySQL to Postgres to MongoDB to DynamoDB?

[00:29:03] **Adam:** would anybody ever leave

[00:29:04] **Ben:** yeah. You're like, whoa. Just like, don't worry about that.

[00:29:08] **Ben:** Just build your application. You probably will never switch databases anyway. It's not a problem you need to deal with.

[00:29:14] **Tim:** Particularly if it's Postgres.

[00:29:18] **Ben:** Or, or, you know, people say like, we shouldn't mirror ourselves to anything that's AWS specific because maybe one day we want to pick up our cloud offering and move from AWS to Google Cloud. And if we start using. Lambda step functions and Google doesn't have that. Then we've locked into a vendor and we, and we wanna try to avoid that.

[00:29:36] **Ben:** And you're like, well, maybe don't worry about this idea that you might completely switch to a new hosting paradigm. Like just build your product, get your customers. Okay. I'm building to something here, which is that it seems so often in the computer world, we try to solve the problem that we have in front of us and not worry about the eventual potential of problems that we may or may never see. And it seems that as a culture, we have completely thrown that to the side when it comes to testing.

[00:30:09] **Tim:** oh. Here

[00:30:09] **Ben:** and, and I, I'm, I'm, this is a very earnest conversation. You know, they say like, you, you don't understand something until you can explain it to someone else. And I've been thinking about how could I explain this to someone else that Why are we so eager to test everything? And yet somehow are okay using much more measure and constraint when it comes to basically every other aspect of computer programming. And I, and I don't know how to answer that question.

[00:30:39] **Adam:** It's an interesting framing of the question,

[00:30:42] **Tim:** Mm-hmm.

[00:30:42] **Ben:** I could build something at work and it could be, let's say it's a, a, a small feature as part of a product and it doesn't touch anything else, and it's very simple and changing something in it will never affect anything else. And I say never in quotes because you can never know, but some things are more never than others.

[00:31:05] **Ben:** And as we get older, I think we have a better sense of where those boundaries exist. And I think as we get older, we're better about building those boundaries into our software. and, and I and I, I can very easily imagine areas of an application. Where testing just wouldn't make sense and would just be like a, a poor use of time.

[00:31:27] **Adam:** Okay, so I'm gonna give you an answer and I'm gonna call it a naive answer, but it's, it's not because I think that it's a bad answer, but more just that I, I haven't had a whole lot of time to think deeply on this. I think that there's an element of truth to this. the, so the naive answer is why do we focus so hard on testing?

[00:31:46] **Adam:** I think it's because we want to be sure that the code works right, and we wanna be sure that when something changes in that code, it doesn't break the existing features while you're working on something new. that's, I mean, that's like the textbook definition, but, like I said, I think that there's a, a grain of truth to this because I don't have a hundred percent test coverage on my stuff.

[00:32:08] **Adam:** I probably don't even have 30% test coverage. And that's not because I don't need it, it's just because we did a piss poor job of that in the beginning and now we are suffering the consequences and it's so hard to add them after the fact. but I agree that there are times that tests are just not worth the, the effort.

[00:32:29] **Adam:** And for me, at least right now, off the top of the head, what makes sense as a, a way to draw that line is like, how important is that feature? If it breaks, are you gonna get called at 3:00 AM for that? I is some executive gonna get really pissed because it broke and it made it outta production. Is somebody gonna get really pissed because it's been broke for two weeks? Like these are all, you know, these are all, I think, reasons to want to put up safeguards so that it, you'll know immediately if it gets broken and, and stop it from making to production in a broken state.

[00:33:03] **Ben:** So one of, one of the things that I think about is the, I dunno what the right phrase here, let's call like ownership distance between the code itself. And the consumption of that code. And, and let me illustrate with something like Angular or React or Cold Box, a library of framework where the people who own the code are not necessarily the people who are consuming and deploying the code.

[00:33:31] **Ben:** And that distance is meaningful because it changes the way they have to prepare for failure. That if you're shipping code to other people who are then using that code to build a product, you don't have the opportunity to react to failures in their software other than through, you know, issues filed on GitHub.

[00:33:52] **Ben:** and I, and I think that changes the, the, the confidence I guess, that you have to have in the code because you're shipping it out of context.

[00:34:02] **Adam:** the product that you're offering there is more than just the code, it's the, the guarantee that the documented API is going to work. That's part of what you're, you're giving them in that product.

[00:34:14] **Ben:** On the other, on the sort of, on the other end of the spectrum, if you're a developer who's writing a line of code, then shipping that line of code to a controlled production environment and then checking to see if the code and production is actually doing the thing you think it's doing by going and clicking the button and saying, oh, great, I added something to a cart.

[00:34:33] **Ben:** That's what I expected. The, you can react very quickly to a failure. You can, Hey, I clicked the button, and for some reason in production, maybe because of an environment variable that was different in production than it is locally. Okay, now I have to roll back. You know, that sucks. Maybe some customers were affected, but hopefully it's a pretty short feedback cycle and we can recover from that very quickly.

[00:34:54] **Ben:** And I think what we often do as an industry is we think about those two extremes as the same thing. And we try to enforce the same type of guarantees in both contexts, and I don't think, I don't think it's like having the same masters, so to speak.

[00:35:14] **Adam:** I wanna turn this around on you actually. you are a huge proponent of feature flags

[00:35:19] **Ben:** Yes.

[00:35:20] **Adam:** and as a result, I would estimate this is a total guess cause I have no idea how much effort it takes for you to create a feature flag and, and code it into your product in a way that makes it possible for you to turn on and off some feature. You know, I guess it depends on how wide, how brawling that feature is, right? But, you know, you're, you're putting in a lot of work for the ability to turn on and off a feature with an instance notice, you know, on demand. And how often do you do that? You know, like you, you might have a staged rollout to just, you know, gain that confidence in it, but how often do you actually need to claw back,

[00:36:01] **Ben:** Very rarely, I mean, maybe very incredibly rarely it, it feature flags to me have become less about, a, a failure avoidance and more about incrementally building something without, without having to deploy, you know, like a thousand files at one time to implement a feature.

[00:36:24] **Adam:** Yeah, I, I'm still not fully on that train of like deploying half finished code. I, I understand that feature flags can make it possible. I, it just doesn't feel like it fits within my workflow yet. Like, we're using feature flags. We, you know, we, we. Build a major change to the product behind a flag, and we can turn it on and off for customers that are and aren't ready for it, or to try it out for somebody in particular, whatever.

[00:36:49] **Adam:** But it just, I, I, I don't, unless you were like, you know, like the type of company where you're, you're constantly merging back into Maine and every merged domain goes to production. I just don't see the workflow.

[00:37:05] **Ben:** So a big part of it for me is keeping pull requests small. if I have a, let's say I have a feature and it's gonna take me two weeks to build. I don't want someone to have to then review a PR that represents two weeks worth of work. What I'd love is for every day to have some cohesive piece of functionality that may not represent the entire effort, but is a, here's a new, here's a new, database table, and here's the low level data access that essentially reads and writes to that table.

[00:37:40] **Ben:** Nothing, nothing uses it yet, but I want you as a reviewer to just look to say, is there anything crazy here? If not, let's ship it to production. And now the next PR that you have to look at doesn't even worry about data access because that's already been reviewed and deployed. And that way we can keep the PRS fairly small.

[00:37:59] **Ben:** And the small, the prs, the faster they get reviewed, the more interest people have in actually giving feedback instead of just rubber stamping things. And and it just keeps the whole PR process, I think, much more enjoyable for everybody.

[00:38:12] **Tim:** I, I would, I would cut. So you started this whole conversation with sort of, I guess an analogy of the whole premature optimization thing of, you know, Moving from Amazon versus, you know, over to Google and trying to prepare for that. I would take issue with that to compare that to testing, because really the premature optimization, what you're dealing with is you're dealing with the world of possibilities when it comes to testing.

[00:38:40] **Tim:** The whole thing about testing is you are asserting what you know to be true at the given time, right? So you, you, you understand the state of your code. You build tests because you say, so given what I know now about how the code works, when this happens, this should be true, right? This function should never return a null.

[00:39:01] **Tim:** And if it does, there's a problem. And, and so you can't really say that, that the, the analogy you gave, that's about a world of possibilities, which are pretty much infinite versus a very limited subset of what you know to be true. And so it's, it's, you say you ain't gonna need it, but. You're not building tests for things you don't need.

[00:39:22] **Tim:** You're building tests for things you know to be true at that time. And if, if the truth changes, that's okay. The test should point that out to you if they're done correctly, so that you can say, okay, the truth is changed now. Therefore, maybe I need to change my test, or I need to look at this and go, is there, is this a red flag I need to look at?

[00:39:41] **Tim:** So I don't really see the Agni principle when it comes to testing if, if you're doing testing correctly.

[00:39:50] **Ben:** So I think the world of possibility that I'm thinking of when it comes to test is the possibility that something in the future might break in an unexpected way, and that the tests are there as guardrails to prevent people from breaking something that they didn't intend to break. I, I will say that there is a mindset that people have that testing is documentation, and that might be true for some people.

[00:40:18] **Ben:** I've, I've personally, Never used documentation or never used testing as a source of documentation. I just, I look at the code and I'm not saying that's right. I mean, it could just be that because I'm not a big tester, I don't have an instinct to look at the test as a way to help me understand the code.

[00:40:37] **Ben:** So I don't, you know, the fact that I don't do that means nothing essentially. but so, and I, and I think this comes back to the idea that not everything needs to be tested, but things that do need to be tested should be tested. And I think in part that's based on complexity and the possibility that things will break.

[00:40:57] **Ben:** If someone wants to understand how a piece of code works and looking at that code is so overwhelming and so confusing that looking at tests are a more meaningful way to understand the code. There might be necessary complexity there, but that could also just mean that that code's too complicated, that it.

[00:41:17] **Ben:** It shouldn't have been written that way there, it, it should have been written in a way where someone can look at it and say, oh, okay, yeah, I get how this works. I understand why this returns true sometimes and false other times. And now when I make changes to the code, I'm, I'm not afraid that that's gonna break.

[00:41:32] **Ben:** And if there's some branching logic, I'll test the branching logic and then I'll move on with my life. And not all code can be that way, but I think more code is that way than we give credit to.

[00:41:43] **Tim:** I mean, I, I personally don't see te. Testing as a, as a method of documentation. I just do see, cause when you're in a kind of a sprawling system that's interconnected. All I wanna know is I worked in Section A, did section D break because of something I did in Section A that I had no clue was, was related.

[00:42:00] **Tim:** I just run the test and if it tells me that I know to go look at it, I don't necessarily think of it. I don't think of it as as documentation, maybe other people do, but I don't.

[00:42:10] **Adam:** I agree. I also don't use tests as documentation. I was sitting here thinking though that. Tests kind of, so, okay. It, it's not a fully formed thought. It's probably gonna come out like gibberish and I apologize in advance. the tests are a program that you write that verifies that the other program that you're writing, adheres to the specification.

[00:42:32] **Adam:** I started out with thinking the tests are like a, a machine readable specification for the code, and that's close. really it's a program that you write to, to prove that the code adheres to the specification. And that, that kind of got me thinking like, what if a pull request, code review was, I look at the, the tests and I agree with the intent of the tests, right?

[00:42:57] **Adam:** It's saying this feature does this thing when given this input. And I read the, the body of the tests to say, okay, I know what I'm supposed to be testing based on the, the title of the test and the, the. So tests are what? It's a,something, a range act assert, right? A a a range act assert.

[00:43:19] **Adam:** So you've got, you know, you're, you're putting together your input data, you run the thing, and then you make the assertions. And if, if I look at that and, okay, and I agree that it does implement the test, as expected, or, it implements what the test is supposed to be doing and the, and the tests pass. Mm. In some ways I don't need to look at the code, right? Like, as long as the code is, is, as long as the application is performing up to our needs, then I don't need to be super concerned with application problem. I, I don't know, I guess I'm kind of talking myself out of this part of it. Like the, you know, you're gonna wanna look at syntax, you're gonna wanna make sure somebody's not doing something that you as a team have already learned is not the right way to do the thing, right?

[00:44:01] **Adam:** Like,

[00:44:02] **Ben:** So I used to believe that Koda would just break. For mystical reasons. I, I remember, I, I have a

[00:44:10] **Adam:** Cosmic bit shifting.

[00:44:12] **Ben:** I have a, a, a very concrete moment in my mind. Years and years ago, but this is probably like 15 years ago. I was working with Clark Valberg, we're working at Epicenter Consulting and I was working on this piece of software that did, it was like a shopping cart system.

[00:44:28] **Ben:** And I dropped into the middle of this project. I had never seen it before. I had never seen the shopping cart, library that it was based on. And I had to make some changes to the code. And I remember ringing my hand so much that I was gonna change something in a file. And I was so unsure about what else might break in the application.

[00:44:46] **Ben:** Cause I was so unfamiliar with it. And Clark looked at me and he said, code doesn't break for no reason. Like, you'll make a change. And it's not sp, it's not spooky behavior at a distance. Code that's not touching, it is not gonna break. You don't have to worry about it. And, you know, whether or not there, there's some elements that they're true and some elements that are false, it, it, it, it sort of codified in my mind that it's all, it's all very practical and pragmatic and code touches code.

[00:45:18] **Ben:** It's not, there's not the, you know, worm holes and, and weird gravitational forces. And it, it, it completely changed the way that I thought about making and pushing changes to production. That there's so little that's actually mysterious about it. And I think what that's done in part is shift my perspective from thinking if I changed code and something unexpected broke, it wasn't because I didn't have tests to guide me, it's cuz that code was probably coupled in a way that should not have been coupled.

[00:45:47] **Ben:** Or there was something really clever going on that shouldn't have been so clever, or there was coupling in place that shouldn't be so tightly coupled. And that was really the root problem, not the fact that I didn't have a test. And I'm not saying that. You know it, I'm not saying that it's not unfortunate that something broke, but I'm just saying that I would be solving the wrong problem if I tried to solve that problem with a test.

[00:46:10] **Adam:** I would, I would disagree with that last statement. I think the test would bring the break to your attention earlier and you would find that coupling issue or whatever and be able to, to deal with that before it hits production. That's the point.

[00:46:23] **Ben:** I, I, I don't disagree with that, but I also, I think that we don't have to do it as nearly as often as we think we do.

[00:46:31] **Adam:** Maybe. Yeah. I think even the most zealous people listening would agree that a hundred percent code coverage is a fool's errand. So, yeah. I, I do like what you were talking about, how everything happens for a reason in the code. That I think is one of the things that I most enjoy, right? Sit me down in front of a really weird problem and say, this is broken.

[00:46:59] **Adam:** We don't know why fix it? You know, you gotta, you gotta like learn some new stuff to figure it out. And like everything there, there's a reason it's happening. It's not, you know, maybe it's a weird race condition. Maybe it's because clock SKU is, is slowly building up over the course of two months and it only happens once every two months.

[00:47:19] **Adam:** But there's a reason. And man, I love finding those obscure reasons.

[00:47:25] **Ben:** Yo, it, it's so interesting, I think about the, the best practices that I start to accumulate as I'm getting older and more experienced and more and more and more I find myself reaching for two sources of truth, which is code that's easy to find and write code that's easy to delete. And if I can do those two things, then I feel like everything else sort of just falls into place much more readily.

[00:47:50] **Adam:** I don't think I can disagree with that.

[00:47:52] **Ben:** So anyway, I'm, I'm not, I mean, I'm not a big tester. I'm not anti-testing. I am anti-testing as dogma because it, it just doesn't, I have, I don't think I could explain to people why it should be that way. And until I can do that, I. It seems just like,

[00:48:12] **Adam:** For most of this conversation, I've been sitting here racking my brain trying to remember the context for a comment you made last week when we were talking about talking to Sean and it finally came to me, you asked him about like, should developers be on hand during deploy to like test their code in production, to make sure it doesn't need to be rolled back or, or whate, you know, I forget the exact way you put it, but, and what struck me about five minutes after we got off the phone, off the phone and I, I was no longer able to commented on it in real time, cuz that's how it always goes, was, there's some things you don't want to test in production.

[00:48:46] **Adam:** You, you know, you're not gonna deploy code to your, credit card charge form and then test it in

[00:48:51] **Ben:** That's immediately what I thought of when you said that.

[00:48:53] **Adam:** Yeah, yeah.

[00:48:56] **Tim:** Although I've done it.

[00:48:57] **Adam:** Oh yeah.

[00:48:57] **Ben:** done it too.

[00:48:58] **Adam:** There, there are times that you do, you're like, it is worth the $5 to know that the form works. I'll, I'll do it.

[00:49:08] **Ben:** Sorry. Quick aside, I'm, I'm sure that I've mentioned this on the podcast before, but in case I didn't, I, I did that one time years ago at work. I charged something on the credit card to make sure that it worked, and then I went into our administration system and I refunded that, that charge. Cause I'm like, oh, I'm just testing.

[00:49:24] **Ben:** I don't wanna actually pay for this, for this system. And, it was American Express and they immediately shut down our account

[00:49:31] **Adam:** Oh no.

[00:49:32] **Ben:** I was, I was doing something fraudulent with like, essentially buying something on the company card and then refunding it back to myself, I don't know, set off some sort of a trip wire and literally we couldn't use American Express for, I think it was like 12 months after that.

[00:49:48] **Adam:** Wow.

[00:49:52] **Tim:** Hopefully there wasn't a whole bunch of descriptions tied to

[00:49:54] **Ben:** Oh, we were running the business on American Express,

[00:49:57] **Tim:** Oh, no.

[00:49:59] **Adam:** Wow. That's a horror

[00:50:02] **Ben:** to, to that. So ever since then I've, I've been extremely afraid of ever refunding something on a card that is somehow related to the business.

[00:50:11] **Adam:** Do you listen to syntax?

[00:50:13] **Ben:** Oh, yeah, of course.

[00:50:14] **Adam:** you know, like every year around Halloween they do their like spooky stories. You should submit that one.

[00:50:19] **Ben:** Oh, that's a good one actually. I should totally do that.

[00:50:22] **Tim:** that's funny.

[00:50:23] **Ben:** Anyway, Tim, what's going on with Tim?

[00:50:25] **Tim:**

## [00:50:25] Dealing With REST API Errors

[00:50:25] **Tim:** All right, so I got one, and Adam can probably answer this pretty easily for me. So I've just been thinking about how to deal with errors in arrest api. I've seen that some of the API's been using lately where they will, they will give you a status code, although it's, I, I guess it's not really the, it's not really a hard

[00:50:48] **Ben:** I want to interject for a second just to paint the context more. Are you talking about as an API producer or an API consumer.

[00:50:56] **Tim:** So I'm looking at it from the, the consumer side, but I'm building it, right? So I wanna know what sort of errors I should give to people. So, for instance, they ask for, Some, like, so in our, our context, it's an insurance policy and they put a policy number in, the policy number doesn't exist. How do you tell them that that doesn't exist?

[00:51:16] **Tim:** I've seen some where it does come back with a 200 Okay. Return, but the return is either empty or there's like zero records, or some will give you a 4 0 4 or some, some sort of 400 error to say, you know, this doesn't exist, and then you gotta deal with the status code and stuff like that. So is there a preferred way on that?

[00:51:35] **Tim:** So this was totally not a, a pre-planned, plant or anything, but somebody should write a book on this. know you have.

[00:51:43] **Adam:** yeah. so, yes. anything, well, it's complicated. It depends. There's your answer. but, no, I mean, if, so you're writing an api, you're targeting developers, right. And, I guess it kind of depends on how your API is structured.

[00:51:59] **Adam:** If you are thinking about the API as a collection of records that they can interact with, and they're saying like, I want the detail of this insurance policy, then. 4 0 4 is the correct, idiomatic way to say that policy doesn't exist to return 200 with zero response is saying, here is the policy that you requested.

[00:52:23] **Adam:** It just happens to be empty,

[00:52:25] **Tim:** Mm-hmm.

[00:52:25] **Ben:** which are kind of different things. It's like, know how ColdFusion can't tell the difference between null and empty string and a query result? You know, like they're different things to different people. One thing that I think I didn't really understand till I was like halfway through my career is that a non successful response code could still contain a response body.

[00:52:48] **Adam:** yes.

[00:52:49] **Ben:** And that, that, for whatever reason, when I had that insight, I'm like, oh, just because it's not a 200 doesn't mean I can't have a fully formed j s o response or whatever format you happen to be using.

[00:53:00] **Adam:** Yeah. And.

[00:53:01] **Ben:** had that insight, I was like, oh, okay. I can really play now with how I want to deliver data back to

[00:53:07] **Adam:** Right. And, and early on in my career, I was very heavily using, iis. I hate saying that because it's hard to

[00:53:14] **Ben:** The, the window server.

[00:53:16] **Adam:** yeah. The windows, server

[00:53:17] **Tim:** in internet information server.

[00:53:20] **Adam:** or Yeah, yeah. Service or something like that. Yeah. yes. and I think by default, at least way back in the day when I was using Windows servers, the default was like if you had certain error codes, like anything in the 500 space and maybe even like 4 0 4, if you set that status code, it would ignore the body that you, the response body that you provided and it would provide its own like, you know, boiler plate, this page not found sort of thing.

[00:53:48] **Adam:** And that drove me nuts. And there was a way to turn it off, like with web dot config and, and stuff. But, yes, you are absolutely right. Probably

[00:53:57] **Tim:** And, and so, and, and that's sort of why I leaned against sending a 404 0 4 error because I, I've seen it show up. Like for instance, like fusion reactor logs. Anytime you hit a 4 0 4, it shows up in your logs. And I didn't want to generate all these logs. Anytime like a non 200 shows up, it shows up in some sort of air log somewhere.

[00:54:19] **Adam:** That's fusion reactor's fault, not the api. Don't, don't build bad things because tools expect the wrong thing.

[00:54:25] **Tim:** Right. But I mean that's sort of why I leaned against it. And then also I wanted to, and, and I didn't realize, like Ben said, that you could have the body with the error. Cuz I do didn't wanna give some context. I hate it when I get some sort of 4 0 4 error and I don't know if I just typed the URL wrong or if it didn't find, so having the, a body in there to say, you know, the

[00:54:44] **Adam:** This insurance policy doesn't exist. Yeah.

[00:54:46] **Tim:** right, the policy number you, you supplied cannot be found, please, you know, check your, you know, some sort of, I like to have some sort of context to the user, to the developer to say, yes, this is not there, but it's not because you wrote something bad, it's because it just doesn't exist.

[00:55:01] **Tim:** So.

[00:55:02] **Adam:** I was supposed to be a one. yeah, totally agree. I, when you said error handling, I thought you were talking about exceptions, but you're talking about logical errors.

[00:55:12] **Tim:** Correct.

[00:55:13] **Adam:** Okay.

[00:55:14] **Tim:** that's

[00:55:14] **Ben:** Well, here, here, here's another thing that I. I think maybe I differ when it comes to other people with how they want to handle errors, which is that I think part of this is because to some degree it's the easy way and I like the easy way, which is that I want to blow up and short circuit the request the first time anything goes wrong.

[00:55:38] **Ben:** And, and the example would be like if someone has to fill out a long form and they have to put their name and their apartment number and their street, and their city and their zip code and they submit that if they don't have their name, it's required. I wanna stop processing immediately and say, Nope, you need to gimme your name.

[00:55:58] **Ben:** whereas I think some people wanna be able to return a response that says, I need your name and your apartment number and your street address, and your city and your zip code, and. I, I want to give like, just the one most important failure at a time. I don't, I don't feel a need to coalesce a bunch of errors in one way or in one response.

[00:56:21] **Ben:** I think if you're creating a client side experience, you can handle things like that more on the client side and not worry about handling it in the api. I like the API to have one very specific reason for failing.

[00:56:34] **Adam:** I would do it the other way personally. I would, I would return an array of errors. And, and for me it's about, the feedback loop, right? So you're submitting a form with 50 fields on it and you don't know it, but there's 20 errors in that form and so you have to hit submit 20 different times, whereas if you to, to fix those each individually as you get a single error response.

[00:56:56] **Adam:** Whereas if you. You have all the data to look at it and you say, okay, well here are the 20 things that are wrong in your form. you know, that you can highlight each of those form fields and, and draw attention to them. So that's, that's the way I look at it.

[00:57:12] **Ben:** I, I, I can't disagree. You know, my only, again, I think a big part of it is because it's literally just easier to blow up at the first sign of a problem and say, Nope, I can't process.

[00:57:24] **Adam:** So this, this actually reminds me of something that was very controversial, in these spelt kit 1.0 changes. I think it was in 1.0, it might have been slightly earlier in the like pre 1.0 beta stuff. But, so obviously spelt kit is the like, as they call them now, meta framework around spelt for building like a whole say monolithic app, right?

[00:57:46] **Adam:** Lots of pages, lots of, client server interactions and basically, They use throw for more things than just throwing errors. If you want to redirect, like you wanna say, okay, you're, you tried to get to a page, but you have to be logged in to get here. That's a throw. You throw a redirect.

[00:58:07] **Ben:** Interesting.

[00:58:08] **Adam:** And, and I think a lot of people got really upset with that because throw is always an error.

[00:58:12] **Adam:** Everything you throw would, would always be an error. And historically that's probably mostly true. But when you think about it, what does throw do? It stops all execution of the current function and, and takes you all the way back up to whatever your, you know, current contextual, error handler is, right?

[00:58:34] **Adam:** So if you're, if you're wrapped in a tri catch, then it's gonna do that. But if you're not, then you know, wherever up the stack, that error handling is, kicks in. And I really like that. I think it's really smart.

[00:58:47] **Ben:** Well, and it, it, it's such an interesting thing that you bring that up because it, it almost feels like it's a, an issue of abstraction because

[00:58:54] **Adam:** It's a naming issue, right? Throw is not like throw is, it's called throw because you think about throwing an error, but yeah.

[00:58:59] **Ben:** in ColdFusion, which obviously is all of our favorite languages, the. The, the CF location tag or the location function halts all processing and sends down a response with a location header, HDP header.

[00:59:15] **Ben:** But I remember there was, I think it was like ColdFusion, eight or nine, suddenly they made a change where when you did a location, you started getting abort errors in the global error handler. And you're like, oh yeah, that's because it's, it's doing exactly what you're saying. It's a boarding out of the request, which is technically a problem, you know, like something didn't go right.

[00:59:33] **Ben:** And, and, but we called it location. We didn't call it throw. And so it's fine, you know, if you call it throw, it just feels weird.

[00:59:40] **Tim:** it never gets to the on request end

[00:59:42] **Ben:** Yeah. They

[00:59:43] **Tim:** you do

[00:59:44] **Adam:** Didn't they add, I mean, this is not CFM L hour, but, didn't they add like a, a, an abort attribute or something like that to the, to the redirect tag?

[00:59:54] **Ben:** added a, an abort to the CF dump tag.

[00:59:58] **Adam:** Well, I'm thinking like a way to prevent the abort from happening when you're doing a redirect or maybe,

[01:00:03] **Ben:** think they don't do it anymore. I think it was like for one or two versions of the language, and then I think they removed it. Maybe

[01:00:10] **Adam:** Or maybe it was like on the handling side, like there was some way to like know that this was a redirect based aboard or something. I don't know. There was some, some relationship between the two beyond just the fact that it happened, but okay, it doesn't matter. That's enough. CFM

[01:00:24] **Tim:** that that was it. That, that was a pretty, that was a pretty simple question. It wasn't, wasn't a whole lot. I'll, I won't go into the other one since we were at an hour so.

## [01:00:31] Patreon

[01:00:31] **Adam:** Okay, then I guess this episode Working Code is brought to you by wanting to be a park ranger in your twenties. Listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this was out into the universe, then you should consider supporting us on Patreon.

[01:00:46] **Adam:** Our patrons cover our recording and editing costs, and we couldn't do this every week without them. Special

[01:00:52] **Adam:** Special thanks of course, to our top patrons, Monte and Giancarlo. You guys rock. If you would like to help us out, you can go to patreon.com/WorkingCodePod.

[01:01:01] **Adam:** All of our patrons get early access to new episodes and our after show. What is the after show you say? It is after?

[01:01:09] **Tim:** the after show?

[01:01:10] **Adam:** It is after the outro music is done. We are just gonna keep talking. and. And you get to listen to that. That's, that's all we're, and, and it's kind of, sometimes it's more of the same.

[01:01:21] **Adam:** Sometimes it's, we're gonna talk about food or, you know, whatever. What kind of testicles is Tim eating this week?

[01:01:30] **Ben:** It's always funny.

[01:01:33] **Adam:** Uh,so that's it. you know,

## [01:01:35] Thanks For Listening!

[01:01:35] **Adam:** here's your homework for this week. it's been a little while, so I'm gonna go ahead and ask you to leave us a review. You can go to workingcode.dev/review and you will be directed to your local, apple Podcasts, your local independent Apple Podcast store.

[01:01:49] **Adam:** and you can, leave us a review there and we would greatly appreciate it. Apparently, supposedly that's supposed to be good for helping people discover the show. We've continued to grow, which is great. our numbers keep going up. I'm loving it. I appreciate all of you guys, spreading the word. So, that's gonna do it for us this week.

[01:02:04] **Adam:** We'll catch you next week. Until then,

[01:02:05] **Tim:** Remember guys, your heart matters even if you're a 20 year old park ranger
