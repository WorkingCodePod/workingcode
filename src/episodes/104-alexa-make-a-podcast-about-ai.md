---
title: "104: Alexa Make A Podcast About AI"
description: "Tim's been reading about AI lately, so the crew checks in on recent advances."
date: 2022-12-07
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/104-alexa-make-a-podcast-about-ai/id1544142288?i=1000589204808"></iframe>

Tim recently read that, "1 in 10 AI (Artificial Intelligence) engineers think that AI will be the downfall of our civilization." But, it's not all doom-and-gloom; he's also been reading about some exciting advances in AI and Machine Learning (ML) such as Amazon Alexa being able to come up with novel bedtime stories for kids, Cosplay stars trying out new outfits using personalized "generative art", and complex software modules being created from simple prompts.

It seems that AI/ML is advancing at a breakneck speed, leveraging a rich Venture Capital (VC) space driven by a "move fast and break things" mentality. This can be really effective at creating change; but, we're also seeing lots of AI models becoming so big and so complex that no one really understand how they work. Which is problematic when such models take on the inherently biased tendencies of their creators and moderators.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/104-alexa-make-a-podcast-about-ai.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** My heart will sing. Your praises oh Lord of PostgresSQL. For you have given us a powerful tool to store and query data with ease.

[00:00:07] **Tim:** It is a gift of such great magnitude. And here's the chorus, hallelujah. Praise the Lord of PostgresSQL. It is such a gift. It's a gift of such great grace for you have provided us a way to store and query data with ease,

## [00:00:41] Intro

[00:00:41] **Carol:** welcome to the show. It's episode 1 0 4 and today we plan to talk about ai. And are you scared yet because you should be? No, not really. Anyways, so, as normal, I'm gonna kick us off with our triumphs of failures and

## [00:00:55] Carol's Triumph

[00:00:55] **Carol:** I'm gonna go with a giant triumph, you guys,

[00:00:58] **Tim:** Yay

[00:00:58] **Carol:** I have let my children live another year. Yeah, yeah. I'm, I'm not for sure how I did it so long, but man, they did. And, this week, The oldest turns 21 and the youngest turns 18. So not only did I let them live, I no longer have children. I have adults. So it's uh,it's been interesting, but we're super excited. We're super proud of them. They're great boys.

[00:01:24] **Carol:** They've done amazing things, and they're gonna go far. So I say I've let them live another year, but in reality, you know, they've let me be a mom another year, and I've enjoyed every bit. So it's gonna be crazy when they're completely gone of the house. And what the hell do I do in my free time, because I don't know what that is.

[00:01:42] **Tim:** uh, break you break that new husband in

[00:01:44] **Carol:** I, I already have

[00:01:48] **Ben:** Oh dear

[00:01:51] **Carol:** right, so that's me. I would normally kick it over to Adam, but, he's Mia, so I'm gonna throw it over to.

## [00:01:58] Ben's Triumph

[00:01:58] **Ben:** Yeah, and I'm gonna go with a triumph, I'm gonna call it a soft triumph cuz it's a triumph laced with a little bit of sadness. But,I, I've decided that the current project that I'm working on, on the legacy platform, I'd like it to be the last project that I work on for the legacy platform. I'm. I'm tired of living on the edge and like never quite knowing when the legacy platform is gonna go away.

[00:02:20] **Ben:** And I'm tired of trying to fight against the current. I sort of just, I just wanna let go of all that baggage and, and move over to the new platform and kind of be looking in the same direction with everybody else.

[00:02:34] **Tim:** Good for you.

[00:02:35] **Carol:** Wow.

[00:02:36] **Carol:** Wow.

[00:02:37] **Ben:** it's

[00:02:37] **Tim:** That's huge.

[00:02:40] **Ben:** you know, I am a little sad about that, but, I started having a one on.

[00:02:44] **Ben:** Meaning weekly with one of our director of engineering for the platform. And, she's the first person that I've really started opening up to in a, in like a reporting structure kind of way. And it sort of just, I, I don't think I realized quite how frustrated I was until I started telling someone how frustrated I was.

[00:03:04] **Ben:** And, it just, it opened up a whole lot of emotions and, and I don't know, I just sort of lost, I lost. The desire to fight, you know? And, and I sort of just wanna be on the same page with everybody else. hold on. I had one more thought in there. Give me one second.

[00:03:19] **Carol:** Okay, you got it.

[00:03:20] **Ben:** what the heck? I know I had like, something was bouncing around in my mind. Oh yeah. Oh yeah. So the other thing is that, we've been slowly migrating all of our enterprise customers off of the legacy platform, and we're basically done. There's. Four or five enterprise customers left on Legacy. And the thing about having the legacy, the thing about having the enterprise customers there is that that was my connection to the customers because Enterprise have support contracts and they talk to our customer facing team.

[00:03:50] **Ben:** And then I can talk to our customer facing team and get a sense of what our customers are liking, what they're not liking, where there's maybe some opportu. Now that it's just non-enterprise users on the legacy platform, there's, there's really no communication channel for me. They, they don't even really file support tickets.

