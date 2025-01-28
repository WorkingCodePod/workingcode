---
title: "069: Now I'm Catching Events"
description: "Carol talks to us about how her Support team manages communication with their customers."
date: 2022-04-06
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/069-now-im-catching-events/id1544142288?i=1000556410726"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week, Carol talks to us about how her Support team manages communication with their customers. And, how she'd love to find an easy way for one Support engineer to know that _another Support engineer_ is currently working on a given ticket. She's been exploring the use of WebSockets and "presence channels" as a means to provide feedback within the Support platform. And, more generally, she's been looking into the concept of Publish and Subscribe (often referred to as Pub/Sub) as a means to push information from one service to another. We talk a lot about [Pusher][pusher] - a fully-managed WebSocket SaaS offering; and, consider other techniques that might be helpful.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[pusher]: https://pusher.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/069-now-im-catching-events.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Tim:** the analogy is like, you know, for boomers and gen X, newspapers magazines, for, younger ones that like, like a subscription to a loot box or something like So yeah, you have a person that has publishing things right there. They're sending you magazines. They're sending you newspapers as in you, you know, swag things and, you as a person can subscribe to that for a period of time.

## [00:00:41] Intro

[00:00:41] **Adam:** Okay. Here we go. It is show number 69 and on today's show, we're going to be talking about pubsub catching and throwing events. and as usual, we're going to start with our triumphs and fails, but first I have a birthday coming up. I'm going to be 40 a after this airs and oh, it starts already.

[00:01:01] **Adam:** And, I have an issue I'd like to raise since I'm officially going to be old. I'd like to take this opportunity to have my very first old man. I have two children and they are 11 and 13 and as 11 and 13 year olds, do they spend the vast majority of their free time watching other people play Minecraft on YouTube.

[00:01:22] **Tim:** right

[00:01:23] **Adam:** most of these people playing Minecraft on YouTube, or I would guess between the ages of like 16 and 30, maybe a little bit less than 30, like 20, 25. And there's obvious there's just this common thread. Anytime the number 69 comes up in the game,I have a stack of 69 wool or whatever it is they have to say nice.

[00:01:45] **Adam:** And it drives me nuts because it's like, you are making content specifically for children. You're making children's content and you're making innuendo jokes. It gets under my skin.

[00:01:59] **Tim:** I get it. I think I mentioned this on the show before, but I told the kids about the back in the old, old days when you had landlines and no caller ID, if you wanted to see who called you, you dog star 69.

[00:02:11] **Carol:** Yeah

[00:02:12] **Tim:** they're nice.

[00:02:14] **Carol:** Nice.

[00:02:15] **Tim:** And I, I think I said, there's two that they said, what happens?

[00:02:18] **Tim:** Would you dial a star for 20? Does your weed guys show up?

[00:02:24] **Adam:** your kids are a little older though. They get

[00:02:26] **Adam:** it

[00:02:26] **Tim:** 16 and 18.

[00:02:28] **Adam:** Yeah. So it just, it's a pet peeve of mine. So old man over I'm done with my rant. Thank you.

[00:02:34] **Carol:** Or

[00:02:34] **Carol:** it's just starting.

[00:02:35] **Tim:** welcome to the club.

[00:02:36] **Adam:** first, of many, thank you for allowing that. So now as usual, let's start with our triumphs and fails and, Tim, you're your first.

## [00:02:44] Tim's Triumph

[00:02:44] **Tim:** Yeah, I'm going with the tribe. I'm off all this week. It's spring break for my kids. We don't really have any plans. It's just actually, it's just been really nice, not being at the computer all day long, you know, realize just how kind of burnt out. It was just sitting here in this, this exact same chair that I'm at right now, every single day, day in, day out.

[00:03:04] **Tim:** And I've been outside and just getting my vegetable garden ready and planting tons of stuff and just playing in the dirt and it's, weather's great. And yeah, I'm loving it. I just, I feel, I feel energized. I'm actually, I think I'm ready to go back to work at the end of this week. So

[00:03:19] **Adam:** Nice.

[00:03:21] **Ben:** I

[00:03:22] **Ben:** Ihave a question about gardening So I know with farmers they have to rotate their crops to keep the soil healthy Is that something that gardeners have to worry about or fertilizer

[00:03:32] **Tim:** no, not on a small, not on a small scale. I got to just. I mean, it's a pretty good size garden, but it's like every year I just kind of add to the soil. So, I mean, if you're doing huge, like acres Mon of monocrop. Yeah. That that's a problem, but it's like, yeah, if you're just, you got like 10, 15 rows crop rotations, not a big deal.

