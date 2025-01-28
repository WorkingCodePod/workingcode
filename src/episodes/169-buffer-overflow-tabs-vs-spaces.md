---
title: "169: Buffer Overflow, Tabs vs Spaces"
description: "In this weeks episode, the crew follow up on last weeks topic of memory management and weigh-in on tabs vs spaces."
date: 2024-03-13
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/169-buffer-overflow-tabs-vs-spaces/id1544142288?i=1000649141155"></iframe>

Several years ago, Stack Overflow noticed a small but surprising [trend within their 2017 Developer Survey data][so-money]. Even when attempting to adjust for several factors, it seems that the programmers who indent their code with spaces (as opposed to with tabs) have a higher earning potential. As an example of programmers who love using tabs, the hosts of the show offer up theories about this strange finding.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[so-money]: https://stackoverflow.blog/2017/06/15/developers-use-spaces-make-money-use-tabs/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/169-buffer-overflow-tabs-vs-spaces.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** Developers who use spaces make more money than those who use tabs. I'll, we'll put the link in the show notes and I'll drop it in our discord here for you.

[00:00:06] **Carol:** Interesting.

[00:00:07] **Ben:** I have a theory. I think it might have to do with psychopathy because

## [00:00:34] Intro

[00:00:34] **Adam:** Okay, here we go. It is show number 169. And on today's show, we're going to follow up a little bit from last week. I got a nice listener comment in our discord, talking about the White House, memory safe languages thing. We thought we'd read that and maybe if there's anything more to discuss there, we're going to talk about spaces, apparently paying more than tabs.

[00:00:52] **Adam:** Uh, and we're going to talk about what's on our work benches. But first, as usual, we'll start with our triumphs and fails. We've got the whole crew here and Ben, it is your turn to go first. My good sir,

## [00:01:01] Ben's Fail

[00:01:01] **Ben:** I'm going to go with a failure. this is like the failure on the back of a triumph, because the triumph is that I've, I've been spending a lot of time learning some new stuff. I've, I've learned a little bit of Svelte. I've learned some AlpineJS. I'm thinking about some new ways of putting applications together, but the failure following that is that All it does is lead to more questions.

[00:01:22] **Ben:** The more I learn, the more I realize I don't know, and I don't know how to put things together. And I've been really struggling with this concept of progressive enhancement. Progressive enhancement's been around, I don't know, for like

[00:01:33] **Adam:** a year or two.

[00:01:34] **Ben:** it's been, it's been around a hot minute. As a, as an idea, and it's one of those things where in the abstract, I think it makes sense, like you, you build something so that it works, it has a basic working functionality, and then you can progressively add additional interactions and additional experiences for browsers and users that can support that.

[00:01:55] **Ben:** And I, and I totally understand that in the abstract, it's all the concrete. What does that actually mean? When the boots hit the ground, questions, Where I just find myself not really finding a path forward. and it's like, take a data grid where I have a search box at the top and maybe some filter dropdowns. The, the kind of base use case would be, I enter some keywords into my search. I do some selects and then I hit submit and it does a full page post back to the server, does the filtering on the server side and then renders the data grid. Now I could progressively enhance that by maybe doing some Ajax fetching behind the scenes so that we're not doing the full page load and maybe adding some sort columns, but I just keep asking myself why it's like, I I'm having trouble finding the use case where it's like, here's a much better user experience with a little effort, or like I'd have to.

[00:02:52] **Ben:** Add a lot of JavaScript to make something really interesting. But at that point, I'm like way out of the realm of progressive enhancement because like, how do I fall back to something that kind of does the same thing, but without adding duplicate effort on the server and the client. And I'm just, I'm just struggling to figure out where the, the, the border line is between useful and low effort versus like just saying, F it.

[00:03:17] **Ben:** I'm going to build a SPA and it's going to be all JSON APIs and template rendering.

[00:03:23] **Adam:** I feel your pain. And I think that you like, you nailed it there with the example. I think that the data grade is sort of the perfect example because there is like, there is no silver bullet fix, right? There's like, you can have a table with a hundred rows or less that you just show and it's static on the page.

[00:03:39] **Adam:** And okay, maybe I want to reorder these or whatever. No big deal, but that's like all of the data that you might want to show on the table. And then like, as the amount of data grows, you start to run into, well, but maybe I shouldn't, you know, we're going to do pagination and so I shouldn't show all the data at once.

[00:03:54] **Adam:** And, but if maybe if there's two or three pages, it might be worth having all the data in browser memory. So I can just real quick client side switch through pages, resort, re, you know, all that.

[00:04:06] **Ben:** Yeah,

[00:04:07] **Adam:** And then, then, you know, and at what, at some point it becomes a better user experience to not make them download all that data and load it like you're saying over Ajax or whatever, and it's just.

[00:04:18] **Ben:** I think that the trick for me is, is the relatively little additional work, meaning I could probably do something where I have a really basic user experience where if the JavaScript failed to load for network reasons or what have you. You'd get an okay experience, but you wouldn't get a good experience.

[00:04:39] **Ben:** And then I could add a lot of JavaScript logic to make something like really snazzy. But then I'm adding a whole lot of extra work to the development process and the JavaScript. And, and at that point, I've, I just, I don't know, I don't know. I'm just frustrated because I keep Googling and watching videos and trying to read articles.

[00:05:00] **Ben:** And it, and I just, I'm not finding anything that's really, I Explaining it very well, or maybe I'm just not searching for the right thing.

[00:05:09] **Adam:** Hey, it sounds like you're describing like a chasm between like simple progressive enhancement and, and like real sophistication, right? Like, okay, making, you can click the table column headers to resort the data that's visible there. That's a simple progressive enhancement. If you don't get it, you don't get it.

[00:05:26] **Adam:** Not that big of a deal. But then when you start to add like filter and sort and drag to, yeah. Mm hmm.

[00:05:33] **Ben:** Like take a pattern. So I have a data grid and maybe I want to edit one of the records. So I click an edit button and maybe the base experience is that it takes me to a completely separate page. That's like a detail for that row that gives me, you know. Headings and fields. And so I can edit that data and I hit save and I come back to the data grid, but then maybe I want to progressively enhance it.

[00:05:51] **Ben:** So instead of taking me to a totally different page, maybe it opens it up in a modal window, or maybe it expands the row and gives me the form in line in the table. And, you know, this was sort of my dream of using Hotwire and Turbo from the Basecamp guys, because that's a lot of their demos were kind of like that.

[00:06:09] **Ben:** But then you start to dig into how that's actually implemented and it gets really, really complicated. At least to me, it's like, you really have to start changing the way you wire things together and you're transcluding views into other views. And then you're conditionally hiding CSS if it's being included versus it's the base experience.

[00:06:28] **Ben:** And it's one of those things where like, yeah, I could get it to work, but it doesn't seem like it's easier.

[00:06:35] **Adam:** hmm.

[00:06:35] **Ben:** all for this. I don't know. I'm just frustrated. That's my failure. So that's me. Carol, what about you?

## [00:06:43] Carol's Fail

[00:06:43] **Carol:** I'm going to join you there on the, failure train tonight. Y'all and your time changes, you really suck. I just wanna say that, cause we don't change time where I'm at, and little did I know, I really enjoy that. right now, I had to get up very early this morning so that I could be on a call and working at 6am, which normally I'm working by 630, but this meant like, I need my coffee processed by then and my brain needs to be on and there are going to be Fridays now where because I'm three hours behind instead of two that I have to start working at four so we can do a 7am, you know, release, which means up way early.

