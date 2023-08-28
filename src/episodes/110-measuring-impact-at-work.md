---
title: "110: Measuring Impact At Work"
description: "On today's show, we look at what goes into making those good days 'good' and those bad days 'bad'."
date: 2023-01-18
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/110-measuring-impact-at-work/id1544142288?i=1000595197301"></iframe>

Not all days are created equal. Some days, you show up and just crush it non-stop. Other days, it can feel challenging to even type good. On today's show, we look at what goes into making those good days "good" and those bad days "bad". Getting into the zone, meetings, switching modes, interfacing with customers, responding to incidents (and other interruptions) - every little thing has the power to push the needle one way or the other.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/110-measuring-impact-at-work.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam:** I, I can remember some meetings that I went to, like sales meetings, early on in our company's history where like we would go in and I would demo the product and, and Steve would be talking about, you know, the vision for it. And, and the customer would be like, well, what about this and what about that?

[00:00:15] **Adam:** And I would just be quietly sitting there making the changes they're talking about. and and they're like, they're looking at the, the big, you know, projector screen and the stuff that they're talking about is appearing. Cuz I've, I'm like, not even refreshing. The screen's got like, hot module reloading going and it's just like, and they're like, This is magic.

[00:00:34] **Ben:** That's awesome.

## [00:00:54] Intro

[00:00:54] **Adam:** Okay, here we go. It is show number 110. And on today's show we're gonna be talking about measuring impact at work. Tim couldn't be with us tonight. He's not feeling great. so hope you feel better soon, Tim.

[00:01:04] **Adam:** But, in the meantime we'll start with our tram said fails. And Ben, why don't you go first?

## [00:01:09] Ben's Failiumph

[00:01:09] **Ben:** Yeah, I'm gonna go with aum. So half failure, half triumph here, which is that I had in my mind this grand idea that I was gonna take the holiday break between Christmas and New Year's, and I was going to build a small ColdFusion site and then layer on hot Wire, which is a, kind of progressive enhancement framework from the guys over at Base.

[00:01:33] **Ben:** in my mind, the ColdFusion part would take a day, knock it out, and then I'd spend the rest of the holiday getting to know Hotwire and, and its little intricacies. fast forward to January 5th, which is the day of this recording, and I literally just finished the c f cfml part and started to play around a little bit with the hot wire.

[00:01:54] **Ben:** So it's a, it's a triumph in that I stepped outside of my comfort zone in that I was sort of building something I didn't know anything about. I was exploring. so I feel good about that, but failure in that I didn't actually accomplish the, like, the very thing that I set out to do, and the irony of it all is I build the whole C F M L site.

[00:02:16] **Ben:** It doesn't have a good interface or anything. It's pretty crappy looking, but like all the data access stuff and all, and everything is behind the scenes, I go to layer in hot wire and it doesn't seem to be doing anything. And it turns out that by default it only works on HTM and HTML extensions. Yeah,

[00:02:36] **Ben:** And, which took me a while to figure out. and, and the reason that they do that is because for dynamic sites like P H P, cfml, Ruby, et cetera, there's no guarantee that the DOT CFM extension or the PHB extension will actually serve up html. It could serve up anything, right? You could just stream down binary for an image.

[00:02:54] **Ben:** so they can't assume that a link will necessarily lead to html, so they don't wire up all of their, interceptors and whatnot. So that was frustrating. But, I could turn on URL rewriting for the ColdFusion site and then just change everything from CFM to HTM or htm. in fact, you can actually just do like index dot cfm slash fubar htm.

[00:03:19] **Ben:** And you know, the Path info part of the URL just gets ignored, but Hotwire thinks it's linking to a HTML page. So, so it'll work. But, but anyway, I was frustrated that I, one, that it took way longer to build this thing that I had anticipated, and then I was getting really angry with myself. Cause I'm like, oh, you picked such a stupid idea and it's taking way longer and you're not even getting to the whole point.

[00:03:40] **Ben:** but I do at least feel like I, I did something, I took a chance and I moved forward. And I feel good about that.

[00:03:47] **Carol:** So what is Hot Wire

[00:03:50] **Ben:** Oh yeah. Sorry. I guess maybe I should have said that. So, hot Wire. Hot Wire is a, an umbrella for two or three different technologies. and I don't know that much about it, but essentially it's, it's the evolution of something called Turbo Links, which came out of Basecamp.

[00:04:06] **Ben:** Turbo Links was essentially a way to say, Hey, you're on one page and there's a link that clicks to another page. Instead of that link actually doing a full reload of the page, it will just fetch the page via Ajax and then replace the body element instead of re parsing all the JavaScript and re parsing all the CSS and re downloading all the css, or you know, pulling it from cash.

[00:04:27] **Ben:** So it gives the perception that the page is actually loading faster, even though all the same data is being loaded behind the scenes. And then Turbo or Hotwired is an evolution of that, that thou contains something called Turbo Drive, which is that kind of interlinking, and then something called stimulus, which is their ability to kind of what they call like sprinkle JavaScript into apps to reduce the amount of JavaScript that you have to build.

[00:04:53] **Ben:** And the other, like the third one is called Turbo Streams, which I think is like a web socket. They'll push changes down instead of you having to request them. I don't really know that much about that part at all.

[00:05:04] **Adam:** this is all sort of based on the idea of like partials too, right? The the new version,

[00:05:10] **Ben:** So you, yes, you're right. the, the other thing that it does is something called turbo frames. And turbo frames is the ability to load little partials and like lazy load parts of the page. And, and, and, yeah, exactly. And I'm, I, I was intending to come into this week knowing all about this stuff, , but, I did not make it that far.

[00:05:33] **Adam:** do you wanna describe partials for somebody who doesn't know what we're talking about?

[00:05:36] **Carol:** Like.

[00:05:37] **Ben:** So, so imagine a, a data grid or a list of items, and there's an edit button and one of those items with a traditional multi-page app, you hit the edit button and it actually goes to an edit screen that's a full refresh of the page and has the edit form with the idea of a partial. can progressively enhance the page and say, Hey, when I click this edit button, instead of going and getting that entire edit page, just go get me the form, like, like the form element and the inputs and the submit button, and just take that over Aja and load that into the page that it requested from.

[00:06:13] **Ben:** So you get like little snippets of pages that then dynamically get added to and removed from the current page.

