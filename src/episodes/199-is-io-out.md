---
title: "199: Is .io Out?"
description: "In this week's episode, the hosts discuss the potential discontinuation of .io domains."
date: 2024-10-23
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/199-is-io-out/id1544142288?i=1000674135267"></iframe>

In this week's episode, the hosts discuss the potential discontinuation of .io domains, the historical and geopolitical nuances of TLDs like .tv and .io, and the complexities of managing and pricing domain names.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/199-is-io-out.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** I think it was yu or something, there was a, a TLD got stolen from the, the organization that, that ran it, right?

[00:00:07] **Adam:** Like literally somebody broke into a building and stole the equipment and, and the configuration,

[00:00:12] **Ben:** Oh

[00:00:12] **Adam:** It was in a university controlled it and they, they, stole the equipment and the, and the configuration in order to like administer this TLD.

## [00:00:20] Intro

[00:00:20] **Adam:** Okay, here we go to show number one hundred and ninety nine.

[00:00:43] **Adam:** And on today's show,

[00:00:45] **Tim:** 199 on the,

[00:00:47] **Adam:** long awaited episode one hundred and ninety nine, we will explain why it's been a couple of weeks since we've been on. And in addition to that, we will discuss the perils of using country code TLDs.top level domains. but first, as usual, let's start with our triumphs and fails.

[00:01:04] **Adam:** I guess, before we do that, let's explain where why we've been gone. So, being that these are the last couple of weeks, before we call this the end of season one and just take a little bit of a break, we really wanted to ha make sure we had all four of us together, right? And so, like, if if we just couldn't get all four butts in seats at the same time, For the week, then we just decided to postpone.

[00:01:25] **Adam:** And I think it, depending on when this comes out, it will either have been one week or two that we missed. I think it feels longer. It feels like I haven't seen your beautiful faces

[00:01:34] **Carol:** so

[00:01:34] **Ben:** feels like so long.

[00:01:35] **Adam:** but I think in reality, it's been like almost two weeks since we recorded an episode, which would, could potentially translate to two weeks of, missed episodes.

[00:01:44] **Adam:** So appreciate your patience. We're, we're still here, still planning on coming back, and so we got this one, and then episode 200 will be the last episode of season one. Then we're going to take a little, break of indeterminate length,

[00:01:57] **Tim:** we'll go make movies on the side, you know, like

[00:02:01] **Adam:** yeah, you know, turn everything into a side hustle as I do.

[00:02:04] **Adam:** and then, then we'll be back anyway. Okay. Triumphs and fails. and you know, since I'm already bill guarding the mic, and also because the document that doesn't exist says it's my turn to go first.I'm going to go first. Surprise, surprise.

## [00:02:17] Adam's Fail

[00:02:17] **Adam:** So I'm gonna start off with a fail. and this is, in hindsight, not that surprising.

[00:02:24] **Adam:** But also like a little bit,non obvious or something. I don't know, whatever. I'll just get into it. So, I've talked in the past about how I've been frustrated with our CI builds on GitHub Actions. And of course there's a lot of different levers you can pull to try and speed that up. You can just pay for, Yeah, yeah.

[00:02:40] **Adam:** Workers with more CPU and more memory and all that stuff. or you can try other alternative methods like, caching, build artifacts and stuff.and that was the one that we tried. So we tried to speed up our workers. In particular for our main monolith container, you know, in order to run the test for that, it has to like, you know, build the CFML container, which is a sort of a two, we have a two stage build.

[00:03:02] **Adam:** So we have a like a base image, which is just Lucy, you know, the whole operating system thing. And then like the, Which is a separate, Docker container. And then the application code itself is like another layer that gets added on at the last minute. So it has to pull in that base image. and then we have to run the test too, right?

[00:03:19] **Adam:** So it's got like, it pulls in our feature flags server and our config. These are all Docker containers, right? Our config service. And, it's got to build a MySQL and a Redis, like, and it's got to pull all those images. You know, create them, get them configured and then run the test, which, as you can imagine, it's not the fastest thing in the world. And so what we tried to do was, one of my coworkers looked into how you can like, use GitHub offers, like a Docker build cache. So you can say, okay, if, if this container, you know, cache the, the Redis image or whatever, like our base. CFML image so that it's available right there when we run, future builds.

[00:03:54] **Adam:** Sounds great. So he spent like a day or two getting that figured out. And it turns out it's slower and

[00:04:03] **Carol:** Oh, no,

[00:04:05] **Adam:** it's slower because It runs everything, basically, it runs everything in serial, right? So previously, when we would like, you know, okay, spin up all these Docker containers, it was doing all the downloading, all the different container images and everything in parallel, and then, and then starting them up and all that.

[00:04:22] **Adam:** if you've ever used Docker Compose to like bring up a cluster of services, it looks very similar to that. And then, I guess for whatever reason, switching it to run out of GitHub Actions, Docker cache, forces it to download them all, in serial. And it's, it's the same, you know, the exact same bites that are being, being transferred.

[00:04:43] **Adam:** It's just, I guess, a little bit closer. you know, it's probably in the same data center or whatever, but because they're in serial, it ends up being even slower.

[00:04:53] **Carol:** how much slower? What are we talking about?

[00:04:55] **Adam:** Enough slower that we went back.

[00:04:57] **Carol:** You reverted that slow. Yeah, that's so sad. How long do your builds take right now?

[00:05:03] **Adam:** Too long. a good one? maybe 8 minutes?

[00:05:07] **Carol:** Yeah,

[00:05:07] **Adam:** That's a fast build.

[00:05:09] **Carol:** that sucks.

[00:05:09] **Ben:** I say this and I'm not intending to throw any fuel on the fire, but it sounds like, so is there a way that you could separate out the services so that they don't all have to build for the deployment where, meaning let's just say you're making a cold fusion change, is there a way that you can just. Build and deploy the cold fusion and not necessarily have to build the Redis and the MySQL and everything, or is that basically counteracting the

[00:05:34] **Adam:** Well, we're not

[00:05:35] **Carol:** good. Wait,

[00:05:36] **Adam:** re go ahead.

[00:05:38] **Carol:** no, I was gonna say, could you please learn that and then teach me? appreciate it.

[00:05:44] **Adam:** the thing is we're not, you know, we're not, building Redis. We're just downloading the, the Redis container image, which is super frustrating, you would think like the download would be, I guess the download kind of is the slow part and it's any one image is not that much to download. But when you've got like six or seven of them, it just starts to, to bog down.

[00:06:03] **Adam:** And

[00:06:05] **Ben:** a death by a thousand cuts when I look. We use CodeShip and it, and you can scroll down through the entire build logging and it, and it, it's exactly to your point, you want to go in and see the clear loser in the list, like, Oh, it takes 12 minutes and nine and a half minutes of it, or this step, but it's like.

[00:06:25] **Ben:** It's three minutes to pull down the images themselves. And then it's like two and a half minutes to run the NPM install. And then it's some other two minutes to run the build. Oh, it's really frustrating.

[00:06:37] **Adam:** then another two minutes to run the tests and, and another two minutes to Push the containers up to the cloud and, and trigger your deploy. And it's just like, come on now,

[00:06:48] **Ben:** Just the composition of the Dockerfile is such a,

[00:06:54] **Adam:** it's a black art.

[00:06:54] **Ben:** Yeah, it does. It's one of those things where you have to think about which files actually change with the highest frequency. So just for listeners sake, who don't deal with Dockerfiles, you can essentially think of a Dockerfile as a list of commands that you want to run in a, in steps to prepare your application and there's caching along the way.

[00:07:15] **Ben:** So if you change a command that's high up in the Dockerfile, it basically has to rerun every command there and afterwards. So you want to try to put the highest changing frequency files at the bottom so you can leverage all that caching. And it's particularly bad if, like if you, we try to put our package.

