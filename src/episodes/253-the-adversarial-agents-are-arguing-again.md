---
title: "253: The Adversarial Agents Are Arguing Again"
description: "What if the best way to get good work out of AI is to stop being nice to it? Adam and Tim have been pitting agents against each other, and the results are uncomfortably better."
date: 2026-03-26
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/253-the-adversarial-agents-are-arguing-again/id1544142288?i=1000757485922"></iframe>

What if the best way to get good work out of AI is to stop being nice to it? Adam and Tim have both landed on the same uncomfortable discovery: when you pit AI agents against each other, with fake points, opposing incentives, and competing models, the output gets dramatically better than anything a single polite prompt can produce.

Adam's bug-hunting pipeline hands fake rewards to sycophantic agents and then throws the scores in the trash. Tim made Claude and ChatGPT argue for twelve rounds straight until they both said "ship it".

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Thursday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/253-the-adversarial-agents-are-arguing-again.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Adam:** anytime that it stops and like is requesting tool use or, or asking me a question or whatever, it, sends me a message. the icon for the Discord server is Ralph Wiggum from The Simpsons.

[00:00:10] **Adam:** And the message is just, father, I need you in all caps.

[00:00:15]

## [00:00:35] Intro

[00:00:35] **Adam:** Okay, here we go. It is show number 253 and on today's show the adversarial agents are arguing again, Al iteratively. Um,but first as usual, we'll start with our tris and fails Carol's on vacation this week. Go, Carol. Good for you. so it's just the boys. and Tim, it is your turn to go first, my friend.

[00:00:52] **Adam:** What's going on?

## [00:00:53] Tim's Triumph

[00:00:53] **Tim:** Well, I'm gonna go with a massive triumph applause.

[00:00:57] **Ben:** Yes. Yes. Congratulations.

[00:00:59] **Adam:** Pause for applause. Go ahead.

[00:01:01] **Tim:** yeah. So I, I think I mentioned earlier that, tonight, this past weekend, Saturday was our ninth annual Wild Game dinner. Where we eat weird foods and you know, always have a testicle course.

[00:01:15] **Ben:** Mm-hmm.

[00:01:16] **Tim:** it went really, really well. So we have it, it's at a country club up in, river North Macon, Georgia. And my boss, ex-boss, the guy started the company I work at, he owns it and got to work.

[00:01:28] **Tim:** I had three chefs working with me, which was a blessing because the whole issues with my eyeballs the past several weeks has really prevented me from being super, super prepared like I normally am. So they were able to help out a lot. In fact, actually I didn't really wind up having to, at the restaurant do much cooking at all that I just told them what to do.

[00:01:49] **Tim:** So I felt like a real executive chef.

[00:01:51] **Ben:** Nice.

[00:01:52] **Tim:** So that was

[00:01:52] **Ben:** Regular Gordon Ramsay.

[00:01:54] **Tim:** That's right. Although I

[00:01:55] **Adam:** you call anybody a donkey or,

[00:01:56] **Tim:** did not, I didn't curse at anybody or call anybody any names. So, so the main courses, it got a little fancy this year. It got a little bit

[00:02:05] **Adam:** oh my God, the pictures.

[00:02:07] **Tim:** Yeah. So in the pictures you'll see that I generated a, a menu, but also I, all the dishes, I gotta put 'em in our Triumphs and Fail channel on Discord, if you wanna see those pictures.

[00:02:18] **Tim:** But, the first course was, like a oyster course, which one of the guys who comes every year, he owns a restaurant, or actually it's a wine merchant that has a little restaurant in it, like for only like five tables. But he had like some really good, like, some of the best oysters I've ever had in my life.

[00:02:34] **Tim:** and the next course was the, quiche. So the one ostrich egg made, five, it was five quiche pies.

[00:02:45] **Ben:** Holy cow.

[00:02:46] **Tim:** dish. Just one. Just one. Single one. And I had, I had some egg custard left over. So that was good. And then

[00:02:53] **Ben:** Yeah, these pictures are great. I hadn't seen these before.

[00:02:57] **Tim:** Yeah. So why, why don't, so rather than me monologuing, why don't you guys ask me about

[00:03:01] **Adam:** Yeah. So first of all, as Ben said, these pictures are freaking amazing. You said you had three chefs did, I mean, I'm guessing not to, not to besmirch your good name, sir, but I, I'm guessing this beautiful plating was not necessarily your doing, it was like these professional chefs.

[00:03:16] **Tim:** I showed them how to do it. They, they, okay. So they, they are professional chefs, but actually I would call them more cooks. So they, a country club. Country club does not have like a fine dining sit down. It's like golfers doing sandwiches, they're doing wings, right? So they're this, they actually really look forward to it every time I talk to them.

[00:03:34] **Adam:** When, when we were planning like, man, I can't wait. This is gonna be, so they really enjoy it too. 'cause they could do stuff outside their comfort zone. So, they're good cooks, but they're not, definitely not chefs. Well, I wanted to kind of follow that up with, was there like a fourth person who's a professional food photographer? 'cause these are bananas. Good pictures.

[00:03:51] **Tim:** so one of the, servers, was a, also is like on the side of professional photographer. So she set up, she set up a special lighting area to take the pictures.

[00:04:03] **Ben:** Nice.

[00:04:04] **Tim:** So that was pretty cool.

[00:04:06] **Ben:** Yeah. So it looks like as someone who doesn't know anything about food, I see these are oysters.

[00:04:12] **Tim:** Yep. Those are oysters that are

[00:04:13] **Ben:** Oysters, but it, the, the, the very cool thing is like the on the plate I'm describing for the listener here, the, the, it's like a flower petals, and three of the flower petals are oysters. And then three are, I'm assuming like homemade, chips.

[00:04:28] **Tim:** yeah, it's a truffle chip.

[00:04:29] **Ben:** A truffle chip with a roe. And what's the white stuff?

[00:04:34] **Tim:** It's, uh, crème fraîche. So it's basically fancy sour cream. Yeah, that, and that was a really nice, expensive caviar too. So we had caviar and crème fraîche on a truffle chip. And then, so you eat the, uh, oyster, and then you chase it down with the chip

[00:04:49] **Ben:** very cool. And then the quiche is, it has a dollop of some sort of cream and like a little bit of a little hint of bacon and

[00:04:59] **Tim:** it's a little bacon. Little bacon

[00:05:00] **Adam:** is that

[00:05:01] **Tim:** in it. Yeah, it's a little, little shard of bacon. And then three little chive sprigs sticking out of it. So it was quiche Lorraine, so that's, uh, Gruyere cheese, bacon and onion, and the ostrich egg all mixed together and then baked in a pie. So that, that was, that was extremely good.

[00:05:18] **Ben:** Oh, quiche is great.

[00:05:20] **Adam:** so let me interrupt real quick. The, the menu here, the ostrich egg, like how does it taste wise? How does that compare to like a chicken egg,

[00:05:27] **Tim:** it? I mean, it's a little richer, but I think that's maybe psychological,

[00:05:34] **Adam:** right?

[00:05:34] **Tim:** know what I mean? Because I

[00:05:35] **Adam:** just expecting to be different.

[00:05:37] **Tim:** Right. You're like, it is an ostrich egg and you taste it and you just, you expect something different. So you get something different. I don't think, I don't think in a quiche, you, you know, if I did one egg, regular egg and regular at an ostrich, you wouldn't be able to tell the difference between the two.

[00:05:50] **Tim:** Honestly, that it's the cheese. It's the cheese that does all the heavy lifting

[00:05:53] **Ben:** I was gonna say next, it looks almost like, like a pasta carbonara, which

[00:05:59] **Adam:** with nuts on top.

[00:06:01] **Ben:** yeah, with some. This is the uni on top.

[00:06:03] **Tim:** That's, that's the uni, so that's sea urchin roe. So sea urchin, those big like balls of spikiness that live in the ocean. you cut those open and there's this, orange stuff in there and people call it the roe, but it's actually the gonads are the testicles of, of the animal type. So I made, so I made a, a cream sauce that had uni in it.

[00:06:28] **Tim:** So half the uni went in the sauce and you mixed it up and gave it a nice oceany. Uni tastes kind of like similar to an oyster, but little, I mean, the texture's really nice. And then I put three or four pieces of uni on top with some chives on top, and then some chive oil, that green stuff on the plates of chive oil.

[00:06:46] **Ben:** The, the people who come to this event, is it a collection of people who are basically down for whatever? I mean, are there anybody who's like hard pass?

[00:06:54] **Tim:** Well, there's one guy, he, we who, he works with us. His name's Mike. And, and I think he just comes for the, for the camaraderie and the, and the alcohol. But, he, he, he's not a pick, you