[00:04:08] **Ben:** Cause they don't, I don't even think, I don't even know if they can file support tickets.

[00:04:11] **Tim:** They're not all,

[00:04:12] **Carol:** They've turned that off

[00:04:13] **Ben:** Yeah. Honestly, I'm, they might not be allowed to. So there's like, I think there's a public forum they can participate in. It's, it's, I'd like, there's no more connection between me and the customers, and it was really the customers that was driving me to wanna improve the legacy platform.

[00:04:29] **Ben:** And if I can't communicate with them, I feel like I'm really working in an echo chamber and, and I, and I got no one to talk to anymore. So, yeah, it's time to move on. Time to move on to the new platform.

[00:04:42] **Carol:** So when you said that this was gonna be your last project, I got emotional for you, like, and then when you kept talking, I got a little sweaty. Like this is a lot, a lot to take in all at once. Like it's been your baby for so long and it's been your life that. hear you've hit that point where you're okay moving and you're okay letting go and just seeing what the future holds, man, you got in my emotions tonight, Ben.

[00:05:11] **Tim:** I, I mean, he, he's had a relationship with this thing as long as you've had kids, Carol

[00:05:18] **Ben:** Well, you know what I, I want to go watch, there's a Netflix show, I think I mentioned it many, many, many episodes ago. There's a Netflix show called Seven Days Out, I think, and, or one Week Out, something like that. And it's, and it's a bunch of episodes. Each episode is completely separate one of them is about the Cassini satellite that they crashed.

[00:05:39] **Ben:** Saturn or Venus or something. And, it's, it's, it's a whole episode about things coming to an end and, and how emotional everybody gets. And I feel like I need to go and watch that, one more time just to like get all the cries out.

[00:05:53] **Tim:** Hey, if, if you want something similar without rewatching, I just on Amazon Prime, I watched, goodnight. OPPI. It's about the, the opportunity probe, the rover that was on Mars that, you know, only supposed to be a 90 day and it lasted like 15 years, I think.

[00:06:09] **Ben:** Oh

[00:06:09] **Tim:** And like the relationship that this, it was pretty well done.

[00:06:12] **Tim:** They very. They very anthropomorphized. These, these, the robots that, that were on Mars, but just the whole relationship that these teams had with them, and I mean, they got at the end, I'm crying like, like Rover.

[00:06:27] **Carol:** I actually, that's one of the few things I have watched, and I agree. At the end of it, I was bawling like a baby because you built this emotional connection with the products that you're working on and what you're delivering, and when you thought it was going to only survive a year and it gave you 15, you're like,

[00:06:44] **Tim:** Yeah.

[00:06:45] **Carol:** How do you let go?

[00:06:46] **Ben:** I I

[00:06:46] **Carol:** do you let go?

[00:06:47] **Ben:** I totally get it. Well, there's, in, in the episode I'm talking about, on Netflix, there's, they, you know, nasa, they calculate everything down to like the half second, practically, even despite the fact it's hundreds of thousands of miles away and they, as the satellite is crashing into the atmosphere, they have an estimate of when it'll stop being able to send back.

[00:07:09] **Ben:** And they hit that mark and then it continues to send back data for like another 30 seconds or 60 seconds. And I was like, oh my God, it's still the love

[00:07:17] **Carol:** ho, ho, ho.

[00:07:19] **Ben:** You go buddy. You go

[00:07:22] **Tim:** Yeah. That's cool. I'm proud of you though, a bit, I mean, it's, it's scary. It, it, it, but, you know, all things that are worth doing are scary at first.

[00:07:32] **Ben:** yeah. It'll be big. And I'm, and I'm sure I'll have a lot to say about it as, as time goes on. So.

[00:07:38] **Tim:** yeah. Well, what we'll have to recall are I work on a legacy platform sticker now.

[00:07:43] **Tim:** Oh wait,

[00:07:44] **Carol:** timing,

[00:07:45] **Tim:** oh wait, red Bubble. Laurie did that. Nevermind.

[00:07:48] **Carol:** as we're shut down.

[00:07:51] **Ben:** All right, so that's me. Tim, what do you got going?

## [00:07:54] Tim's Fail

[00:07:54] **Tim:** And I wish I could make this three in a row, but No. So, you know, just came off Thanksgiving weekend and I got sick during Thanksgiving as for some reason I want to do, and, spent pretty much most of Thanksgiving. Four, you know, four day weekend sick and just sleeping all day long, 15, 16 hours a day and feeling like crap.

[00:08:15] **Tim:** And then even like the beginning of this week, I felt terrible. Today was actually the first day I actually woke. I, I felt had energy. I worked yesterday, I took the first Monday, Tuesday off, and I worked Wednesday. But just, I was so tired and, you know, couldn't breathe. It, it's not covid. It was, I don't know, it's just a cold flu.

[00:08:34] **Tim:** I don't know what it is. But today I had energy. I felt good, but I woke up with pink eye . So we nor we normally record this and we, we actually have our cameras on normally, but I have it off today cause I look ridiculous. I have a, a homemade eye patch on, which is toilet paper and blue painter's tape over my eye.

