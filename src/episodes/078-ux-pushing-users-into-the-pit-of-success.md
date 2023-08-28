---
title: "078: UX - Pushing Users Into The Pit of Success"
description: "This week on the show, Adam and Ben talk about the 'unhappy paths' in software design."
date: 2022-06-08
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/078-ux-pushing-users-into-the-pit-of-success/id1544142288?i=1000565630029"></iframe>

Sponsors

-  [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

This week on the show, Adam and Ben talk about the "unhappy paths" in software design. An unhappy path - also known as a "sad path" - is _anything that can go wrong_ during the consumption of a product. Some unhappy paths are nothing more than unanticipated edge-cases in the code while other unhappy paths are caused by poorly designed user interfaces (UI) that lack necessary constraints and affordances. But of course, it doesn't much matter why something is breaking, if our customers are unhappy, it is our job to fix it.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/078-ux-pushing-users-into-the-pit-of-success.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** But I will say the idea that a scanner is just a keyboard blows my mind. And I remember I was working at a company and one of the other guys with was scanning. are the, what are the,

[00:00:11] **Adam:** Barcodes.

[00:00:11] **Ben:** what are they here? Yes. Thank you. I was, my brain was trying to say horizontal QR.

## [00:00:40] Intro

[00:00:40] **Adam:** Okay, here we go. It is show number 78 and on today's show, just the two of us. Ben and I are going to be talking about user experience guardrails. Tim is currently Mia in Barcelona, Barcelona, and Carol is Mia in California. I guess hopefully those guys are having fun getting sun, but we're going to hold it down and do the podcast.

[00:01:01] **Adam:** So as usual, we'll start with our triumphs and veils. Ben, I guess we'll start.

## [00:01:05] Ben's Failiumph

[00:01:05] **Ben:** I'm going to start with a failure and that's a kind of a combination of triumph and fail. And the triumph being that I feel just like I'm manically crushing it. This. I'm taking vacation next week. So I have in my mind this idea that I want to finish and deploy this feature by Friday, which is looming very closely.

[00:01:26] **Ben:** We're recording here on Wednesday night. I created an epic for myself last week that outlined most of the tickets, and I've just been burning through these interfaces and, backend API calls and database table creations. It, the feature that I'm building is the ability for Invision administrators, to be able to send an email to some segments or multiple segments of their team through the Invision platform.

[00:01:54] **Ben:** So new tables, new endpoints, new workflows, new user interfaces. it's not a ton, but it's a lot and it's multifaceted and I'm just like cranking out these tickets. so that's the triumph. I really feel like I'm just being super, super productive. The failure there is that it's at the sacrifice of basically everything else.

[00:02:17] **Ben:** I've been putting in some extra time, like quite a bit of extra time this week, just trying to get those tickets. basically not looking at my emails at all. I'm not responding to people. I just like have not been working out this week. I have not really been paying as much attention to the dog as I normally should.

[00:02:34] **Ben:** It's just, I've become super tunnel vision right now. The idea of getting this feature to production by Friday. so I don't love the fact that it's all kind of been a sacrifice, but, at least it's in a very constrained time period. I'm like I'm in the middle of this race and when the race is done, I can go back to normal.

[00:02:52] **Ben:** So crushing it, but crushing it at the cost of everything else that might be meaningful in my life.

[00:02:59] **Adam:** So what's your approach. If you finished the last thing that you need in order to deploy this stuff at like four 30 on Friday afternoon, are you going to toss a match over your shoulder and walk out for, not just the weekend, but like your entire vacation or are you just going to let us sit on the shelf until you get back?

[00:03:16] **Ben:** I think I would need to finish it by tomorrow night in order for me to turn it on Friday, I feel like I need a solid day here with it on and me being able to test it in production to be comfortable just walking away. it

[00:03:34] **Adam:** for listeners that's Thursday night, so you can turn it on

[00:03:37] **Ben:** So I have one more day tomorrow to, I think get it to be quote unquote, feature complete.

[00:03:42] **Ben:** It doesn't mean it's like super polished necessarily, but it's like MVP enough to show people if I can get that done by tomorrow night, I think I can come in Friday morning, turn it on for myself. Do a bunch of testing and production. And then just let it rip for everybody else. I mean, the reality is like, it's not going to be a huge uptick in usage almost certainly not.

[00:04:08] **Ben:** but because it involves emailing people and emailing people in bulk that's like that could go really bad really quickly if there's mistakes. So, I'm definitely going to be cautious, but I mean, ultimately it's not even about the users. I mean, it is about the users, but like half of it is I want to make my, my little celebratory, release video and post it in our private slack channel and be like, yo, check it out.

[00:04:34] **Ben:** I did this, I did a thing. and that's like half of the joy for me is making that video and kind of get into beat my chest a little bit,in the front of my. So it's a mixture of motivations. I just want to make sure I don't make any stupid moves.

[00:04:50] **Adam:** I feel like, I mean, I don't know what you've done for this particular thing, but you guys are heavy users of feature flags. So if this is behind a feature flag, you could in theory, just throw that match over your shoulder on Friday at five o'clock. And if it doesn't work out, they can just turn it off.

[00:05:04] **Adam:** Right.

[00:05:04] **Ben:** yeah, exactly. And the vacation is a staycation. it's just some sort of time off with the fan. We got some, my wife has heard nephew coming to visit us for a couple of days and we're just gonna, we're just going to chill. So theoretically, if there was an incident,I'm still in the on-call rotation, cause there's literally not enough people on the team to not be on the on-call rotation.

[00:05:26] **Adam:** Oh, are you on call 24 7 now until

[00:05:29] **Ben:** I mean, If the other big, if yeah. If the other people don't pick up, it still rotates through number of people. But if those people don't pick up, I'm always in the rotation of people that will get paged. Yeah.

[00:05:41] **Adam:** Gotcha. You're in the escalation

[00:05:43] **Ben:** yeah. Yeah. But the application at this point, there's not enough things that go horrifically wrong for really my team to get paged in the last, I want to say three years.

[00:05:55] **Ben:** I think my team has been page like twice. and that's not a Testament to the rock solidness of the application. it's more just like, not enough of the application has changed. So it's just, there's less opportunity for things to break and the things that do break, like don't break to the level of incident.

[00:06:13] **Adam:** so when you say you page, Do you guys have like automated pages where like the system will detect something is going poorly and paid you? Or is it only like a human is in the loop and they decide to pay you.

[00:06:23] **Ben:** Yeah. So it depends on who you're talking to in the company. A lot of the teams do have automated paging based on metrics that they're, that the system is logging, whether it's, the CPU has been running at a hundred percent for some period of time or something's run out of memory, or the number of available pods has dropped below some threshold, on the legacy side of the house, the system has never been stable enough to get like really good automated paging in place.

[00:06:52] **Ben:** So on the legacy side, the vast majority of pages are triggered either by the support team or by one of the other teams pulling in additional people. So, so like, oftentimes what'll happen as support because we have support 24 hours a day. which I think is mostly like we mostly have support in the U S but then I think we have a couple of support people in Australia.

[00:07:14] **Ben:** So that kind of covers us. what they'll typically do is they'll see an uptick in support tickets and be able to replicate an issue. Then they'll probably page a SRE is our site reliability engineers. And then the SRE is what we'll end up, paging other teams based on what might need to be done. but again, that's for the legacy stuff,the newer platform, they do have, a ton more observed, non observability.

[00:07:38] **Ben:** What's the word I'm thinking of. Yeah. Instrumentation. I think I'm thinking of observability anyway. They have a bunch of, they have a bunch of that kind of stuff.

[00:07:47] **Adam:** Like metrics that they're

[00:07:48] **Ben:** Yeah, yeah,yeah, yeah.

[00:07:50] **Adam:** Cool. Well, I mean, a quick tangent on your triumph there. And we were talking about feature flags. I had a quick feature flag, win moment today at work. one of my coworkers wrote something in our team chat about, I expect to see a lot of, chat notifications for such and such things doing, like a scheduled job doing its work for the next few hours.

[00:08:10] **Adam:** he just wanted to know, let us know. and where'd the thing go? I mean, basically,he disabled a part of the application because the data it depends on, was in the process of being rebuilt. So it wouldn't have been a useful feature anyway. And I was just like, I had this moment where it was. Wow, we can do that. Right. We can just turn off part of the application because we have that ability, it doesn't require deploy or anything. Feature flags are like a total game

[00:08:36] **Ben:** it is such a game changer. I'm so excited that it'sit's it's it's in your head now and you can't go back. You can't go back.

[00:08:45] **Adam:** So there's this guy that, Adam Cameron friend of the show, blah, blah, blah. he shares a lot of this guy's videos. He's a, I guess he's a YouTuber and he mostly posts stuff on testing. but,I watched one of the videos that he shared that was about continuous integration and talking about how like long running feature branches are an anti-pattern and, all that stuff.

[00:09:04] **Adam:** And how feature flags are an integral part of doing true continuous integration. originally I thought of continuous integration as like, anytime you check in code the tests from right, that's.

[00:09:16] **Ben:** Right, right.

[00:09:17] **Adam:** Th that was just my early understanding. And I think that I still don't have a perfect understanding of it, but my currently evolved understanding is that is true.

[00:09:26] **Adam:** But also I'm kind of always checking into Maine and like, so my code and my test additions are always there. And that way, if you and I are both working on the same day and we're kind of bumping up against each other, then it, if one of my tests fails because of a change that you made, even though my feature is not in production yet, we're aware of that problem before it gets to production.

[00:09:49] **Adam:** like, we're not at that level of our feature flag usage, but I like that we have that opportunity ahead of us.

[00:09:55] **Ben:** well, let me ask you a question. How long can something sit in the main branch reasonably before you deploy it? this is a philosophical debate that we have at the company a lot.

[00:10:07] **Adam:** okay.

[00:10:07] **Ben:** and my team tends to sit on the side of what's in production should be what's in Maine, so that if something is exploding in production, you can look at the main branch and be like, this is a representation of what's in production. Other teams will like merge to Maine for days before, the deploying and yeah, and that has caused all kinds of issues on their side, but I can see it both ways.

[00:10:34] **Adam:** I can see. Yeah. I can say it go both ways. I think if you're going to do the multiple, like commits over days or whatever, you have to go with tagging, right? So you have these points in time where, this is what. Deployed. So you can get back to that state to debug something or whatever. And there's, it's tempting to take that approach, but I guess I'm also a huge automation fan boy, and I would love, we have the ability right now, and we do for certain things currently deploy because you pushed a code change, right?

[00:11:07] **Adam:** you pushed a code change that triggers a good hub action. That action will like build a Docker container, run the tests. And if everything passes, it all deploy a new container to ECR and ECS, or it'll push up a new version of a Lambda function or whatever. And we were, even for our QA environments, we are doing that, which are our QA environments are CFML.

[00:11:26] **Adam:** So we're building a new CFML Docker container with Lucy and our application code in it, running the meager tests that we have against that, and then deploying that. and it's not a fast thing, which is annoying, but that's not the automation tool chains fault. Java and Lucy's fault. and, I think some of my team members, especially, well, I don't want to, I don't want to throw anyone, anybody under the bus, but I think some of my team members are skiddish about that level of automation.

[00:11:51] **Adam:** They're worried about something getting accidentally created a domain and then making its way out to production. And, my opinion is

[00:11:59] **Ben:** the more effort we can put into automating deploys and making that deploy process as fast as possible, the faster we can recover from anything that anything problematic that makes it out to production.

[00:12:13] **Adam:** And it's a non-issue

[00:12:14] **Ben:** Yeah, definitely.

[00:12:17] **Adam:** So yeah, I see both sides. I'm of the opinion, like just, anytime you push domain, it should.

[00:12:23] **Ben:** that's where I stand,

[00:12:24] **Adam:** Realistically, like we have a few things that are automated, like I said, like our production environments and certain other things are manually deployed. It's all automated still, but it's at the push of a button instead, so that we have that human in the loop.

[00:12:38] **Ben:** yeah, we still have the human in the loop. We it's, we have a chat bot at work. So I go into a deployment channel and I say our chat bot is called rosy, based on the Jetsons. And I say Rosie release and then the name of the service that's being deployed and then the robot does all the things.

[00:12:55] **Ben:** yeah, but I'll tell you, so you talked about some of the slowness around Lucy and Java. one place that I struggle with, and this is going back to, how often do I want to deploy versus how often do I want to merge into main part of my thinking there that weighs on me is that when we deploy and I don't know where this goes wrong, but we have Kubernetes, Kubernetes is what manages all the things in production.

[00:13:21] **Ben:** I know next to nothing about Kubernetes, other than this like general idea that it's basically like a much fancier version of Docker for Mac. And I don't even know if that's accurate, but that's like, that's my mental model. So anyway, we deployed a production and the deployment process. It takes a bunch of the old pods offline and puts a bunch of new pods with the new containers running and then shift the traffic over for reasons that I have not understood.

[00:13:49] **Ben:** And we've been using Korean Indians for like five years now. And I still don't understand why this happens. Kootenays will continue to send traffic to a pod that is shutting down. And I don't know if it's that the pod is shutting down too fast or Kubernetes. And all of the load balancers are too slow to sync up and they continue to send traffic to places they shouldn't.

[00:14:10] **Ben:** But essentially during every deployment, even though we're spinning things up and spinning things down gradually over a period of time. I know for a fact that every deployment does cause some small degree of user interruption, because I can see it in the air logs. Every deployment they'll be like a small spike in.

[00:14:31] **Ben:** Out of memory errors, because someone was making a request to a pod that was just about to shut down or like thread deaths, or like thread interruptions, like things that just shouldn't happen. And I don't know how to solve it. And I feel terrible about it because every deployment that I do, as excited as I am to deploy code to production, I know like somebody requests it probably going to break and they're going to have a crappy experience.

[00:14:53] **Ben:** And I've tried to put things in place. And this actually ties a little bit into the topic of the show. I've tried to build like some automatic retries and the JavaScript on the client side so that, cause it's all load balanced. So if one request hits a note and that note is just about to shut down and that request fails.

[00:15:09] **Ben:** Like sometimes the UI will actually retry the Ajax request and get the data and hopefully it hits a new pod. and it should be load balanced. But then people telling me that the Kubernetes load balancing is actually like, not really that. So if you hit a dying pod, there's not, it's not an insignificant chance that your next request, we'll also try and hit that same dying pod.

[00:15:29] **Ben:** This is all just like over my head and I end it and I feel crappy about it. Cause I know it's not a good user experience, but at the same time I have to get the code to production. And there's not like there's not a lot of Java expertise to help me figure out how to configure the pods better.

[00:15:44] **Ben:** And I don't know. It's very frustrating. I feel really bad about it, but I

[00:15:49] **Adam:** Yeah,

[00:15:50] **Ben:** moving forward.

[00:15:52] **Adam:** Yeah. It's like on one hand you want to be like, no request left behind, just every request matters. But on the other hand, like if you're handling 10,000 requests a minute, you know, is an error for three of them,

[00:16:06] **Adam:** that big of a deal.

[00:16:07] **Ben:** right, right. Yeah. it's it's very challenging. It's very challenging.

[00:16:12] **Adam:** Yeah.

[00:16:13] **Ben:** Oh, so that's my triumph, my failure.

[00:16:18] **Adam:** We're 15 minutes in.

[00:16:20] **Ben:** What about you? What do you got going

## [00:16:21] Adam's Triumph

[00:16:21] **Ben:** on?

[00:16:22] **Adam:** I'm going to go with a triumph. it's a weird week for me. So, I was not on the show last week because I was out of town. we've talked a couple of times about some of the stuff that my company does. we have software designed specifically for universities and colleges to use for their large events, like commencement reunion, homecoming, that sort of thing.

[00:16:40] **Adam:** that's one of the, like one line of our business. But, so we were at Princeton's reunion this weekend, which I believe they had, 27,000 people register for, 23,000 of whom showed up.

[00:16:51] **Ben:** holy cow.

[00:16:53] **Adam:** yeah, it's a huge event. They've got like 14, like class headquarters. Right. So if you're now granted, this is their first time back after COVID, so there's a lot of pent up, like got to get back to. Yeah. and so, and I don't know if this is typical or not, but like, so say it's your 10th reunion, so it's 20, 22. So it would've been 2002 graduation year. Right. So, but like, so they have a, a dedicated area on campus. It's got literal fences around it, big, like, eight foot tall wooden fences around it.

[00:17:22] **Adam:** this is the 10th reunion area. and their signs out front say, okay, this is 2002, but it's also for 2000, 2001, 2000, 2003, 2004, 2005, whatever, like a group of years. And it's like 2002, this is your reunion year. This is your spot. But if you happen to be from one of these other years, like, you're welcome here.

[00:17:39] **Adam:** You're, you're kind of invited, this is your designated home. you're an honorary where you here, sort of thing anyway. and there's, so there's 14 of those across campus ranging from, I think the, so the there's big ones and they're small ones. And I think that they had. First and second, I don't know.

[00:17:58] **Adam:** I don't know, but that the huge ones were fifth and 10th reunions and then it kind of trickles down. They have a, it goes all the way up to 60th. I

[00:18:06] **Ben:** Holy cow.

[00:18:08] **Adam:** it's either 63 or 65th. That one of the two was their last one. And then they have what they call the old guard, which is just like

[00:18:15] **Ben:** If anyone is still alive, come to this fenced off area.

[00:18:19] **Adam:** yeah.

[00:18:19] **Adam:** Yeah, it was huge. we, so we deployed a crap load of equipment to this. I mean, we're doing so when you check into the event, you pre-register online, you get an email with a QR code in it, in your confirmation. When you show up to. To check in on campus. You bring either that printed out or on your phone or whatever we scan the QR code will bring up your record, make sure you don't still own money.

[00:18:41] **Adam:** And then we click the check-in button or whatever, and you're there for identification. They give you a wristband instead of like, a lot of things like when you go to conference, you often get a name tag on a lanyard, or you wear it around your next. We're saying Princeton has, I guess, for a long time done what the, they it's a wristband.

[00:18:56] **Adam:** and they, I think they would just to have like maybe numbered wristbands or something like that. It wasn't, you would get a wristband and it would be like, okay, you're, registered and you're officially here, but there was no like identification on it. So one of the things that we did for them.

[00:19:12] **Adam:** Is, they got these pretty cool upgraded wristbands. there, you can only put them on you can't take them off. like it's kind of a, like a bead slides down the fabric or whatever to tighten on, but you can't take it off. And then, it had like little, a little plastic plaque on top, almost like a watch, right?

[00:19:28] **Adam:** Like you can think of like a watch band that you just can't take off. and on that plastic plaque was a QR code. And then, so when you would check in, they would check you in and then they would pair your registration to the QR code that they put on your wrist. So that when you walk into one of those zones, you're like you're walking into the fifth reunion and there's somebody standing at the door with like a little, it looks like a Palm pilot with like a trigger handle.

[00:19:51] **Adam:** Right. You know, they scan it, a little red light comes out the front, they scan your QR code and it shows them, okay, this is your name and your,older enough to drink or whatever. And you're, you're good to go. or it'll say reject it. They sold us money, or don't let this person in it's a stolen wristband or. Yeah. Yeah. a couple of different things. it was huge event and it went off great. Oh, the other thing that fantastic, they now, I can't really claim credit for this, but you know, it's my company I'm gonna take partial credit. so a lot of these people come, and during the day some people bring their kids, right?

[00:20:22] **Adam:** Like, it's just, it's a big party. there was a three-year-old kid. I think it was three young enough that they weren't really talking all that much. Especially just strangers got separated from their parents. and like somebody just like found a kid and we were like, now what they brought them to, to like the registration desk who got public safety involved, that's a campus security.

[00:20:43] **Adam:** And we figured out scan their wristband on the. That brings up their registration record, and then we can call the parent or right off the registration record. And within like three minutes of somebody finding the kid, we were calling the parent and we called them before they even realized they didn't have the kid with them anymore.

[00:20:58] **Ben:** Yeah. Very cool.

[00:21:00] **Adam:** that was awesome.

[00:21:01] **Ben:** you talked about how you're on a relatively small engineering team, right? I think you said there's five of you. So when AlumnIQ gets deployed to a university, how many people are going of your

[00:21:13] **Adam:** Well, so, yeah. Yeah. So my team, I guess I would say is three people, it's myself and two other developers. And then we have two other people in the company, my CEO, who does like a little bit of everything, at Steve who we've had on the show before, and then we have another guy who's his whole job is just logistics, like sorting out the name tag designs for all these events in advance and doing paper orders and managing all of our equipment and shipping and all that stuff and dealing with setting up their events so that the developers can focus on developing a, not data input sort of thing.

[00:21:42] **Adam:** the number of people that we send to an event depends heavily on, the size of the event, really like that was Princeton. They had 27,000 people registered. We had four of us onsite. We probably could have done with more, but we just didn't have the staff, between COVID and other events going on and stuff.

[00:22:00] **Ben:** I mean, that's pretty amazing that you can run an event that large with just a handful of people.

[00:22:04] **Adam:** that was our staff to, to manage our equipment. There

[00:22:07] **Adam:** was also the, you

[00:22:08] **Ben:** right, Princeton is running up and it has like hundreds of people helping to run.

[00:22:11] **Ben:** There's probably hundreds of just security guards.

[00:22:13] **Adam:** Oh yeah. There was, that their campus security staff, then they pulled in, like, I don't want to be smart to anybody, but you know, like rent a cop type services,

[00:22:21] **Ben:** yeah. Yeah.

[00:22:21] **Adam:** to help them out. And then they also, from what I understand, got some of the like Princeton, New Jersey police to like come in and help and, that sort of thing.

[00:22:30] **Adam:** And, yeah, and that, that's just the like security side. Then there's all of the like university staff that are like working the check-in areas of the tents. Right? So like our job being there is not to sit there and check people in our job is to. Respond to whatever might be going on. Notice the patterns if it looks like equipment starting to go down, or if we're having network issues, whatever, that sort of thing.

[00:22:51] **Adam:** So we're running around like crazy trying to keep an eye on stuff and deal with whatever might come up and retrain people that didn't pay attention to training. but,the real work is being done by like basically staff and volunteers and some student workers.

[00:23:05] **Ben:** Have you ever had something go wrong at an event that you couldn't recover from at the event?

[00:23:10] **Adam:** Not that we couldn't recover from. I mean, we've had some pretty big things like, pretty early on when it was just me and Steve. we had an event at the university of Delaware and we set up, like they had a whole line of tables for like self check-in, right. Your way through the line, you go through the stanchions, that little zigzag Serpentini thing.

[00:23:26] **Adam:** When you get to the front of the line, there's like 12 or 20 whatever computers in front of you. You go to the next one. Empty and you just go scan your QR code. It prints out your name, badges, and you go on. Well, for whatever reason, we ended up with just this one spot where there was a, they have a floor pocket where the power comes up out of the middle of the floor so that you can get it in different sections of the room.

[00:23:48] **Adam:** And that was supposed to be under the table, but for whatever reason ended up in front of the table. And so we had like taped it down, try to make it real nice or whatever. And,you would think college graduates would think maybe I shouldn't step on this cable. That's taped to the floor. Well, enough of them did that.

[00:24:08] **Adam:** Eventually somebody stepped on it and step and like snapped through the extension cord that was running half of our machines.

[00:24:15] **Ben:** Crazy.

[00:24:17] **Adam:** Yeah. and what's even crazier. And this was like during peak check-in. So this was at a, I don't want to give away too much, but like, this was at an event where like, let's just say it's like 15,000 people registered and like we're expecting, I don't know, nine or 10,000 of them to come through.

[00:24:33] **Adam:** in like a three hour period. so it's like peak check-in time and a boom, half the stations just go offline. They just powered down screens, go black. And you're like, what the heck just happened is cause somebody cut the extension cord that everything was running off of. Well, it could have been worse because when we were setting up, we were like, okay, should we let, we could have very easily run everything off of that one extension cord, but I was like, eh, let's have some separation here.

[00:24:59] **Adam:** like the

[00:25:00] **Ben:** to build in redundancy.

[00:25:02] **Adam:** Yeah, some redundancy. So, so we did have two power sources that we were using and he it's like, although the machines on the left half were on here and all the machines on the right half were on there and it's like, we just lost that one half. And so they were able to keep using the machines on the left and I ran a new extension cord real quick, and I got everything back up and

[00:25:21] **Ben:** I assume that, early days, the level of anxiety going to a live event and the number of things that theoretically could go wrong, I assume there's still some anxiety going to an event, but are you just way more comfortable now than you were before?

[00:25:35] **Adam:** those like gifts of people, like looking around all confused and there's like weird math equations

[00:25:41] **Adam:** floating in front of their faces. That is us heading into these enormous events, especially like, so Princeton, this was our first like real event with them. We had done something with them shortly pre COVID, but just with like one of those reunion sites like that, that one tent had pulled us in to do their registration and check-in that year.

[00:25:59] **Adam:** And then they were so happy. They were like, everybody has to use this. This is great. and so that one year,we kind of got a little bit of an understanding of how the event goes, but we didn't really truly get to grok like how much equipment is needed and what needs to go, where and where we can expect a people volume to go.

[00:26:17] **Adam:** And that sort of thing. So we expected chaos at this at Princeton's reunion and we got it, but we learned a ton and I think that next year we'll do so much better. It will be so much lower stress. we'll have wait, like we were working 18 hour days plus or minus,it's like get up at six and get ready and, be on campus at eight so that you can train people so that,they can set up at nine so that registration can open at 10 and then you're running from 10:00 AM until like 2:00 AM.

[00:26:44] **Adam:** And you gotta wait for the equipment to come back, make sure you get it all charging so that it can be used the next day. And then, go back to your hotel. And, you get back to your hotel room at like three 30 crash and get up at six o'clock and do it that again, the next

[00:26:56] **Adam:** day it's like, poof, it was rough.

[00:26:59] **Adam:** so we learned from that too. It's like, okay, let's do some shift work or something to try and make that a little easier. But,

[00:27:05] **Ben:** where you like knee deep in, in mountain Dew bottles, I assume.

[00:27:10] **Adam:** oh man, the first day I was like trying so hard to stick to like, I'm just the one soda a day. And

[00:27:15] **Ben:** Oh, extenuating circumstances.

[00:27:17] **Adam:** Yeah, exactly. Yeah. I didn't have any monster, but it was like, oh yeah, just pour the whatever caffeinated beverages you got. Actually, I did have monster.

[00:27:25] **Adam:** I take it back. They had, so by the end we figured out that the, public safety crew had no problem with us. Just kind of hanging out in their little headquarters building. and they, I don't know what the deal is, but they had the best food and the best like drinks. And I mean, they're sending out tons of officers and stuff, and they want him to stay hydrated and well fed and stuff so that they can do their job.

[00:27:44] **Adam:** but it was just like nonstop, great food. I mean, obviously it's not amazing food. It wasn't like, caviar and whatever, but it was, like pizza or Buffalo wings or, there was like a Chick-fil-A catered one day or, Qdoba or whatever, it's just like tons of food, lots of beverages just cooler after cooler with water and monster and Gatorade and anything you could want.

[00:28:04] **Adam:** And yeah, I was abusing the caffeine there.

[00:28:07] **Ben:** No,

[00:28:07] **Adam:** I'm back down to like two a day for the last couple of days.

[00:28:10] **Ben:** Yeah, nice. I, one time went to a tech crunch disrupt hack-a-thon it's the only hackathon I've ever been to. it was like a, just 1 24 hour period. And, they just had so much caffeine in there. And I, I coated all through the night and I remember at one point like at 2:00 AM or something, my hands started to shake.

[00:28:30] **Ben:** And for the first time in my entire life of drinking caffeine, I was like, I don't feel safe. Like this does not feel like a good amount of caffeine.

[00:28:40] **Adam:** This is not what crushing it is supposed to feel like.

[00:28:44] **Ben:** Oh man. Well, congratulations on getting through a, such a huge event. That's awesome.

[00:28:49] **Adam:** Thanks. Yeah, it was, it was a lot of fun. It was very exhausting. everybody was really happy. I mean, everything, all the feedback that we got was everybody loved it. it wasn't without issues, but we figured out what some of them are. we dealt with it. It's little things, right? Like, so here it's, everything is outside.

[00:29:03] **Adam:** So you're trying to run the wifi out of, off of antennas that are like stuck onto the side of buildings or whatever. And it's like, they anticipated the need to be over here, but then it was five feet to the left. And because it's five feet to the left now it is not in the sight line of the antenna. It's like around a corner of a brick building and now there's crappy wifi.

[00:29:21] **Adam:** and so, just little things like that can make a huge difference.

[00:29:25] **Ben:** Well, do you speaking of wifi, cause I know it at large events, wifi is often a problem. Do you hard, do you wire in for all of your equipment to make sure that you always connect.

[00:29:37] **Adam:** We would love to be able to do that. 99% of the time we are forced into these areas where it's like, yeah, here's a table under a tent, like an easy up tent out in the middle of a

[00:29:48] **Ben:** yeah.

[00:29:49] **Adam:** So, yeah. we're, sometimes we're even lucky if they run power. I mean, I don't think we could truly work without power.

[00:29:56] **Adam:** Our printers need to be plugged in, but I think everything else could theoretically run off battery. so it, like, I guess we've done things where, we don't need to print, like with the wristband thing, we don't need to print because it's already there pre-made wristbands. yeah, I mean, it's basically we run everything off of my FYS or sometimes we'd have like some devices with SIM cards.

[00:30:15] **Ben:** Oh, so that, so you're running off of your own network.

[00:30:18] **Adam:** Yeah, or, I mean, it's a mixture, right? So, my FYS or, if it depends on what we're doing, right. So there's PCI concerns too. Cause sometimes you're going to be collecting payments. so typically what we'll do is we have a dedicated wifi network that the school will provide. it's like specific to that event specific for our machines.

[00:30:38] **Adam:** and that way, at least we don't have to worry about that network itself being clogged. So I have concerns about it. if there's a thousand phones within a radius of that antenna, it doesn't matter whether or not they're connecting, they're going to be seeing, and there's going to be interference, if they're trying to connect to a different wifi network.

[00:30:56] **Adam:** So yeah, I don't know, it tends to be one of those things that like is never perfect, but you can typically find a way to make it good.

[00:31:04] **Ben:** So much tickets. This is one of those things where,people have an idea for something, and they're super cagey about sharing that idea because they think off, if anyone else heard this idea,then you know, they'll just run with it. and my, they, like, I won't get rich off this idea, but like so much more goes into getting something to work than just the idea.

[00:31:26] **Ben:** Like there's just so many moving parts, so many barriers to entry and hurdles, just thinking about how power cords and networks and dedicated networks and my FYS. I mean, just, it's just like, I would just, if I dare to even think about the, extensive city of what goes on, I'd be like, oh no, not for me.

[00:31:44] **Adam:** Yeah. I mean, it was something you said earlier made me think of,you were talking about us having a small team and putting on these events for these huge people. Obviously we couldn't do it ourselves. we rely a lot on the campus staff and their volunteers. all that, but,when we started, it was just me and Steve and we had, the university of Delaware's our first big one.

[00:32:02] **Adam:** I guess before Delaware, Steve was working with Cornell, they have a really big event as well, but yeah, I mean, there's a huge imposter syndrome. You're like, if I fail at this, then this whole event is going to crash and burn and it's going to be my fault. And that's a huge amount of pressure, but so far we've never had any major issues.

[00:32:23] **Adam:** Nothing unrecoverable.

[00:32:24] **Ben:** Yeah. Awesome men and many more.

[00:32:27] **Adam:** Thank you. Yeah. Oh man, it's crazy. Like this is it's a blessing and a curse. Cause like this is our busy time of year. this is the time of year that all the schools want to have their commencements and reunions and everything. And so basically my entire company is on the road every weekend from like, I dunno, sometimes as early, as like last weekend in April through mid June,

[00:32:49] **Adam:** and yeah, I mean, like I did university of Penn, yeah.

[00:32:52] **Adam:** University of Pennsylvania. I did Princeton last weekend. This weekend, I'm going to be at Swarthmore and the following weekend, I'm going to be at university of Delaware and that's just me. Right. Like my coworkers are flying all over the place too. Right. We're doing brown up in Rhode Island and,university of Maryland has an event in Manhattan tonight.

[00:33:10] **Adam:** Somebody is going to work and like, it's just crazy. This time of year is nuts for us.

[00:33:15] **Ben:** Yeah, I can imagine.

[00:33:17] **Adam:** So, yeah.

## [00:33:20] Guardrails For A Bulk Email System

[00:33:20] **Adam:** So, you had talked previously about, something like from your failure about, sometimes you have to, you feel like you have to put in guard rails. for your users for stuff.

[00:33:28] **Ben:** Yeah. So, one of the things that I'm considering here, and this is part of the gravity of the situation is that I'm sending out emails to a lot of people or theoretically, I could be sending out emails to a lot of people. and as silly as it sounds, we still live in a world where people on the way.

[00:33:45] **Ben:** Double click submit buttons and it can be really easy for that. Double-click to lead to double things in the server. And, if it's two records that get created accidentally, that's like not a huge deal, but if it's two sets of a thousand people being notified by email, I mean, you could squint and say like, it's just email.

[00:34:06] **Ben:** It's not such a huge deal, but it feels like a much bigger deal when you're notifying people in bulk.

[00:34:12] **Adam:** yeah, and it's not a big deal until somebody important gets notified twice or

[00:34:16] **Ben:** yeah, yeah, yeah, yeah,

[00:34:18] **Ben:** exactly. And oftentimes I try to lean on the database as much as possible for you to have like, I'll have a unique index on something. So that double submits either fail. Like the second one will fail or at least there'll be something I can, I don't know if this is something I can recover from potentially, or I could do like an insert ignore into kind of a thing.

[00:34:40] **Ben:** And at the SQL level, But something like this where it's, there's nothing particularly unique about an individual email. I'm a little bit stumped on, obviously on the client side, I prevent DoubleClick's from actually doing something. Right. So the first click, usually we'll set some sort of an is processing flag in the JavaScript so that even if someone were to click again, the second click would just be ignored.

[00:35:07] **Ben:** and I feel like, that's probably gonna to cut out the issues period, but like I, part of me is always worried about that. Maybe it won't, or maybe someone will accidentally remove that flag or maybe I just messed it up.

[00:35:20] **Adam:** Or disabled JavaScript or whatever. Yeah.

[00:35:22] **Ben:** Like something will happen. And then I was like, I don't know what else to do if

[00:35:29] **Adam:** Yeah. You want to, I have a, an idea. So the first thing that came to my mind, throw a grid in the form as like one of your hidden form fields.

[00:35:36] **Ben:** Yo, it's so funny. I was literally like, just before we got on the call, I was like, oh, maybe what if I've just provided a value from the clients, but go ahead. Go ahead.

[00:35:44] **Adam:** so yeah, you just have a grid and then you assign that to your message or whatever that you're sending wherever you're storing that. And you just check for duplicates. If I've already sent this go ahead, then I don't,

[00:35:54] **Adam:** I can

[00:35:55] **Adam:** ignore this request.

[00:35:56] **Ben:** you, store that in the table,or you storing it in like a temporary mechanism somewhere?

[00:36:00] **Adam:** it depends entirely on how your email system is operating. I don't know if you're saving the contents of the messages that are

[00:36:05] **Ben:** Yes. Yeah. Well, no, no.

[00:36:07] **Ben:** So, so essentially the way I've designed it is it's a two table mechanism that there's one table that represents like the subject line and the content and a call to action. Like basically the outlines, what the email will be. And then a second table that says, okay, now for each one of those records, now I need an individual record for each user.

[00:36:29] **Ben:** That's going to be notified. So essentially the second table acts like a, I don't want to say message queue, cause it's not really a message queue. Cause it is, it's a historical record of the emails that go out, but it's not the copy. So it's like a one to many relationships. So essentially you create the, this, I call it, I'm calling him a mail blast.

[00:36:49] **Ben:** there's one mail blast record. And then there's N number of male blast recipients. And they all kind of get this scheduled and sent date. And then there's a background, a ColdFusion scheduled task that runs in the back and just says like, give me the next chunk of people who have been scheduled, but not sent and I'll send them and then I'll mark them as send kind of a thing.

[00:37:09] **Adam:** So what, when somebody clicks the send button, what is that actually triggering? That's like saying is that

[00:37:16] **Adam:** sending, like, setting a, a flag

[00:37:17] **Adam:** that says I should be sending,

[00:37:19] **Ben:** Yeah, so it creates the mail blast record and it creates the end number of user records that need to be notified.

[00:37:25] **Adam:** do you not have like a draft status or anything?

[00:37:28] **Ben:** I was thinking about doing a draft status, but then because I'm racing to get to this deadline, I'm like, it's. So I'll tell you, there's something fascinating about flexing, a MVP muscle where every time you think, Hey, wouldn't have this feature would just be a little bit cooler if I did X or like, it would be just a little bit more elegant if I did Y and you constantly have to say to yourself, like, no, no MVP solve that next time, get this out the door.

[00:37:57] **Ben:** And then like create a fast follow epic or something else to add the new value. But, so I've been really, I've been really trying hard to solve only the problems that I have right now. And even that I've failed at a little bit, but, I'm trying so.

[00:38:12] **Adam:** Well, yeah, I mean,there's a couple of things you could do. I mean, even if you're, so you, you don't have an ID that already exists on like your draft message that you could say, okay, well I've already sent that one, so I don't need to do it again. But you could still, just in the view itself, create a grid and say, this is the grade for this action.

[00:38:30] **Adam:** and log each one. It would cost almost nothing to throw that in the database, even if you delete them all after two weeks or something,here's a grid for a message and it belongs to this message ID or blast ID, sorry, I'm using my own terminology from my app. right. So it's got a mail blast ID and the code that was used to send it.

[00:38:47] **Adam:** And, and like a flag that just says it was sent or whatever, or it was cute,

[00:38:51] **Ben:** I'll tell you, I really liked that idea because it's so simple and the grid doesn't really mean anything. It's just a uniqueness marker. So. It's like a, I don't love the idea of storing in the database, but if I do store it in the database, then I can put a unique index on it. And even if I never look anything up, at least two inserts in a row with the same grid will fail.

[00:39:14] **Ben:** And like, ultimately it here's. The thing is like from a user experience standpoint, you're weighing the pros and cons of different failure modes essentially, right? With like how you put everything together. So there's the failure mode where I accidentally sent the same email twice to a thousand people.

[00:39:30] **Ben:** And then there's the failure mode where their form shows an error message because they're getting the results of the second click and not the first click kind of a thing. Definitely I can recover much better from the something went wrong with your form submission error than the I accidentally sent the wrong email to a lot of people.

[00:39:48] **Ben:** So, I, I'm definitely liking this idea. I mean,

[00:39:53] **Adam:** Yeah.

[00:39:57] **Ben:** And it doesn't, as far as a grid, it doesn't even necessarily need to be globally unique. Right. So, so the mail blast table has a customer ID. and if I add, if I had some other unique token, I could have my, I could have my unique index on the customer ID, comma, token value.

[00:40:16] **Ben:** So it doesn't have to, it would just have to be unique to that customer. And then, it could even be just like a tick count or something.

[00:40:23] **Adam:** Honestly, I think that you're already over-complicating it like that. Cause I know you're using CFML

[00:40:30] **Ben:** Just

[00:40:31] **Adam:** you know, the yeah. create you, UID is going to be unique enough. Like the possibility

[00:40:37] **Adam:** of overlap there is. Yeah.

## [00:40:40] UUID, Hashes and Integers

[00:40:40] **Ben:** Yo, can I, sorry, just a side tangent for a second. I have this weird irrational fear. That I'm going to quote unquote, use up the UIDs. And I know that technically that's not how you UIDs work. Like there they're time based as far as I understand, like it's a combination, I think of like times and counters and entropy.

[00:41:03] **Ben:** but I'm just, every time I call create you, UID part of me is like, don't call that too much. You're gonna run that.

[00:41:12] **Adam:** Yeah, it's crazy though. It's like something like, there's more available than there are atoms in the universe or something like that. It's possibility. And then, like I, I totally understand that feeling though, because, so for our support tickets, we have a ticketing feature built into our app.

[00:41:29] **Adam:** And instead of having like a numeric ticket ID, we kind of wanted to hide the fact that the app was real young. So we were like, okay, anything numeric? it starts at 6,000 instead of one. and, so our support tickets, what I did was I like did a shot 2 50, 6 of squid or something like that.

[00:41:46] **Adam:** And then it's like the first six or eight characters of that Shaw is the, is the ticket ID. And I store the full Shaw in the database. But if you're searching a w like where you're trying to pull up a ticket by ID, the ID is in the. Whatever ID you pass it. It looks for a Shaw that begins with that. So if for some reason in the future, we need to expand out to 10 characters or something.

[00:42:07] **Adam:** We could do that. And we just have to start

[00:42:09] **Ben:** Mm.

[00:42:10] **Adam:** more back.

[00:42:11] **Ben:** Yeah. I feel like using non-numeric keys in a database is an area that I just don't feel very versed in. Like I don't feel very comfortable. I don't know what the doubt that implications. I know that having an integer as a primary key, that's like super battle tested. And th there's not, there's nothing you can do.

[00:42:32] **Ben:** That's wrong. That's just like, that's how

[00:42:35] **Ben:** the

[00:42:36] **Adam:** Uh,

[00:42:36] **Ben:** efficient.

[00:42:37] **Adam:** have you,have you seen some of these apps?

[00:42:40] **Ben:** what I mean is like the, there's, it's a small space, right? it's four bytes for an unsigned integer. and they're just really good at looking up by integers as far as I understand. but if I wanted to start storing character based keys as my primary keys, I start to, I just, I feel like someone needs to educate me on how that works and what are the trade-offs like, what are the downsides of doing that?

[00:43:09] **Ben:** What are the benefits of doing that? and then just like what things to keep in mind. Cause right now I feel like. I wouldn't do it. Right. And I'd ended up creating like massive indexes where instead of four bytes for each index entry, it's like 32 bytes of character data.

[00:43:26] **Adam:** Yeah. I mean, you're,

[00:43:27] **Adam:** you're on the right path.

[00:43:29] **Ben:** some databases, I think they have like special representations of DUID is like, it's not 32 characters.

[00:43:37] **Ben:** It's like a binary value. That's much more efficient, I think. But then I think that's only if the database does it for you, not if you provide it. I don't know. Say like, I don't know what I'm talking about. I probably what I just said is entirely wrong, but

[00:43:49] **Adam:** we're out past our depth here.

[00:43:50] **Ben:** yeah. I just feel like I, I need to take like a, you dummy chorus on, so you want to use as primary keys.

[00:43:58] **Ben:** w I would watch 10 part episode of that,

## [00:44:04] Guardrails For An Android QR Code Scanner

[00:44:04] **Adam:** So I want to move over and talk about a user experience thing that I've see a lot. So I find that like with certain types of people. Teaching them how the equipment works. Like, so specifically I'm thinking about a certain piece of equipment that we use for our reunions, like our QR code scanner, things that I said, it looks like a Palm pilot with a trigger handle.

[00:44:24] **Adam:** basically the way that it works is it's an Android phone. That's got a built in like laser scanner thing, like I like to have at the grocery store. and it's trigger actuated. and that scanner, acts as a keyboard in the Android phone, right? So you focus a field and you click the trigger, it shoots out the scanner, whatever data it reads, it drops into whatever field happens to be focused and hits. and there are certain people, like, especially when you're working with like college students, you're like this thing is a keyboard. You just got to make sure that input is focused. You pull the trigger and it does its job. And they're like, cool, perfect. I got it. And then, I don't want to throw old people under the bus.

[00:44:59] **Adam:** that's my crew now. Right. I'm old, but,certain people find it particularly difficult to understand that concept and, no matter what you do there, it's the type of person that like can't help, but brush up against the touch screen and mess something up when they're not trying to, they're just holding the device off to the side or whatever.

[00:45:17] **Adam:** and like, it's too easy to get upset with people that are trying to use your application that don't fully understand. Like how to make things go perfectly, because if you know what you're doing and you use it perfectly, it works wonderfully. But if you don't have those guardrails up and somebody brushes up against a touchscreen or something like that and sends things haywire, then it's really easy for everything to go off the rails.

[00:45:46] **Adam:** And all of a sudden you're getting called down to a reunion site because their scanner device has 37 tabs open in the little Chrome browser. and, they're just, it's making a beeping noise, but it's not showing them anything useful. so, we, my team, saw some of the struggles that we were seeing with those things this last weekend, and we're brainstorming all these different ideas of how to make that thing, like more user proof.

[00:46:09] **Adam:** Right? So like, I think that there's a, like a kiosk mode in certain Android devices or in, different apps you can set up so that like, or maybe it's in Chrome. I forget exactly where it is, but there's a kiosk mode sort of thing you can turn on, which is. You can't exit the app and you can't open any new tabs.

[00:46:26] **Adam:** So you're just there and it's full screen and it looks like that's the only thing that the device does. and then like, so th that would help partially. and then it's like something as simple as you could do, like, on document dot on click,focus that input again, so that if they happen to touch elsewhere, then it focuses it and put again, and you don't have to worry about it.

[00:46:44] **Adam:** Like, just lots of little things like that could go a long way to, to make the, user experience like more foolproof. And it was kind of fun to sit down and brainstorm, like all the different possibilities we, before we came up with that document dot, on click thing, it was like, we were thinking, okay, well, what if we did a set time out of like every three seconds, just re focus that input.

[00:47:05] **Adam:** Yeah. Or like, what if we did on blur of the input, refocus it or whatever, but.

[00:47:11] **Ben:** Yeah.

[00:47:12] **Adam:** I don't know, I feel a personal responsibility not to get upset when users find a way that I didn't predict, to mess up how they use my application. Right? Like as the designer of the application, I take full ownership of that user experience.

[00:47:27] **Adam:** And if it doesn't go as I intended, then that's on me. and that's just, that's it that's that, ah, can't explain it any further than that.

[00:47:38] **Ben:** no, I think it makes a lot of sense. I think we've talked about this on the podcast before that just not enough people even consider the unhappy paths of workflows and user interfaces. And there's so much that can go wrong even, just in the mail blast thing that I'm working on right now, for example, My database field is let's say the subject line is 250 characters or 2 55, whatever the default is.

[00:48:04] **Ben:** I think I just use that. but it's storing utfh M before, so people could theoretically put emojis, like little rocket ships and whatnot and there's subject lines.

[00:48:13] **Adam:** Yeah,

[00:48:14] **Adam:** it's a sore subject for me, but go ahead.

[00:48:18] **Ben:** so I also have max length on the input fields, cause I don't want people to put in a lot more than they can do, but I don't yet have a strong grasp of how max length on say an input field maps to a character said that can like, can take up to three bites.

[00:48:36] **Ben:** Right? So, so, a lot of the emoji characters can actually require three bites or even more to store. But then, so I don't actually know if, the max length that I have on the input is valid, meaning it is a max length of 2 55. In the browser equal to a max length VAR car, 2 55, if the VAR car can contain emojis or does the browser also take that into account?

[00:49:00] **Ben:** What their max length? I don't know. I should probably test that so that all of a sudden it just doesn't fail because of, uh,

[00:49:06] **Adam:** Because somebody tried to send an

[00:49:07] **Adam:** email with 255 kissy emojis as the

[00:49:10] **Ben:** Yeah. Yeah. That's right. Just lots of rockets. I don't know. There's just so much that can go wrong. and when you're barreling towards trying to get something just to a working mode, it, you, you don't take the time all day every day to, to think about all the things that can go wrong.

[00:49:26] **Ben:** and then to what you're saying then to put in all the safeguards so that not just the, to acknowledge that they can go wrong, but then how can we try to counteract those measures? it's really challenging. and I think a lot of, I don't want to say. Younger developers. I think a lot of developers in general, just don't take the time to really appreciate everything that can go wrong and how to cater a better experience. But I will say the idea that a scanner is just a keyboard blows my mind. And I remember I was working at a company and one of the other guys with was scanning. are the, what are the,

[00:49:58] **Adam:** Barcodes.

[00:49:58] **Ben:** what are they here? Yes. Thank you. I was, my brain was trying to say horizontal QR. he was doing something.

[00:50:09] **Ben:** We had to scan QR codes off of, like registration papers for something. And I was like, oh, this is so magical. Anytime hardware gets involved, my brain flips into, oh, this is so magical mode. And he was reading through the documentation of this hardware device that, that he, that we got at the company.

[00:50:26] **Ben:** And w and that's what it said is like, this is just a keyboard, you focus and input and it'll type keys into that input. I was like,

[00:50:33] **Adam:** Yeah,

[00:50:34] **Adam:**

[00:50:34] **Ben:** what mind blown? so simple,

[00:50:37] **Adam:** yeah. Too clever for its own. Good. Actually just clever enough for its own. Good. Really.

[00:50:41] **Ben:** yeah. and he ran into the same kind of issues that you were talking about where I think the input, they didn't even want the input to be visible on the screen.

[00:50:49] **Ben:** So it was like he, they had to wire it up with some sort of a hidden thing. So then it kept losing focus, but no one could actually tell that it lost focus because it wasn't really being vendored facially on the screen. And I, this was 15 years

[00:51:01] **Adam:** Ooh.

[00:51:02] **Ben:** the heck they were doing.

[00:51:04] **Adam:** I just had a totally random thought, like a, some sort of like a, like on focus, event. That's like, okay, I'm ready to scan like a show, a thing, ready to scan on the screen and on blur show, not ready to scan. That would be kind of cool. And like another, so another UX thing, about these scanners, right?

[00:51:21] **Adam:** Like, so one of the things that we noticed is by default, when you scan something with the scanner device, like a physical, thing happens, is it beeps right? To let you know that it captured something out of that barcode? now I guess it happens in software, but it's like part of the scanner app itself and you can turn it on. And we didn't think too much of it. And we were, deployed these things and when somebody with, less, I'm trying to be politically correct here when somebody is not paying attention to what's going on. And they're just like, my job is to stand here and pull the trigger and wait for the beep sort of thing.

[00:51:54] **Adam:** They're not like looking at the screen to make sure it's actually doing anything. It's not just Google searching for six, a, for F two, it's like actually doing something. then, that's a problem right there. We're just listening for the beep. So what we decided we're going to do is we're going to disable that beep from the scanner app itself, but then we're going to have our app beep like a success noise and a failure noise.

[00:52:14] **Adam:** And that, like, that's just one of those little things that you can't really predict that you're going to need until you see how people are misusing your applicator.

[00:52:21] **Ben:** how are you going to make it beep,

[00:52:22] **Adam:** we already do other things to play sounds. It has a speaker on it. and, so you know, like our web app play sounds. Yeah. Like a little MP3 or

[00:52:29] **Adam:** something. An app.

[00:52:31] **Adam:** Yeah. who

[00:52:33] **Adam:** knows?

[00:52:34] **Ben:** there is a, I think there is some sort of like audio synthesis,

[00:52:37] **Adam:** Yeah. Wait,

[00:52:39] **Ben:** there is,

[00:52:40] **Adam:** have you seen the Hitchhiker's guide to the galaxy movie?

[00:52:42] **Ben:** yeah, I watched it like a year.

[00:52:44] **Adam:** Do you remember Marvin? The like super depressed robot?

[00:52:47] **Ben:** Yeah. Yeah, yeah,yeah,

[00:52:49] **Adam:** yeah, this is a great use of my computing power or my resources or something. Like, he always sounds as Alan Rickman, God rest his soul wonderful guy, but,

[00:52:57] **Ben:** Labella

[00:52:58] **Adam:** so we took that as inspiration. So we have this like dashboard that watches our live mail sending, or, you know, when we're sending bajillions of messages out, we kind of want to be able to monitor stuff.

[00:53:08] **Adam:** And so we use the text to speech API as if you happen to have the dashboard up when it's about to send mail and you have the little box check, that's like, make audio, make noise to let me know when stuff's going on. It'll say like, what does it say? Oh, like, it's like, oh, look more male or stuff like that.

[00:53:23] **Adam:** Like, this is a great use of my resources. Cause we pick one of the voices

[00:53:27] **Adam:** that sounds kind of depressed.

[00:53:28] **Ben:** I think the text to speech API would make for a really awesome, Eastern. Well, like an April fool's joke or something like trying to go and do something, the system and the system's like, are you sure you want to do that?

## [00:53:41] April Fool's Joke Goes Wrong

[00:53:41] **Adam:** Oh, man, maybe this is an appropriate time to bring up what I did for our April fool's joke this year. Cause it was, it did kind of have some UX concerns and it wasn't something we could have predicted. And when it went sour, we turned it off real quick, but inspired by somebody in the, the working code discord.

[00:53:56] **Adam:** I set it up so that, the entire application I just did, like on the body tag, actually, it was the, just the, like the main area of the application, like the sidebar and the header were fine, but that main application portion would rotate, somewhere between two and five or maybe it was like two and 10 degrees, but a random amount just like twist the screen just a little bit to like make people.

[00:54:19] **Ben:** transform.

[00:54:20] **Adam:** yeah. Just on that one, Dave, and it would, all the content inside of it and it was working great at first. Right. we got all these tickets that were like, something's wrong. My screen just doesn't look right. And I wouldn't even attach a screenshot or whatever, and I would send them one back.

[00:54:32] **Adam:** I would like,open it up and go into the dev console and take out the transform or just like disable it and take a screenshot of it. I'd be like, it looks fine to me. I don't know. Maybe your monitors tilted or something. and that was fine. Except, the, what was it? It was causing problems with.

[00:54:48] **Adam:** Like the, I think with all of our models and we use models pretty heavily, like somehow it mess up and like it put the dark background that goes up behind the modal in front of the modal or something like that. So you really couldn't do anything once you popped up a modal, like, ah, well, okay. we couldn't have predicted that was going to happen.

[00:55:07] **Adam:** And so I might've been able to fix it, but at that point it was like, all right, funds over, turn it off. and I mean, I later had a discussion with somebody and they were like, it was, I don't know, I don't want to, I don't want to claim anything. It's not, but basically what they were saying is it mounted, it counted as like an accessibility issue.

[00:55:27] **Adam:** Like having the screen tilted was making it more difficult for them to use the app. And I, I get that. I don't want to be a stick in the mud. I don't want to say that they're being a stick in the mud, but at the same time, Yeah, just a little,

## [00:55:39] Accessibility

[00:55:39] **Ben:** yeah. yeah. yeah.accessibility is a, is another one of those things that, I feel like I'm only beginning to scratch the surface on how to not just think about it, but how to build it into my day to day thinking it's a. Especially with a single page application. So, so Invision is primarily a single page application there's so there's other, individual pages, but for the most part, you load a platform and then the platform is what you're in for some extended period of time. And just all the focus and the even like, even just semantic elements, like choosing the right semantic elements that would theoretically help a screen reader and then shifting focus around so that people assisted devices know where they actually are. Oh man. It feels like one of those things that it almost, you can't learn it on your own, the way you can, other technologies, like you really need someone to hand hold you.

[00:56:33] **Adam:** Yeah.

[00:56:34] **Ben:** like

[00:56:34] **Adam:** and I don't want to, I don't want to like victim blame, but I wonder part of me wonders if like, so a lot of these assistive technologies are, based heavily on, or possibly just were last built, before like single page apps and Ajax was a thing. Right. And so they, they just had this expectation of the post and response.

[00:56:54] **Adam:** And I wonder if it's not time for like a new generation of assistive technologies that like, are aware of how single page apps work and like, notice that the document changed and it's like, okay, a modal has appeared and this is, the title of it. And.

[00:57:10] **Ben:** Yeah. Yeah. I mean, I don't know anything about it really. So it's,it's, I've read a couple of books and, and it still feels, 99% foreign to how to do it properly. I just like the biggest thing I do now is I try to use a button instead of link. Just doing an action. And I feel like that's a big step in the right direction, but so much more to go.

## [00:57:35] Patreon

[00:57:35] **Adam:** Okay. So, this episode of Working Code is brought to you by the user experience corporation, who would like you to please listen carefully as their menu options have changed and listeners like you. If you're enjoying the show, you should consider supporting us on Patreon.

[00:57:47] **Adam:** It's the best way to keep the show running. Patreon donations, get put towards things like, our editor and our recording software. So we appreciate all the help that. and special, thanks to our top patron Monte.

[00:57:59] **Adam:** so we have a new patron this week. Coleman's Brando welcome aboard. Thanks for

[00:58:03] **Adam:** your and make sure you join our Discord. and so

[00:58:09] **Adam:** all of our patrons get early access to new episodes and our after show, which, you know what I started thinking. I think either we need to start calling the after show the post-mortem or like the after action review, something like that. I don't know. We'll figure it out.

[00:58:23] **Adam:** but,we keep the mix going and we talk about random stuff.

## [00:58:26] Thanks For Listening!

[00:58:26] **Adam:** and if you're feeling generous, you can leave us a review. You can go to workingcode.dev/review, and that'll take you to the right place to leave us a good old review on that apple thing, wherever your local country is. so we'd appreciate topic suggestions and your questions.

[00:58:40] **Adam:** You can send those to us @WorkingCodePod on Twitter or Instagram. You can join our Discord by going to workingcode.dev/discord. You can, send your questions via text, to WorkingCodePod@gmail.com. Or you can record a voice memo on your phone and send it to that same email address. That's going to do it for us this week.

[00:58:57] **Adam:** We'll catch you next week. And until then,

[00:58:59] **Ben:** sure. Heart matters.