[00:06:20] **Carol:** That sounds amazing.

[00:06:22] **Ben:** Well, so I mean, it sounds really cool and, Basecamp built the new email. I dunno if email client is the right word. Email service hey.com and apparently hey.com is entirely built with Rubian rails on the backend and then this hot wired on the front end.

[00:06:39] **Ben:** And it's like a, it's a Multipage app, but it looks and feels and behaves like a single page app or a spa because they're using all of these advanced techniques. But, Again, my plan was to know more about this and really, I just know a little bit of what I've read.

[00:06:55] **Carol:** Well,

[00:06:56] **Adam:** is it in Docker?

[00:06:57] **Carol:** year, the year just

[00:06:58] **Ben:** It isn't Docker. Yes,

[00:07:00] **Adam:** So I mean, just locally, right?

[00:07:02] **Ben:** Yeah. Yeah. Just locally.

[00:07:03] **Adam:** Hey, that's a, that's a good first step.

[00:07:06] **Ben:** Well, and it's, it's like half in Docker, so it's running on the command box Lucy, C F M L image. So the Lucy system is all running inside of a Docker container. But then when I started trying to play around with Hot Wire this morning and running the JavaScript, I actually just run the JavaScript comp compilation on my host computer.

[00:07:28] **Ben:** So all of the node modules and stuff are kind of technically outside of the Docker container, but it it's sloppy. Yeah. Yeah. Yeah. So I'm not running those commands inside of Docker. but I, I think I could, I'd have to change the volume out slightly, but.

[00:07:43] **Adam:** That's all right.

[00:07:44] **Ben:** You know, baby steps.

[00:07:45] **Adam:** Nothing, nothing wrong with that.

[00:07:48] **Ben:** Anyway,

[00:07:48] **Adam:** Cool.

[00:07:49] **Ben:** so that's me.

[00:07:50] **Ben:** Carol, what about you? What do you got going on?

## [00:07:52] Carol's Triumph and Failure

[00:07:52] **Carol:** Hi, can I go with both? Can I call the trier? I'm gonna,

[00:07:57] **Carol:** I'm gonna call my failure because my mic broke you

[00:07:59] **Adam:** Yeah.

[00:08:00] **Carol:** I'm gonna sound great tonight on my AirPods. But I'm gonna order a new one from Amazon tonight cause you know it's best place to shop from and, hopefully we'll be here by the next episode.

[00:08:10] **Carol:** So, sorry guys. But, I also have a big triumph.

[00:08:14] **Carol:** before I got sick, which was the week of my birthday last year, you know, cause it's a whole year different south. As I talked to you guys, I started this project where we were trying to change how we deliver a product. and basically we have these different APIs we get and we're like, Hey, once one is established and we have successful submission and they agree that everything's good, we're gonna call this, this transaction approved, and then we're gonna send everything to the other endpoint.

[00:08:42] **Carol:** Well, one of the big changes is that now everything needs to come back approved before we. Everything can come back successfully submitted before we can approve the transaction, which doesn't sound too difficult until you start looking at legacy code that's just been layered on top of each other with the expectation that we would never need approval from anyone else to say we're done, right?

[00:09:04] **Carol:** And I'm like, oh my God, oh my God, what have we done? What have we do to ourselves here? So, I started working on it, got sick, and then had to circle back to it after Christmas and go, ok, where was I with it? And then today, even though the endpoints aren't fully working, I wrote some tests to test that the SNS messages are received successfully.

[00:09:25] **Carol:** And when I run all of my tests, I'm able to successfully do the without resubmission accidentally and without running into any errors and everything's correctly. And it requires all of the correct data. I'm

[00:09:44] **Carol:** that's, Yeah, it was a huge win tonight. So when my husband got home, I'm like excited. I'm like, I solved the problem. This is great. Everything's good. I get to talk to my friends tonight. Yay,

[00:09:56] **Ben:** Very,

[00:09:57] **Ben:** very

[00:09:57] **Carol:** a triumph. Yeah.

[00:09:59] **Ben:** so just for my sake of clarity here, , your system is calling another system and now there's like, it needs to kind of ping pong back and forth once or twice to sort of handshake in both directions. Is that the idea?

[00:10:12] **Carol:** no. So we are calling one system. That system says, Hey, we've validated everything that you've said. So it does like a rules check. Our rules say we passed the next system. Doesn't it? Never wanted a hit to it till the first systems rules passed. Cause it assume if the first pass, they don't wanna spend the time processing it because they know it's gonna fail.

[00:10:34] **Carol:** So they were like, we're gonna use you as our qa, and then once your QA is done, we're gonna go to the next. So once that approved, we just assumed everything was good to go. So now we aren't approving the transaction until we get successful submissions to all of,

[00:10:50] **Ben:** Uh. Okay.

[00:10:52] **Carol:** so

[00:10:56] **Carol:** we're approve, approve it.

[00:11:01] **Ben:** Gotcha. Gotcha, gotcha. Kind of like

[00:11:02] **Ben:** a, uh, promise dot all

[00:11:05] **Ben:** kind of a

[00:11:06] **Carol:** You gotta get it all back before you can move forward. Yep.

[00:11:09] **Ben:** Nice, nice, nice.

[00:11:11] **Carol:** But legacy code is a, a challenge sometimes when people make assumptions to processes and workflows

[00:11:18] **Carol:** that are never gonna change. Right.

[00:11:22] **Ben:** Happy birthday, by the way.

[00:11:24] **Carol:** Oh, thank you. Thank you. I am rolling into 38. Great.

[00:11:28] **Ben:** No.

[00:11:29] **Carol:** I've been so sick.

[00:11:31] **Ben:** Oh, Carol.

[00:11:32] **Adam:** Well, we're glad you're well enough to be back now.

[00:11:34] **Carol:** Yeah. Yeah. I finally went back to work and you know, can talk without coughing, so that's a good thing.

[00:11:40] **Adam:** Yeah.

[00:11:41] **Carol:** Yeah, that's me. What about you, Adam?

## [00:11:44] Adam's Triumph

[00:11:44] **Adam:** So I also am gonna go with a triumph. I also, like Ben, took the week off, at the end of the year from Christmas to New Year's Eve. and like Ben, I also had, probably over ambitious because that's my brand, goals for the week. including both, like putting in some serious reps and, and getting good at turning bowls on my lathe, which, uh, you know, I've just barely dabbled in prior to this week. And, and the other thing was I wanted to play with Spel kit and, you know, try to sort of lay the groundwork for what could become the next,the next major evolution of our monolith.

