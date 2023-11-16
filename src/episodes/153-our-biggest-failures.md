---
title: "153: Our Biggest Failures"
description: "On today's show, we talk about our biggest failures and being open with failure."
date: 2023-11-15
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/8d0a0f39-b05b-4545-ae86-cf4477938589"></script><div class="redcirclePlayer-8d0a0f39-b05b-4545-ae86-cf4477938589"></div>

Inspired by a [4-part series on "Failure"][freakanomics-failure] produced by the [Freakanomics radio podcast][freakanomics-radio], we went around the table and talked about our own failures. This helps to remove the social stigma associated with failure; and, helps other people process internal conflicts of emotion. Tim talks about failing to sell websites in the early dot-com boom; Adam talks about failing to create a ColdFusion package manager; and, Ben talks about the _years he lost_ trying to learn Object Oriented Programming (OOP).

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[freakanomics-failure]: https://freakonomics.com/podcast/how-to-succeed-at-failing-part-1-the-chain-of-events/
[freakanomics-radio]: https://freakonomics.com/series/freakonomics-radio/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/153-our-biggest-failures.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Ben:** I felt like I had to take everything that was a simple data structure and elevate it into an entity

[00:00:07] **Ben:** and it just like. didn't add value and it made everything more complicated. And I just, I think

[00:00:13] **Adam:** Shame on you. Do you feel better

[00:00:14] **Ben:** the time, all the time that I spent trying to figure it out

## [00:00:37] Intro

[00:00:37] **Adam:** Okay, here we go to show number 153 and on today's show, Carol's out sick. hope you feel better Carol, but the other three of us, we're going to do a potluck. We're gonna talk about, failures, log levels, and pre mortems. But first, as usual, we'll start with attributes and fails.

[00:00:51] **Adam:** Like I said, Carol's out sick, so Tim, you're up first, man.

## [00:00:54] Tim's Fail - No Code

[00:00:54] **Tim:** Man. So it's been a little over a week since we recorded last and I guess I'll go with a failure here. I feel like I maybe wrote 20 lines of code this past week. I mean, I've done work as far as coding wise. Like,

[00:01:06] **Adam:** Mm hmm.

[00:01:08] **Tim:** I need, I need to, I need to, I need to break stuff.

[00:01:11] **Adam:** know you're, uh, you're, you're higher up in the company, right? You're some sort of muckety muck. how

[00:01:17] **Tim:** the director. A

[00:01:20] **Adam:** those words in front of your title. How much do you identify as a coder versus a manager?

[00:01:26] **Tim:** hundred percent.

[00:01:28] **Adam:** You still got that

[00:01:29] **Tim:** Yeah, 100 percent coder, but it's like, when I'm not doing it, I don't feel like I'm, I feel like I'm not working and I'm doing, taking meetings, talking to legal, talking to marketing. I feel like all I'm doing is talking, it doesn't feel like I'm working.

[00:01:42] **Adam:** Yeah,

[00:01:43] **Tim:** And so I feel a little guilty about that.

[00:01:44] **Tim:** I mean, the 20 lines of code I wrote were, you know, important.

[00:01:47] **Adam:** bangers.

[00:01:48] **Tim:** They were bangers. Yeah. They, they, they were, they were, they were awesome. But, I just like, what was my output this week? And a lot of it's like talking to the team and making, you know. They alerted me to some previous decisions that, they made that, so we have multiple companies, right?

[00:02:06] **Tim:** So we're all owned by one huge, giant corporation called Constellation Software out of Canada. And of our sister companies, they had an SSO server and we just kind of glommed onto that one. I didn't realize some very mission critical part of our. Stuff is, is that's not live yet, but it's going to be was it's using their SSO.

[00:02:25] **Tim:** I'm like, why are they using theirs? What happens if they start messing around with it and they break it? They're like, well, it was ours. I'm like, one, no, we need to, that needs to be aligned. We need to either like use like a cloud version of SSO or put our own server up. Cause I don't, don't like, I don't like intermixing companies priorities.

[00:02:46] **Tim:** Right. So I do that. But again, it doesn't feel like I'm really working. It's just me telling someone else to work.

[00:02:56] **Ben:** your force multiplier there.

[00:02:58] **Tim:** no, I feel like a jerk. Like a complete jerk. It's like, oh, you go do that. I don't know how to do it. So you do it.

[00:03:04] **Adam:** You're the April Ludgate of, Constellation Software.

[00:03:07] **Tim:** I don't get that reference.

[00:03:08] **Adam:** Parks and Recreation.

[00:03:09] **Tim:** Oh, you know, started watching Parks and Rec and I got like the first few episodes in and I just, I just couldn't finish, but I hear it

[00:03:14] **Adam:** first season is tough to get through. They didn't really, like, figure out how the show should feel until season two, but it is so worth it. High, strong recommend.

[00:03:24] **Tim:** All right. I'll, I'll try to get into it.

[00:03:26] **Ben:** we watched it years ago, and to this day, we're constantly saying, you got jammed for like anything that goes wrong. Which...

[00:03:33] **Adam:** Roomba, feed yourself.

[00:03:36] **Ben:** Yo.

[00:03:37] **Tim:** so hold on. So, so as, Adam likes to make fun of me, riding on people's coattails, typically I talk about my, my, my son and, you know, right.

[00:03:45] **Adam:** Well, that's the thing, Tim. You're so perfect. There's nothing wrong with you. I gotta have something. You gotta make up an insult. Gotcha.

[00:03:51] **Tim:** Okay. I'll, I'll, I'll take haters however I can get them, but, I have to brag on my daughter. So I talked earlier about my daughter. She went to one act play, which is the thing I did in high school where they, it's competitive acting, which sounds crazy, but it's true. they did a home shows, they did two shows, one last Thursday and then one this past Saturday and watch the play.

[00:04:12] **Tim:** And it was hilarious. It really was. you know, I was very proud of her. She's, she's not. She's not a very outgoing person. She's very personable, but she's not really outgoing person, but she was so funny and this play, this play was hilarious. It really was. I mentioned it before, but it was called the 25th Annual Putnam County Spelling Cut, Putnam County Spelling Bee.

[00:04:37] **Tim:** And it's a bunch of kids, you know, doing a spelling bee and just some of the like, particularly like her line was, they gave her a word and they said, please spell acouchi. And her line is, I'm sorry, what? acouchi, how do I spell English? What does it mean? And it, it, it's actually a word. It means it's some sort of rodent from South America. and, and her shtick is, so each, like, contestant has, like, a certain,a thing that they do so that they spell, so one guy, he has a magic foot, he'll, like, spell, he'll use his toe, and write the word out on the floor, and it's a whole song called Magic Footwork, but hers is, she goes into, like, this trance, she says, I'm, I, I don't know the word, Then all of a sudden she goes into this trance and like starts spilling the word out.