[00:07:06] **Adam:** an adventurous

[00:07:07] **Tim:** in fact, he actually showed up, hung out with the guys beforehand. 'cause they like, they come at like four and they smoke cigars and hang out and catch up and he left at dinner.

[00:07:16] **Tim:** He's just, I'm not feeling good. And I, I, I know the real reason. He just didn't want to, he didn't want to eat it. He would the other, when he would come to the dinner when he was at my boss's house, he would eat beforehand and then, but, and then sometimes he'd take a taste and go, man, that's really good. I wish it wasn't, wish it wasn't a bowl. So, but yeah, the rest of the guys are all down for whatever.

[00:07:38] **Ben:** Very cool.and then you have your scotch egg right

[00:07:42] **Tim:** Yep. Scotch egg.

[00:07:43] **Adam:** so this looks like it's almost a hundred percent yolk. Is that

[00:07:48] **Ben:** of yolk.

[00:07:49] **Tim:** That's, that's the, that's the fail here. So I, I tried to, test her at home like a few weeks ago. It was complete failure. It just fell apart. And then, at the restaurant, I had boiled this thing, this egg for like two and a half hours on, on high. And for some reason the, the yolk was perfect, but the, the whites just weren't done.

[00:08:13] **Adam:** Hmm. Like a little too slimy or

[00:08:15] **Tim:** yeah, a little was slimy. And they basically, when I tried to wrap it in the sausage, it just, they fell apart. Absolutely. Just so I just, I said, you know what? The yolks the best part. Anyway, so I just, and even, even then, the, the yolk was really about the size of a, of a softball. So it fed every, it fed everybody.

[00:08:34] **Ben:** sliced the yolk into a bunch of littler compartments and then you made the scotch egg from the parts.

[00:08:41] **Tim:** no, no. So I basically took the yolk, came out whole, and I just breaded it, wrapped it in sausage, rolled it in Panko breadcrumbs, deep fried it, and then cooked it in the oven for a bit, and then sliced it, then sliced it

[00:08:53] **Ben:** was your, okay. My understanding of a scotch egg, and maybe it's wrong, is it's a hard boiled egg that then is itself wrapped, you know, peeled and then wrapped and baked in a sausage, and then breaded more or less.

[00:09:06] **Tim:** Is that what I said?

[00:09:07] **Ben:** I, I think, I think we mentioned that the last time. was your intention to make a ostrich egg sized scotched egg?

[00:09:15] **Tim:** Yes. Mm-hmm.

[00:09:17] **Ben:** moly. Yeah, that would've been bonkers.

[00:09:19] **Tim:** Yeah. I, so, I mean the, the, when I did try to wrap it. I found a bowl that was about the size of what I wanted wrapped, wrapped the whole, the entire egg. And the white sausage is probably about four pounds of sausage on it, and then shoved it in the bowl to see if it'd stay together. And we cooked it in that, and it just, it, it didn't stay together and it, but it was massive.

[00:09:40] **Tim:** It, I mean, it, it was much bigger than a basketball.

[00:09:44] **Adam:** Wow.

[00:09:45] **Ben:** Oh my good. Okay. Then maybe I'm not getting the size because there's no, uhoh, I guess the next photo there is someone holding a tray with the scotch egg. So it is pretty big. It is like the size of a softball.

[00:09:55] **Tim:** yeah. So if the whites were on that, it'd be more than double, probably almost three times bigger than that, and almost took up the entire, sheet pan.

[00:10:05] **Ben:** bonkers.

[00:10:06] **Tim:** And then the, the last meal dish was shark, mako shark. And it

[00:10:11] **Adam:** Oh, okay. I was

[00:10:11] **Tim:** Abs absolutely delicious and it's, it's cheaper than swordfish, but it's, it's just as good if not better than swordfish.so I highly recommend if you can get a hold of, mako shark in particular. That's really good.

[00:10:24] **Tim:** And then lastly, I made, I made ice cream out of one of the eggs. and so you can see that there, it's a little puck of ice cream. I got those little, little, little white tubs.

[00:10:33] **Ben:** I thought that was like a little cheesecake.

[00:10:35] **Tim:** No, it's, it's, it's, it's vanilla ostrich ice cream. And it made, it made, 12 more than 12 pints of ice.

[00:10:43] **Adam:** 12 pints. Jesus.

[00:10:45] **Tim:** Yeah.

[00:10:45] **Tim:** One egg. And, and so I had, I had bought 50 little of those little paper cups. It filled all 50 of them up. So I have some at home, I left some at the restaurant. My, 'cause my daughter, my daughter works at that country club now, so she, she works there. So I told her, I was like, there are two extra quiches in there and there's ice cream.

[00:11:04] **Tim:** You can eat all of it. So that's her lunch for the next few next week.

[00:11:09] **Adam:** For the next month. Yeah.

[00:11:10] **Tim:** Yeah. But it went really good. Every, everyone was super pleased. And next year is the 10th anniversary, so we're like, what are we gonna do? And so next year we're gonna go back to our greatest hits and I'll talk about that on another show.

[00:11:19] **Adam:** Oops. All testicles.

[00:11:21] **Tim:** May. Jokingly, jokingly, one of the guys, whose wife works with us, he was there. He is like, maybe you should just have every course be testicles.

[00:11:31] **Adam:** These are long pig testicles.

[00:11:33] **Tim:** Yep.

[00:11:35] **Ben:** cool

[00:11:35] **Tim:** kept, I got the joke.

[00:11:38] **Adam:** that was, I wish I could've been there. It looks like it would've been like fun.

[00:11:41] **Tim:** Yeah. I mean, if any of you guys wanna come, it's, it's

[00:11:44] **Adam:** a long way to drive for, uh, an expensive dinner.

[00:11:46] **Ben:** is way too out there for me. I'm sorry.

[00:11:49] **Tim:** I know Ben. I, I, I knew I was safe inviting you. You wouldn't come.

[00:11:55] **Ben:** Oh man,

[00:11:56] **Tim:** Anyway, that's me. How about you, Adam?

## [00:11:58] Adam's Fail

[00:11:58] **Adam:** Well, I'm gonna go with a big old fat nasty fail. Um,so you guys are familiar,probably at least in name with John Mayer and his song, what is it, your Body? No. Yeah, your Body is a Wonderland. Yeah. Yeah. My body is not a wonderland. My body is a, my body is a dumpster fire. Um,so we're recording this, like maybe three quarters of the way through March.

[00:12:21] **Adam:** so, like March 24th is the date. While we're recording this on January 20th, was the, the best approximation of when I started having this round of health issues. I had a sinus infection. and I've, I've done three different rounds of antibiotics and steroids to get rid of it. I think it might finally be gone.

[00:12:42] **Adam:** I still have like other sort of related, it seems sinus issues. But the sinus infection itself seems to be gone. my iritis is back. I don't know. I'm pretty sure I talked about iritis on the show before. It's like inflammation of the iris in your eye and left untreated. You can go blind from that. So I'm,

[00:13:00] **Tim:** So two. So two Outta three Working Code Podcast Hosts on this show have eye problems.

[00:13:05] **Ben:** Oh no.

[00:13:06] **Adam:** Yeah. And then just sort of in addition to all of that, I think, you know, probably, it, who knows, it could have been a preexisting thing or maybe these other conditions have exacerbated my systemic inflammation. It's, it's like a chicken and egg problem. Who came first? I don't know. But my systemic inflammation is just sort of off the charts I've been.

[00:13:27] **Adam:** Spending pretty much all day and all night using heating pads on different parts of my body. Like I sleep on a heating pad, like, it's like for an hour, it'll be like my left shoulder blade that's in extreme pain. And then for a while it's like my right shoulder blade and then it's my lower back and then, you know, whatever, it goes all over the place.

[00:13:43] **Adam:** I just, I'm falling apart, man. I wish

[00:13:46] **Tim:** to the club.

[00:13:47] **Adam:** Yeah. This is a,

[00:13:49] **Tim:** you hit your fifties yet, dude,

[00:13:51] **Adam:** no, I have not, thankfully. I, and to be honest, it makes me worried about what life is gonna be like in my fifties and in my eighties and, you know, I, I hope I make it that far, but man, I'm, I'm worried. And that's honestly a big part of like why I work out so hard these days and stuff.

[00:14:07] **Adam:** Speaking of working out. Because of this adjusters to all of me. and, and then in addition to those things that I mentioned, I've also been battling some shoulder pain. I'm not sure if I like, exacerbated something from working out or if this is just like an underlying thing that, you know, is getting slightly worse or whatever.

[00:14:24] **Adam:** But I've just been being very careful to not push myself so hard that I actually injure myself. But I do have some shoulder pain going on. So like between the iritis, which just started on like Saturday and, and all this other stuff going on, I'm like, okay, I need to slow things down and cool the tempo a bit.