[00:12:21] **Adam:** and you know, the, the funny thing is, so like it's a C F M L app, the current version of the monolith. And because it was easy to change the C F M L session cookie, we made it, What's the word, compatible with express js so that all of our node services could share sessions, right? So if you sign in with the cfml app in the monolith and you have a valid session cookie, and you go over to one of our apps that's written in Node, it just consumes the same cookie and you have the exact same session data available to you, which has been really handed.

[00:12:54] **Adam:** We can pass stuff back and forth between apps that way. and so, I, I had to figure out how to, parse and decrypt that cookie. Using the exact same tools that, express Js does. Like it's, I believe it's Connect Session or something like that, whatever the plugin. and, and why are that in Just Felt, which was kind of cool, kind of fun.

[00:13:12] **Adam:** but that's about as far as I got with it because I got consumed with, turning Bowls, but I've turned like five or six different bowls on my lath now. and I went into my local, woodworking store. So there's a couple of different stores. If you're, if you're in the, the Craft, then you know the stores, rocker and Woodcraft, they're sort of the, the top two.

[00:13:28] **Adam:** it's like the, the, home Depot and Lowe's, right? They ev they're the ones that everybody knows. They're, they have different chains around the country or different, stores around the country from the same chain. And, so I went into my local Woodcraft, to talk to their turning instructor.

[00:13:40] **Adam:** Turning is, you know, making things on a lathe cuz it spins. And, you know, I showed him some of my work and he complimented me and I was like, I was kind of blown back by that. Cuz he is like, you know, I was expecting him to be like, no, these suck. You gotta, you gotta sign up for my classes. And he's like, you could teach the, the 1 0 1 class.

[00:13:56] **Adam:** I'm like, whoa, thanks. So thanks. Yeah, I'm, I'm really happy about that and excited. And, and I've been making some bowls. I I have posted some pictures on my Mastodon account because the bird site is dead to me. but, yeah, so, I posted some pictures there. I think I might have posted some in our Discord, but if not then I'll make a point of doing it soon.

[00:14:17] **Adam:** yeah, that's a lot of fun.

[00:14:18] **Carol:** Are you selling them?

[00:14:20] **Adam:** Long term. That's the plan. I, I think the early ones are, you know, I've got a lot of, friends and family who, who want one right first, and, and, so I got a, a bunch of those to fulfill and that'll be good practice anyway. And then I'll start throwing some up on my auntie shop.

[00:14:34] **Adam:** It'll be weird. I'll have like 3D printed stuff and turned bowls, on my Etsy store, but, hey, why not?

[00:14:40] **Carol:** Can I get on that friends list? For a bowl I'll pay shipping

[00:14:45] **Adam:** I'm sure we can work something out.

[00:14:48] **Carol:** Cool. That's really awesome.

[00:14:49] **Ben:** Btechs a big chunk of wood. Is that, is that, like, are you, like, do you have a failed tree that you're taking slices from or do you go to Home Depot and get a giant

[00:14:58] **Ben:** block of wood?

[00:14:59] **Adam:** The, so the, the all, yes, all of the bowls that I have made so far. Are out of chunks of trees that I picked up off the side of the road. So, you know, like when a storm rolls through and you know, a tree falls across the road and the, the, you know, the local public works, whatever, they come up and they cut it up and they just throw it on the side of the road.

[00:15:19] **Adam:** So every time it storms around here, I'm like, okay, I'm gonna go drive around, look for , look for trees on the side

[00:15:24] **Adam:** of the road. Look for

[00:15:25] **Carol:** Kids Daddy's going shopping.

[00:15:27] **Adam:** Yeah.

[00:15:27] **Ben:** once you get your dream job of the helicopter with giant chain of, chainsaws, you'll be able to feed from one career right into another

[00:15:39] **Ben:** maybe. So, yeah, I mean, and you know, of course, like I said, over ambitious goals, I didn't get anywhere near as far as I'd hoped to with that, what I was considering, like a mad science project. With spelt, you're talking about

[00:15:50] **Adam:** Yeah. Playing with felt kit, I, I had fun. I figured a couple things out and, you know, I'll come back to it.

[00:15:56] **Adam:** I just, I think I got. I had some early success turning and that really kind of sucked me in. I was like, okay, that's fine. I'll follow the thing that's I'm doing well at. That's interesting. Me and why not? So

[00:16:08] **Ben:** I get a little, nervous, I guess is the right word. So I, I, I understand that when we listen to things on various podcasts and you see people talk about stuff, there is, there is an echo chamber of people who are highly engaged in social activities, which is, you know, a, a, a small slice of the development pie, most likely.

[00:16:28] **Carol:** What do you mean by social activit?

[00:16:30] **Ben:** Like, like people who give presentations or talk on podcasts or tweet about things like people who are, are, are facing the

[00:16:38] **Ben:** world. Yeah. Yeah. And, and it feels very much like all the progress that's being made lately is in the, I'm running JavaScript both on the server and on the client. Kind of a world with all of the edge functions and the winter CG compatibility stuff and wam and web components and njs and NT and view and SEL kit.

[00:17:04] **Ben:** And what's the, what's the one that Ken see DODs is in

[00:17:09] **Adam:** Oh, remix.

[00:17:10] **Ben:** remix. It, it, it seems like there's this world of ColdFusion developers and PHP developers and ASP net developers who are like not gonna be able to leverage all of this really fancy, I'm running JavaScript all over the place, kind of a world.

[00:17:26] **Adam:** Mm-hmm.

[00:17:28] **Ben:** And I'm nervous that I'm left out of the party, but then I also am trying to keep the perspective that that's just one area of web development and doesn't necessarily represent the entirety of the future of, of the career.

[00:17:41] **Adam:** Mm-hmm.

[00:17:42] **Ben:** But I'm not a hundred percent sold on that mindset, .

[00:17:45] **Adam:** Yeah. Well, I mean, it's a double edged sword, right? So on the one hand, , you are correct in that, you know, your current stack is not going anywhere anytime soon. Right. There will be Cfml apps that need maintenance for

[00:18:01] **Ben:** or even just php