[00:07:23] **Carol:** And I just want to say time change sucks. So you, you time change people who like it, go enjoy it somewhere else. Yeah.

[00:07:32] **Ben:** The frustrating thing for me is that the, the fall back, which is where we gain an extra hour of sleep and the spring forward, which is what we just had, which is where we lose an hour of sleep, you'd think that one would be much harder than the other. But they both destroy me

[00:07:46] **Tim:** Mm-Hmm.

[00:07:47] **Ben:** for, I don't even understand it.

[00:07:48] **Ben:** Like, how does getting an extra hour of sleep making me tired in the fall? That makes no sense, but just both of them, I'm tired all week.

[00:07:56] **Tim:** Yeah. It's been rough.

[00:07:57] **Carol:** Well, that's me. What about you, Tim?

## [00:08:00] Tim's Triumph

[00:08:00] **Tim:** Well, unlike you two losers, I'm going for a triumph. we got our bonuses today, or we got what we're told was gonna be our bonuses. No, I can't disclose financial information or things like that, but we did, we did, we did really, really good. This was the first, first year that there was another company that we're kind of, we're rolled in with.

[00:08:21] **Tim:** And they were kind of dragging us down. So we're, we're being measured on our own, which is, I mean, the bonus is supposed to be, you know, encouragement to motivate you. so the best bonus that I've ever gotten my entire time working in the 24 years

[00:08:38] **Carol:** Heck yeah. Yeah.

[00:08:41] **Ben:** Yeah,

[00:08:44] **Tim:** basically a third of my salary.

[00:08:47] **Adam:** Wow.

[00:08:48] **Tim:** And one, one lump chunk.

[00:08:50] **Carol:** Yeah. Awesome.

[00:08:55] **Tim:** Oh yeah. We'll probably talk about that later, but I have to give you guys an update on the, on the testicles.

[00:08:59] **Carol:** Well, congrats to you, Tim. Cause I know like you've been working hard with some contracts and legal things and doing a lot with the system and sales. So it's not, it's not easy to get there. So congratulations to you and your team. You

[00:09:17] **Tim:** make it happen. So, and they should be rewarded for that. And as it was frustrating for the past few years where it's like, well, if we were on our own, we, we probably would have got a much bigger bonus, but we're not, the other company's dragging us down.

[00:09:29] **Tim:** There's nothing we can do about that. So it was kind of dismotivating, but yeah, I got to message everyone and say, guess what, guess how much you're going to get? Like how much? Like this much? It's like, holy moly.

[00:09:42] **Adam:** Wow.

[00:09:45] **Carol:** can buy two tacos at dinner tonight.

[00:09:47] **Tim:** right.

[00:09:49] **Ben:** Two taco Tuesday. Love

[00:09:51] **Tim:** That's right. We did have tacos tonight, but my son, my son normally is like a picky eater. Like he's a scared eater and he's like, you know what? I think I'm going to try, cause he only put like meat and cheese on it. And he never gets excited. My daughter loves tacos, like the hard shell tacos. And he's like, I'm going to try a little something.

[00:10:09] **Tim:** So he put, you know, cilantro and lettuce and cheese and some,

[00:10:13] **Ben:** move.

[00:10:14] **Tim:** and I love cilantro and

[00:10:15] **Adam:** I like it

[00:10:16] **Tim:** some, some, some salsa, put it all on there and he's eating. He goes. Oh, wow. Wow. I've been missing out all these years. Like we told you, he, he gobbled down two of them faster than I could. It's like good for the third. So, um,so anyway, that's me.

[00:10:32] **Tim:** How about you, Adam?

## [00:10:34] Adam's Fail

[00:10:34] **Adam:** Oh, I'm going to round it out with, our third fail. I have jet lag like, whoa. So we are recording on Tuesday. I, so, you know, I just got back from that cruise. I was gone for a whole week. and

[00:10:46] **Tim:** How was it?

[00:10:47] **Adam:** the cruise was excellent. We had so much fun. I was a little anxious going into it because I don't know if I mentioned on the show, like we flew out.

[00:10:54] **Adam:** To Los Angeles the morning that we're supposed to leave the port and we would land with approximately four hours to make it from LAX to Long Beach, which is where the port was, which is like, you know, 45 minutes to an hour with traffic with typical traffic there. So we weren't too worried about traffic, but what we were primarily worried about is like a delayed or canceled flight.

[00:11:16] **Adam:** If that had happened, we would have been completely screwed. And fortunately, no issues. we made it there just fine, just fine. And, everything went well. We had a great time. what was difficult about it though, was coming home. so we, you know, on the whole, during the cruise, you use what's called ship time, which is, you know, they, there's a clock channel on the TV.

[00:11:37] **Adam:** It tells you what time it is on ship time. You can update your phone or whatever. and for the most part, it's whatever time zone that you are in in, or in some cases they just say, okay, ship time is whatever the time zone was that when we, like, when we left our original home port, right? So we left from Los Angeles, that would have been Pacific time.

[00:11:56] **Adam:** This ship or this cruise, we did go back into what would be U. S. mountain time. We were down in Mexico, but, we did come back East enough to go into mountain time. And ShipTime did go with it. So we, you know, we, we flew to Los Angeles. We ended up in Pacific Time for a few hours, actually for like a day.

[00:12:13] **Adam:** And then the next day, we were in Mountain Time and we were in Mountain Time for like three or four days. And then, that we have like a day at sea on the way home. And, and for that, we switched back to Pacific Time and then, we get off the boat and we fly home and so we're flying Pacific to East coast.

[00:12:33] **Adam:** So we're, you know, we're, I guess, losing three hours to that. Is that how that works? Yeah. and then, it also happened to be the night of daylight savings time.

[00:12:42] **Tim:** Oh, I

[00:12:46] **Adam:** landed at like 1155 by the time we got our bags and got home, it was like, we walked in the door at like 1 45 AM. So we got home just in time for the clocks to change.

[00:12:57] **Adam:** And yeah, it was just off. I was like, you know, you guys were talking about how, daylight savings can kind of mess with you. I have never felt it as bad as I did this year, like flying from the West coast to the East coast on the night of daylight savings was. The worst,

[00:13:12] **Ben:** Hmm.

[00:13:14] **Tim:** bet.

[00:13:14] **Adam:** I'm still struggling.

[00:13:16] **Tim:** that's crazy.

[00:13:17] **Ben:** you see any, interesting marine wildlife?

[00:13:21] **Adam:** we had an opportunity or, or we thought we were hoping for an opportunity to see some humpback whales in the Gulf of California down there. we didn't, although we did see a sea lion. I don't know if I believe it, but the, the guy that showed us, we were on this little, like little speed boat to go from the ship over to our excursion.

[00:13:41] **Adam:** And we stopped in the middle of the Bay and he goes, you know, we, I think I saw a whale, we're going to wait here and see if it pops up. And it was, we took off after like 10 minutes of waiting to see if it came around. And then, on the way back, I don't know, whatever, same, same day, same Bay, we saw, we stopped again and there was a sea lion just kind of like doing like an otter, right?

[00:14:02] **Tim:** Just like kind of laying on the surface of the water. I got like a couple of fins in the air, just chilling. He's waving at you.