[00:07:35] **Ben:** json as high up as possible because we don't change our dependencies very often, but I could imagine it's like then you install a dependency and suddenly it blows away the entire cache and has to rerun everything.

[00:07:46] **Adam:** Yeah. And the, the frustrating thing is you're not reusing the same memory slash disk space for CI runs or deployment runs. You know, that's, it's created basically empty every time you run it. So there is no Docker cache,

[00:08:02] **Ben:** Right, right, right. Yeah. Yeah. Good,

[00:08:04] **Adam:** it locally, you know, your, your, your package. JSON hasn't changed.

[00:08:07] **Adam:** You skip that step, but yeah, when you're doing that CI run, it's just like, you got to, if you know, you want to make an apple pie first, you have to invent the universe. Is that how it goes?

[00:08:16] **Ben:** So you mentioned that you have a multi step build and, is there an opportunity there to leverage different kind of caching, meaning, could you say, do your NPM install on a, on an image that changes very rarely and then have that just be pulled down so you can eliminate kind of swaths of the steps?

[00:08:35] **Ben:** Or like a, is there a version of a MySQL database that already has the data? Prepare that can be its own image. I I'm really talking outside of how I understand how Docker works, but I'm wondering if there's like some fancy stuff you can,

[00:08:50] **Adam:** Potentially there is some more performance to be squeezed from this stone. We were just hoping that this caching thing was going to be some lower hanging fruit and it turned out to be rotten.

[00:09:01] **Ben:** P.

[00:09:03] **Tim:** That's disappointing.

[00:09:04] **Ben:** That's how they get y'all.

[00:09:07]

[00:09:08] **Adam:** And I'm quacked for the first time. Oh, well. Um,okay. So that's me. Ben, what do you got going on?

## [00:09:14] Ben's Triumphs

[00:09:14] **Ben:** I'm going to go with a couple of little triumphs here. my primary triumph, just being that I peopled really hard in the last two weeks. I flew out to Vegas to CF Summit West 2024, met a whole bunch of really great people, took some photos, met Mark Takata for the first time, that was very exciting. Been chatting with him for years online.

[00:09:37] **Ben:** and then I came home from that and I managed to not get sick, which is its own little separate side triumph. Yeah. Yeah, I was washing my hands like a mofo though. I was like to the point where around my wrist it was starting to get kind of raw and, and chapped. But I didn't get sick. It was amazing.

[00:09:54] **Ben:** And, then I came home and Scott Strohs, longtime friend of the show, appeared in an episode where he talked about Angular, I don't know, like a hundred episodes ago.he came to New York to do a MySQL presentation and I jumped right on the train and came down to New York to see him. So I basically peopled back to back, which is fairly unprecedented for me.

[00:10:15] **Carol:** Wowzas.

[00:10:15] **Ben:** Yeah. Feeling, feeling good. Feeling good about

[00:10:18] **Carol:** Did, did Scott, did Scott bring the cooler to New York for his conference?

[00:10:22] **Ben:** he brought a bunch of tiny little stuffed MySQL dolphins to give out.

[00:10:27] **Tim:** Yeah,

[00:10:27] **Ben:** So

[00:10:28] **Carol:** No cooler. Oh, man.

[00:10:30] **Adam:** I think the cooler is retired.

[00:10:31] **Tim:** the cool

[00:10:31] **Carol:** think it's done.

[00:10:33] **Tim:** Yeah.

[00:10:33] **Adam:** It's probably framed.

[00:10:35] **Tim:** I saw all your, you know, pictures for your blog, you know, the processed all those photos and this is me and whoever,

[00:10:42] **Ben:** Yeah.

[00:10:43] **Tim:** picking up Emily,

[00:10:44] **Ben:** Yeah. Yeah. Emily Meyer, she's a good sport. She's, she's good people.

[00:10:50] **Tim:** How was, so how many people were there at the summit?

[00:10:52] **Ben:** I think they said it was somewhere around like 430, 440 people.

[00:10:58] **Tim:** Okay.

[00:10:59] **Ben:** So yeah, it wasn't, it wasn't an overwhelming number of people. Basically, if you think about these hotel ballrooms, the keynote was very comfortably inside of a, a conjoined ballroom where they take down the wall and you get kind of two of the big rooms together, it was, it was quite comfortable in there.

[00:11:17] **Ben:** and that was my first time really staying in Vegas for any period of time. So that was, that was interesting. I, I, I have zero desire to go to Vegas itself, but the conference and the hotel were one in the same facilities, so I basically went upstairs and then downstairs and, I barely had to leave the hotel at all, which was how I like it.

[00:11:37] **Carol:** Did you, did you gamble at all?

[00:11:39] **Ben:** No, I have zero desire to gamble whatsoever. This,

[00:11:42] **Carol:** Not even like a penny slot

[00:11:44] **Ben:** Not even like a tempting in the airport on the way home kind of a thing. Just, I, it's not a moral issue for me. It's literally just, there's nothing about it that is appealing at all.

[00:11:56] **Tim:** Did, did, did you try out for the Chippendales?

[00:11:58] **Ben:** Well, you know, it's funny, right next door. So the conference center was fairly large. This hotel is pretty massive. And there was, it was the Resort World's Conrad, which apparently that building has three separate hotels in it. It's like the Conrad, the Hilton, and maybe the Marriott or something.

[00:12:18] **Ben:** But there was a world's gym franchisee, conference literally right down the hall from us. So there was a lot of tanned and waxed people walking around,

[00:12:27] **Ben:** I appreciate

[00:12:28] **Adam:** Did they mistake you for one of

[00:12:29] **Ben:** No, definitely not. I don't have the coloring. I don't think.

[00:12:37] **Tim:** that's awesome.

[00:12:39] **Carol:** I'm glad you had a good time and you know, got to see our CF people.

[00:12:43] **Ben:** Yeah.

[00:12:43] **Tim:** didn't get sick.

[00:12:44] **Carol:** Yeah, that's huge.

[00:12:45] **Ben:** was amazing. And I did a layover in Atlanta. Oh, I was so panicked because both of my layovers were really short. One was 40 minutes and one was I think like 43 minutes. And I was like, oh man, this is gonna be impossible. I got off the plane, got right on the tram. Tram took me to the next terminal.

[00:13:03] **Ben:** It was literally five minutes gate to gate. I was blown away going to different terminals. So I'm, I'm told that the Atlanta airport has run super, super well.

[00:13:13] **Carol:** smooth. It's the best airport I've ever been in.

[00:13:15] **Tim:** Yep.

[00:13:16] **Ben:** yeah, both of my connections were already boarding by the time I got there.

[00:13:20] **Carol:** Hey, we didn't have to sit around and wait. That's always a win.

[00:13:22] **Ben:** That was pretty great. And I got to stretch my legs.

[00:13:24] **Adam:** one of my triumphs, I guess early this year, or maybe late last year was that like, you know, in writing company policies, I had convinced Steve that we should like Give all of our engineering staff, a training budget that we can use to like attend conferences and stuff.

[00:13:39] **Adam:** And I did not make time or find anything interesting enough for myself to make the time, this year. And I, I feel kind of bad about that. Like that was a perk that I negotiated for myself that I just didn't end up using. I need to be more intentional about using that next year.

[00:13:55] **Tim:** You're leaving money on the table there, buddy.

[00:13:57] **Ben:** I know, I feel like I'm not good about keeping track of what is available, especially in my local area. Now that I'm not in New York City directly or adjacently, it, it's, you know, when I went to see Scott the other day, I actually stayed in New York overnight because by the time the presentation would have been finished, I would have gotten home like midnight, 1am, and that's just, I'm, I can't function that late anymore.

[00:14:21] **Ben:** I'm not a kid anymore, dammit.

[00:14:23] **Tim:** You were, you weren't a kid when you were a kid, man.