[00:14:44] **Adam:** So I'm taking this week off from exercise. I'll probably do like more dog walking and stuff than usual, but on the, the weightlifting side, definitely taking a break. So yeah, I'm just, you know, existence is suffering and,

[00:15:00] **Ben:** I was saying to my wife the other day, I was like, if I have to think honestly, when's the last time I went through a good long period where nothing hurt. I feel like I was 20 then like since then, just one thing or another has sort of had a kind of a, you know, nothing's been terrible, but just like a chronic, like, oh, my knee hurts or my thumb hurts for some reason, or shoulder pain persists for months.

[00:15:26] **Ben:** The human body, it's both simultaneously amazing and also ridiculous. It's just like, who designed this? It's, it's, it's crazy. We're just held together by these little ligaments.

[00:15:43] **Tim:** Yeah, that's what, when I went to the doctor, he showed me like a time lapse. Every time I've been to the doctor, he showed me a time lapse of. Basically my macula, which is like the center part of your vision a little, it's almost like a cord. And he just showed it. It's like the body just, just took, was taking slowly that it was a bis bis, big rip.

[00:16:02] **Tim:** And the macula was kind of drifting and it just reattached and connected and it just showed it. I'm like, that is nuts. It

[00:16:09] **Adam:** So it's a time-lapse of your eye. The, the detached retina healing.

[00:16:12] **Tim:** right, but, but particularly the macula, which was really, yeah. So yeah, bodies are amazing. But yeah, something has to be real jerks.

[00:16:19] **Adam:** Yeah. So that's what's, uh, keeping me awake at night. What do you got going on, Ben?

## [00:16:24] Ben's Fail

[00:16:24] **Ben:** Well, I'm gonna go with the fum and I'm gonna unfortunately bring it back into the technical world here after your, exciting food and body adventures.my fum is that in my effort to try to be. More immersive in the AI world. I've been trying to watch some videos on it and take some Udemy courses and, and just try to get better in some way.

[00:16:48] **Ben:** And the other weekend I had. Here. Two four really only had CLAUDE.md files, which is the kind of Agent MD standard where you put a whole bunch of stuff into this file and it gets read into the context window on every command to prime the engines. And then, I was, I don't know if this was Aaron Francis' Faster dev course or if this was something I saw on, YouTube, I don't remember, but someone said, oh, you can do rules now.

[00:17:15] **Ben:** And rule is essentially a mini CLAUDE.md file, so to speak, that is scope to a file type patterns. You could say this, this rule, but only applies to dot ts files or only applies to CFC files. So I thought, oh, okay. That's gonna be great. I'll put it all into there and then I'll shrink my context window and I should hopefully, try to avoid the, uh, the dumb zone.

[00:17:39] **Ben:** sooner or, or, you know, more effectively. And, um, I found that everything got worse. Claude just started to make a lot more mistakes and I, I had asked, uh, you know, as part of when I was deciding whether or not to do this, I was asking, you know, why is this good or why is this bad? And it was saying that having the rule-based metadata files, the markdown files is good because it keeps the context windows smaller, but it's bad because it only works for existing files.

[00:18:09] **Ben:** So if you're gonna read and edit. A CFC, great. If you're gonna create a new CFC, there's no file type to glob onto, so it doesn't know how to load that rule. And I think that's what was happening is I was ending up creating, as much as a lot of my work is editing files, a lot of it is also creating new files.

[00:18:29] **Ben:** And it was just missing a tremendous amount of context. So I actually went and I reverted that entire thing, got rid of all my rules and moved them all back into CLAUDE.md and the, the kind of the triumphing part of the fum here is I feel like I was maybe trying to be too proactive. You know, kind of like a reading the, the Gang of four Design patterns book and then realizing, oh, I've got all these patterns, I can now start applying immediately and not realizing that the patterns are there to solve problems.

[00:18:57] **Ben:** But I don't actually know if I have those problems yet. So I'm back to just put everything in CLAUDE.md and when I hit a problem, that's when I can start to think what are the tools I have available? To solve that problem. Otherwise, I feel like I'm just taking shots in the dark and I have no idea if I'm doing anything that's even relevant.

[00:19:20] **Adam:** How big is your CLAUDE.md file?

[00:19:22] **Ben:** I will

[00:19:23] **Tim:** That's a very personal question.

[00:19:27] **Ben:** let's see. So this is, this is all for big sexy poems and the CLAUDE.md file. It's not huge. It's 464 lines. Is that big?

[00:19:38] **Adam:** that's pretty big. I mean, I've seen worse. I've seen

[00:19:42] **Ben:** what can I say?

[00:19:46] **Adam:** so let me tell you, so for, for my CF ORM migration branch, I have a, a CLAUDE.md specific to this branch. And like I will delete the file before I merge my branch into Main, right?and basically I started with an empty, call it empty file. And then what I do is like, I add stuff to it, when I get tired of repeating myself, like, stop doing this, stop doing that.

[00:20:14] **Adam:** including, so, as we're gonna get into in the show, show topic today, including some stuff I've just added in the last couple of days. that are gonna, that help with some of the automation that I've just started doing. it's up to 38 lines, if you include the blank line at the end of the file.

[00:20:30] **Ben:** So it's an order of magnitude difference.

[00:20:32] **Adam:** Yes.

[00:20:33] **Ben:** okay. I started out with just the /init command and I think.

[00:20:37] **Adam:** Ooh,

[00:20:38] **Ben:** it probably

[00:20:39] **Adam:** number one.

[00:20:40] **Ben:** it, I think it immediately gave me something that was like a hundred lines. And then I went in and I said, okay, I understand the architecture of the application. Here's where all of my data access stuff works.

[00:20:51] **Ben:** Here's how my view components work. My view components kind of have, uh, these like co-location of several different types of files and like, here's how the services work and here's how permissions work. So I tried to give it all the things that it would need from a patterns perspective. And it, and it honestly has been doing pretty well.

[00:21:10] **Ben:** it, it does mess up things like I have notes in my CLAUDE.md file for how it should alphabetize the methods within a component. And that's one of those things where it gets it right 90% of the time and then 10% of the time it'll just throw a method at the very end.

[00:21:26] **Tim:** You mean like the casing?

[00:21:27] **Ben:** Like, I like to have things, in alphabetical order.

[00:21:30] **Tim:** Oh, okay. So you can find him.

[00:21:32] **Ben:** So it's, it's pretty good. But then I'll, I'll watch videos by, what's his name? Is it Matt Pocock? Something like

[00:21:40] **Adam:** Matt Pocock. Yeah.

[00:21:41] **Ben:** And he's, he's like a one line CLAUDE.md file kind of guy. but like, here's the thing is I don't think that my big CLAUDE.md file is ruining anything. I don't think it's getting worse.

[00:21:55] **Ben:** You know, it's like, that's, that's what I'm saying. I want to be

[00:21:57] **Tim:** It's like, it's like your security blanket. You're like, I know it's there. If it, it might help.

[00:22:03] **Ben:** I know it's because he keeps talking about in his videos that you shouldn't have to give it anything that it can really easily identify from existing code as far as patterns go. And I mean, maybe I can try to just delete a lot of this stuff and see what happens. but I'm not, I don't know. And that, but again, like that's the, am I, am I just gonna be, am I being too proactive?

[00:22:24] **Ben:** Like I don't have pain points yet.

[00:22:26] **Tim:** yeah, I don't know. 'cause it's like, one thing I've noticed is that, I really wanted Claude to use like good patterns, like provider, like a provider pattern. 'cause one thing that happens is you start working and then you realize it isn't building quite what you want and it's gotta go do a whole bunch of recoding.

[00:22:43] **Tim:** 'cause it's, it's, it hasn't created something that's in that, it doesn't automatically build interfaces for you out of the gate. So I put in all of mine, here are the patterns that I, that I want you to follow for this project. And so for the one I'm gonna talk about. In the shows, I used the provider pattern in case I wanted to switch something.

[00:23:02] **Tim:** And sure enough, it gotta the point where I, I'm like, I don't want to use, this service. I wanna swap it out for another service.

[00:23:09] **Tim:** Yeah, it's tough and I, it's one of these things, this is the really challenging part about deterministic versus non-deterministic. I. In a deterministic world, I could have a theory and change something and test that theory, and you can more or less say, this worked or it didn't work. But with something like this where it's so fuzzy and so non-deterministic, you know, I can make a bunch of changes and then I try something small and it seems to work, and then I try something bigger and it totally falls on its face.

[00:23:41] **Ben:** And I'm not saying that would happen. I'm just saying there's so many facets. It's so hard to know what to do. Like, I wanna be, I wanna be a little bit more cutting edge, you know, I wanna wear Adam's skin a little bit more, but, uh I'm nervous