[00:14:10] **Adam:** just chilling, getting some sun on his flippers. and the guy said that it was a pretty rare to see them do that. I don't know how much I believe that, you know, it might've been just like a, a thing to make us feel good.

[00:14:20] **Adam:** So we'll leave him a good review or something. but, it was fun. It was cool. Got some pictures.

[00:14:24] **Ben:** All right, cool.

[00:14:25] **Adam:** We had a great time, but just the, oh man, I am, I'm like dead to the world. I can't think I barely, the first day back at work, I barely just like caught up on all my notifications, email and discord and everything.

[00:14:37] **Adam:** And like, that was 90 percent of the work that I did on Monday and today was better, but I'm still struggling, not, not anywhere near back to a hundred percent. I changed my name in our company discord to, Jet lagged and over caffeinated.

[00:14:53] **Ben:** That's how I'm feeling.

[00:14:55] **Carol:** the big question is, did you come back and your application still work?

[00:14:59] **Adam:** yes and no. So, my stuff is fine, but,so somebody, I mentioned, you know, we've got this SvelteKit app that we're working on, and one of my teammates has been working on a GraphQL server. And how like, I think I talked a little bit about how like, he's kind of doing a whole sort of like, client for it as well built in, and he's using the same Zod schemas and types to, to make it easy to like, get a fully typed response from database all the way down to client.

[00:15:28] **Adam:** and he had that sort of working in theory in his project, but he's using Bun for the server so that he doesn't have to compile the TypeScript, before he can run it on Node, right? Just Bun will just run TypeScript. and then in order to be able to export a client that I could then import into, my app, he, what did he use?

[00:15:48] **Adam:** he used ESBuild to compile that to, ESM and CommonJS so that I could import it into my app. And for whatever reason, when he did that. It like, it causes build errors in my app now. So, but so yeah, so we just kind of punted on that one. Right. So just kick the can. it was like the client was like one file with maybe 50 lines of code in it.

[00:16:12] **Adam:** I'm just like, I will copy that over to mine. We won't get the fully type safe thing, but I'm just going to like build my own schemas in the client for now.

[00:16:19] **Carol:** We'll work around it.

[00:16:20] **Adam:** Yeah, and you know, hopefully in the coming weeks, we'll get that sorted out. But in the meantime, I'm just going to keep my build working so that I can work.

[00:16:27] **Adam:** So, yeah, so that actually, so that's a good way to like round out mine, but I really want to ask you, Carol, last week you came back from vacation and your app was broken. I want to, I want to hear an update.

[00:16:37] **Carol:** Well, let's get it right. I didn't come back from vacation. I came back from being very sick,

[00:16:43] **Adam:** That's right.

[00:16:43] **Carol:** very sick to then coming back to my application would not run at all. So if you missed last week's episode, it was kind of the same issue I had before where we have a connection strings in our application, like a lot of people do, and they point to different places.

[00:16:58] **Carol:** So like we have connections strings for our local DB. And then there's connection strings and the, the dev configs that point to the dev databases. Well, ours were all set up using local DB, which is, like a feature of SQL Express and with the update that we need for SQL 2020, SQL 22 does, developer edition doesn't support local DB.

[00:17:24] **Carol:** But because of one of those wonderful White House initiatives that we talked about last week, all of our data has to be stored. Encrypted. So all of our backups are encrypted. So whenever I want to restore my dev database, it is now an encrypted database, which LocalDB does not support. Unencrypting, or unencrypting is not a thing.

[00:17:52] **Carol:** So decrypting, that's the correct word. So LocalDB doesn't support decrypting. so whenever you try using it, it's like, oh, we can't do anything with this database, you're going to have to get the right version of SQL. So I had gotten everything working previously, but I came back and all of this happened again. Well, it turns out this whole time I've had LocalDB running and there are some places that were stored in secrets inside my, like Local secrets, like NET secrets, that were pointed to local DB and I didn't know it until we updated the, consumer project and all of a sudden it started using secrets and now these secrets were pointing to local DB.

[00:18:34] **Carol:** So little did I know, I actually wasn't using the right database for a few different connection strings, so I now have my app. Point it to the new version, which requires like 36 file changes every time I make a code change. But we are working with our DBAs to figure out if we can not encrypt the database that we are going to be restoring for backups, or we're going to actually check in by changes.

[00:19:00] **Carol:** So everyone's gonna be forced to update the SQL 2022, who's currently running local db because technically if they're running local db. That's a problem because they're running the databases that were restored before the encryption was mandated. So it's basically going to open up the everyone has to now switch to the new version.

[00:19:21] **Ben:** Plus it's something like LocalDB and I don't know anything about the NET world, but if you want developers to be running roughly what is in production, is LocalDB production like enough?

[00:19:34] **Carol:** It was until, it's yes, yes and no. So yes, it was until like this last update that we made. Now we really would like for people to be running the developer edition because it does more closely mimic what our production settings were and what would be happening with our data.

[00:19:52] **Ben:** Nice. When you have a, an encrypted database or like an encrypted at rest database, maybe,

[00:19:58] **Carol:** That's what it's our, it's EAR. Yep. Encryption at rest.

[00:20:01] **Ben:** if, if you like right click on the database in your database manager and you do something like dump to SQL, can it actually write, will it write like regular SQL statements or does it write some sort of special encrypted dump file?

[00:20:16] **Carol:** I've never tried that. It generates SQL for me. Like, so if I do, like the right click on the tables and I say generate to create script, it just generates it like normal SQL. I've never tried the dumb

[00:20:28] **Ben:** of regular insert statements.

[00:20:30] **Carol:** Yep, but the only way you can get to it is if you actually have your certificate installed.

[00:20:35] **Carol:** So we actually have to get the server certificate that was used to create the encryption and install that on our, on our local, like, instances of SQL to use the data.

[00:20:47] **Ben:** Well, glad you got it working.

[00:20:49] **Carol:** Yeah. Thanks. Yeah, me too, sort of. I mean. There's going to be 36 file changes checked in and everyone's, not everyone, half of the team's probably going to yell when they realize that they have to now install SQL 2022.

[00:21:03] **Adam:** But then it'll just be solved, right?

[00:21:05] **Carol:** Yeah, it'll be solved.

[00:21:07] **Ben:** And the 30s,

[00:21:08] **Carol:** We think it'll be solved. It was working before. Yeah. What are you going to say, Ben?

[00:21:15] **Ben:** 36 files. I was curious if that's, you're saying that you'd have to do that every time you make a change to your database. Is that because of some sort of like a code generation thing?

[00:21:25] **Carol:** Nope. So that's because our monolith has 50 projects in it. So there's 36 config, config and web app files, or web config files that have to be changed to get that connection string updated. And not everybody would need to change everything cause a lot of people don't run all the projects. They only run a few that are just tightly tied to what they're doing.

[00:21:45] **Carol:** But because of the work I'm doing, I'm having to run several of them. So it's just easier to do a mass find and replace in all of them than only do mine.

[00:21:54] **Adam:** Word up.

[00:21:58] **Carol:** But thanks for asking.

[00:22:00] **Adam:** Yeah, I'm glad it's at least on the path to fixed.

[00:22:03] **Carol:** Yeah. Thanks. Yeah. Yeah. It's

## [00:22:06] Follow Up on Last Weeks Episode

[00:22:06] **Adam:** Alright, well then let's move on to, a follow up from last week. so we got this awesome comment from somebody who I would say is smarter than those of us here on the podcast. You're, you're free to disagree.

