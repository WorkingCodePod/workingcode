---
title: "070: Self Reflections"
description: "The crew looks back on the first 70 episodes of Working Code and reflects on what's working, what's not working, and what we'd like to see in the future."
date: 2022-04-13
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/070-self-reflections/id1544142288?i=1000557466108"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, the crew looks back on the first 70 episodes of Working Code and reflects on what's working, what's not working, and what we'd like to see in the future. I think we all agree that we've made it a lot farther than we thought we would. And, thanks to [Matt at Z-Cross Media][zcross], we always end up sounding _totes profesh'_ on tape even when we sounded like bunch of monkeys in the recording studio. We've also been super thrilled to see our Discord community become such a lively and diverse forum, even if half of it is just people mocking Ben for not having any tests. We're all excited to see how the show evolves; and, we hope you come on this adventure with us!

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[zcross]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/070-self-reflections.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** I know there's that children's book everybody poops. I feel like maybe,maybe there should be a everybody

[00:00:05] **Ben:** fails book.

[00:00:06] **Carol:** It's kind of like that. Yeah.

[00:00:08] **Tim:** fails

[00:00:08] **Tim:** for sure.

[00:00:09] **Adam:** we just found your next career. Ben

[00:00:12] **Adam:** w when they shut down the legacy system, instead of going and learning a new

[00:00:14] **Adam:** language, you'll write children's books about.

## [00:00:17] Intro

[00:00:36] **Adam:** Okay. Here we go. It is show number 70 and on today's show, we're going to do some self-reflection. We're going to look at ourselves in the mirror and look at all those freckles and pimples and just tell ourselves how terrible we are. And,just the thing that you're supposed to do every once in a while to cut yourself down. And, but as

[00:00:53] **Adam:** first.

[00:00:54] **Carol:** Or build yourself up.

[00:00:55] **Adam:** No just cutting ourselves down. My ego's too big as it is. So I need to like rein it in every once in a while.

[00:01:01] **Tim:**

[00:01:01] **Adam:** but as usual, we'll start with our triumphs and fails. And Carol, you get to go first. What's going on?

## [00:01:06] Carol's Triumph

[00:01:06] **Carol:** All right, I'm going with the triumph, you guys. So I talked on the last episode about pusher and about pub subs and just some ideas that we had while the legacy app is written in ColdFusion. So started playing with web sockets, just to kind of understand what was going on and five and a half hours later, who he still can't get a channel to create and are just, flipping out.

[00:01:29] **Carol:** Cause we're pretty convinced we're dumb at this point. Have no idea what's going on. We check all the settings, nothing is working for us. And finally, we get one of the server admins on and he's like, let's just give this a try. And they uncheck the box, start it off. Restart it, check the box, turn it back on.

[00:01:48] **Carol:** We tested again, suddenly we have channels. So it's literally someone enabled it and no one actually made sure it worked and we just assumed it was going to be working. And we thought we just clearly didn't understand how to put this new channel in the application CFC, and then just go subscribe. Like we just were like, there should be like three, four lines of code just to make sure it works.

[00:02:11] **Carol:** half of the day over half the day's gone and we're flipping out going, we felt like idiots, but learning is fun. And it's always good when you get the chance to figure out what's going on and debug something. And yeah, so it's still a triumph for us because at the end of the day it's working and now we have the ability to finish our kind of demo for everything one day.

[00:02:32] **Tim:** Cool. So pusher was easier than you expected,

[00:02:35] **Tim:** huh?

[00:02:35] **Carol:** Oh, we're not going with. yeah, pusher, the concurrent connection is going to cost us way too much money for what we're trying to accomplish. So I'm not even putting that in the presentation. I can put it in. It's going to be in there in a footnote as like, Hey, this is another option that we can use in place of something.

[00:02:54] **Carol:** But the cost is going to be more than I think we want to spend on this.

[00:02:57] **Carol:** So, yeah.

[00:02:57] **Ben:** So you're to be clear, you're using the native WebSocket functionality that ships with

[00:03:02] **Ben:** ColdFusion.

[00:03:03] **Carol:** Yup. Yup. That's

[00:03:04] **Carol:** what we're going to do.

[00:03:05] **Ben:** I can't remember. I looked at that a long time ago. is that bi-directional like, can the client make calls to the server or web socket or is it just from the server

[00:03:13] **Ben:** down to the client?

[00:03:14] **Ben:** Do you

[00:03:15] **Ben:** know?

[00:03:15] **Carol:** I think it server to the client, I think, but don't hold me to that again. We're

[00:03:19] **Carol:** still learning how this is

[00:03:20] **Carol:** working. Am I wrong,

[00:03:22] **Carol:** Adam?

[00:03:23] **Adam:** I think it's bi-directional

[00:03:25] **Carol:** it.

[00:03:25] **Adam:** I want to say.

[00:03:28] **Ben:** Oh,

[00:03:28] **Carol:** The code I have and right now is not doing that. So that's why I said maybe

[00:03:33] **Carol:** not.

[00:03:34] **Adam:** Yeah.

[00:03:34] **Ben:** Cause I vaguely remember having to create a ColdFusion component that had some special methods on it that was like channel, join and message. Receive that kind of something.

[00:03:44] **Carol:** Yeah.

[00:03:44] **Carol:** Maybe I'll let you know next week after we get the little demo up and see if WebSockets on the CF

[00:03:50] **Carol:** built-in is what we're actually gonna use. That's just what we're

[00:03:52] **Carol:** putting out for now.

[00:03:53] **Carol:** So

[00:03:53] **Carol:** yeah,

[00:03:53] **Adam:** Well, we'll expect an update next week.

[00:03:55] **Carol:** absolutely. You'll get one. All right. Let's let you ban once you got,

## [00:04:00] Ben's Triumph

[00:04:00] **Ben:** I'm going to go with a triumph. And that is that a, this sort of loops back to last year. I believe my big goal for last year was to get more comfortable with design systems

[00:04:09] **Carol:** yeah.

[00:04:10] **Ben:** it was a very slow start and I sort of trickled in some, Homegrown components locally in my angular JS application. And, I've just been feeling really good about it lately.

[00:04:21] **Ben:** I'm seeing definitely the benefit of having a design system component library, ready to go. building new UI has just feels like it takes a lot less effort. without a design system, I always feel like I can do the ColdFusion code relatively quickly. And then it feels like a much larger level of effort than getting a client side code to look right. But, having buttons and drop downs and text areas and check boxes. And I don't know, in some modal styles,I'm definitely seeing that my user interface generation is picking up speed. Like newer features are becoming easier and easier to build. I'm S I'm still like, very far away from really wrapping my head around design systems.

[00:05:02] **Ben:** But, I'm at the point now where I've gotten enough of it locally to really start to see the value. And I'm pretty excited

[00:05:09] **Ben:** about that.

[00:05:10] **Carol:** That's awesome.

[00:05:10] **Adam:** I've always wanted to have a nice like component library to pull from a nice design system to even just tell me how things should be. Even if it's not components never had one. And it sounds like.

[00:05:21] **Carol:** Sounds amazing.

[00:05:21] **Ben:** the hard part for me has been, giving into not having a completely consistent way of doing things. And what I mean by that is. in the design system makes sense as full-fledged components where it's doing content projection into a shadow Dom kind of a thing, but then some just make sense as a CSS classes that are ready to be used and don't actually need to have really fancy components stuff.

[00:05:48] **Ben:** And at first I was really struggling with that. Cause I sort of wanted everything to be a component because I figured it was all supposed to be fancy and capsulation and everything was components all the way down. But that started to just look way too complicated and having now a mix of complicated things or components and simple things are just CSS classes.

[00:06:10] **Ben:** that once I got my head wrapped around that's okay. Then it became a lot easier to create reusable