[00:14:27] **Ben:** so I, I do need to just plan stuff. I can't do things off the cuff. You know, I can't at three o'clock on a Tuesday afternoon, find out that there's a meetup at six 30 that night and attend. I have to be days ahead of time, trying to figure out what's available. How am I going to make it work?

[00:14:43] **Ben:** Do I have to stay in the city? Is it worth the cost? Is there a way I can get back at night? You know, that kind of stuff. And I, I don't have, I don't have the muscle for it yet. Like the, I don't know where to look. I don't know how to plan for that stuff. So, all right. That's, that's my triumph. Carol, kick it over to you.

[00:15:00] **Ben:** What do you got going on?

## [00:15:01] Carol's Triumphs

[00:15:01] **Carol:** Yeah. I'm going to go with two triumphs. The first is I survived surgery. I have a slight. You know, slur in my, like, voice because, I had mouth surgery done. So that's still healing. So that's been fun to deal with, talking on calls all day today. And, you know, yeah, but that survives. That's good. And then the second thing is, we have found some security issues through our GitHub migration that we talked about before, and some were known, but.

[00:15:28] **Carol:** You know, we were just kind of holding off on another feature to be released so that we could then fix it all at once. Well, that feature kept being delayed and delayed and delayed. So finally, I, I made a push and asked that this be prioritized. And my supervisor listened, and the team listened, and now it's going to go in the next PI.

[00:15:48] **Carol:** So I'm super happy that in my new role, that when I push for a change, that they actually listen, and they see the value add to what I'm asking for, and we get things done. So. I knew it was going to be after the first of the year before they did it currently. And now it should be in the next couple of months.

[00:16:06] **Carol:** So that's a big win. Cause it's all about us. Yeah.

[00:16:10] **Ben:** Nice.

[00:16:11] **Adam:** Yeah. Security issues are definitely important to jump on.

[00:16:14] **Carol:** Huge. And this is like, it's not, it's really not a big issue because it is how. One of our like internal tools that we have like access is Swagger, right? So it's basically just endpoints and how we're authenticating and we pretty much aren't like we're just trusting whitelists and you have to be on the network to even hit it and it's already behind several things.

[00:16:36] **Carol:** But the fact that we can clear it up and just have authentication and authorization actually in place, and now they won't yell at us. And, you know, there's actually two more features coming down where we need to open up some APIs, so we'll use this new, auth, authentication process and be able to develop these and not have to worry about it.

[00:16:54] **Ben:** And Swagger is just a Swagger's documentation or its actual functionality?

[00:17:01] **Carol:** It's functionality, sort of, it's basically Imagine postman on steroids. So my bas can actually use swagger so they can authenticate and once they have their token, they throw it in and then they hit the same endpoints that are code hits. So like they can run a get, edit, you know, they can get counts, they can, you know, hit some of our main controllers and get data back and see what the API would be returning if the customer were to hit these APIs.

[00:17:28] **Carol:** Yeah,

[00:17:29] **Tim:** So you're hosting your own, you're hosting your own Swagger page,

[00:17:31] **Carol:** yeah, we're, oh, yeah, but only, it only hits our dev, like, servers. It's only local. It's not something that, like, is exposed externally. It's just a tool for our BAs and our developers to use to better understand what the data's doing.

[00:17:44] **Ben:** That's interesting. It's almost, don't mean this in a dismissive way, but it's almost like you're using a documentation UI as a reporting interface that people can use to access the application.

[00:17:55] **Carol:** Yeah, I mean, oh, so it's not really for reporting?

[00:17:58] **Ben:** I don't mean reporting, but I mean like

[00:18:00] **Tim:** API

[00:18:01] **Adam:** It's a, it's a sandbox.

[00:18:02] **Carol:** yeah, it's just a

[00:18:03] **Ben:** built an interface to do this, but you're like, ah, you could just use a swagger documentation and put your token in and you can

[00:18:09] **Carol:** Yep. Now we ain't gotta build anything and it already works.

[00:18:12] **Ben:** I, I totally respect that. I think that's, you know, solving the right problem that needs to be solved.

[00:18:18] **Carol:** Yeah, and I'm always big on, there are things I shouldn't do, and if there's a tool that does it correctly, why would I want to create something myself if someone does it better, and that's their job. Like, their job, like, from Swagger, is to give you a tool that allows you to, like, test your endpoints in a visual way that makes sense to, like, any user looking at it. So, use it!

[00:18:45] **Tim:** We, we have Swagger endpoints on our documentation page for API so that people can test it and just play with it there and not have to download or anything to test it.

[00:18:54] **Ben:** So I'm just watching Carol's dog in the background. She was just rolling around on her back. That was funny.

[00:19:01] **Carol:** is a sweetheart. She's currently trying to get my attention, it looks like. It's dinner time for her. Anyway, so that's me. What about you, Tim?

## [00:19:10] Tim's Triumph

[00:19:10] **Tim:** going for a triumph too. So we got, you know, three out of four, ain't bad.So one of the reasons we couldn't record is I was out of town. I was up in upstate New York and near Poughkeepsie visiting my sister.

[00:19:21] **Ben:** What dude? I live just North of Poughkeepsie.

[00:19:24] **Tim:** Oh, really? I, I meant, I meant to message you. I knew you lives. I meant to message you and ask where you were, but yeah, I was, I was, it actually was Fishkill is where my sister lives.

[00:19:34] **Ben:** know exactly where that is.

[00:19:35] **Carol:** I did I thought Poughkeepsie was like a mythical place.

[00:19:38] **Tim:** It, it is, I think it really is.

[00:19:41] **Ben:** it's downtrodden. It used to be, IBM used to have a huge campus there, and IBM still has a presence, but I think when it downsized, I think it really hurt the town a lot.

[00:19:51] **Tim:** Yeah. I mean, it was beautiful up there. I mean, the, the leaves are just starting to change. The weather, it was absolutely perfect. My sister, her and her husband live like right on the Hudson River up in, Fishkill, New York. And, yeah, it was just good to see her. I hadn't seen her in a while and hang out with her and see a bunch of friends that, cause I used to live, I used to live in Brooklyn and so a lot of my friends in Brooklyn now live where my sister lives, so I got to hang out with some people I haven't seen in like 20 years.

[00:20:19] **Ben:** So it's pretty awesome. It's a good family time. The family went with me. I am an airline snob. I usually only fly Delta because as you know, Delta's hub is Atlanta and it works great, but I just couldn't, didn't, didn't want to spend the money for that, so we flew Frontier and it wasn't awful. It wasn't great either, but it wasn't awful.you fly into, dude? Because there is a Westchester airport

[00:20:41] **Tim:** we flew, we flew into LaGuardia and I didn't get to Westchester. So we flew into LaGuardia and we rented a car and then just drove up. It was a great drive. Just, it was beautiful.

[00:20:49] **Ben:** The Hudson Valley is beautiful.

[00:20:50] **Tim:** We picked apples, you know, it's, it's, yeah, it's, it's fantastic. So that was good. And then we got back, I got back from, got back to work and then finally finished our PCI 4.

[00:21:02] **Tim:** 0 compliance. Got our final, our, our, attestation of compliance. Finally, it took a really long time because this is a new, a new, standard. PCI standard, the 4.

[00:21:12] **Adam:** Oh, V4.

[00:21:13] **Tim:** V4, we're on V4 and there's just a lot of new things on it. And so it wasn't even us that was the, was hold up. It was the, it was the auditor.

[00:21:21] **Adam:** Nice.

[00:21:21] **Tim:** They were having to go through the, this new steps and, and we, you know, just took them much longer, but took them two months longer than what they normally take, to, to finish the, finish the tests. So, but yeah, we fought, went through flying colors, no big issues, no, no, no problems, so got, got that. So that was a big triumph.

[00:21:42] **Tim:** Yep.

[00:21:43] **Ben:** Quick question, do you have to get re certified for PCI compliance annually, or this is just because it was a new change?

[00:21:50] **Tim:** No, every year. Do it every year. They're going to get their money, man.