[00:08:53] **Tim:** Cause it, you know, any amount of air on my eye

[00:08:55] **Tim:** makes it hurt.

[00:08:57] **Tim:** But yeah, so I don't really have anything coding related, you know, to, to share cuz I really haven't done a whole lot. I, I did, I did a bit today, but it's really, you know, it's, it's really hard to, to, to work on a computer when you only have one eye.

[00:09:11] **Tim:** You, I'm like trying to move the mouse around and you wouldn't think on a 2d, you need depth perception, but it's like, I'm trying to find where the mouse goes and I'm moving it all around like, no, that's not it. , trying to see where it click and Yeah, it, it was, it was a, it was stressful writing code today.

[00:09:29] **Tim:** Someone wanted me to do, do, do something to like, delete a whole bunch of data and I'm like, Nope, I'm not doing that until I have two eyes.

[00:09:36] **Carol:** Yeah. In the full working brain,

[00:09:38] **Tim:** Yeah. And a full working brain. So.

[00:09:41] **Ben:** that's brutal,

[00:09:41] **Carol:** you get to feeling better.

[00:09:43] **Tim:** All right. Thank you. Thanks.

## [00:09:45] Open AI

[00:09:45] **Carol:** I think we should probably talk about AI since that's what I said in the intro,

[00:09:51] **Tim:** That's, that's a good point. Yeah, that's a good point.

[00:09:53] **Carol:** If only the show were by ai, it would already know what we're gonna talk about, but it's not. So

[00:09:59] **Ben:** Hold on. Actually, let me see. I'm gonna go to open AI cuz I was playing with that today. So beta open ai.com. What is open?

[00:10:10] **Tim:** so this

[00:10:11] **Carol:** the back of GitHub pilot, right?

[00:10:14] **Tim:** is it.

[00:10:15] **Carol:** Yeah, I'm pretty sure.

[00:10:16] **Tim:** that's cool. So beta open ai.com. This, this one that has a little playground, we can just put in a prompt and it will create a story for you. So it'll do, it'll do writing for you.

[00:10:26] **Tim:** So I'm gonna type in a prompt for, a, let's see a tag, maybe a tagline for a podcast about writing codes. Let me do that.

[00:10:35] **Tim:** So,unlock your coding potential with code. Right. Podcast

[00:10:42] **Carol:** We'll take that out and put our real name in and we're good.

[00:10:45] **Tim:** There we go. There we go.

[00:10:46] **Carol:** Yeah.

[00:10:47] **Tim:** Yeah.

[00:10:48] **Carol:** So yeah, I did Google real quick because I was pretty sure it's what it was. And GitHub co-pilot does use the open AI codex for their suggestive code, so, which I now pay for, because I loved it so much, I refused to get rid of it. So

[00:11:03] **Ben:** Oh, nice.

[00:11:04] **Carol:** I did that thing.

[00:11:05] **Tim:** Yeah, so I mean, I brought this topic up cuz I've just been reading a lot about. AI and its potentials and people's fears of it. And so this is kind of a general topic of it. Don't really know where this will go, but I mean, I've been playing around with like, you know, this open ai.com and also the, the generative art, that it, that it creates and it's gotten, I mean it's gotten amazingly better just within like the past three to four months since I've been following it.

[00:11:33] **Tim:** It's just getting better and better to the point. Like it's, it's really getting kind of scary.

[00:11:37] **Carol:** I will say that kind of about this, our teams get really mad if you're on the AI team and you refer to them as the ML team, or if you're on the ML team and you refer to them as the AI team, and I don't understand why they get so mad. It's very confusing, like machine learning versus artificial intelligence.

[00:11:58] **Carol:** Like where does the line.

[00:12:01] **Ben:** Well, didn't, I think Adam one time was griping about the fact that there is technically no ai, that it's all machine learning.

[00:12:07] **Tim:** Yeah, I, I remember him talking about that. Yeah. I, I asked the same question. I mean, what, where is the line? What, what do your teammates say? What the, in their mind, what the difference is?

[00:12:17] **Carol:** I wish I could remember an answer off the top of my head. They usually just remind me that they're not part of the ML team, that they're technically an AI developer, and I don't know what they do.

[00:12:28] **Ben:** wait, so you have an AI team at work?

[00:12:31] **Carol:** Yeah. Yeah. We have people who write AI and we have people who write ml.

[00:12:35] **Ben:** I don't know if you can talk about this, but what is the AI team? Cause you're in real estate, right?

[00:12:40] **Carol:** Yeah, we're in real estate.

[00:12:41] **Ben:** So what, what do you have an ai, what does the AI do?

[00:12:45] **Carol:** Again, you go back to, I don't know which ones do what. So I can tell you we have predictive models, which don't know which team does it. We have a lot of analytics. We have. I mean, I would really have to go look at what people and their titles are to know what projects they work on because like I said, they get mad that I confuse them for the wrong team.