[00:03:53] **Adam:** thought about that too We have a garden and my wife tends to plant the tomatoes in the same spot and the cucumbers in the same spot So I guess if you're adding top soil that

[00:04:02] **Tim:** yeah, every single year I buy big bags of composted cow manure in like soil conditioner, just till it in. So it's basically different soil every time. So

[00:04:12] **Carol:** you're getting fresh.

[00:04:14] **Tim:** yeah, but that's me Carol. How about you

## [00:04:17] Carol's Triumphs

[00:04:17] **Carol:** Man, I'm going with a triumph. I got a couple

[00:04:20] **Carol:** actually. I got engaged this weekend,

[00:04:24] **Adam:** Yeah

[00:04:24] **Adam:** he

[00:04:24] **Adam:** did

[00:04:28] **Carol:** Yeah. Steve asked me to marry him and I said, um, yeah, sure. I guess I can. So woo.

[00:04:35] **Ben:** Congratulations

[00:04:36] **Adam:** smile on her face right now

[00:04:38] **Tim:** she's

[00:04:38] **Adam:** like ear

[00:04:39] **Adam:** to ear

[00:04:40] **Carol:** it's been like this since the day of, so, and the day of the morning that he proposed, I also signed a promotion at work. So I am now the manager of engineering. So manager of engineering and got engaged and he took my stitches out of my foot. So yes. Things are just great.

[00:04:59] **Tim:** your fiance or your boss?

[00:05:01] **Carol:** no, no, no,

[00:05:03] **Carol:** Steve

[00:05:03] **Carol:** Oh, the stitches came out the promotion then.

[00:05:07] **Adam:** So when you took him out he was your boyfriend

[00:05:08] **Carol:** Yeah. He was still the boyfriend Yeah.

[00:05:11] **Tim:** Order operations.

[00:05:12] **Carol:** It is crazy. I keep like, forgetting to say fiance and I pick up my phone. I'm like call my boyfriend. I'm like, oh, I should probably change that to fiance now. Huh?

[00:05:22] **Carol:** So

[00:05:23] **Carol:** yet Not yet

[00:05:26] **Carol:** It'll get there.

[00:05:27] **Carol:** I'm sure. At some point. So I'm just super excited. Yay.

[00:05:30] **Tim:** I'm excited for you. I mean, I'll be honest. I've known you a long time. I honestly never thought this day

[00:05:34] **Tim:** would come

[00:05:36] **Carol:** he, he called both of my boys and that's what the oldest said. The oldest is like, there's no possible way she was ever getting married. So you're the only person that's ever had a chance. So congratulations. You should have done it already.

[00:05:49] **Tim:** wow.

[00:05:50] **Ben:** That's nice

[00:05:50] **Carol:** Yeah

[00:05:51] **Adam:** classy move

[00:05:52] **Carol:** Yeah. Called and got the voice permission. Then call my mom, then call my best friends. Then ask me

[00:05:58] **Tim:** You didn't call me.

[00:05:59] **Carol:** and sorry, you guys, you can yell at him

[00:06:02] **Adam:** We're not best friends

[00:06:03] **Adam:** Apparently

[00:06:05] **Carol:** Yeah, that's me.

[00:06:06] **Adam:** that's a heck of a way to find out you're not somebody's best friend

[00:06:09] **Carol:** know, right. Sorry. I love guys though.

[00:06:14] **Tim:** Congratulations. So

[00:06:14] **Adam:** Yeah Congratulations

[00:06:17] **Carol:** All right. What about you, Ben? What you got

## [00:06:19] Ben's Triumph

[00:06:19] **Ben:** triumph

[00:06:21] **Ben:** No no this'll be a pale in comparison but I'm going with a triumph which is that I did a presentation at work and call it presentation is very liberal It was five minutes of screen time in the midst of a much much larger presentation but it sometimes it feels like no matter how long the presentation is the stress of preparing for it especially as an introvert feels just massive but I did it it was basically a little brief history about my Path at Invision and how I see the company and what my experience has been like and and where I am now And I think it went really well And I got a lot of really positive feedback And I was so mentally drained though when I was done I finished that meeting was at like one 30 I think I put in another hour of work And then I had to take the rest of the day off It's just the five minutes of screen time was so exhausting but I feel really good that I did it so

[00:07:14] **Adam:** was it the screen time that was exhausting or was it the six hours of worrying prior to the five minutes That

[00:07:19] **Ben:** well So it's funny So meeting was 12 to one 30 and I had penciled some a time in at like 10 o'clock to do a little bit of rehearsal And so I have five minutes of time allocated and at like seven 30 that morning or eight 30 that morning I was like Let me put a little time in now just to ease the nerves And I ran through it the first time and it was like 22 minutes long