[00:23:58] **Adam:** with some fava beans?

[00:23:59] **Tim:** Some fava beans.

[00:24:00] **Ben:** and a nice Chianti.

[00:24:02] **Tim:** Well, well, maybe Adam and I could tell you about some adversarial AI stuff that

[00:24:06] **Ben:** Please do.

## [00:24:08] Adversarial AI Agent Loops

[00:24:08] **Adam:** Okay. Well, so as I discussed in the opening, we've, Tim and I both have been getting into kind of, adversarial, age agentic loop type stuff. basically having multiple. Competing agents running with different prompts or, or take the output of one and feed it into as an input to another and try and get them to kind of pit against each other to improve the end result.

[00:24:32] **Adam:** Right. You're not just saying argue for argument's sake, but like you start with a a, a primary input and then the, the goal is to kind of have it bounce back and forth either for however long it takes to until they agree or, like, okay. So what I did, I'll get into it a little bit here, but basically, you know, my ORM migration branch I've been working on, I had it.

## [00:24:56] Adam's Multi-Agent Bug Review Pipeline

[00:24:56] **Adam:** this is all based on something I, I think I mentioned, uh, a post on Twitter either last week or two weeks ago, about, becoming a world class agent engineer, I think was the title of it. But there's a section in there about adversarial. agent Loops and basically I had to do a code review and I said, okay, for the first one, your job is to look at this particular file like a controller in my MVC application and say like, you can read up and down the dependency tree, right?

[00:25:22] **Adam:** You can crawl, crawl up into SER services and see what they're doing and you can view the views and see what they're doing and you're just stay within this sort of vertical slice of the application and look for bugs. And I think it was like for, find whatever bugs you can find, but you get more points for finding a critical bug,

[00:25:42] **Adam:** A critical bug might be worth 10 points. A moderate bug is worth five, and a low severity bug is a single point.

[00:25:49] **Ben:** Are the agents self-reporting the severity, or is there like a managing agent that's evaluating?

[00:25:56] **Adam:** Well, the thing is you are just trying to appeal to the sycophancy of the agent. You're not like it, yes, it self-reports points, but it's more just trying to influence the way that it thinks, right? it self-report points and these other agents that I have involved are also getting different scoring, scoring criteria and self-reporting their own points, and it all just falls on the floor.

[00:26:19] **Adam:** I don't give a crap what the points are. The goal is to just kind of influence the way that they're thinking about the, their inputs. Yes, exactly. And, you know, I can't take credit for that. That was something I pulled directly from, that article I read. But yeah, it's like, okay, so the first thing is looking for bugs and it's like, you know, write a separate file for each bug you find and, you know, use this sort of template, and classify things and propose a fix and, you know, justify why you think it's a bug sort of thing.

[00:26:48] **Adam:** And then, so it's, it's writing all these, bug report files, and then I have a separate, agent that is reading those files. And its job is to judge is this actually a bug or not? And it, what it is, the way that it is incentivized is to emphasize correctness. So if, if it confirms a bug, or like, so if the finding is it is a bug, then if it confirms it, it gets that point value as well.

[00:27:18] **Adam:** But if it, confirms it and it turns out to be wrong, then it loses twice the point value, right? So if, if the, if the bug was worth 10 points and it confirmed it, it got 10 points. If it con, if it confirmed it, but it turned out to not be a bug, then it loses 20 points. So it's really, you know, I'm incentivizing it to be correct and then there's like a referee agent at the end of it.

[00:27:41] **Adam:** It says, it looks at the original finding, it looks at the, the judge, I guess is what it's called, something like that.which all of these additional agents, they just append something to the end of the file so that it's all in one place.

[00:27:52] **Tim:** and all. Are all these running on the same LLM?

[00:27:55] **Adam:** Yes. I'm, I'm just using Claude Opus for all of this, because that's what I have access to. And, and it was easy. so yeah, the, the finding bot does findings, then there's the judge determines whether or not it agrees with the finding. and then there is a referee that determines which one of them was right.

[00:28:13] **Adam:** Like it reads it, you know, just, it's kind of like a, a second double check sort of situation. And I forget what the finish him. Um,so, I don't, I don't remember where the point values were, but again, you know, it's like using the points to just kind of. pit the, like, use the, the thing, 'cause you know, the agents want to provide output that, makes us feel good, right? And so you try to give it a reason to do, to behave a specific way.

[00:28:41] **Adam:** That's the whole thing with the points. And then I have another agent at the end that it's job is to summarize the findings, spit out, you know, just a very brief, like one sentence listing of each finding that there was, and write a summary MD file in the the run folder as well. since I said, you know, I'm working vertical slices, it does make it very easy to break the application up by controllers, right?

[00:29:02] **Adam:** So there's, I don't remember how many controller files, but I just wrote a, a list of all the controller files and I have a batch, or I'm sorry, not a batch script, a bash script that, that runs in a loop, in an infinite loop. Just pulls the f the first controller out of that file and runs it through this process.

[00:29:19] **Adam:** And then, you know, so it's, it's running serial, right? Because I don't want to burn through all my credits in an hour. so I can, I can stop it at any point if it looks like I'm starting to run onto credits and I just leave it for the rest of the session. but so that has worked pretty well for me.

[00:29:33] **Adam:** I'm getting very few false negatives and very few false positives as well. They, they do happen and actually most of, I think what are false positives are like, it actually found a bunch of stuff that is bugs, but they're also bugs in the main branch.

[00:29:48] **Adam:** And I'm like, there, there were a few that were bad enough that I went and I filed pull requests against main to fix those things. 'cause I'm like, I can't just let that go. But like, I would say 90%, I'm like, you know, I, I'm marking it as not a bug 'cause I don't care for the purposes of my branch. Like, we can come back to that.

[00:30:04] **Adam:** It's not a big deal.

[00:30:05] **Ben:** Yo, I've started to play around a little bit with trying to use the dangerously bypass permissions flag.

[00:30:12] **Adam:** Mm-hmm.

[00:30:13] **Ben:** And that was one of the things that, that went down a rabbit hole Claude just found something and said, oh, this is a preexisting bug. And I didn't even, I wasn't really paying attention to what was going on, and it just said, oh, let me fix that too.

[00:30:26] **Ben:** And that ended up going down this rabbit hole for like 45 minutes fixing something. And it's one of these things, it's like, I could kill it now, but I only noticed it like 15 minutes in. I'm like, oh, it's gotta be done any moment now, so I can't kill it. And then it went on for another half an hour.

[00:30:41] **Tim:** that was an Olympic sized pool full of water that it just consumed to cool the AI.

[00:30:50] **Ben:** All right. let me try to say back just a very high level workflow, 'cause I think I missed

[00:30:54] **Adam:** Yeah. Yeah, I think that'd be really useful.

[00:30:57] **Ben:** So you're running this all in serial, so it's basically like a multi-phase operation.

[00:31:03] **Adam:** Yes,

[00:31:04] **Ben:** First pass is you say to an agent, go through this application, find as many bugs as you can for each bug, write it to a file, and estimate to your best degree the severity of this bug.

[00:31:19] **Ben:** if your evaluation of the bug turns out to be true, you get 10 points. If the evaluation of the bug turns out to be false, you lose 20 points. And that's just to prime the agent to be aggressive, but not sycophantic, sycophantic

[00:31:32] **Adam:** sycophantic. Um, so you've, you've kind of combined two steps there. the, the first agent in the, in the process is only incentivized to find things. it does, I forget exactly what the prompt is. I'd be more than happy to share it with you or, with the audience if they.

[00:31:48] **Ben:** So you do a quick pass just to find all the bugs.

[00:31:50] **Adam:** You say quick.

[00:31:51] **Ben:** Oh yeah.

[00:31:53] **Ben:** But yes. The, the first pass is just like, look for bugs. You can find as many as you can find. You get, you know, this is the point structure. So now, so now it has it, it's generated 30 markdown files, one bug per file. Okay. Then you do a phase two, which is a different agent.

[00:32:10] **Adam:** it's still in the same loop, right? So we're talking about a, a vertical slice of the application. Everything that we're gonna talk about in this loop is, considering one controller, right? MVC controller. The C, to the, the, the first agent was like, okay, here is our admin, you know, like, let's call the security controller, right?

[00:32:27] **Adam:** The one that controls user accounts and stuff like that. So look for bugs in there. Write the findings out to files. And then, so now we're talking about the second step and its job is to look at the bug reports. And report back whether it agrees with them or not, basically.

[00:32:45] **Ben:** And where is it storing that information? Is it storing that back into the file?

