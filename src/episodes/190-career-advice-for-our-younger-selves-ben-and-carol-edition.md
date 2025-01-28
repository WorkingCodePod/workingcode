---
title: "190: Career Advice For Our Younger Selves - Ben & Carol Edition"
description: "In this week's episode, Ben and Carol of the Working Code Podcast reflect on career advice they would give to their younger selves."
date: 2024-08-07
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/190-career-advice-for-our-younger-selves-ben-carol-edition/id1544142288?i=1000664582557"></iframe>

In this week's episode, Ben and Carol of the Working Code Podcast reflect on career advice they would give to their younger selves, touching on the importance of simplicity in coding, continuous learning, and maintaining work-life balance. They emphasize the significance of learning from mentors, leveraging database constraints, and avoiding premature optimization.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/190-career-advice-for-our-younger-selves-ben-and-carol-edition.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Carol:** and I had someone explaining me how to, like, explaining to me like how you get data from the database, right? So it's like select star from said table, right? He's like, go ahead and start typing that.

[00:00:10] **Carol:** I'm like, select S T A R and he goes. Oh, God, you don't know anything, do you? And I'm like, I know nothing. He's like, all right, let me sit down. Let me sit down for this one.

[00:00:26] **Ben:** Diane, clear my meetings.

[00:00:27] **Carol:** Yeah.

## [00:00:48] Intro

[00:00:48] **Carol:** Welcome to episode 190 of the Working Code Podcast. And today you've got Ben and myself, and we've decided to, piggyback on what adam and Tim gave you last week, and we're going to talk about some of our career advice that we would give our young selves if we had the opportunity. But before then, we'll do our normal and kick it off with a Triumph or fail. I guess I'll keep going first.

[00:01:11] **Ben:** Hit it.

## [00:01:12] Carol's Triumph

[00:01:12] **Carol:** I feel like I am going to throw in a big giant triumph. And the triumph is just that I've made some decisions on how I'm going to lead my team. And I want to lead by example. And I had a conversation with another architect.

[00:01:26] **Carol:** Shout out to Jason for this, you know, advice here. We were talking about some things we wanted to do to keep our developers engaged and feel like we are able to help and just be honest about everything going on. And one thing that we struggle with at work is our laptops, just like the blue screen, they just enjoy dying.

[00:01:47] **Carol:** So if you're not constantly pushing your code at any day, you risk losing a lot of work, depending on how Like how much you have stored that you haven't pushed to, um, GitHub. So as much as I have always hated pushing like broken code and pushing up debug and exposing myself to show people, I have no idea what I'm doing in Knockout because if you just look at all my console logs and debuggers, you'll know that I'm pretty stuck, right?

[00:02:15] **Carol:** I've decided it doesn't matter. I'm just going to do it, but every day I'm going to push up my work and expose myself and let it be okay. And I'm going to reach out when I need help to my team. So like I was stuck on something and instead of just kind of plowing through it, because I know they're busy. I reached out and was like, Hey, can you guys help me with this?

[00:02:31] **Carol:** Cause I want them to feel like they can always come to me and ask for assistance, ask for, you know, guidance on how to do something. And I want them to know that as much as they trust me, I trust them to, to help me out. So I've decided to just lead a little better and set up some things that can be scary, like pushing up broken code, but I'm okay with it.

[00:02:55] **Ben:** Yeah, I think being vulnerable. I mean, I think you're, you're even over, it's not as bad as I think you're making it out to be in your head, but, but being vulnerable, I think sets a good precedent in general for any kind of a team setting.

[00:03:11] **Carol:** Completely agree.

[00:03:12] **Ben:** It reminds me, someone made a, took a photo of a printout. This was like a couple of years ago.

[00:03:18] **Ben:** And it was, I guess, for an office. And it was like, in case of emergency, get, commit, push, and then leave the building.

[00:03:23] **Carol:** Oh, I love it.

[00:03:24] **Ben:** And I remember seeing that there were a bunch of people in common thread got really offended by this and like, took it way too seriously and were saying like, oh, like disregard for human life and code shouldn't be that important.

[00:03:37] **Ben:** I'm like, first of all, it was a joke, I'm sure.

[00:03:40] **Carol:** Yes,

[00:03:41] **Ben:** But also You know, code's important

[00:03:45] **Carol:** it is.

[00:03:47] **Ben:** to your point.

[00:03:48] **Carol:** Yeah. Yeah, I mean, it hit me hard when my laptop started blue screening, cause I hadn't really pushed much up. Like I'd pushed up a few things just to show people what I was working on, but I was on a lonely single developer island just doing my thing. So I really didn't have a big need, but once it started happening, I'm like, Oh, I need to get my code up there because if this thing doesn't turn on tomorrow, This is like three months worth of work that's just gone.

[00:04:12] **Ben:** Does anyone know why these computers are just randomly failing? Are they old? Or is it this, I don't know. I mean,

[00:04:19] **Carol:** No, it's not that they're old. Our theory is that it's a mixture of forced applications on there that don't play well with the operating systems and they basically put their own image on it. Like our approved image goes onto it and something within those images just Isn't very well like defined. We don't actually know what causes it, but that's our theory, that it's a bad government image that they just put on everything and yeah,

[00:04:46] **Ben:** Yeah. Things are just getting very complicated. Macs have, I think, historically been seen as very stable. But even on the Mac, I've had a lot of times where I'll be at my desk, everything's working perfectly. I go to make my lunch in the next room and I come back and it says that it's restarted or my, my screen has crashed and says it had to restart my monitor or I don't know, something.

[00:05:08] **Ben:** And I feel like that's been happening a lot more than it's ever happened before. And to your point, I'm on an M1 Mac, so maybe this is just a difference between the new chip architectures and some of the old programs and the fact that I'm running off of a backup of, of an old, of an older computer on a different architecture.

[00:05:27] **Ben:** I don't know how any of it works. It's all magic to me, honestly.

[00:05:30] **Carol:** it turns on that's all you care

[00:05:31] **Ben:** Yeah, that's all I care about. The battery's not exploding. That's a kid. That's, that's a key factor.

[00:05:37] **Carol:** Again, didn't you have that happen?

[00:05:38] **Ben:** Yeah, yeah, yeah. I had that happen. That's why I'm on one Mac now.

[00:05:42] **Carol:** All right. Well, that's my big win when you got Ben.

## [00:05:45] Ben's Triumph

[00:05:45] **Ben:** I'm also going to go with the Triumph. I had mentioned that, I don't know, like two or three weeks ago, I had went to a meetup, which is the first meetup I've been to in like three years or something, well, I went to another meetup on this Tuesday. So today's Thursday. So two days ago, I went to a very casual meetup.

[00:06:05] **Ben:** It was basically just. Six of us at a diner eating dinner together and talking about technology. And, it was just really enjoyable. And I, when I lived in the city, New York city, I never wanted to do meetups like this because it was always like, Oh, we'll meet up at this bar and we'll talk about technology.