[00:21:54] **Ben:** And it's separate from SOC compliance, right? Okay.

[00:21:59] **Tim:** We're 2 as well. And that's just, I mean, it's, I mean, we have people, a team of people. That's all they do is, is handle compliance and that's their full time job. I, I pretty much just fill out any necessary stuff that we're doing for the software.

[00:22:13] **Tim:** making sure that how we're building the software is best practices with security. And I supply them documentation of how we. To change control and things like that. So yeah, it's ridiculous.

[00:22:28] **Adam:** believe it, some of the work that I've been doing over the last two weeks has made me, appreciate the work that I have to do for compliance. I've like, it's, it's, I've had to, I've been working on Salesforce integration, which if you've never done. Is literally my new definition of hell. And, and, so when I got the opportunity to step away from Salesforce integration work and go back to compliance, I was like, yes.

[00:22:54] **Tim:** You sound like you're living in the worst possible of all worlds. Between

[00:23:00] **Adam:** I guess, AKA, tech management.

[00:23:05] **Adam:** So

[00:23:06] **Ben:** Very cool. Alright, and then Adam mentioned this prior to the show, but we sort of have a, a group triumph that we're able to assemble here, all four of us. Yeah.

[00:23:19] **Adam:** shining faces. Sorry about the face grease. So,

[00:23:22] **Carol:** I was noticing you were looking a little shiny shiny. Like extra shiny

[00:23:27] **Adam:** well, I, I'm sorry. I just came from my Chippendales interview.

[00:23:31] **Carol:** No.

[00:23:33] **Tim:** You're not going to beat out Ben, no matter what. Yeah.

[00:23:37] **Carol:** for Christmas this year.

[00:23:39] **Adam:** Ooh.

[00:23:40] **Carol:** Steve and I are going for a week. We just want to get out of

[00:23:42] **Ben:** I hope I didn't, yuck your yum. Again, my, my issue is not the, I just, it's just not my, my scene.

[00:23:49] **Carol:** Oh, no, I enjoy shows. I enjoy people watching, so just walking around like watching people be drunk and knowing I'm sober. It's kind of nice. Yeah.

[00:23:58] **Adam:** Mm mm. Heh

[00:23:59] **Ben:** That's true, I did ride up the moment I got there in the elevator with what looked to be some sort of a hen party. And the way these women were dressed was just outrageous. It is a good

[00:24:12] **Adam:** Uh,my, the, the thing that drives me nuts about Vegas is trying to exit the hotel and you have to walk through a smoky casino to do it?

[00:24:21] **Ben:** I was shocked that you could smoke in a casino.

[00:24:23] **Carol:** yeah. Yeah. There's I think there's only one.

[00:24:26] **Adam:** Heh heh

[00:24:27] **Ben:** just no laws there.

[00:24:29] **Carol:** The, the newest MGM, I can't remember what it's even called now. It's like the one that has the big concert hall and everything. It's where I say that last time. It's smoke free. No, not the sphere. Yeah, it's down right beside New York, New York.

[00:24:43] **Adam:** MGM Grand?

[00:24:44] **Carol:** And no, it's across the street. MGM Park. Yeah, MGM Park. It is one of the only smoke free. So every time I come down, all I'd smell was coffee and like Italian, like bakery stuff. And it was so amazing. I was like, this is how you get people to come play in the casino. Make it smell like coffee and pastries.

[00:25:03] **Tim:** Awesome. Did you see this sphere, Ben? I mean, that thing's amazing, isn't it?

[00:25:07] **Ben:** I saw it from the cab ride on the way back to the airport.

[00:25:11] **Tim:** Okay. It's pretty ridiculous, that thing.

[00:25:14] **Ben:** I'm told it's immersive and pretty amazing. Groovy.

## [00:25:18] The .io Kerfuffle

[00:25:18] **Adam:** Well, I guess let's move into our topic for the day, the du jour, if you're fancy, so you've probably heard the news by now that, there's some kerfuffle and there's a possibility, although, you know, a lot of people, most of us included, think that it's a slim possibility that io domains are, the TLD is going away, right?

[00:25:41] **Tim:** Yeah, it's funny. my, our auditor sent me like, like the last day of the audit. He's like, Hey, did you see this? And they're like, the dot IO could be going away because our company name is paycloud. io. It's actually part of the company name. And then I sent him another article that was basically saying, yeah, they could technically, but I don't think it will.

[00:25:59] **Adam:** I think you should have a backup plan, you know,

[00:26:02] **Tim:** For sure.

[00:26:03] **Adam:** have an exit strategy. But, you know, what is it, plan for the worst and hope for the best? Yeah.

[00:26:10] **Carol:** seem to have changed it out to be like, Y2KIO. There you

[00:26:14] **Ben:** we should say that IO is a very popular domain in the tech world because in programming IO stands for input output, so it has that sort of tech adjacent feel to it.

[00:26:24] **Tim:** Yeah. It's funny. I was, you say that, but I was on a call one time, it was the insurance company and they're kind of old fashioned and they had a young guy on the call who's like really pushing for them to make changes and, and, he was like, so, you know, how do you guys, you know, do your credit card payment?

[00:26:40] **Tim:** I said, well, we have a RESTful API and blah, blah, blah. And he goes, Oh, so you're a real dot IO company. I'm like,

[00:26:47] **Carol:** I'm so fancy, you guys.

[00:26:49] **Tim:** we're so trendy.

[00:26:50] **Carol:** Yeah.

[00:26:51] **Adam:** paycloud. carrier pigeon was taken,

[00:26:53] **Tim:** Yeah, exactly. Yeah. Very mindful, very demure.

[00:26:58] **Carol:** Techno.

[00:26:59] **Adam:** okay, so, do any of the three of you guys have any io domains?

[00:27:05] **Carol:** Techno.

[00:27:06] **Ben:** I, I had one a while back for an idea that I had that I never executed on, so I, I think I held it for a year and then just let it lapse at that point.

[00:27:15] **Carol:** Who would be silly enough to have jumped on that bandwagon?

[00:27:19] **Ben:** heh

[00:27:19] **Adam:** just, just us idiots.

[00:27:21] **Tim:** Yeah.

[00:27:22] **Ben:** heh.

[00:27:23] **Adam:** I, I do. I have taffy. io, which is for my CFML REST API framework called, oddly enough, taffy. and I thought at the time, I was like, ooh, IO, that's so like, perfect for a REST framework, right? Like, yeah.

[00:27:39] **Tim:** You put up with.

[00:27:40] **Adam:** Yeah, you know what? We haven't explained just like why might it be going away.

## [00:27:45] Why Might .io Be Going Away?

[00:27:45] **Adam:** So I guess for the, for anybody who hasn't heard, obviously something you can google, but the, the TLDR is there's, an island in the Indian Ocean. which was, occupied by England or the British empire. and they have been convinced to give it back, you know, details, whatever. It's going to back to the people who live there instead of to the British empire.

[00:28:09] **Adam:** and I guess the, the IO is from the British Indian Ocean territory or whatever. Like that was kind of what they called that island or set of islands. And so it, like, that's kind of like their, their slave name, right? Like it doesn't make sense for them to keep it. and so, the country name will be changing or I guess officially going

[00:28:32] **Tim:** The control goes to Mauritius.

[00:28:34] **Adam:** yes, and so it doesn't make any sense for them to keep that as their country code TLD, so there's some precedent and some, some top, some. It makes sense for the, for them to not continue to offer io domains. However. There's just so much money currently being spent on Iodomain that's obviously in demand. Like, I think that they will probably find some, find or make some loophole to keep it around.

[00:29:02] **Ben:** Let me, let me ask a question just about networking in general, because this is an area that's very murky for me. So I know if you were to type in jibber jabber. io, it has to go to, well, like a domain name server, like Google has 8888, right? So I think that's the big one. And then they say, Oh, that's gets routed to this subnet of the world.

