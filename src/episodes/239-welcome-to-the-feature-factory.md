---
title: "239: Welcome to the Feature Factory"
description: "When developers burn out from building features without understanding why, Carol explores how teams can reconnect work to meaningful outcomes."
date: 2025-11-20
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/78c9a98f-7250-4bfc-99e5-a26eb8adf6bb"></script>
<div class="redcirclePlayer-78c9a98f-7250-4bfc-99e5-a26eb8adf6bb"></div>

How do you stay motivated when you're stuck building features you don't understand? Carol brings a conversation she's been having with her team about feeling like a "feature factory"—churning out work without clarity on what problem they're solving or what value it adds. When every standup is "is this done?" instead of "have we made anything better?", burnout follows fast. The hosts explore the tension between customer-driven features, competitive pressure, arbitrary boss decisions, and the human need to feel connected to meaningful work.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/239-welcome-to-the-feature-factory.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Cold Open

[00:00:00] **Carol:** when you start feeling like the work that you're putting out is just features with no understanding of what you are delivering on, then developers just kinda get burned out.

[00:00:10] **Carol:** every single day in standup. It's, is this done? Is this done and not, have we made anything better?

## [00:00:37] Intro

[00:00:37] **Adam:** Okay, here we go with a show number 239. On today's show, we're gonna talk about not driving your own product roadmap and also how Ben, once again destroyed half the internet today as

[00:00:46] **Carol:** Ben,

[00:00:47] **Adam:** this.

[00:00:48] **Adam:** Benjamin what do you have to say for yourself?

[00:00:50] **Carol:** have you been in CloudFlare again?

[00:00:52] **Ben:** from my mistakes.

[00:00:54] **Adam:** but first, as usual, we'll start with the tris and fails. Tim has an excused absence tonight. He's da at a company dinner, probably eating some sort of animal testicles. and so Ben, I'm coming to you first, my friend. What's going on?

## [00:01:07] Ben's Triumph: Open Graph Image Generation

[00:01:07] **Ben:** I'm gonna kick us off with a triumph, and that is that, as I've mentioned before, I'm working on this poetry application mostly as a learning context. And one of the things you can do in it is create share links. So if you wanna share a poem with a person or share it more publicly on a social platform, you have this public, token based link that you can pass around.

[00:01:29] **Ben:** Now, a lot of people are probably familiar that when you share something in a social context, whether it's in Slack or Facebook or LinkedIn, oftentimes you will get a little preview of what that link is going to be bringing you to. And that information there is in part driven by something called open graph.

[00:01:49] **Ben:** Which is really just a set of meta tags in your HTML that say like what the title is, what the description is, is there an image associated with this link? And if there is, it'll, it'll try to render it. So I have created a custom open graph image for my poem links, and it's all done with ColdFusion and CF image and some lower level Java stuff.

[00:02:15] **Ben:** But basically, a poem isn't necessarily something that lends well to a, you know, a 16 by nine ratio image that a, that like a rich graphic would really lend well to. So I had to make some, you know, concessions on how to lay that information out. So if you think of a poem as having a title and content, copy, whatever you wanna call it.

[00:02:39] **Ben:** I am ignoring white space in the poem. So poems usually have shorter lines and they have line breaks, and I'm just stripping out all the line breaks.

[00:02:47] **Adam:** wounded from this

[00:02:48] **Ben:** I know.

[00:02:49] **Adam:** the white

[00:02:49] **Adam:** space.

[00:02:50] **Ben:** so I'm turning it more into prose. I'm just basically taking every new line and replacing with the space. so then I have basically one line of title and one long line of content.

[00:03:00] **Ben:** But of course, in order to render this in an image, I can't just have texts going off the edge of the page. So the trick is to figure out within the constraints of the image, which are a known dimension, it's like 1200 by six 40 or something. when can I wrap the text? So if I'm rendering the title, how many words in the title can I get before I actually have to move, you know, like a line feed down and start the second line of text.

[00:03:25] **Ben:** And cold fusion doesn't really have anything for that, but the layer below cold fusion, Java does, you can essentially create these. Text layout instances and you can say, here's the text I'm trying to render. what's the bounding box and what's the ascent of the text from the baseline and what's the descent from the baseline down to the, the little dangly bits?

[00:03:44] **Ben:** so I essentially, I, I, you know, through a bunch of trial and error, I came up with an algorithm where I try to render a word and I see what the bounding box is, and if it fits on one line, then I try the second word and if that fits on the same line, then I try the third word and so on until I can't fit it.

[00:03:59] **Ben:** And then I start a new line and I do the same thing. And, I did that for the title and that for the content. And ultimately I was able to render, an open graph image on the fly, which can have, you know, one line of title and five lines of poetry or like two lines of title and three lines of poetry or something like that.

[00:04:18] **Ben:** it took me a couple mornings 'cause I only squeezed little, you know, an hour here and hour there. But, I'm pretty pleased that I got it working. Pretty pleased as punch. And I think ultimately, even though it doesn't represent the, the feel of a poem, the visual feel of a poem, I think from a preview standpoint, I think it's the best I'm gonna do.

[00:04:38] **Ben:** So I'm pretty happy about that.

[00:04:40] **Carol:** That's cool. Congratulations on doing something kind of neat. I feel like this is coming with a, but.

[00:04:45] **Adam:** now that it's behind you and you're done and you're ready to move on to the next thing, did you think about doing like maybe a word cloud instead? Like that might be an interesting visualization of the poem.

[00:04:56] **Ben:** A word. So word cloud for the, for myself and for the users clarification. I'm used to thinking of a word cloud in terms of a very large body of work where you're sort of making certain words of higher popularity, bigger and smaller kind of a thing. that's an interesting idea. I don't, I don't know if I.

[00:05:13] **Adam:** how well it would translate to a poem.

[00:05:15] **Ben:** Yeah, it, but, but, but I do think there are things that I can do to make it more visually interesting. For sure. I think I went down the rabbit hole so deep on just trying to get the maths to math, so to speak, on all of the, the line breaking and the measuring and the line heights. And I did briefly consider trying to learn about puppeteer, I think does the sort of headless chrome where can take screenshots.

[00:05:44] **Adam:** Hmm. I think you're right. Yeah.

[00:05:45] **Ben:** which, you know, it's like the moment I started to look into that, it was like, oh yeah, you're not gonna wanna boot up a headless chrome on every request. 'cause it has a lot of memory. So you're gonna want to have a process. It's like always running and having chrome open so that you don't have this cold start for the chrome every time.

[00:05:59] **Ben:** I'm like, ah, that's too much work already.

[00:06:01] **Adam:** Why are you regenerating this image on every request