[00:06:16] **Ben:** stuff.

[00:06:17] **Tim:** still black magic to me. I don't work in it often. I, we have people that do that and they're really good at it. And they're really fast if the few times I've had to really do some stuff. I struggle. It's total struggle bus. So

[00:06:30] **Tim:** it's yeah. More power to you. Been.

[00:06:33] **Ben:** Yeah. So yeah, feeling good a year short, but I'm feeling good about it. Adam, what about you? What are you guys.

## [00:06:40] Adam's Triumph

[00:06:40] **Adam:** So we've talked in the past about, my goal for the year being to one of my goals for the year being to get back into exercising, I kind of let myself go here toward the last few months or year of the pandemic.

[00:06:52] **Adam:** And, so one of the things that stopped me, was I was getting discouraged because my back muscles are too weak to continue progressing some of the other exercises I was doing. cause I could tell like my weak back was causing me to have bad form and possibly injured myself. So that was discouraging and I kind of stopped working out in part because of that also because I'm lazy.

[00:07:12] **Adam:** And and so I got, I bought myself a Roman chair, which is a thing that like you, it lets you bend at the hips, to do like lower yourself down and raise yourself back up,to work out those back muscles. And I used it for the first time. And I felt, I was like dead yesterday. I was asking myself, okay.

[00:07:31] **Adam:** I was kind of planning like,

[00:07:31] **Adam:** okay, I kind of want to work on endurance. So like lots of reps with no weight to, to make it so that, I don't have back pain from standing all day at my standing desk, but I also like want to be able to progress these weights. So I kind of want to, do with weights to build strength so that I can do these other exercises that I'm held back on. And after just doing like, two and a half sets of 20 reps with no weight this morning, I was like, I hope I survive this week.

[00:07:56] **Tim:** So is that where you, like, it's a little chair and you kind of lay down on your chest and you're well, on your abdomen, your chest kind of hangs over it and your knees are like kind of blocked and you do

[00:08:07] **Tim:** inverted, setups.

[00:08:09] **Adam:** Yeah. Kind of, so, yeah. Yeah. So you can picture it, you're laying down on your stomach, but there's nothing under your stomach below your hips. Right. So it's all like below hips and then you're hinging at the hips down. So you start out maybe flat and you hinge at the hips down and then you have to like lift yourself back up to even, and some people do it like a hyperextension where you come back past horizontal.

[00:08:27] **Adam:** and I'm not going to get into the bro science there of whether or not you should. so, yeah, but that's

[00:08:32] **Tim:** yes, sir. Sounds like torture.

[00:08:34] **Adam:** Oh man. there was a time in my life where I could like lay down on the floor and do 200 setups. That is not me anymore.

[00:08:41] **Adam:** And,

[00:08:41] **Adam:** uh, yeah. Yeah.

[00:08:43] **Carol:** not going to lie. When you said a roaming chair, I immediately thought of like a chair going around the house that you had to go, like find this is my new

[00:08:52] **Carol:** workout.

[00:08:53] **Tim:** no.

[00:08:53] **Carol:** roaming chair.

[00:08:55] **Tim:** Roman Legionnaire

[00:08:57] **Carol:** Listen, Emma, in my head, it was way funnier. Okay.

[00:09:03] **Tim:** I'm playing hide and seek with a chair.

[00:09:04] **Adam:** Like, like a roaming alarm clock

[00:09:06] **Adam:** sort of

[00:09:06] **Adam:** situation. Yeah.

[00:09:09] **Adam:** So that's me, slowly, but surely now, hopefully, maybe sort of, kind of, going to get stronger.

[00:09:14] **Adam:** So that's me. Yeah. How about you,

[00:09:15] **Carol:** Yeah. Well, good luck.

[00:09:16] **Adam:** Thank you.

## [00:09:17] Tim's Triumph

[00:09:17] **Tim:** Yeah. So I mentioned this in the after show last episode, but,I'll just bring it as my triumph here because I'm excited about it. So for work, we have like an annual thing where they pick different people from each company. We were part of a huge global company that has many companies inside of it.

[00:09:32] **Tim:** And, we get to go to. Places to like, do best practices and share ideas with our peers. And, this year is in Barcelona. So I get to go to Barcelona, and in may, so really looking forward to it. I haven't been to Barcelona since I was in my mid twenties, so, and I really enjoyed it then.

[00:09:48] **Tim:** And so afterward my family is going to join me. So we'll have a little family vacation afterward in Barcelona. So yeah, just super stoked about that. So we have again, second episode in a row

[00:09:59] **Tim:** for triumphs.

[00:10:00] **Carol:** Hey.

[00:10:01] **Tim:** Yeah.

[00:10:02] **Adam:** pew,

[00:10:03] **Tim:**

[00:10:03] **Carol:** And by family, you mean your podcast, family, right?

[00:10:07] **Carol:** That's who shortening you?

[00:10:08] **Carol:** Us all of us.

[00:10:10] **Tim:** I mean y'all, if you show up, you can hang out.

[00:10:14] **Adam:** why do you think he's checking so many.

[00:10:16] **Tim:** Right? Yeah. And I get that some of my company, every, like when you make your 15 year anniversary and 20 year anniversary, you get like money to spend. You can only spend it on travel. So it's, I'll get like $3,000 and I can re get reimbursed for $3,000 with the travel expenses. So all that's going to go toward that.

[00:10:34] **Tim:** So just kind of all fell in place. And after two years of staying at home and yeah, I'm so looking forward to a trip and we need this so bad.

[00:10:42] **Carol:** So I think it's really cool when companies do that, when they're like, you have to use it on travel because it forces you to detach and it forces you to take a vacation. And after being somewhere for so long, you really need to know that it's okay to just step away and enjoy a vacation. And I think it's good when they're like, you have to

[00:10:57] **Carol:** use it on travel, wherever it is.

[00:10:59] **Carol:** Just take a

[00:10:59] **Carol:** break.

[00:11:00] **Tim:** yeah. Otherwise I'd, I'd buy, some kitchen tool or

[00:11:03] **Carol:** Electronics.

[00:11:05] **Tim:** some gardening thing and be like, oh yeah, for sure.

[00:11:11] **Adam:**

## [00:11:12] Reflections On The Podcast

[00:11:12] **Tim:** So, it's a time for self-reflection.

[00:11:15] **Adam:** when isn't it

## [00:11:16] Making It This Far

[00:11:16] **Ben:** Well, I mean, I'll just kick it off and say that I started never thought we would make it this far and having nothing to do with any of us individually, just, there's a lot of work that goes into us into this and showing up and The editing and everything. And I mean, we've been doing it

[00:11:32] **Ben:** for this will be 70

[00:11:33] **Ben:** episodes.

[00:11:34] **Adam:** 70 weeks.

[00:11:35] **Ben:** that's kind of crazy. I'm pretty

[00:11:37] **Ben:** proud of that.

[00:11:38] **Tim:** yeah.

[00:11:39] **Carol:** Yeah.

[00:11:39] **Ben:** I mean, what

[00:11:39] **Ben:** we've

[00:11:40] **Ben:** missed one

[00:11:40] **Ben:** week ish.

[00:11:42] **Carol:** I've missed a

[00:11:43] **Adam:** yeah, that's true.

[00:11:44] **Adam:** we did a take a week

[00:11:45] **Adam:** off in terms of, production, Matt, put out an episode for us of highlights. I kind of forgot about that, but I was also thinking not only did that happen, but we,that spanned multiple holidays here in the U S we had Thanksgiving and Christmas and managed to make it through those.

[00:12:01] **Adam:** So,

[00:12:02] **Adam:** yeah.

[00:12:02] **Adam:** hella proud.

[00:12:04] **Carol:** Oh, absolutely.