[00:13:02] **Carol:** So I'm not for sure what they do,

[00:13:04] **Ben:** All right. All right, fine, fine, fine.

[00:13:07] **Carol:** but I'm gonna put it on my notes and I'm gonna find out and I'll.

[00:13:10] **Tim:** Cool.

## [00:13:11] Amazon Poly

[00:13:11] **Ben:** I was playing around with, Amazon Poly, I think. Tim, you may have brought this up

[00:13:17] **Tim:** Yeah. I use it.

[00:13:18] **Ben:** so I was just playing around with, and, and if you sign into the Amazon console, you can go into Poly and you can enter a paragraph of text and you can have it turn that text into speech. And it has two options. One option is Standard Voices, and then the other option is like Standard Voices plus machine learning algorithms.

[00:13:35] **Ben:** And it just, it makes it sound, I don't wanna say perfectly human, but it definitely. Smooths out a lot of the weirdness that the, that the normal voices bring to it. And, it's, it was pretty cool. Like it definitely, it, it opens up in my mind a lot of opportunity where I can take something that I would maybe normally need a voiceover actor for.

[00:13:56] **Ben:** Not that I have a lot of these opportunities, but like, you know, if you wanted to make a demonstration video for animations or something and you wanted someone to be narrating it, It becomes very feasible in my mind to to just write it out and then, and then get something like Amazon Poly to use their machine learning algorithms to make it sound like a real person.

[00:14:15] **Ben:** It's pretty, it was very cool.

[00:14:17] **Tim:** That's cool. I, I'd have to check that out cause I didn't know they, they've added that feature to Poly,

[00:14:21] **Ben:** Yeah. Yeah.

[00:14:22] **Tim:** huh? .

## [00:14:23] Stable Diffusion

[00:14:23] **Carol:** So what have you been like reading about. That made you wanna talk about this or listening?

[00:14:29] **Tim:** So like the, so the image generation, right? So the generative art, so, stable diffusion, which is an open source, project that does, you know, you give it some text and you generate images. and I mean, it's eventually, when I first started looking at it, I was like, images were. Kind of suspect, but now it's like, I mean, they're generating stuff that's just like people are entering it into art competitions and winning

[00:14:52] **Carol:** Oh, okay. So I've looked at some of this like. It's able to create is amazing, but should it really be eligible for a winning awards like you're against a human, the computer's gonna win every time.

[00:15:05] **Tim:** Yeah. There's people, like their job is to just, to write really good prompts to generate stuff.

[00:15:11] **Carol:** wow.

[00:15:12] **Ben:** Although, you know, when this started to come out a couple of months ago and everybody was talking about, How offended, quote unquote real artist would be that people were essentially creating stuff in their styles. But, I feel like it sort of died down. And I wonder if, if there was a lot of fear, uncertainty, doubt, kind of mindset, and maybe it's just not becoming the issue that people thought it was.

[00:15:36] **Ben:** Or maybe it just hasn't had enough time to play out, but.

[00:15:39] **Tim:** don't, I don't think there's enough time to play out. I think eventually there's gonna be some lawsuit that will kind of shake things out a little bit in that regard of, you know, particularly if it's a living artist, you know, you have a living artist, they're trying to make a living, creating their art, and then people are using your name as a prompt to generate, to generate art that looks like yours.

[00:15:58] **Tim:** That. And then they're selling it and you know, you're now, you know, you're creating with your own, you're competing with your own self. So is that fair? What I did read that I didn't recently. I read that. so stable diffusion, if there's a watermark. Or, on the image or photo or, you know, whatever that the art that it's, it will not use that.

[00:16:22] **Tim:** It will automatically throw that out. So if you put a watermark on your art online, then, but it's like, you know, there's just so much stuff on the, it's, it's using the internet, right? So it's like tons of people will go put your, put a picture of your art or put, you know, whatever, cropped out the, crop out the, the watermark or whatever it is, and, it'll get used.

[00:16:42] **Tim:** So it's like the genie's out of the bottle.

[00:16:44] **Ben:** Yeah, it is really interesting. I, I played around with one of the, The, the prompt for, for image creation. And, I, I was just having a fun time and I was, my prompt was something like large muscular women with, with veiny biceps dripping with sweat and glistening under the overhead light, you know, something like, and, and the, and it generated stuff that.

[00:17:07] **Ben:** L almost looked like photography, like it looked like real people, but like real people with some problems kind of a thing.

[00:17:19] **Carol:** Interesting.

## [00:17:20] Code Generation

[00:17:20] **Tim:** what what really gets scary though, is like when we start using AI to create code and to create programs. There, there's, there was, there's projects now where you can just try to describe a, Like a code project, like, you know, did you describe basically a Trello board and it will generate the code for you

[00:17:40] **Carol:** That's nuts.

[00:17:41] **Tim:** and you can run it and a lot of times it gets close and you have to tweak it and everything, but it's like that's beginning stages at some point, you know, at some point.

[00:17:49] **Tim:** And it seems to be moving really, really fast. It. We won't be coding anymore. We'll just be telling a computer, you know, describing what we want. It'll build it, and then we're just quality assuring it. All of us will become QA