[00:22:18] **Tim:** Nope, I agree.

[00:22:20] **Adam:** so Brian, aka SpiffyTech in our Discord, Left a comment after last week's show, and I'll read it here for no particular reason, and then we can discuss.

[00:22:29] **Adam:** So here, Brian says, Adam basically got it on the show.

[00:22:32] **Tim:** Hold on, wait,

[00:22:33] **Adam:** ha ha ha!

[00:22:34] **Tim:** So that's exactly why you want to read this comment. Okay, I see how it is.

[00:22:38] **Tim:** I don't know what you're talking about, sir. Proceed.

[00:22:41] **Adam:** okay, yeah, yeah. Just in case anybody in here got interrupted, let me start over. Adam basically got it on the show. C, C and Assembly are the big languages today that aren't memory safe. Objective C, maybe. Not sure. For a long time, we didn't have a good alternative for a lot of cases.

[00:22:58] **Adam:** Some languages have gotten very fast, but not at the limit fast, and they frequently paused execution to do garbage collection. With Rust getting serious traction, that's finally changing. Memory safety gets attention because something like 70 percent of all vulnerabilities are tied to it. And the scope of impact is often unlimited, meaning that the attacker gets to put their code on your computer and do literally whatever they want. An emblematic example, that's a SAT word for you, an emblematic example is the buffer overflow. The programmer allocates n bytes of memory for some data, then inserts data the program received from disk or network. The language doesn't automatically check that the stored data fits the allocated space, the programmer has to do that themselves.

[00:23:38] **Adam:** If they slip up. An attacker can send extra malicious data, and the program just stores it all, overwriting nearby memory. Often the attacker's extra data is machine code, which the attacker tricks the victim's computer into executing. So that's a, a fantastic explanation of what a buffer overflow is, which I know we mentioned, but I, I, I kind of had a vague idea that that was kind of, you know, what was going on, but to have it spelled out so clearly is wonderful.

[00:24:05] **Adam:** Thank you, Brian. And then he says, Another thing, allocating memory and forgetting to set it to an initial value so it holds whatever random bits were floating around in RAM at that location, based on whatever the computer's been doing, which of course an attacker will find a way to control. The, okay, end quote, right, so we can

[00:24:24] **Carol:** And thank you. And thank you. Yes.

[00:24:26] **Adam:** It's good, very well said, Brian. Good job. thank you for that. it's educational as well as, perfectly ego stroking.

[00:24:34] **Tim:** Yes, exactly. Confirming you're right. Adam said it best.

[00:24:40] **Carol:** So I don't know why, when you're reading all of this, all I can think about are the days back at a previous job, where I would spend lots of hours inside Fusion Reactor constantly going, why am I running out of memory? Why am I running out of memory? Like what's eating all of my memory? And I know that's not really like, this, This isn't really that, but it just constantly reminds me of the things that eat up resources and never get wiped out, even if your application is writing it.

[00:25:14] **Adam:** Can I, can I do a quick side tangent on, on garbage collection?

[00:25:17] **Carol:** Yes, please do. Cause they're fun. So much

[00:25:20] **Tim:** Well, before, before you do that, what I think of is, is, I don't think necessarily the movie, The Martian, but the book, The Martian, when, when he got the rover and he was wanting to make it, the camera moved to do hex decimal for communication, they, they sent him a machine language, machine language code program.

[00:25:39] **Tim:** And he had to basically upload, he basically did what he did. It was a, a buffer overrun. In order to, in order to, to, and he described it and I was like, Oh, that's pretty cool.

[00:25:49] **Ben:** That's

## [00:25:49] Garbage Collection

[00:25:49] **Tim:** So garbage collection,

[00:25:51] **Adam:** Okay. Yeah. Yeah. So we just ran into this at work. So it's, it's funny and interesting the way you can run into weird edge case problems. So we have a couple of tables in our databases for certain customers that have a ridiculous amount of data in them, like maybe I would say dozens of millions of rows, for some customers. And. So in those cases, you run into certain SQL that is not performant enough at that scale. And so for us, for example, you know, if you're going to send an email, there's, how do I explain this succinctly? Sometimes we might want to delete, the initial stubs that were created the last time that you tried to stub this message. And, so you would think, you know, just delete from table where message ID equals one, two, three would be the thing that you would do. But as it turns out, we, through experimentation, we have found that it is much faster to get the list of IDs and iterate over that in a loop and, and do a single delete at a time.

[00:26:51] **Adam:** I don't know if that's because of database index rebuilding or, or what. Right. Or some sort of weird locking thing. So deleting them one at a time. Is faster, period, end of statement. However, our, our initial approach to accomplish that was, let's say, short sighted, I don't know. what we did was like a CFML for loop, and loop over the list of IDs and, and run like a query execute to, to do that, and what that ended up doing is causing the server to crash because it was doing, you know, 300, 000 query executes. Like, as fast as it possibly could, and that was causing, like, garbage collection and stuff, and we basically, we figured that out by, instead of one query execute per query, we started doing multiple statement queries, right, like generate 500 delete statements, semicolon between each one. Send that in one query execute and that solved the problem and it brought it down from crash the server down to takes 12 seconds or something, you know, so, that was just a fun little like dumb thing.

[00:28:04] **Ben:** That's cool. I know we've talked about at least the fact that you can do a limit when you do an update, but at least in MySQL, you can do a limit with deletes as well. So you could have something where you say, delete where customer ID equals this, order by something, limit a thousand, and essentially just be deleting batches of a thousand until you have none left, which is,

[00:28:26] **Carol:** Does it automatically iterate over it? Or do you have to tell it to iterate over it till it's finished? Like,

[00:28:31] **Ben:** No, no, you'd have to make multiple calls to the database, but you can

[00:28:34] **Adam:** like a while, uh,

[00:28:36] **Ben:** Yeah,

[00:28:36] **Carol:** Yeah.

[00:28:39] **Adam:** I believe, so this is something that they discovered and fixed while I was on vacation. So I don't have a hundred percent of the details. thankfully I was able to be totally.

[00:28:47] **Carol:** you leaving for them to fix it. Yeah.

[00:28:49] **Adam:** It's like, wait till Adam leaves and then stuff can break. but, I believe that they tried the delete with a limit as one of the experiments, but this ended up being faster in our case for, for this data.

[00:29:02] **Ben:** There is some strange, I can only speak about MySQL and I'm not a database administrator, so take this with a grain of salt. But I do feel like I have run into issues where it does do some, not like table level locking, but like index level locking when you do certain large operations.

[00:29:22] **Adam:** There's row level locking. I don't know about index locking.

[00:29:26] **Ben:** There, I think there are some bizarre edge cases where you do something and it feels like it has to lock an entire index. For a particular value in case it has to generate a primary key during that operation and it can't lose track of like which primary keys are available. I could be making that up, but I'm pretty sure I've run into that where there's weird contention, unexpected contention.

[00:29:47] **Adam:** Could be, I don't know, it's all kinds of weird stuff. And like you said, you know, we're not DBAs. We, we are a team of all highly experienced senior developers and none of us have specialized in that. And so our approach is try a bunch of different stuff until something works well and go with that.

[00:30:05] **Ben:** Yeah, before

[00:30:07] **Tim:** it doesn't lock the server too long.