[00:29:26] **Ben:** And it sends it to an IP address somewhere. If something like the IOD domain names were no longer being offered by the Indian Ocean Registrar, could Google step in and say, okay, that's fine for new domains, but we're not going to allow an entire segment of the internet to suddenly stop resolving. Can they step in and just say, anyone who uses our DNS servers, we will continue to route to the appropriate IP addresses.

[00:29:55] **Ben:** Or is that not how registrations work?

[00:29:57] **Tim:** Yeah. I think the gov, the governing body for registration is ICANN. ICANN.

[00:30:04] **Carol:** I can, yeah.

[00:30:06] **Adam:** Yeah, I mean, so, and, I mean, there's a, if you, if you Google up the articles, it's really interesting to read the history of all this stuff. Like there was a, in, oh, Yugoslavia, I think that there was like a, back in the days of the USSR, there was like a,

[00:30:21] **Tim:** Dot S U is Soviet Union.

[00:30:23] **Adam:** yeah, well, but there was a, I think it was yu or something, there was a, a TLD got stolen from the, the organization that, that ran it, right?

[00:30:32] **Adam:** Like literally somebody broke into a building and stole the equipment and, and the configuration,

[00:30:37] **Ben:** Oh

[00:30:37] **Adam:** It was in a university controlled it and they, they, stole the equipment and the, and the configuration in order to like administer this TLD. And so they just stole it and it was that way for like years until like one person with enough authority finally was like, you know what, this is friggin stupid.

[00:30:53] **Adam:** And he just like cut them off and, and gave new credentials to the university to go back and, you know, Own it again, but it was, yeah, it's crazy. So, I mean, I don't want to try and act like some sort of authority on this, but as somebody who has a io domain, like I was saying with Tim, you know, I, I'm trying to figure out my exit strategy, plan for the worst, hope for the best, you know, and I only have the one domain I feel bad for people who, well, I feel the tiniest little bit bad for people who like, there's, I think there's a certain type of personality.

[00:31:28] **Adam:** Of people who like buy dozens or hundreds of domain names in the hopes that either they become valuable and they can, you know, profit on that squatting or, or maybe they're like hoping to make a side project with it one day or whatever. But like, feel a little bad for people who have, you know, maybe 10, 20 of these domains that they have to deal with.

[00:31:48] **Adam:** And

[00:31:51] **Tim:** I've made tens of thousands of dollars of selling domain names over my lifetime.

[00:31:56] **Adam:** I'm just jealous.

[00:31:57] **Carol:** like you. Yeah.

[00:31:59] **Adam:** Yeah. I mean, for, for a lot of reasons, but

[00:32:02] **Tim:** but, whatever you do, don't, don't go to ai.cause, cause, cause basically there's one guy in, in, in Ghia who, sets the pot, the, the policy for the domain and those policies keep changing. So it's like,

[00:32:14] **Ben:** Nice.

[00:32:14] **Carol:** aren't the, aren't the costs on those just ridiculous to you right now?

[00:32:18] **Tim:** that he sets the, he can set the price and everything for those.

## [00:32:22] How TLDs Work

[00:32:22] **Ben:** that's, that's another thing I'd like to touch on. I don't, I don't understand why are different domains, different prices? And like, why are certain domains considered premium domains? what is, is that just completely arbitrary?

[00:32:35] **Adam:** it's,

[00:32:35] **Tim:** supply and demand.

[00:32:36] **Adam:** yeah, so, okay. All two letter TLDs. So TLD is the.com, dot.net, dot org. Dot edu. All those, right? the.io. It's the, the very, the, yeah, do dev, right? We're working code do dev. those are TLDs. Then there's S sld sec, second layer domain, or second level domain, right? So you've got your google.com.

[00:32:59] **Carol:** Google. co. uk or whatever, right?and so if you are, or let me back up, all of the two letter TLDs are Currently country code TLDs, right? Everything that's, all the country code TLDs are two letter, all the two, two letter TLDs are country codes. So if IO sticks around, that'll be interesting to see, cause now that's going to be like,A one off. Like,

[00:33:25] **Adam:** yeah, an exception to the rule.

[00:33:27] **Adam:** but, yeah, so, So actually, it was not even that long ago. I think it was maybe during the life of this podcast or, or shortly before it, that ICANN introduced a whole bunch of new TLDs, right? There's like pizza and there's, you know,

[00:33:41] **Ben:** ninja,

[00:33:43] **Adam:** Yeah, yeah. All, all of these dot TV. Actually, TV

[00:33:48] **Tim:** TV is a country

[00:33:49] **Carol:** Yeah.

[00:33:49] **Adam:** but it, it gets, obviously, co opted for television stuff.

[00:33:53] **Adam:** But anyway, so you could, I think there was, I think there was like, a proposal process for that and you could have like, you know, proposed a TLD and said like, and I think that there's a, there's a fee involved in like owning a TLD. And then, you know, And there's probably, you got to play the, you got to pay the VIG and like, protection racket, all that.

[00:34:15] **Adam:** But, and then as the owner, you get to set the, the price basically for, for domains. And so all these country code ones, like if you happen to be something that's going to be useful for like, you know, a web 2. 0 domain name, then. Then their demand goes up. And so price goes up. Oh,

[00:34:33] **Tim:** So, I mean, I think maybe a broader takeaway you take for this. Cause I remember who was it? Shannon Hicks. He had like a beer, like a beer rating kind of

[00:34:43] **Carol:** Oh, I remember

[00:34:45] **Tim:** Remember? Yeah. And I remember he put out. Like, this is back when Twitter was relevant. he put out some requests to say, Hey, I'm, I'm trying to find, a, a TLD for, for this app, you know, cause it's a beer thing.

[00:34:58] **Tim:** But the problem was that a lot, like, like the L Y was Libya. A lot of these countries that had these country codes that were, that made a nice name, were like, Muslim countries that didn't allow it. Their rule was no alcohol, no alcohol. You can't, your domain can't be. And so you don't think, you know, sometimes you don't think about that.

[00:35:17] **Tim:** You're just, you know, you have all these tools that you can go online. You put like the idea of your, your company you're putting in there. I mean, that's how we came up with PayCloud. io. We found what was available and that's what we named the company, right? That's like, oh, look at io's available. Oh, PayCloud's there.

[00:35:30] **Tim:** Let's buy it. Quick, quick, quick, quick. And so if you do that without like researching, all right, well, where is this like dot tv? That's a little tiny island a super tiny island, called, Tuvalu, Tuvalu. I don't know how to pronounce it. But anyway, it's it's barely above sea level and as Waters are rising this country's going to be gone in 25 years.

[00:35:51] **Tim:** It'll be just completely covered in water So there won't be a country anymore. So what's going to happen to dot tv? I don't know, you know, he's, people that,

[00:35:59] **Adam:** They're going to be like, it'll be like water world. They'll just switch to boats, a flotilla.

[00:36:07] **Ben:** water world. That's a, that's a throwback. It reminds me, you can't pee into a Mr. Coffee and get clean water. Well, let me ask you this. How many URLs do you manually type into the search bar anymore? Or like search your main gesture for navigating around the web? I still type Gmail. Or

[00:36:26] **Carol:** I do not type.

[00:36:27] **Ben:** com. I'll search, I'll

[00:36:28] **Tim:** I type Google into Google.

[00:36:31] **Carol:** I've done that before. Yep. Yep.

[00:36:33] **Adam:** I can't stand watching somebody like go, like type in google. com and then in the search type Facebook.

[00:36:40] **Carol:** Uh

[00:36:40] **Carol:** huh.

[00:36:41] **Adam:** My opinion of you goes to negative at that point.

[00:36:44] **Carol:** Yeah.

[00:36:46] **Ben:** things that I try every day. More or less. I I'll type it's not more, it's more like I'll hit the first letter and it's the auto suggest immediately. So like Facebook, LinkedIn, Gmail, I mean, those are