[00:12:05] **Carol:** And I don't feel like we're running out of topics. That was my concern up front, unlike after a few, what are we going to talk about?

[00:12:12] **Carol:** Like I'm out of things and then suddenly we just show up

[00:12:15] **Carol:** and there's conversations to be had.

[00:12:17] **Adam:** There's always something to

[00:12:19] **Adam:** be talking

[00:12:19] **Ben:** Absolutely. And, I like that we all sort of have different perspectives on stuff. Like we're not all just working on the same type of thing and we don't all exactly have the same skillset. Obviously we're all, engineers here, but we work in different technologies and in different types of applications.

[00:12:37] **Ben:** Slightly different types of roles. Carol just moved into a completely different roles. So that's going to be exciting to see how that plays out here on the show. But I feel like we have a lot of good voices and, not to

[00:12:49] **Ben:** pump Carroll

[00:12:50] **Ben:** up

[00:12:50] **Ben:** too much.

[00:12:51] **Ben:** but when she's not here on the show, it feels very different to me.

[00:12:55] **Ben:** I think she really brings a different perspective she really brings that not white man perspective to the show,

[00:13:01] **Ben:** which

[00:13:02] **Carol:** diversity you guys.

[00:13:05] **Tim:** she's like the rug, she's bringing really brings a room together big Lebowski.

[00:13:11] **Carol:** Oh yeah. I didn't get that.

[00:13:13] **Tim:** I love that. You never get any reference.

[00:13:15] **Carol:** No references.

[00:13:16] **Adam:** obviously you are not a golfer.

[00:13:18] **Tim:** Yeah. She really brings the room together.

[00:13:23] **Ben:** yes.

[00:13:24] **Carol:** Thank you guys.

## [00:13:25] Show Topics

[00:13:25] **Tim:** It was funny. It's like, so sometimes I would go into a podcast for like, for the. We'll just let people know. We don't put a whole lot of work into figuring out about a topic. Right. I mean, so sometimes we show up at seven, we usually recorded seven on Thursday as like, what are we talking about? Like, well, I don't know.

[00:13:42] **Tim:** And we kind of bandy about for a little bit, then all of a sudden we're like someone throws something out there and sometimes we'd be like all that, we can't talk for more than 10 minutes on that in my mind. And then we wind up an hour and a half long show.

[00:13:52] **Tim:** Right.

[00:13:53] **Carol:** Adams Adams cutting us off going all right. I think it's time to end this

[00:13:57] **Carol:** when you

[00:13:57] **Tim:** Yeah. All right, guys, are we done

[00:13:58] **Carol:** are we done now.

[00:14:00] **Tim:** We've been talking about this for an hour and a half. So I love that. I really do love that. It's just kind of, it, w when Adam kind of approached me about the idea that the show is kind of like a water cooler kind of thing, you're just talking with your coworkers at work about coding is not anything, no technology specific, no, nothing, is not a specific language programming podcasts.

[00:14:20] **Tim:** It's just kind of a day in the life. Right. And I think, we're patting ourselves on the back here. I think we have achieved that. Well, maybe, some of our folks in the Discord can say they feel the same thing, but, I think we've achieved that. It's kind of like a conversation among friends about stuff they love to do.

[00:14:35] **Ben:** Yeah, absolutely. And Matt always makes us sound way better than I think we sound during the show. You know,every Thursday night I leave the office and I go into the bedroom. My wife is laying there watching television, and she's always like, oh, how'd the show go? And some nights I'm like, oh, It was okay.

[00:14:54] **Ben:** It was okay. Didn't really flow exactly how I would've liked it to flow. And then Matt will drop the recording. I'm like what? We didn't sound like that. It's a, so He's just been doing an

[00:15:04] **Ben:** awesome job.

[00:15:05] **Tim:** Thank you, Matt. We appreciate you. Patrons who support us. Cause that's the only way we can pay him to do this.

[00:15:10] **Ben:** Absolutely.

[00:15:12] **Adam:** Indeed.

[00:15:12] **Ben:** What else is good? What do people liking?

## [00:15:14] Learning From Eachother

[00:15:14] **Carol:** Oh, I'd love to them. Learn. And back to my triumph, peanut, like, I feel like I constantly am learning from you guys and it's either something new I pick up that didn't know, or you're just expanding my knowledge. further in something I do know about. So I just, I love that aspect of it

[00:15:29] **Ben:** That's awesome.

## [00:15:30] Triumphs And Fails

[00:15:30] **Tim:** I like the, the tribes and fails thing that we do. I liked that because it forces me during the week too. Strive to have a triumph, right. I'm doing that. I'm like, maybe it's something I'm avoiding. Cause I just feel like it's too hard and I'm like, you know what? This would be a great triumph. If I just put myself to it, I can bring this up on Thursday.

[00:15:51] **Tim:** So that's really, that's helped me in those times when, maybe I, we didn't have quite enough gas in the tank to do what I think I could do. So it just gave me the little extra. So I love

[00:16:02] **Tim:** that.

[00:16:03] **Adam:** Nice. I like that. It normalizes failure.

[00:16:06] **Adam:** That was, the original goal. when I came up with that sort of segment idea was like, I everybody always talks about their success stories and nobody ever talks about how important it is to fail along the way.

[00:16:16] **Ben:** that's a great point. I find it just a satisfying, honestly, to talk about a failure week as a triumph week. It just feels, I don't know. I just very cathartic. There's also, just by saying it out loud, you get it out of your head and it kind of just like a mental reset and doesn't feel as heavy going forward, which is

[00:16:35] **Ben:** nice.

[00:16:36] **Carol:** It reminds me I'm normal that I sell. Everyone else. Like I, you guys don't get it right every time. And when the people I look up to you are always succeeding and I'm the one sending back, like, man, I'm not getting it. Right. It's nice to see that someone else's are so failing. Sorry. I'm sorry. You failed and didn't get it right.

[00:16:54] **Carol:** But I'm glad I didn't do it alone. Okay.

[00:16:57] **Ben:** I know there's that children's book everybody poops. I feel like maybe,maybe there should be a everybody

[00:17:02] **Ben:** fails book.

[00:17:03] **Carol:** It's kind of like that. Yeah.

[00:17:05] **Tim:** fails

[00:17:06] **Tim:** for sure.

[00:17:06] **Adam:** we just found your next career. Ben

[00:17:09] **Adam:** w when they shut down the legacy system, instead of going and learning a new

[00:17:12] **Adam:** language, you'll write children's books about.

## [00:17:14] The Discord Community

[00:17:14] **Tim:** Yep. And can we just talk about the Discord community that we have going on? It's I mean, it's so it's, I didn't expect it to take off as well as it did, but it's like, it's very active. Honestly, guys, I have to, sometimes during work, I have to turn it off just because I'm like, I don't, I w I want to join the conversation, but I really need to get something done here, but yeah, it just, it's just a great community there on Discord whereby you know, we haven't had too many fights.

[00:17:42] **Tim:** Uh,I wouldn't even consider, you know, we had one little thing that kind of happened is, a little disturbing, but I wouldn't consider that a fight, but yeah, everyone gets along and it's been supportive And

[00:17:52] **Tim:** so that's pretty awesome.

[00:17:53] **Adam:** Okay. And I mean, there's so many people there. We're coming up on a hundred. I think there's like 70 something,

[00:17:58] **Adam:** 75

[00:17:59] **Adam:** people in there. They're

[00:18:00] **Adam:** they're not all online

[00:18:01] **Adam:** right now, but.

[00:18:02] **Carol:** Yeah.

[00:18:03] **Ben:** I always wished that I could participate more. I feel flustered most of my life and, and I wish I had more

[00:18:10] **Ben:** concentration to get in there and

[00:18:12] **Ben:** participate because when I do it's.

[00:18:13] **Carol:** Yeah.