[00:07:43] **Carol:** Oh,

[00:07:43] **Ben:** was like okay I was like okay I got four hours this down to five minutes so there was a lot of slicing and dicing And actually I have to say this was really interesting having to pare it down from the 22 minutes to five minutes I got rid of a lot of stuff that probably could have been construed as negative like me complaining or talking about how certain things were hard or I don't know just some things that may have rubbed a few people the wrong way not everybody but a few people the wrong way and having to get it down to five minutes I basically got rid of everything that felt unnecessary And a lot of the a lot of the grumpy stuff was unnecessary and I pared it down to really just the essence of Of my experience And and it came out sounding I think just a lot more professional which was nice So having a pair down that sort of saved myself from myself yeah Feel really good about it That's me triumph

[00:08:36] **Adam:** Well

[00:08:36] **Adam:** I said well done I meant nice

[00:08:40] **Ben:** What about you Adam Take us home

## [00:08:42] Adam's Triumph

[00:08:42] **Adam:** I'm going to make it for buddy I also have a triumph to share a totally unrelated to work well Okay It's tenuously related to work so we talked recently about I did my I had my 10 year anniversary I got a nice little bonus from that yes Nice And I was specifically given instruction with that bonus that I was not to just put it in the bank that I had to do something extremely frivolous with it And I had a couple of ideas here

[00:09:05] **Tim:** it gets my money. Get, tell me what to do.

[00:09:08] **Adam:** but I had some ideas here and there I have no shortage of expensive hobbies so it was not difficult to find a place to allocate the money but where I eventually landed my father-in-law has been a longtime woodworker and the he this weekend they came up to visit

[00:09:24] **Adam:** I'm trying just

[00:09:25] **Carol:** That was so good.

[00:09:26] **Adam:** and And he came up and he let me borrow his leg He just has a little it's like entry-level Harbor freight bench-top lave

[00:09:33] **Adam:** It's nothing

[00:09:34] **Adam:** special Elaine is you make round things with it So it's a motor and it spins your piece of wood then

[00:09:39] **Ben:** table leg that kind of thing

[00:09:41] **Adam:** yeah a table leg a baseball bat you can do like bowls and stuff this is going to be a difficult show so he let me borrow his leg and I had way more fun with it than I thought like it turned out to be so much easier than I was expecting I had this image intimidation factor that I I was just expecting it to be difficult And I didn't I wasn't really looking for a challenge and it can be kind of an expensive hobby a little bit It like it isn't there's so here's the thing This is what's exciting to me about it is not only can you by the late but like now there's this whole other list of accessories that you can spend

[00:10:11] **Adam:** all kinds of

[00:10:12] **Adam:** money on Right The shopping that's the fun part for me so yeah I'm just I'm I've already guess is the right word I've already turned my first bowl and been playing with all kinds of fun stuff So I'm great time

[00:10:25] **Ben:** very cool I remember nice

[00:10:29] **Ben:** remember working with a hardware customer years and years ago And they were talking about how specialized tooling is And he brought up lays as an example and he said that there's a special kind of bolt or something that keeps the wood from spinning off And like there's like at each end there's a special kind of bolt that keeps it in place And he says there were companies that specialize in just making that bolt And I don't know

[00:10:54] **Ben:** blew my mind

[00:10:54] **Ben:** random aside

[00:10:56] **Adam:** Nice I'm trying to make it real old real fast So everybody just hates it

## [00:11:01] Audible

[00:11:01] **Tim:** Timmy here. I hope you're enjoying the podcast. You know, we put a lot of work into it. It really is a labor of love. There are costs. However, and if you'd like to help us out, one low friction auction is to sign up for a free trial of audible. All of us at WorkingCodePod, listen to audible every day. So it's something we believe in.

[00:11:21] **Tim:** I personally have over 500 titles, most are fiction, some coding and other non-fiction titles. I'm sure if you don't already have audible, you'll find some great titles to listen to. Long story short, if you'd like to help us out to cover the cost of the show, sign up at workingcode.dev/audible. That's workingcode.dev/audible.

[00:11:43] **Tim:** And thanks and remember your heart map.

## [00:11:46] What Is PubSub?

[00:11:46] **Adam:** Anyway let's talk about

[00:11:50] **Tim:** Well, yes, Adam, why don't you explain to us what pops up is.

[00:11:54] **Adam:** I mean I guess at its simplest form the way that I understand it is broadcasting events and receiving events In I guess you could technically do it in process right If you have a monolithic application you don't have to do something out of process to for it to qualify as pubsub But I think that it tends to lend itself well to uses that incorporate multiple technologies or multiple services integrating external satellite type services sort of thing So you broadcast an event and maybe you're broadcasting I made a sale somebody who has checked out and so there might be something that logs it and it might be something that charges their credit card something that sends a welcome emails something that you know and all these things are just listening for the I made a sale event but the thing that that records that event that broadcasts it has no concept of what's listening on the other end It's just I made a sale and here are the details and I don't care what you do