[00:18:02] **Adam:** or php, yeah, yeah, yeah.

[00:18:04] **Ben:** anything that's just not happened to run. Yeah.

[00:18:06] **Adam:** Yeah.

[00:18:07] **Adam:** But, sort of the other side of that coin, the other edge of that sword is like, do you really want to go back and work on Cobalt or classic as p right now, like, you know, I think innovation moves in like, in swarms, right?

[00:18:24] **Adam:** you know, there are gonna be bees that, that fly off and do their own thing. There are gonna be, bees that choose to stay behind when the swarm moves on, and hopefully they do okay. But, you know, I think that right now the swarm is around JavaScript. It's a good time to be a JavaScript type script developer.

[00:18:42] **Ben:** Yeah. And don't get me wrong, I love JavaScript very much. I just, I, I sometimes feel like, I don't know enough to put it all in perspective. So it feels like it's very easy to get swept up in the, in the, I dunno what's the right word, but like mob mentality of JavaScript is the future.

[00:19:02] **Adam:** Mm-hmm.

[00:19:02] **Ben:** and, and not have enough experience to say that actually a lot of what they're doing is possible in other ways.

[00:19:07] **Ben:** That just doesn't get a lot. A lot of, you know, radio time, but I don't know.

[00:19:12] **Adam:** Is there anything left to say about P H P, I mean at this point,

[00:19:16] **Ben:** I mean, word, you know, WordPress still powers like, like 70% of the world's websites or something crazy.

[00:19:25] **Adam:** Yeah. And there was a big, I saw in our Discord, somebody posted. There was a, like a recent, leak or breach.

[00:19:31] **Adam:** Hundreds of WordPress sites infected by recently discovered backdoor.

[00:19:35] **Carol:** woo

[00:19:35] **Ben:** Oh, gulp.

[00:19:38] **Ben:** I guess that link has to go on the show notes now. Oh man.

[00:19:41] **Carol:** I will say my son and I just had the conversation because he's about a year, a little over a year out from graduating with his CS degree, and he's like, what? What should I be doing? I'm like, go learn tight scripts. And I was like, don't just learn like a little bit. I'm like, go deep in it. Just start learning it now, because when you walk into a job and you're like, oh, I already know type script.

[00:19:58] **Carol:** They're like, oh, well if you could pick it up, then we need JavaScript for everything in the world that we do, so you probably can adapt to what we're trying to build. I was like, that's a good entry point for you. He was like, should I learn called Fusion? I was like, no. Well, I love you. Don't spend the time learning it.

[00:20:15] **Carol:** You

[00:20:15] **Adam:** No, it's because I love you.

[00:20:17] **Carol:** You can pick that up quickly. Yes, your job requires it, but learn something that is like needed across the board right now. I was like, don't like put yourself in a tiny bubble.

[00:20:28] **Ben:** Very cool.

## [00:20:29] Measuring Impact At Work

[00:20:29] **Adam:** So our, our main topic today is gonna be like measuring impact at work. So yeah, like I was trying to think like how do we, how do we frame this discussion? And so for me, I think what makes sense is like asking the question, what makes you feel like you had a really good day at work? What, you know, what's the difference between the days that you leave work, feeling satisfied and productive and excited to go back the next day?

## [00:21:00] What Makes A Productive Day

[00:21:00] **Adam:** What's the difference between that day and the days that you're like, so glad work is done.

[00:21:05] **Adam:** Just I just need to go sit in a corner and stare at the wall for an hour before I'm ready to deal with the rest of the world.

[00:21:11] **Adam:** Cause they, they, both.

[00:21:13] **Carol:** they do absolutely. I, I have two things that kind of like may play into it. So there are days where I get up and walk away from my computer and it still takes me 30 to 45 minutes to have a conversation with my husband or with my kids because my brain is still turned on to what I'm doing so much that I can't just talk.

[00:21:32] **Carol:** It's just, yes, nos and what's for dinner? Like, can I just be alone for a bit? And then there are days when I'm like, okay, it's you know, 5 30, 5 o'clock, 4 44 whenever, you know, I'm like, alright, what you guys doing? Let's go all hang out. Let's do something. Because I'm able to transition off because I finished or because I felt like I accomplished or I felt like I did something that could be resolved.

[00:21:58] **Carol:** The days that I don't resolve it and I'm still working on it late and I'm like, ok, I have to get up now I work at home. So like lemme get up, move away from it and go transition into my family time. I hate those days and I feel like I didn't have a big impact and I didn't finish it. So I need to be able to finish and find a stopping point to where I can transition into family.

[00:22:20] **Adam:** is it about productivity or

[00:22:23] **Carol:** It's just feeling accomplished, right? It's feeling like you found that spot to stop. Whether I made a note that says, tomorrow when I come in, go to step five and start there because you've hit a spot. But when I can't get to a spot where I can finish, then where do I stop? How do I tell my brain to stop thinking about it?

[00:22:47] **Carol:** Because as I'm writing code, my brain's just churn and churn and it's thinking so far ahead and trying to, I can't turn that's stopping

[00:22:59] **Adam:** Yeah. me, I, I, it's easier for me to think about the bad days, right? So the, the last bad day that I can remember, I was just not having, you know, just a rough day, right? You know, things are not going the way that you want, you're not working on the things that you wanna work on. And that puts me in this just like really negative sour mood.

[00:23:18] **Adam:** And I can remember it because it was the day that my son wanted me to help him install Unreal Engine on his computer. And so he, he's 14, he still has like parental controls on his computer to help reduce the possibility that he will install a virus and stuff like that, right? So I have to go put in my pin code on his computer to allow to install stuff, that sort of thing.

[00:23:39] **Adam:** And, you know, unreal Engine is a big download and you know, it makes a bunch of modifications. So, you know, it was like five, six different times that he was asking me to come down and put in my code. And I'm getting like more and more annoyed every time that it's like it. And it's, and it's not just that, it's like every time anybody needs anything from me, if I'm having a bad day, it's just instant.

[00:24:01] **Adam:** Like you are the worst person in the world. You know, like in the back of my mind, like I, I know I love you and, you know, I would, I would do really good things for you, what's, but, like, yeah, it's just, and I even told him on that day, I was like, look, I'm having a bad day. It's not your fault, I'm sorry, but, you know, I'm just, I, I apologize for being gruff with you, but this is, this is how my day is going.