[00:32:48] **Adam:** Yeah. So it depends to the end of that file, its findings or its decision on the findings.

[00:32:55] **Ben:** Gotcha. And then at the end of that phase, you basically have a list of bugs that you can start to attack, or is there is, 'cause we're talking also about the adversarial stuff. Is there like another thing

[00:33:07] **Ben:** that does like a.

[00:33:09] **Adam:** yeah, the, the, there's, I guess you could say like three different agents for the adversary stuff we've talked about the first two, right? So the finding, and then there's the judge, or I forget what it's called, but and then after that there's the referee, and the referee looks at both of them and kind of decides between them, which is if they disagree, which one's right.

[00:33:29] **Adam:** or if they agree, it might be like, and they're both wrong or, or whatever, but like it, it kind of takes, so the first one is just a finding. The second one is an opportunity looking through a slightly different lens because of the incentive, the, the point structure incentivizes a different perspective.

[00:33:45] **Ben:** It it, you're basically like priming the context with a little bit different type of entropy, more or less.

[00:33:52] **Adam:** Yeah. Kind of. and then given those two outputs, you know, sometimes they're gonna agree, sometimes they're gonna disagree, sometimes they're gonna agree and be both be wrong. but then, so given both of those outputs as input, the referee then goes and looks at the code again and says, okay, well here are two opinions on this code.

[00:34:09] **Adam:** Do I agree with them or do I

[00:34:11] **Ben:** Oh, so the referee is also doing a code review to reconcile the initial and then the, the, the, the rating. Oh,

[00:34:19] **Tim:** Yeah, I was, I wasn't getting that either. Okay.

[00:34:21] **Adam:** So, and then, all of that, you know, so including the referee's opinion goes into the file. And so I've just got a collection, a very long list of these files. so that's like, okay, cool. Great. So I just did a bunch of code review should be 90 plus percent accurate on the, you know, the ultimate findings in each file, which is great.

[00:34:40] **Adam:** and so now I have all these files and, and what I've spent some time today doing is writing, a script that automates as much as possible of the review of the files and helping me to quickly and easily tell Claude what to do with them. Right? So it gives me a report and it says, or it, it explains the whole finding.

[00:35:01] **Adam:** It kind of summarizes it. Then it says, you know, do you want to ignore it, mark it as archived and, and move on? Or do you want me to fix it or do you want to ask a follow up question sort of thing. so basically I can get through it, kinda like if I just wanna ignore it. I hit a for archive, and it just moves the file, moves on to the next one, you know, starts to loop over.

[00:35:20] **Adam:** Or if I tell it to fix it, it'll write the fix and show me the git diff and then I can, mark it as accepted, at which point it'll commit it, or I can, tell that didn't work and I can leave notes in that same finding file. Like, it'll ask me, what, what notes do you have? It adds them to the finding file, reverts the, the git changes, and then runs the loop again.

[00:35:41] **Adam:** So it'll pick up the same finding file, with my new notes added and attempt to go through the process again and potentially fix that.

[00:35:48] **Ben:** Bonkers. Very fascinating.

[00:35:50] **Tim:** Very cool. I should try playing with that.

[00:35:53] **Adam:** Yeah, I'd be happy to share my script. So now, you know, Claude did most of the writing. I kind of coached it through the process. Like, this is what I want it to do because I'm not, I, I'm a lot better with TypeScript than I am with Bash script. you know, I, I was like, this is what I want it to do.

[00:36:06] **Adam:** Make it do that, and it works great. I could I read it to you and tell you exactly what it's doing? Probably not.

[00:36:11] **Tim:** Yeah.

[00:36:11] **Ben:** one thing that I've been doing lately, which I find it's one of these things, like I'm just impressed that it actually works very well, is I'll have Claude create a combination prompt and to-do list, so kind of how you had the REPL loop, where you're like, just keep looping until all these things are done.

[00:36:31] **Ben:** I'll, as part of the planning mode, I'll say to Claude, design a prompt file. All I want to do is be able to feed this file back into you and give you no other insight. And you read it and then you update the checklist inside and then it's like, oh, I gotta do that. So then I have to add this note about how the first thing I should do after I read this prompt is get the next thing that appears to be not completed yet.

[00:36:56] **Ben:** And it's really cool, like it'll just keep overriding itself over and over again until it's done.

[00:37:01] **Tim:** Yeah.

[00:37:02] **Ben:** I dunno.

[00:37:02] **Adam:** So, or Boris.

[00:37:03] **Tim:** Yep.

[00:37:04] **Ben:** it's just cool.

[00:37:05] **Tim:** It is. And,

## [00:37:06] Tim's Dual-AI Architecture Review

[00:37:06] **Tim:** I also, over the weekend, just, I don't know, the idea came to me like, you know, I got two a, a two ais. I have subscriptions and I've noticed that Claude tends to be very good at some things ChatGPT tends to be very good at other things, and they definitely have preferences about tools to use and, and how to do things.

[00:37:26] **Tim:** My, my gut tells me that Claude is. Developer focused because anytime you ask it anything slightly technical, it starts spitting out code fragments, ChatGPT on the other hand, you've gotta beg it to create code fragments, but it's very good at it. It seems good at like, just knowing what's the most up-to-date stuff going on.

[00:37:45] **Tim:** And it's very good at image generation and very

[00:37:49] **Adam:** talking about ChatGPT?

[00:37:50] **Tim:** ChatGPT. Yeah. Yeah. and so I said, well, you know what? Let me see if I can get the best of both worlds here. So it started out, the idea was that, I wanted to rework my blog. So I have a blog. It was on, just on blogger. It was a recipe blog, timothy cunningham.com.

[00:38:07] **Tim:** And I'm like, let, let's, let's rebuild it. And so I basically told, I think I started on Claude and just said, Hey, here's the, here's what I got. I already have AWS, I have a Claude Anthropic key. I have an OpenAI key. But as far as that goes, I want to create this blog as cheaply as possible, free being preferred, and kind of told what I wanted the blog to do.

[00:38:33] **Tim:** I, I want it to be a food blog running on AWS that has monetization. So, has links to, Amazon products to sell and want to auto-create those links, for me, or allow me to specifically put those links in. it's AI assisted publishing, so I can give it a recipe and it can create all the, the voice around the recipe.

[00:38:56] **Tim:** Based off of my other writings that I, that I fed it and automatically generate an image. Or if I give you an image, gimme an option. Like gimme a couple options based off that image that I could choose from or just use my image. And so the loop kind of went like this. So once, once I kind of had the initial idea, I took Claude's stuff and then I fed it into ChatGPT and basically I told, I told it that they were auditing each other.

[00:39:22] **Tim:** sort of the main thing that I did, I had like a three question gate. So I had a boilerplate, prompt that I created and basically said before every response you have to ask me three questions to verify my assumptions about what's, verify your assumptions about what's going on. And so that, I think that kind of prevented the AIs from just kind of arguing in the abstract they had to say, here's how I understand the problem and.

[00:39:48] **Tim:** Then I, when I fed it back into the other ai, it also would ask me three questions. So that list of questions just kept growing and helped really refine it.

[00:39:56] **Ben:** my first question is the thing that you took out of. Claude, did you basically ask Claude to generate a plan and the plan is what you fed back into ChatGPT. Okay.

[00:40:09] **Tim:** Yep. Yeah, I said, so give me your plan. Explain, give your rationale why you think this is the best option to build this. I said I'm gonna have the other LLM review it for me. And we, we did about 12 rounds. So start out at the beginning that,

[00:40:24] **Ben:** Okay. Sorry. Sorry. Let me ask one more

[00:40:25] **Tim:** Okay. Yeah, yeah.

[00:40:26] **Ben:** you get into it and, and maybe this is too much of a leading question, but I'll say Blogger is a, you know, a content management system of sorts. Did you guide Claude to say that you want to create a content management system, or to not create a content management system, or you just said, I want to create a site that does this stuff.

[00:40:47] **Tim:** a site that does this stuff? Yeah. Yeah. I didn't wanna CMS because, 'cause I told it, I told it things I was comfortable with. I'm like, actually I asked to ask me a series of like, questions about what I'm comfortable with and it, so I, I'm like, I'm comfortable in Git. I'm a developer, so I'm happy with that.

[00:41:04] **Tim:** I, I like mark down files. you know, I, I basically gave it all my preferences and so based off those preferences to started building it. So those, this is a very code forward kind of blog. It's not like I couldn't hand this off to someone else and they'd be like, immediately understand it. That make sense?

[00:41:19] **Ben:** Yep.

[00:41:20] **Tim:** So, so kind of the, the loop was, and, and I was doing it all on my mobile phone 'cause I wasn't even at my computer. And, and I can't see, and I can't see my phone very well, so I was using a hundred percent using voice dict dictate dictation to do it. So