[00:05:29] **Tim:** Like s it's just screaming it, right? . And her song is, I'm not that smart. So the, she's homeschool. The character is homeschooled. The character's name is Leaf. first name's Lee. I forget what Le Leaf. Coney Bear. That's the, that's the name. And she's homeschooled. And like everyone in her family tells her she's stupid.

[00:05:52] **Tim:** And her song is, I'm not that smart. And she sings a song about how she's not that smart, but then like, they do a reprise of the song later and like, she's like, faking it. She's like, she pretends to be dumb because she's actually smarter than all of them. So it was, it was, it was really funny. Yep. And so I saw it twice and yeah, they did good.

[00:06:11] **Tim:** So just, just proud of her carrying on the acting tradition in our family. We'll see. We'll see. She got cut out Godzilla movies. She had like a closeup shot that was like awesome. And then they cut it.

[00:06:26] **Ben:** Oh, crazy.

[00:06:27] **Tim:** Did I tell you guys about that?

[00:06:28] **Ben:** No,

[00:06:29] **Adam:** I don't recall that.

[00:06:31] **Tim:** So, the, like, the first Godzilla King of Monsters, they had a scene where all these, like, warriors were gonna go and, you know, fight.

[00:06:39] **Tim:** The, the kaiju and she was the daughter of one of them and it was just her, it was just her, me and the director on, on set, and the camera guy was, and there was like this whole set there and the scene was, she was like on an iPad saying goodbye to her daddy, you know, and, and, so there's zooming in on her on the couch and she had to cry, right?

[00:07:00] **Tim:** So they wanted her to cry. So she's, and because. You know, your background, you're not allowed to actually talk. So you have to mouth the words. You can't actually say anything. It's just, she's looking into the little iPad. She's like. Daddy, I love you. And she's not actually saying the words. He's like, okay, so we need you to cry.

[00:07:17] **Tim:** And normally they'll put like clove oil under your eyelid. And then they'll, they'll use like a little puffer, puff of air to like blow in your eye. She didn't need that at all. He's like, can you think you can cry? She goes, yeah, I can do that. And she's, this was years ago. She's probably, she's probably 12 years old at the time.

[00:07:33] **Tim:** And so she's just looking straight into the iPad or actually in the camera and just this perfect little tear

[00:07:38] **Adam:** Oh,

[00:07:39] **Tim:** rolls down her cheek. He looks at me, the director looks at me and goes. She's good. I'm like, I like that surprised me. I didn't even know she could do that.

[00:07:49] **Adam:** yeah. It makes you put it into question all those years,

[00:07:51] **Tim:** Yeah. All those don't, don't spank me, daddy. Okay. You were crocodile tears, so yeah. But anyway, that's me. I don't really work that hard and my daughter's awesome. So

[00:08:02] **Adam:** don't worry, we won't tell anybody. Nobody listens to this.

[00:08:04] **Tim:** No one's listening to this anyway. All right. How about you, Adam?

## [00:08:07] Adam's Triumph - Decorator

[00:08:07] **Adam:** I'm going to go with a triumph. I've got a couple of things on my list here, so it could go either way. But the thing that's, striking a nerve with me right now that I did within the last week is, I wrote this pretty neat, for lack of a better word, I'm going to call it a decorator.

[00:08:18] **Adam:** it's, it's sort of a, it's just a CFC, right? So we're talking about cold fusion code.

[00:08:23] **Ben:** nice.

[00:08:24] **Adam:** And it's got a constructor method and you pass that constructor method, and instantiated, and attached, like a session attached, I guess is the right, word, soup for it, for a ORM entity, right? So you create an instance of my, of my, Did you,

[00:08:40] **Adam:** Yeah. Or, um.yeah, yeah, I, I'm not a fan, but, you know, the code you got is the code you got and you got to make it work.

[00:08:45] **Adam:** Right. Like, anyway, so you create an instance of my CFC, you pass it an entity to the constructor, and then you just treat it like normal. Right. So you say, get this property, set this property, whatever. And then, because of the way that ColdFusion ORM works, you can't just, it's not a true decorator, and this is why I say it's not a decorator, because you can't just say, entity save my CFC that contains your CFC, right?

[00:09:07] **Adam:** You have to, like, get your entity back out to pass it to entity save to save the changes that you made to that record, right? so that's like the one place where it fails as a decorator, but I think that that's less of a failure of my code than it is of just the way the ColdFusion ORM stuff works.

[00:09:26] **Adam:** Like, there's no, there's not really a good way to do decorators in ColdFusion. Anyway, so I got as close as I could there, and the whole point of it was to make atomic logging of record changes super easy. So... It wraps an entity and then as you're calling different setters on it, whatever changes compared to whatever the current value is, it's logging only those per column changes.

[00:09:48] **Adam:** So you could, you know, take a column that's got 50, I'm sorry, you could take a row that's got 50 columns, change three of them, and you know, and then you say, okay, give me the entity back so that I can save it and also give me the changes so I can audit that. And you get back like an array of the three columns and their before and after.

[00:10:05] **Adam:** values, so that it makes it super easy to log those things. Which was, it was kind of funny, it was like a lightning in a bottle moment, right? You know, it's like, how am I going to do this? This just doesn't, it just like, I kind of tried two or three different things, and then finally I was like, wait a minute, let me try this.

[00:10:19] **Adam:** And I, and I did it, and I was like, oh wow, this is, this is pretty cool. This is pretty awesome. And it's like, it makes use of, onMissingMethod, to, to do the getters and setters. And there's some logic about like, I only want to do it for, I guess in ColdFusion parlance, they're called simple values, like booleans, strings, and numbers, right?

[00:10:37] **Adam:** So if you pass in a null or if you pass in another entity instance for like a relationship set sort of thing, it just ignores those in terms of the, the atomic changes tracking. but all the, all the simple values get. For atomic changes. So the

[00:10:56] **Tim:** I saw, I saw you posted that on the discord and it's like, someone took an exception. I think it was Sean with, with the code, how the code was done.

[00:11:05] **Adam:** screenshots. Yeah.

[00:11:06] **Tim:** His eyes were burning, apparently from, from

[00:11:09] **Adam:** Because of my use of getters and setters, to be honest, it wasn't even my use, but Hey, that's, that's the code, you know, it is what it is. You got to start where you're at.

[00:11:17] **Ben:** It'd be cool if there was a, on missing property handler as well. I think maybe there might be in Lucy. I can't remember because.

[00:11:27] **Adam:** Go ahead. Explain this to me. What would on missing property do?

[00:11:29] **Ben:** in, in the same way where you can have the on missing method get invoked, if you say object. foo and foo doesn't exist as a method call, it'll call that if you just did object. foo as a property call, the same way you might do like CGI. http underscore refer, and if that didn't exist, you could invoke a method and essentially like fill out values that, that don't exist.