[00:36:59] **Adam:** we found him. We found the guy that still uses LinkedIn.

[00:37:05] **Ben:** YouTube I'll type the Y they all have different first names. So first letter. So it works out really nicely. But I'm, I'm trying to embrace the idea that the domain names just don't have to be short and pithy anymore, that you can

[00:37:18] **Tim:** Don't tell that to the marketing people.

[00:37:20] **Ben:** you can throw an HQ at the end, like the Basecamp people did, or an app at the end, like we did at work.

[00:37:27] **Ben:** I don't know. I would like people find your stuff. Doesn't seem to be such a huge issue anymore.

[00:37:31] **Carol:** Yeah, but when I am on like some results, if my first result is like an IO or let's switch it, say my second result is a.io and the first one is a.net, I'm not clicking on the first result. I'm going to the second because I'm assuming anything that's like a.net is no longer valid 'cause it feels obsolete.

[00:37:50] **Carol:** like.net is a thing, you know, like, so I, I do look at what is at the end, or if it's like UK I am like, probably shouldn't click on that at work. It's might get me in trouble. Like, let's not open this.

[00:38:02] **Adam:** it's like a bias toward Trendy or

[00:38:04] **Carol:** Yeah,

[00:38:04] **Tim:** Yeah, like, it's like those judgments you make about people that give you their email and it's like AOL. com.

[00:38:10] **Carol:** I know. Yeah.

[00:38:13] **Ben:** hard.

[00:38:14] **Carol:** Oh, my husband still has a hot mouth.

[00:38:16] **Tim:** Hotmail is my spam account. That's it. I give that to any, any, any, yeah, that's pretty much just only spam.

[00:38:23] **Carol:** Mm-Hmm?

[00:38:24] **Tim:** All

## [00:38:26] Picking a Domain Registrar

[00:38:26] **Ben:** don't, the other thing I don't quite understand about domain names is why certain registrars only support certain domain names. For example, I use, I've been using CloudFlare for most of my registrations. I've been slowly moving all of my domains from GoDaddy over to CloudFlare just

[00:38:41] **Carol:** Ooh. GoDaddy.

[00:38:43] **Ben:** CloudFlare as a, as a.

[00:38:45] **Ben:** Company and an application interface. It just seems nicer and cleaner. And GoDaddy is, I don't know, had some shady stuff apparently in the past. I don't feel that strongly about it, but for example, I have one domain name that I can't move, which is my bjam. in, which was my, my URL shortener. and Cloudflare as of yet does not, provide the in domain name.

[00:39:07] **Ben:** And I'm like, it just feels so arbitrary, but it feels arbitrary because I don't actually know how any of this works.

[00:39:13] **Adam:** Yeah, I mean, I'm sure that it requires some sort of agreement between them and the owner of the TLD that they can sell on their behalf and, you know, collect the money for them and transfer it to them and all that. Cloudflare, I also like Cloudflare as my registrar. One of the things that I really like about them is that they sell at cost, right?

[00:39:34] **Adam:** So they, you know, if you go to, ben del's domain registrar.com au,

[00:39:40] **Ben:** Yee

[00:39:40] **Ben:** uh,since you

[00:39:43] **Adam:** you're gonna buy the same domain, but you are, you're gonna pay the extra 50 Australian dollars for it so that Ben can line his pocket. And, Cloudflare just pays you, they charge you their cost, which is super nice. And I think that, you know, that for them, that's just like a, it's a loss leader, right?

[00:40:00] **Adam:** They're, they're losing money on that transaction because they're providing infrastructure to support that. But they're hoping that by providing that service to you and making it, you know, easy and more or less fun to use, then you will continue to use them for your DNS and for DDoS protection

[00:40:20] **Ben:** DNS as well, then if we can take a slight sidestep here to yet another thing that I don't quite understand, when I had mentioned to people that I'm moving my domain name registration from GoDaddy to CloudFlare, and then I would also mention, and I'm using CloudFlare for my name servers as well, the thing that resolves the.

[00:40:40] **Ben:** The domain name to the IP address of my origin server. People are like, Oh, that's a terrible idea. You don't want to put all your eggs in one basket. And I'm like, I don't know. Cloudflare powers like half the web. Should I be concerned about this? Is that a valid concern? Or is that like a doomsday or, you know, Oh, you should have stuff in Azure cloud and Google cloud and Amazon cloud at the same time for ultimate redundancy.

[00:41:03] **Carol:** You really wanna manage all of that?

[00:41:05] **Tim:** right.

[00:41:06] **Ben:** That's how I

[00:41:07] **Carol:** be real.

[00:41:07] **Ben:** I'm like, if, if, if Cloudflare is out for a bit, I don't know. The whole world is done,

[00:41:12] **Adam:** Right. Yeah. When AWS goes down, so does Twitter and Facebook. And you know, like,

[00:41:19] **Carol:** Airplane.

[00:41:20] **Adam:** you to work when half the internet is

[00:41:22] **Ben:** Right. I feel like when I have a hundred million dollars in venture capital investment. Yeah. Okay. I'll separate my name servers from my domain

[00:41:29] **Adam:** you know, honestly, like, I don't, I don't see how that makes anything any better except possibly for like, some sort of nefarious domain name takeover, like try to steal it from you through phishing or whatever. Right. Cause like, So what the, your registrar and, and the same company also provides your name server.

[00:41:54] **Ben:** That's how I feel.

[00:41:56] **Adam:** how is that a problem? I just don't understand it. Now, the, the part that I

[00:42:00] **Ben:** convenient?

[00:42:02] **Adam:** right, the, the part that I do kind of somewhat agree with is that like, it's, it's starting to feel a little bit like Cloudflare is getting a bit of a monopoly in terms of like, everybody is just moving there. for, for name servers in particular, because their service is just good.

[00:42:20] **Adam:** And like, you know, I, it feels a little bit like being mad at them for, for being so good at what they do, but at the same time, like the other side of that coin, you know, we've seen a couple of stories within the last year of like crappy HR practices and crappy sales tactics and stuff. And it's like, maybe they are getting a little bit, you know, too big for their britches or whatever, and starting to act like.

[00:42:43] **Adam:** The domain mob or whatever. so I have a, an element of pause around that.

[00:42:50] **Tim:** You sure got a nice domain there. Be shame if anything bad happened to it.

[00:42:56] **Ben:** Yeah. There's some of them at cost, plus protection money. No problem.

[00:43:00] **Tim:** I don't know if they sell at cost, but I use,AWS for my domain names. And that's because it's just, it's super easy to, to do where I'm already there. And, there's, they usually are a lot cheaper than GoDaddy. And I don't get the constant nagging marketing emails and upsells that GoDaddy tries to get you with.

[00:43:19] **Tim:** I guess. Cause they're like, well, if you're going to host it, you're probably gonna host it with us. So we're going to make money off of you anyway.

[00:43:24] **Adam:** Well, according to GPT4O, they do not sell at cost.

[00:43:30] **Tim:** Okay.

[00:43:31] **Carol:** AWS is it?

[00:43:33] **Adam:** Yeah, correct.

[00:43:34] **Ben:** I only just recently learned that AWS even had a domain registration feature. I mean, I learned this like two months ago. I had no idea.

[00:43:41] **Tim:** Where have you been, man?

[00:43:43] **Ben:** I'm registering stuff at GoDaddy. Apparently.

[00:43:46] **Adam:** Hey, he's, he's the, the world's biggest Danica Patrick fan.

[00:43:50] **Tim:** It's uh,oh man.

[00:43:54] **Adam:** So then, you know, what are the, the, like the long term takeaways from this? Like not the, the. io problem, but like, obviously country codes, like you, you mentioned TV and how the country itself might just, you know, cease to exist. does that mean we should never use them, but maybe like, I don't think that it means we should never.