[00:06:04] **Ben:** well, so the next thing I wanna do is add some caching to it. I am right now in the middle of IE everything I'd run right now is behind Cloudflare, which, you know, again, slayer for taking down the internet. Uh,but you know, theoretically I can put some CDN based caching on this so that it's not necessarily generated at all the time.

[00:06:25] **Ben:** But as far as why generated at all ever, because the image has title content and copy content, presumably the moment that the user changes any of that, I'll have to regenerate the image or I guess blow away the cache. blowing away the cache would probably make more sense so that I'm not constantly regenerating it every time they're changing the content.

[00:06:49] **Ben:** but yeah, that's, that's definitely something I could do. I right now I could take all of the logic for generating it. Right now it's really just directly in the view. 'cause it was proof of concept more than anything else. I can, I can move it into, to more of. Businessy logic, e servicey layer kind of thing and call it from anywhere.

[00:07:09] **Ben:** I'm just happen to be calling it on the fly right now, So.

[00:07:12] **Adam:** You generating PNGs or like a WebP

[00:07:15] **Ben:** PNG. Yeah,

[00:07:16] **Adam:** okay,

[00:07:16] **Ben:** but so here's the other, the complexity that I was just looking into right before we joined the recording here is even if I want to cache it in Cloudflare, because it is a CFM file, the Cloudflare apparently will not cache it even if you have cache control headers in the response.

[00:07:34] **Ben:** 'cause I, I think it doesn't look at the cache control headers prior to determining whether or not it's gonna cache this at all. So I think I have to add a, some sort of caching rule to say, Hey, you can do CFM files, but then I'm nervous that I'm gonna start caching stuff I shouldn't cash.

[00:07:51] **Adam:** Right. Well, so I, I don't know about Cloudflare specifically, like the way that they're detecting that, but I have I've run into similar challenges in the past and the thing that I did, 'cause I just added like a URL a query param to the URL that I'm not even like using for anything other than to just make it look like an image request.

[00:08:08] **Adam:** So it's like,you know, whatever. Do CFM question mark, type, equal image PNG or whatever. And like the, the URL ends with PNG and they're like, okay, cool.

[00:08:19] **Ben:** Oh, that's interesting. I'll try that. 'cause that would definitely be,

[00:08:23] **Adam:** I wonder, it may not work as a PNG, but if you could do something like, you know, ColdFusion usually supports, i, I call it path info. I don't know. but like you can do, you can just keep adding slashes after the CFM, right? So you do like index CFM slash image PNG or whatever, like just ignore that whole CGI crap that gets added after, the index dot CFM.

[00:08:46] **Adam:** And then it looks like that's the URL even before a question mark, right? Any even reasonably, intelligent system's gonna chop off the question mark. Everything after that to determine file type. So

[00:08:58] **Ben:** That, that's a solid idea. I like that. I'm gonna, I'll try that tomorrow. Tomorrow morning pre-work.

[00:09:05] **Adam:**

[00:09:05] **Ben:** yeah, so anyway, that's my triumph. I felt pretty solid about that. Happy about that. So I will kick it over to Carol. What do you got?

## [00:09:11] Carol's Failure: The Disintegrating Chair

[00:09:11] **Carol:** I think I'm gonna take, Tim's spot since he's not here today, and I'm gonna go with a failure and a triumph, so I'm gonna do both. All right. So I'm gonna start with my failure because it's failure because I don't know how to fix it. It's kind of funny. I'm sitting at work today, you know, at home in my desk chair, and all of a sudden a bolt falls out of my chair.

[00:09:32] **Adam:** Is that why you're sitting on a floor?

[00:09:33] **Carol:** I, I roll my chair around, another bolt falls out and a washer. I can't find where these bolts came from, but throughout the day, throughout the day, multiple times my chair would go from its normal, like resting spot to just completely deflated and drop me down.

[00:09:51] **Adam:** Oh. Like the piston that

[00:09:52] **Carol:** yeah, yeah. I was like, this isn't good.

[00:09:56] **Carol:** So I would like press the thing on the side and it would go back up and then a little later I'd be fidgeting around and it would just fall back down. So, I'm gonna have to have my husband look at the chair, I think, 'cause I don't know where these holes are at, that these bolts are missing from

[00:10:11] **Ben:** pranking you. You got pranked.

[00:10:14] **Adam:** even got LAC on it. Look at that. That's crazy.

## [00:10:18] Carol's Triumph: Outstanding Annual Review

[00:10:18] **Carol:** So, but my triumph is today I have my annual assessment. They were delayed because of the government shutdown and the furloughs in place, so we weren't able to go over them just yet. So I got mine today and I got outstanding across the board. So I'm super, super happy with that. 'cause this year's been a challenge.

[00:10:35] **Carol:** This year's been hard. It's, it's pushed my limits.

[00:10:39] **Ben:** point of clarity, 'cause time means nothing to me anymore.

[00:10:43] **Ben:** Is this your first review since you've taken a managerial role?

[00:10:46] **Carol:** Yep. I'm not, I'm not manager, so I'm not in a management role. I don't do any supervising. My title is Lead It, enterprise Solutions Architect. So I,

[00:10:57] **Ben:** review since that change?

[00:10:59] **Carol:** It's my first review in this position. So, yeah. So super, super happy. Yeah. To be. To be told I'm doing a good job when there have been days that I just cry and don't know that I'm doing that well.

[00:11:12] **Carol:** So it was good to hear the, the praise and to hear that my customers are happy with the success that we're providing overall. The, the customer service they're getting from me and my team is happy with the leadership that they're getting. So I just, I feel like a big winner today. Yay.

[00:11:28] **Ben:** Congratulations.

[00:11:29] **Adam:** Yeah.

[00:11:30] **Carol:** Yeah, thank you.

[00:11:31] **Carol:** Yeah, but Destiny's, what about you, Adam? What have you got?

## [00:11:34] Adam's Triumph: Cursor AI Success

[00:11:34] **Adam:** I'm gonna go, with the triumph myself. this is not so much for work. This is more like side project stuff, but it, it counts. I've just been really happy with having Cursor code for me. you know, so I've, I've talked in recent episodes about, giving Cursor another try. They have their own model now available.

[00:11:50] **Adam:** I'm paying for it outta my own pocket. it's been a little bit of a bumpy road to kind of figure out the best path to make it work. But like, just for example, you know, I stopped work today a little after five, ran downstairs and was kind of chatting with my wife while I was working, air quotes, working on something.

[00:12:05] **Adam:** I was working on jump run and, and I had this idea for a feature. It's like, okay, cool. Well, it couldn't have been more than 30 words, right? This, I just wrote a prompt. I said, here's some files that I think are gonna be relevant as context. Here's my idea for a feature.