[00:06:25] **Ben:** And I'm like, I don't want to hang out at a bar with you people. I don't know you. The bars are not my scene, but I'm, you know, in the boondocks now. So you go to the diner, we went to a diner on Tuesday night. It's 250 capacity diner, as it says on the, you know, the door.

[00:06:42] **Carol:** The fire

[00:06:42] **Ben:** uh,and there were like 12 people in the diner.

[00:06:45] **Carol:** And you guys were like six of

[00:06:47] **Ben:** yeah, yeah. I'm like, Oh, this is my scene. So I just had a really very lovely time meeting, even in a small group of six people, it was actually quite a diverse group. It had two guys who were already retired and they're just love to talk about programming. And then we had some young guys and then there was another guy who was kind of my age and he's actually trying to get into the technology industry coming from the finance world.

[00:07:13] **Ben:** So it's just. It was just a nice time.and, there was some validation for me because I felt like I had something to contribute, even if not in depth, but I had something to contribute in every conversation. And the reason that that feels very validating for me now is because I do come under some heat occasionally for maybe being too focused on a particular set of technologies, but I do try to keep my finger on the pulse of a lot of different things and.

[00:07:45] **Ben:** Even if that's done in such a lightweight way, it does seem to allow me to participate in conversations that are much broader than the things I focus on primarily. So I felt, patted myself on the back a little bit for

[00:07:58] **Carol:** Aww. I'm happy for you. So I remember, I feel like maybe a year ago, it might not have been that long ago, you were taking a train ride in to somewhere to do a meetup or to meet with someone to talk about tech. And you had a really good time because I think you decided to stay the night or not stay the night.

[00:08:16] **Carol:** I just remember how happy you were, like that you got to meet with someone and talk about tech, like have dinner and talk. Yeah.

[00:08:22] **Ben:** I think it, I don't even remember what that was. And it was probably, it was probably longer ago than we realize.

[00:08:27] **Carol:** Yeah. We've been doing this a few days.

[00:08:31] **Ben:** Yeah. But here's, okay. So here's a very interesting thing about this group of people. So one of the guys there. I'm guessing that he was,

[00:08:38] **Carol:** step back. Are these people, you know, from work? Is it just a random meetup?

[00:08:42] **Ben:** this is from meetup. com.

[00:08:43] **Carol:** Oh, cool. Okay.

[00:08:45] **Ben:** So one of the guys there, I'd never met any of them before. One of the guys there, I want to guess he was maybe in his late sixties or maybe early seventies. He's retired, but he also is publishing Sudoku books on the side for fun. And he's using computer programming to generate the Sudoku puzzles.

[00:09:07] **Ben:** And I asked him, I said, what do you? Yeah, it's really cool. I said, Oh, that's really interesting. What are you, what language are you using to generate these puzzles? And he said, he's using Pascal. I've never used Pascal, but I think it's Pascal. Been around for like a million years.

[00:09:21] **Carol:** Yeah.

[00:09:22] **Ben:** And I said, I said, that's so interesting.

[00:09:24] **Ben:** There's so many languages now. What is it about Pascal, Pascal, Pascal, whatever, however you pronounce it, that makes it particularly good for this particular problem? And he said, what makes it particularly good? Is it was the first language I learned,

[00:09:40] **Carol:** Oh, I love that.

[00:09:41] **Ben:** you know, and, and I think that just goes to show how I think we fool ourselves so often into thinking that, Oh, we chose this particular technology because it was the right tool for the job.

[00:09:54] **Ben:** And I'm so thoughtful and academic about how I approach problem solving. And I think more often than not, it is just, this is the thing that I learned and this is the thing that I know. And it is therefore the thing that I use. And I just love the fact that he is making money because he's selling these books, he's got a publishing deal and everything, he's making money using a programming language that I think has been around since like the seventies.

[00:10:19] **Carol:** It's old. Yeah. Yeah. When I hear Pascal, I think of, like, Cobalt. Like, I think of some really old technology. Things I've never touched and never even, like, had the urge to go figure out or look into.

[00:10:32] **Ben:** Yeah, absolutely. Absolutely. So anyway, I had a great time.

[00:10:36] **Carol:** That's awesome. So you were talking about how, you know, he was using it. Cause it's something that he's just, he knew, right? Today when I was debugging some code, I was looking to the left and just typing in Visual Studio while I was like looking at what was going on in the screen and without even thinking about what I was trying to do, because all I was really trying to do was see what the data looked like and that's a watch.

[00:11:00] **Carol:** Like I just. Put a break point and I could see the data. I just typed CFDOMPVAR and I went, I like look back at my screen and look back toward like the interface. And I was like, I guess like muscle memory really is a thing and some stuff just never goes away. I was like, why would I ever like, I haven't, I don't know the last time I've like tried putting CF code in anything, but the immediate thought was what is this value and it was CFDOMPVAR and I was like, Oh no, that's not what I want.

[00:11:31] **Ben:** Well, to piggyback on that for a second. So one in the discord chat, again, I was getting a little bit of shade thrown at me for being too focused on a particular set of technologies and someone, a couple of people brought up a PHP and I have purchased a Udemy course on PHP and I've been watching it just, you know.

[00:11:52] **Ben:** My spare time when I don't wanna do anything else, and they have a var dump function for dumping out

[00:11:59] **Carol:** Uh huh.

[00:12:00] **Ben:** I, I haven't looked at it very much in depth yet. I've, I've just been going through the video. I figure my next step will be to try to set up a docker environment. So that I can do a little playground work with PHP.

[00:12:11] **Ben:** but I just wanted, people in the discord to know that I am listening and I see you and I am trying to become a more well rounded person

[00:12:21] **Carol:** Why did you pick PHP?

[00:12:24] **Ben:** because that's what someone mentioned and it still runs like 70 percent of the web or something.

[00:12:32] **Carol:** Let me know what you think when you learn it. I never took the time to learn it, but I've also never had an urge to learn it.

[00:12:39] **Ben:** It's interesting. I mean, I'm only like an hour into this course, but already there are things that I don't like. And it's so hard, you know, you get so anchored into the things you already know. So what I know is ColdFusion. So everything I'm learning about in PHP, I'm constantly translating. Okay. This is how it would work in ColdFusion.

[00:12:57] **Ben:** This is how it works in PHP. And PHP, there's a difference between single quotes and double quotes. And I'm immediately like, Oh, this is garbage. But like, I guess you just got to get used to it. Cause other languages work that way too.

[00:13:13] **Carol:** Yep. A lot of them work that way.

[00:13:15] **Ben:** I just, I, it's one of those things where I feel like ColdFusion made a lot of really good choices in terms of keeping things simple and not over complicating weird nuances.

[00:13:27] **Ben:** They also made a lot of mistakes. I don't want to sugarcoat it, but, you know, Even just outputting stuff in PHP, and maybe this gets covered later on in the course, but it's like you gotta do less than sign question mark, PHP, and then you gotta close it with a question mark greater than sign. And then inside that you have to echo and, and write things out.

[00:13:48] **Ben:** And I just freaking love the fact that you can wrap an entire ColdFusion page and CF output and then just do pound signs to output things.