[00:30:08] **Carol:** It's actually funny you said that. Working through all of these like weird SQL issues I had, I spent quite a bit of time, on like one afternoon or one morning actually with my DBA and he was like, man, you sure do know a lot. I'm like, yeah, cause this is the only job I've ever been given a DBA. So I know it's just enough to get myself in a lot of trouble and sometimes how to get myself out of that trouble.

[00:30:34] **Carol:** You do the rest.

[00:30:36] **Adam:** man. When, when we just, I mean, I know we're like way down on 10 to central here, but, we just, I don't know, within the last year, upgraded to MySQL 8, which gave us, CTEs, common table expressions. And oh my god, they are amazing.

[00:30:48] **Carol:** They're like a dream. They're the best thing ever. G

[00:30:51] **Ben:** This is, this is where you like save a query kind of as a variable, and then you can query that variable kind of a

[00:30:57] **Adam:** Yeah, yeah. So the syntax is like, with variable name as

[00:31:00] **Carol:** L.

[00:31:01] **Adam:** query in parentheses, and then you can have multiple, right? You can do, and they can reference each other, or you can reference previous CTEs. So, you know, with A as thing, with, and then comma B as thing, and B can reference A, and then you've got your, like, final query can reference A and B.

[00:31:16] **Adam:** And I've done,

[00:31:17] **Carol:** select this from my CTA or CTE. It's perfect.

[00:31:21] **Ben:** That is cool. I can simplify some stuff.

[00:31:23] **Adam:** oh yeah, and I've, I've done things where it was like, okay, this, this query that generates a report crashes the server and you can, like, if you're smart about it and spend enough time staring at the SQL editor, you can get it down to like near instant running. It's amazing.

[00:31:38] **Tim:** They are pretty cool.

[00:31:39] **Adam:** So, okay. that's,

[00:31:41] **Carol:** Brian. Great topic.

[00:31:43] **Adam:** yes, yes, yes. And I'm glad that we were able to, to share that, with the listeners. so we did kind of talk about your database thing, Carol. and as we were going through all of this, previous content on the show,

## [00:31:54] Tabs vs Spaces

[00:31:54] **Adam:** I, I had pulled up this article, from the Stack Overflow blog about developers who use spaces make more money than those who use tabs.

[00:32:02] **Adam:** Because this was a recent topic of discussion in our Discord, you know, this was like within the last 24 hours, people have been chatting about this article, I just assumed,

[00:32:10] **Tim:** Monte posted it initially.

[00:32:13] **Adam:** and you know, I'm great. It's great. I'm glad that people are having the discussion, but I just assumed that it was like a recent post, and, and it is not.

[00:32:23] **Adam:** It's from 2017. Um,Which is like two lifetimes ago or something.

[00:32:28] **Carol:** the post call again?

[00:32:29] **Adam:** Developers who use spaces make more money than those who use tabs. I'll, we'll put the link in the show notes and I'll drop it in our discord here for you. so, and basically if I can summarize the blog post, I, my understanding as I was thinking about this as a, as a recent article was like many years ago, somebody, StackOverflow developer survey, they had found like, okay, people who they'd found a correlation between people Use spaces or prefer spaces versus tabs because they're heathens and they're wrong. And, and people who are more highly paid, they found a correlation between those two. And my, of course I didn't read the article. Why would I do that? what happened in my brain was like, okay, and, and I, I kind of skimmed and, and from between skimming the article and the conversation in Discord, I was like, okay, they, you know, refined their, their survey and a more recent survey happened and they have, Tried to control for different variables, which they did, was in their article.

[00:33:29] **Adam:** They did try to control for, okay, are you a Python user where you are kind of forced into using spaces? Or are you in another language where you can choose tabs? Or do you, are you forced into tabs or whatever? So they can try to control for all these different things. And apparently to the best of their ability, they were still not able to find any, way to say this is the cause for, the correlation, right?

[00:33:55] **Adam:** So basically, I guess they're not saying there's causation, but. That can't find any other explanation.

[00:34:02] **Carol:** Interesting.

[00:34:03] **Ben:** I have a theory. I think it might have to do with psychopathy because so, and I'm, I'm teasing, but I'm also not teasing, which is that if you look at, or from what I have heard on various radio pieces, radio news pieces, there is a disproportionately high number of psychopaths at the C level suite within organizations.

[00:34:29] **Adam:** That doesn't surprise

[00:34:30] **Ben:** yeah, it, it, it doesn't feel surprising because it's a very specific type of personality.

[00:34:35] **Adam:** As somebody at the C level, that doesn't surprise me. Hang,

[00:34:41] **Ben:** You know, and it's not like all of them are, are, are psychopaths, but a,

[00:34:45] **Tim:** Just the good ones.

[00:34:48] **Ben:** you compare that to other groups of people within organizations, there is a higher percentage, apparently this is what I've heard because it takes that kind of personality to be very driven and probably to make very hard choices and probably to make very hard choices at the expense of other people. going back to the tabs and spaces. I could very much imagine that the people who are willing to subject a team to spaces at their own whim are also the people who are probably willing to put themselves out for promotions, are probably willing to ask for promotions, are probably willing to move up the ladder at greater cost to those around them.

[00:35:29] **Tim:** They're so hateful. They're like, you look at my spaces, just look at them.

[00:35:33] **Ben:** It's not even like a hateful thing. It's like, well, this is clearly the right way to do it. And that's how we're going to proceed.

[00:35:38] **Carol:** me. This is what's happening.

[00:35:39] **Ben:** the way I see the world. And I think people,

[00:35:42] **Adam:** hang on. I need to indent some code. I

[00:35:49] **Ben:** so, so that's what, that's my guess is that there is it's, and I'm not saying that all people who use spaces are psychopaths. I'm saying that if you compared psychopathy in the two, I would wager that there are more psychopaths in the I use spaces than the I use tabs. Yo,

[00:36:12] **Adam:** to be able to get the stack overflow guys to put that on their next developer survey.

[00:36:16] **Carol:** How

[00:36:17] **Adam:** Do you take anti psychotics?

[00:36:19] **Carol:** are you psychotic?

[00:36:21] **Tim:** I mean, if you looked at the salary references, you should've told you it was old. I mean, their salaries are like starting at 25, 000 going up to, yeah, like person 15. Psychopathy.

[00:36:37] **Adam:** Skim, skim, skim. Okay. Have an opinion. Done.

[00:36:42] **Carol:** It's interesting that, like in the US, so it, it breaks it out by country, right? So I guess I shouldn't say in the US. It's interesting that overall, if you use both, you're lower than if you choose one or the other. And I feel like people who don't care typically don't make as much money. So maybe you're right.

[00:37:01] **Carol:** You're like, whatever is in the files, what I'm going to use. Me, I'm one of those people that. I don't have to worry about it here cause everything is tabbed. So I'm great. I have no issue, but, at my previous job, I used to open the file and if the files I had were spaced, I would change the little input in the bottom of VS Code from space to tabs, open the file, hit tab one tab, like one, like tab it over once, check it in, do a PR for that and say, it's just changing spaces to tabs and then go do my work.

[00:37:33] **Carol:** I hated it so much.

[00:37:36] **Adam:** I like that you went as far as doing a specific PR for it because I would do that, but only as a single commit and, and it, it does dirty up the whole. Yeah,

[00:37:47] **Carol:** then someone's looking at it and they're like, wait, where's the line you actually changed? Because if they don't have that in there, like, Bitbucket or I can't remember the one we were using at the time, doesn't matter, there was an option in there that said ignore white lines, right?