[00:12:48] **Adam:** with it

[00:12:49] **Carol:** And those

[00:12:49] **Carol:** subscribers.

[00:12:50] **Tim:** the analogy is like, you know, for boomers and gen X, newspapers magazines, for, younger ones that like, like a subscription to a loot box or something like So yeah, you have a person that has publishing things right there. They're sending you magazines. They're sending you newspapers as in you, you know, swag things and, you as a person can subscribe to that for a period of time.

[00:13:13] **Tim:** And so anytime they publish something, if you're subscribed to it, you're going to get a notification. You're going to get the magazine. You're going to get the loot box, whatever. if you choose to stop that, then you no longer get it. So that's, that's sort of the, the analogy of it.

[00:13:27] **Ben:** Well I think a lot of people I would venture to say that most people who listen to this podcast have actually used pubsub on the low down and don't even realize it And that's because the browser dumb event bindings are all pubs up in that Everybody who runs JavaScript on the page combined to say the document on click or the document loaded event and then something somewhere triggers that event And now all these callbacks get invoked and that's basically published and subscribed except to Adam's point that's happening in process Right It's all in the one JavaScript and a document object model But you can have pub sub work across multiple systems as well

## [00:14:10] Carol's Dive Into PubSub And Pusher

[00:14:10] **Carol:** So I've been challenged at work to come up with a solution for communication between our systems. So these are end users, in one system, communicating with our customer support team. So if you think of like chats, but not immediate response, we want the end user to send the message and then our customer servicing to get notification of that message and have the ability to respond to it.

[00:14:39] **Carol:** But then we don't want to have anyone stepping on anyone else's toes. So once they're in, like looking at the message, we don't want the message to show as available for work. In a in process kind of state. So anyways, that's kind of the goal. So I was looking at pusher and socket IO. The drawback with pusher was, I'm not really for sure how their connections work and the tier I was looking at buying only allows 500 open connections at a time.

[00:15:08] **Carol:** And we have like 10,000 users. So I didn't really think that, 500 open connections would be enough unless it's 500 open connections per channel. And does each channel exists? Like I didn't understand all that. So I just kind of took a step back and we actually are going to go with a whole nother route, but.

[00:15:26] **Carol:** Make me go, okay. How does this work? Like how do pub subs work? Like how do you pee? Like I know saying how the public understand how the subscribe, but then the connection between the channels. That's where I get a little lost as far as what's considered like a connection and how many channels do you have open and then the private versus public, and then the idea of the presence.

[00:15:47] **Carol:** So for what I was trying, which I may still need to use something for this, for the present side of it. So when the user opens up that message, I want it to show and progress for all the other users. So no one else picks it up and if they don't do anything with it, then I want it to show back in the work queue as, okay.

[00:16:05] **Carol:** Someone needs to go look at this message. And I think that the presence feature and pusher would be an option for that. I shouldn't really know yet. I still got to go learn more. So hopefully you guys can open up my eyes a little bit here.

[00:16:20] **Ben:** there's a lot to impact there

[00:16:21] **Ben:** I can tell you that I have a lot of hands-on experience with pusher That's what we use on the legacy platform it essentially just for other people's benefit here pusher is a completely managed web socket service The web socket system doesn't exist on your servers at all whatsoever So the browser will connect directly to pushers web sockets And then we communicate with the browser from the server by making API calls from our backend servers through their rest API and then they propagated down through their web sockets so th so right off the bat the really nice thing there is you just don't have to worry about any of the infrastructure related concerns And you also don't have to worry about what happens if a user gets disconnected from a web socket or the server that was serving up a WebSocket crashes or is being deployed So it gets taken out of rotation and then a new server gets put into rotation You don't have to worry about all of That handshaking and rig and roll about making sure people are connected to the right things So that's been very helpful The costs that you're talking about the open connections Yeah That's you can think of connections basically like a browser instance and it's expensive in that There's basically two two levers that they can pull for their pricing There's the concurrent connections and the number of messages The messages is much much cheaper You can send like millions of messages a day for very little

[00:17:50] **Carol:** Oh yeah. I was like, think our messages are easy. Like that. Wasn't what

[00:17:54] **Carol:** I was worried

[00:17:54] **Carol:** about. This.

[00:17:55] **Ben:** We're to be completely honest we're like on a seventh level custom enterprise plan with them because kept running into the connections