[00:13:55] **Carol:** It's like magic,

[00:13:56] **Ben:** It's so easy. It's so little syntax. And, anyway, you know, like I don't want to go into judgy judgy because I'm trying to learn and embrace, but you know, that's how, that's how you learn new things as you translate from old.

[00:14:11] **Ben:** And, and, anyway, so Discord people, thank you for pushing.

[00:14:15] **Carol:** And the whole, like you said, there were goods and bads, right? There are good and bad decisions made within how CF was designed. I will always stand by, I can't imagine learning to write like web applications on anything before I did Codefusion. Like the way that I was able to just kind of Get concepts working, could very quickly understand it.

[00:14:40] **Carol:** Things worked because they weren't really type driven. So it didn't really matter, like how it went through, like, as long as it seemed right, it was okay, usually. So I love that I was able to learn key concepts and like, understand how to become a software engineer using it. Cause any other thing is so strict that I don't know that I would have felt like I had the freedom to branch out.

[00:15:01] **Ben:** Yeah. A hundred percent. I love how the language is both strict and loose at the same time.

[00:15:08] **Carol:** Well, I think that's a good, a good spot to turn into our main topic here.

## [00:15:12] Career Advice We'd Give Ourselves

[00:15:12] **Carol:** So career advice we'd give ourselves, I guess. Number one, always learn on ColdFusion. It's the right way to go.

[00:15:18] **Ben:** yeah,

[00:15:19] **Carol:** Young Carol, learn ColdFusion.

[00:15:21] **Ben:** yeah. Coldfusions rocks. It's funny. I think one of, Adam's one was always bet on JavaScript. And I, and I, I do love JavaScript. I write JavaScript. Actually, I'd say more than half the time that I spend at work. I'm writing JavaScript. but yeah, I just freaking love Coldfusion.

[00:15:39] **Carol:** so do you want to do like a alternating back and forth? Yeah. Okay. Why don't you kick us off?

## [00:15:45] Breakthroughs Do Not Equal Progress

[00:15:45] **Ben:** All right. Here's something I've been thinking about lately, and I think it is a trap that I fell into a lot in my career, which is that I conflated the notion of a mental breakthrough with feeling like I'm moving in the right direction. And what I mean is I did a lot of things.

[00:16:05] **Ben:** Simply because they were challenging, but didn't actually end up being a real value add. And in fact, overcomplicated a lot of the things that I, that I did. if I could do like a case in point when I was learning less CSS, so less as a, as a CSS preprocessor, like Sass, One of the things that I learned how to do in less CSS is you can actually evaluate JavaScript code inside of CSS preprocessors.

[00:16:33] **Ben:** And it's not simple, it's not simple. And it's like a really weird syntax and it, and like, it has all this weird evaluation constraints. And, I remember figuring it out and feeling really proud of myself that I had figured it out and that made it feel like I was moving in the right direction. And I think I tried to use it a couple of times.

[00:16:54] **Ben:** And at one point I was just like, this is stupid. Like, I don't want to write JavaScript in my CSS. Like that was clearly the wrong direction to move in. But it was, it, sometimes we embrace things and I don't know if it's like a sunk cost fallacy. It's almost like, I don't know how to describe it well.

[00:17:13] **Ben:** Other than to say, just because you could figure something out doesn't mean you should use it. And in fact, if it was really hard to figure out. That might be a sign that you shouldn't use it. Yeah. So that's, that's going to be my first big. I fell into that pit many times in my career.

[00:17:31] **Carol:** oh man, I think we all have been like I think we've all been there where we you know Dug our feet in the sand and we you know plowed through it and figured out how to make it work Like it works, right? And we're so happy that it works now, but in reality, it working is a really bad thing that we wrote it this way, any, we just had this conversation at work with me and another engineer about like, You know, we use Knockout, which is really old and it's whatever, but it's a view model, view model, whatever, of how you basically get your data and stuff.

[00:18:09] **Carol:** So all your data like becomes these observers and you're able to then like see what's happening. Like it's really neat how we, how it's used, but I definitely think we could do. Better and have other options, but that's not for here. but ultimately like we had pushed a observer into an observer. So the only way to get to the data was to be like data.

[00:18:31] **Carol:** thisdata. latestvalue. latestvalue. latestvalue. Because we're into like 3D. And I was like, you know, this is probably a pretty good indicator that we're using this data wrong. If we're having to like three layers down, go get it. I was like, and this is also why it's not able to be linked in the, like in the view, because now the model doesn't really know what it is.

[00:18:53] **Carol:** Like we're not using the real model for it. So it was one of those, like, I think that developer was like, yeah, I didn't really know what I was doing wrong, but something was wrong and I just went with it. I'm like, well, just a side note. If it says dot latest value, dot latest value, anything else, you've got a problem.

[00:19:08] **Carol:** Yeah.

[00:19:10] **Ben:** this is one of the solid principles, right? S-O-L-I-D. what is it? L is like the Liskov's. No. Yeah, right. The Liskov substitution. No, no. Lisc. What is it? There's one where like, you can only have one.in an expression. You can't do dot something, dot something, dot something because

[00:19:27] **Carol:** Oh, that's awful.

[00:19:28] **Ben:** You're too tied to the implementation,

[00:19:31] **Carol:** See, I enjoy my dot dots, so we won't fight about that one.

[00:19:36] **Ben:** but it, it, it feels a little bit like, they, they say, if you go on a cruise that they, there's some psychological trick where the first night, the buffet is amazing. And the last night the buffet is amazing. Cause that's what people are good at remembering the first thing and the last thing, and they don't remember the whole middle journey and that's kind of this mental hack you play on yourself.

[00:19:57] **Ben:** Where you're so happy that you finally solved the problem that you forget to question whether or not you should have solved it in the first place.

[00:20:06] **Carol:** Yeah. Oh man, been there.

[00:20:09] **Ben:** All right. So what do you got?

## [00:20:10] Work For a Good Home Life

[00:20:10] **Carol:** I have to go with something that took me a long time to learn was that you do a job. To have a great home life. Like, for me, like, I worked, like, for years just so that I could feed my kids and they had a roof over their head and they could play all the sports that they wanted to.

[00:20:29] **Carol:** And there were years, I will say years, because there were multiple of them, back to back to back, where I was so stressed at work that I came home And would crash and kind of just miss out on a lot of opportunity to just be happy with my kids. So if you're in a job that is preventing you from enjoying your life, you probably have a problem and should look for something else.

[00:20:56] **Ben:** It, it, it's really interesting that you bring that up because I think I, Adam mentioned this on one of the earlier podcasts that the four of us were picked in a way because of how driven we were and how You know, the idea of being part of a podcast was, was part of what made us who we are and we're very driven and we're very productive people and want to get stuff done.

[00:21:20] **Ben:** And so it's, it's, it's, we're almost a little bit skewed in how we view things. And one of the podcasts I was listening to, which I just recently discovered, I really love it's called Pivot. It's,