[00:38:02] **Carol:** So some of them don't do that. So then you end up with the, Oh, everything changed in this file. Yeah. Yeah.

[00:38:10] **Adam:** when that would happen, I'd be like, okay, only look at this one commit, right? There's two commits. One of them is just whitespace. Click on the other one. If there was a bunch, then I would be like, yeah, sorry. I fixed a bunch of whitespace. Sorry for your luck. Turn off the, turn on the ignore whitespace changes option.

[00:38:25] **Carol:** I'm straight up a full PR. Go ahead and merge that in.

[00:38:30] **Adam:** Fixing your psychotic choices.

[00:38:31] **Carol:** Yeah.

[00:38:32] **Adam:** I'm the kind of, I'm a little sad that I discovered that this was from 2017 while we were on the show because I, like I, I introduced it at the top of the show and I was all ready to like talk about it and now like I feel like the, the wind has been sucked out of my sails.

[00:38:46] **Carol:** Listen, it's a retro podcast tonight, guys. It's okay. Retro's the new in. You're, you're fine.

[00:38:52] **Adam:** Breaking news from 2017.

[00:38:55] **Ben:** Not, not to harp on just the superiority of tabs, but. One of the, I think one thing that showcases it so well is that on GitHub, and I think this is sort of a web default and GitHub has brought that default forward, is that a tab is represented as four spaces, sorry, eight spaces, but you can go in with CSS and you can set tab size to four if you want to decrease it, I suspect, and I've never questioned anybody about this, but I suspect that GitHub has purposefully left it at eight spaces.

[00:39:30] **Ben:** So that if you have a file that's mixing tabs and spaces, it'll show up as four spaces. When they're spaces and eight spaces when it's a tab. So you can much more clearly see that, Oh, somebody screwed up. They mixed spaces and tabs, which again, it's just showcasing the power of tabs because you can literally customize them to be what you want.

[00:39:52] **Ben:** And I feel like once that becomes part of the argument, it's hard to understand any other argument. Yeah, exactly. Other than psychopathy,

[00:40:03] **Adam:** Yeah, I had totally forgotten about that CSS setting. And I just put on my to do list to go update that in the design system to change our tab width. You know, it's not like we print out, pre blocks of code in the application that often, but it does like every now and then I'll drop one in a ticket or something and, that's nice.

[00:40:20] **Ben:** totes. And just as a pro tip for anyone using GitHub, in case this is not Widely known or not known by anyone in particular. If you're looking at a PR in GitHub, there is an option, a little config dropdown, and in that you can turn off white space diffing. So if. You have a kind of a, yeah, a Carol situation where she, she blew away all the spaces and then made one line change.

[00:40:42] **Ben:** you can have it show you only that one line of change, which has been super, super helpful.

[00:40:49] **Carol:** But sometimes you want that on so you can see who it is that's committing the spaces back to your project so you can ridicule, like ridicule them in public.

[00:40:58] **Adam:** I, so I have, whitespace characters turned on in my, in, in VS code. So I, they're like very low contrast and just like dots or dashes. And, and I also have the, I think it's called get lens plugin installed. So like, if I have my cursor on a line at very low contact contrast at the end of the line, it says, you know, last changed three weeks ago by, you know, I don't want to, sorry, I was going to try and say somebody's name and I was

[00:41:22] **Carol:** let's say Ben. Ben did it.

[00:41:24] **Adam:** bye, bye Ben.

[00:41:25] **Adam:** and so that, and then I'll go send him a private message. Like, Hey, by the way, I found another place where you inserted a bunch of spaces to indent, reminder tabs, or like I can forgive. Accidentally creating a whole file with spaces. Like, you know, you forget that your editor's on that setting or whatever.

[00:41:43] **Adam:** What I, what really gets my goat is when you have a single line that has a mixture of tabs and spaces, and it's not done for indentation plus align, right? Like I'm, I'm on the indent tabs or indentation spaces for alignment team, right, indent, and then if you want to like line up with the line above, cause you're continuing the line or whatever, then use spaces because you're Doing single characters.

[00:42:07] **Adam:** Anyway, I'm like way off the rails here.

[00:42:10] **Carol:** for anyone listening that doesn't do technology, this is your confirmation that we really do care about tabs versus spaces. This isn't just like a thing you've heard. It can go on for hours.

[00:42:23] **Tim:** It's for real, I think we may have mentioned it way back, but one year at the Adobe Cold Fusion Summit, they had the, the writer from Office, no, Silicon Valley was there, right. And he's doing a little speech and he was really hilarious. He was super funny. He's like, you know, so been around, he's talking about all these other really great Shows and scripts he's written.

[00:42:45] **Tim:** He goes, and then I do Silicon Valley. And now I'm talking to a bunch of neckbeards here in Las Vegas. But, at the end, he's like, so the tabs versus spaces thing. Does that, is that really such a big deal? And the whole audience just exploded. He's like, all right. All right.

[00:43:01] **Carol:** My bad, bro.

[00:43:05] **Adam:** Yeah. That was part of what made the show good was like the touches of realism in it.

[00:43:08] **Tim:** Yeah, sure.

[00:43:11] **Adam:** Personalities. okay. So let's try to get this train back on the, on the tracks here. I know we were trying to do a relatively short show because, because of the time change and how we were all dragging, booty. And, so I guess let's, let's just kind of round this out with a quick discussion of like what's everybody working on that's interesting.

## [00:43:31] Tim - Rogue Database

[00:43:31] **Tim:** I'll go first. I got a quick one. So in our production database, which is our, in our PCI environment, I'm looking at all the databases and I see a database called SADJDKLGI, like a cat walked across the keyboard and I did not create it. I'm one of the few people who ever messes with this database and I immediately

[00:43:55] **Carol:** Did you pull, did you pull like the ethernet out of the box? You're like

[00:43:58] **Tim:** yeah, I was like, turn the, pull the cables out.

[00:44:01] **Tim:** I'm like, we've been compromised as somebody get in. And so I sent a message to our DBA and I'm like, Hey, I sent a screenshot. I'm like, I didn't create this database. Where did this come from? And he's like, Oh God. Oh God. And so he starts talking to his team and it turns out someone in our operations team was testing our replication.

[00:44:21] **Tim:** And so he just wouldn't created a database to see if it would create the database on our replication side and then didn't delete it.

[00:44:28] **Adam:** Mm hm.

[00:44:29] **Tim:** I didn't tell anybody. I was like, dude, you gave me a heart attack. I thought we were compromised. I thought the whole business was going to go down. It's like, you know, we don't have credit card data in there, but if there's a data breach, it's like, we got to tell everyone.

[00:44:43] **Tim:** And then everyone assumes the worst. I'm like, if someone has the ability to create a database, That is really, really, really, really bad. So turns out it wasn't that big a deal. I'm like, please delete it next time. Don't do this to me again.

[00:45:00] **Carol:** But here's the thing, if I were going to compromise your database, I wouldn't name it that, right? Like I would name a database that was like account users or logins or something that you would just glance over and never think about twice. I wouldn't name it something silly.

[00:45:16] **Tim:** Schema underscore data. You're like, Oh, it must be a

[00:45:19] **Carol:** Yeah, it's just a system thing.

[00:45:21] **Adam:** testing underscore replication. How about that?

[00:45:24] **Carol:** Yeah, probably wouldn't have even questioned that one.

[00:45:28] **Adam:** To,