[00:12:17] **Adam:** Kind of roughly laid it out and said, go. And, and it built a plan. And I, it, it, I mean, I think that's the biggest part of this, like agentic coding stuff, is it seems to do better if you have it, do a plan. So you gotta like, okay, build a plan and then I go review the plan and that takes five minutes to like, you know, carefully read a markdown file that it generates.

[00:12:37] **Adam:** I'm like, okay, that's close enough. You know, like, I'm not gonna waste the, the, the time and the, the tokens to say, well, okay, you made this one little change and I don't really care about that in particular. It'd be easier for me to just like, let it code it and then I'll go rip that out myself.

[00:12:51] **Carol:** it out. Yeah.

[00:12:52] **Adam:** So, you know, take the time to read that and they're like, okay, cool.

[00:12:55] **Adam:** Build it and it builds it. and I have like, in my environment, I have it set up to like, okay, this is how you can run the TypeScript linter to check for type errors and this is how you can run the tests and stuff. and so it like makes, it changes, it runs the test, it runs the linter, oh, there's two TypeScript errors and goes back and fixes those.

[00:13:10] **Adam:** And then it's boop all done. And I look at it and it's like. Perfect. Just go rip out that one thing. It did exactly what I wanted. and I even like, you know, I said, use a responsive dialogue, right? So this app is intended for most of the users to be using it on their phone, right?

[00:13:25] **Adam:** They're at the drop zone, they're just like trying to get on a load or whatever, or maybe they're checking their data at the end of the day. And so it's in it's small screen first. And so I have this component called a responsive dialogue, which when you're looking at the app on a full, like, on your computer, right?

[00:13:41] **Adam:** You got this like 16 by nine aspect, monitor it pops up as like a modal, right? But on your phone, you really don't have room for modal stuff. So it just comes up as like this, it slides in from one of the sides of the screen and it just takes up the whole screen, right? It's like cover the whole screen and then just there's your, your quote unquote modal or whatever.

[00:13:58] **Adam:** and so I was like, use the responsive dialogue. I didn't tell it where it was. I didn't tell it anything. It just, it kind of figures out from context in other files or other components or whatever. And, it, it just was like perfect. So I'm, I've been really happy with it. It's take, like I said, it's been a little bit of a bumpy road to figure out the best way to make it work, but, I'm happy with it and it's, it makes me happy to just be getting stuff done.

[00:14:21] **Carol:** How long have you been working on it?

[00:14:23] **Adam:** I guess what, I had a two week free trial and I think I've been paying for it for about a week, maybe a week and a half now, two

[00:14:28] **Carol:** So I re I remember you mentioning that you were gonna look at how many tokens you used and if it was worth it or not. I guess you're not at that point yet. Right. Okay.

[00:14:37] **Adam:** It's tough to say. I, part of the problem and the reason that I haven't been using it at work so much is because the work I'm doing for my job has been when I'm coding, which is not all that frequent right now, but the work that I'm doing is incredibly specific and it's like, I don't feel like any model does like super well with ColdFusion.

[00:14:55] **Adam:** Like it gets the basics and, and stuff, but I don't feel like it knows. That language anywhere near as well as it knows like JavaScript and Svelte and stuff. But, yeah, I mean C Sharp, Java, I mean, all of these things. Python, I'm sure it's like, you know, pretty darn, pretty dang good at,

[00:15:14] **Carol:** split and pretty good. Yeah.

[00:15:14] **Adam:** so like for example, the stuff that I've been working on for the last couple of days has been like updating this interface in our app where you can, specify like a bunch of HTML colors that will then be used in a different area of the app, right?

[00:15:27] **Adam:** It's like admin and use, you can customize the skin that you're putting on the, the white label, public facing side of the stuff.and there's like color swatches and, and all kinds of stuff. And it's, it, it's the amount of work it would take me to like, figure out how to ask for what I want in the prompt and then read through the, the plan and then go back and like check the work that it does.

[00:15:47] **Adam:** I might as well just build it myself. So that's what I do. I haven't been doing that. But to, I guess more directly answer your question about volume, like the, is it worth the value or whatever. So if I pull it up now, I just minimized it before we started.

[00:16:00] **Ben:** I, I've used 33% of my limit, and like I said, I think I've been on the paid plan for about two weeks now. Okay, and that's per month.

[00:16:08] **Adam:** it's probably more like, more like a week and a half. and, and that's for a month's worth. like the billing period is a month. I've been, I'm a week and a half into it, so about a third and about a third roughly, I think.

[00:16:18] **Adam:** so that's not bad. And honestly, I'll say like the first 20% of that or so I burned through quick. I, I don't remember what I had it do. But I, I do think that, doing the, the, the plan and then build the, from the plan approach saves a ton of tokens. Like if you just give it a big prompt, if you, if you give it like four paragraphs of text and say.

[00:16:39] **Adam:** If this is what I want you to do and just go do it, then it spends a lot of time, like, a, it takes a lot of time, but b there's a lot of like, iteration, looping, and I'm, from what I understand, it runs your prompt and then like it does a step or, you know, it does some, some amount of work and then it kind of has to reevaluate where it is in the process.

[00:17:01] **Adam:** And so it like reruns with your original prompt, the output of your first prompt

[00:17:06] **Adam:** and

[00:17:06] **Carol:** close am

[00:17:07] **Adam:** some additional stuff. Yeah. Right. What's next? the iteration, like every time it's kind of not fully, exponentially growing, but it is like ballooning quickly. Right. And I feel like that was a, a quick way to, to burn through tokens, whereas now I'm trying to be a little bit more economical with it.

[00:17:21] **Adam:** Like not asking for dumb stuff and not making my ask too big. Like try to be thoughtful about being. Small chunks. Oh, that was the big thing that I did. one of the first things that I did that burn through a bunch of tokens was like, just write tests for my app. And it's like, okay, cool. I'm gonna write Playwright tests and I'm gonna write Vitest tests and like all this stuff.

[00:17:41] **Adam:** And it generated like 50,000 lines of code, and like 70% of the tests were failing. And even though I was like, the tests are failing, try again. You know, it's just like churn, churn, churn, churn, you know, meanwhile, like, you know, I feel really bad about the water usage and the electricity usage and all that, but like, it was garbage.

[00:17:59] **Adam:** I ended up throwing it all away and, and that was

[00:18:01] **Carol:** said that you deleted All

[00:18:02] **Adam:** Yeah. I just totally threw it away. And I went back and I was like, okay, we're, we're gonna write just this kind of test and just for this file, blah, blah, blah. And, and it did it, and it it one shot of that. And then I was like, okay, now we're gonna add tests for this and it one shot of that.