[00:11:57] **Tim:** Be cool if you could do Elvis operator with a function at the other side.

[00:12:00] **Ben:** The E. Yeah, yeah, I know what you're saying. Like, like, if you think about a JavaScript proxy, which I've, to be fair, have only used I think once in my entire life, you can essentially intercept every single possible way to access an object. And one of them is, is the missing property stuff, or like, you're not missing, but you can just intercept any property and you can intercept method calls, you can intercept.

[00:12:24] **Ben:** Getters and setters. And I think there's a couple of other things you can also intercept.

[00:12:29] **Adam:** Yeah. So, I mean, that was just like a, it was kind of a fun little coding thing. I like, Tim mentioned, I'm kind of getting into this point of my, my career, I guess I'll say, where it's like. A good chunk of my time is spent doing things that are not writing code. Like today, for example, I spent maybe two hours like reading through the co op program of a local college to, like how am I going to get involved in and like hire some interns or, or co op students to, to help us out and that sort of thing.

[00:13:01] **Adam:** It's like, it's not coding, but it's going to help us.

[00:13:03] **Tim:** Should we change the name of this podcast to not working code pod? Thought Dev?

[00:13:08] **Ben:** So between you working on more managerial stuff and, and Tim apparently never writing code, one

[00:13:15] **Tim:** No, no, no. Oh, 20 lines, 20 lines.

[00:13:19] **Adam:** That's like two a day,

[00:13:20] **Ben:** one thing that I think would be an interesting, maybe not a topic, but maybe just a segment would be, So there's all these different roles that you can have in a team. So there's engineers and then there's, you know, lead engineers and staff. And then there's product managers and there's project managers and there's engineering managers.

[00:13:38] **Ben:** And sometimes I'll see people at work do things and I think to myself. That's not really your job. And, and I say that in part because I would never want to do that role. And, and, and I use my role a little bit as protection to not do certain things, which I know is like not the best way to think about teamwork, but anyway, I think it would be interesting to have a list of activities.

[00:14:00] **Ben:** And then have to put them into a bucket, like negotiating contract prices on reserved instances for Amazon. Like, is that an engineering manager doing that? Is that a principal engineer? Is that a... you know, financial guy doing that. Like whose job is it to do that thing? Given the fact that there are people available to do the work and not like, yeah, Johnny's wearing his engineering hat today and his PM hat tomorrow and his HR hat the next day.

[00:14:27] **Ben:** Like,

[00:14:29] **Adam:** How much money do you have to spend at Amazon to, to have the kind of cred where you can negotiate on their prices?

[00:14:36] **Ben:** Oh, that was just, that was just something I pulled out of my butt here.

[00:14:38] **Adam:** Okay. I was like, wait a minute, those things are negotiable. Okay. Well, maybe they're negotiable if you spend enough money, like, right. They say everything is negotiable, right? Like,

[00:14:48] **Tim:** time Amazon's ever contacted me, it's always like, Hey, so you've reached a certain level and you know, you can, it's always like, basically they just want you to spend more money. That's, that's the whole call. They're like, so are you using this or using that? I'm like, I don't need that. I don't need this.

[00:15:00] **Tim:** And they just like, okay, we're not going to talk to you anymore.

[00:15:02] **Adam:** yeah. I've been getting those emails that are like, Hey, we, you know, I'm your designated account representative or whatever. And it's like, You know, we just want to have a check in, make sure that you're making the most of the services you're paying for. And I'm like,

[00:15:13] **Tim:** Those calls

[00:15:14] **Adam:** know exactly what you want to talk about.

[00:15:15] **Adam:** And I am not interested.

[00:15:17] **Tim:** you want to upsell us? So, but I'll tell you that. So in our organization, you know, there's different ways to do that. But it's like, so, you know, we'll have people that will like say, okay, you guys know what you need. So you guys, you know, suggest it. But then we always have some bean counter up at the top.

[00:15:35] **Tim:** It's like justifying it. Right. So if we don't do this, what will be the cause? And if we do do this, what's going to be the benefit, right? And sometimes you just put them like, you know what, you, I can't even explain it to you in a way that you will even understand. All you do is like push numbers around on Excel. So just, just trust me, but they, they never take that answer. So you have to make, sometimes you just have to make stuff up and go, Oh yeah, yeah. We would lose like a million dollars if we don't do this. And like, Oh, we can't do that. Okay. Yeah. Just sign it. Jesus.

[00:16:07] **Adam:** well that's, I guess that's enough riffing on my, entity decorator. So Ben, how about you, man?

## [00:16:14] Ben's Fails - Dog Weight Management

[00:16:14] **Ben:** to go with two fails. One, one small fail is, so it's finally cold here up in the Northeast. I live in New York. I woke up the other morning, it was 24 degrees and, uh, we just gave our dog a haircut. And so I put on her winter jacket to take her for a walk. And the winter jacket barely fit her. It was like a, it was like a doggy Spanx control top, kind of a thing.

[00:16:37] **Ben:** And I just, I feel so bad. Yeah. I have let her get fat and, I've teased her about it for a while now, but it was sort of, she had such long hair. It was, you could sort of say like, Oh, it's just the hair. It's not really her, but we got her

[00:16:49] **Tim:** She's fluffy.

[00:16:51] **Ben:** She's, she turns out she's fat and, I, I feel, I feel bad. I gotta, we gotta start feeding her less cause it's, she's just a sausage.

[00:17:01] **Tim:** How's she handling that?

[00:17:03] **Ben:** the, the, the constant mocking or the eating?

[00:17:06] **Tim:** No, the eating, cause, cause we have a, we have a, you know, pugs tend to be very over. So we have our, our male pug and he, after he had like his testicles removed, he got really, we didn't eat them by the way. We did not, we didn't, just, just before Adam jumps in. We did not, we did not cook them. and he just got.

[00:17:25] **Tim:** Yeah, too close to home. And, he just got chunky, chunky. And so we like, so we had like a half cup, you know, per kibble per meal, like two meals a day, we went to like a quarter cup and that dog lost his fricking mind.

[00:17:39] **Ben:** that's the thing it's, it's, you know, we're not feeding her because we want her to get fat. We're feeding her cause she's. You know, to be honest, she's such a jerk sometimes. And you're like, how do I, I can close your mouth by putting food in it is, is the, is the approach and, we just have to be better about redirecting her energy or something.

[00:17:57] **Ben:** I mean, we've clearly, we've clearly taken some wrong turns in an effort to. Avoid parenting, I suppose. So anyway, so that's one fail. And then the other fail is, so I'm trying to round out the, the draft of my book on feature flags. And I think I mentioned this before, conceptually the book is sort of in two halves.