[00:24:24] **Adam:** So I'm, I'm helping you out, but I'm, I'm sorry I'm not being as nice as I could about it,

[00:24:29] **Carol:** Yeah,

[00:24:30] **Carol:** sitting

[00:24:30] **Adam:** I'll do it with everybody. You know, it's like when, when, we were trying to plan a vacation, like we're going to the Grand Canyon next? No, this year, sorry. It was last year that we had this, conversation with my wife.

[00:24:40] **Adam:** and we were talking about like flights and she was trying to communicate to me that like we had a couple of different options to consider. Like, we could come back on Friday, or we could come back on Saturday and we can. , you know, pick whichever day is gonna be better for getting a good deal on a flight.

[00:24:57] **Adam:** But the way that she was trying to explain that to me was really getting on my nerves. And it was had nothing to do with the way that she was explaining it. It had everything to do with the fact that I was having a bad day. Right. And I just was, I, you know, I was rude to her and I was like, I'm, I'm sorry,

[00:25:12] **Adam:** for me, I think two things make me feel like I'm productive. One is kind of what Carol was talking about, where I just feel like I'm in the zone and I, it's like there's a path forward and I see the path very clearly and I just need to run as fast as I can to, to get to the end. And I, and so it's just, it's like a, it's a laws of physics.

[00:25:36] **Ben:** How fast can I hit the keyboard to, to get what's in my head onto the, the screen That makes me feel very productive. also, I am a huge fan of creating tickets in our ticketing system, and I tend to keep my tickets fairly small in scope. So if I can just see those tickets moving across the board at a regular interval, I feel like done, done, done, done.

[00:26:02] **Ben:** You know, I feel like I'm, I'm ticking the boxes and that makes me one, it makes me feel like I'm accomplishing something, but it also, it gives me good feedback as to whether or not the, the, the plan that I had laid out for a particular project is on track,

[00:26:20] **Ben:** right? We can go in, I can say, oh, like I have a project, for example, that's due, I estimated by January 27th and we're recording this on January 5th.

[00:26:28] **Ben:** That's 22 days from now. That's longer than I usually estimate anything. I usually estimate things like in the week. so I'm moving tickets across the board and I'm getting that sense every day. That feedback, like, does the January 27th goal feel. Feasible. And if I can keep moving those tickets and I can keep seeing the, you know, the hundred percent bar moving across on the Jira ticket on the Jira Epic, then I feel like I'm, I'm getting work done.

[00:26:53] **Adam:** I don't mean this as like a criticism or anything like that, but I, I think I've had enough people leverage that criticism at me that it, it immediately springs to mind for me. Is that like what you were describing, keeping the scope of the tickets very small and, you know, tracking every little bit of it, all the way across the, the, CanBan board?

[00:27:12] **Adam:** I think,

[00:27:13] **Carol:** sure. I knew what you meant.

[00:27:15] **Adam:** what's that, that I mispronounced it? Koban Koban. Yeah, it's one of those words that, like I, I've read a million times and only heard when people are like saying, oh, you're saying it wrong. So like, I don't know what the actual pronunciation is. Pronunciation. they would say like, you're creating extra work, right?

[00:27:33] **Adam:** Like you're, you're making a take longer because you are creating a bunch of meta work to track the work, right? So like, if you could just have one ticket that has these 20 things in it and just do the 20 things and then move the ticket, then it'll take you, 90% of the amount of time that it'll take you to do all the other things, right?

[00:27:51] **Adam:** That it's like that extra 10% to do all the extra tracking. And I, I mean, I, that's gotta be based on truth. At least I can't argue against it. But I also agree with you that it's, there's something good about it.

[00:28:06] **Carol:** about the large story with smaller on

[00:28:08] **Adam:** I agree with Ben that, that there's something good about breaking it into small chunks and, and tracking it. I'm an over communicator,

[00:28:16] **Adam:** if you

[00:28:16] **Adam:** haven't noticed, by the way that I talk over everybody on this podcast.

[00:28:19] **Ben:** We, we, we've talked before, I believe about the getting things done system of work. And, and I can't say that I actually know that much about it, but I believe one of the tenants of that lifestyle is the moment that something comes into your brain, you gotta write it down. Otherwise it's gonna sit there and take up space and frustrates you and slow you down.

[00:28:40] **Ben:** And so I treat my, my Kaban board or my Jira epics very similarly. Like I'll be in the middle of code and I'll realize that something I had wrote previously was incomplete or incorrect or just something totally random. And I'll immediately just jump over into the Jira Epic, add a, just a note, a ticket that's just a title.

[00:29:00] **Ben:** Like, oh, double check the logic on this operation. Or don't forget to clean up something in a try-catch. And then I'll go back to what I was doing before. And now I feel like I don't have to keep that in my brain anymore, but I know it's track somewhere and I know I can come back and get it. And it may be be like three lines of code.

[00:29:15] **Ben:** But now was not the time to go and fix it.

[00:29:19] **Ben:** Um, so that it, it makes me feel like I'm being very efficient with my time.

[00:29:24] **Carol:** when I put my manager hat, I like the idea of doing whatever you want to do that makes you feel like you are more productive and makes your day easier. So if the cost is 10% of your time, versus another engineer who only puts in one story and it has 20 tasks on that and it saves them 10%, well whatever workflow makes sense for you and makes you feel productive and makes you feel like you're doing a good job, that's the workflow you should do.

[00:29:50] **Ben:** Mm. Like it

[00:29:53] **Adam:** It's cuz you're a good manager, Carol.

[00:29:55] **Carol:** I try side, side note, we're doing career conversations right now and the very last little block on all of our career conversations is, what do you need from me?

[00:30:07] **Ben:** is that, is that a performance review? I don't know what, I dunno what the term career conversation

[00:30:10] **Carol:** It's something they, they coined internally or maybe they picked it up somewhere, but call, but instead of calling it an assessment or a review, it's a career conversation.

[00:30:19] **Carol:** So it's a conversation we have that goes, Hey, here's what you're doing great. Here's what we're gonna do to help you move forward, promotions and raise, here's what we need from you. It's just a conversation about your career and about what you're doing. And they seem to go very well. They're a lot smoother here than I've ever had at any other job.

[00:30:40] **Adam:** I.