[00:18:14] **Adam:** think what you need. Ben

[00:18:15] **Adam:** is another app on your phone, the little notification count on it. That just steadily climbs because you never check it.

[00:18:22] **Tim:** Like your emails.

[00:18:23] **Adam:** And your text messages.

[00:18:26] **Tim:** I'm on vacation. I'm still at inbox zero. I cannot get behind on emails.

[00:18:31] **Ben:** I'm at 1,496 text

[00:18:34] **Ben:** messages.

[00:18:36] **Tim:** You Philistine.

[00:18:39] **Ben:** Good times.

[00:18:40] **Adam:** I feel physical pain from that.

[00:18:43] **Ben:** sure. Half of

[00:18:43] **Ben:** them are just like Octa verification codes

[00:18:46] **Ben:** and stuff.

[00:18:47] **Carol:** yeah,

[00:18:49] **Adam:** You signed into stuff that often, huh?

[00:18:52]

[00:18:52] **Carol:**

## [00:18:52] Having Fun

[00:18:52] **Ben:** say, and this is sort of a meta point, but I think I just have a lot of fun. I feel like we don't take ourselves too seriously and we come in, we have a good time every now and then we try to be more serious. I don't think I last very long and, I don't know. I just it's the highlight of my week coming in a recording with you all.

[00:19:10] **Ben:** So I'm very

[00:19:11] **Ben:** thankful for that.

[00:19:13] **Carol:** And I will say the episodes that we've done, where we were like trying to be very structured. Those are the ones I didn't like. Those are the ones I'm like, this feels really forced and it feels like blah, like I just, it's not right.

[00:19:27] **Ben:** Yeah. And

[00:19:28] **Ben:** the reality is there's day night rolls around and this is not always the first thing I want to do in my evening. but by the time we're done, I'm like always jacked up and I have to take some action. And they'll PM's to knock myself out so that I could

[00:19:43] **Ben:** sleep

[00:19:44] **Tim:** We gave him a drug problem guys.

[00:19:47] **Adam:** Success.

[00:19:49] **Ben:** nothing like Advil, PM chaser to my melatonin.

## [00:19:55] Room For Improvement

[00:19:55] **Tim:** Yeah. So the things that we have, what's not going to great, what's room for improvement. I would think we could say, we got, I think we got Adam, Cameron is watching. He's very good at telling people what could be better and what's not so great. so yeah,maybe he can jump in unless you guys got something.

[00:20:14] **Adam:** I don't think we've mentioned yet that there

[00:20:16] **Adam:** is, for our Discord, community members. We invited them to watch us record this one live. So yes, there are people watching us live and participating in the chat here. And, yeah, he says, Adam said, this could be better, Tim.

[00:20:33] **Tim:** Yes. I agree. You're good at it.

## [00:20:38] Deep Dives

[00:20:38] **Ben:** My, my biggest reservation is I always want to talk more about code. I know sometimes I think we try to stay a little bit higher level, which I totally get because they have a wider audience, but sometimes I just want to go deep on something and nothing in particular, just, I just get some jazz stuff about

[00:20:56] **Ben:** code

[00:20:57] **Adam:** Well, then you would need an extra Tylenol PM.

[00:21:01] **Ben:** I'd have to shift my whole sleeping pattern Thursday

[00:21:03] **Ben:** nights.

[00:21:04] **Carol:** There's a nice, you're going to walk away and have to go write something. Cause you're like, so on that level, you like code must be produced now.

[00:21:12] **Tim:** Yeah. I mean, I agree with that sometimes, like, we are we really educational or where you more entertainment. And I honestly think we're kind of entertainment with somewhat of an educational slant to it. and that's okay. because I don't know if a podcast is really the format for like a deep dive kind of learning on things.

[00:21:31] **Tim:** Right. that's kinda more tutorial kind of video, structures that you can go back and play and things like that. But it's,I would like to go deeper on, on certain topics.

[00:21:41] **Tim:** I just don't know how that, what that would look like,

[00:21:44] **Adam:** T to use what here in the United States, we call English class or English teacher terms. I don't know what the heck like English class in the

[00:21:50] **Adam:** UK or in Spain, like whatever literature.

[00:21:53] **Tim:** but they call it real English

[00:21:55] **Adam:** Oh, they, I think they call it language

[00:21:56] **Adam:** arts. anyway, the, when I pitched this podcast to you guys, I said coding is the setting, but it's not the plot.

[00:22:04] **Adam:** Right. We are all coders. And that is a background to what we're doing

[00:22:10] **Adam:** here.

[00:22:10] **Carol:** yeah,

[00:22:10] **Carol:** This is the human

[00:22:11] **Carol:** side of it.

[00:22:13] **Ben:** That said, we also sort of talked about it being just, bunch of people at the bar hanging out after conference kind of thing. And I definitely talk about a lot of code at a

[00:22:22] **Ben:** conference.

[00:22:23] **Carol:** Yeah, I

[00:22:24] **Carol:** agree. Yeah,

[00:22:25] **Tim:** that's true.

[00:22:26] **Ben:** I mean, here's the thing, like when Carol was doing the, the mail stuff and inbound processing and natural language processing, it's like she, she went into it, but it wasn't super, super detailed, but that was a lot of fun. And that was,she was talking about a lot of technologies that I have no experience with.

[00:22:41] **Ben:** So that was especially fun. I don't know. I just, if I want more of that,

[00:22:47] **Carol:** Yeah, I do like that side of it.

[00:22:49] **Carol:** I agree.

[00:22:50] **Carol:** We can throw more in there.

[00:22:51] **Adam:** Yeah. Yeah. It's our podcast.

[00:22:53] **Adam:** We can do whatever we want.

[00:22:55] **Adam:** We can post job without on episode one,

[00:22:58] **Ben:** what'd

[00:22:59] **Carol:** what that means.

[00:23:01] **Adam:** you had another pop culture reference that probably nobody gets,

[00:23:04] **Adam:** uh, don't worry

[00:23:05] **Carol:** imposed somebody somebody's somebody's Jabba the hut

[00:23:09] **Carol:** on

[00:23:10] **Adam:** episode

[00:23:10] **Carol:** There you go.

[00:23:11] **Ben:** don't know. I don't know what's going on here.

[00:23:14] **Adam:** to south park reference.

[00:23:15] **Adam:** Let it

[00:23:15] **Adam:** go

[00:23:16] **Carol:** is it Java or

[00:23:17] **Carol:** Java?

[00:23:19] **Ben:** Uh, I think,

[00:23:20] **Carol:** BA okay. It'd be

[00:23:21] **Adam:** with, to be.

[00:23:23] **Carol:** it's like Java.

[00:23:24] **Ben:** and then I didn't realize this I've been slowly watching a book of Boba fat

[00:23:30] **Carol:** Yeah.

[00:23:31] **Ben:** hot is like a family name or something, or there's a bunch of huts. I did not know that.

[00:23:36] **Adam:** yeah.

[00:23:37] **Ben:** I thought Java though. It was like a title. Star

[00:23:39] **Ben:** wars

[00:23:40] **Adam:** Nope. You're not enough of a star wars nerd.

[00:23:41] **Adam:** Sorry, you're

[00:23:42] **Ben:** No, no, no. I just like all the pupils and stuff.

[00:23:47] **Carol:** Lightsaber.

[00:23:48] **Adam:** Cool.

[00:23:49] **Ben:** So what

[00:23:49] **Ben:** else is going on?

[00:23:50] **Adam:** I liked, I like Tim's framing what? What's the room for improvement?

[00:23:54] **Adam:** Nothing. We're perfect.

## [00:23:58] Episode Length

[00:23:58] **Tim:** I just, I'm just curious how our listeners feel about the length of the episodes. Cause sometimes they get pretty long, right? I haven't heard anyone complain.