[00:18:15] **Ben:** The first half is a technical Component and then the second half is kind of a personal inter interpersonal component. I'm really having trouble finding the words in the second half and kind of getting my thoughts onto the page. And it's just, it doesn't feel like it's gelling because I think it's much more, I dunno, I think maybe I'm trying to make it longer than the book needs to be.

[00:18:40] **Ben:** And I'm, and I'm, and I'm just, I'm hitting a wall in terms of. Creating a story, but I'm going to, I'm going to, yeah, go ahead.

[00:18:49] **Ben:** volunteer as tribute, man. Send it my way, I'll copy, you know, I'll read it and let you know what, I appreciate that. So I have, I have one chapter left that is not at least at full draft. and I want to get that done. Before I, I share it with anyone. Only because then I think I can, I'll do a quick, I'll do a read of it through myself and, and, move chapters around or do some more tweaking, or there's probably stuff I've completely forgotten about, but have since remembered, but didn't remember to go back and put it in.

[00:19:16] **Ben:** So I want to, I want to get that final chapter in, draft, and then I can do a read through and feel like. Is it crazy? Is it, is there, is it, is it making sense? Is it cohesive? Is there a storyline, et cetera? And then, and then I'll try to start getting maybe some feedback. Anyway, so that's me. It's I've been writing this book now for about two and a half months and it's, it.

[00:19:40] **Ben:** It's feeling like a slog. It's feeling like a slog. I kind of just want to be done already at this point. It's not even so much that I want to be done with the writing. I want to take the time that I'm writing and now do other things. I don't want to spend that time writing anymore. I want to... Get back to blogging.

[00:19:57] **Ben:** I want to get back to, Angular 17 just came out. That's very exciting. They've done some huge revamping. people are talking about Angular as having a new renaissance, which is very exciting for me as someone who loves Angular. Those may, you know, those might all be people on the Angular team saying that.

[00:20:13] **Ben:** I don't know, but I'm just, I'm getting itchy. You know, I got, I'm getting that cabin fever.

[00:20:20] **Adam:** Yeah, I saw a mutual friend of all of ours on Facebook recently talking about, you know, I guess he got laid off a while back and he's gotten to the point where he's looking for a job and, He said that every job posting, is looking for, that he, I guess, every job posting that he's run across is looking for React developers and he doesn't want to put React on his resume yet because he, like, he knows it, but he doesn't know it, know it, you know, like, so yeah, it's a brave new world.

[00:20:47] **Ben:** Apparently companies looking for React are having trouble keeping engineers. That's all I'm saying. All

[00:20:56] **Adam:** Okay, cool.

[00:20:57] **Ben:** right. So those are my fails.

[00:21:00] **Adam:** uh,

## [00:21:01] Failure

[00:21:01] **Adam:** Tim, how are you a failure? I'm the king of segues, aren't I?

[00:21:08] **Tim:** you are. Yeah. Yeah. So that was pretty, pretty, that was so smooth. No one saw that coming. so I was listening to Freakonomics podcast the other day.

[00:21:16] **Adam:** See, you do listen to podcasts.

[00:21:17] **Tim:** well, actually it was in the car, it was on the radio. And then I was

[00:21:20] **Adam:** Oh, okay, like you're just

## [00:21:21] Survivorship Bias

[00:21:21] **Tim:** This is really, really good. So I went and got NPR one, NPR one on my phone.

[00:21:24] **Tim:** Like what was that called? It was an episode called, is it, is it four part series about failures? And this one is called grit versus quit.

[00:21:33] **Adam:** Okay. Mm hmm.

[00:21:34] **Tim:** And so there was several different portions of this podcast. And they talked about, you know, the American way is like, you just grit it out, keep fighting, keep fighting.

[00:21:42] **Tim:** But you know, at some points, like it's, it's the sunk cost fallacy. You just can't keep throwing energy after energy into something if, if it's never going to happen. But, and part of the, I think the whole idea that we just think gritting it out is better than quitting, you know, when you need to quit is that people don't talk about their failures. Enough. People, all we see is the winners in life. They talk about, you know, oh, I built this company and, you know, had a good idea and it turned into a multi billion dollar company. Well, that was the one success. They don't talk about the 15 or, you know, however many other companies that they started that failed because some ridiculous number of companies, particularly startups, like 90 percent of startups fail and, and, and like more than half of, of, small businesses that startup fail.

[00:22:32] **Adam:** Yeah, what is that, like, survivor bias, basically,

[00:22:34] **Tim:** Yeah. Survivor bias, right? Yeah. You, you, all you talk about is stuff you did right in the things that you want at, and everybody's like. I failed, so I must not be as good as them. So there was, this researcher, academic researcher, she put started, she put out her, she called it her CV of failures. So for Americans, CV is the curriculum, Vitale, it's what Europeans call their resume.

[00:22:57] **Tim:** and so she put all the, the re research papers, all the things that she put out there that never got accepted, and then some other big muckety muck in the, in the academic world, put that out there. And I just thought that was interesting. It's like, you know, we on the show.

[00:23:11] **Adam:** like, published this.

[00:23:12] **Tim:** Ashley published this, right?

[00:23:13] **Tim:** It didn't get much, didn't get much traction until the other person who was much more known in the community put his out, and then they sort of became a thing of just, you know, letting people know it's like, you know, if you've had like 10 research papers, proposals, or grant proposals, rejected. These very successful people did too.

[00:23:34] **Tim:** And I just thought about that too, you know, on our podcast, you know, to our credit, pat myself on the back, we do it, we do a triumphant and a fail every week, but I don't think we've ever talked about what were biggest. Like career failures, like things that we tried and just either didn't work or ideas that we had that we pursued that just didn't pan out.

[00:23:55] **Tim:** we, we tend to, we as humans, not we as a, us here on the, on the show tend to, you know, focus on the, the, the successes rather than the failures. So I just thought it might be interesting to pass that around the room and say, you know, if you had a CV of failures, what would be some of the more embarrassing or more painful lessons in your.

[00:24:17] **Tim:** Professional career, because I don't want to get into personal stuff. This is a CV, not a, not a, I drank too much and I lost a million dollars in Vegas. You know, that's whatever. Um,

[00:24:27] **Adam:** I had a million dollars to lose in Vegas, geez.

[00:24:29] **Tim:** still paying it off. yes. So yeah,

[00:24:32] **Adam:** at a time.

[00:24:33] **Tim:** exactly.

[00:24:34] **Ben:** Well, I think one of the very interesting things in one of those episodes, cause I also listened to Freakonomics, love it, one of my favorite podcasts, is that they were saying in the Scientific world, it's actually a huge disservice because people, so the scientific method is you have a thesis and then you test the thesis, but they're saying that that's not really how it works in the real world.