[00:30:41] **Carol:** the very bottom bullet point is, what do you need from me, me being the manager, like what can I do to provide you like more assistance and all of my team like put on there. I'm doing a great job. And that today also made me feel really good cause I finally working through all of their conversations and to see that they actually enjoy working with me and that they, I'm doing a good job.

[00:31:06] **Carol:** Yay. Makes, that's. That's amazing. Cause growing people is the best thing ever.

[00:31:12] **Carol:** So yeah.

[00:31:14] **Adam:** Virtual high five.

[00:31:15] **Carol:** Yay.

[00:31:16] **Adam:** So, I feel like I'm kind of the self-appointed secretary when we have meetings, cuz you know, people will be talking and we'll be, we'll come up with action items, basically, right? Like, things that are gonna need to be done as a result of a meeting or a discussion that was had.

[00:31:34] **Adam:** Oftentimes, I feel like I'm the only one who thinks we should be writing this down. So I do, you know, I pull out Notion or I create a, a couple of GitHub issues, whatever it's gonna be, and I start writing stuff down. And sometimes it's annoying. Sometimes I feel like, I'm annoying them. Sometimes I feel like, that I'm annoyed with them, that like I have to, I feel like I have to drag everybody kicking and screaming into being intentional and well organized about, you know, keeping track of what we're gonna do and when we're gonna do it.

[00:32:01] **Adam:** but, you know, it's, it's a small team. We do what we gotta do to get it done. Um

[00:32:07] **Ben:** It is, it is frustrating, I'll say, when you feel like you personally have a lot of SU success with tickets and then people don't create tickets, it, it is very frustrating cause you're like, just do it. It works.

[00:32:21]

## [00:32:21] What Makes A Bad Day?

[00:32:21] **Adam:** So, okay. We talked about what makes a good day. I don't know that we necessarily went into, we talked about the, the result of a bad day, but what makes a day a bad day?

[00:32:34] **Carol:** Not finding an endpoint to anything or having so much on your plate that your checklist tomorrow is so full. You know you're busy doing what didn't bad for when hardware doesn't work

[00:32:53] **Ben:** So sometimes though you talk about getting to an end point, I have terrible days where I feel like I don't even have a, an, an starting point. I have a problem and I just feel incapable of solving it. And, and it's one of those days where you just feel like you have to walk away and hope, you know, hope is not a great plan, but hope that, you know, some Chinese food and a good night's.

[00:33:18] **Ben:** Will somehow magically make the problem solution appear to you the next day.

[00:33:23] **Adam:** Do you guys just never have like production issues, you know, emergencies, corrupted data systems going offline because like the, these are all the things that spring to mind for me and you guys just totally, you know, if I'm, I'm not able to end the day on a good news, like, come

[00:33:39] **Ben:** well

[00:33:40] **Carol:** So over Christmas break I worked the whole week. Like I was one of the people that didn't take off, which was great cuz I worked extra and didn't have to take so much time off from being sick was good. But we did have a production issue where this PDF will not generate, I'm Googling solutions from anything I can possibly find.

[00:34:00] **Carol:** One solution is try changing the the file from HTM to html. Maybe that'll stop it from breaking on, creating the pdf. So I even tried that doesn't work still to this day the order will not approve. So what they've done is they've created a new order, duplicated everything and it approves. So no, I had a really bad day during that week where I've spent eight hours trying to figure out why PDF will generate when everything says it should generate and it's so not as, as it has at other jobs.

[00:34:35] **Ben:** I, I'll tell you on our end, unless I did something terrible that caused an incident, which feels crappy, there is a camaraderie that we have at work around incidents where everyone jumps on a call and there's someone from the security team and there's someone from the s r E team, and then there's front end engineers or backend engineers, depending on what's breaking.

[00:34:56] **Ben:** And it feels like everybody comes together to solve this problem. And even though it sucks, and sometimes even though the site is down, it, it, it feels like you're part of this. This unit and it, and there is something very nice about that. So I actually don't mind incidents all that much unless it's in the middle of the night.

[00:35:18] **Adam:** Yeah. I was gonna say

[00:35:18] **Ben:** the time. Yeah. Unless, unless you mess with my sleep, then that's a problem.

[00:35:23] **Adam:** or it's like Christmas day or something.

[00:35:25] **Ben:** Yeah. We actually had a denial of service attack at work, I think the day after Christmas.

[00:35:31] **Carol:** Oh.

[00:35:32] **Ben:** Yeah. And it was frustrating too because our, our whole infrastructure is behind CloudFlare,

[00:35:38] **Ben:** but it was, it was coming from so many IP addresses, but each individual IP address was of like a relatively low amount of volume that it wasn't tripping the right CloudFlare, firewall rules.

[00:35:53] **Carol:** those

[00:35:53] **Ben:** frustrating. Yeah. So they had a security came in and they updated the firewall to block certain. ASNs or something. I don't really know what, how networking works, but I guess there's a, an ASN that's like a block of the network. and that, and that mitigated it, but frustrating.

[00:36:10] **Adam:** I just had this idea of like, we'll just take the server, like just unplug the network cable. We're up, but nobody can get to us and services are running fine. Like, it's not our

[00:36:19] **Ben:** Look at those CPUs. Whisper, quiet,

[00:36:24] **Carol:** So yeah. Do your production issues take you down, Adam?

[00:36:26] **Adam:** I think what gets to me is if we have like multiple production issues in a week or you know, sort of like when, when it starts to feel like emergencies are the new normal, then that starts to get to me. Like I can deal with an emergency. I am no stranger to, you know, oh it's four o'clock on Friday and we just discovered a big problem and at the end of when it, when it's all dealt with, it's like 2:00 AM on Saturday and I've been, you know, at my.

[00:36:58] **Adam:** Since four o'clock on Friday, you know, skipped dinner, just working the problem and you know, not by myself obviously, like, you know, we sort of an that would be like an all hands type situation.

[00:37:09] **Carol:** like what Ben said, right?

[00:37:10] **Adam:** yeah. Yeah. Like, and there is some comradery in it like Ben was saying. I can recognize when that happens.

[00:37:17] **Adam:** I have done it a few times. I don't have a hero complex, thankfully. It's one, one positive treat I do have going for me. so, yeah,