[00:24:05] **Adam:** Lately. Some of them have been pretty short too. I mean, we've come in with clocked in the last several between like 30 and 40 minutes.

[00:24:11] **Ben:** Yeah.

[00:24:12] **Tim:** which, I mean, that's all about the time I can hear

[00:24:14] **Tim:** myself talk, honestly. So

[00:24:16] **Adam:** I think something that we've kind of said

[00:24:19] **Adam:** going into this is we're not going to force ourselves to talk for any specific amount of time. It's just going to be, when we decide that we've talked ourselves out and we don't have anything to say, then we're going to stop.

[00:24:28] **Carol:** Oh, perfect. 1.2 times. Speed. So an hour is fine.

[00:24:36] **Tim:** So someone else said I listened to whatever y'all have to save for

[00:24:40] **Tim:** however long, all

[00:24:42] **Adam:** oh, name namesake is a Adam Cameron,

[00:24:45] **Carol:** not you, not use

[00:24:47] **Tim:** Yeah, my, my, hater, but that was the goal. That was my goal for joining this podcast. I wanted some haters

[00:24:53] **Ben:** I think we're definitely better about it now than we were in the beginning. I do feel like in the beginning there were a couple of episodes where it felt like we were trying to drag it out

[00:25:02] **Ben:** with it fits of like, we're trying to fill time. And, but now I feel like we, we go until we have nothing and then we stopped.

[00:25:09] **Tim:** Which Ben gets sleepy around

[00:25:10] **Tim:** eight. So it's like ready for

[00:25:14] **Carol:** He's over there. Yawning and

[00:25:15] **Carol:** rubbing his

[00:25:16] **Adam:** you gotta pregame the podcast with caffeine and then it takes

[00:25:18] **Tim:** yeah.

[00:25:19] **Adam:** at the end to

[00:25:20] **Tim:** Yeah.

[00:25:20] **Tim:** it, gets up to the middle podcasts puts on his jammies.

[00:25:23] **Ben:** you know, what'sbeen messing me up. We've been watching a resident alien

[00:25:26] **Ben:** comedy shows are half an hour long and our nighttime TV routine tends to start heavy with drama and then end life with the comedies. And usually we end with a half hour comedy, like when we're going through Schitt's Creek or a modern family, that.

[00:25:43] **Ben:** kind of stuff, but a resonant is an hour long.

[00:25:46] **Ben:** And so it's been confusing us. And I ended up going to bed a lot later. I mean, a lot, 20 minutes

[00:25:51] **Ben:** later than I normally do. So it's, I'm all over

[00:25:54] **Ben:** the

[00:25:54] **Adam:** We'll just

[00:25:54] **Adam:** pause an episode halfway through.

[00:25:56] **Tim:** I love that you have a scheduled entertainment regimen, you get your dosage so bad. It's so bad. That's

[00:26:05] **Carol:** Creature of habit.

## [00:26:06] Guests And Interviews

[00:26:06] **Tim:** So one thing, maybe I'm kind of going into the differently thing. I really enjoyed this. I think it's a nice breather when we have either a guest host or we have a person that we interviewed, like when, we had six on and talked to him.

[00:26:21] **Tim:** That was really nice. And then having Scott, even though we didn't have, Caroline, unfortunately, but you had Scott on as a cohost. I think that was really nice. I think that's kind of breaks things up.

[00:26:31] **Tim:** And Brian, we had Brian and we did the individual. That's one thing. Other thing we did to kind of extend out the year

[00:26:37] **Tim:** we did individual interviews.

[00:26:38] **Tim:** I talked to, Adam and, yeah,

[00:26:42] **Carol:** Um, Ben and I, we kind of dropped the ball there. We were going to do my QA team, but they kind of had issues come up. So, so working on that,

[00:26:51] **Tim:** That's all right. It's room for

[00:26:52] **Tim:** improvement.

[00:26:54] **Ben:** But that's true. I've actually, I did not think I would enjoy having guests on mostly because I get very stressed talking to people. I mean, I'm very comfortable talking. Yeah. Yeah. I'm very comfortable talking to you three, but having someone else joined the party, especially the idea of interviewing someone on my own, that was like deer in headlights.

[00:27:14] **Ben:** but once, once it's on and it starts, it's a lot of fun.

[00:27:18] **Tim:** You're very inquisitive, man. He asked really good

[00:27:20] **Tim:** questions to be. I mean, you have this sort of sense of wonder when you talk to folks.

[00:27:25] **Carol:** And the light in your eyes, when you ask the question makes me want to go into it so deep. Cause you're just like, oh, tell me more.

[00:27:32] **Carol:** And we're like, yes.

[00:27:33] **Ben:** I love this stuff so much.

[00:27:35] **Carol:** the smile. You

[00:27:36] **Carol:** guys all

[00:27:37] **Tim:** E even we're talking about non-coding stuff, like our after show, a couple of days ago, I was talking about gardening and you're like, is crop rotation really a thing. And you were sincerely interested. I'm like, that's actually a pretty good

[00:27:48] **Tim:** question.

[00:27:49] **Ben:** gonna, I was going to bring up, someone at work about months ago was talking about this concept of the three sisters.

[00:27:56] **Ben:** It's like

[00:27:57] **Ben:** beans plus

[00:27:59] **Ben:** yeah.

[00:27:59] **Ben:** Something. And it was fascinating about how, like, pardon me, it gives the shade. And then part of it keeps the soil moist. And

[00:28:06] **Ben:** part of it

[00:28:07] **Tim:** he's he's so curious. he's so curious.

[00:28:10] **Ben:** love that. I'm so

[00:28:11] **Ben:** fascinated that one, people figure this stuff out. It's kind of mind blowing, even though we've had, thousands and thousands of years to figure it out, it's still like just trial and error. It's amazing. Working

[00:28:21] **Ben:** for podcasts.

[00:28:23] **Carol:** Yeah in chat, we just got welcome to the working farm podcasts.

[00:28:27] **Ben:** I will say that when we decided to do this podcast and Tim was going to be part of it, I had assumed we'd be talking a lot more about spicy peppers. I don't know why. I just thought that's going to be like a really big recurring theme.

[00:28:46] **Tim:** Yes, I do grow Carolina reapers and I do make hot sauce out of it, but

[00:28:50] **Ben:** Yeah.

[00:28:51] **Tim:** it's not even hot to me anymore. So it's not worth talking about.

[00:28:55] **Adam:** Speaking of the working farm podcast. I got myself, a new truck a few years back. And, I, so I had the occasion, the opportunity to record myself driving over the hundred mile mark, which

[00:29:05] **Adam:** was, that was pretty cool. Right. So I recorded a little video of it and I sent it to my coworkers and you know what they did, they made fun of me because the podcasts that I was listening to at the time, the dude was talking about like owning a tractor.

[00:29:16] **Adam:** And what do you like? Oh yeah. But it's a woodworking podcast. Come on. These are just like? Hicks that live in the middle of nowhere and they have to talk about something right.

[00:29:26] **Ben:** So we, this is something that we had briefly touched on as an idea for a show, and then we never circled around to it. Just what other kinds of podcasts people listen to? I mean, not that this is really even appropriate for the show, but I listened to, I'd say like half tech podcasts and half NPR podcasts, but it sounds like you all have a lot more variety than I do.

[00:29:47] **Ben:** I mean, I don't listen to anything about farming.

[00:29:48] **Tim:** I don't listen to, I don't listen to any podcasts. I don't listen to ours.

[00:29:55] **Tim:** I listen to books.

[00:29:56] **Adam:** Yeah. I listened to a lot of audio books.

[00:29:57] **Adam:** too. I listened to

[00:29:58] **Adam:** about half tech and then the other half is like