[00:21:30] **Carol:** Pivot,

[00:21:31] **Ben:** Yeah, it's by the Vox Media Network. I think it's Kara Swisher and, and, I'm kind of blanking on his name, Galloway, something Galloway, Scott Galloway.

[00:21:41] **Ben:** Thank

[00:21:42] **Carol:** Mm hmm.

[00:21:42] **Ben:** And they had an episode just recently where Kara Swisher was talking about her son and about the younger generation and how they have a much better work life balance and Scott's pushback to that was. It's really easy for us to say that, us being he and Kara Swisher, because the two of them worked their asses off for 40 years and now have been very successful and are mostly financially independent.

[00:22:12] **Ben:** And they can, it's like, it's easy for them to appreciate the work like balance and forget how much work they put in. And so it's hard because you've done so much work to set your kids up for success. And to then say to the younger generation, don't forget to relax and have fun. But it's like a counterfactual, you know, like, could you, could you look back and say that if you had relaxed and had fun?

[00:22:41] **Ben:** And I'm, and I, and I'm not saying this to diminish because I also often, I do feel like I missed out on a lot of stuff because I also worked very hard, but I don't know. I don't know if I couldn't have worked very hard. I feel like that's just who I was.

[00:22:54] **Carol:** Yeah, I also saw a lot of people who were doing very little, still succeeding.

[00:23:00] **Ben:** And,

[00:23:00] **Carol:** Like, we were still making the same salary. We were still, you know, getting the same, you know, work assigned or whatever, but. You know, I kind of moved up the chain faster and had more responsibility. Same pay, just more responsibility and less of a nice home life.

[00:23:18] **Carol:** So I guess, I guess kind of looking back, right? Like it's okay to have those moments at a job. Where things are just crazy and you have a month of pure chaos and you don't know if you're going left or right. But if that takes up multiple years, I think it's time that you move on and find a job that's slightly less chaotic so you can enjoy life with your family.

[00:23:45] **Ben:** and, and I, and again, like, I'm not, I'm not pushing back at all. I, I, I do think having good balance is important. I do love the fact that I think people in general are moving away from this sort of suicidal work effort level. I've, I've been watching this show. I don't think it runs anymore, but it's on Netflix called Suits.

[00:24:08] **Ben:** And it's about

[00:24:09] **Carol:** I love suits.

[00:24:10] **Ben:** yeah, I'm, I'm quite enjoying it. And, I'm, I'm like, I'm a third season. And at least in the first two seasons, they really make a lot of references to how much lawyers work. There'll be like, there's one scene where guys, guy's like, where have you been? It's eight o'clock. And the guy's like, yeah, but we started at seven 30, so I'm only half an hour late.

[00:24:30] **Ben:** And he's like, no, we started at seven 30, which means that you should have been here half an hour before we started, so you're already an hour late. And then people will be leaving and some will be like, yo, where are you going? It's only 10 30 at night. We got work to do and, and. Like I could, even when I was working my hardest, I was never putting in that kind of time.

[00:24:48] **Ben:** Like that to me is just insane. I don't know how anyone has the capacity to work like that for so long.

[00:24:57] **Carol:** Then you will be probably not very shocked to know that through the majority of my 20s. I would work all day if I had the kids, like, cause we did split custody, right? So I would, if I had the kids, I'd go pick them up from school. You know, we'd do what we had to do, get them in bed. Then I would work four, five, six hours, you know, more.

[00:25:21] **Carol:** I would sleep like three or four hours.

[00:25:23] **Ben:** goodness. No.

[00:25:25] **Carol:** it wasn't, it wasn't the best situation, right? But it's, I felt like it's what I had to do in order for my company to succeed. And I was very invested in their success. So,

[00:25:36] **Ben:** mean, that's pretty amazing that you could put in time like that. That's. That's super human.

[00:25:41] **Carol:** It wasn't healthy. That's why I have wrinkles now. Alright, let's see.

[00:25:50] **Ben:** my turn.

[00:25:50] **Carol:** Yeah, yeah. You do one now.

## [00:25:52] Keep it Simple

[00:25:52] **Ben:** so I have several times on this podcast mentioned. Rich Hickey, he's the inventor of Clojure, and he has some very well received presentations on YouTube, and I'm just going to reference it again, because I think it is so impactful, and it's one of these things that I wish I had learned really early on and took to heart, which is just to learn.

[00:26:18] **Ben:** Keep things simple and to keep your data structures simple and to not get, I mean, I'm probably going to get flack for this, but like to not overemphasize things like object oriented programming when simple procedural code and, you know, arrays of structures would be 100 percent adequate. There was a lot of my career, I'd say years of my career where I was so focused on object oriented programming as this.

[00:26:48] **Ben:** Achievement that I had to reach. This understanding goal that I would somehow make me a real programmer if I could finally understand object oriented programming and use it all the time in my, in my applications. And I think it was just such a waste of time. and, and it really wasn't fruitful. And I think the problem was, is I was just trying to overcomplicate things for the sake of the complexity, because I thought the value was almost in the complexity and I could have built.

[00:27:21] **Ben:** Better, more maintainable applications if I just kept it much more simple. So the keep it simple, stupid kiss, as they say, or keep it super simple. If you're more family friendly, but just kiss, kiss, kiss all day.

[00:27:37] **Carol:** hundred percent. Like I wish I would have like thought through that early on in my career. I can't tell you the number of times I've went back and look at something I'd written, you know, in the past and went, why the heck did I do that? Like we had a process that was working. Yes. I could make it a lot more complex and work more efficiently.

[00:28:00] **Carol:** But it was working and everyone understood it. And now I have this process that no one can figure out, that no one understands and I'm stuck supporting it because I'm the only one that understands how my brain works. Yeah. Yeah, absolutely. I got a call the other day was like, Hey, just thinking about you.

[00:28:18] **Carol:** I see your name all over the code and I'm not for sure what it's doing. So I'm just thinking about you. I'm like, I probably could still explain it to you, but you can learn it. You're good.

[00:28:31] **Ben:** Absolutely. I I've, I have code, not that I've had to touch in forever. But I've written code that was so bad. I think it basically killed a project that I was working on. It was so over budget and so over time. And I I'm sure no one else came in after me and could figure out what the hell I was thinking when I put this thing together, I was just, I was basically just throwing stuff against the wall and seeing what would stick.

[00:29:01] **Ben:** And, and contorting myself around the complexities of the code in order to make something work, instead of saying, maybe I should just remove the complexity. Oh my God. It's, it was such hot garbage.

[00:29:14] **Carol:** Now, I will say now at a bit of, you know, admit my age, I'll be 40 at the end of the year. So me, now at 40, I get really happy when I remove complexity and processes and I can make things readable and they still function correctly. Like, breaking out these giant functions that do too many things into very small ones that can then be called from other pages to do that little piece of work.

[00:29:42] **Carol:** Yay, I'm happy!