[00:18:04] **Carol:** Yeah, because if you run out of connections, it just doesn't allow anymore. It's not like, oh, we're going to roll up and charge you. It just, nobody can get on until connections are open. I was like, well, that's not a good solution for us.

[00:18:16] **Ben:** Yeah I don't know what the exact cost is but our pusher bill is definitely in the thousands per month

[00:18:22] **Carol:** Yeah.

## [00:18:24] PubSub Vs Message Queuing

[00:18:24] **Tim:** Can I ask you why the choice for pubs versus message queuing?

[00:18:28] **Carol:** I just looked up a few things and pub sub seemed fun and I wanted to learn something new. And when it's something that would update the interface easy. So I didn't have to add anything. And pretty much, like I could just add the script to it whenever the subscription here, like, I guess it's here is that the right way to say that?

[00:18:46] **Carol:** So when the subscription like reads the event, it just automatically updates the page for me with very little changes needed.

[00:18:53] **Tim:** So does, does the component that you're sending the message, does it know where the destination is typically or is it kind of unaware of who all out there is using it?

[00:19:06] **Carol:** It would be an, a, well, okay. It would know that it's going to a certain system, so we would know what two systems are communicating and you would be authorized if I looked at everything I was reading was right. Basically we authorized to the channel from the server itself. I think so. I mean, I think it would know where it's going.

[00:19:24] **Carol:** I don't think it would go out into like an empty space and then have to figure out.

[00:19:29] **Tim:** cause that's the big, I mean, that's the biggest difference between a pub sub model versus a message queuing. So if, if you know where the destination is, you can just queue the message up and then that message will eventually wind up going to where it needs to go. And, you know, if it doesn't receive a response that it expects it, you know, it's out, it can rescind.

[00:19:53] **Tim:** Rikyu the message. So w w with, with pubsub my mental model of it is that you know, people subscribe to a message or to a, to an event, and you don't really know who those people are, you that you're ignorant of that. So you just push it out and say, Hey, this happened and everyone who subscribed to it, you know, takes action.

[00:20:15] **Adam:** Yeah and there can be multiple consumers and you may not even know what they all are starting now Like you could decide to add them

[00:20:23] **Tim:** Yeah. So my brain is saying you might want to step back and say, you know, maybe maybe message queuing might be better solution than just, in pubsub.

[00:20:34] **Carol:** Yeah, the solution we're doing right now is actually just going to be writing it because we don't need to do any notification through email or texts or anything. So we're just literally going to write the message to a table and then read it from the other application because they have access to each other already.

[00:20:49] **Carol:** They're both ColdFusion servers. They're actually on the same box, just, they are served up different for whatever user you're on. So they already have connections to each other.

## [00:20:58] Presence

[00:20:58] **Carol:** So we're just going to write, read, and then I just need something to handle the present so that we don't have people stepping on each other's toes.

[00:21:06] **Carol:** And that was the place where I was looking at pusher again, was for the presence feature inside their channels. Just to know if someone was in there looking at it to then update it back to like in progress on the fly without any refreshing.

[00:21:21] **Adam:** So if your primary goal is awareness of who else is like on the same page basically I did something like that in our product with a very simple database polling So basically like while you're on the page it's just every there's a timer runs and every 10 seconds or something it says I'm here on this page And when the page loads JavaScript says okay this is the URL And it makes that Ajax request every 10 seconds And then the response that it gets back from that is the list of everybody else that's currently on that page and then it updates the UI of who's still there from that And what happens is so let's say the timer runs every 10 seconds after 15 seconds If you haven't checked in again Then the next time that somebody does a read for that that that page see who's there you're you'll be deleted So we do like a cleanup pass and then select who's still on the page and in their response And that is a very simple and lightweight

[00:22:14] **Carol:** That's not bad. Yeah, because the view we're thinking of is a queue. So it's going to be like a queue of messages that need responses to them. And it would be so when any customer service member is in that queue, looking at what messages they need to reply to, they don't pick up one that another customer service user has open on their side.

[00:22:33] **Carol:** So it would just be slightly different. But using, I think what you're, I think what you're saying.

[00:22:38] **Adam:** Yeah I mean what about an initial step where so if there's a message that needs to be like even something as simple as like a support ticket right So to prevent multiple support representatives from responding to the same If before you can even respond to the ticket you have to like claim it as yours Then if somebody else claims it like if you claim it and then I two seconds later try to claim it It'll tell me okay Carol already has this one and it won't let me take it

[00:23:03] **Carol:** Yeah, there would be an option too.

[00:23:05] **Tim:** I mean, couldn't you do that with callbacks rather than setting up some sort of pubsub or queuing. So basically to, to claim once you claim it, that that sends sort of, a message out to change the, the status of it so that it's no one else can get it.