[00:41:38] **Adam:** Yeah, the only thing could have been better is if you were on a ski lift.

[00:41:41] **Tim:** right. Yeah.and so I, I kinda set the prompt up and at the very beginning,

[00:41:47] **Tim:** they disagreed pretty hard, so like, Claude recommended using, an Amazon AWS API that actually is gonna be deprecated in like two weeks and ChatGPT caught that, right? So it said, Hey, you shouldn't do that.

[00:42:00] **Tim:** And then Claude said, yep, you're absolutely right. I was wrong there. I love how apologetic Claude gets when

[00:42:06] **Adam:** There's, yeah, there's these like key phrase. Is that it loves to repeat. Like, I have the full picture now,

[00:42:12] **Ben:** Yeah, mine's been saying a lot of Here's my honest take.

[00:42:16] **Adam:** Oh, I don't get that one.

[00:42:16] **Ben:** Oh, everything is my honest take. Here's my honest feedback.

[00:42:20] **Tim:** Yeah. And, and then, and ChatGPT was recommending more kind of like consumer led grade products, and then I. Claude would basically clobber those to death and say, no, that's, that's, that's dumb. You don't want to use that. And so by around eight they stopped arguing about the actual architecture. They, they agreed on what I, you know, I was gonna use Hugo, for static site generation, store everything in S3 buckets, use Terraform, you know, do, all my talking in, so in AWS Lambdas, I was gonna use, my anthropic key to do any of the coding, but I'll use my, OpenAI ChatGPT key to do any image generation and like, you know, author voice generation.

[00:43:05] **Tim:** And then they just rounds nine through 12. They basically, were just disagreeing on implementation details and they, they, each one of 'em caught each other's problems and fixed them in the, in the document by round round 12, they both agreed and they both said ship it. And so I did.

[00:43:21] **Ben:** from a mechanical standpoint, I'm just trying just so that we have the, the back and forth illustrated. So you have two chat windows open for, for lack of a better term here, and you're on your iPhone and you, you have a prompt. The prompt gives you a bunch of feedback. So Claude says, here's all my feedback.

[00:43:40] **Ben:** And then are you then taking that feedback and then just going over to ChatGPT and saying, here's, here's what Claude said, and pasting that in, and then back and forth. Back and forth.

[00:43:51] **Tim:** I, I basically phrased it so that they would, when they responded, they would always do the, these things. They would, they would, give a summary of all the assumptions. That were had been made and the, the correct answers and then, state its case, and then it, it would, it, it was basically once I did the first loop, I basically created a, a prompt out of it that would just copy back and forth the top of the prompt, the body of what they said, and then the bottom of the, the prompt.

[00:44:21] **Tim:** So I had this just cut and paste thing to go 'cause I was on my phone, right? So I had, what's it, the your notes app in there? So I had the notes app open and I would just copy and paste. And I mean, it would've been a lot faster on a computer. I probably could've wrote a program to do it, but, but yeah, that, that was sort of the, so step one I

[00:44:36] **Adam:** But why pull away from Deep Space Nine if you

[00:44:38] **Tim:** Exactly, exactly.

[00:44:39] **Tim:** Exactly. A hundred percent. I, I, so I had the, the initial design created step two, I carried it, you know, to ChatGPT and OpenAI for the, for an audit. And then I brought. ChatGPT's critique back to Claude. And then Claude issued a formal verdict on each criticism and then had Claude reinstate the full updated blueprint.

[00:44:59] **Tim:** And then once I had the blueprint, I said, you know, build everything that needs to be done to do this. Make sure I have, and then also make sure that I have pre prerequisites on need on my machine. So I ran the prerequisites one. It installed everything I needed. Alm I think only one of the tools needed me to just click some buttons.

## [00:45:17] Building a Blog in Hours With Claude

[00:45:17] **Tim:** So I installed all the tools to my machine. And then the other, prompt generated like the checklist of what needed to be built, all the features. And I just let it run for like two hours.

[00:45:28] **Ben:** Dang.

[00:45:29] **Tim:** And it was almo, it was, had a working website. It had some things I had to do to change the DNS and pointing and all that sort of stuff.

[00:45:37] **Tim:** But, it told me how to do all that. And so about two hours I had a working blog and then, you know, I spent the next couple hours just kind of tweaking it and getting it better, adding features.

[00:45:47] **Adam:** In an AI photo of you in a apron with a spoon that has, it's a double-ended spoon. Is that what that is?

[00:45:53] **Tim:** Yeah. I cannot get that spoon changed no matter if, if I really like, so I like my face on that one, that picture. I, I'll probably delete

[00:46:01] **Ben:** What's,

[00:46:01] **Tim:** it's obviously, uh, timothy cunningham.com.

[00:46:04] **Ben:** again?

[00:46:04] **Tim:** I like the, my face on that one. It was the best, it was the very first one it did, and I could never get it to make my face look bad again. It made me look up, up fatter or wider or I, it check kept changing my head shape.

[00:46:18] **Adam:** you know what's really funny? this is a total aside, so ding for me, but, the,

[00:46:22] **Tim:** ding,

[00:46:24] **Adam:** just for, for giggles, one day I took a selfie of myself and I put it in ChatGPT, this was, I, I don't remember if I started, I don't remember if I did this with or without beard, but I just, I started, it's like, okay, let's just say I had, I did it while I had my beard.

[00:46:36] **Adam:** So I said, you know, what would I look like if I shaved my beard off? And it guesses, right? There's, it can't really see through the beard, so it kind of figures it, it makes a guess. And then I take that,

[00:46:44] **Tim:** it said JD Vance.

[00:46:49] **Adam:** Low blow. Done me dirty,

[00:46:51] **Adam:** sir.

[00:46:52] **Adam:** Um,

[00:46:52] **Tim:** that was just for humor. I meant no disrespect. I love you

[00:46:55] **Adam:** I, yeah, I, I would've made the same joke if I could have, but I took the, so it, it generates what a, a picture of what I think I would look like or what it thinks I would look like. And I just take that and I create a new session. I'm like, here's me without a beard.

[00:47:06] **Adam:** What would I look like with a beard? And you just go back and forth a few times and it totally like generates this whole sort of like, alternate reality of yourself. You look like. It's like, this is my, this might be what I look like in a different universe. Like,

[00:47:16] **Tim:** Yeah.

[00:47:18] **Ben:** the image generation stuff is so fascinating to me because I find that I can give it, I mean, to, to Tim to your point, like you just can't get rid of the double-ended spoon. Like even nano banana, which everyone is like, oh my God, Nana Banana is so great. 'cause you can totally edit it with text and it can keep making same edits to the same image.

[00:47:36] **Ben:** And I feel like I can make two edits to the same image. And then after that it's basically just ignoring everything that I

[00:47:42] **Tim:** Yeah, I, I sort of feel that same way with, with ChatGPT. but it's 10 times better than whatever Claude tries to do. The Claude's terrible.

[00:47:49] **Ben:** I didn't even know Claude could do images.

[00:47:50] **Tim:** It, it doesn't, it cre it programmatically creates vector files. I, yeah. SVGs, I was trying to make it do a, menu for the, the Wild Game Party. It looked like children's drawing when it was done.

[00:48:02] **Tim:** It was terrible. But yeah, so I, I, so I was talking about this with some of 'em were Discord members and, and I think it was Brian, you get a, you did a mention in another episode, Brian, said that this pattern of, of competing ais against each other, either it could be different LLMs, different agent models or even, you know, different companies like I did, uh, it's called the AI Council.

[00:48:25] **Ben:** Hmm.

[00:48:25] **Tim:** Or Council of AI, which sounds like something from a Rick and Morty

[00:48:29] **Adam:** Yeah. The, the citadel of AI or something.

[00:48:32] **Ben:** Well, then there's another, AI service, I can't remember what it's called, but they have something called the Oracle, which is like the most expensive deep thinking of, of models apparently. And you can consult the Oracle and it'll go off and do like a deep research task that's much more expensive.

[00:48:48] **Ben:** so when you say that you let it rip for. Two, three hours, whatever it

[00:48:53] **Tim:** mm-hmm.

[00:48:53] **Ben:** You're, you're, are you putting it into a, into like a accept all,

[00:48:59] **Tim:** one hundo yolo yolo mode.

[00:49:01] **Tim:** Yep. Bypassed dangerously.

[00:49:04] **Ben:** I didn't know if there were tricks to, to get it to run otherwise,

[00:49:06] **Tim:** I mean, I didn't do that initially. I just realized it was doing everything. I wonder do, it didn't seem like it was going off the rails and, and wandering because the document, it created, it was a, it's a massive, massive markdown file, that basically gave every feature of implementation to the beginning and.