[00:24:56] **Ben:** That usually what happens is a scientist has 12 different theses that they have interest in experimenting with. And so they run all the experiments and then they find an outcome that matches one of the theses. And then they sort of work backwards and say, well, this was the thesis the whole time. And here's the experiment we run.

[00:25:13] **Ben:** And here's the outcome I got. So they, they published the thing that worked, but they don't publish the other 11 experiments that didn't work at all. And because of that, no one else gets to know that they tried that and no one else gets to say, Hey, let me not try that. Cause it's already been proven to not be the right approach.

[00:25:31] **Adam:** The other thing about that particularly, scientific research publishing, is that... You don't just decide, hey, I'm going to publish this, you know, I'm going to write a blog post about my research that I did that, that went nowhere and it was totally pointless and I wasted a year of my life on that, you, submit that as a proposal to publish in a, in a variety of different, scientific journals, right?

[00:25:53] **Adam:** So you can publish to nature or science or whatever. and the, the journal itself has to accept it. And the, like, they try, I guess in, in theory, I, I'm not a scientific researcher, I don't know any of this for sure, but from what I've heard, you know, they try to... Adjust for their biases, but they're also trying to sell publications, right?

[00:26:15] **Adam:** Like they, if it's just a whole magazine full of, I tried this and it didn't work. And then somebody else says, I tried this and it didn't work. Like, it's not gonna be a very interesting magazine. Right. So they have to like, they're still, it's just like the news on TV, right? That nobody would pay attention if there wasn't some reason to look, right.

[00:26:32] **Adam:** There's gotta be clickbait

[00:26:33] **Ben:** Right. Right.

[00:26:35] **Adam:** So that's just how like bias sneaks into scientific research too. It's not just that, they don't write about the, the stuff that didn't work out, or you know, the other 99 percent of their research, it's that they can't because nobody cares. Basically,

[00:26:52] **Ben:** Well, we see that even in the technology world where

[00:26:55] **Adam:** sell.

[00:26:56] **Ben:** not uncommon to read some article, like our team switched to react and now suddenly they were. Operating at super speeds or we finally switched to a Golang and now we've reduced our processing by 10, 000%. But you're not reading about all the teams who tried similar things and completely failed and that wasn't the right choice.

[00:27:21] **Ben:** Because to your point, it's not, you know, one there's shame in, in usually announcing things like that publicly. you might not even be allowed to because of the company that you're working for. And, and it's just. People don't want to do it. And then you, you, you enter this echo chamber where you're hearing only the positive outcomes.

[00:27:40] **Ben:** People often talk about Steve Jobs as being this mastermind. And he was kind of a jerk to a lot of people. And you say, was he successful because he was a jerk or was he successful in spite of the fact that he was a jerk? And he just happened to be one of the people who survived with that trait.

[00:28:00] **Tim:** I mean, his whole,

[00:28:01] **Adam:** he was successful?

[00:28:02] **Tim:** and his whole next, it was the computer, the next computer. I mean, that was, that was a failure and we didn't, no one's talking about next these days, right? They're talking about, they're talking about Apple. You know, that was a success that after he came back the second time, after he was fired the first time,

[00:28:18] **Adam:** Mm hmm.

## [00:28:20] Tim's Biggest Failure - Special Effects Conference

[00:28:20] **Tim:** So I'll go first. I'll talk about, so I've worked the same company, same 23 years. So I've not had a whole, I've had a pretty good cushion against failure, but I have had some. So in between, had a fit, we had a family business that I was a part of. And then after my parents sold the company, I had a period of their way, I was trying to just be a freelance, programmer.

[00:28:43] **Tim:** Right. And this is early days of internet. Right. So it's like, you know, this is MySpace days. This is, you know, AOL dial up days kind of thing. But you know, that's like, I was super excited about it. And I thought, you know, everyone wants, everyone needs a website. I had a website, you know, I created my own website.

[00:28:57] **Tim:** So, you know, everyone needs one. So I started going to businesses and trying to sell it to them. And it's like, I just couldn't get people to see the need for it.

[00:29:05] **Ben:** Mm.

[00:29:09] **Tim:** another source of income, but like, if, if that had been my only gig, I would have starved, totally starved. and, and then another one, so this one is not coding related, but, just because of my wife's interest in special effects makeup and, you know, Georgia being, you know, sort of the Southeastern, you know, Hollywood, Yollywood of, of America, um, I had made friends with, there was a TV show here called, I think it was on FX, it was, it was called, It was a sci fi channel, it was called The Face Off, where they had like, it was a reality competition where they had like special effects makeup artists and they competed.

[00:29:46] **Tim:** Well, I became friends through just different channels with several of them, particularly a guy named RJ Hattie. and so we put together a, a conference that where we would teach, it was a three day, three day conference where we would teach people who are interested in like special effects makeup, Hollywood makeup, that sort of thing.

[00:30:05] **Tim:** Three days. You know, paid conference. I think people paid like six, 700 to do this, you know, to come to that. And, And I told him from the beginning, I'm like, listen, if we break even the first year, it's a win. And I guess he didn't hear that because, because we did break even, we did not lose money, but he, in his mind, it's like, he, you know, he wanted to get paid.

[00:30:27] **Tim:** You know, he's like, and then, so I, it was a failure for me, for me, actually, I thought we had, you know, we'd done good. And people are like, can you do this again? But he was so upset that he didn't make any money off of it. And part of it was because we, he had it at a, at a. The place was called The Engineer Guy, and The Engineer Guy sells like all the silicone, latex, all the stuff that is used for it.

[00:30:50] **Tim:** And, we just pulled from their stock and we weren't really selling it. The only thing we were selling was basically the membership. And so The Engineer Guy made a huge amount of money because like, while people were there, they were buying his stuff. He made a huge amount of money. And then the instructors were pulling from inventory to do their tutorials.

[00:31:09] **Tim:** And so we wound up, all the profit that we had wound up, we had to pay the engineer guy company for all the product we used during that. And that's where all the profit went. So there was zero profit. Had we not, had we had our own product and we're selling it, we probably would have made 30, 40, 000 off that conference.

[00:31:26] **Tim:** Him and I would have split, but we didn't. And so I'm like, listen, this is a win. We, you know, next time we'll know better. But he was like, no, we're not doing this anymore. He's like, if you want to keep the name, cause I had bought the domain name. I'm like, you know what, you take it, you have it. I don't, I don't care.

[00:31:40] **Tim:** And we never did it again. I think it was a shame. Cause you know, it's like, I see other folks that kind of took the idea that we had and they're doing it and being very successful with it, but.

[00:31:50] **Ben:** Oh, that's rough.

[00:31:51] **Tim:** Yeah. And he hasn't really spoken to me since. So that's kind of it. Cause we like, we, we, we were like tight. We had meetings every week and I enjoyed hanging out with him.