[00:44:13] **Adam:** I just think that maybe you shouldn't build a business around it. Sorry, Tim, no shade intended.

[00:44:21] **Tim:** I'm sure they'll be, I'm pretty sure Mauritius is going to see all that money they can make off of it. And they'll be like, we'll take it over. Just give it to us. The prices might go up, but whatever.

[00:44:31] **Adam:** Yeah. I, I wonder if ICANN is going to be like, well, but you have to have some sort of, you know, legitimate claim to the, those letters, right? Like, is Marissa's going to, change its name to have like a I O somewhere in there,

[00:44:45] **Tim:** Mauritius of the Indian ocean.

[00:44:47] **Adam:** it'll, they'll change the spelling to, you know, M A R A T I O U S.

[00:44:51] **Adam:** So it

[00:44:53] **Ben:** I don't know why this just popped into my head, but there's all kinds of IP trademark issues around domain names. And I wonder if there is anyone who has purposefully named their newborn baby after a company like, oh, this is my son, JP Morgan Chase. And then like, then immediately tried to buy up like a JPMorgan Chase dot r ru or or ch or something to and,

[00:45:17] **Adam:** sounds like something Elon Musk would do

[00:45:18] **Ben:** Yeah. Cause then like, if, if Chase came after you and you're like, whoa, that is our intellectual property slash trademark. You can't be using that domain name. You're like, what? That's my kid's name. I don't know if that would hold up. I like to think that there's some creative people out there.

[00:45:34] **Tim:** As far as top, top level takeaway, I think. Yeah, like you said, before you like name a company after your domain name, make sure that the company that, or the country that you're, that you're getting the domain from is, is stable, right?which is funny cause it's like USA. I hardly, I don't think I've ever seen a USA domain name in actual

[00:45:54] **Carol:** Is it? I thought it was Start U. S.

[00:45:56] **Tim:** Is it US? Yeah. You're right. It'd be US, but I don't, is that just government? Is that just government only?

[00:46:03] **Ben:** one I

[00:46:03] **Carol:** no. All the government sites are gov. gov.

[00:46:06] **Tim:** Yeah. But I don't, I don't see too many us ones.

[00:46:09] **Carol:** Maybe Team America. I don't know.

[00:46:12] **Tim:** Harak? Yeah. Be careful with like the ly. I think Bitly ran into some issues when they,

[00:46:18] **Adam:** That was Liberia, isn't

[00:46:19] **Tim:** Liberia, Liberia was ly. So yeah, just, just do a little research before you pull the trigger on, you know, naming your whole company and future off of a, a two letter domain name. Right.

[00:46:31] **Adam:** Yeah, and it's going to make me think the next time I get that email that my 40 a year domain name is, that, that hasn't brought me, I think, any actual money in return. You know, when I get that renewal, I'm gonna be like, Hmm, do I really want this?

## [00:46:47] Domain Safety

[00:46:47] **Ben:** Yo, can I, sorry. This just made me think of something totally, mostly disconnected, but I'm gonna just go with it anyway. We'll have to do annual security training at work. And one of the things that they show you to do, or that they teach you to do is that when you get an email with links, you're supposed to mouse over the link so that you see the URL show up in the bottom.

[00:47:06] **Ben:** You're like, if this is an email from, from chase. com, you know, make sure the links are actually chase. com. This is an

[00:47:13] **Carol:** and not like Prizely.

[00:47:14] **Ben:** Yeah, exactly. But it gets so frustrating because everybody everywhere is tracking links all the time. So even if you get an email from chase.com, if you mouse over it, it's like eMarketing do campaigns.one click tracking, do you know this dot that, dot something else.

[00:47:32] **Ben:** And one thing that I would love companies to do, and I know this is way off topic now, but that made me think of it, is I, I, I would love at the bottom of every email for, for like an official. to be like, don't trust this email. But if you are like, you don't have to trust this email, you can go to this site and get to this functionality by taking these steps, because.

[00:47:52] **Ben:** So many times I'll get an email from Chase, which is my bank, and I don't want to click on a link because I know there's a bunch of shady people. but then I go to log in to my banking site and I have no idea how to get to the functionality that was the one click link from the email.

[00:48:06] **Ben:** And I just wish they outlined how to get to

[00:48:09] **Tim:** I'm, I'm with you

[00:48:11] **Carol:** so you bank at Chase. What's your favorite color? I'm just curious.

[00:48:16] **Ben:** Chartreuse, my second grade teacher, Mrs. Burdick, really enjoyed that.

[00:48:21] **Tim:** you, you, you lived on Drew Relayne.

[00:48:23] **Ben:** Yeah,

[00:48:24] **Carol:** Yeah.

[00:48:25] **Adam:** And what's your grandmother's weight on the moon?

[00:48:27] **Carol:** Yeah. Yeah. It's so funny, like we go through that same training, but whenever we hover over any link in our email, no matter what it is, it says like, outlook, do gc Safe Link. Do this giant hash. I'm like, well, is this a safe link? I don't know.

[00:48:46] **Ben:** Yeah. It's really, it's almost, it's like they're, they're going out of their way. I think oftentimes, well, at least the email providers now are going out of their way to try and protect you from, from tracking and, and image, whatever they call that, like the pig, yeah, the tracking pickles. Thank you. But by doing that, they're also then making it much more confusing for the people who are actively trying to understand whether or not something is necessary.

[00:49:09] **Ben:** Ha ha

[00:49:10] **Tim:** I agree.

[00:49:11] **Adam:** I wonder if there's like an opportunity there, right? So my first thought was like, okay, now the, the security practice needs to be anytime you want to click a link in an email, you open up a VM that has nothing in it

[00:49:21] **Ben:** ha

[00:49:22] **Adam:** and you, and you paste it in there. Right. But like, it sounds, it feels like there should be a way, right?

[00:49:27] **Adam:** Like even. It's not a foolproof thing, but like, even if you were to just copy the link and paste it into an incognito window and see where you land, right? Like after the, after the nine tracking redirects, where do you land? Is it Chase with a five instead of an S. com? Or, or what, right? And at that point, like, I don't know.

[00:49:49] **Ben:** That even that though, is one of those things where I'm not confident that I actually know what's going on. So I will, I'll do exactly what you're saying is every now and then I'll copy a link and open it up in incognito, because I believe that as long as the browser doesn't load with all my cookies, then nothing really bad can happen.

[00:50:07] **Ben:** But then I'm like, what if there's a big fundamental misunderstanding in how I think about security? And this is actually really dangerous for me to do. Like, yeah, maybe it's not a cookie issue. Maybe this is going to download an EXE somehow and execute it.

[00:50:20] **Tim:** And, I mean, think about this, we're four people who have been in tech for

[00:50:23] **Ben:** Right?

[00:50:24] **Tim:** And we're worried about this. What are your, our parents and grandparents? I mean, and these people, you know, they don't stand a chance. No wonder.

[00:50:34] **Carol:** my husband is so gullible. He's just so gullible.

[00:50:38] **Adam:** Don't.

[00:50:39] **Carol:** I am constantly, constantly getting notification on my phone. We have the Deco system, like a T Link, like a home mesh system. And, I'm constantly getting messages from Deco. We've blocked this for malware. We've blocked this for suspicious activity.

[00:50:54] **Carol:** Like, this is known for stealing data. Like, we've blocked this site. And I would, like, look at my husband and he's just, like, scrolling the internet, just happily going along. Something getting low he didn't even know.

[00:51:05] **Tim:** Click, click, click.

[00:51:07] **Carol:** Yeah. I like that ad. I want to buy that pan for Christmas. You're right.

[00:51:12] **Ben:** good. What

[00:51:15] **Tim:** It's crazy.

[00:51:16] **Adam:** he was, he was on Only Pans

[00:51:18] **Carol:** Yeah. OnlyPants. io. Yeah.