[00:30:01] **Adam:** just other odd topics that I'm interested in. So I have like skydiving woodworking. I'm a little bit of a space nerd. I really liked the podcast space above us. what else has.

[00:30:10] **Carol:** And I was like, I need to open my library and see what I got

[00:30:13] **Adam:** Yeah. I mean, there's a bunch of like maker type podcasts that I listened to the role sort of off did somebody just snore.

[00:30:22] **Tim:** I got

[00:30:23] **Adam:** Okay. Sorry. I thought that was an, like a joke.

[00:30:25] **Carol:** Way to call someone out Adam. Oh,

[00:30:29] **Adam:** You're welcome. Gold.

## [00:30:33] Hot Ones Edition

[00:30:33] **Tim:** So Monte wants to know. Would you guys be interested in doing a hot one's version of the podcast episode? Hey, I'll sit. I'll send everybody hot sauce. I'm sure. Ben will

[00:30:42] **Carol:** let's do it. I would

[00:30:43] **Ben:** well, what is high ones? Is that.

[00:30:44] **Ben:** a reference.

[00:30:45] **Ben:** to something?

[00:30:46] **Carol:** Oh, hot

[00:30:47] **Tim:** Yeah,

[00:30:47] **Carol:** is the

[00:30:47] **Tim:** it's a YouTube.

[00:30:49] **Carol:** Yeah,

[00:30:50] **Carol:** Okay. Let me

[00:30:50] **Adam:** yeah,

[00:30:51] **Carol:** since

[00:30:51] **Carol:** I have this one,

[00:30:53] **Carol:** so there's this YouTube channel where basically they go on with celebrities and interview them and they

[00:30:57] **Carol:** work their way up from like the

[00:30:59] **Carol:** mildest hot

[00:31:00] **Carol:** sauce to the hottest hot sauce.

[00:31:01] **Carol:** Right. So by the end of it, they're sweating and dying and trying to figure out where bathroom is.

[00:31:11] **Ben:** I'd make it to

[00:31:12] **Ben:** mild.

[00:31:12] **Adam:** lot

[00:31:13] **Adam:** of

[00:31:13] **Tim:** Yeah.

[00:31:13] **Adam:** ones.

[00:31:13] **Carol:** Yeah.

[00:31:14] **Carol:** There's some really good interviews.

[00:31:16] **Ben:** That'd be kind of fun

[00:31:16] **Ben:** actually.

[00:31:17] **Carol:** Yeah. I would

[00:31:18] **Carol:** be game for that. Plus I love wings.

[00:31:21] **Adam:** it's a, I mean, it's a really interesting format because the hot sauce like gets into people's brains and like takes down their barriers. So they become like, they're more honest. They can't,

[00:31:30] **Adam:** they can't,

[00:31:30] **Adam:** think straight. So

[00:31:31] **Adam:** they

[00:31:31] **Adam:** can't like keep

[00:31:32] **Adam:** their guard up.

[00:31:34] **Tim:** And the host Sean Evans, is that his name?

[00:31:37] **Tim:** He is such a good interviewer. He has really, he doesn't ask to like, just throw away questions. They're very specific. He does extreme. You can tell he's done a lot of research on the person and like brings up stuff and constantly people are like, oh wow, that's a good question.

[00:31:50] **Tim:** No one has ever asked me that. So, so yeah, if you guys are down,

[00:31:55] **Tim:** I'll ship everyone, some hot sauces and we will, the,

[00:31:58] **Adam:** I mean,w you'll have to tell me where on the scale, the Carolina Reaper lands. Cause

[00:32:03] **Adam:** like

[00:32:03] **Adam:** I, right. But how does that compare to like their scale on hot ones? like

[00:32:08] **Adam:** Scovel wise.

[00:32:09] **Tim:** So that was so their last one, the last dab is

[00:32:13] **Tim:** pepper X, which is a little bit hotter than Carolina

[00:32:16] **Adam:** now is that the current season? Cause

[00:32:17] **Adam:** they, they last

[00:32:18] **Adam:** dab is

[00:32:19] **Tim:** It's last day. I is always the, yeah, the,

[00:32:21] **Tim:** last,

[00:32:21] **Adam:** multiple last.

[00:32:22] **Adam:** abs. They've got multiple like flavors and

[00:32:25] **Adam:** concoctions.

[00:32:26] **Tim:** but the flavor is the same pepper is pepper X. So yeah. So I don't have pepper

[00:32:30] **Tim:** X because you can't really, you can't buy that right

[00:32:33] **Adam:** So pepper X is actually worse than Carolina

[00:32:35] **Tim:** yeah, it'sthe same guy. I forget his name, but he has a company called pucker, but, and he,and he's the one who, he's the one who came up with the Carolina Reaper and he's also came up

[00:32:45] **Tim:** with

[00:32:45] **Ben:** Are these peppers discovered or are they cultivated?

[00:32:49] **Tim:** so you, you breed them, right? So you keep crossing things and you just get ones that are hotter and then you take that one that's hotter

[00:32:55] **Tim:** and you keep it.

[00:32:57] **Tim:** so, so so so so the folks here, those folks who are watching the live show right now are saying, that'd be awesome. So I think this has to happen.

[00:33:06] **Tim:** We'd have to record it because it's no fun to just hear

[00:33:08] **Tim:** a people.

[00:33:09] **Tim:** You got to see people

[00:33:10] **Carol:** Oh yeah. We can make a video of

[00:33:12] **Carol:** it.

[00:33:12] **Carol:** I'm

[00:33:12] **Adam:** Yeah.

[00:33:12] **Adam:** we'll do a video podcast episode or something. Let's do it. Why not? One, one week of pain from one night of recording is probably not

[00:33:21] **Tim:** Oh, yeah. Yep.

[00:33:25] **Adam:** All right. Let me,let me put it this way. So, I try not to overdo it with the, what is the hot sauce? It's the rooster sauce,

[00:33:32] **Adam:** uh, Soraya. Yes. Thank you.

[00:33:36] **Carol:** Oh, I love Serratia. It's like a S

[00:33:39] **Carol:** it's a

[00:33:39] **Carol:** sweet

[00:33:40] **Tim:** No,

[00:33:40] **Tim:** tastes, I catch

[00:33:41] **Tim:** up compared to

[00:33:43] **Carol:** Yeah. So Russia has like a sweet

[00:33:44] **Carol:** taste to me.

[00:33:46] **Tim:** but what we'll build up to it. We'll build

[00:33:48] **Tim:** up

[00:33:48] **Tim:** to

[00:33:48] **Tim:** it.

[00:33:48] **Adam:** to send us more than just Reaper.

[00:33:50] **Tim:** Oh yeah. Yeah. I'll send you. Yeah, I forgot. I have in

[00:33:52] **Tim:** Euro, I got jalapeno. I'll send you a different ones.

[00:33:55] **Adam:** Yeah. Thanks. w we'll have some, one of the Discord peoples says have some and ice cream on hand just in case.

[00:34:00] **Tim:** Yep. Too bad. I'm lactose intolerant.

[00:34:02] **Tim:** So,

[00:34:04] **Adam:** So

[00:34:05] **Tim:** but I don't need it. I put

[00:34:07] **Tim:** all my food.

[00:34:11] **Adam:** this is getting a awfully after showy. So let's start a circle back a little bit. What would you like to do differently here on the podcast? If anything.

## [00:34:18] Rants And Tangents

[00:34:18] **Ben:** here's something that I wouldn't say that this is different. This is more like an open question. Sometimes I have stuff that I want to talk about, and I just don't know when it would even be appropriate to bring up. For example, we talked about goals for this year and I'm constantly bouncing around between a couple of different things that I'd like to try to contain our eyes.