[00:31:59] **Tim:** He's a good guy, but yeah, I feel bad about it. I lost a friend and, but we didn't lose any money. So he lost gas money driving down there. So sucks.

## [00:32:08] Adam's Biggest Failures - Lack of Interest, Conference

[00:32:08] **Adam:** Well, I guess in some ways I'm going to call this a little bit of a personal triumph and that is that I don't tend to, dwell in my mortifications. So, I'm sure that, you know, several very negative things have happened to me professionally throughout my career, but I just don't, you know, I live in the moment.

[00:32:25] **Adam:** I think I've told you guys something similar to that, you know, many times. I

[00:32:29] **Tim:** Ooh, squirrel.

[00:32:30] **Adam:** I just don't, I don't sit around and introspect about, the recent past or the, you know, like, this is what's going on in my life today and this is what I'm gonna deal with, right? And then I'm gonna go have fun tomorrow and I'm gonna do the thing after that.

[00:32:42] **Adam:** Anyway, so I've been sitting here trying to rack my brain and I've only come up with two things that, I will put in the fail category. I don't think either one of them was like damaging, but they, I think they both had potential and for lack of skill or, or for lack of effort or something on my part, they just kind of petered out and went nowhere.

[00:33:04] **Adam:** So. the first one that I'm going to say is, do you guys remember, this was an open source project of mine, and I called it Ramen, as in the food. does that ring a bell for either of you? No? Okay, so, do you remember in Adobe ColdFusion, there was a way to add, like, custom, I think they called it extensions, to the, ColdFusion Administrator?

[00:33:28] **Adam:** Right, so you could, like, write your own code and then, like, it's like an XML file or something that you, like, pop in and it adds menu items on to the navigation bar on, in the ColdFusion Administrator. And so ramen was an attempt of mine. To sort of put together a package manager for ColdFusion. this was well before Forgebox.

[00:33:49] **Adam:** This was well before, you know, like, what is it, CommandBox, the CLI, all that. and the idea was, you know, people could, it's inspired by Node, right? So that you would have some sort of like a package JSON or something like that, that would describe the package. And then it would all just be hosted on GitHub, which they tell you you're not supposed to do, but you know, it's early days, I was just trying to like, proof of concept this thing, right?

[00:34:11] **Adam:** I'm not paying to put together like a CDN and all that junk, like let's get kicked off of GitHub before we start investing any money in this thing. Anyway, the idea was like, you know, you'd publish your thing, and maybe like send a pull request to the registry, and then your stuff would start showing up as like, one click installs inside of the ColdFusion administrator.

[00:34:30] **Adam:** and like, I remember I, like I set it up so that Taffy could be installed that way. I remember our friend, Nathan Strutz, gave me some support. You know, he was, I remember him talking about it. He might've submitted a couple of things to it. but it never really went anywhere. And I was, I was always very bummed about that.

[00:34:46] **Adam:** I felt like it had potential, but, You know, honestly, with the benefit of hindsight, I think that a good chunk of the reason why that didn't go anywhere is also a good chunk of the reason why I kind of just decided to move away from ColdFusion in general. The community is there. There are plenty of people that get paid to write ColdFusion code, but as a rule of thumb, which does not apply to everybody.

[00:35:13] **Adam:** So, you know, individuals who are thinking, Hey, that's not me. I'm, I'm super passionate. I'm not talking about you, but I'm talking about the other 99 percent of people. Don't give You know, they're, they, they show up, they write some code, you know, the, the five taggers or whatever, they write their code and then they punch out and they go home and they don't think about it and they don't care about open source and they don't care about going to conferences and they don't care about writing blogs and any of that, right?

[00:35:38] **Adam:** and, and it was, it was like a stake to my heart as a, as a passionate person to like be so invested in a community that didn't care to reflect any of that back. Um,that's, that's the first one that comes to mind. and then, this one is more local. So this is, I, I put on a conference with a friend and now, boss, Steve Rittler, who's been on the show.

[00:35:59] **Adam:** we, it was, we did just a very small local Philly thing. It was called Philly Merge. The idea was to get, entrepreneurial people and. Coding people together in the same space and like, what, you know, like, focus on that crossover, the, the, this merging of ideas, right? between the two and like, sort of fostering the relationships and trying to help each other, help each side, improve their, their skill set going in, in the opposite direction.

[00:36:29] **Adam:** and... It was successful in that we, like you said, it kind of, we broke even. We didn't lose money on this thing. We had t shirts made and the t shirts are nice. we still have a couple of them. and you know, overall, you know, I think it was pretty well received, but like, it became very clear to me that it was, this was very much outside of our mission.

[00:36:51] **Adam:** Right. It was just a thing that we were like, we could do that. Well, you know, I, I, I got hookups. I can get some space and I can, you know, get the word out enough that people would show up. And, you know, we probably had a hundred people show up or something like that, which was fine.

[00:37:05] **Tim:** Pretty good.

[00:37:06] **Adam:** and we had, you know, some local, the, the guy, I feel like a jerk cause I, our kids played together.

[00:37:12] **Adam:** The guy who started DuckDuckGo. I feel like I said, I feel like a jerk. Sorry. He's a, he's a Philly local, and we met through, Bar Camp Philly and did some parent stuff together for a while, among a, among a group of other parents, but, he was there and, and, he, was on like a panel for us.

[00:37:29] **Adam:** So he was like a, an angel investor type guy and that sort of thing. Anyway, so those are the first two things that come to mind. Like I said, I, I don't dwell in my, I've, I've forgotten the word.

[00:37:39] **Ben:** Failures?

[00:37:40] **Adam:** Well,

[00:37:42] **Ben:** Mortifies, is that what

[00:37:42] **Adam:** mortifications.

[00:37:43] **Ben:** Mortification.

[00:37:44] **Adam:** I don't dwell in my mortifications. so it's just, it's just not my personality, but, like I said, there's, I'm sure that there's a lot of skeletons in that closet that I'm just like, keep piling the skeletons on while I'm moving forward, right?

[00:37:56] **Tim:** Yeah.

## [00:37:57] Ben's Biggest Failure - Forcing OOP

[00:37:57] **Ben:** You know, all right. done a lot of things wrong in my time. Some, I don't know how wrong they actually were, but they feel wrong. One thing that stands out for me is I just spent way, way too long trying to wrap my head around object oriented programming. And I mean, years I spent trying to think about it.

[00:38:22] **Ben:** And I remember back when I was really early in my career, I just thought in my head, Oh, if I just do this for 10 years, then I'll know it at the end. And I don't have to worry about it. And I swear years went by and I'm just like, none of this made any sense. None of this felt like it was gelling or making my life any easier.