[00:29:44] **Ben:** you know, it gives me so much joy kind of along those lines. I can't tell you how much data I have processed. By creating a little standalone ColdFusion script that does a little bit of work, writes some data to a text file. And then literally writes a set timeout in JavaScript that refreshes the page in 200 milliseconds and then basically continues on with that work.

[00:30:09] **Ben:** Well, like read in data from the text file, do some more work and then write data back to a text file. And it's so janky, but it's so Easy. Processes so much data. It's, you know, compared to like, Oh, you know, all we have to do is, spin up a Hadoop cluster and do some map reducing over this, you know, gigabytes of data and we'll get some, we'll queue up some data.

[00:30:33] **Ben:** I'm just like, bro, I got a, I got like a hundred lines CFML file that refreshes itself as long as I keep the browser open.

[00:30:44] **Carol:** I love that. I love it.

[00:30:46] **Ben:** know, using, using.

[00:30:47] **Carol:** things.

[00:30:48] **Ben:** Using an auto refresh browser tab to get work done. It's like the jankiest of jank, but it, dang it. If it does not get it done.

[00:30:57] **Carol:** So, there was a girl I work with who was trying to get tickets to something and she had no idea that you could install like an auto refresh extension in Chrome that would just refresh the page. So we were in this meeting and she's just clicking, clicking, clicking, and I got tired of the click. So I just sent her a link.

[00:31:14] **Carol:** I'm like, install this. And she's like, Oh my god, you're like my new best friend and I'm gonna get these tickets and now I can pay attention. I'm like, yeah.

[00:31:24] **Ben:** Yeah, that's awesome. All right. What do you got?

## [00:31:29] Don't Be Afraid to Say &quot;I Don't Know&quot;

[00:31:29] **Carol:** I'm kind of gonna throw together, you know, early on in my career, I felt like saying, I don't know, was a big red flag and that admitting I didn't know how to do something just proves that I was weak and I wasn't good enough for the job. In reality, like, being on the other side of it now. If someone comes to me and says, I don't know, I get excited.

[00:31:55] **Carol:** I'm like, okay, let's talk about what you're trying to accomplish. Let's talk about where you're at so far. Let's see where you've gotten. If you can't even start, that's totally fine. I don't even care. I love working with people that I love helping. So for me early on, like I was like, I can't tell anyone I don't know, cause they're just going to fire me.

[00:32:13] **Carol:** They're not going to keep me around if I say I don't know. Like they hired me to do a job and saying I don't know is not okay. And now being on the flip side, saying I don't know is the best answer or like the best response you can have if you don't know. Because otherwise you said they're stuck. Or you go about it all wrong and cause big problems and waste a lot of time.

[00:32:34] **Carol:** And you learn something the wrong way. Can't tell you how many times I did that early on. Like, oh, it, you know, Stack Overflow said it was okay. So I thought it was okay. In reality, it wasn't okay. That's not how you do things. So yeah.

[00:32:48] **Ben:** hundred percent agree. I, I have learned to very much embrace the, I don't know, Can you please explain that in more detail? Because I don't understand what you're talking about for me. I think that was easier for me to come into because in school, I was always someone who sat in the front row and never liked to sit in the back row.

[00:33:10] **Ben:** Actually, that's not true. I was a row two person because I didn't want to be quite in the teacher's face, but I also wanted to be at the chalkboard. Part of it is because I didn't realize early on in my life that I needed glasses, so I had to sit close. But when you're in the front row, I think mentally, it unblocks you, like, you're there, you're making heavy eye contact with the teacher, raising your hand and saying, I don't quite understand that.

[00:33:34] **Ben:** It feels more natural, and at work, I've definitely, that's, that's like, definitely become my move, is saying, I don't know. But, but, go ahead.

[00:33:43] **Carol:** No, I was going to say for me, it felt like I was a minority. So there were, there was no one else like me working, right? Like I was working with a whole bunch of guys and there were a couple of female engineers, but they seemed to not have the urge to do better. Like they didn't want to keep going. It was just a sit in the background, not ask questions.

[00:34:05] **Carol:** So I was like, if I say, I don't know, they're going to fire me. Like I'm going to be the troublemaker here. So I feel like sometimes it is based off of like the people And the people you work with and who you have influencing your ability to make those decisions. So maybe if I had been working at like a bigger company where there were more female engineers and at least female leadership, like there was nobody even a female like leadership ahead of me.

[00:34:28] **Carol:** It was all men. I would feel like I could make more progress, but,

[00:34:34] **Ben:** It's a great thing that you bring that up because I definitely felt as the co founder of the company, I had the opportunity to lead by example, just like your Triumph.

[00:34:45] **Carol:** uh, And, and when I was in a meeting, I was very cognizant of the fact that people had a, a reverence for my position, maybe not for me necessarily, but for my position.

[00:34:57] **Carol:** The title means

[00:34:58] **Ben:** Yeah, if I could come out in a meeting and say, I don't quite understand this, or I'm not sure this is a great idea, or let's explore this in more depth, I, I always viewed it as giving other people permission to do the same thing.

[00:35:11] **Carol:** I agree. I agree.

[00:35:13] **Ben:** I was like you, I was trying to lead by example

[00:35:17] **Carol:** Oh,

[00:35:17] **Ben:** with the I don't knows, but let me, let me ask something about this because this is something I.

[00:35:22] **Ben:** Struggle with reconciling. When you work at a company full time, I feel like it is accepted that you're not going to know things and part of the job is learning and figuring things out along the way. I don't know what the expectation is for consultants. Let's say you hire a firm to come in and help with a problem.

[00:35:47] **Ben:** Is it okay for those people to not know? Cause I always feel like that's what you're paying them for. Not necessarily to learn on the job, but to come in with the answers. And that might be unfair, but I don't know how to reconcile that kind of SWAT team dynamic with, with saying, I don't know.

[00:36:06] **Carol:** okay. Yeah. So maybe let's take a step back. So you're hiring consulted to come in because you're, you know, databases are constantly hitting max for like a hundred percent CPU, but you can't see queries that are hitting it. Like you don't know what's going on with it. So you hire this like consultant firm to come help with it.

[00:36:25] **Carol:** I feel like it is fully Like, I feel like it is completely okay to say you're going to need a ramp up time to understand how we work, we've done to cause the problem, like how we function day to day, like what we're doing in our application, what our application does, like what are we processing, like how are we load balancing?

[00:36:47] **Carol:** Like, I think there's a lot that they have to figure out upfront. But then once they have the information, I do feel like it's okay to expect them to be experts in the problem itself, or for them to identify early on that this is outside of something they've seen, and they're going to need time to figure it out.

[00:37:04] **Ben:** Right. So it's like, in some cases you're hiring people for their domain expertise. And in some cases you're hiring people for their problem solving abilities, which is a little bit fuzzier, but still kind of an expected level of, of operation.

[00:37:21] **Carol:** So, a great example was years ago, I was at a company and we were having an issue with what appeared to be like memory leak, and I don't know like how memory leak works. I can't remember anymore, but we were having issues with, with PDF generations causing like one of our PDF generation servers to just completely max out and ultimately CF would just become unusable, so nothing would happen.