[00:23:19] **Carol:** I would just need to make sure that the cue update, like that view updated for all the users in that case.

[00:23:25] **Ben:** Yeah the nice thing about the web socket connection between the browser and backend server is just that the browser doesn't have to sit there and pull for it that the event will just be pushed to it when it happens

[00:23:36] **Carol:** Yeah. That's what I was liking. It seemed really clean.

[00:23:40] **Adam:** And I think in that type of a situation the extra niceties of something like pusher where it's dealing with deploys and what if the server crashes and that sort of thing are less of a concern because if the server crashes or if you're doing a deploy then it's less important that connection survives that event So you could do something simple built in like a very basic socket IO or whatever your app server has built in for web sockets useful there I feel like we're spending this our topic is pub stuff and we're spending so far like almost the entire time trying to talk you out of pubsub

[00:24:15] **Carol:** Oh, no, it was wanting to know more about it because it was okay. The way we work right now is we have cycle work and you get put on a project like, Hey, we're trying to accomplish this. There's no guidelines. There's no, you have to do it this way. There's no, like, there's literally no information other than here's the problem that business is trying to solve.

[00:24:37] **Carol:** Take it away. Come back in like two weeks and give us an idea of how you think you can solve this problem. If they have thoughts, they'll put them in little bullet points like, oh, well maybe consider this or consider something. Like they asked me to consider using front. And I was like, okay, I'll consider front because we have a contract with them already.

[00:24:55] **Carol:** But this does mean nothing. I literally would have to send to front API, tell them to save a message, send a message back when we're just going to store the message ourselves. Like we want to be the source of truth for the data. So I don't want to go push it to front, to just create a view of messages.

[00:25:11] **Carol:** Like this was silly. So I did the initial. Okay. It's not front. So then I was like, okay, well what can I do? And I went down the route of writing data. I went to the pub sub, so it was just fun to get to learn. But then I just had more questions. Like would this be used for, not for this case?

[00:25:27] **Adam:** I totally know exactly what you're talking about This isn't for me at all but for those who might not know what front is can you give a little explanation

[00:25:36] **Carol:** Oh, yeah, I'm sorry. Front is, pretty much like a data aggregate. So it allows our users to see like all of the emails coming in to our customer service box and it gives them the ability to create things in conversations. they can respond to stuff like we have views over every communication going on.

[00:25:54] **Carol:** We can run reports on it. It's just a front to a data, so it can do your voicemails. It can do your text messages. They can do your, Facebook messages. It can do WhatsApp, like all kinds of

[00:26:06] **Adam:** it's like team communication collaboration type

[00:26:09] **Carol:** Yeah. It just puts it all in one spot. So the business thought that we should just use front to do the messaging when it made no sense because front cancer, our data, we have to be the source of truth for it, or like our Google bot has to be

[00:26:23] **Adam:** sure The listeners that didn't know what that meant appreciate that So on their behalf I will Thank you

[00:26:30] **Carol:** Hey

[00:26:30] **Carol:** there. Welcome and sorry. Yeah.

## [00:26:32] AWS Options

[00:26:32] **Tim:** So are you building this on Amazon as well? Is this all part of the Amazon thing you were working on too? Is this.

[00:26:38] **Carol:** So we were, so me and another engineer are working on this project and we were gonna put it up on AWS as just like a TypeScript project. We hadn't really went far with it yet. And that's when we backed back out and realized that leaving it in our ColdFusion project actually makes sense for what we're trying to accomplish.

[00:26:56] **Carol:** There, wasn't a reason to break out a separate application yet because it's not going to be communicating with anything outside of the legacy platform that already exists and it's not going to be moved over. So there was a reason to add extra complexity to a process is not really that difficult. If you think about it, it's literally just writing a message.

[00:27:15] **Carol:** Telling someone to go look at the message and allowing replies now that's it. So it didn't make sense to, to build it out into a big, bigger project, but it was fun to research and figure out could go that route.

[00:27:27] **Adam:** yeah And with 10,000 users you do have some considerations you need to think about for whatever solution you come up with

[00:27:34] **Carol:** Yeah,

[00:27:34] **Tim:** Reason I asked, cause you know, our friend of the show, Brian class, he, he has several articles from not too long ago, 2019 about, ColdFusion and using, SNS from Amazon

[00:27:48] **Carol:** yeah.

[00:27:49] **Tim:** to do pubsub.

[00:27:50] **Tim:** So

[00:27:51] **Tim:** have you have you maybe take a look at that?

[00:27:53] **Carol:** We did that with the last project that I use, actually we use, so we had the Lambda that pushes out to the natural language processor and then it sends over to a message queue and it does the notification. And then we just do a web hook backend for relaying to ColdFusion.