[00:18:03] **Ben:** But I love coding.

[00:18:05] **Tim:** I know, right.

[00:18:06] **Carol:** Yeah, whenever I'm using copilot to do stuff, I'll be like, I'll start by typing out like a little comment. I'm like, oh, I just need, you know, A to see if it equals B, or you know, something simple, not too in depth. Right. And it will like pop up whenever I hit tab. It's like cause A equal B. And then it's like return true or return false.

[00:18:26] **Carol:** And I'm like, okay, this is so nice. Like so. It takes me a second to like, that's not a hard one. I usually can get that one you guys, but sometimes I do write things slightly more complex, right? So whenever I hit the tab button and it populates something, I'm like, oh yeah, that seems like a good way to do it.

[00:18:47] **Carol:** And I wouldn't have done it that way. I would've probably taken a much more complicated approach to get to this answer. So I'm like, thank you for helping me today, But one thing it cannot figure out is CF abort . Just letting you know that not figured out. CF Abort yet. I type in CF abort, and then it's like CF abort and it types label and it tries telling me to put like a sentence there.

[00:19:10] **Carol:** It's like, return for case equals false, right? And I'm like, no, I just was abor. Just stop. No more, no more syntax needed. Just stop

[00:19:20] **Ben:** Maybe if you do a dump first, then

[00:19:22] **Ben:** cuz that it'll understand that pattern Maybe.

[00:19:25] **Carol:** no, like even if you know how you can do cf, like dump and then inside the dump you can do abort at the end of it, it still doesn't understand to put 'em together.

[00:19:33] **Carol:** So even if I do like a tag base, if I'm in a, like a C file and I do a tag base like CF dump and I don't put it in the, the dump, attribute, like I put it on the next line and I do CF abort, it still automatically wants to insert label equals, and I'm like, It doesn't get one. Stop it.

[00:19:54] **Ben:** No label for you,

[00:19:55] **Carol:** to hit backspace.

[00:19:57] **Tim:** that's cuz it's based on all, all the GitHub code that all the ColdFusion people are doing wrong.

[00:20:02] **Carol:** yeah. Yeah. I'm like, you're no labels. I don't even think it'd work. I'm pretty sure it'd break if I did that.

[00:20:09] **Tim:** Yeah.

[00:20:11] **Ben:** It's interesting though. I mean, when Tim, when you talk about it, about us becoming. Quality assurance people, not necessarily coders. I, I think about products that are, that encapsulate really complex things, but not necessarily creative things. And I, and I'm painting with a super broad brush there, so take that with a grain of salt.

[00:20:32] **Ben:** But I, you know, something like, like off zero where they've encapsulated all the logic you could ever need for authentication and user management and like social logins and the reason. That's a business is because that's stuff at a low level is really complicated. I mean, there's all that kinds of o you know, like, um,OAuth, hand shaking and back and forth and stuff and, and the social logins.

[00:20:56] **Ben:** But you know, I imagine that there's not a ton of creative work in there and, and that seems like if you could talk to an AI and just be like, build me, uh, a social login integr.

[00:21:09] **Ben:** I mean, that's kind of, that's kind of terrifying, the idea that you could maybe wipe out a business like that.

[00:21:15] **Tim:** true. But at the same time, it's like, yeah, we we're at work, we're building up a new site. It's a new, new product, and, You know, the whole user authentication and a multi-tenant type system. I mean, guys been working on it for four to five weeks now. It's like, if you could just describe that to an AI and have it done and then just review the code, make sure it looks good in qa.

[00:21:35] **Tim:** I'm like, that would be amazing.

[00:21:39] **Ben:** It is very, it's fas, it's terrifying, but it's.

[00:21:42] **Tim:** Yeah, it is. And the, so other things I've been reading about, I'll talk about the dark side of it a little bit, is, so from what I understand, this is very much a layman's view of, of how this things works. So, Machine learning used to be like, you know, building instruction sets and things like that. But now that what they do is they, they build this data model.

[00:22:02] **Tim:** It's all about the model, right? So they build this, and I don't understand what goes in building this data model and the size of the model makes a big difference and where it gets this stuff from. But they build this data model and then they attach the AI to it to hit against the model, to, to build stuff.

[00:22:18] **Tim:** And, but what is interesting is, The model is being pulled from the real world, and the real world is, inherently biased and inherently, uh, racist,

[00:22:31] **Ben:** Mm-hmm.

[00:22:31] **Tim:** it, it, it, those models have the same thing. So we're people are, you know, companies are building AI products that are inherently, you know, biased towards certain people, and they are people that look a lot like us.

[00:22:46] **Tim:** Let's be fair and. And so that they're like, you know, how do you prevent that? Because, you know, people are gonna take the outputs of this. They're gonna put information in about healthcare, about, finance and about, you know, making decisions about who gets what. And if your model is biased and the AI comes up with biased answers, you're just perpetuating that same bias, that's going on in the world.