[00:37:46] **Carol:** So we called Charlie Earhart because at the time Charlie Earhart was just amazing. And I feel like he's one of those that when we brought him in. I expected him to just fix our problem. Instead, he went through every single, like, troubleshooting, like, this is how you can find this, this is what you can do.

[00:38:04] **Carol:** And at first I was like, no, this is not what I want. Like, fix it. Like, my customers aren't happy. Fix this. I'm being yelled at. I'm tired of midnight calls, like fix it. But then at the end of it, I was really happy that he came into it with the problem, like with the problem solving mindset, because he gave me great tools to figure out what was going on and how to do it better in the future.

[00:38:27] **Carol:** So sometimes those consultantsfrustrate you up front, but can be a great asset at the end too.

[00:38:34] **Ben:** It, it's so funny, I've, I've had not the exact same conversation with Charlie, but I've had very much along the same lines where, I had him help me with a, a server one time and we were basically doing a screen share for like four hours walking through the stuff he wanted to install and he was telling me, and, and I was personally loving it and I kept saying, you know, thank you so much.

[00:38:57] **Ben:** I'm sure you could get it done much faster if I wasn't here, watch him, but I'm just, I really want to understand this. And he was like, no, that's exactly what I want is for you to sit here and watch and we can talk about it. He's like, I don't want to have to come back. He's like, I want to educate you so that you can do it by yourself.

[00:39:12] **Ben:** And I don't know. I, I love Charlie. I'm just a huge Charlie fan.

[00:39:16] **Carol:** absolutely. Like I've never had any bad interaction with him. Like he's always been great, but he's definitely one of those problem solving consultants and not just a domain like expert.

[00:39:28] **Ben:** Absolutely.

[00:39:29] **Carol:**

## [00:39:29] Talk About Problems and What You're Working On

[00:39:29] **Carol:** all right. So I just mentioned like, don't be like, don't be afraid to say, I don't know. Right. So I feel like the thing that also is key there is you have a lot of people willing to help you take advantage of it. Like if you have someone willing to sit like Charlie Earhart, they'll sit on the screen share with you for four hours and go through every problem that you're seeing, and just talk to what he's seen before, soak that up.

[00:39:53] **Carol:** Like, don't get so focused on the problem that you forget to learn from your mentors along the way.

[00:39:59] **Ben:** Yeah. Absolutely. And to be fair, this is something I think I still struggle with a lot. I have a lot of insecurities about interrupting people and, and, and asking for their time.I have found that it becomes much easier if I schedule time. Like, hey, can I grab an hour on your calendar tomorrow? So. And if people can agree to that, I feel like, okay, now we're both on the same page, what the expectation is going to be, it's time constrained, everything's going to work out.

[00:40:31] **Ben:** but I've really only learned to do that in the last couple of years. I, I agree. That is something I wish I was much better at early on.

[00:40:39] **Carol:** Yeah. Like I talked about early on in the episode, you know, I'm trying to do better by leading by example. So I pretty much have a chat going with my developers cause we've decided to pair program on this effort that we have because we're a little delayed on it. So to get it out, we're just going to work through all of the remaining items together and we're just pushing code nonstop and we're getting it done.

[00:40:59] **Carol:** And it's actually going great. So, I feel like my mornings have turned into, hey friends, like the Forrest Gump, awkward like waving gif. I'm like, how's it going? I want to talk real quick, anything, anything going on? And I hit call, they all answered, I asked my question, and then immediately followed up with two more questions from someone else and a third person chiming in on how to fix their questions.

[00:41:21] **Carol:** So, I feel like, Interrupting people is definitely a problem for me. Like, I don't want to do it, but I'm getting better and I'm realizing that if we're collaborating on something, it's very important to keep talking.

[00:41:36] **Ben:** You know, at work, we don't have this anymore, but when we were a really big team. We had what we sort of called office hours, which was originally intended to be the architecture team answering questions about architecture, but ironically, the architecture team never actually showed up to these meetings, so it mostly just became the, the kind of the low level engineers would show up and just have conversations and this just became this weekly.

[00:42:05] **Ben:** Cadence of, Hey, everybody get in the zoom and let's just talk rando programming stuff. And it was my favorite meeting of the entire week because it was just that kind of stuff. Like, Oh, just shooting the, shooting the breeze and talking about interesting programming problems. I mean, it was. Stuff people were working on.

[00:42:22] **Ben:** It wasn't just random and like, Oh, I read this thing on tech Twitter. It was like, Hey, I'm, I'm approaching this problem and I'm not struggling. And what do you guys think? And go back and forth. And I don't know, it was so great. And I was shocked that more people didn't want to come to a meeting like that.

[00:42:42] **Ben:** If you can imagine that at the time the company maybe had, I don't know, let's say 150 engineers and maybe. Four people consistently showed up and the size of the meeting was maybe between like six and eight people most weeks. And

[00:43:01] **Carol:** Oh, wow.

[00:43:01] **Ben:** how are you all not showing up to this? This is the most exhilarating meeting and it's fun.

[00:43:07] **Ben:** You're getting to meet people and you get to talk about interesting stuff. And I wish I had known how to promote that meeting better or make it seem more appealing to people. I just, I didn't know. I, I never knew what to do. I never knew what to do because to me, so it'd be like, if you offered someone some chocolate.

[00:43:26] **Ben:** And they're like, no, thanks. And you're like, what are you talking about? It's chocolate. I don't know how to make this better.

[00:43:34] **Carol:** So we, we just set that meeting up on my team. So we do it as a team now. I mean, like today we created that invite. So every Tuesday at one o'clock, we're going to meet for an hour and a half just to go over what we're working on, any blockers, any help we need, anything we found in the system, and if there's nothing to talk about, we're just going to talk about like, like getting to know each other, right?

[00:43:54] **Carol:** Like just chat in general. Tell me about something you've read about. Tell me about something you've listened to. Like just to build. That, almost like that trust relationship, right? Like once you know more about a person, it's easier to feel like you have their back. Like.

[00:44:08] **Ben:** percent.

[00:44:09] **Carol:** Like, okay, I know Ben's not getting a ton done this week.

[00:44:12] **Carol:** However, I also know that Ben's mom is having surgery this week, right? So, it's easy for me to go to bat and say, no, it's all good. Like, it'll be fine next week. Like, don't even stress about it. And I'm not asking, like, for any personal information, right? But it's just those getting to know each other better and getting to understand, kind of, like, Who you're working with and what they struggle with, whether it's tech or even personal stuff, like it just helps build a better team.

[00:44:40] **Ben:** 100%. All

## [00:44:42] Database Indexes are Crazy Powerful

[00:44:42] **Ben:** right. I Will go with, Database indexes are just crazy powerful.

[00:44:48] **Carol:** Oh my God. Right?

[00:44:50] **Ben:** I, I, I'm almost embarrassed to admit that for the first several years of using databases professionally, I did not know what an index was. And I did not know why certain queries were much slower than other queries. And, you know, I, part of the problem is I was working on such small applications, it almost didn't matter.