[00:45:28] **Tim:** No, I would have.

[00:45:29] **Adam:** To steal a joke from Jon Stewart, I think my pants just their pants.

[00:45:35] **Carol:** Yeah, you had me on pins and needles here. I'm glad there was nothing wrong, but I would have been freaking out with you.

[00:45:41] **Tim:** Oh, I was, I was. And the DPA is like, good catch. I'm like, yeah,

[00:45:46] **Ben:** That's like, on my personal server, I have this thing that monitors the file system and it sends me an email anytime it detects changes within a particular tree. I don't even remember what the heck, I think it's called like file site, something like that. And, every now and then, it'll sh it, when I upload stuff to the server, I totally expect to get these emails, so I just delete them right away.

[00:46:07] **Ben:** But every now and then, when they're doing some maintenance, or say like they're renewing an SSL certificate, and they have to put a file into a known location so that the certificate authority can verify that it's my site, I'll get an email for that. But it's coming out of one of my, you know, dub, dub, dub, like INetPub folders.

[00:46:26] **Ben:** And I'm like, what, this is not good. And then I realized I looked closer and I'm like, oh, okay. It's just the SSL people.

[00:46:34] **Carol:** All safe, all safe.

[00:46:35] **Ben:** Yeah. It's terrifying every time.

[00:46:37] **Adam:** Oh, I'm glad you're okay, Ben. Er, not Ben, sorry,

[00:46:40] **Carol:** Tim.

[00:46:41] **Adam:** My jimmies are rustled, I can't

[00:46:46] **Tim:** Anyway, so that was my fun for the week.

## [00:46:49] Carol - User/Account ID Problems

[00:46:49] **Carol:** Yeah. Mine's kind of quick to you. I can kind of go over it. So in our application, we have this concept of a user that gets, it's the information that kind of gets stored on the table, so if you come back to it, you know, what user created records, what user, you know, links. And you can see it. However, there's like lots of places where we are right history and we are right logs based off of what we call the account, which is who's logged into the system. So it doesn't really matter too much until you hit my situation. Where I have a consumer project now that has its own account that's triggering these actions based off a user that triggered them in the other application. And suddenly everything is writing all these logs and history as the consumer account.

[00:47:36] **Carol:** So it's like, Oh, this consumer. You know, MessageService now created these requests. It's approving these requests. It's linking these vacancies to requests. And I'm going, Oh no, how do I solve this? Like, cause it's either going to be, I have to tell it to use a different account. So I think what I'm going to do is just kind of bypass the dependency injection, which is kind of what I want to talk about a little bit, but I'll wait and see how I actually go with it.

[00:48:03] **Carol:** so kind of bypass the dependency injection there and actually, force a new account when I'm coming from this consumer and kind of see how it goes. If not, I'm going to make some code changes to the handlers so that they actually, create the account again based off the user I pass in.

[00:48:20] **Tim:** So is it almost like a circular dependency?

[00:48:23] **Carol:** I don't think so. No.

[00:48:25] **Ben:** Can you get. Colliding IDs, meaning can a user, can a user in one, can a user in your system have the same ID as a user in a different system? So now you have an account saying, I'm user ID 4, because that's 4 in a different system, but the user ID with 4 in the system is different user.

[00:48:42] **Carol:** no, no. They're all, they're all the same. I don't have an issue with that. The issue is that we have created the consumer project as having its own account. So everything that, that executes inside the application actually executes under this consumer account. So that's, what's getting written to the logs.

[00:49:01] **Ben:** Hmm.

[00:49:02] **Carol:** It's fun.

[00:49:04] **Tim:** us know how you figure it out.

[00:49:06] **Carol:** Yeah, will

[00:49:06] **Tim:** sure you will.

[00:49:07] **Ben:** On a

[00:49:07] **Carol:** Oh, I have no doubt.

## [00:49:09] Dependency Injection

[00:49:09] **Ben:** dependency injection, which you mentioned, it's just amazing.

[00:49:13] **Carol:** It's so

[00:49:14] **Ben:** I feel like once you use dependency injection, you can't not use dependency injection to, to the point where when you go and you start working with, well, I'll call it legacy code, but that's not really the right word. You go and start working in code in languages like Node.

[00:49:28] **Ben:** js, where they don't really have a good mechanism for that kind of stuff, or at least not in the common JS world. And, and like, they just don't get it. They're like, what do you, I just include the things that I need to include. And I'm like, yeah, but you're depending on the fact that that module only executes once and they're like, yeah, well, that's how CommonJS works.

[00:49:46] **Ben:** And I'm like, yeah, but you're still just depending on it. You should be injecting things you need. This is crazy. They're like, why? I just include what I need. I'm just like, oh my God, how do you not get this? Dependency injection is amazing.

[00:49:59] **Carol:** Yeah, it's, it's fun until you need to track something back. And I'm like, wait, how did it ever even get over there? I have to go find it. Cause it's not, there's no like direct reference, right? It's not like I went here to here with an include. So I know what I did. I have to go, wait, this command goes to this handler and use these validators and it used this service that actually created from somewhere else.

[00:50:23] **Carol:** I'm like, okay. I have all these files open. I'm like, please don't crash because I'm going to forget what files I had open and how I got there.

[00:50:32] **Adam:** Mine should actually

## [00:50:33] Adam - GraphQL

[00:50:33] **Adam:** be relatively quick, too. I mentioned earlier, the TypeScript issues that we've been having, and that was What I was originally planning on talking about for this, but then I remembered in addition to the TypeScript stuff where like, you know, compiled stuff is breaking the build and I just kind of like kicked the can on that.

[00:50:50] **Adam:** the sort of the positive from that is that we're doing some really cool stuff with GraphQL, not that it's like. High level GraphQL. It's just like, it's new for us and different and exciting. And I'm having a lot of fun with that. So like, we're basically, we decided to create a centralized GraphQL API, a multi tenant API for like all of our databases.

[00:51:12] **Adam:** So all future data access should be done through this GraphQL API. And then if we want to expose a REST API to somebody, then it'll just be like a REST layer on top of our GraphQL layer. And, it's, it's just fun and different and new and I'm excited about it.

[00:51:28] **Tim:** That is cool. I played around with a couple of years ago with, with GraphQL stuff and just haven't found a real world example that I could benefit from it, but I was like, that's pretty, it was actually a hackathon, that, that, that it was just playing around with, and they, they were like giving prizes if you did something cool with their stuff.

[00:51:44] **Tim:** They never submitted anything. I was interested to learn about it. What, what, is there any like open source or will you use any particular type of,

[00:51:52] **Adam:** I, I'm not the one writing it. so I don't know all the details, but I know it's on Node. there are, I'm sure there are, like reference implementations in other languages or other libraries for other languages. I think sort of, not table stakes, but you know, probably 90 percent or something close to it of GraphQL implementations are on Node using some sort of.

[00:52:13] **Adam:** You know, framework or library or whatever. we are using a tool called Pothos. I don't remember exactly what for, it's just like a GraphQL, plugin library sort of thing, I think, it's doing some code generation for us. And I think it might be part of what's helping us have like strong types from the database all the way down through the client, in theory, hasn't actually come to fruition yet, but,you know, we'll see, hopefully.

[00:52:39] **Tim:** is there a particular. Use case reason why you chose GraphQL instead of other.