[00:38:42] **Ben:** And it just felt like such a waste of time in retrospect. You know, one thing that illustrates it I think so well is that early on in my ColdFusion applications, there's a SessionScope, which is basically just a struct that lives across requests automatically. And I used to create a SessionFacade component that would provide essentially methods for accessing data on the SessionScope. And like, it, it literally had zero value add whatsoever to the point where when I went and revamped my blog a couple of years ago, two, three years ago, basically ripped out all of this old, awful code that was really just componentizing simple data structures and replace them all with simple structs and arrays.

[00:39:34] **Ben:** And it just. Made all of the code so much easier to understand and maintain and, and edit and delete. And I just, what a, just, what a waste of time that all felt.

[00:39:46] **Adam:** I, I'm interested in the fact that you used SessionFacade as your example, because I feel like if there's one thing that people commonly do that actually could have been a good investment of that, you know, like the boilerplate y time, that might be the one that immediately comes to mind for me.

[00:40:06] **Adam:** Because so, like, if you, you know, you're, you're using SessionScope. And you're just trying to do something like, you know, a little startup product or whatever, and it goes viral and you need to scale up. Like, then you can change the implementation of your session facade from ins instead of using in memory session scope, you can tell it to use a Redis or whatever.

[00:40:25] **Adam:** to, to get external session data and, and spread that out. So now you're, now your sessions are, external to the, to the process and can be shared across load balance servers, right? So that one in particular, I think may, may not have been the best example, which is, you know, pot, meat, kettle, right?

[00:40:43] **Adam:** I'm, I'm terrible at examples when I'm on the spot, but,

[00:40:45] **Ben:** No, but I think, I mean, you know, even something like that, I think, become, can, can be of even a deeper problem. Meaning that if you think about how a request comes into the application, comes into the application CFC, I mean, this is obviously very CodeFusion specific. Like, so, Node people imagine that this is an Express or a Coast server and you're So

[00:41:11] **Adam:** HTML comes out the other side. Okay. Go ahead.

[00:41:15] **Ben:** you have your request coming in and it's usually some sort of very high level handler. And then it gets routed to some sort of a controller and the controller defers to something that contains more meaty business logic y stuff, um, whether that's through middleware or whatnot. So if you had something like a session facade.

[00:41:33] **Ben:** I think you would be more inclined to start passing that session facade around so that other things could use it, which I think it's like, you just start to go down this bizarre OO rabbit hole. Whereas what you could do at the top of your incoming request is just say, here's the cookie for this user.

[00:41:50] **Ben:** Let me go get the session data. And you could be going to the database. You could be going to Redis. You could be going to the session scope. And then you just pull that out as a simple data structure. And now you have that simple data structure. And you can pass that around. And

[00:42:04] **Adam:** I see. You're saying just push the, data read and write for the session data to the edges.

[00:42:09] **Ben:** yeah, yeah, exactly. and, you know, obviously other things have to click for things like that to happen, but it just, I mean, I had silly things, you know, just to give you a couple more examples, I had, an errors object. That literally wrapped around an array and stored the array of errors internally, but then added things like a size method instead of having a dot len.

[00:42:36] **Ben:** And like, for no other reason that the errors object was, and I'm air quoting here, semantically more meaningful. Then an array, but really it was just an array and that's how I wanted to use it. I just felt like I had to, I felt like I had to take everything that was a simple data structure and elevate it into an entity quotes, you know, entity.

[00:43:00] **Ben:** And it just,

[00:43:00] **Adam:** but, yeah, yeah.

[00:43:01] **Ben:** and it just like. It, it didn't add value and it made everything more complicated. And I just, I think

[00:43:11] **Adam:** Shame on you. Do you feel better

[00:43:12] **Ben:** the time, all the time that I spent trying to figure it out and that is time that could have been better spent.

## [00:43:19] Being Open With Failure

[00:43:19] **Adam:** Well, I mean, and let's not let it go unsaid that this whole concept is, exactly what inspired the triumphs and fails for this podcast, right? So that was like, that was the very first thing that we settled on for the podcast of life. Yeah. You know, we want to normalize failure and, and bring those to the forefront and discuss them and, you know, help people, make progress in their careers by, you know, understanding that this is just part of what everybody has to go through.

[00:43:48] **Tim:** And what I love. So we have like a, on our, discord, we have a channel called triumphs and fails. And like regularly people are posting in there, you know, pretty much on almost a daily basis, either a triumph or a failure, you can, we can rejoice with when they rejoice and cry when they cry. And I think it's great.

[00:44:04] **Tim:** I, what I'd like to see is, you know, some of our listeners, if they want to put their CV of failures out there, I think it, I think it'd be educational and instructive. Hmm. Hmm.

[00:44:14] **Adam:** Sounds like fun.

[00:44:15] **Ben:** And I think that there, there's a deeper thing here, which is that people feel shame in private and they feel like they are falling short in ways when they compare themselves to other people in their field and. When, when people talk about not only their successes, but also their failures and they talk about the conflicts that they have internally, you allow people to connect with that in a way that sort of gives them permission to feel the same thing.

[00:44:48] **Ben:** And I, you know, going back to my example here of, of taking simple data structures and wrapping them in complex object mechanics. I remember listening to a Rich Hickey talk. I'm sure I've brought Rich Hickey up like every 10 episodes or something.

[00:45:01] **Adam:** yeah,

[00:45:03] **Ben:** He, he has this great talk. I think it's the simple made easy talk.

[00:45:07] **Ben:** And, he, in his talk, he says, you just use simple data structures. Your language has simple data structures. You don't need to be creating lots of complexity on top of it. And hearing him say that it was like, okay, all of this conflict and shame that I feel internally about not being a quote unquote real programmer, because I don't understand object oriented programming, suddenly someone is giving me permission in a sense.

[00:45:34] **Ben:** To release that guilt and lean into the things that I'm finding most effective. And there's a real power in that.

[00:45:43] **Adam:** for sure. We need like a Instagram, but instead of like, it's all, you know, everybody posing and, and trying to make it look like they're super rich and, Super influential and they got a brand deal with whoever or whatever. Like, it just needs to be like Instagram for failure,

[00:46:01] **Ben:** It's,

[00:46:01] **Adam:** failure influencers.

[00:46:03] **Ben:** I mean. So I've brought this up a couple of times in general, just this idea that you build this mental model in your head about how you think somebody intended something. And then it turns out years later that that's not actually how they intended that to be understood. And now you've had this misconception for years.

[00:46:22] **Ben:** And I remember, you know, TDD, test driven development obviously is very popular. It's been very popular for, I want to say maybe the last, like, 10, 10 ish years or so. and I remember when it first came out, everyone was like, Oh yeah, TDD. You have to write all of your tests. Absolutely. First, that's exactly how it has to be done.