[00:37:28] **Ben:** If we could tangent one second on hero complexes, not, not hero complexes necessarily, but being the hero and talk about, what makes a good day. Every now and then a customer will come to us where they did something terrible or they deleted data that they weren't supposed to, or something to that effect. and they're like, oh, is there anything you can do? And, and, we'll do something like we can, we can restore a database to a read replica somewhere and then pull the records. But then it's like not just pulling the records and I have to take those records and I have to, author. It's like I have to, Adam actually did this, I think just recently on a, on a previous episode where you, you take the records from one table and you use it to actually author insert statements that are the results set.

[00:38:12] **Ben:** And then you run those against a different database, you know, every now and then you do something like that and you feel like, like a ninja and that you save the day and the customer's like, oh my God, you guys are so amazing. I can't believe you did that. Thank you. Save my bacon. And and that feels great.

[00:38:26] **Ben:** That feels

[00:38:27] **Adam:** It, it feels good when it wasn't caused by your code. When it's the result. When it's the result of a bug that you wrote. You feel like the worst person on the planet.

## [00:38:41] Meetings

[00:38:41] **Ben:** I also, I, and this is not a dig at managers, cause I know managers have a lot of meetings, but if I have a day that is consumed by meetings, it's awful. I just, it feels like I didn't get anything done.

[00:38:54] **Carol:** my Tuesdays and Thursdays every day of the week. And I make sure if anyone's trying to schedule anything that Wednesday stays free because I'm, I need day that I can just write code and when I write for 30 minutes and to another meeting and then try writing again, it doesn't work. Like I'm not productive that way.

[00:39:12] **Carol:** I need time to actually get going and stay going. So I try moving everything off of my Wednesdays cause the same thing. Tuesdays and Thursdays just feel like a, like nothing got accomplished, but a lot got accomplished. Cause things are moving, right? Things are getting planned.

[00:39:28] **Adam:** Yeah. Now, I guess I should preface this by saying I, I average, probably just over one meeting a day,which is our daily standup meeting. you know, on, on a good week. Those are the only meetings that I have on a bad week. I might have two more meetings in the week that are like a half hour to an hour.

[00:39:48] **Adam:** So, With that caveat, I feel like I don't hate having a bunch of meetings. Right. Like I, it's not like I experience a lot of it, but, yeah, it's just like I, again, I'm an overcommunicator so when commu, I, I feel like communicating well and, and, you know, being able to accomplish something with that communication is, is work getting done

[00:40:12] **Ben:** that's very good of you, I, well, to be fair, I do like a meeting where I'm very engaged in the meeting,

[00:40:23] **Ben:** but you know how, I mean, I don't, I don't know, everyone has their own experience here, but I am definitely part of a number of meetings. 10 people are on the call and I probably don't have to be there,

[00:40:35] **Adam:** Yeah. You could have just sent me a summary of this meeting by email after it was over

[00:40:39] **Ben:** Yeah. Which I would not have read,

[00:40:40] **Ben:** but yes,

[00:40:41] **Carol:** somebody took notes.

[00:40:43] **Ben:** But, yeah, meanings are a tough one for me. Especially if I have something that I'm chomping at the bit to get done, then it's, it's like you're just in my way.

[00:40:51] **Carol:** I swear like that's every Thursday, like I go into story time going, oh, I won't turn my camera on for this hour long session of ticket planning because I'm gonna keep writing codes from what I was trying to wrap up yesterday. I really engaged in it. Then I have to stop myself and go. Turn your camera on.

[00:41:09] **Carol:** Pay attention,

[00:41:11] **Adam:** because then they'll be like, well, what do you think, Carol? And, and then you're like, sorry, I, I dropped my earbud. What was that?

[00:41:17] **Carol:** the dog was barking. I'm sorry,

[00:41:21] **Ben:** Well, I was listening to a previous episode and there was a clip from Carol and she was talking about how she'll be deep in code and then she has to stop to go to a meeting, and then people spend the first five minutes meeting talking about the weather, and she's like, the weather. I could have been coding right now.

[00:41:39] **Carol:** It's still, to this day, it drives me crazy. I, I don't know why I'm not a small talk person and I have to try very hard to not cut people off. Like we started story time today and the, one of our product, owners was talking about tater tots and how she eats her tater tots. And I'm going. 60 seconds. Give her 60 seconds.

[00:42:03] **Carol:** 60 seconds. Then say, what's your first story? Because that's enough

[00:42:07] **Adam:** Right.

[00:42:08] **Carol:** Let's get going.

[00:42:08] **Adam:** So is story time what you guys call like a standup?

[00:42:12] **Carol:** No, our standups are, 30 minutes, twice a week. Story time is sprint. This is our planning for the, what's going into the, we call it sprints, but we're on combine. So we just float whatever's ready to go to a top of the to do ready and you pick it up and throw it to the sprint and we just close it at the end of the month.

[00:42:28] **Carol:** Cause we don't really do sprints on my team. we just work, release, work release, work release, and we know what priorities are coming down from the customers. So story time is what I, is what we all call it. At first I was like, Ooh, naps, right? Like, let's story take a nap. Like, ah, it's story review. Got it pointing.

[00:42:45] **Carol:** Okay.

[00:42:46] **Ben:** one thing, circling back to my comment about being the hero for a customer, one thing that looks like it's gonna be a good day and then turns out to not be a great day, is when I'll be on a call with a customer and they express some sort of paid point or frustration that they're having with the application.

[00:43:04] **Ben:** And as they're talking, I immediately see a solution to their problem in my head and I'm like, oh, this is so great. I'm gonna be able to knock this out for them. It's gonna blow their minds. We get off the call, I go heads down for like two hours, and I hammer out a solution that I think solves their problem.

[00:43:18] **Ben:** Exactly. I'm so excited. I, I get in contact with our customer success people. I'm like, Hey, please send this over to, you know, Joe Blow at Acme Incorporated. Let them know that I was inspired by our call and I built this for them and I hope they're really happy with it. And then like, they couldn't care less.

[00:43:34] **Ben:** They're like, oh, great.

[00:43:35] **Ben:** And then that's it. And I'm like, Aw, my high just became a

[00:43:39] **Adam:** Oh man. I, I can remember some meetings that I went to, like sales meetings, early on in our company's history where like we would go in and I would demo the product and, and Steve would be talking about, you know, the vision for it. And, and the customer would be like, well, what about this and what about that?