[00:49:24] **Tim:** What's crazy, it actually built everything it said it was gonna build. And it, I mean, there's a lot of features here. It uses, Simple Email Service, SES for newsletter signups, the image generation. It automatically will scan the, the blog post and look for, words that match products in Amazon, hook them together so you can get revenue from that.

[00:49:45] **Tim:** built all the Google Analytics stuff in there and, and Google Clarity, which I didn't even know about,

[00:49:50] **Ben:** I've never even heard of it.

[00:49:51] **Tim:** ever heard of it, but it's, it's another kind of like thing where you can build heat maps of your site and all the cool data that you want to see about what's, what's working well, what's not working well.

[00:50:01] **Ben:** deployment process? Are you just pushing to GitHub or something, or?

[00:50:05] **Tim:** Yeah, it's just going to GitHub and then it's using, GitHub Actions to, to do everything. And I didn't touch any of those. I just gave it my, I just, it's using my key to talk to GitHub and I didn't, I, so it is crazy. So I built something that probably in the old days, and I've, I've said this before, would've taken me months and I did it in several hours.

[00:50:28] **Tim:** And without having to, I didn't touch a line of code. I basically, I was the QA reviewer,

[00:50:35] **Tim:** a a technical, technical decider on, on things, with their suggestions. And I really, I honestly a hundred percent believe that if I had only used Claude, it would, its recommendations would've hit some bad snags. And I wouldn't have been able to just have that build loop run.

[00:50:56] **Tim:** but the fact that these two. Checked each other and their models are different enough where they know different things.

[00:51:02] **Tim:** that it was a whole lot more accurate that by the time I had the, the final, you know, PRD

[00:51:09] **Adam:** The

[00:51:09] **Adam:** spec.

[00:51:10] **Tim:** Yeah, the, the spec of the thing that it was so complete that when it built it, it built it.

[00:51:16] **Adam:** And which one did you have? Do the final build did you

[00:51:19] **Adam:** say? Oh, interesting. Okay.

[00:51:21] **Tim:** Yeah, Claude. Claude did the final build.

[00:51:23] **Adam:** Was there a specific reason you chose Claude over?

[00:51:26] **Tim:** Well, at that, that point, they had both agreed. Right? So they, they both had signed off on each other's

[00:51:31] **Adam:** But I bet you if you gave the same spec to ChatGPT Codex or whatever it is, you'd get a different result,

[00:51:38] **Tim:** probably would've, I, I just, my gut from having worked with Claude is, Claude is so much better at code

[00:51:43] **Adam:** yeah.

[00:51:44] **Tim:** than in ChatGPT that, that I trusted it to do. So it's, they're like almost like employees where, you know, they have different strengths and weaknesses once you have been working with them like we have for these past couple years.

[00:51:56] **Tim:** So,

## [00:51:57] CLAUDE.md Best Practices and Session Logs

[00:51:57] **Ben:** Yo, can I just say I appreciate the fact that you just said that Claude did something in four hours that would've taken you months to do, because I feel like my new, imposter syndrome is seeing on people say things on LinkedIn where they'd be like, oh yeah, Claude did this in 20 minutes. And if I had done it manually, it probably would've taken three hours.

[00:52:16] **Ben:** And I look at it, I'm like, three hours. I'm like that. That would've taken me days.

[00:52:21] **Tim:** yeah. Another thing, so I have a, like almost a hundred percent test coverage on everything. So, you use something called Vitest,

[00:52:33] **Adam:** Vitest.

[00:52:33] **Adam:** Yeah.

[00:52:34] **Tim:** Vitest. So I could sit there and like just in the browser, check it and it would forget often not to do the test. And I'd say, Uhuh, i'd, I'd stop it and say, Uhuh build the test.

[00:52:43] **Tim:** Dammit.

[00:52:44] **Adam:** didn't say the magic word.

[00:52:45] **Tim:** Because it would start, I'd see it'd starting to a new feature and I said I let it run for two hours, but there were a few times I interjected myself, it started a new feature and I wouldn't see any test added and I'd be like, no, no, no, no. Control C, stop. Build your test. Oh, oh, you're right. I'm so sorry.

[00:53:01] **Tim:** Blah, blah, blah. Build the test and then, alright, keep going. So.

[00:53:05] **Ben:** That's funny.

[00:53:06] **Adam:** I mean, there's, there's newer stuff that you can do. I forget the name of it, but there's like hooks you can put in to say like, okay, after you're done writing code, it, it'll automatically run this hook like deterministically. It'll run the hook. It say, okay, I finished writing code. What do you want me to do now?

[00:53:18] **Adam:** And you can say, run the tests or, or run type checker or whatever. Yeah.

[00:53:24] **Tim:** That's a tool, not just like a CLAUDE.md instruction.

[00:53:27] **Adam:** Correct. Yeah.

[00:53:29] **Ben:** a lifecycle hook.

[00:53:30] **Adam:** kind of, yeah. I have one setup that, so just so that I'm a, I don't really use it that much right now, but, there are times that I will have, a task that I know, like I'm, I'm running Claude in interactive mode, but I know I need to step away. Like I'm making lunch or whatever, and I wanna step away, but I wanna be alerted when it needs my to answer a question or approve a tool, use something like that.

[00:53:55] **Adam:** and so I have it set up, or like, I just have, I created a CLI command that will send me a notification via Discord because I'll, I know I'll get that on my phone. It'll pop up, it'll pop up on my watch or whatever, right? And so I have like a personal Discord server that exists almost entirely just for this, for, for Claude to be able to send me notifications.

[00:54:11] **Adam:** And it's a simple CLI command, so I can say. I have it as a, as a hook and say like, anytime that it stops and like is requesting tool use or, or asking me a question or whatever, if it needs input, it, sends me a message. And so I just, I have this like, the icon for the Discord server is Ralph Wiggum from The Simpsons.

[00:54:30] **Adam:** And the message is just, father, I need you in all caps.

[00:54:35] **Tim:** That's

[00:54:36] **Adam:** And so I'll get these messages on my watch all day long. They're like, father, I need you when I'm sitting here at my desk. And it is whatever, you know, because it's, it does it all the time. So I'm kind of getting a little desensitized to it because I, you know, it's happening even when I'm sitting at my desk because I want it to happen when I'm not sitting at my desk.

[00:54:50] **Adam:** But it is interesting and kind of fun, to just be like, okay, I know I can step away and it will let me know if it needs anything from me.

[00:54:56] **Tim:** Mm. In the process of doing this, it c Claude came up with a phrase that, I'm going to keep it, it started like when I was very hands-on, interactive at the beginning with it. It trying, it was trying to fix some errors and it would just like. I, I, I know that feelings like where you're just patching the error but not really fixing the problem.

[00:55:16] **Adam:** Yeah.

[00:55:17] **Tim:** And I berated it and I said, you're not fixing the problem. You're just trying stuff and hoping it works. And it said, oh, you're right. I am firefighting instead of engineering.

[00:55:29] **Tim:** And so now every ti, every time I see that pattern happen, I'm like, Claude, stop firefighting and start engineering. And, and some reason gets better.

[00:55:38] **Tim:** And, and another thing that I think helped this whole build not have a whole lot of issues. and have to, because I, there's multiple times where I've got like 50% done or 60% done, and then I realize that it, it starts struggling. And then I realized, oh, there was an assumption made at the beginning that was wrong

[00:55:55] **Adam:** Mm-hmm.

[00:55:56] **Tim:** and we gotta go back and restart, burn all those tokens.

[00:55:59] **Tim:** So my CLAUDE.md for this project, it was always, I start with number zero, clean code, follow all the principles of clean code by Bob Martin. Failure to do so will make Uncle Bob sad. And then the next number one is auto commits. Anytime it makes file changes, it auto, auto commits. So that way it, if it does go off the rails, I can roll it back.

[00:56:22] **Tim:** Self-test. Always self-test. I have a rule for, for cause a lot of times they'll say, Hey, can you run this and see the output? There'll be an error and I copy paste the error. I'm like, why do I need to do that? I'm like, you run the test. You know what to run. You just gave me the command. Go run the test.

[00:56:37] **Tim:** Go, go run the thing or the, you know, do the curl to the service and make sure that it gives you the expected output. So it does self-testing. And then as always, if I have to do something, one instruction at a time, if you need a human to do something, don't give me a, a list of 10 things. Gimme one at a time.

[00:56:54] **Tim:** Let me tell you the result. 'cause I'm dumb. I, I'm not a $400,000, server in, in Utah. And then this was one thing I added this time. So session logs. so each prompt I give you, save each prompt I give you along with a summary of your response to this folder. So I have, so like, sometimes it's like I'll give a, I'll remember, Hey, back on.