[00:28:09] **Ben:** Yeah it sounds like the hardest part is that last mile between the boundary between the server and the client that at some point you can use all this fancy backend infrastructure but at the end of the day something has to tell the browser that something happened And then that's a little bit more like

## [00:28:26] Managed PubSub Options

[00:28:26] **Carol:** And that's where I was like, Ooh, push her so sexy for this. Right. Like it just works. It doesn't require a lot of, changing. Like it, it just plug in it. I kind of it's just plug and play with what I was doing. Like, it didn't require a ton of effort to change things. So this was like, Ooh, push her was like, I don't know what the connections of they'll go for that or not.

[00:28:45] **Carol:** So then we did look at socket IO and I was just worried about like what Ben was saying. Cause we're going to have to manage all of those connections. And I think there is like a server engine for it that could do it. I just, again, We would have to learn all of it. So.

[00:29:01] **Ben:** I can tell you that at work there is a team that I don't know if socket IO is the technology they use but they were managing their own web sockets And essentially they may have solved this problem but for a long time of there was a huge period during the day that they weren't supposed to deploy have disconnected all the users and application at the time depended really heavily on the fact that the web server sockets worked and getting disconnected Everybody would like their whole system was sort of just freeze up so there there was a it is a big challenge if you're deploying those boxes

[00:29:35] **Adam:** an I'd that's

[00:29:36] **Carol:** the time.

[00:29:38] **Ben:** we've been using pusher I dunno pro probably close to a decade now and at the time we were comparing it we were we're coming down to a decision between pusher and another company called PubNub And I'm not even sure if PubNub still exist I think they they got really huge in the game community and at the time The thing that sold us on pusher was they had much more of a security mindset at least compared to PubNub circuit 10 years ago a lot of the companies that I've seen their security is really a security through obscurity where they're saying use a UID ID for the channel name so that no one else knows that they can subscribe to it and pusher they actually have a first like a first-class citizen security model where you can actually the browser client their pusher JavaScript client will make a request back to your server to get us a token generated using your private key and then they'll have to and then the client passes that through with the subscription to the channel So you essentially your application has to authorize every user's connection to a private channel it's specifically for private channels but that was what put us over the edge with pusher we appreciated that security was actually a thing baked into the platform itself

[00:30:46] **Carol:** that's what I liked when I was looking at it, because we do have a piece of our application. That's open to the public. So a user can come in and not know their login and just submit a request. So they would be able to submit with some generic information like our customers do it. They're like we don't want to log in, but here's the request for this.

[00:31:04] **Carol:** So we would need to be able to authenticate and prevent any, I guess, bad actors.

[00:31:10] **Ben:** and the nice thing too and I'm just going off the top of my head here I they have three different types of channels I believe there's like a fully open public channel that doesn't have security then by convention any channel that starts with private dash as a private channel and goes through the authentication workflow And then I think there's like a presence dash workflow That's specifically for the present stuff you're talking about Like this many people are looking at this channel right now kind of

[00:31:39] **Adam:** like presence

[00:31:41] **Carol:** you presents are

[00:31:42] **Adam:** coming up

[00:31:44] **Carol:** Yeah. The presence was a fun one to kind of play around with and learn, so

## [00:31:49] Redis For PubSub

[00:31:49] **Adam:** So I was Googling a little bit about what's it called pusher and ColdFusion And I found a bunch of these blog posts by this guy Ben Naval

[00:31:56] **Carol:** From like 20 10,

[00:31:58] **Adam:** yeah they're really old but I was wondering if you guys know him or

[00:32:03] **Ben:** W what's great is like that stuff is relatively unchanged I went to use pusher again the other day and it just an experiment and the codes exactly the same more or less other than I think when I first wrote that it's all tags and now all script

[00:32:16] **Adam:** yeah actually I did have a question for you and not at all because I haven't read them because as we know as your best friend have read everything you've ever written on your blog and have perfect recall of it all but you know for the people who haven't read your blog of the reasons I haven't done more with pubsub personally I have a great fondness for Reddis and I wish that I could use pubsub and Reddis cause we have our own Reddis instance that we use for a lot of things And it's probably my favorite piece of our stack but one of the reasons that I haven't used it specifically with pubsub for ourselves is because we are the majority of our legacy application is still CFML and there there used to be really great support for like it wasn't API gateway was it was it just gateways

[00:33:02] **Adam:** you know talking

[00:33:03] **Adam:** I think gateways Yes Thank you And I feel like that would have been a good use case for them to have the messages sent to you as an event and the event gateway I'm curious if it wasn't if not just for pusher or I guess maybe through pusher is it just calling web hooks for you or how is that broadcasting events into your ColdFusion app or does it only client side