[00:46:41] **Ben:** You can't do any code until you have tests that are failing. And then I remember years later, and this is maybe like four years ago, five years ago, I was listening to an interview with a guy who is like part of the whole TDD craze. And they were saying, well, what do you do when you're not even sure what your application is supposed to do?

[00:47:00] **Ben:** Like you're, you have a very rough idea in your head and you don't even know what your code should do. How do you write tests? He goes, well, I wouldn't write tests at that point. That's crazy. Like, I don't know what the application is supposed to do. How can I possibly test it? And you're like, holy There's a whole world of programmers out there who didn't have that nuance, and now think that day one, you have to write tests as your very first thing, because they didn't understand where you were coming into that. And I just... Oh, sorry. I'm getting all worked up now.

[00:47:27] **Adam:** What you're, what you're talking about is the gap between knowledge and wisdom.

[00:47:31] **Ben:** Yeah, definitely.

[00:47:34] **Tim:** I'll put this out rather than a individual level, like at a company level. So one of the things that Constellation does, they, you know, we buy our competitors, you know, we, they, yeah. and it's like

[00:47:47] **Adam:** It's a nice business you got there. Be a

[00:47:48] **Tim:** Yeah, nice.

[00:47:49] **Adam:** along and bought it and shut you down.

[00:47:52] **Tim:** No, we don't shut them down. So they're a buy, they're a buy and hold strategy. They, they don't shut them down.

[00:47:55] **Tim:** They don't change the name. They don't change, they don't change the leadership if they're doing good.

[00:47:59] **Adam:** all the money goes into one bucket instead.

[00:48:01] **Tim:** Yeah. And, so it's like we had to, in fact, I'm drinking out of one of their, uh, InsureSoft. They were for years, they were like our biggest competitor in, not the payment space. This was the insurance space and, they got bought several years ago.

[00:48:14] **Tim:** And yeah, I just sort of had this whole like shiny vision of how amazing they were. Like their, their, their corporation was like a well oiled machine and they became part of the family. Like, you know, part of the thing you do is like when you're looking to buy them, you do like a code review. And, so we're looking at their stuff and I'm like, Oh my God, they're using Visual Basic

[00:48:35] **Ben:** Yo,

[00:48:37] **Tim:** and I looked at, I mean, it wasn't bad Visual Basic, but I'm like, there's no, well, I, I shouldn't say anymore, but it's, I'm like, yeah,

[00:48:44] **Adam:** you going to say there's no good visual basic?

[00:48:46] **Tim:** no, no, no, no, no, I can't.

[00:48:50] **Tim:** Anyway, so it's like you realize, you realize, you know, it's like you, you, from the outside, when you see someone who, who seems successful, all you do is like you assign positive. Traits to that person beyond what, what they do. And then it's like the more and more companies we bought, it's like, we realized all of us have the exact same problem.

[00:49:09] **Tim:** All of us really kind of suck at what we do. And it's like, we're, we're trying to cover over our flaws. And so it's like, I think that's just, I think that's why it's important to be. Open and honest with other, other people. It's like, it makes, it makes you more relatable when people are like, you know what, we're not perfect at everything.

[00:49:29] **Tim:** We, you know, we fail at stuff because if you, if you put on the posture that you're, you know, perfect, the second anyone finds it, a flaw, it's just amplified because you're not, you're not what you've been sold.

[00:49:42] **Adam:** Yeah, for sure.

[00:49:43] **Ben:** there's gotta be a cognitive bias for that where, so there's, so there's imposter syndrome, which is where you think that you're a fraud and you don't know what you're doing and you assume other people are smarter. But I feel like there's a macro version of that where it's my company doesn't know what the hell we're doing.

[00:50:00] **Ben:** And every other company has all of this stuff locked down. It's, it's. It's something bigger than imposter syndrome, but I've never, I'm not quite sure what it is.

[00:50:10] **Adam:** But it's still, it's still a personal feeling though. Right.

[00:50:12] **Tim:** submit, submit a paper on it. It might, it might get accepted.

[00:50:16] **Adam:** You don't feel it as an organization. You feel it as a member of that

[00:50:19] **Ben:** Right. Right. Absolutely.

[00:50:21] **Adam:** Well, this topic really got away from us and, and, we, we went pretty long on this, so what, you know, we're, we're just going to have to save, the other stuff, Ben, you wanted to talk about premortems and I wasn't going to talk about the, the lost art of, log levels.

[00:50:34] **Adam:** So we'll just have to save that content for, for later. so, I'm just going to

[00:50:38] **Tim:** we, we, we failed at doing a potluck. Congratulations.

[00:50:42] **Adam:** so I'm just gonna, you know, take us through the off ramp here.

## [00:50:45] Patreon

[00:50:45] **Adam:** So, this episode of Working Code is brought to you by Tim's acouchi.

[00:50:47] **Adam:** acouchi.

[00:50:48] **Adam:** acouchi

[00:50:49] **Tim:** What? It was spelling bee?

[00:50:53] **Adam:** And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Why do I always touch the corner of my glasses as I'm like reading the outro? I'm like, read it. Okay, grab this side.

[00:51:05] **Adam:** Now grab this

[00:51:06] **Ben:** it makes you look very intelligent.

[00:51:08] **Adam:** Yeah, gotta

[00:51:09] **Tim:** spelled acouchi right, by the way. That's amazing. Did you Google it?

[00:51:12] **Adam:** No, I just guessed. Anyway, more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing costs and our transcription costs, and we couldn't do this every week without them.

[00:51:25] **Adam:** So special thanks to our top patrons, Monte and Giancarlo, you guys rock.

## [00:51:29] Thanks For Listening!

[00:51:29] **Adam:** I have no idea what we're gonna talk about on the after show, but I'm sure it will be... Delightful, not at all mortifying, and not at all a failure. And if you would like to, find out what we talk about on the after show, your your time for getting a free trial of our Patreon is running out.

[00:51:45] **Adam:** End of the calendar year, end of 2020. What year is it? Three? your your opportunity for getting a free trial of our Patreon is gonna go away, so, get in there. And, find out whatever we talk about after this. if you want to do that, you can go to patreon.com/workingcodepod. I'm gonna say, I'm gonna throw in a plug here for our Discord.

[00:52:04] **Adam:** Go to workingcode.dev/discord. Come join the community. Talk to other like minded developers. Share your triumphs and fails. share pictures of your acouchi. And,

[00:52:16] **Tim:** bad.

[00:52:17] **Ben:** to look up. What does an acouchi look like?

[00:52:20] **Tim:** Careful, careful, buddy. Going in incognito mode.

[00:52:24] **Adam:** alright, alright, alright. That's it for this week. We'll catch you next week, and until then,

[00:52:29] **Tim:** You guys, you guys, listen, listen, listen. You guys, you're not a failure. Your heart matters.