[00:57:20] **Tim:** 10 questions ago, I gave it something and it said this, and I wanna remember that, but I can never remember it. So now I have a log called in a folder called Claude Sessions. that gets expensive though. It seems to get really expensive.

[00:57:33] **Ben:** Oh, interesting. Because it has to generate all those tokens, you think?

[00:57:36] **Tim:** I think so. And then also some of the other rules that I have, make it, scan everything.

[00:57:40] **Tim:** I think maybe if I tell it to, it starts scanning that folder. And so that adds to the, to the context window.

[00:57:46] **Tim:** So,

[00:57:47] **Adam:** maybe they should add like a .claudeignore,

[00:57:49] **Tim:** yeah, that, that's what I was thinking, that, that maybe the rules should be explicit of, you know, when you are researching and do not scan these folders. 'cause those folders get huge.

[00:58:00] **Adam:** Tell it to, instead of writing those files to like a sub folder of your project, just have it write 'em directly to your desktop, not in a folder or anything. Just every file goes straight onto your desktop.

[00:58:10] **Tim:** That's, that's a great idea. Adam, why don't you do that and take a screenshot for me.

[00:58:15] **Ben:** Let me, let me ask you two a

[00:58:17] **Tim:** Oh, hold on, hold on.

[00:58:18] **Ben:** Oh, okay.

[00:58:18] **Tim:** me just go through. There's a, there's a few more things in the rules. and this one I think was really important because, some, when you're in, I'm in planning mode, so I said, when I ask you to plan a research, write that research down.

[00:58:29] **Tim:** And I gave a, a path to a folder in the project called research, to, to this as an MD file. Because a lot of times, like they'll do the ration of the planning and it is just ephemeral. It's, it's somewhere probably in my user's file that gets deleted, right? But, so whenever it act, I ask it explicitly to plan or to research.

[00:58:50] **Tim:** Having that file there, I can go back and look at the MD file and go, okay, here's what we were doing. Here's the plan. You know, and 'cause sometimes it will, it will won't a hundred percent do everything and ask, I'll say, in our plan, you said to do this, I don't see that implemented. Go implement it.

[00:59:05] **Ben:** quick aside in the Claude. In the dot CLAUDE.md, in the settings file, you can actually define a, a plan directory. So that's what I've actually started to do in my personal thing. I'll say anytime you wanna do it, I have a WIP, you know, work in progress directory. This is where it has to write the plans to, and it follows up nicely.

[00:59:27] **Tim:** Yeah. And then, um, it's, even though I told it to test itself, it's some, at some point stopped. And I, I chastised it and told it to add a rule to the CLAUDE.md so that it won't do that. And it gave a very specific example, auto diagnose after deploy. So we would deploy, I'd want it to go test the deploy. And so it did.

[00:59:50] **Tim:** So that's kind of that whole loop of where it was constantly like, 'cause it got errors, right? So it, but it fixed the errors based off of the CLAUDE.md file that I had. It'd find it, it'd go, oh, it errored and then it'd research. Write the research, come back, fix it, try it again. And that's, I think that's why it took at, at one point, like a couple hours for stuff to run.

[01:00:11] **Tim:** 'cause it was in this iterative loop of creating bugs and fixing them.

## [01:00:16] Recording Decisions for AI Context

[01:00:16] **Ben:** Very cool. So, let me ask the two of you, because you've been doing a lot more of this agentic kind of big. Broad stroke agent stuff. I've heard a lot of people on podcasts say that because we're using the agents so much that it is more important than ever to record the decisions that the, that the application is making so that the agents have the ability to go back and understand why decisions were made.

[01:00:46] **Ben:** And I feel like nobody actually explains what they mean when they say that.

[01:00:50] **Tim:** I just explained it. That's exactly what I did.

[01:00:52] **Ben:** no, but like, I, I feel like you're doing it for yourself so that you can go back and say, Hey, we said we were gonna do

[01:00:57] **Tim:** No, no, I did it also for the ai 'cause the AI reviews, the, the research. I, I wondered it. So

[01:01:03] **Ben:** But is that, is that transient for this effort? Or like, like when you, okay, so you built the blog, the blog is done, or, you know, like the, the, the initial phase to get from blogger to. AWS with Hugo, like that's done. So do you now get rid of all of those transient files that have all the decisions? Like do they, in your mind, do they serve a purpose going forward?

[01:01:28] **Tim:** I think so because. If so, let's imagine like six months. I don't touch it. It runs for six months from now and I'm like, oh, how did this thing work? And you, you know, why are we doing, I can go look through those. Although to be honest, I just asked Claude,

[01:01:43] **Ben:** Yeah, that, that's the thing that I keep coming back to is, is that everyone, it's almost like they have, it's like they have their cake and they want to eat it too. That's a terrible analogy. But people say like, oh, one of the great things about Claude is you can just interrogate it about your code base.

[01:01:57] **Ben:** But then it also feels like people want all of these files as if you couldn't just interrogate your code base.

[01:02:04] **Adam:** Well, I think the decisions thing is a very interesting spot to, to have that conversation. And maybe we should save this as a topic for later, but I think that the, the reason that decisions is a good, example here is because the code doesn't answer why. The only, the, the only thing that code does is, is answer what am I supposed to be doing?

[01:02:25] **Ben:** I guess my, my OCD is like, I have markdown files in my directory that feel like they don't relate to the application except peripherally, and every bone in my body wants to delete them because otherwise I will never know when to delete them. And like that just makes me unhappy.

[01:02:43] **Tim:** And they're markdown files and they cost you nothing to sit there. So just close the folder,

[01:02:47] **Adam:** yeah. And I was just sitting here thinking like, you know, okay, let's, let's think about it, right? So you've got like decisions.md. But like over the life of the application, this thing is gonna get huge. Right? If it's, if you just say, oh, if we make any significant decisions, document them here. It's gotta be one sentence and only explain why it does what it does or whatever.

[01:03:05] **Adam:** Right? But, you know, okay, you come back six months later, there's gonna be a thousand decisions in there. Something like that. Like that's a lot of context to feed into every request.and so I was thinking like, what if you, you know, I talked about breaking my app up into vertical slices. Like, okay, here's the controller.

[01:03:22] **Adam:** You can go up, you can go down, but never move sideways. I wonder if there's like a way to do that, like have a decisions.md in your vertical slice folders.

[01:03:31] **Ben:** Right, right.

[01:03:32] **Adam:** and, and you can say like, okay, hey, if, if you need to understand why something was done the way it's done, you can look at the decisions.md for this particular slice.

[01:03:41] **Adam:** I don't know, but

[01:03:43] **Ben:** To be, I think this, I think this is an interesting conversation to be had here, but probably not an hour and

[01:03:48] **Adam:** not at an hour in, yeah.

[01:03:50] **Tim:** for sure. So mark that down as TB, d

[01:03:54] **Adam:** Okay. Well, Go. Sign up for Tim's newsletter.

[01:03:58] **Tim:** or don't, doesn't matter.

[01:04:00] **Tim:** It's more for me than you guys. Oh, did you? Okay.

[01:04:04] **Tim:** I'll, after the show, if you guys wanna see it, I'll show you how. I'll create a very quick, blog post and let you guys see it.

[01:04:11] **Adam:** Sure. all right.

## [01:04:12] Patreon

[01:04:23] **Adam:** Well then this episode of Working Code was brought to you by Tim's double-ended Spoon. You can use one side for eating testicles and the other side for everything else and listeners like you. If you're enjoying this show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[01:04:35] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock. Really appreciate your support over the years.

## [01:04:42] Thanks For Listening!

[01:04:50] **Adam:** Uh, we're gonna go record the after show. That is the outro music is gonna play, and for the few, the proud the patrons, we will come back on the air and talk about stuff. last week we briefly did like a no spoilers project, hail Mary discussion.

[01:04:59] **Adam:** if you don't know what that means, you live under a rock and you should be ashamed.and this week, I don't know, we may or may not get into spoilers. We'll, we'll have to discuss that, but we'll, announce that at the beginning of the after show so we're not just gonna drop spoilers on you.

[01:05:12] **Adam:** But anyway, so Ben has seen Project Hail Mary now, so we could in theory talk about it. and, uh, you know, whatever else might come up. We got some stuff on the list here. Uh, if you want access to content like that, go to patreon.com/workingcodepod cost you a few bucks a month, and, we would greatly appreciate your support.

[01:05:30] **Adam:** And you get. In addition to our heartfelt thanks, you'd get some extra audio for your ear holes.that's gonna do it for us this week. We'll catch you next week. And until then,

[01:05:42] **Tim:** The enemy of my AIS is another AI enemy, but you're no enemy. You're a friend. Your heart matters.