[00:18:16] **Adam:** And it just like, if you, if you are willing to kind of babysit it more, I feel like it does a lot better. So

[00:18:22] **Carol:** Yeah, that's what I do when I'm doing tests. I get very specific and there have been times when I get a response of, it would be better if you refactor your code kind of thing and let's go look at how to refactor it so we actually can test this. I'm like, perfect, I can handle that. Just don't try to test this whole file.

[00:18:40] **Carol:** 'cause I don't check that in. My developers don't wanna see a PR that big.

[00:18:45] **Adam:** Yep.

## [00:18:46] AI Coding Discussion

[00:18:46] **Ben:** I've never actually motivated to try this, so this is all just me thinking out loud. I have now several times, you know, I do a lot of hemming and hawing and hand ringing about how all this AI stuff works.and I'm, after I struggle with a task, like I'm talking about creating these open graph images and it took me a couple of mornings and a lot of trial and error with the math and dropping down to the Java layer.

[00:19:08] **Ben:** I always, when I'm done with something like that and I have a moment to exhale, I'd almost want to revert back to an earlier commit so that I don't have any of that. And now that I know exactly what I wanna build, try to get AI to build it for me. 'cause I think a lot of the hemming and hawing that I have is that how do I know that the thing that AI is gonna build is actually the thing that I wanted to build And not just like a thing that gets me to a solution that is acceptable.

[00:19:38] **Ben:** Like acceptable is not necessarily the thing I wanted, but it's the thing that'll do. and I'm not, and I'm not saying that in an, in like a dismissive way. I guess my thing is like I, when I have a very clear vision in my head, I don't know if I can get the AI to do that thing for me.

[00:19:53] **Adam:** Mm.

[00:19:53] **Ben:** and now, so it's like I, I get to the end of these tasks that, that I really spun my wheels on and I want to go back and say like, now can I have AI do this?

[00:20:02] **Ben:** Knowing very specifically about a litmus test that says, no, I can't get it to do this, or, or, yes, absolutely I can if I have all the right words and incantations. but like I said, I've never actually motivated to try this.

[00:20:14] **Adam:** Yeah, that's a really interesting pers like perspective or, or situation you find yourself in. it's funny, I often find myself like almost the exact opposite. I usually think and, and kind of figure out what it is that I want to do by writing the code. Like pre ai, I thought in code, right? I was like, okay, the only thing I could, you, you've said, what was it?

[00:20:36] **Adam:** You can't.think about, think deeply about something until you write it down. I

[00:20:39] **Ben:** Yeah. Yeah, a hundred

[00:20:40] **Adam:** and I, for a long time, I feel like I've been the same way about code, right? I have to get that first chunk of code outta my head so I can think about what comes next. And this whole exercise has been just forcing me to take a minute and think about, okay, what, what outcome do I want and how do I want to get there?

[00:20:59] **Adam:** And that has been really like, that's a helpful way to prompt the, the AI stuff, but

[00:21:03] **Ben:** It's all fascinating. I just need to motivate to actually do it. I dunno why I, I just, it's like even this little thought experiment. I feel like I put so much effort into writing the code that by the time I do finish it and I'm tempted to try something like this, I feel like I'm already so emotionally drained and like out of time that I'm like, ah, maybe next time.

[00:21:25] **Ben:** And then, you know, rinse and repeat.

[00:21:27] **Adam:** yeah.

[00:21:28] **Ben:** Now that the Google just dropped their,

[00:21:30] **Ben:** what is it called? Anti-gravity or something?

[00:21:33] **Adam:** Yeah, I, so that's another thing that happened today. Yeah. so it's a, it's a, it looks a lot like a Cursor fork, although I believe it is kind of, somewhat of a, like a spiritual fork of Windsurf. like it's, it's got fingerprints in it from Windsurf. what is the, I think it's called Cascade is like the, the name of the agent in Windsurf.

[00:21:55] **Adam:** And if you're poking around in the anti-gravity thing, every now and then you'll see the word cascade pop up. So it almost looks like they, forked it did cut, find and replace. It didn't get all the, the places where it was referenced. but I did download it. I haven't even opened it yet, and I, I have watched a couple of videos about it, like people kind of, here's what's up sort of situation.

[00:22:17] **Adam:** And every video I've seen has been like, it's got some interesting ideas, but this whole thing is just half baked. Like it's,

[00:22:23] **Ben:** Hmm.

[00:22:25] **Adam:** Uh,

[00:22:25] **Adam:** the one thing that's, yeah, the, I mean, I, I hope that it's just like we have to launch now 'cause we need hype and, we gotta get people's attention. This might be a good moment and we'll fix the problems next week.

[00:22:36] **Adam:** I hope that they're still churning hard on it and, and gonna push it forward, but, and that it was just like, somebody up high made the decision, like, no screw waiting for it to be good. Let's just launch and we'll make it good as we go. The, the one thing that's really interesting and, and helped me make the decision to at least install it so far, and want to play with it, is that for now it's a hundred percent free.

[00:22:58] **Adam:** Like all, and, and supposedly the, the Gemini 3 model in it is really good.

[00:23:05] **Ben:** also like just launched today or

[00:23:07] **Ben:** yesterday?

[00:23:07] **Carol:** Mm-hmm.

[00:23:08] **Adam:** I think they launched it at the same time. Yeah. so I mean, it's not gonna be free forever, but you know, it's at least. To me, that makes it worth checking out. Right? It's, I've been getting good results with Cursor. If this is, there were some things, like the one thing that I saw, I told you, you know, I like to do the plan and then build the plan thing.

[00:23:26] **Adam:** the one thing that I saw was like, you can have it build the plan and then like you, as you're reading through the plan, you can kind of hover your mouse over, individual bullet list items or whatever, and there's like a thing that pops up and you can just like a little button next to whatever.

[00:23:37] **Adam:** But you can say like, you can get feedback on individual lines of the plan instead of having to reply to the planning prompt results and say, oh, this one line, you know, three quarters of the way through your 700 lines in markdown, I wanna change this one thing about it and hope that that's the only thing it changes.

[00:23:54] **Adam:** Now you can say, or like write on, it's almost like leaving a comment on a pull request, right? So you can just like click the thing there and say, actually you, you said we're gonna do this, but instead of X we're gonna do Y. Right? And that is intriguing to me, like as somebody who is detail oriented and,

[00:24:12] **Adam:** would probably make use of that,

[00:24:13] **Ben:** Yeah, that is interesting. I, I think I even saw some demo where you could, like highlight something visually in the UI and say, I, I don't know, leave a comment or something. So, you know what you're saying at the code level, but at the rendering level,