[00:43:55] **Adam:** And I would just be quietly sitting there making the changes they're talking about. and and they're like, they're looking at the, the big, you know, projector screen and the stuff that they're talking about is appearing. Cuz I've, I'm like, not even refreshing. The screen's got like, hot module reloading going and it's just like, and they're like, This is magic.

[00:44:14] **Ben:** That's awesome. Yo, that's great.

## [00:44:18] OKRs

[00:44:18] **Ben:** I will say that nothing in my day ever rolls up to OKRs. Like OKRs just never enter my head whatsoever. I most, like 90% of the time, I can't even remember what OKRs stands

[00:44:31] **Carol:** Mm-hmm.

[00:44:32] **Adam:** objectives and key results.

[00:44:34] **Ben:** Yeah. none of that means anything to me.

[00:44:36] **Adam:** Well, it, that's funny that you say that because like you were talking about breaking down a task into really small scoped pieces, you could take your OKRs and break them down into the task that you then break down into your really small pieces, you

[00:44:47] **Ben:** I don't know. That feels just like an abstract.

[00:44:50] **Adam:** And, and I mean, I would. As somebody who doesn't do OKRs, you know, we're, we're just a startup, kind of wild West Gosling do whatever the heck feels right. But, I would venture to say that if your company does OKRs and you can't take them and break them down into tasks like that, then you're doing your OKRs or your tasks are both wrong.

[00:45:11] **Carol:** Yeah, so our OKRs, like we have KRS for the department, which we have to come up with for how we are gonna achieve our OKRs for the company. So like one of our OKRs is to, provide a positive impact in the communities where we live.

[00:45:28] **Carol:** So we have to, as the engineering department come up with a, with a key result that we can actually measure that says how are we going to achieve that? I do think about that often. And actually in my career conversation to my manager, which is the director of engineering, I was like, okay, I have a problem. Because I would much rather write code than work on the, or work on some of this management stuff because, so one of my things is I need to do a better job managing my time so that I can spend part of my day coding and part of my time actually working on the stuff.

[00:46:03] **Carol:** I don't wanna like growing people's fun building measurables. Not so much

[00:46:09] **Ben:** Maybe my problem is that I've never had OKRs that feel actionable, if that makes sense. But I, I think maybe all of the OKRs that, that have always been applied to my team or my department just feel very hand wavy and not like they, like, maybe they feel very strategic, but not tactical in any.

[00:46:32] **Carol:** like in like, some I've seen before are. Increase revenue by 20%. Well, as an engineering department, how do I impact that? Like, product determines what we write. Marketing needs to get our information out there. Sales needs to bring on new customers, I'm just gonna deliver it, right? Like they're gonna bring on a customer.

[00:46:52] **Carol:** We're gonna deliver everything for the customer. So all we can do is make that process more efficient, which then allows us to onboard faster, which could help revenue, but that doesn't really become a, a result that we can accomplish unless we have customers coming in. So they're not achievable always by the department and it's hard to puts to it.

[00:47:15] **Carol:** That makes sense with what you could deliver.

[00:47:18] **Ben:** Yeah. I think that's my problem. So that's why I, I, I feel like, I don't know how often I think we do o Okay. As annually, or maybe it's

[00:47:26] **Carol:** usually, they should be yearly,

[00:47:29] **Ben:** Yeah, I think it's

[00:47:30] **Carol:** Mm-hmm. typically it's annually and then you have a quarterly accomplishment to it. So for this, we expect to accomplish something in q1, which is gonna have a deliverable by q2. So that's when we expect that Oqr OKR to be met, or this is the breakout of how we're gonna accomplish it overall. Four quarters.

[00:47:49] **Ben:** I, I think maybe also because I've been on the Legacy platform for so long, it just wasn't taken seriously.

[00:47:56] **Ben:** I don't know, maybe, maybe when I go to the new platform and there's, you know, layers upon layers of management that suddenly it'll mean something. But I have just historically, it's always been, okay, everyone wants to do this OKR thing for a week.

[00:48:08] **Ben:** Let's get that done so that we can go back to our regular work. Like, that's kind of how I've always thought about it, but we'll

[00:48:14] **Carol:** I, I do feel like that they're perceived differently by engineering than they are by other departments.

[00:48:19] **Ben:** That could be,

[00:48:20] **Adam:** I feel like that's gotta be partially because the work that we do is literal knowledge work, right? Like if you're in manufacturing, your OKRs are gonna be like, you know, reduce, injuries in the workplace. And so you can do things to make the workplace safer. They're gonna be like improving, you know, throughput and production, whatever.

[00:48:43] **Adam:** These are all very easy to visualize, you know, ways to think about improving the way that you do your job when, when your job is squeeze. Value out of your brain. It becomes a lot harder, I

[00:48:58] **Carol:** It is. It is. It's, it's completely different.

[00:49:02] **Adam:** yeah.

[00:49:03] **Carol:** Mm-hmm.

[00:49:03] **Adam:** Okay. It sounds like we're about done here.

## [00:49:06] Patreon

[00:49:06] **Adam:** So this episode of Working Code is brought to you by Hero Complexes because only I can save the day and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording and editing costs. And our goal for this year, if you haven't heard, is we want to keep increasing our Patreon up into the right so that we can afford to get transcripts for accessibility improvements and searchability.

[00:49:38] **Adam:** and if you wanna help us out with that, you can go to Working Code. I'm sorry. Yeah, you can go to workingcode.dev and there's a support us link there, or you can just go to patreon.com/working code. Special thanks to our top patrons, Monte, Sean and Giancarlo.

## [00:49:52] Thanks For Listening!

[00:49:52] **Adam:** your homework this week, I wanna say it's a new year.

[00:49:56] **Adam:** You need to have a goal this year of come in and hanging out with your fellow working code listeners. And you wanna do that by going to workingcode.dev/discord. Join our Discord server. It's just a chat server like Slack or Microsoft Teams, I guess if people use that and enjoy it. Except it's better.

[00:50:13] **Adam:** It's for communities and it's good and we like it. We have fun there together. anyway, come join us at Discord. Have a good time, and we'll see you there. that's it for this week. We'll catch you next week. And until then,

[00:50:23] **Carol:** Your heart matters. Even you guys who run JavaScript on the client and server.

[00:50:30] **Adam:** Nicely done.