[00:52:46] **Adam:** Because it will, sort of force some structure on us. Well, okay, to take a step back and maybe it will help to think about some of the problems that we've experienced in the 10 years of writing this product. you know, our current API that we expose for our customers is just a very hand rolled, CFML REST API built on Taffy and it works great.

[00:53:08] **Adam:** It's super fast, very functional. The problem is the meatbags that wrote it. We're very inconsistent. so, you know, where you might have one place where you're talking about, let's say people, right? And so you have like first underscore name and it's a character field and it might be up to, And then in another resource, even for like the same data, right?

[00:53:32] **Adam:** We're talking about like, attending an event and, and attending an activity or something, which is like a child of an event. and, and that other API might refer to the exact same piece of data as like, snake case, or I guess that was snake case, but so camel case, first. Capital N name, no underscore, and it be, you know, a maximum of 200 characters or something like that.

[00:53:55] **Adam:** And it's just, the inconsistency was, in my case, personally driving me crazy, because I feel like it, looks unprofessional. and like, and especially when I know some of our clients are using like Java and they, so they are like, okay, we're setting up a strict type to consume this data, right? We've got a Java bean that we're creating and it's this type and how come when we, populate the bean from this resource, it's different than when we populate the bean from this resource.

[00:54:24] **Adam:** Why are they different? They're the same data. And it's like, yeah, sorry, because we suck. That's why. and so one of the nice things about GraphQL is it'll allow us to just be like, here is the database schema in the code, and you get the exact same thing every time, right? It's got the same capitalization, the same snake case, camel case, whatever, every time.

[00:54:46] **Adam:** As long as you're referring to the same field, and we're working on with some other concurrent projects to improve the consistency. So like if we're, if there's a first name field on the user table of the admin, you know, user thing, it should be the same length as the first name column on a event registration, right?

[00:55:02] **Adam:** Like first name is a first name. and so we're, we're trying to improve consistency there as well, because again, meatbags with their pointy sticks on the end of their meat arms, defined the database and did a very inconsistent job, of, of setting that up initially. And so, that, that's kind of like, I would say the, the lion's share of our interest in GraphQL is just kind of forcing us to be consistent across everything.

[00:55:28] **Adam:** And then knowing that we can have TypeScript types generated from our schema and use those throughout the application and the, the client, is very

[00:55:38] **Carol:** snazzy. Yeah.

[00:55:40] **Tim:** Yeah. So Facebook created this. So what you're saying is Facebook's pretty cool,

[00:55:44] **Carol:** Yeah. That's what I

[00:55:45] **Adam:** shut your mouth.

[00:55:49] **Carol:** I mean, you, you've got to go for anything that has an IDE for it. That's called banana cake pop. There's actually an IDE

[00:55:56] **Tim:** Is that what it's

[00:55:57] **Adam:** I have never heard of this. Is this

[00:56:00] **Carol:** for it. It's called banana cake pop.

[00:56:02] **Adam:** is for GraphQL?

[00:56:03] **Carol:** Yeah. It's for GraphQL.

[00:56:05] **Adam:** I'll look that up. Banana cake

[00:56:08] **Carol:** I will post a link to it right now. Yeah,

## [00:56:12] Code Generation

[00:56:12] **Ben:** Code generation is, is one of the reasons that I've never really looked into GraphQL. There's a couple of things in the programming world, and I'll caveat this by saying this is 100, 000 percent subjective, but there are some things that just don't make sense. Rub me the wrong way, like defining lots of stuff.

[00:56:31] **Ben:** Yeah, it's basically defining lots of stuff inside of a string. Like anytime I see, Oh, here, just, all you have to do is define this giant chunk of HTML inside of a template literal. I'm like, Nope, that's not how I do HTML. Sorry. Or, or when I say like, Oh yeah, all you have to do is point it at this database schema and it'll generate a bunch of types.

[00:56:51] **Ben:** I'm like, Nope, that's not how I write code. And again, that's, Not a judgment call, this is just personal. but I, there's something about generating code that has just always felt, know, like a hurdle for me.

[00:57:03] **Carol:** we've seen your blog. We know you, we don't like it when they take out like all your white lines and stuff. Yeah.

[00:57:10] **Adam:** I used a tool from Brian Rinaldi forever ago called IlludiumPU36. I think it was,

[00:57:17] **Carol:** Sounds cool.

[00:57:18] **Adam:** Generator, code generator. It would like, so you would, I don't know if it worked from the database or if you had to like somehow give it a schema or something, but like it would generate a gateway object and a DAO and beans and all this stuff.

[00:57:32] **Ben:** It was a reference to the, that Martian, cartoon. Yeah. I don't know.

[00:57:37] **Carol:** What about you, Ben? You're the last one.

[00:57:38] **Ben:** I,

## [00:57:39] Ben - Data Exports

[00:57:39] **Ben:** I'm, I'm working on this data export. So as we've talked about before, Invision is closing at the end of the year and I'm in my spare time trying to come up with a way to maybe export a more comprehensive set of data for a particular prototype.

[00:57:53] **Ben:** And, it's just been fun. because there's no pressure. I mean, no one's asked me to do this. I'm just. Curious to do it and, essentially what I'm doing is generating an, an Angular application and I'm going to store it in a zip file. I'm going to download all the, Images that go with the prototype.

[00:58:10] **Ben:** And I'm going to put that in the zip file and then I'm going to reference them in the Angular app. And, I don't know, it's, it's a lot of fun. And in order to get this Angular to compile in a meaningful way, I had to write a Gulp script and it was the first Gulp script that I have ever written. And I'm sure that, younger developers listening to the show are like, Gulp script, what the heck is that? So before you had,esbuild, you had webpack and before you had webpack, you had. I think it's basically kind of the, the, the evolutionary

[00:58:41] **Adam:** you had gulp, you had grunt

[00:58:42] **Ben:** Yeah. Yeah, exactly. And then before you had Grunt, you had just including a whole bunch of files. yeah, so it's just been, it, it's always fun when there's sort of a black box piece of technology, like a Gulp script.

[00:58:54] **Ben:** We have Gulp scripts in our application. We've had them for a decade and, they've always just been complicated and I didn't know how to use them. And it's been mysterious. And then I finally sat down and I wrote one and I still don't really understand how the streams parts of it work, but I was able to compile files and substitute values and concatenate and minify.

[00:59:11] **Ben:** And, and, I don't know, suddenly it doesn't sound so crazy. And I always liked that, that removal of the magic.

[00:59:19] **Carol:** Yeah, that's really cool.

## [00:59:21] Patreon

[00:59:21] **Adam:** Alright, well then this episode of working code is brought to you by the new database in, in. Insurance application. and listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:59:37] **Adam:** Our patrons cover our recording and editing and transcription costs. And we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:59:47] Thanks For Listening!

[00:59:47] **Adam:** We're going to go record the after show. Tim's going to give us a testicle trip report. turkey testicle trip report, and apparently Carol has some good news, so, we'll have to find out what that's about.

[00:59:57] **Adam:** If you're not familiar, the after show is a special bonus, few minutes of the show, sometimes five minutes, sometimes it's 30, And we just, you know, outro plays and then we keep talking. And if you'd like to help, if you'd like to listen to that, you can go to patreon.com/workingcodepod and support us there for as little as 4 a month.

[01:00:15] **Adam:** And actually lower than that, if you, pay, yearly. we would really appreciate that. that's it for us this week. We'll catch you next week. And until then,

[01:00:22] **Tim:** heart matters.