[00:24:29] **Adam:** yeah. You draw a box over it or whatever and, and,

[00:24:31] **Ben:** just bonkers. And I don't, I don't know if this is misguided or unearned, but I do kind of trust Google a little bit more.

[00:24:41] **Ben:** Meaning, and what I mean by is, like, I already, they already have my email,

[00:24:45] **Ben:** so if I didn't trust them with that, that'd be problematic.I just feel like they have such a reputational risk. You

[00:24:52] **Ben:** know, if, if something happened to Cursor or something happened to even OpenAI Google, it would be such a catastrophic faux pas to be like, oh yeah, we accidentally leaked everybody's code because it was going through our AI model.

[00:25:05] **Ben:** I mean, that would be massively problematic. I assume maybe it wouldn't be, nothing seemed to actually be problematic anymore these days, but I, I don't know. So maybe it's totally misguided, but I, I just, I trust the thought, the, the brain trust at Google a little bit more. Maybe

[00:25:23] **Carol:** I don't know. When I think of Google, I think of features just magically disappear. That they're

[00:25:28] **Carol:** not consistent. They just aren't consistent in what they do and they don't maintain what they've published. Like it just goes away so fast. I guess that if it didn't work, it would just be brushed under the rug and no one would even remember they published this thing.

[00:25:44] **Adam:** what it was called before they changed the name to Hangouts, but I miss the Google Hangouts like, Instant messaging.

[00:25:49] **Adam:** It was, I don't think No, no, no. so Hangouts got pulled into Meet because it was like, it was a thing. Then they renamed it to Hangouts and then, I believe Hangouts ended up getting like video chat.

[00:25:58] **Adam:** And then they made that Google Meet. And then I think shortly after that they dropped the, the text chat interface.

[00:26:05] **Carol:** It was like a hay or a wave or something like that.

[00:26:08] **Adam:** There was Google Wave. Yeah, that was different. But yeah,

[00:26:11] **Ben:** Could you say that Google is almost the opposite of a feature factory. They're feature butchers.

[00:26:21] **Adam:** yeah. For, for serious. yeah.

## [00:26:24] Not Driving Your Own Product Roadmap

[00:26:25] **Adam:** So let's, let's, on that note, let's move on to our, topic for the day, not driving your own product roadmap.

[00:26:30] **Carol:** Yeah, so I brought this up, as a, I don't wanna say it's exactly what I feel like is going on at work because I definitely don't want anyone to feel like I'm throwing them under the bus. Like I know we're all shuffling where we can and we're do doing our best to make things get out the door, right?

[00:26:45] **Carol:** But I did have some conversations recently where I've had some developers say that it feels like we are just pushing out features and not doing any product thinking. So when you think of things like the product work, you go, okay, what value does this add? I don't wanna do work if it doesn't add value.

[00:27:04] **Carol:** And instead, features come in and there's not a good answer as to why are we doing this other than. It's in the sprint and we need to do this because somebody, like a person said, this is important. So when I think of doing work, I think of things that make the tech stack better, that improves the user experience, that I can answer the why are we doing this?

[00:27:29] **Carol:** Like what problem am I solving when I put new code in the system? But when you start feeling like the work that you're putting out is just features with no understanding of what you are delivering on, or what metrics this is helping improve or how you even know it's successful, then developers just kinda get burned out.

[00:27:50] **Carol:** Like they get tired of the constant, every single day in standup. It's, is this done? Is this done and not, have we made anything better? It's just, is this done? Are we done? Did this get merged in? Are we

[00:28:04] **Carol:** ready to

[00:28:04] **Adam:** like, is your whole team working on the same thing?

[00:28:07] **Carol:** No. No. So it was a few months back it was, the team was ver, a big section of the team was focused on the same features and the same work for some legal stuff. And that all got out the door. And that was one of the ones that kinda like burnt everyone because when you would push out suggestions on ways to make the tech better, it was kind of shot down and said, we don't have time now instead of pulling in the right people to make sure we have the time to do it or the right resources to do it.

[00:28:37] **Carol:** So I don't know, I don't really know like where exactly to take the conversation, but I don't want my team to be in a spot where they just feel like they are just pushing out features and not growing themselves and not doing work that fulfills them.

[00:28:54] **Ben:** To me, I'm, I'm having a couple of feelings. One feeling is that a lot of this could be solved with better communication. Meaning I have had experiences in my career where a feature gets handed down for development and it's just not a feature that I understand or I don't connect with, or I don't see the value of it.

[00:29:16] **Ben:** And so it feels very forced, it feels very burdensome to have to implement this because I don't have that emotional buy-in. And I have had, sometimes I wish I could say I have all the time done this, but I have sometimes gone back to the product manager or the designer and said, you know, like, can you pitch this to me?

[00:29:32] **Ben:** Like, I don't understand, help me understand, you know, help me help you. And they give the story and they say, well, here's the research that we've done, and here are the users that we talked to, and this is why it's gonna be helpful. And it might not be helpful for everyone, but it'll be helpful for this niche of customers.

[00:29:48] **Ben:** And when they have the opportunity to explain it to me. Almost every single time, not every single time, but almost every single time I get it. And at that point it doesn't feel like I'm just churning out features. Like I'm much more connected to the vision. So I, I don't know what layers of reporting you're dealing with here, so there may be more or less feasibility, but just opening up a better dialogue about the features could go a long way to helping alleviate the, the people problems part of it. I don't know if that connects at all.

[00:30:20] **Carol:** It does, it does. And I, I even feel bad because, A day ago I was in a meeting and I was meeting with one of my engineers and some product people, and the conversation was one, solve is a pretty hefty rewrite of how we, don't have a, a solid source of truth for some data.

[00:30:41] **Carol:** It's stored in multiple tables and there are instances where you could update, update one like a DBA could run a script for us and there is no backwards updating on the other table. So now statuses are out of sync. So the, the real fix is to go actually make sure that everything is in a single like table.

[00:31:01] **Carol:** Like we don't need statuses across the board. Everything should come from one place. And instead I went, what's the fastest solve here? And it's clean it up, monitor for another one, and then let's see, like what we need to invest in it. And I feel bad for like even having that thought that I'm telling someone.

[00:31:21] **Carol:** We don't have the time or resources to actually invest in a full fledged like rewrite of this. And it's not even a big section. It probably wouldn't take that long. Just there's no time, right? And the thing that needs to get done has to get done, and there's no time to get that finished. So, I don't know.

[00:31:40] **Carol:** I just think that I need to do a better job of enforcing standards upfront when we do the feature works and make sure there's not so much tech debt. But when the feature is so unknown and it's not clear on what we're even trying to solve, how do you prevent the tech debt from getting into the system?