[00:45:12] **Ben:** But. Oh my goodness, because not only are database indexes a huge performance boon to your application, but when you lean on the constraints that databases bring to the table, you can actually create, I think, a more robust, more reliable application, because you can remove things like weird race conditions and so And like double submissions and, and, you know, you throw a unique index on something and suddenly your database is doing the heavy lifting for half your workflows.

[00:45:47] **Ben:** And I, I just, I really wish I had put more time into understanding, not necessarily how databases work, but just understanding basic database functionality earlier on in my career.

[00:45:59] **Carol:** Yeah, I can get behind that. I feel like what I do every day is write an application that waits for data to do something. So, I mean, like, I do some of the processing up front with like, you know, what do I want the data to be? But then I just send it over, wait for it to do its thing, and come back, right? So if I'm not investing into optimizing my database or to making sure what I'm sending over, like, Has the best coverage, has the best, indexes on it, like, has the right, like, link tables and stuff connected so I don't have to, like, query every table, then I'm probably not doing a pretty, I'm not doing a good job, right? Oh,

[00:46:41] **Ben:** memory, I was doing, I was working on this legal, like a law firm website. And I think I had to have a page that just said the number of lawyers that we had in our database. And I had a select star from the attorney table so that I could output a results dot record count. And I mean, just the absurdity.

[00:47:04] **Ben:** Of having to do a full table scan, pull all the data back into the ColdFusion memory space, just to tell a record count. Oh my, that's like the most embarrassing of all of my database files, my, my database party files in my career. It's so much so that this code that I wrote, I mean, it's got to be. Over 15 years old at this point.

[00:47:27] **Ben:** And it's still, I can still remember

[00:47:29] **Carol:** Well, I think, I think early on one of my worst database things was when I was learning how to write SQL and had no idea what I was doing and I had someone explaining me how to, like, explaining to me like how you get data from the database, right? So it's like select star from said table, right? He's like, go ahead and start typing that.

[00:47:48] **Carol:** I'm like, select S T A R and he goes. Oh, God, you don't know anything, do you? And I'm like, I know nothing. He's like, all right, let me sit down. Let me sit down for this one.

[00:48:04] **Ben:** Diane, clear my meetings.

[00:48:05] **Carol:** Yeah. But again, that goes back to if you have the mentor take advantage of them, because he did, that was Sean at the time. And Sean sat with me for hours when I was starting out early, explaining to me just concepts I didn't know because I hadn't been exposed to it.

[00:48:22] **Carol:** Yeah. Yeah. SQL is fun though. I love

[00:48:25] **Ben:** SQL

[00:48:26] **Carol:** Data makes me happy.

[00:48:28] **Ben:** data is great. SQL is great. I get, I get very frustrated when I hear people hate on SQL. And yet I feel like it's really great to work with and it's very expressive and it's like, it says exactly what it's doing, and, and for some reason it drives people crazy and I don't, I don't connect with whatever it is, whatever pain they're feeling.

[00:48:51] **Ben:** I do not feel

[00:48:53] **Carol:** I think for me too, like, I enjoy, like, tables. I don't know the correct term for it. Like, when data is linked by IDs. So, like, I know this table links by this ID. Like, they're all related. Like, I enjoy, like, a database that's set up with clear understanding of where the data lives rather

[00:49:12] **Ben:** good naming conventions basically.

## [00:49:14] Learn More Instead of Just Problem Solving

[00:49:14] **Carol:** Okay, so I think this is probably one of my last ones. You get to do one more each maybe?

[00:49:18] **Ben:** I'll do one more.

[00:49:19] **Carol:** Yeah, I feel like, early on, I wish I would have spent more time learning and less time just trying to solve problems. Like I spent so much time just solving the fire in front of me like that I didn't take the time to actually learn new technology and to learn new ways of doing things.

[00:49:37] **Carol:** It was just spent making sure that what was already written kept functioning and when it didn't making very small tweaks to make it work again. And instead, I should have spent more time learning and building up that love for learning so that it would have carried on. Because now I still find myself where I'm like, oh, I have to learn something.

[00:49:56] **Carol:** Unless it super motivates me, I have to push pretty hard to go learn it. And usually it's only when it's something that's being introduced at work. So I'm like, oh yeah, I'm going to learn RabbitMQ because I have to use it. So I think finding passion for learning and it'll take you a long way.

[00:50:11] **Ben:** I, I agree. I think I fell into the same trap in that mostly what I learned. was the stuff I failed to do that day. You know, oh, I had a problem at work. All right, let me figure out how to do that. I'll write about it. And that's how I'll kind of codify it into my mental model. I was not very good about just doing wild experiments.

[00:50:34] **Ben:** Other than, like, Based on what I had failed to do the day before, you know, I never took a weekend to do a hackathon experiment or just try something totally new for the sake of trying something new. I've gotten a little bit better about that as I've gotten older, but it's still very much a Even when I start down that road, it's hard for me to stay dedicated to it because I find myself often getting distracted again by the things that I'm doing at work.

[00:51:03] **Carol:** Yeah, the learning at work and what you have to do at work tends to always get in my way of learning extra things outside of work.

[00:51:12] **Ben:** Yeah. But okay, I want to counterpoint this a little bit. And I'm mostly thinking out loud here. so I've been doing ColdFusion for a really long time. I've been doing JavaScript for a really long time. I've been doing SQL for a really long time. And these technologies are obviously evolving. So there's always something new in those domains to learn,

[00:51:33] **Carol:** Is CultFusion really evolving? I'm sorry, I had to be the voice of Adam. I had to be the voice of Adam.

[00:51:39] **Ben:** Even within those domains, I do feel like I am always refining the way that I think about the work, and I'm always playing with the strategies and I'm playing with the algorithms and I am, I think even within the constraints of the language, becoming a better programmer over time, and it's hard for me to reconcile that continuous learning within a domain versus just learning something for fun.

[00:52:09] **Ben:** So at the top of the show, I talked about how I'm taking this Udemy course now on PHP and I'll set up a Docker playground with, you know, Nginx and, and PHP, and I'll be able to do some hello world scripts and, you know, probably create a class and do some rendering and whatnot. is that ultimately going to get me very far if I'm not also doing PHP at work on a daily basis?

[00:52:34] **Carol:** Like, how better are you actually gonna get at it?

[00:52:37] **Ben:** Right. It's right. It's like, if I read a textbook on PHP and then I also did some experimentation, I feel like the experimentation probably is only going to get me incrementally better unless I'm actually doing PHP on a daily basis. So I want to be better about exploring and, and expanding the scope of the technology that I use.

[00:53:02] **Ben:** But I also feel like sometimes we underplay. How important work is as a, as a fertile ground for learning.

[00:53:11] **Carol:** So let me pitch this idea to you. What if you just went to a site and it said, here's my broken code, you figure it out. To me, if I pull in code that's broke, and I spend time figuring out like, why it's not working, and what's going on with it, and what's happening, I learn so much more. Then just doing some like, hello world, start up a new project.

