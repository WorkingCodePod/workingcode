---
title: "053: Product Management with Adam Lehman"
description: "On this week's show, Tim interviews Adam Lehman, the Director of Product for Marketplace Core at Spotify."
date: 2021-12-15
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/053-product-management-with-adam-lehman/id1544142288?i=1000545043071"></iframe>

On this week's show, Tim interviews [Adam Lehman][adam-lehman], the Director of Product for Marketplace Core at [Spotify][spotify]. Of course, many friends-of-the-show will know Adam more intimately as the former Director of Product and Engineering at Adobe where he helped drive the Adobe ColdFusion product and community forward. Or, as Tim puts it, where Adam _"lead by throwing grenades"_. Like most Product Managers (PMs), Adam never quite Invisioned himself as a PM. He started out as an engineer who ended-up falling backwards into the PM role when he maxed-out his ability to exert change as an individual contributor (IC). Adam believes that engineers ultimately make the best Product Managers because of their ability to bring a holistic set of skills to the table. Which is why he's always on the look-out for engineers that gravitate towards a management mindset.

## Notes &amp; Links

- [Brackets IDE](https://brackets.io/)
- [Spotify is hiring](https://lifeatspotify.com/jobs)

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. Or, leave us a message at (512) 253-2633 (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[adam-lehman]: https://www.linkedin.com/in/adrock/
[spotify]: https://www.spotify.com/
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/053-product-management-with-adam-lehman.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Adam Lehman:** anecdotally, when I found though too, and this was always, I felt really good with my team, a really great moment for me. We had always be growing the engineering team and our product team. And we'd always have headcount and we'd say, okay, next year we can hire 10 more people. And for the first few years it was like, well, let's just keep hiring engineers.

[00:00:17] **Adam Lehman:** Yeah. We could do more with engineers. Engineers could do everything. but my engineering managers who were handling the product. Prioritization for a couple of these projects. And when we got to, I think like year two and we had some head and everyone's like,we should just hire some product managers because this stuff is hard and we'd like to offload it.

[00:00:33] **Adam Lehman:** And I feel like, and I went through this when I chose to come to Spotify. If you want to be a really good engineer, you kind ofwant to really focus on it exclusively. And if you want to be a really good product manager, you got to focus on it exclusively. It's very hard to be great at these two different disciplines at the same time,

## [00:01:09] Intro

[00:01:09] **Adam:** Okay. Here we go. It is show number 53 and on today's show, our very own Tim Cunningham is going to have an interview with Adam Lehman. so I guess, for the most part, let's just jump right into it. Tim, is there anything you want to say before the interview starts?

[00:01:22] **Tim:** Yeah. So, I mean, Adam layman, many of them who might know him, he's currently a product director at Spotify. So most of us have heard of Spotify, but his background, obviously those who know him know he was the product director for, ColdFusion back in like a fusion seven days.

[00:01:39] **Ben:** Thank you.

[00:01:40] **Tim:** Yeah, so great guy, just enjoy catching up with them and just really got to get some really good information about, making that leap from a developer to product manager.

[00:01:51] **Tim:** So that's great, great, great information. And he's a listener of the show. So found that out.

[00:01:56] **Adam:** Yeah. Cool. Well, let's have a listen.

## [00:01:58] Adam Lehman Interview

[00:01:58] **Tim:** Hey, we've got Adam layman on the show today. Hey Adam,

[00:02:02] **Adam Lehman:** Hey, Tim, how are you doing?

[00:02:04] **Tim:** doing well long time ago.

[00:02:05] **Adam Lehman:** I know it's been a forever and a day.

[00:02:08] **Tim:** It's a today. It has. So I know Adam from the days when he was the Adobe ColdFusion product manager, and a great guy hung out with mini conferences. so w for those who don't know you, Adam, just, why don't you give us the introduction who you are and what you do, what you're

[00:02:24] **Tim:** doing.

[00:02:25] **Adam Lehman:** yeah, so my name's Adam, I'm a product manager now going on 15 plus years, with my first product management job, being back on Adobe called fusions curve. Discovered the trade. I

[00:02:36] **Adam Lehman:** spent 15 years at Adobe doing various product roles and eventually actually even taking on director of engineering and product role for quite a while.

[00:02:44] **Adam Lehman:** but then more recently, about three months ago, I moved over to Spotify to focus exclusively on product again. and so I've been leading a team there that focuses on the music side of the house.

[00:02:54] **Tim:** Okay, very cool. So when you say music side of the house, what does that

[00:02:57] **Tim:** entail?

[00:02:58] **Adam Lehman:** Well, you could probably imagine a lot of listeners are probably familiar with the listening piece of how Spotify works in all of our sort of player aspects and getting our vast collection of music out to your speakers. I focus on the other side, which is how we work with the artists, the labels, the music providers to get all of that content into our system, manage their metadata, their profiles have interactions with fans, all that sort of stuff.

[00:03:21] **Adam Lehman:** So Spotify considers it, their quote unquote enterprise side of the business a little bit. Term for enterprise that I'm used to, but from Spotify is perspective. This is like the professional side that when we're dealing with pros and creatives,

[00:03:33] **Tim:** Cool. Very cool.

## [00:03:35] What's The Key To Being A Good Product Manager?

[00:03:35] **Tim:** So I know we talked a little bit about, who we had an earlier episode. We talked about project management to some extent about, setting deadlines and things like that. But yeah. Having your years of experience and product management. what's the key to being a good product manager.

[00:03:50] **Adam Lehman:** Oh, wow. Right. The million dollar question. for me, I mean, and this is a little bit cliche. It always comes down to empathy and the ability to put yourselves in other people's shoes understand, their perspective, their pains, their passions, and typically that's, I think the strongest skill that.

[00:04:09] **Adam Lehman:** Building, even transparently as you're of becoming a product manager going through it is just of stability to see things from different perspectives. and when you can do that, you tend to end up being able to what we'll call it, go from your gut quite a bit, but it's really not really your gut.

[00:04:22] **Adam Lehman:** It's actually experienced and learned, understandings of how to do that. So.

[00:04:28] **Tim:** So I'm laughing a little bit here. So when did you come to that realization? Was that like something you knew early on? And it does this, the mature older Adam, because I remember Adam the how the, the phrase that we use to describe you was to lead by throwing grenades.

[00:04:42] **Adam Lehman:** Yeah. Now, I don't know if that's a, this is a difference of personality from just my twenties to where I am today or it's as a result of a lot of experience. But one thing about product management is, usually we lead through influence. Like we don't typically have engineers report to us and we're trying to even go out and promote the ideas or the products that we built.

[00:05:04] **Adam Lehman:** it's always through influence. And so, I mean, to throw grenades, I've found that,that can be effective in some areas to shake things up and get into it. but ideally that's probably not the way that I think I've been successful in the last few years at least. but yeah, I dunno.

[00:05:17] **Adam Lehman:** I dunno if that's just product management maturity, or just a personal maturity that happens when you get older.

[00:05:22] **Tim:** maybe you've been a both. All right. Yeah.

[00:05:24] **Adam Lehman:** Exactly.

## [00:05:25] What Led You To Product Management?

[00:05:25] **Tim:** So what led you to get mean? Was this always your goal? I mean, what background you come from before you got into product manager before you came to Adobe? what was the plan for like Adam out of school?

[00:05:35] **Adam Lehman:** So I went to school for film. I really wanted to be like a writer director, coming out of high school, really passionate about some of the sort of, I don't know, cult classics now, like pulp fiction and things. I was a hundred percent moving towards the creative side of the house of when I was going into school.

[00:05:53] **Adam Lehman:** but you know, not to age myself too much, this was, roughly around 97. So the internet was just like becoming formed, HTML one and two days type of thing. And so in the summers. Spending in between college, I was spending doing web development, for a company that my cousins ran.

[00:06:11] **Adam Lehman:** and then I started getting into other things and realizing wow, this is actually quite lucrative. I was making more money, I think on the summer that I could pay for my college tuition for the following year. and then realizing. There's not a lot in college. That's really helping us to meet, to build skills for building into the internet.

[00:06:27] **Adam Lehman:** And so one thing led to another and I ended up doing web development full time. definitely this, these are the days where I discovered ColdFusion moved from back in the old days, I think Pearl and CGI scripts and then was like blown away by what you could do with ColdFusion, back then.

[00:06:41] **Adam Lehman:** And then gap beta pretty. pretty good career out of it. and then I, so I spent about. the first half of my career, as a, as an engineer, I worked at places like we used to call them dotcoms before they were startups here in the DC area. I spend a bunch of time working at Johns Hopkins with a guess.

[00:06:58] **Adam Lehman:** You had earlier my old boss, Brian Kloss. and then I went to the U S department of state post nine, 11, got a little patriotic wanting to sort of,do my part. and we spent a lot of time at department of state. Basically converting old Delphi apps into web applications, which is really where I got very serious about ColdFusion and Java.

[00:07:17] **Adam Lehman:** and anecdotally, the stories to tell is we'd have all this backlog of these old client server apps that we needed to move to the web. And we'd always have this long conversation about, okay, should we do this? And. J two EE enterprisey Javi, or should we just get it done really quickly and do it in ColdFusion?

[00:07:32] **Adam Lehman:** And you can imagine we'd knocked out like 10 or 12 ColdFusion projects while they were working on the one big Java project. so I got started falling really in love with ColdFusion. At that point in time, I started a user group, at the us department of state and that got me on Adobe's radar.

[00:07:47] **Adam Lehman:** so as. They were looking to have someone come in and do technical sales, basically work with the salespeople who are selling ColdFusion, but don't know necessarily how to speak to developers or really get into the details about how to implement stuff. and at that time, ColdFusion was.

[00:08:03] **Adam Lehman:** 80% of the business was coming from the U S government here in Washington, DC. And so they were looking for someone, a new ColdFusion and someone who was in Washington DC. And so that was I think, a fairly short list. And I seem to only made it to the top of that list and ended up taking the job with Adobe.

[00:08:18] **Adam Lehman:** I spent about a year or so in this sort of sales se role. it's probably maybe the first time we met Tim, I think. The sales call back in the day. but then when Ben Forta moved up the stack and Adobe and started looking into evangelism beyond just ColdFusion prefix, we used to call developer advocacy.

[00:08:38] **Adam Lehman:** We used to call it evangelism. and so I ended up getting to, I mean, basically have the job of a lifetime of taking over as the sort of ColdFusion evangelist, which in my early twenties, You know, traveling the entire world, going wherever ColdFusion was wherever the community was being part of that community.

[00:08:54] **Adam Lehman:** And,and, you know, trying to share what we were doing with ColdFusion, but more importantly, try to take everything I was hearing from the community back. And I was definitely in this situation where I kept going back to the engineering team, being like, guys, if we would have built this feature differently, it would make a plant life a lot easier.

[00:09:09] **Adam Lehman:** Cause the community. Like happy with this or it just didn't meet everyone's needs. And that's when, someone who later became a very strong mentor of mine, tapped on his, like, sounded like you want to be the product manager for ColdFusion. And I was like, I have no idea what that is. but if it means I could, we could have more control over what we're building.

[00:09:26] **Adam Lehman:** I'm up for it. So there's a little bit of an anecdote in there too, or a little bit of a story about being hit by a car and being able to walk. So I also couldn't be an evangelist for awhile and that was like, Hey, why don't you just be on product for awhile since we don't want you back on the road?

[00:09:40] **Adam Lehman:** yeah whether it was fate or whatnot, but that's how I discovered product management.

[00:09:43] **Adam Lehman:** And honestly just completely fell in love with it since then.

[00:09:46] **Tim:** Very cool. Yeah. I did not know that about you, that you were into making movies and stuff. That's very

[00:09:51] **Tim:** cool.

[00:09:52] **Adam Lehman:** Yeah. You know, I interview a lot of product managers these days and one of the jokes that I don't always have as I ask people to tell me about their product management journey, because it's very rare that anybody like went to school and thought I'm going to become a product manager.

[00:10:05] **Adam Lehman:** We usually always discuss that. Somehow part of our life. so it's usually never like an obvious choice, although I think that's changing. I think the there's some schools now that are actually investing in that even at the pre graduate level, which is great to see, but it does. Yeah, itit was one of those things where no one ever sought out to be a product manager back in the day.

[00:10:24] **Adam Lehman:** They just kind of stumbled into it.

## [00:10:26] Product Management With An Engineering Background

[00:10:26] **Tim:** Yeah, definitely. So how do you think your background in starting out a bit of, as an engineer informs your decisions now as a product man?

[00:10:37] **Adam Lehman:** Oh, quite a bit. And so. would say that, there's different styles of product management and I think different, I don't know, archetypes. I definitely fall into what some would call a technical product manager where as you know, likean Adobe, whether it was ColdFusion, I moved on into flash platform, built a open source code editor.

[00:10:56] **Adam Lehman:** did a lot more stuff around web development, built some STKs. it was always developer focus. So our core customer, the user I was representing was it developers. Being an engineer. It was a bit of a cheat because likevery easy to find empathy with the other engineers since that's the background that I was coming from.

[00:11:13] **Adam Lehman:** and that, that helped me provide a lot of opportunities also within Adobe, because, we have a lot of product managers, building creative tools, visual artists, side of the house. so when it came to, Hey, when we need to do stuff for developers, it's a pretty short list of people who had that background and experience.

[00:11:28] **Adam Lehman:** so it's informed quite a bit. It became a little bit interesting when I took on engineering again. So the last five years I would visit Adobe, I was a director of both product and technology. And that's where I really had to sort ofmake sure that I was walking the right line as a product manager who has an engineering background.

[00:11:47] **Adam Lehman:** I was always very careful to not lead with a technical solution. Not the right rules and responsibilities. And you want to make sure that everybody's clear on what's expected of each role and if a product managers coming in being like, Hey engineer, build it this way. That's not a recipe for a good collaborative work relationship.

[00:12:02] **Adam Lehman:** and so that's always been a little bit of the struggle of having enough technical background to be dangerous with some technical ideas. Being careful enough to always bite my tongue and make sure, like it's not necessarily appropriate before we to bring this. I did get to scratch that edge again, once I got back into engineering a bit, but even then it was very clear that what were the boundaries of like when we could make an engineering recommendation versus a product recommendation and keeping those things hopefully separate, as I've found, that is a key to build a great products is letting engineering.

[00:12:34] **Adam Lehman:** Do their thing and figuring out the hard technical problems that product to figure out the prioritization, the backlog, they go to market problems. and so you get a good, strong trust relationship when those roles and responsibilities are well-defined.

[00:12:46] **Tim:** Yeah, that'sgood. So the product manager. If I hear what you're saying is his or her role is to, find out what the market wants, what there's demand for. and then take that to the engineering team. and so you're advocating on behalf of the customers really.

[00:12:59] **Adam Lehman:** Yeah,it, honestly, it depends. And then I'd say I, I see product management is like actually a spectrum and it's a fairly dynamic role. And, in my time at Adobe, I probably had seven or so different products, roles, and each working with different teams on different products. And each one was dramatically different of what was asked of me or expected of me because.

[00:13:20] **Adam Lehman:** For one reason is that, the other roles with building software are fairly well-defined like we know what engineers are expected to. They're coming to work everyday to write code marketing design. They all have very prescriptive, like straightforward ideas on what the work is. Product management tends to be the catch all for everything that doesn't fit in those clean buckets.

[00:13:40] **Adam Lehman:** And so. There's always been that term of the mini CEO, which I'm not super fond of. But when I think we're trying to say with that is that, you're always responsible for the success of the. how you make that success is pretty dramatically different. it could be making sure that the engineer has great clean stories in their answers.

[00:14:00] **Adam Lehman:** We have answers to all their questions. It can mean working with user research to figuring out what the next features should be, but it could also be taking it to market writing the blog, posts, the release notes, going out to the conference and sharing the work that we've done. And depending on the makeup of the team, depending on the level of experience with the product manager, or you'll find that you're focusing in these different arrogants.

[00:14:21] **Adam Lehman:** so I've always seen this as a bit of a spectrum with one side being product market fit, user research at the core in the middle of the spectrum is what scrub would call the product owner, the execution pieces, and making sure that engineering has what they need is getting unblocked. And then you're making sure what comes out of engineering is good.

[00:14:38] **Adam Lehman:** So more executing on the vision. And then you've got the sort of other side of the spectrum, which is. Usually more of the evangelism advocacy partnering with marketing socialization aspects. and yeah, and depending on the team, you might find that, oh, you know what? This is a research team. Engineering really does figure out what's going to be built.

[00:14:56] **Adam Lehman:** Really what they need help with is amplifying the message after it's built, type of thing. And so you'll find that then the product manager will spend most of their time on that side. And not necessarily all the market fit side, because that's more technically driven if that

[00:15:07] **Tim:** Gotcha. Now that you're at Spotify. Where on the spectrum, would you say your role is now as product manager dealing with the creative.

[00:15:17] **Adam Lehman:** Well, so, I'm a director of product at Spotify, which means my role is really about, helping my product management team, to unblock them, to try to spur on their creativity and play devil's advocate to their ideas. So not to try to persuade them or change their ideas, but make sure that they feel that They can stand up behind their ideas that, if there's criticism or doubt coming, that we've walked through all of that sort of stuff.

[00:15:41] **Adam Lehman:** So my days are now a little bit more focused on thinking of the higher level piece, but mostly it's more about empowering and helping others on my team to grow and so that they can make those right decisions and lead the products correctly.

[00:15:54] **Tim:** So, yeah, so I guess I didn't really recognize it. So you're a director of product. So you have product managers reporting.

[00:16:01] **Adam Lehman:** Yep. Yes, I've got aa whole team.

[00:16:04] **Tim:** Oh, I imagine it's as big as Spotify as I imagined, it would have to be a pretty big team. So you're even further removed. It's almost like you're are you're vetting the ideas of the product management team and challenging them and making sure they thought everything through is that

[00:16:18] **Tim:** fair characterization?

[00:16:19] **Adam Lehman:** I think so. I'm still trying to figure out exactly what the role is because as I said, like with product management, it's more. Is needed. And so it's always a conversation around what's missing and where I can help. especially even at this higher. So, my team again is focused on the music side of the house, but we also are considered a foundational team.

[00:16:39] **Adam Lehman:** And so our core stakeholders are actually the internal teams that are building products for, the music side of the house, the record labels and the artists. And so what we've been trying to do is build a portfolio. Takes as much off of those engineer's plates as possible so that those products can move quickly, pivot, ship fast, but also so that we can standardize, where it makes sense.

[00:17:00] **Adam Lehman:** this is part of helping the company to mature, I think to become a much larger, more consistent, company in terms of how we ship software. so, so we have a fairly diverse portfolio, that comes from. We're either delivering technologies, managing things like CACD processes for some of our apps to building out platforms, to actually even bring some products to market.

[00:17:20] **Adam Lehman:** So it's a bit of a mix. And so my task since I've joined has really been trying to make sense of this portfolio and make sure that it's not just a bag of door knobs, that we're all pointing the ship in the same direction that we're amplifying the impact that we have, when we're working together across these different disciplines.

## [00:17:36] The Spotify Agile Model

[00:17:36] **Tim:** Very cool. So I have a personal question. So we had recently had. Session. And one of the things that someone brought up that we need to look at is the Spotify agile model, is that something you're exposed to over there? It's like a different way of how your engineers and your product and all the teams relate to each other.

[00:17:58] **Adam Lehman:** Yeah. So, I've got complicated feelings about this.

[00:18:03] **Adam Lehman:** Uh,

[00:18:03] **Tim:** those.

[00:18:05] **Adam Lehman:** my first exposure to the Spotify model was probably about a decade ago while I was at Adobe. I think this is when Spotify was really pioneer. Uh, way to build out their company and be able to ship software extremely fast at a very high quality.

[00:18:20] **Adam Lehman:** and so that got a lot of buzz in the industry. And as a result, I remember we had trainers come in at Adobe as we were launching a new project, to train us on how to think on the Spotify model. I think there's a couple of things. I took away from that, then that I've definitely carried on forward.

[00:18:36] **Adam Lehman:** we ultimately did not adopt it at Adobe in the exact same way that it was prescribed, but I've also found that now that I've joined the company, that model,as the company grows was really strong for Smaller companies getting off the ground, but not necessarily for the larger mature companies where we have thousands of engineers trying to collaborate together.

[00:18:58] **Adam Lehman:** but there are a couple of really strong things that came out of it. one of them, there's some nomenclature around squads and tribes and missions, which I think actually is a really strong way of thinking about companies and organizations, but it also really instills. and so one of the things that I really admire about the model is that we get.

[00:19:18] **Adam Lehman:** Fairly little guidance on how to succeed from up above what we have is high level goals for the company and says, Hey, we want to go and do X, but you won't really hear. And this is how to do it because the outside the atomic nature. it's up to us at a tribe level or a squad level to figure out how we could contribute to that goal and how we could have an impact on that goal.

[00:19:41] **Adam Lehman:** And so it builds a lot of autonomy and independence, which, is a product manager is as our lifeblood. if we're being told everything to build from stakeholders or else, we don't have any creative input or any sort of independence, this is typically where we're product managers get super frustrated and leave.

[00:19:58] **Adam Lehman:** And so as a result, it's a really great environment. Product thinking, because of that, now the con and why my feelings are complicated is that, my role in our team's role in the company is to help amplify the success of those around us. So we're sort ofin a platform position. These teams who are typically autonomous, aren't used to having these big dependencies where they have to depend on other teams for their success.

[00:20:23] **Adam Lehman:** And so there's a bit of this friction that kind of goes with that. but ultimately it works because the other part of the Spotify model is about shipping. Failing fast pivoting. And when you have that piece where teams really do want to move quickly, respond to customer needs and develop products as fast as they can and get it out to market.

[00:20:45] **Adam Lehman:** They also realize they need help to keep that acceleration going. And so what you may have found is well, we don't really want to have these dependencies because we want to be independent, autonomous. They're willing to take those because they'll help on that other goal. Okay. Hey, if you guys are going to handle localization, Right.

[00:21:00] **Adam Lehman:** For as an example, across all of our products, we don't have to think about it. We can just think about the feature, right? Security, these other sort of must do's That cut across. if we can offload that to other teams, that's a dependency that they're welcome to take and they can still be independent and move quickly, with those dependencies.

[00:21:17] **Tim:** Okay. Cool. Very good. I appreciate that. That will, we'll take that into consideration because we were looking to implement it. We were much smaller than Spotify, so maybe it will fit us well for, until we get as big as you guys.

[00:21:28] **Adam Lehman:** Yeah,

## [00:21:29] Making The Move To Product Manager

[00:21:29] **Tim:** Very cool. All right.anything else you want to talk about

[00:21:32] **Adam Lehman:** Yeah, I mean, well, so there's a couple of topics that I think, that are at least top of mind for me in recent time. and one of them is about this journey between going from an engineer to a product manager. I'm very biased in the sense that I think a lot of great product managers come from engineering backgrounds since that's sort ofwhere I came from as well.

[00:21:51] **Adam Lehman:** And so, I've always been on the lookout and helping other engineers make this jump in transition. I think there's definitely a style of an engineer who if you're like me, got to a point where realizing there's only so much you can do as an individual contributor, writing code, right?

[00:22:06] **Adam Lehman:** There's only system. So complex, you can build in the time that you've got. And I just found sort of product management is a cheat, which is we can build bigger things when I can lead product across 10 engineers. Right. And then we can get them all working together and that's largely how you build the cooler, bigger stuff.

[00:22:22] **Adam Lehman:** and so for me, that was like an engineer. Kind of strategy of I just want to build bigger stuff. That's more impactful. I can't do it alone. And so product management was the right place for me to move into, to basically be able to corral that energy and get everybody on the right page.

[00:22:37] **Adam Lehman:** And I think there's a certain types of engineers who kind of gravitate towards that. And I always recommend if that's something you're interested in. that, that not to be too concerned about switching careers or jumping into product management. there's definitely a pathway there.

[00:22:50] **Adam Lehman:** and at least in a lot of the organizations I've been in and especially at the organization at Spotify,it's very, I'd say it's a lot easier to teach things like. How to be a PO and manage a backlog and VPs and stakeholder management. Those are things that are tens of books out there and training on, but it's really hard to do is to have that technical background and that empathy, especially on the developer side of things, that's something that just comes through experience.

[00:23:17] **Adam Lehman:** And those most engineers have that. They may not realize that they've got it and they're using that tool, but it's there. And so it's pretty easy to make that jump. I'm always usually on the lookout for engineers who are looking to make that jump, especially when we're talking about platform engineers or re or platform, product management or research product management, because we tend to really Excel there with technical backgrounds.

[00:23:37] **Adam Lehman:** So, if there's anybody out there who's been thinking about whether product management's for them and concerned about making a big career change, I'd say, go for it, and find a pathway that you can do it, but in general, the other piece about product management and learning it's historically has been a Prentice mentorship type of approach.

[00:23:56] **Adam Lehman:** at least, for me and my generation and seeing it even moving forward. There isn't a lot of like structure to going to school to become a product manager. This there's some ability to start now, but largely it does tend to come from finding someone who's been doing this job for awhile and learning from them, getting into the trenches, learning on the job, but then having somebody who can at least, provide some mentorship there.

[00:24:21] **Adam Lehman:** And so another key piece there is being able to establish relationships with other product managers is definitely ones who are a little bit more senior. Product management is a craft that you've never stopped. Learning is similar to engineering. There's always something new on an engineering front that you've gotta be learning to stay.

[00:24:37] **Adam Lehman:** Current product management is one of those things where if I ever run into a product management, who's just oh, I'm an expert in all things. I'm pretty much good at all of this. I don't need to learn anything. That's usually a red flag because it's constantly dynamic and changing. and as I mentioned that spectrum, you may be very good.

[00:24:52] **Adam Lehman:** managing a backlog and being the PO, but you may not be as strong on strategy, or you may not be as strong on the advocacy of the socialization and to go to market pieces. And so it's always a learning piece and hence finding good mentors and finding other product managers you can learn from because not a lot of this stuff is written down.

[00:25:09] **Adam Lehman:** it's also very specific to the types of products you're building or the industry that you're serving and the users that you're after. and so therefore you have to find people that are in that same space.

[00:25:20] **Tim:** That's interesting. Now that you say it, if you're an engineer it's easy to make that transition, but I will tell you from my experience, it can be hard, particularly because I've worn that I've had the product manager title several times in my 20 something career. And, but unfortunately it was like, I would be the first right there really wasn't a defined role there.

[00:25:39] **Tim:** It was like, well, figure it out. Okay. Without any clear defined goals. What I found, over time, it was easier to go back to what I knew and that was like hands on keyboard contributing. and so I think for you, that's great though, that you have, you've had mentors that makes sense that you would need someone to mentor you in that, to get you to there.

[00:25:57] **Tim:** but yeah, from what I w what I've observed personally is that is, been a hard step.

[00:26:02] **Adam Lehman:** Yeah. And for what it's worth, I've heard that from some of my reports as well. So, when I was managing both product and engineering at Adobe, we were short on product. And so what ended up happening is we, I had to talk to my engineering managers and start to help them to develop. Product sense because we needed basically the engineering managers to think about the prioritization and our customers when we didn't have, when it was a lack of product and.

[00:26:27] **Adam Lehman:** Some took to it very well, but some definitely struggled with this idea of, things not being logically, laid out all the time and decisions being always data-driven, in a perfect world, if we can make every decision based off of data, you don't really need a product manager. The reason we exist is not all of our decisions can be, they can be informed by data, but there's usually a bit of a.

[00:26:46] **Adam Lehman:** experience piece that comes into it. And I know that makes some people a bit nervous, right? Because, Hey, the fate of the product and the team that's working on it, if we make this wrong decision could be bad for everybody. and I guess that's a bit of the part where I've seen some struggle, but I recommend that anybody who's in an engineering management position, who's going beyond just being an individual contributor and starting to think about the whole team.

[00:27:07] **Adam Lehman:** Start to think about product in that sense of Understanding trade-offs and priorities that sometimes. picking the best technology is not the right thing for the business. and sometimes these investments of saying, Hey, let's go and refactor the application because we know that's the right thing to do from an engineering perspective, may not necessarily be the right thing from a business perspective.

[00:27:25] **Adam Lehman:** And so when any engineering manager who's getting into these roles or thinking more about can understand the other side of these equations, it tends to help out quite a bit. cause ultimately. product managers, aren't really making decisions are out the product. We shouldn't be in general.

[00:27:40] **Adam Lehman:** We should be leading the conversations for the team to make decisions as a whole. and as a sense, you have to teach product management a little bit to everybody so that we all feel like we're having, a role to play when we talk about which direction and how to make trade-offs, Because ultimately, yeah, if it's just a product manager at the end of the day, making all those decisions, the product's probably not going to be that great.

[00:28:01] **Adam Lehman:** and also you're highly dependent on them, this one person, for all of your success, whether it's right or wrong. And if that person leaves or something happens, you're back to square one. so I've always felt it was important for at least once we get past individual level engineering commits to start thinking about product, it started to have.

[00:28:20] **Adam Lehman:** anecdotally, when I found though too, and this was always, I felt really good with my team, a really great moment for me. We had always be growing the engineering team and our product team. And we'd always have headcount and we'd say, okay, next year we can hire 10 more people. And for the first few years it was like, well, let's just keep hiring engineers.

[00:28:38] **Adam Lehman:** Yeah. We could do more with engineers. Engineers could do everything. but my engineering managers who were handling the product. Prioritization for a couple of these projects. And when we got to, I think like year two and we had some head and everyone's like,we should just hire some product managers because this stuff is hard and we'd like to offload it.

[00:28:54] **Adam Lehman:** And I feel like, and I went through this when I chose to come to Spotify. If you want to be a really good engineer, you kind ofwant to really focus on it exclusively. And if you want to be a really good product manager, you got to focus on it exclusively. It's very hard to be great at these two different disciplines at the same time, people can do it, but you tend to just sort of.

[00:29:13] **Adam Lehman:** Jack of all trades, but not a master in any of those. and so that was a nice moment where the team who's traditionally would always like more engineers was like, now it's time, we should be hiring product managers because we could take this off of our shoulders and they can really drive it.

[00:29:25] **Adam Lehman:** but that also then helped to build, which is another important. respect for product management as a craft, because that's another thing that's gone up and down over the years of, sometimes there are cultures and organizations that don't believe they need product at all. and sometimes it's over the top where we think all we need is product.

[00:29:42] **Adam Lehman:** and so one of those things is making sure everybody understands what the roles and the value is there. and then you have a good foundation for the roles and responsibilities and value that you put in.

## [00:29:51] Product Management Resources

[00:29:51] **Tim:** Nice. So, if I were to say to you, Adam is Tim talking, I really would like to make the move and become a product manager. But,I just don't know how to start. you've touched on a little bit, but what would be some good resources that we'd say, Tim, you need to check this out and this out or people you need to talk to or books you need to read or any sort of resource that you think would help me out.

[00:30:13] **Adam Lehman:** Well, the, so there's a couple of things. one looking around your company, there's probably a need for product managers. Work, that's just not being covered. And you can usually pick up some of those tasks as an engineer where there's product managers who are more like, we're happy to have the help to do that.

[00:30:28] **Adam Lehman:** So I've always look around and I guarantee you'll find things that look a lot like product management, even without having to take on the title that you can start to get. You can start to add that to. From a training perspective. I haven't gone through this yet, but it's really growing on me.

[00:30:43] **Adam Lehman:** And I'm looking to do this with my team in the future. There's a new, a new site out there called Reforge, which has been putting a lot of product management training online, in sort of cohort fashion where they run similar to a university style. There's a course that's running, in an afternoon or, sorry.

[00:30:58] **Adam Lehman:** A quarter, say the fall cohort for, so to speak that lots of different, companies will send product management into they'll all go through the course online together. that seems to be pretty good. And then looking at the content that they offer, there's definitely a lot the beginnings of how to learn product management here.

[00:31:13] **Adam Lehman:** And you also get to do it with a group of other people who are in the same peer group, as well. Any product, anybody who's looking at product manage that those seem to be fairly good resources to get into, but I do come back to find a product manager that you have a lot of respect for that you think is doing a good job.

[00:31:29] **Adam Lehman:** cause usually if you're an engineer and you think the product manager is doing a good job, they're probably a good product manager. And so, and just learn from that perspective. it's a good, it's important to though to engage and sort of ask questions and actually have a conversation around it because.

[00:31:43] **Adam Lehman:** I've also found that what you see a product manager do, like visibly is not necessarily everything that a product manager does. And so you can get the idea that, oh, I see this person's going out and speaking at conferences and then coming in, like doing things in JIRA and outlining a backlog. That must be the job.

[00:32:00] **Adam Lehman:** And it's true. Really just the externally viewable parts of the job. There's actually this other piece, all these other pieces that come into play that I know a couple of people have been surprised about when they've made the transition, because they were saying, well, I saw all that stuff. I thought that was the whole job.

[00:32:15] **Adam Lehman:** And it's like, no, no. That's like the fun part. There's the other stuff. That's not always as fun. Right. and these are the harder things that we.

[00:32:22] **Tim:** Cool. I'll check that out. And we'll put that in the show notes. reforge.com mastering product management. I'm looking at it right now and that looks interesting.

## [00:32:28] Spotify Job Opportunities And Brackets.io

[00:32:28] **Tim:** Well, Adam, so appreciate you coming on. Is there anything else that you want to plug or talk about or let the folks know going on

[00:32:35] **Tim:** with you and your life?

[00:32:36] **Adam Lehman:** Sure. I've got a couple things to plug. I am always hiring more product managers at Spotify. and as I talked about, I've definitely got a pension for those who want to make the jump from engineering over. and I've got a couple roles right now that are probably good fit for engineers who want to transition into it.

[00:32:53] **Adam Lehman:** And I'm also, I'm definitely, open and supportive of helping to grow product managers from the beginning all the way up. It says part of my role here. So if you're interested in product management, definitely take a look at the job boards over at Spotify. I think we've got a lot of great opportunities coming up too.

[00:33:08] **Adam Lehman:** The other part that I'll talk a little bit about, just to get the word out of bed is one of the projects that I started at Adobe, which is Adobe's first open source project. now we've had things we have open source after the fact that this was the first time where we started the project on day one with the attentive at being an open source project and being community-driven.

[00:33:26] **Adam Lehman:** And that is. Brackets the lightweight code ender. if you got familiar with brackets, the high-level idea was, and this was a long time ago prior to vs code and others, which was build a lightweight code editor. In HTML, JavaScript and CSS that's meant for HTML, JavaScript and CSS development. So it's a bit of a recursive idea where if you are able to use this product, then you're also able to contribute to the product.

[00:33:51] **Adam Lehman:** Right. it broke some of the previous boundaries we have where maybe if you're a web developer, but you wanted to contribute to your editor. You'd have to, in eclipse stays, learn Java or you'd have to write C or something else to do desktop development. so we tried to solve that by building a, sort of

[00:34:04] **Adam Lehman:** on top of the web stack, even though it's a desktop application. The reason I bring it up now is we've now transitioned the project a hundred percent from Adobe back to the community. so for a while, after I had left the team, brackets had moved over to the responsibility of the Dreamweaver team.

[00:34:20] **Adam Lehman:** So they were managing both three and we have our amp brackets in parallel, and sharing. Awesome features in between the two, but net, but more recently, Adobe having to step back from the project it's fully now in the community's hands. And of course we're always looking for more support on the project.

[00:34:34] **Adam Lehman:** any developers who want to contribute to it. it's a bit of a task though. I'll be honest with you at this point, because, as I mentioned, we started this project ahead of vs code. A lot of the core ideas that came into brackets, you'll find out in vs code and other editors. Although the suit, our goal really was to try to shake up and try to move forward web development tooling at that time.

[00:34:55] **Adam Lehman:** And I think we did a great job. but now that the editor's still out there, I think the last time we checked, there's almost a million monthly active users of it. And so there's actually a large community out there still using the product. But that also means like th there's a lot of work still to be done.

[00:35:09] **Adam Lehman:** and so the community is about to have its first major. Which will be the first builds that we've made posts, Adobe. And of course we're dealing with stuff like getting certs and stuff like that and getting all the boring stuff aligned. but if you're interested in contributing or interested in checking out the project, I highly recommend checking out brackets.io on the website.

[00:35:28] **Adam Lehman:** you'll find pretty much everything you need there to like either contribute to the. Joined the Discord with the community build extensions. If you're not into actually working on the core product, there's a whole bid sensibility layer for plugins and stuff like that. But, but yeah, it's a great little project.

[00:35:42] **Adam Lehman:** it's not, out there to try to take over the world and become like the definitive code editor. It's very focused on its space of HTML, CSS, and JavaScript. but yeah, give it a shot and ideally contribute if you're up for it.

[00:35:54] **Tim:** Well, Adam, thanks so much for coming on the show, really enjoyed the conversations and some excellent insights and I hope things go well with you at

[00:36:00] **Tim:** Spotify.

[00:36:01] **Adam Lehman:** Thanks. Thanks. Oh, wait, I forgot to say the one thing I've always wanted to say listener. First time caller.

[00:36:07] **Tim:** That's true. Yeah, he blows it. So how long you actually

[00:36:09] **Tim:** listened to the show?

[00:36:11] **Adam Lehman:** I've listened to the show since episode one. Of course.

[00:36:14] **Tim:** Well, that's all. That's awesome. So I feel bad now. You probably know a whole lot more about me than you ever wanted to

[00:36:18] **Tim:** know.

[00:36:19] **Adam Lehman:** Yup. Yup.

[00:36:21] **Tim:** Good deal. Well, thanks so much.

[00:36:24] **Tim:** Great talking to you.

[00:36:25] **Adam Lehman:** All right. Thanks.

[00:36:27] **Adam:** Okay. Tim, that was a great interview. Good job, man.

[00:36:30] **Tim:** Hey, well, I mean, Adam did all the work, man. he loves talking about products, so

[00:36:34] **Tim:** I just gave him the rope and he ran with it. So.

[00:36:37] **Adam:** Yeah. I, I found it particularly interesting how there's like this whole other side of Spotify I guess he's director of product, but not for the music player apps. It's like for the, what did he call it? The content team or something

[00:36:50] **Tim:** Yeah. We're working with the creatives the tools that they use,

[00:36:53] **Adam:** The artists and stuff. Yeah. That was it. it makes perfect sense now that you think about it, but it had never occurred to me.

[00:36:59] **Tim:** Yeah. Well, I sound like he's doing well and, he's made the offer out there. If you're interested in getting into product development and product managing, he, he's looking to mentor people and they're hiring constantly. So I will put that in the show.

[00:37:11] **Adam:** Yeah. I saw you because he mentioned all of the open positions. I went and took a look at night. They have a ton of open positions in their hiring all around the world.

[00:37:19] **Tim:** Yeah,

[00:37:20] **Adam:** It's a pretty good opportunity, pretty neat place to work. It seems like. All right. Well, I guess that's going to do it for us tonight.

[00:37:26] **Adam:** as usual,

## [00:37:27] Patreon

[00:37:27] **Adam:** this episode of Working Code is brought to you by grenades first, the best way to get stuff done, grenades first and listeners like you. if you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod.

[00:37:38] **Adam:** so new this week, we have a new patron, Matthew Darby. Welcome to the team. Glad to have you.

[00:37:43] **Tim:** Thanks Matt.

[00:37:44] **Ben:** Yeah, we, oh.

[00:37:45] **Adam:** So of course we have to thank our top patrons, Mani and Peter, you guys rock. Thanks so much for your continued support and to everybody else,

## [00:37:52] Thanks For Listening!

[00:37:52] **Adam:** if patronizing podcast, doesn't your thing. That's totally cool with us. We just appreciate that you take the time to listen. We are thankful for you this time of year.

[00:37:59] **Adam:** if you enjoyed this episode, maybe you could post about it on your social media or tell your friends and your coworkers about it. and it would apparently, as they say, really help us out. If you leave us a rating and review on apple podcasts or wherever you get your. please send us your questions and your show topics on Twitter or Instagram @WorkingCodePod, or you can leave us a message at 512-253-2633 that's 512-253-CODE.

[00:38:22] **Adam:** Or you can join our Discord at workingcode.dev/discord. And not only can you give us your topic, ideas and questions there, but you can just interact with the other listeners and us the hosts. and it's a lot of fun. We'll catch you next week. And until then,

[00:38:39] **Tim:** Remember guys, your heart matters. Even if you stream on not Spotify.

[00:38:47] **Adam:** tell Adam. I listen on YouTube music.

[00:38:51] **Tim:** Oops. He knows now.