[00:31:57] **Ben:** I know this is not exactly what you're asking necessarily. and this again, may not be a feasibility issue here, but I, I have always thought that if people have to fix their own problems, it's a much better learning feedback system. So if you can imagine developer A works on this area of the code does not a bad job, but let's call it a hasty job, a not long-term thinking job gets the work done.

[00:32:25] **Carol:** And then some issues arise and then developer B is the one assigned to go in and fix it. I feel like there's no learning opportunity for developer A to be like, oh, okay, I see where I could have done this better. Let me fix this. And I think a lot of organizations that were like, well, developer A has already been moved on to this other high priority project, so we can't divert them back to the thing that they broke the fir, you know, like didn't build right the first time. But I almost wonder if like we could make that part of the social pressure, like, okay, you have to stop what you're working on now and go fix the thing you worked on before that like adds not just a learning opportunity, but like a learning and it had implications, opportunity. remember you saying this before, in another episode not too long ago, that it would be nice if there was some type of, like, ownership with what you write, meaning that even if I leave a company, it's my responsibility to maintain it after the fact,

[00:33:18] **Ben:** Yeah.

[00:33:18] **Carol:** Like I

[00:33:19] **Carol:** remember. Yeah. Like, and that's not a bad thought, but I, and I, I should, you know, I completely agree with what you're saying.

[00:33:26] **Carol:** I'm not saying that we shouldn't have ownership of our work. But what I find myself doing is developer A did the work. It didn't go so well. I don't trust them to go back and figure out what they did wrong. Like I want another person to come behind them and go, what did they get wrong?

[00:33:43] **Carol:** Let's solve it because if they got it wrong the first time, are they just gonna get it wrong again? And now I've wasted a lot of time and resources.

[00:33:52] **Adam:** I mean of those two approaches, I think I would tend to side with Ben. I feel like, now I'm not saying that Ben's idea there is perfect, but I do think that, from a, from a managerial perspective, like. You have to trust your teammates to do better and like they're, they're not gonna be perfect. And so like by saying look, this has these problems.

[00:34:14] **Adam:** And here's some reference material that you can read, like maybe this pattern would help or maybe this pattern would help. And I'm here if you want to talk about it more deeply. that is going to gonna push them to be better and they'll carry that forward.

[00:34:27] **Carol:** Yeah. Y'all are such

[00:34:29] **Adam:** But it's hard. Yeah. I know.

[00:34:30] **Carol:** Such good leaders, aren't you?

[00:34:33] **Adam:** It's easy for me to say in a vacuum.

[00:34:35] **Adam:** I

[00:34:35] **Ben:** exactly. I've never actually had to do this. Well, so the person coming in to fix it though, that could also be, again, not a communications problem, but you could always spin it. Get that person excited. Hey, you, we all know developer A sucks. Ha ha ha. Not, not in so many words, but like, I need you to, like, you're my rock star.

[00:34:58] **Ben:** I need you to come in and fix this code because I know that you're the person to do it. And it sucks that you're the one to do it, but you're the only person I trust. You know, there's like a, you

[00:35:09] **Carol:** yeah, I definitely have those people. I definitely have those people on the team where they're my first, my first call when there's something broken, like there's a few of them that ever, it never fails. I call the same people over and over again because I just trust their ability to do research and get to the bottom of it and provide a solid solution.

[00:35:26] **Carol:** But I will burn them out doing that.

[00:35:29] **Ben:** it's the, it's the battle always. So going back to, the Phoenix Project, was it with Brent? Deep cut here many hundreds of episodes ago.

[00:35:38] **Carol:** Geez, that

[00:35:39] **Ben:** Brent was the guy at the company that could fix anything and he was also then therefore the guy who had to do everything and was the bottleneck. So it's always frustrating 'cause like in my mind, I always a little bit wanna be the Brent knowing that that's not the healthiest, but it also just feels good emotionally, just wanna be needed.

[00:35:57] **Carol:** Yeah.

[00:35:57] **Carol:** Uh one 30,

[00:35:59] **Carol:** oh. You found it. Look at you.

[00:36:00] **Ben:** Alright. So when I said many hundreds ago, it was over a hundred. That's tipping into the two hundreds, rounding.

[00:36:08] **Adam:** that was

[00:36:08] **Carol:** is, uh,

[00:36:09] **Ben:** Yeah.

[00:36:10] **Ben:** But it's deep into the two hundreds.

[00:36:12] **Adam:** Oh

[00:36:12] **Carol:** 239 the correct number after the math was fixed, or is that an adjustment? Okay. Okay, so we're actually 239.

[00:36:21] **Adam:** that's right.

[00:36:22] **Carol:** Nice.

[00:36:22] **Carol:** Nice.

## [00:36:23] Customer Features vs. Boss Features

[00:36:23] **Ben:** here, here's another feeling that I'm having that to me, there are. Two kinds of like feature factory mentalities. there's the feature that we have to build because customer asked for it,

[00:36:39] **Carol:** sure.

[00:36:39] **Ben:** and we need to make that customer happy. And then there's the, we need to build this feature because someone just arbitrarily said we needed it.

[00:36:48] **Ben:** Oh, the CEO heard an interview about such and such, and we just need to build it. And

[00:36:53] **Carol:** oh, suddenly you should support, dark mode because a competitor has it.

[00:36:59] **Ben:** yeah.

[00:37:00] **Carol:** Hmm.

[00:37:01] **Adam:** I mean, as stupid as it sounds, I mean that, that exact example. Now I'm not saying that we've done that, we haven't done that exact example, but I like that example because you can, it's very easy to concretely say like. I was in a sales meeting as a, you know, as a CEO, as a sales guy, whatever. I was in a sales meeting and they, they flat out told me like, look, our, our, we're going to this other competitor because they have dark mode and you don't like, and if you're losing sales for that feature specifically, and if it's not the first or second or third time it's happened, then it's like, okay, this is consistently costing us sales.

[00:37:35] **Adam:** We need to do this.

[00:37:36] **Ben:** Yeah,

[00:37:37] **Adam:** But

[00:37:37] **Adam:** that's a, that's a usable story, right? Like, it's like you were saying, it's gotta be a communication. You gotta say like, look, we're losing sales because of this. It seems like tedious stuff, but, you know, if you've got a functioning design system, it's not gonna be that hard to edit in.

[00:37:49] **Adam:** But

[00:37:50] **Ben:** But, but I will say that for me personally, and I hazard to guess that this is more broadly applicable, making a customer happy feels better than just arbitrarily making a boss happy.

[00:38:05] **Carol:** I agree.

[00:38:06] **Ben:** at least at the end of the day, it feels like it's being driven by something and not just