[00:23:09] **Tim:** So how do you, how they fix that problem is they don't really underst. The model is so big they don't really understand how it works, why it works, or how it gets the answers that it comes up with. And that's the craziest thing. They don't, people that are building stuff that's coming out with the right answers, really good answers, but they don't know why.

[00:23:27] **Tim:** That's just insane

[00:23:29] **Carol:** I will say that's a sentence I hear at work, not that we don't know what we're doing and that, you know, we don't know how the data works, but I do hear like, oh, we're training the model, like we're training the model. And I'm like, what the hell do you mean? You're training the model? Like from my side, that just sounds crazy cause I'm an application engineer, right?

[00:23:48] **Carol:** Like, I don't know what the heck you're doing over there. So you're training the model, which just means that they're giving it information with valid. Outputs and it's learning based off of what it's been given with true and false returned, right? So it's kind of like it's able to predict where markets are going to go when you look at housing ups and downs, right?

[00:24:12] **Carol:** And the value of a house. So it takes the information it's been given, it takes. Information about the industry and it learns from it. And I'm just like, I don't understand this but it sounds so fancy and I want to train something like How to Train Your Dragon. I don't know. But , like my application doesn't do that.

[00:24:32] **Carol:** Right? My application is business logic. It's, I tell it everything it's gonna do. It doesn't have to assume anything cuz I've told it every path it could. So it's just, it's a whole nother world to me that it feels so far beyond what my brain can comprehend at.

[00:24:48] **Ben:** Totally. Well, I was listening to a, an interview I, I, one of the podcasts I listened to is about Google search, like I, I think it's people on the Google search team and one of the episodes they were saying, can anyone at Google actually tell you how search works? And, the guy was like, maybe a, maybe years ago, there were people who had it all in their head, like they really understood the algorithm, but he's like, today no one could really tell you how Google search works.

[00:25:15] **Ben:** It's so complicated and it runs through so many different algorithms and, and it's just impossible for anyone to point at any one thing and, and understand the ramifications of changing it. And he

[00:25:26] **Carol:** I would be so scared. I'd be so scared.

[00:25:28] **Ben:** and, and he said like, they'll, they'll make mistakes. Like they'll roll out a change in, go in the Google search algorithm and suddenly page rankings will completely tank, and then they'll have to roll it back because they didn't realize it would have the, the ramifications. And they said like they just, you know, they make mistakes. It's

[00:25:45] **Carol:** Yeah. Yeah.

[00:25:47] **Tim:** I mean, hey, all of us have had a project like that at some point, right? all of us have had some code we inherited or maybe we, we wrote years ago and we're like, I don't wanna touch that cuz I don't know what's gonna do. I have no clue what this does. I can't figure it out. Anything I do will break it. So you think of that on a scale, you know, times a million

[00:26:07] **Tim:** That's what we're dealing with with ai.

[00:26:10] **Ben:** At, at work, sorry, a little side story for a second, but at work, one time we were talking about, so we had the new platform has a lot of microservices and sometimes we're not always entirely sure if a microservice is actually being used anymore.

[00:26:22] **Tim:** Elon says, turn it

[00:26:23] **Ben:** Well, yeah, that's what I was gonna say. So like they'll look at the CPU utilization, but the problem is because it's running in a containerized environment, there's health checks constantly being fired.

[00:26:33] **Ben:** So the machines are doing stuff even if no one's really using them. And so Yeah, to exactly to what Tim was saying where someone said, just use the screen test. And I was like, what's the scream test? And she was like, you turn it off and you see who starts screaming.

[00:26:50] **Tim:** I will admit, I've done that many times

[00:26:51] **Tim:** in

[00:26:51] **Ben:** You know, totally, totally

[00:26:53] **Tim:** are we still using this service? Like, oh, I dunno, turn it off. Let's see.

[00:26:58] **Carol:** So I don't think I've actually ever done that. Like I have looked at code and been like, okay, this is clearly deprecated and we are not utilizing it anywhere. Like it's just being initialized as a property or it's like a getter center, but it's not actually being used. It was just never taken out of some files.

[00:27:14] **Carol:** But when I look at something and anyone still calls it, I'm like, Hell no, I'm not taking this out cuz I don't want someone screaming at me. Like I get so scared, like sweaty, like, I can't do this. Someone else has to, has to be the one to decide to remove this and I should be able to. But nope. The, the fear of my customers hitting that and it being needed and me being the one that hit delete on that file.

[00:27:40] **Carol:** Pass. Pass hard, pass.

[00:27:43] **Ben:** Yo totally.

## [00:27:45] The Singularity

[00:27:45] **Tim:** So something I read two days ago. Was talking, the headline was that one in 10 Artificial intelligence developers feel that, AI will be the end of our civilization at some point. which it's, it's kinda scary and it's not, it's not like, you know, just ma pa sitting on the front porch shooting the breeze. These are people actually were working on it and they, they were worried about that. And one of the points it made is, The difference between, they're like, well, you know, haven't we had other things that we've worried about in our society that we thought was gonna ruin, destroy the world?