[00:33:26] **Ben:** So yeahI maybe I should clarify there My experience with pusher is purely from a pushing from the server through the pusher API to the browser I believe they have SDKs for having server side technology actually subscribed to web sockets I just have never had a that's never been a use case for us personally but I th I'm pretty sure that exists 'cause I mean anything that can connect to a web socket shouldn't be able to leverage it but I've never to a web socket from a server before

[00:34:02] **Adam:** And I mean it's built on top of Java So in theory anything that has the job as SDK should be Quote unquote possible But as as I think I've mentioned a few times with other topics I have never quite managed to get the rain dance and the voodoo doll incantation stuff just right To get the more complex Java libraries to actually work with

[00:34:24] **Ben:** Well and speaking of Reddis so I've I have a love affair with Reddis but I use it for so little but I want to use it for so much

[00:34:32] **Ben:** more

[00:34:32] **Ben:** Uhand yeah and one of the things that it has that they make really apparently dead easy is pub sub The problem is in order to leverage it from ColdFusion at least with the Jedis library which is the primary Java driver for Uh to use their pub sub you actually have to extend one of their Java classes And I'm at a loss of how to do that in ColdFusion I've tried so many times like I've even tried to build compile like a little Java class that extends it and then I can instantiate that Java class but I don't know anything about Java or compiling Java and that's so it's I'm sure for anyone who actually was good at Java it would be very trivial to build a class that extends it and then make that available to ColdFusion But for someone like me who's not familiar with ColdFusion That's like climbing Mount Everest It feels like but I so badly want to use Reddis for publicity if for no other reason just to know how it works

[00:35:30] **Adam:** I love love love working with redness It's so fast and so simple and yeah it's just amazing

[00:35:36] **Adam:** I do I been, was talking. It made me wonder because there's been several recent updates to Lucy's Reddis drivers and I don't know there's one called Yamaha. they have where they're adding pumps up to it, to the

[00:35:55] **Ben:** Oh interesting

[00:35:56] **Carol:** Hm.

[00:35:57] **Tim:** So

[00:35:57] **Tim:** I'll put

[00:35:58] **Ben:** made curious

[00:35:59] **Tim:** I'll put it in our little chat here, so you can take a look at that.

[00:36:02] **Tim:** I mean, I mean, it was just a simple Google. I don't, it may be nothing, but.

[00:36:06] **Ben:** I'll take a look

[00:36:08] **Tim:** Cause I, I did notice the other day when I logged in my server, I'm like, oh, there's a redness update and some

[00:36:13] **Ben:** I'm ride or die with ColdFusion I love it but this is one of those moments where I can hear it In the back of my head being like if it was just JavaScript it would be a lot

[00:36:23] **Ben:** Like you would just instantiate an object and it would just work

[00:36:27] **Carol:** Yeah.

[00:36:28] **Adam:** Yeah I mean that is my job in life is to remind everybody how JavaScript

[00:36:33] **Adam:** be bad

[00:36:35] **Tim:** JavaScript everywhere.

[00:36:37] **Ben:** I do love JavaScript So I'm a man who loves many things And by many things I mean two things JavaScript and cultivation

[00:36:45] **Adam:** not talking to people

[00:36:47] **Ben:** Sometimes I love that Most of all

[00:36:50] **Tim:** you're in, you're in your dog.

[00:36:51] **Carol:** going to

[00:36:51] **Carol:** say Lucy.

[00:36:52]

[00:36:52] **Adam:**

## [00:36:52] Patreon

[00:36:52] **Adam:** So this episode of Working Code is brought to you by 18 to 25 year old kids on YouTube playing Minecraft saying nice and listeners like If you're like we're doing here you should consider supporting us on Patreon we have a bunch of people helping us out over there and we appreciate you all special Thanks of course to our top patrons Monte and Peter if you'd like to help us out you can go to patreon.com/WorkingCodePod All of our patrons get early access to an ad-free version of new episodes and our after show

## [00:37:22] Thanks For Listening!

[00:37:22] **Adam:** And here let me ask you guys this was the last time you searched a podcast directory for something new to listen to that's right You never have because you're a normal human being you're probably listening to us right now because of a recommendation someone made to you So you owe it to that person to pay the favor forward and recommend us to at least two of your friends and colleagues and Jeff Bezos will mail you a hundred Wait that's a spam I'm sending out after this anyway share the show with your friends They'll Thank you We'll Thank you It's a win-win and that's going to do it for us this week We'll catch you next week and until then

[00:37:55] **Tim:** Remember your heart matters because you're nice.