[00:38:10] **Carol:** It's, yeah. I mean, when the customer wants it, I still say, well, the end user is satisfied. Right? Like the end user of the system is the one that I need to make happy. 'cause they have to keep coming back to it. Whereas if it's a boss, it's just some whimsical thing because you drink too much on Friday night and now we're all living this decision.

[00:38:31] **Carol:** Right. Not that I deal with that down. That was a joke. Yeah.

[00:38:35] **Adam:** So I've been lucky in this regard. I, you know, I've been working at the same company for 13 years on the same product for 10 years. Actually, today is the 10 year anniversary of our launch. Um, like at, as we're talking today is the 10 year anniversary of, of when we went to production with the, the product,

[00:38:50] **Carol:** you can't leave because Ben's gonna make sure you support all your codes for the rest of your life.

[00:38:56] **Adam:** He's gonna hunt me down. but, so, you know, I've been working on the same product and I've been kind of primarily. the driver of like how things get done, not necessarily always what gets done. I, I've always had my voice in, should we do this and how should we do this? but it, you know, as, as the primary driver, I, I just haven't had this problem because it's, I've been so close to the problems that, the solution just feels necessary.

[00:39:22] **Adam:** I will say the closest I've come has been, we are now working on integrating with Salesforce, and by, when I say we, I mean one of my cust, one of my coworkers is, is dealing with that problem, and, and integrating our stuff with Salesforce. And it's very much like a, it's a necessary evil in my mind.

[00:39:41] **Adam:** You know, a bunch of our customers are moving their like system of record data, their like internal data warehouse stuff over to Salesforce. And so if we want to continue to. Be a good choice for them, then we need to be able to integrate. And it, you know, once we have the integration, it does make some of the like, onboarding stuff easier.

[00:39:58] **Adam:** We can just be like, give us access to your data and we'll go get it. You don't have to build exports and send them to us, we'll just go get it for you sort of thing. but I gotta say my heart is not in it, right? Salesforce do not

[00:40:11] **Carol:** Uh,yeah. Yeah.

[00:40:12] **Adam:** and so, for me that's been a very like, kind of a dark line of thinking, early on when we were integrating with Salesforce and like, all of us, like my whole team, we were like taking Salesforce trainings and I'm like, God, do I need to start looking for a new job?

[00:40:27] **Adam:** this is not what I wanna be doing with my time. You know, fortunately it didn't work out that way. And cooler heads prevailed sort of situation. but, It's, yeah, it's not exactly the same thing, but it is like it's absolutely demoralizing to be stuck working on something that you just don't have your heart in.

[00:40:46] **Ben:** I, I know that this is never true or almost never true, but I almost feel like things that are really hard, it feels like a red flag. And I know that's ridiculous because so much of we build is about solving hard problems. Sometimes things just feel difficult in a way that's not interesting, difficult,

[00:41:07] **Ben:** and it almost, it always meant I'm like, there's gotta be a different way to do this.

[00:41:10] **Ben:** Like, this has gotta be a red flag in the back of my mind where my mind is trying to tell me something. I think that's probably actually not the case at all, but I always want it, like I always wanna be able to trust my gut.

[00:41:23] **Adam:** Yeah.

## [00:41:24] Hard vs. Interesting Difficult

[00:41:24] **Carol:** I get that because when I look at a big project, and like I know you're talking about Salesforce, but we're doing the same thing with Zendesk right now. So we're being forced onto Zendesk and. It's a must go do thing. And we have a spike in to go figure out like how we scrape the data to get it to Zendesk.

[00:41:40] **Carol:** So when a user puts in a help desk ticket, we have the information we need, right? And I'm going, oh, but there's so much more to that. It's not just what data are you sending? It's, you know, can we even get firewall open to it? It's a whole lot of other stuff that goes into it. And I didn't even wanna look at it, so I was so happy when someone else's name popped up on the research.

[00:42:01] **Carol:** 'cause I was like, I know this is about to just land on my plate, like Zendesk and the integration piece of stuff. And to me, like I feel like once you integrate with something, it should be so easy to roll to another partner. Like another vendor should just be on and off. But that's not how they develop things.

[00:42:18] **Carol:** Everyone's very unique.

[00:42:21] **Ben:** Yeah, and I've, I've heard pros and cons of that. I know people talk about how deep the Amazon services menu is and that to try to build in like an Amazon agnostic way is to kind of rule out so much of the efficiencies that Amazon does where like pipe events into queues, and then you can have functions that feed off of queues that pipe into other things and whatnot to try to build stuff like that generically.

[00:42:51] **Ben:** And, you know, full caveat, I've never built any of that for anybody. it, you know, it's definitely a trade off.

[00:42:57] **Adam:** Yeah. the other thing coming to mind for me, kind of similar to this, not driving your own product roadmap, when we have these like long running projects like the Salesforce integration or like this SvelteKit migration that we've been working on, we do also try to make sure that we're continuing to be visibly moving the needle for our customers, right?

[00:43:16] **Adam:** So. we may be 80% heads down trying to make a big push on some big project, but if we're like that for three, four, you know, six weeks, they're gonna be like, you've said we'll get to it on all of our tickets, but we're not actually seeing anything change. Right. So, during those periods, I feel like we get into this habit of, jumping on little tickets.

[00:43:40] **Adam:** anything that, that pops up as like a, I can solve that in less than two hours. most of us would be like, I'll do it. I think partly it's like that, that little, what is it, endorphin hit or whatever, of like shipping something. It's like, yes, I actually got to push code to production instead of,making another 2000 line change in this pull request.

[00:44:01] **Adam:** That's gonna be a nightmare to review in six weeks. But part of it too is like, yeah, we just have to, we have to be visibly improving the product every day, so.

[00:44:11] **Ben:** this doesn't really fit nicely into the conversation, but I wanna mention it anyway 'cause it. I just have to get it off my chest. but I had to deal a lot with, in my career the concept of like, I don't wanna say me too, 'cause that's very loaded, but like us also features where we have a product, we've built it for customers, and then a competitor

[00:44:34] **Adam:** Mm.

[00:44:34] **Ben:** built some new feature.

[00:44:36] **Ben:** And now we feel like we have to also build that feature. Not because the customers asked for it, but simply because a competitor has it. And those features always felt super emotionally draining to have to build. 'cause it just felt like all you were doing was trying to play catch up with someone else and you were building something that no one asked for.

[00:44:59] **Ben:** And the only reasoning was, well, they built it so we have to build it.

[00:45:03] **Carol:** And you have no idea if they're going to use it

[00:45:06] **Adam:** Yeah.