[00:28:20] **Tim:** Like nuclear power, right? Nuclear, nuclear war. Well, they made the point that the difference is that nuclear bomb doesn't really have. A goal on its own, it doesn't have its own motivation. Right. Someone fired it and, you know, something blew up with ai, the entire thing is, is you give it a goal. That's, it's the entire thing.

[00:28:41] **Tim:** You give it a set goal and it has to figure out how to do that. It's not, it doesn't have malevolent intent. Right. it just, you give it a goal and it's like, what's the best way to do that and the way it might do. Could be very detrimental to a lot of people if, if it has the power to actually enact what it wants to do.

[00:29:00] **Tim:** And the illustration they gave the comparison was so, you know, I don't think of myself as a, an aunt Genocide, right? But, you

[00:29:08] **Carol:** I don't even know what that means. So can we circle back to that in a minute?

[00:29:11] **Tim:** so a person who wants to kill all the ants,

[00:29:14] **Carol:** okay.

[00:29:14] **Tim:** Yeah, so, so, but whenever, so around the air conditioner, very important in south to have a good air conditioner and there's lots of constant condensation that comes off of it.

[00:29:25] **Tim:** And the ants love the water, so they come, they will block up your air conditioner. I, I've had so many times my air conditioner break because an ants get in there and just clog it up. Yeah. They

[00:29:35] **Carol:** build a ant mound.

[00:29:36] **Tim:** They build an ant mound to get the water and then it like shorts, the circuits on, on the capacitors

[00:29:41] **Ben:** I've never heard of that. That's

[00:29:43] **Tim:** it, it's happened to me probably 10 times, in the past, like nine years.

[00:29:49] **Tim:** So now I'm very diligent about going out there and I spray with pesticides on a regular basis and I'm killing all these ants. That was my goal. My goal is I want air conditioning. My, my, my answer is, I have to kill the ants. And so if you give a goal to AI and their answer is, well, we just need to destroy half the population, like Thano said, I mean , and then you give them access to tools to do that, then that's a bad thing.

[00:30:18] **Ben:** Yeah, it can escalate pretty quickly.

[00:30:20] **Tim:** Now is that gonna be the reality? I don't know. But since the fact that we don't really know how they come to these answers, And what's, what's the big issue is that people are in such a hurry right now to make money off of it. People are just throwing tons of money right now building these kind of things, and you can see the results because it's gotten so much better that the art, the story generation, and they aren't really, you know, what is, what was the model?

[00:30:46] **Tim:** move fast and break

[00:30:47] **Tim:** stuff.

[00:30:48] **Carol:** Oh yeah. I hate that. Yeah.

[00:30:49] **Tim:** and that's exactly what they're doing with, with ai. They're like, just move fast. We throw money. We don't wanna worry about, you know, the quality of what we're doing or the, the ramifications of what we're doing. And so that, that, that makes it kind of scary.

[00:31:01] **Carol:** See, I would like to see the progression of it. Like Ben was talking about his picture right. woman, sweaty veins, like I don't, I don't remember all the words you gave, but I would like to see step by step, like what it used to get to that. Like when you type in the word vein, what does it get? Like if I just put vein in first, like what happens versus muscular vein?

[00:31:23] **Carol:** It's completely different, you know? it's very interesting.

## [00:31:27] Boston Dynamics

[00:31:27] **Ben:** You know what I love is the Boston Dynamics. Those, the robotics

[00:31:31] **Carol:** Oh my God, their robots are the,

[00:31:34] **Ben:** they make the best videos too.

[00:31:36] **Carol:** And I don't know why, but when it falls I tear up. Right? Like, I'm like, no, no, walk over it. Don't fall. Don't fall again. And when it finally makes it, I cheer cuz this robot has worked so hard and oh,

[00:31:51] **Carol:** oh

[00:31:51] **Ben:** such small little steps sometimes, like the little durable dainty steps. I remember in one of the early videos that they posted the, I think it was one of the robots is there and he is holding a box. And one of the, engineers is next to him and he's hitting him with a hockey stick or something and, and knocking the box out his hands and the robot to keep picking the up.

[00:32:12] **Ben:** And one of the people who was commenting on it, they were like, just so we know, this is the moment it all,

[00:32:21] **Tim:** This is the robot uprising.

[00:32:22] **Ben:** yeah.

## [00:32:23] Alexa

[00:32:23] **Tim:** So do you guys, do you guys know that? So Alexa's coming up with a new feature that's that's coming out that they will, You can have Alexa tell you a bedtime story or just any sort of story. Yeah. And it will come up with story and sometimes little pictures and music and like different voices. And so you give it maybe a prompt or something, you know, tell me a story Alexa, about, you know, this

[00:32:46] **Tim:** And it just, and I'm just worried, you know what happens whenever you ask a story and it's like, don't give your kids nightmares for weeks. Cause it goes up with a scary

[00:32:55] **Carol:** The wrong one, right?