[00:34:40] **Ben:** And I think it'd be fun to talk about, fun for me at least,to talk about what I'm thinking. And I just never know. I'd love to talk about it and I never know when to bring that kind of stuff up. Cause it's not quite a triumphant

[00:34:50] **Ben:** of fail and it's not an after show really kind of.

[00:34:55] **Carol:** But those, I think those things are perfect for like our potlucks. I mean, maybe it doesn't fill up a whole

[00:35:00] **Carol:** episode, but we should probably do it more potlucks in so that we each bring in a 15 minute, like, I just want to rant about this, or I just want to talk about this.

[00:35:09] **Carol:** It's not a full episode. It's just like a few minutes.

[00:35:13] **Carol:** I know. I think we should definitely keep doing Ben's diary cause that's uh,

[00:35:19] **Carol:** but I, you know, I also, I don't want to make that just about me. I, feel like I want to know

[00:35:24] **Ben:** about your Randy.

[00:35:27] **Adam:** you're the one with the ransom and that's totally fine.

[00:35:29] **Adam:** Listen,

[00:35:30] **Adam:** have you ever watched,

[00:35:31] **Adam:** bill Nye has a Netflix show. It has lots of faults, right? I'm not like a super fan or anything, but I watched it, it was entertaining. He has a new ish show. It's probably three or four years old by this point on Netflix.

[00:35:41] **Adam:** I think it has two seasons. and I think it's like bill Nye

[00:35:44] **Adam:** saves the

[00:35:44] **Adam:** world or something like that.

[00:35:46] **Adam:** and, and, one of his little segments that he does, it's not even every episode, just maybe acouple per season. he has like a bill nine needs a minute or something and,those got this own little intro music and then he just goes off on a rant for like five minutes and he's like, okay, thanks for letting me get that off my

[00:35:58] **Adam:** chest.

[00:35:59] **Adam:** And then they go back to the show.

[00:36:00] **Carol:** That's perfect. Yeah.

[00:36:02] **Tim:** Yeah.

[00:36:02] **Adam:** We need to look a Ben

[00:36:03] **Carol:** Yeah. Ben

[00:36:04] **Carol:** needs a minute. Let's add

[00:36:05] **Ben:** I definitely need

[00:36:06] **Ben:** some minutes.

[00:36:07] **Ben:** Yeah.

[00:36:09] **Adam:** I we're going to have to let's do a potluck next week.

[00:36:11] **Carol:** I think We should

[00:36:12] **Carol:** do.

[00:36:12] **Adam:** it. It's been

[00:36:12] **Adam:** awhile. We're

[00:36:13] **Adam:** due

[00:36:14] **Carol:** Potluck. It is.

[00:36:15] **Tim:** It's he bends really good about he in our little private discord, just the four of us. He's really good about putting their little notes to self in there. And so you can go back and see them. I don't think I've

[00:36:23] **Carol:** I copied and pasted

[00:36:24] **Tim:** Carol's done a few carols on a few

[00:36:28] **Tim:** I think

[00:36:29] **Carol:** I think you know how to format desk copy and paste

[00:36:32] **Carol:** bins.

[00:36:32] **Tim:** Yeah,

[00:36:33] **Ben:** I don't know. I forget what came up in slack, in, in the Discord the other day. And I was midway through writing something. you guys were talking about tests and I was midway through writing something like expects number of tests to be zero. And I was like, all my tests passed, but I didn't,

[00:36:48] **Ben:** uh,it didn't come

[00:36:50] **Ben:** out quite

[00:36:50] **Carol:** Oh, you should have,

[00:36:52] **Carol:** that

[00:36:53] **Carol:** would be hilarious.

## [00:36:54] Monte Joins

[00:36:54] **Adam:** So, I know we have a couple people out there listening. Maybe we should, this would be a good opportunity to invite somebody to try that, like call in

[00:37:00] **Adam:** button

[00:37:01] **Carol:** Yeah. Does anyone want to join?

[00:37:02] **Tim:** Five bucks has no one

[00:37:03] **Tim:** does. They're all too

[00:37:04] **Tim:** scared.

[00:37:05] **Carol:** Come on in,

[00:37:07] **Tim:** They're all too

[00:37:07] **Tim:** scared.

[00:37:08] **Carol:** give me a dollar. If you can make Ben

[00:37:10] **Carol:** laugh really hard.

[00:37:11] **Adam:** doo doo.

[00:37:14] **Carol:** It's our goal. Every

[00:37:15] **Carol:** game.

[00:37:15] **Carol:** Oh, see the blood vessel coming out a little, a

[00:37:19] **Carol:** tiny little bit.

[00:37:22] **Tim:** oh, look at that. Monte's

[00:37:23] **Ben:** Ooh,

[00:37:23] **Adam:** let's invite

[00:37:24] **Carol:** Yeah.

[00:37:24] **Adam:** oh, here comes a monkey.

[00:37:26] **Carol:** Hey, Maddie.

[00:37:27] **Monte:** We Hi, everybody

[00:37:29] **Adam:** Hi, Monte. Welcome to the show.

[00:37:33] **Carol:** Hey, that's from the scary

[00:37:35] **Carol:** movie.

[00:37:36] **Ben:** I think it's from a bud light commercial or

[00:37:38] **Ben:** something.

[00:37:39] **Monte:** just fumble, wiser but

[00:37:40] **Ben:** Yeah.

[00:37:45] **Monte:** yeah.

[00:37:46] **Monte:** Paul went up first came up,

[00:37:49] **Monte:** I guess

[00:37:49] **Monte:** I stuck, my tongue That was so good that my coworkers actually still remember to stay.

[00:37:55] **Adam:** Wow. That's impressive.

[00:37:57] **Monte:** even asked me to, do a YouTube video

[00:38:00] **Monte:** and sent

[00:38:01] **Monte:** that to them. Let me see if I can, I believe the link is still well, Let me see if I can find

[00:38:06] **Tim:** Oh, that's

[00:38:07] **Carol:** You get the dollar, you

[00:38:08] **Carol:** may have been last,

[00:38:09] **Tim:**

[00:38:09] **Ben:** Oh Yeah. that was so popular for

[00:38:11] **Ben:** I'd say like a

[00:38:11] **Ben:** good two or three years in my social circle.

[00:38:14] **Adam:** Far too long. Yeah. This was before

[00:38:16] **Adam:** like,internet memes was like a

[00:38:18] **Adam:** culture thing. And so like, It was

[00:38:20] **Adam:** like,

[00:38:20] **Adam:** sort of, yeah, it was the first sort of meme

[00:38:24] **Adam:** I know of my consciousness anyway,

[00:38:27] **Adam:** and

[00:38:27] **Tim:** Samati

[00:38:28] **Monte:** oh,

[00:38:28] **Monte:** here you go. I found it. Let me see.

[00:38:31] **Tim:** oh, put in the show notes.

[00:38:34] **Carol:** put that thing in chat.

[00:38:35] **Ben:** Monte's triumphs this

[00:38:36] **Ben:** week.

[00:38:38] **Carol:** Yeah,

[00:38:39] **Tim:** he stuck his tongue out so far. It became a meme.

[00:38:41] **Monte:** Cool.

[00:38:42] **Monte:** Here's the link. I put them in

[00:38:43] **Monte:** the chat

[00:38:45] **Carol:** I got to watch

[00:38:45] **Carol:** it.

[00:38:49] **Adam:** that's pretty

[00:38:49] **Adam:** impressive

[00:38:51] **Adam:** That's pretty impressive.

[00:38:52] **Carol:** that's impressive. Very impressive.

[00:39:02] **Tim:** Yeah. I love to see secure in his

[00:39:06] **Ben:** So, what are these these new YouTube, these like vertical videos that I've seen is that like their

[00:39:10] **Ben:** version

[00:39:11] **Ben:** of reels.