[00:45:07] **Carol:** So you're investing all this time and like energy and when I write code, like I'm, I'm attached to it a little. Like, I'm like, I am invested in what I'm producing. Like I care about it.

[00:45:17] **Carol:** And when I feel like I'm just putting something out there that I don't even know if anyone wants or wanted, like, that's just disheartening.

[00:45:24] **Ben:** Yeah, absolutely.

[00:45:25] **Carol:** Mm-hmm.

[00:45:26] **Ben:** Usually, ultimately it's just great to feel connected to customers. I mean, that really is, for me, the thing that makes it all so, so easy in the grant scheme of things.

## [00:45:37] Prioritization and Visibility

[00:45:37] **Adam:** Mm-hmm. The thing I keep coming back to in my head, right, so kind of refocusing on our topic, not driving you in product roadmap, the purist will say, you've gotta have, whether it's your Kanban board or whatever, you gotta have this centralized. source of truth that is, these are our current priorities and if something is gonna come in and like be the new priority, then it has to be visible that is pushing other things down the list.

[00:46:00] **Adam:** And there has to be like, buy into that. Like even if it's not your decision to make, it has to be visible to the, the other stakeholders, right? If, if you're pushing somebody else's PET project down the list, then that person's gonna get mad. But if they can look at the list and go, okay, well that's the CEO's project and he or she has the, the right to overrule me and say that that's more important, fine.

[00:46:21] **Adam:** Or if they're like, oh yeah, we definitely need their thing more than my thing, then, you know, as long as the stakeholders are, are actually agreeing on it, then I think that that could, again, this is the purist's perspective. I think that that could, kind of make everything work out emotionally. Nobody wants to do the work of maintaining that. Like, here are our current priorities. You know, like, especially when we're talking about these changes, I'm making some text customizable on a particular page. Right? And so that's a, that's a 30 minute task. I'm not gonna go drop that at the top of the list and send a notification.

[00:46:54] **Adam:** Hey, by the way, I'm, I'm putting it this at the top of the list. It's only gonna take me 30 minutes. So don't worry about it too much. But it's there, it's just so, it's such a, fuzzy thing, managing the work stream.

[00:47:03] **Adam:** Mm-hmm.

[00:47:04] **Carol:** Yeah.

[00:47:05] **Ben:** You know, if we could go 180 degrees to the other direction, which is being almost maniacal in driving your own roadmap, I am not part of the Ruby. World or the Ruby on Rails world. But from everything that I have heard in interviews and discussions, the Basecamp people are like extremists about this to the point of they built a lot of stuff and they release it publicly.

[00:47:34] **Ben:** Like Ruby on Rails came out of DHH's mind basically. And, and like all of their ActiveRecord and Hotwire and li you know, lots of libraries and, and patterns have come out of Basecamp. And again, I'm not in that world, but from everything I've heard, they're basically like, we built this for us. Use it if you like, and like kind of f you otherwise where you're like, oh, could we add this to the library or like tweak the framework to do this.

[00:48:03] **Ben:** And again, my understanding is they're basically like, that won't help us. So no, we're not gonna do that.

[00:48:10] **Adam:** Yeah. Or, or you just get a no.

[00:48:13] **Ben:** Yeah. So that's like, it's, it's like on one hand I get it, but on the other hand I'm like, that doesn't, that also doesn't seem like the right way to be, from a or, or like don't release that stuff publicly.

[00:48:25] **Ben:** Then, you know, if you're gonna make it public, you're making it public almost with the intention that it is for sharing and collaboration a little

[00:48:32] **Ben:** bit.

[00:48:33] **Adam:** you know, I think this goes back to there is no right way or wrong way. so you, you, what you're kind of describing as like the BDFL benevolent dictator for life, like what I say goes, this is my thing. It's, it's there if you want to use it, sort of thing. That's, that's kind of how, Python started too with, Guido van Rossum.

[00:48:51] **Adam:** but.

[00:48:52] **Adam:** I think it cuts both ways,

[00:48:53] **Ben:** it does cut both ways.

[00:48:55] **Adam:** you're, if you're the BDFL, then it's up to you, right? You're not getting community contribution. Or if you are, then you're, you're spending your time doing the, the gatekeeping of what goes in and what doesn't. And writing specs or, or whatever. but at the same time, if you go the complete opposite, then it's just open floodgates and like, I guess the complete opposite would be just every poll request gets merged no matter what.

[00:49:18] **Adam:** But, you know, somewhere in the middle is like the happy gray area. And it's like a spectrum. You're gonna be, I think, fluctuating back and forth. There's gonna be periods where you're gonna be like, no, you know, I need to make, I need to be particular about what I accept in my project.

[00:49:32] **Adam:** For the good of the project as a whole, added lines of code to, to support one user is not necessarily good for the whole project.

[00:49:40] **Adam:** and and then the, sometimes you're gonna be at the other, other end of the spectrum, and you're just gonna wanna be like, yeah. You know, sure.

[00:49:46] **Adam:** Why not?

[00:49:47] **Ben:** Well, even just. I dunno if it was last week or the week before we were talking about, Tim had mentioned Quiet UI where the guy released his component library and then a week later he was like, well, that was a terrible idea.

[00:50:04] **Ben:** I'll be bringing that back in house.

[00:50:06] **Adam:** I, didn't see the library before it was taken down. I only heard about it because it got taken down. But I have so much respect for that dude, like, knowing what his personal needs are and putting up boundaries. Like, cool. I, I have, I have mad

[00:50:20] **Ben:** a hundred percent.

[00:50:21] **Adam:** Yeah.

## [00:50:22] Patreon

[00:50:22] **Adam:** alright. Well then this episode of Working Code is brought to you by Salesforce. Are you too content with your life? Try integrating with Salesforce.and listeners like you. If you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the universe than you should consider supporting us on Patreon.

[00:50:38] **Adam:** Our patrons cover our recording, editing and transcription costs and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [00:50:47] Thanks For Listening!

[00:50:47] **Adam:** we're gonna go record the after show, which is outro Music Plays and patrons stick around 'cause they know they're getting bonus content after music plays and we just keep going on and on.

[00:50:56] **Adam:** Tonight it looks like we're gonna be talking about white space blindness. and, somebody is not happy with their YouTube homepage. Hmm. I wonder who that could be.if you'd like to get content like that and the whole back catalog of After shows, you can go to patreon.com/workingcodepod.

[00:51:12] **Adam:** First little is, less than four bucks a month. You can get access to all of that. and, we'd love to have your support.

[00:51:19] **Adam:** that's gonna do it for us this week. We'll catch you next week. And until then,

[00:51:23] **Carol:** And remember, even if you don't control your product backlog, your heart still matters. ​