[00:32:57] **Ben:** Well, years ago, I mean, maybe like four years ago, five years ago, at work, I forget, we had some sort of meeting and there was like goody bags and everybody got some sort of a, an Alexa dot or something, some sort of, you know, like little round speaker thing you keep at home. And I turned it on. And me and the misses were sitting there and we were trying to figure out how it works and asking questions and, and it just like didn't understand a lot of the questions.

[00:33:25] **Ben:** And finally I was like, Alexa, why is my wife so hot? And it was like, I'm sorry, I don't understand that question. I was like, this thing's dumb. And I turned it off and I never turned it back on

[00:33:36] **Tim:** I'm sure it's gotten better. Let me give you another example. So I, I posted this on our Discord for, patrons. I said, write a limerick about a code monkey. And so here's a limerick, A code monkey with no degree works hard with great tenacity, though he's not a pro, he codes like he knows that his work will bring prosperity

[00:33:58] **Ben:** Oh my God, that's kind of great.

[00:34:00] **Carol:** great. That's actually amazing.

[00:34:03] **Tim:** And I also did one. the prompt was write a, a Bible song. A Bible song about PostgresSQL. It's pretty long, so I won't give you the whole thing. I'll just give you the, the, the first verse and the chorus. My heart will sing. Your praises oh Lord of PostgresSQL. For you have given us a powerful tool to store and query data with ease.

[00:34:23] **Tim:** It is a gift of such great magnitude. And here's the chorus, hallelujah. Praise the Lord of PostgresSQL. It is such a gift. It's a gift of such great grace for you have provided us a way to store and query data with ease,

[00:34:37] **Ben:** Oh my. Wait, so what? What is it? What's generating these things?

[00:34:41] **Tim:** That's the same thing. The, the beta, open ai.

[00:34:43] **Tim:** Yeah. Yeah.

[00:34:46] **Ben:** Well, now I gotta try it. That's, this is, this is just a lot of fun sounding

[00:34:50] **Tim:** It is pretty

[00:34:50] **Carol:** all so silly. So silly.

[00:34:52] **Ben:** open ai.

[00:34:53] **Tim:** yeah, if you wanna do some fun, so there's like stable diffusion. You can upload a photo of yourself at, or a photo of anything actually. But it's like you put a, like a portrait of yourself and just, you know, put prompts in, like, make me look like Superman. Whatever they will just generate and these totally do this stuff.

[00:35:11] **Tim:** There's a, a friend I follow on, on Facebook and she's been doing like hundreds of these of herself. She's a cosplay professional and just like to get ideas for cosplay and she's like, can see kind of her and costume already fully, you know, fully imagined. And she's like, oh great. Then she can pick out, you know, what she wants to do cuz it looks, it's her, it's her face, her body and costumes and different like art styles and everything.

[00:35:37] **Tim:** That's pretty cool.

[00:35:38] **Ben:** That is really cool actually.

[00:35:40] **Ben:** Dang

[00:35:41] **Tim:** So I'm working on my, resume to see what I can do besides coding, cuz I, think maybe we just got a

[00:35:47] **Carol:** Gonna need to tweak that up, aren't we?

[00:35:49] **Tim:** Yeah. what can't, what can a robot or a computer do?

[00:35:54] **Carol:** Oh gosh. Have babies.

[00:36:01] **Tim:** I can't do that either,

[00:36:02] **Carol:** you just, you're screwed. I'm sorry, Tim.

[00:36:05] **Tim:** yeah.

[00:36:06] **Ben:** worthless,

[00:36:06] **Carol:** Yeah.

[00:36:07] **Tim:** I'm, I'm appendix now. Just take me out. Not needed.

[00:36:14] **Carol:** All right.

## [00:36:14] Patreon

[00:36:14] **Carol:** If you're listening to this show and you are an ML or an AI engineer and you would love to talk to us, we'd like to hear from you because clearly we don't really know the difference and it might be great to know. So we hope you've enjoyed this episode. this episode working code was brought to you by Let It Go.

[00:36:31] **Carol:** Let it go. Let it go. Letting go of Legacy and listeners like you. If you're enjoying this show and you wanna make sure we can keep putting more of whatever this is out into the universe, you, you should consider supporting us on Patreon. Our Patreons cover, our recording and editing costs.

[00:36:49] **Carol:** So we can't do this every single week without them. Uh, special thanks to Monte, Sean, and Giancarlo.

## [00:36:56] Thanks For Listening!

[00:36:56] **Carol:** So, your homework this week is tell a friend, tell someone about the show who you might think would enjoy this, and we'd love to hear from them.

[00:37:03] **Carol:** You can find us@workingcode.dev.

[00:37:06] **Carol:** Do y'all have anything for the after show?

[00:37:08] **Tim:** after she actually sing, sing My PostgresSQL

[00:37:11] **Ben:** Yeah,

[00:37:11] **Carol:** Oh, please do. And, I would love to tell you about a show I've been watching called Wednesday. It's pretty damn great. So, that's it for this week. We'll catch you next time. And until then,

[00:37:23] **Tim:** Remember, your heart matters, especially our soon to be robot overlords. Please don't delete me.