[00:39:13] **Tim:** tick tock

[00:39:14] **Carol:** YouTube.

[00:39:15] **Adam:** YouTube. Yeah. Everybody just sees somebody at some other platform doing something different, so they

[00:39:20] **Adam:** have to copy it so that you have a reason to stay where you are.

[00:39:22] **Carol:** Yeah.

[00:39:23] **Tim:** Uh, okay, so let's back up. So Monte join Monte. Tell us, what do you think of the show? What was self-reflecting here? give us the

[00:39:30] **Tim:** good, the

[00:39:31] **Tim:** bad

[00:39:31] **Tim:** and the ugly.

[00:39:32] **Monte:**

[00:39:32] **Monte:** I

[00:39:32] **Monte:** actually

[00:39:32] **Monte:** never thought about fats. That's

[00:39:35] **Monte:** why

[00:39:35] **Monte:** I

[00:39:35] **Monte:** enjoy everything that you guys are

[00:39:37] **Carol:** Oh,

[00:39:38] **Ben:** very much.

[00:39:40] **Carol:** that's

[00:39:40] **Tim:** good that's

[00:39:41] **Carol:** we'll take it.

[00:39:41] **Monte:** Yes.

[00:39:42] **Tim:** we enjoy having you. Thank you so much for

[00:39:44] **Adam:** Absolutely

[00:39:45] **Monte:** Oh, always a great.

[00:39:48] **Adam:** Monte

[00:39:49] **Adam:** before we even had a Patreon reached out and said, do you have a Patreon I'd like to support you? So,

[00:39:53] **Adam:** I will never forget that. Thank you

[00:39:54] **Adam:** so much.

[00:39:55] **Monte:** You're always

[00:39:56] **Monte:** welcome.

[00:39:56] **Tim:** And I enjoy

[00:39:57] **Tim:** you on our game nights.

[00:39:58] **Carol:** So much. So you're a, you

[00:40:00] **Carol:** are a hoot, so it's like where the,

[00:40:01] **Carol:** which we need to have more of that can be one of our things we should do.

[00:40:04] **Carol:** Better. More involvement.

[00:40:06] **Carol:** Yeah.

[00:40:07] **Carol:** Yeah.

[00:40:08] **Tim:** More game nights. Yeah. Yeah. We played a, RPG,

[00:40:11] **Tim:** one

[00:40:12] **Tim:** shot called what about John?

[00:40:13] **Carol:** is

[00:40:13] **Carol:** John? Yeah.

[00:40:15] **Tim:** who is John? Thank you. My game. I can't remember. Monte was a multi was. Yeah, he was great.

[00:40:22] **Tim:** Trying to

[00:40:22] **Tim:** try and

[00:40:23] **Tim:** create world peace.

[00:40:25] **Ben:** What is a one

[00:40:26] **Ben:** shot What does that mean?

[00:40:28] **Tim:** So it's, you know, D and D and stuff like that. It's like a long campaign. This is a game that has

[00:40:33] **Ben:** Ah,

[00:40:33] **Tim:** rules. You can play in one.

[00:40:36] **Tim:** And sometimes even multiple times and one evening. And so, yeah. So what, who is John is basically about a guy who has different voices in his head and all the players have the voices and there's rules, how they can control him to create, an end result that they want.

[00:40:48] **Tim:** And so if they get the end result by controlling John,

[00:40:51] **Adam:** it's everyone is John.

[00:40:52] **Carol:** there

[00:40:53] **Carol:** you go.

[00:40:53] **Tim:** everyone has drawn.

[00:40:54] **Tim:** Thank

[00:40:54] **Tim:** you.

[00:40:55] **Tim:** So was fun.

[00:40:57] **Adam:** And that

[00:40:57] **Adam:** was a lot of

[00:40:57] **Adam:** fun.

[00:40:58] **Ben:** it to game night. One of these nights,

[00:41:00] **Tim:** doubt it, but, okay.

[00:41:03] **Ben:** one day, one day.

[00:41:04] **Adam:** starts after you're in bed.

[00:41:07] **Tim:** Yeah. Right. goes way too long.

[00:41:10] **Carol:** I mean you could join and just hang out and chat until you're like yawning and then just drop

[00:41:15] **Ben:** That's true.

[00:41:15] **Ben:** just be in the group.

[00:41:16] **Tim:** Yup. So where do you live, Monte?

[00:41:18] **Monte:** currently I actually am in

[00:41:20] **Monte:** Texas.

[00:41:21] **Tim:** Texas.

[00:41:22] **Monte:** Antonio,

[00:41:25] **Tim:** town.

[00:41:25] **Monte:** really hot, and there's a drought going on right now.

[00:41:30] **Ben:** A lot of people seem to be in Texas these days.

[00:41:32] **Ben:** I don't know

[00:41:33] **Ben:** if it's becoming a more popular

[00:41:35] **Adam:** I don't know if you noticed this.

[00:41:36] **Tim:** It is kind of big.

[00:41:37] **Ben:** even at work. I

[00:41:38] **Ben:** feel like every other person that I talked to who lives in Dallas or Austin or Houston, it just

[00:41:45] **Ben:** seems to

[00:41:45] **Ben:** be much more

[00:41:46] **Ben:** popular.

[00:41:47] **Carol:** didn't see. I just listened to something where they were

[00:41:49] **Carol:** talking about how the Dallas area has just grown, like by 35% or something just in the

[00:41:54] **Carol:** last year or in the last, very short amount of time. Just the whole area around Dallas and like the

[00:42:00] **Carol:** Plano, all that area is just

[00:42:03] **Carol:** Yeah.

[00:42:04] **Monte:** Yet. they said that not Dallas, but Austin. That's the capital of Texas.

[00:42:10] **Monte:** my belief was they said Austin, either Austin. or Houston there's the fastest growing city in the United States at this moment.

[00:42:18] **Adam:** Yeah. Yeah. Aston is exploding.

[00:42:21] **Monte:** I mean, he, but Elon Musk, moved the headquarters to Austin.

[00:42:26] **Tim:** Oh,

[00:42:27] **Monte:** Yeah,

[00:42:28] **Monte:** this, the space Xspace X

[00:42:30] **Monte:** this far, this Elan Musk, right. was.

[00:42:33] **Adam:** .

## [00:42:33] Patreon

[00:42:33] **Adam:** All right. So, this episode of Working Code is brought to you by mixing your Advil PM

[00:42:36] **Adam:** with caffeine and listeners like you

[00:42:38] **Adam:** if you like what we're doing here, you should consider supporting us

[00:42:40] **Adam:** on Patreon. We have a bunch of people helping us out over there, and we really appreciate you all

[00:42:45] **Adam:** special. Thanks to our top patrons,

[00:42:46] **Adam:** Monte and Peter. if you'd like to help us out, you can go to patreon.com/WorkingCodePod.

[00:42:51] **Adam:** All of our patrons get early access to an ad-free version of new episodes

[00:42:54] **Adam:** and our after show.

## [00:42:56] Thanks For Listening

[00:42:56] **Adam:** and you know what you should do right now. You should

[00:42:57] **Adam:** go leave us a review on apple podcasts. How else is

[00:43:00] **Adam:** apple gonna know

[00:43:01] **Adam:** that they should be recommending us to other people who listened to the same shows

[00:43:04] **Adam:** that

[00:43:04] **Adam:** you do? So head on over to workingcode.dev/review and get her done. So that's going to be it for us this week. We'll catch you next week. And until then,

[00:43:12] **Tim:** you know, and when you really self-reflect on it,

[00:43:15] **Tim:** and you think about your life. Your goals, what do you want to do? Who you are, who you love?

[00:43:22] **Adam:** this is.

[00:43:25] **Tim:** it's true. It's so true. Your heart matters kisses.