[00:51:24] **Tim:** well, here's kind of a throwback, we're kind of done talking about the domain names back to the days when there were like no domain names. We had bulletin boards, bulletin board systems way back when I'm, I'm an, I'm an elder Gen X er here kind of talking. So I used to run a, a bulletin board systems.

[00:51:45] **Tim:** And so these were like dial up modem days. So you'd like, I would go to like the local, drugstore and they'd have a big giant computer shopper magazine. And the back of it was just like 50, 60 pages, just phone numbers. And you could put those phone numbers in, hook your modem up to the computer and then call that phone number and then you could get on there and it was like a, you know, no graphics, nothing, it's all text

[00:52:09] **Adam:** You, it didn't, it didn't say Welcome. You've got mail

[00:52:12] **Tim:** no, this is, this is pre, pre those days.

[00:52:15] **Tim:** And, you know, you could, you could like play some rudimentary like text games. MUDs and like share files and just chat boards and things like that. So I did one of those when I was 15, but I bring that up because, someone on our discord posted that Ward Christensen, who's like, he was the inventor of the BBS system.

[00:52:32] **Tim:** He died a couple of days ago at the age of 78. But what I love about this guy is he was like, you know, you think about these like big tech moguls are all just super self centered, kind of flashy people that just, You know, they're all about their presence and their persona and their brand. This dude was just chill. He worked for IBM and retired from IBM and created the BBS. And he didn't go out there and like dump his chest and do whatever. He just gave everything away for free.

[00:53:01] **Carol:** Oh wow.

[00:53:02] **Tim:** He came up, the, one of the protocols that he developed was one of the super early protocols for, for, computer modems was Xmodem. And so he created Xmodem so that, that way, cause you're on these phone lines, the phone line quality was not good, you know, it was scratchy.

[00:53:16] **Tim:** And so it would, you know, do the check sums and everything. And if it was bad, it would resend. So he had a pretty decent connection. You could, you know, you could get through his super slow, like 300 baud. But, yeah, so I just, I'm going to take my tip of the hat to Ward Christensen for the work he did and just, just being, being a good guy.

[00:53:32] **Tim:** Yeah. Early days of internet, I really thought that the internet was going to change the world in a good way.

[00:53:38] **Carol:** Yeah.

[00:53:39] **Tim:** The

[00:53:39] **Adam:** wrong you were

[00:53:40] **Tim:** how wrong I was, you know, I thought it was going to be a democratization of, of information and knowledge, and now we have access to all this information and we realized that lack of information was not our problem, it was lack of intelligence.

[00:53:57] **Ben:** what were, what were use groups? I vaguely remember being, typing Usenet. Was that a, was that a BBS related thing or this was a separate system?

[00:54:07] **Tim:** That was a separate system. I've actually, early Usenets I think were actually, you could do via email. But then they did like an

[00:54:15] **Ben:** Yeah. They were like message boards where you

[00:54:17] **Tim:** Kinda, but you could also share files. You could. You can download things, more like a file transfer kind of thing that you could do with Usenet.

[00:54:29] **Carol:** I will say,

[00:54:30] **Adam:** experience with that book. Mm-Hmm.

[00:54:32] **Carol:** if I had little kids, there's one thing I would do now that I never did to mine. I saw a video of a mom that made her kids sit on the couch for like two minutes and listen to like, the dial up sound. You know, the beep boop, and like, every time, their phone, yeah, it's awful, right?

[00:54:49] **Carol:** Like, we remember it. But every time her phone got like a notification, the mom would make her sit there and restart it over again. Cause she's like, you can't use your phone and be on the internet. Like that doesn't work. You're going to have to disconnect and reconnect again. Like you're going to appreciate this internet connection.

[00:55:05] **Adam:** That makes me wanna change my notification sound to the modem, like connection handshake thing.

[00:55:12] **Carol:** I would be, I would be so stressed out.

[00:55:15] **Tim:** I remember I would spin like a friend of mine before I had a computer, before my dad bought me a computer. I was like 14, 15. I go over to my best friend's house. He had a TRS 80. RadioShack computer with the, we took the, the phone, you took the phone off the rotary phone, right? With the handset, you take that off, you dial the number and then you'd stick it like this little cups, these two cups for the, for one for the ear part, one for the mouth part.

[00:55:40] **Tim:** You'd stick that down the cradle and we spent, we would spend all evening, we'd never connect. It's like we'd spend all evening diagnosing why we can't connect. And try to figure out what the issue was and not, you know, four or five hours. We would go by the entire evening trying to figure it out and maybe connect for like a minute or two.

[00:55:58] **Tim:** And like, we, we thought we had just won the world. Like we're making change, buddy.

[00:56:05] **Adam:** Spoiler alert. It was DNS.

[00:56:08] **Tim:** Exactly. Cloud, Cloudflare was down. This is pre DNS. There was no web, there were no web addresses. You just had a phone number you called.

[00:56:17] **Adam:** know I was just making a DNS joke.

[00:56:19] **Tim:** Yeah. So anyway, thank you Word for your service. Rest in peace.

## [00:56:24] Patreon

[00:56:24] **Adam:** okay. okay. Well then, since they're making me do this, this episode working code was brought to you by my, my new TLD pans.and, and, and,

[00:56:33] **Tim:** Only pans.

[00:56:34] **Adam:** That's right. Only dot pans. and, and listeners like you, if you're enjoying the show and you wanna make sure that we keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:56:44] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks of course to our top patrons, Monte and Giancarlo. You guys rock.

## [00:56:53] Thanks For Listening!

[00:56:53] **Adam:** We are gonna go record our after show, which is where we just keep the mics on after the outro music plays, and we keep talking about whatever's on our minds.

[00:57:00] **Adam:** I have, another fail I'm going to bring up this week on the outro or on the after show, it looks like Carol is going to back to, to, to Georgia, visit, some family. So we'll, we've got some interesting stuff to talk about. if you'd like to help us out, you can go to patreon.com/workingcodepod, throw a few dollars our way and we would be very, very grateful.

[00:57:19] **Ben:** Yo. Can I just, before Tim goes, I just wanna interject with another win of mine is I met,Monte and Giancarlo at CF Summit and I didn't even realize, I mean, I, I, I know Monte 'cause he appeared on the show before. I had never, I didn't know who Giancarlo was by face and I had been talking to him and he said something about the show and I was like, wait a minute.

[00:57:39] **Ben:** Are you the Giancarlo of this show is brought to you by Giancarlo? He was like, yes, I am. And I also met Sean Oden. Sorry. I forgot to shout out all the, the working code people.

[00:57:50] **Adam:** that's

[00:57:51] **Tim:** even, they even wore their t shirts.

[00:57:53] **Ben:** And yeah.

[00:57:53] **Tim:** working code.

[00:57:54] **Ben:** it's so good. It's so good. And, yeah, it's just really good.

[00:57:57] **Adam:** indeed.

[00:57:58] **Ben:** And Cronin. Sorry. Oh my God. I can't remember her first name all of a sudden.

[00:58:01] **Ben:** Sandy Cronin. Yeah. I've just met a bunch of people. Everybody was so great.

[00:58:04] **Adam:** Yes. And probably there were some people there that, don't go by their name or that are listeners, but don't participate in Discord, that sort of thing. So, if you met Ben, I apologize.

[00:58:15] **Tim:** If you met

[00:58:18] **Carol:** doesn't people well. Yeah.

[00:58:19] **Tim:** met Ben, it was definitely before 9 PM.

[00:58:21] **Ben:** Yeah, that's for sure.

[00:58:24] **Adam:** All right. that's going to do it for us this week. We'll catch you next week. And until then,

[00:58:28] **Tim:** Unlike DNS guys, your heart matters.

[00:58:31] **Adam:** DNS matters.and you can read it all. Read, read all about how much DNS matters on my website, which is 1 7 4 3 9 2 5 2 11.anyway,

[00:58:45] **Tim:** Mine's, mine's an IPV6, so.