[00:53:36] **Carol:** Like if you give me the project where the core works, like it's going to run PHP, everything's going to be fine, but this isn't going to render. This isn't going to work and we're going to get errors. I can go backwards from that. And I would learn a lot more about the inner workings of the application and of the code than I would from just doing a simple like setup.

[00:53:55] **Carol:** hello, let's look at this code example.

[00:53:58] **Ben:** I think, I think there's a project someone created, I want to say in the Ruby world called Exorcism, which I think is kind of like that, where they have a bunch of things that aren't working. And, you know, and you have to go in and figure out why they're, I guess you have to exercise the demons, so to speak, but, but apparently I think that's a hundred percent on point.

[00:54:22] **Ben:** Like you just learn better that way.

[00:54:25] **Carol:** I do anyways.

[00:54:26] **Ben:** I don't know. It's so tricky. It's so tricky. I, so I listened to the show that Adam and Tim recorded earlier in the week. And one of the things that they talk about was, I think Adam said this, that he, one of the advice that he would give his younger self is. Don't be afraid to switch jobs more often.

[00:54:47] **Carol:** Oh, that's a good one.

[00:54:48] **Ben:** And I think that is almost.

[00:54:51] **Ben:** The, that's like the power move of learning things on the side. Like instead of learning things on the side, just go to a different job and learn. And, you know, instead of a couple of hours on the weekends, spend 40 hours a week learning something new. And, I, I, I mean, I've never been good at that. I'm, I'm 43 and I've had like three jobs in my life,

[00:55:12] **Ben:** So I,

[00:55:14] **Carol:** no. I just had that conversation and I kind of had that on my list too, and I didn't, we didn't talk about it, but definitely don't be scared to change. Like if you're not fulfilled with your job, if you, if it's, if your job's not making you better, get a better job.

[00:55:30] **Ben:** Yeah.

[00:55:30] **Carol:** Like sometimes a career and a job will hold you back and don't let that be a thing.

[00:55:36] **Carol:** But actually I've changed a lot. You guys know that. Sometime was out of force and sometimes just cause, well, I need change. I get burnt out and if it's not getting better, I'm gonna go on.

[00:55:46] **Ben:** yeah. I mean, I don't know if you listened to the episode that they recorded, but they gave you a lot of credit

[00:55:51] **Carol:** Oh, I did not yet.

[00:55:53] **Ben:** for, oh, so, so Tim and Adam gave you a lot of credit for being very good about that, that you seem very confident in moving on when it's the right thing for you to do. Whereas I think a lot of people get stuck.

[00:56:08] **Carol:** I'm very self aware. And then when I'm not growing, it becomes a problem.

[00:56:12] **Ben:** Awesome.

## [00:56:13] Wait For Problems Before You Solve

[00:56:13] **Ben:** All right. I'll do, I'll do a quick one here. My last one was, wait until problems arise before you solve them. And I, you know, this is basically a more long winded way of saying don't prematurely optimize, but I think I spent a lot of time in my career worrying about all the things that could go wrong and then never having to deal with most of those things anyway.

[00:56:38] **Ben:** And this kind of dovetails with the idea of keeping things simple. You want to have robust and resilient code. I think that's, that's a given. But there are ways to do that without having to solve every foreseeable problem.

[00:56:52] **Carol:** Completely agree.

[00:56:53] **Ben:** yeah, I just wish that I had erred more on the side of not worrying about things that could go wrong and just worried more about getting stuff done.

[00:57:03] **Carol:** So we've started, on my team, I'm not going to speak for the other teams with them within my group, but on my team, personally, we've started building all of our MVPs to only account for happy paths, so we write some unit tests that cover to make sure like, you know, I have the correct data, things hit the right amount of times.

[00:57:21] **Carol:** If I get an error. Everything is able to be seen and I'm able to continue or, you know, it can be reported. So our happy path is all we code for up front. So we code for the happy path. We give it to you usable and anything you break we'll figure it out along the way. We want to see that first you're going to use it and then we're going to kind of figure out like what you're breaking.

[00:57:44] **Carol:** Like obviously the data is going to save, it's going to all calculate right, like all that's checked

[00:57:48] **Ben:** There's a baseline that

[00:57:49] **Carol:** There is, but there's no point in me sitting through going through every single scenario of how this could go wrong. Like, are the RabbitMQ servers down? Did our Outbox sweeper not pick up messages?

[00:58:00] **Carol:** Like, was there a, like an Azure outage that day and suddenly nothing processed? How do I reprocess everything? Like, you know what? We're just going to re trigger things. Like, things are going to happen again. There's going to be some manual until we figure out if it's actually something we need to cover for. Yeah.

[00:58:17] **Ben:** hundred percent. I think on a previous show, you were, you know, I don't know if you were saying someone was retroactively creating tickets or they were trying to outline a problem space and they were just like, code the happy path. You were like, what's the happy path? They were like, whatever you're doing now, when you click that button, that's what the happy path is.

[00:58:33] **Ben:** Do that.

[00:58:35] **Carol:** this, you've made the happy path and that's what we're gonna deliver. Yep,

[00:58:39] **Ben:** I know that they say that, Hope is never a plan, right? Like you can't just hope that things work out.

[00:58:44] **Carol:** you gotta do some action.

[00:58:46] **Ben:** I do feel though that there is a certain degree of hope that something terrible won't happen right away. And that on day one, you know, we're not going to suffer from a distributed denial of service attack and we don't necessarily have to code for that on day one and yes, we're hoping that that doesn't happen, but I feel like sometimes Yeah, you just gotta hope that something doesn't happen and worry about getting the work done.

[00:59:12] **Ben:** And then maybe solve it later.

[00:59:15] **Carol:** Completely agree.

[00:59:17] **Carol:** We good there?

[00:59:18] **Ben:** Yeah, I think we've schooled our younger selves pretty sufficiently.

[00:59:22] **Carol:** I'll do better. I'll do better in my next life.

[00:59:25] **Ben:** That's right. Be better, Carol.

[00:59:27] **Carol:** that'll be better. Yeah. Yeah.

## [00:59:30] Patreon

[00:59:30] **Carol:** This episode of Working Code. was brought to you by exercising your demons, like on a treadmill or something, and listeners like you. If you're enjoying the show and you want to make sure we can keep putting out more of whatever this is into the universe, you Patreon.

[00:59:45] **Carol:** Our Patreons cover our recording, editing, and transcription costs, and we couldn't do it without them. . Special thanks. , it goes out. So Monte and Giancarlo,

## [00:59:54] Thanks For Listening!

[00:59:54] **Carol:** Ben and I are not gonna be doing an after show this week. We're pretty exhausted. Long weeks at work and we're done.but if you'd like to help us out, definitely head over to workingcode.dev/review and leave us a review.

[01:00:06] **Carol:** We'd love to hear what you think about us.that's it for this week. We'll catch you next week, and until then,

[01:00:12] **Ben:** Remember, folks, your heart matters, especially if you're wise enough to learn from other people's mistakes.
