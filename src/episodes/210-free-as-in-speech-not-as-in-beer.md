---
title: "210: Free as in Speech, not as in Beer"
description: "In week's this episode, the crew explores the often confusing phrase 'free as in speech, not as in beer.'"
date: 2025-03-20
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/210-free-as-in-speech-not-as-in-beer/id1544142288?i=1000700103148"></iframe>

In week's this episode, the crew explores the often confusing phrase 'free as in speech, not as in beer.'

They discuss the differences between software that's free in terms of cost (beer) and free in terms of user freedoms (speech). The conversation delves into open-source licensing, the implications for users and developers, and comparisons to various software models.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky](https://bsky.app/profile/workingcode.dev). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/210-free-as-in-speech-not-as-in-beer.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** somebody, I think being cheeky about this turn of phrase created a beer, like literally a beer and, and I believe if I'm, if I'm recalling correctly, it was called open source beer. And so now that beer is, it can potentially be, if somebody is giving it away, free as in beer and free as in speech, because you can have the recipe and it, I'm sure it has a license and stuff

## [00:00:45] Intro

[00:00:45] **Adam:** Here we go to show number 210. And on today's show, we're going to talk about free as in speech, not as in beer. What does it mean? Why is it confusing? How are we confused? Can we, can we unconfuse ourselves now? I'm stuck. I'm confused. What? Uh, But first I think as usual, we start with our triumphs and fails.

[00:01:04] **Adam:** According to the Google doc that definitely doesn't exist. It looks like it's my turn to go first.

## [00:01:09] Adam's Triumph

[00:01:09] **Adam:** So I'm going to go first and my, I'm going to start us off with a triumph. And so you're going to have to excuse me. I'm going to just right off the jump here, gonna, I'm going to svelte all over the place.

[00:01:21] **Adam:** So apologies, but there are, how do we say it? Sorry, not sorry. I really did confuse myself. This is, I'm off to a great start. So, if you know, then like, if you're, if you are into Svelte at all, then this is going to make total sense to you. If you don't, then you're, maybe it'll sound. Good. I don't know.

[00:01:39] **Adam:** But if you're, if you're a Svelte person, you'd be like, duh, really? You took you this long to figure that out? I don't know. Whatever. So my triumph is I figured out invalidations. So Svelte is like, or Svelte kit in particular is like just a little bit of magic added on top of JavaScript, right? So it's like JavaScript with a routing engine and just a little Svelte itself is like little bits of magic, like make things reactive.

[00:02:01] **Adam:** And, and easier. And So, they, with SvelteKit, they added this really cool thing where you can have two separate files and you've got your like, your, your view and your if you've, if you've done C sharp or probably most net flavors you're familiar with like the concept of a code behind, right?

[00:02:21] **Adam:** You've got your view and the the logic is in a separate file that's kind of Tightly coupled or associated with that view. So with Svelte, you have your view, you have your client side code behind and your server side code behind. And it's felt just kind of manages the magic of calling the server.

[00:02:40] **Adam:** It's a single page app. It runs in the browser, but then like when necessary, it'll call the server side code behind to, to run that loader function and get the data that it returns. It doesn't actually make a full round trip and rerender the HTML. It'll just. You know, call that function over Ajax, get the result and wire it all in.

[00:02:57] **Adam:** It's pretty neat. And. If you do things the way that they tell you to do them, if, like, if you load your data the way they tell you to load it they make it really easy to, like, have a way to say, okay, refresh the data, right, like, literally that simple, just say, I want the data on this page to be refreshed, everything that I did it, or you can do specific bits of data, like refresh this piece and, I've seen a bunch of tutorials on this and it's been, it's been out for over a year now, maybe two and not that I've had every day to work on it, you know, here and there, but I, I've always struggled with this and like, okay, I got to move on.

[00:03:33] **Adam:** I can't, I can't work for a week on this problem. So I got to like, just live without it and, and do it the hard way. And that's fine. And, and finally, while I was working on this skydiving app, I've been working on I, I. Hit the issue again and did a little searching and finally found the issue and basically If I can simplify the magic that it does When the that code behind runs and it returns some data to your view the when the view runs all of the top level variables that get created are Only created once like as the, the page initially renders and they never get re rendered even if you invalidate the data and it goes and you can see the network tab in the dev tools, you know, it goes out and makes network requests and you can see, okay, like I'm getting the new data back, why isn't the view updating?

[00:04:22] **Adam:** It's because I was setting those all as top level variables with like destructuring, right? So. Let's say all my data comes back in a, in a bundle called data, like one variable and it's an object with a bunch of keys on it, right? And, and so my, the keys might be like jumps or aircraft or loads or whatever.

[00:04:39] **Adam:** And those are the things that are being refreshed. But I'm destructuring those so that their top level variables easy to reference in the view. Unfortunately, because they're top level variables. They only get rend, only get like set on initial page render. And so even though the data is going at being refreshed, my destructuring isn't being refreshed.

[00:04:59] **Adam:** And so by simply not destructuring them and referencing them as like data dot jumps, data dot loads. Now my invalidations work. It's so nice. It's, it's so nice to just be able to like have a button that's like refresh all the data and it just calls invalidate all and all the data gets refreshed instantly.

[00:05:16] **Adam:** Oh my God. It's so nice.

[00:05:19] **Ben:** is it is it like making a a page request back to the server? Is it, is it almost like you refresh the browser? I don't know the mechanics or is it more like you're doing an Ajax request and getting JSON,

[00:05:30] **Adam:** it's more like Ajax. Yeah, it's definitely not doing like a full page reload or anything like that. And it's, it could potentially be many Ajax requests depending on, you know, how you're loading your data, if you've got different API endpoints, or if it's all in one code behind.

[00:05:44] **Tim:** Well, I didn't understand most of that, but I enjoyed your enthusiasm.

[00:05:49] **Adam:** You're welcome? Question mark?

[00:05:52] **Ben:** that's cool.

[00:05:53] **Carol:** Not to out myself here or anything, but we use knockout and some of our code and knockout has some of that same built in functionality. Where if you like var a data set that's coming back, whenever you render it back in, it's no longer tied to your model. So the update never happens. So the easiest thing I go look for when someone's like, Oh, this value isn't working.

[00:06:17] **Carol:** I'm like, Oh, did you declare it in a different way? And now it doesn't know how to get to it. Like, let's go look at everywhere it's being set at. So I've definitely seen that before where, when it comes in, it's like, Hey, why isn't that updating? And you're like, Oh, you just set it to something. Now we don't know how to get to.

[00:06:32] **Adam:** I should probably like write a blog post on this if for no reason other than for myself in six months when I'm like, why isn't it working?

[00:06:39] **Carol:** you should 100 percent because I did a quick search just to understand like, what you were talking about with the invalidations and spell kit. I'm like, I don't even know what he's talking about here. And the last post was like, a year ago. I was like, well, that's not really irrelevant.

[00:06:53] **Adam:** Well, I, I'll have to do that then.

[00:06:55] **Ben:** I wonder if it has something to do with. The way Svelte does it's it's like, whatever the runes are, you know, like the kind of proxy data, I wonder if it's proxying the payload that comes back. So when you pull something out of it, you're kind of detaching it from that proxy.

[00:07:09] **Adam:** Could be. Yeah. I, I don't entirely know. I haven't had the, the time and the inclination to dig into, you know, what comes out the other end of the compiler. I just know the code that I write and it's very fun to write and maintainable and it makes me happy. That's good enough for me.

[00:07:28] **Ben:** I'm sure I've mentioned this podcast in the past before. There's a.

[00:07:32] **Adam:** our podcast on our podcast.

[00:07:34] **Ben:** There's another podcast that I've recently started listening to called the future of coding and it's a very academic podcast. They talk about kind of landmark papers and essays that have been written and just how they understand them and the impacts they've had on the industry.

[00:07:49] **Ben:** It's, it's, it's, it's like the nerdiest podcast that I listened to. And that one of the guys was like a philosophy major. So he's always pulling philosophy into it. And each episode is, is one of these papers or essays and they talked about one I can't remember exactly what it's called, but it was like worst is best.

[00:08:05] **Ben:** And so they're comparing two different types of programming and it boiled down to either you, you expose an API that either puts the complexity of consumption onto the consumer or the complexity of consumption onto the internals of the app itself. So basically, like, do you expose an API that's easy to use, or do you expose an API that's the most efficient, but makes it more complicated?

[00:08:32] **Ben:** And it's, it's, it's like, I don't understand most of what they talk about in the show, but I find myself thinking about a lot of the stuff that I hear in the framing that they bring up on the show. So every time now I hear about API design choices, I'm constantly thinking back to this worst is better.

[00:08:51] **Ben:** And, and I'm shocked sometimes not shocked, but it's just, it's just fascinating. Like you can, so there's, there's a, you can wrap these things in proxies and you can set and get on objects and set and get on arrays. And it just seamlessly picks up the fact that these mutations are happening and does all the fancy immutable and, you know, signal based and all the kind of propagation behind the scenes.

[00:09:16] **Ben:** And it makes consuming these objects. So simple from a developer standpoint, and then you compare that to other you know, like react with its flux and whatever the, you know, that's kind of architectures we're meeting events and everything has to be like slices and, and spreads. And, and you're like, Oh.

[00:09:35] **Ben:** Like you've put all of the complexity onto the consumer so that you could do something efficient internally. And it just, it just gives me so much more, not respect, but like so much more admiration for these APIs that have clearly been designed to make the ease of consumption, the primary focus.

[00:09:54] **Adam:** Right.

[00:09:55] **Ben:** And I don't know, I just, I love it.

[00:09:57] **Ben:** I love hearing about things

[00:09:58] **Tim:** Fun, fun fact. The worst is better is also known as the New Jersey style.

[00:10:04] **Adam:** Okay. Do you care to elaborate on that at all,

[00:10:06] **Tim:** I, I I, I don't know. Wikipedia is telling me that.

[00:10:09] **Ben:** That is hilarious.

[00:10:12] **Tim:** Word.

[00:10:13] **Adam:** So presented without comment.

[00:10:15] **Tim:** Yeah. New Jersey style. For some reason, AT&amp; T, Richard Gabriel, 1991 came up with it.

[00:10:22] **Ben:** Oh, that's funny. Does it say what it's compared to? I can't remember the MIT style,

[00:10:28] **Tim:** yeah, I mean, it's MIT style versus Jersey style. So MIT, I imagine is the more complex one in Jersey style. It's like, Hey, whatever, you know?

[00:10:36] **Ben:** but I think, you know, I think one of the things that would fall into this category is, is like languages that do automatic garbage collection. They're easier to use, but they're slower in certain cases, but they don't put a lot of the complexity onto the consumer, but things we have to allocate and deallocate memory, it's better performance wise, but the complexity is all shifted to the

[00:10:57] **Tim:** And that's funny you say that. Cause I struggle with that. I, you know, mostly do like API design and it's like, I, I will toggle back and forth between those two things. It's like, I want an API where like, for instance, like you got a note, like a number, like represents a policy. But those hold, there's a policy ID, the policy ID is obviously going to be quicker and I'll get mad at myself because like, I'll come, I will switch from, from being a writer of the API versus I sometimes I have to consume it.

[00:11:27] **Tim:** And I'm like, why do I have to know these five pieces of data in order to use this end point? I just, just, just let me give you the policy number and you do all that work for me. And I'm like, wait, I wrote this. Why am I yelling at myself?

[00:11:39] **Ben:** you know, I've been thinking a lot about this as well, because I'm sure I've talked about this many, many, many episodes ago, but the first real API that I ever tried to design was for Envision. And it was for the desktop client that would do some sinking down to the computer. Files and I had designed these routes that I thought like, this is quote unquote, how, how API routes were designed, where it was like users slash the user ID slash project slash the project ID slash screen slash the screen ID.

[00:12:12] **Ben:** Cause I feel like all of the quote unquote professional APIs that I had seen out there in the world had this kind of hierarchical. Um, But what I was discovering, sadly, after the fact was that every time you wanted to go to interact with the API, you often had to get these other IDs merely to satisfy the URL, but not because they were actually needed by the endpoint that was processing the information.

[00:12:39] **Ben:** It's like given a screen ID, I could tell you. You know, what project to belong to and what user owned that project. It's not like any of that was actually required. And then it becomes just one more thing that I have to keep in alignment. Like now what happens if you give me a project ID and the URL that doesn't actually match the screen project ID, but you have permissions to see that screen.

[00:13:04] **Ben:** I'm like, do I have to reject that request now? Just because these two arbitrary IDs don't line up.

[00:13:10] **Adam:** Right. Yeah. That was that's something I touched a little bit on in my book. Not, you know, no, no instead of like, whatever, can it be like, no plug, no plug? I'm not. Yeah, I'm not, I'm not plugging, but yeah, like API design I, I also early fell down the trap of making things hierarchical just because it seems like that's a logical way to organize things.

[00:13:32] **Adam:** But then you get to that point and you're like, so I'm making you in some cases, look up an ID just so that you can include it in the URL. Like I don't need it either,

[00:13:41] **Ben:** Yeah.

[00:13:42] **Adam:** yeah.

[00:13:43] **Ben:** And I definitely, I mean, there's a lot of stuff that I like in theory, like I like the idea of URLs being explorable. You know, if you're looking at a hierarchical URL in theory, you can just cut off half of it and see something higher up in the data tree. But, but in reality, I feel like I've never done that.

[00:14:02] **Ben:** Like if I've ever done that on a website, it's usually because the page that I'm on isn't working properly, or it's like not the right version of something. And I want to see if I can go up one level to find the right version. It's never because I'm like actively engaged with the site. It's because something's broken and I'm just trying to manipulate the URL.

[00:14:22] **Adam:** Okay. So that's the end of my triumph.

[00:14:26] **Tim:** And two, and two sidetracks.

[00:14:29] **Adam:** so that's it for me. What do you got going on, Ben? Oh.

## [00:14:33] Ben's Fail

[00:14:33] **Ben:** I, I'm, I'm, I've pepped myself up here, but I've actually been kind of depressed lately I don't know, I've just been, I feel like I'm having a little bit of a midlife crisis, and 45, or I'll, I'll be

[00:14:46] **Tim:** You might live to 90. Okay. I'll give you

[00:14:48] **Ben:** Yeah, yeah, there you go I don't know, I've just been very almost sad, just sad and depressed actually and then I think it's been manifesting itself physically.

[00:14:59] **Ben:** So then my, my wrists have been hurting me lately which, you know, then I kind of like spiral off into the, you know, like, what if I can never type again?

[00:15:08] **Tim:** Oh man.

[00:15:09] **Ben:** so I dunno, I've just been, I've been not in a great place and I've been kind of just floating through my day and and not really particularly feeling like.

[00:15:18] **Ben:** I've been adding value and the, my wife has been very supportive, so that's been fantastic. And I actually just this morning went to my very first therapy session. I've never done therapy before, so yeah, that was, that was nice. It was nice to just be completely open and honest and feeling not judged and

[00:15:41] **Carol:** Yeah.

[00:15:42] **Tim:** Like, like you do here.

[00:15:43] **Ben:** there you go.

[00:15:44] **Ben:** Exactly.

[00:15:45] **Carol:** you. I have a personal question. Was it like an in person visit or did you do one of the online, like,

[00:15:52] **Ben:** I, I did it in

[00:15:53] **Carol:** do a video call? Okay.

[00:15:54] **Ben:** in person. We had a there's a right in town. I mean, literally it's like a three minute ride from my house. So you know, I mean, triumph in that I'm trying to do something about it, but failure and that I just, I, I'm hoping, yeah, I'm hoping that you know, this too shall pass kind of a scenario and I just have to get through it.

[00:16:15] **Tim:** I mean, you're going through a big change. You, you sunsetted a company. You were with that for a very long time.

[00:16:20] **Ben:** Yeah.

[00:16:21] **Carol:** Found it, you know?

[00:16:22] **Ben:** I know. I, I kind of just assumed I was past it. And um, and maybe I'm not, I don't know.

[00:16:29] **Carol:** Yeah.

[00:16:29] **Ben:** just a lot going on too. My dog keeps waking me up in the middle of the night. She keeps wanting to

[00:16:33] **Carol:** Damn her.

[00:16:35] **Ben:** three 30, four o'clock in the morning. We're going to try to uh, Ferber. This is a misuse of the term, but you know, with babies, you can, you can do the Ferber method, which is where you just let them cry it out so that they can start to self soothe. We're going to try to do something like that if she gets up at the, the, the issue isn't so much that she gets up and wants to go out. That's fine. You know, that's just, that's how it is. It's that she then wants to either have someone on the couch with her or she wants to eat her breakfast at three 30 in the morning and like, that's just unacceptable and we have to break her of that.

[00:17:09] **Carol:** a spoiled toddler you

[00:17:10] **Ben:** She's the most spoiled. So anyway, it, there's just been a lot going on,

[00:17:15] **Carol:** Well, I'm sorry, Ben.

[00:17:17] **Ben:** but it's always, it's always so wonderful to see you guys

[00:17:20] **Carol:** Yeah, same.

[00:17:21] **Tim:** If there's anything we can do, buddy, I know we're geographically apart, but if you ever need to just call and cry,

[00:17:29] **Ben:** I appreciate that.

[00:17:30] **Carol:** We're definitely here for you.

[00:17:32] **Ben:** Thank you. So that's me, Carol. What do you got going on?

## [00:17:35] Carol's Triumph

[00:17:35] **Carol:** Well, I'm gonna go with a triumph. I've realized this week I don't fully suck at what I do

[00:17:41] **Ben:** nice.

[00:17:41] **Carol:** even though you guys may have heard differently,

[00:17:44] **Tim:** no, no. You're awesome.

[00:17:47] **Carol:** I definitely am finding my footing again. Like, it's taken a few weeks to, to regroup and figure out All the knowledge I didn't know, because there were so many people doing these jobs and now they're not there.

[00:18:02] **Carol:** So when my team has questions, I'm scrambling to go a, who still works here who still works here with access and who still works here with access and knows what the hell I'm talking about. So. It's very, very slim. So I've spent a lot of time helping my team over the past two weeks, and it's just been good to feel like I can find the answers and I can get through the the levels above me to make sure that my team is still succeeding.

[00:18:30] **Carol:** So I'm going to call it a big win. I still have my job and I am helping my team and I don't feel like I totally suck at everything. So I think that's a good, a good one for me.

[00:18:40] **Ben:** We'll take it.

[00:18:41] **Carol:** Yeah. I take on more. I can these days, just to be honest.

[00:18:45] **Ben:** Yeah.

[00:18:46] **Carol:** I messaged my boss and I'm just like, Hey, am I fired today?

[00:18:52] **Adam:** no.

[00:18:52] **Carol:** He's like, I haven't heard yet.

[00:18:54] **Tim:** Yeah.

[00:18:55] **Ben:** Oh my god.

[00:18:56] **Tim:** a tough situation. I know you can't talk a whole lot about it for fear of

[00:19:00] **Carol:** yeah.

[00:19:01] **Tim:** so, but yeah, it's, you're sticking it out. So that's,

[00:19:05] **Adam:** Good night, Wesley. Sleep well. I'll most likely kill you in the morning.

[00:19:10] **Tim:** Good work today, Wesley. That's a Princess Bride reference.

[00:19:13] **Carol:** I had no idea. So, yeah,

[00:19:15] **Ben:** Wait, have you never seen The Princess Bride?

[00:19:18] **Carol:** I watched the, like, 1 part of it because my friend had me recite it for his

[00:19:22] **Ben:** Oh,

[00:19:23] **Carol:** And that's the only part I know is like a wedding scene.

[00:19:26] **Tim:** it is literally the best movie ever. It is a perfect movie. There is, there is no flaws. No flaws in that film.

[00:19:33] **Adam:** baby Fred Savage. Come on now.

[00:19:36] **Ben:** Yeah. Put that on your list,

[00:19:38] **Tim:** Andre the Giant, you gotta watch it.

[00:19:40] **Carol:** I

[00:19:40] **Tim:** watch it multiple times a year.

[00:19:43] **Carol:** Yeah, I was going to say, I just repin my my must watch list because we're at the TV shows. So now we're going to go back to my movies. I've never seen.

[00:19:52] **Adam:** Well, if we're ever in the same place at the same time, Carol, don't worry, because I literally keep an emergency copy of it in my glove box in my car.

[00:19:59] **Tim:** That's awesome. I don't need a copy, I can quote you every single line.

[00:20:03] **Carol:** Oh, I love it. I love it. We'll do a viewing one night. There you

[00:20:06] **Tim:** Yeah, that'd be

[00:20:07] **Adam:** you go. Well, maybe that'll be like a patron berk perk. We can do like our own riff tracks.

[00:20:12] **Tim:** Yeah.

[00:20:13] **Carol:** Well,

[00:20:16] **Tim:** of instead of director's commentary, it's a working, working code dev commentary on, on it.

[00:20:21] **Carol:** Alright, well that's me. That's my big giant triumph. What do I use him? What you got going on?

## [00:20:25] Tim's Nothing

[00:20:25] **Tim:** Well, I'm not doing either one of what you got doing a no one.

[00:20:30] **Ben:** Nice.

[00:20:31] **Tim:** I got, I got a no one. I got nothing. I, you know, there's no, there was no highs. There was no lows. It was just, yeah, it's like, there's nothing really exciting that I learned this week, the past seven days. There's nothing that I failed at this, which is great.

[00:20:45] **Tim:** I mean, that's, that's, you know, not failing is a good thing. Yeah, that's a, that's a win. So it's, it's really a no oomph. You know, I'd like to have learned something. I'd like to have done something, but a lot of what I've been dealing with is just like working out the fine print, helping the lawyers craft something.

[00:21:02] **Tim:** So, and I can't really talk about that. So it's like, yeah, I got nothing.

[00:21:05] **Carol:** Sometimes, sometimes I think status quo is just okay. Like,

[00:21:09] **Adam:** could be a triumph on its own.

[00:21:11] **Tim:** Exactly.

[00:21:12] **Carol:** just get through it. Some weeks you just need status quo to be okay.

[00:21:16] **Tim:** Status quo is okay. You know, I, I wish there, I honestly wish there had been a fire to make my life a little more exciting, but there wasn't. So

[00:21:25] **Adam:** A metaphorical fire.

[00:21:26] **Tim:** a metaphorical fire. Yeah. Yeah, yeah, yeah, yeah, yeah.

[00:21:30] **Adam:** Okay, well then I guess that ends our triumphs and fails, right? Nobody has anything else to add or tangents to go on?

[00:21:35] **Carol:** Well, I have I have 1 little tiny 1 when you said fire 10. So, I had someone suggest this week that we and this is not what we're doing. So, any of my developers listening to this, just know we're not doing this. I'm not doing this. Okay. Clear on that. I had someone on the other side suggest that we split our team in between maintenance and

[00:21:59] **Adam:** Oh,

[00:22:00] **Tim:** yeah. Between, between suckage and

[00:22:05] **Carol:** I was like, could you imagine me telling like half my team, you're going to do nothing but fight fires that the other team caused all day long. I said, I've been there. We're not going that way. So please, let's never suggest this again.

[00:22:18] **Tim:** yeah. That's a terrible idea.

[00:22:20] **Carol:** you fight your fire because you caused it. Yeah.

[00:22:24] **Adam:** that's like right out of the bad part of the Phoenix Project.

[00:22:29] **Carol:** So

[00:22:29] **Adam:** So when are you activating that plan, Carol?

[00:22:32] **Carol:** Never, never. Devs, we're not doing it. Yeah.

[00:22:36] **Adam:** All right.

## [00:22:36] Programming Update

[00:22:36] **Adam:** Well, before we move on to the topic for the day, I do have a little bit of a programming update and I use that terminology intentionally. Programming update. Get it? See? Um, But so I mentioned previously, I don't know if I mentioned this on the main show or if I only mentioned it on the after show.

[00:22:52] **Adam:** The internal workings of the private feed for patrons is changing, not because of any choice that we made, just because of a thing something going on within Patreon. I have figured out a little bit more of that. So basically just patrons continue to watch the space. Probably what's going to end up happening is you, the URL that you put in your podcast player is going to have to change, shouldn't be much more than that.

[00:23:14] **Adam:** Expect that it's coming and we have, I mean, we're, we're still like a month and a half plus before that's going to be the deadline but you know, it's coming so pay attention anyway moving on

## [00:23:24] Free as in Speech, not as in Beer

[00:23:24] **Adam:** free as in speech not as in beer So we were talking before we started recording about like that that phrase right?

[00:23:32] **Adam:** Like we've all heard it None of us really in the core of our bones knew what it meant And we did a little bit of research and I think that it would probably be beneficial to the community to just talk about It a little bit, right?

[00:23:45] **Carol:** And and could we circle back? Three of you had heard it. I've never heard this saying before.

[00:23:51] **Tim:** I've heard it. I didn't know what I meant.

[00:23:52] **Ben:** Yeah. I've also heard Frias and puppies. Puppies. Puppies. Oh,

[00:24:02] **Adam:** that you can put in the saying for beer, right? So, not for bad reasons the community or society's focus on alcohol has kind of started to be replaced with other things, right? So, like, happy hour after work or whatever. So, whatever.

[00:24:20] **Adam:** What's that?

[00:24:21] **Tim:** Wimps,

[00:24:23] **Adam:** Hey, if you like a beer, you're still welcome to have a beer. It's just that not everybody partakes. And so,

[00:24:27] **Tim:** can't drink a puppy.

[00:24:29] **Adam:** more inclusive.

[00:24:30] **Carol:** Or you shouldn't.

[00:24:31] **Tim:** No, exactly.

[00:24:33] **Adam:** If you're not, if you can't, then you're not trying hard enough. Um, anyway, so. Phrasing speech not as in puppies, I guess, but yeah, so I'll take a first swing at it and then I'll, I don't know, we'll see what happens from there. I don't want to try to predict what's going to come out of our mouths.

[00:24:51] **Adam:** So phrasing speech not as in beer, basically or as in puppies. Let's start with the second half, phrasing a puppy, right? So if I give you A free puppy. Basically you're getting something in exchange for no money. I'm not I'm not giving you any warranty with that. I'm not giving you permission to modify it.

[00:25:11] **Adam:** I don't know how you would modify a puppy, but whatever. I'm not, I'm also not putting any limitations on it. I'm just like, here, this is your thing now. It doesn't cost you any money. With free as in speech. You know, there's, there are rights associated with that. And I guess actually before we get into all this, I should just Say that this phrase comes up in the context of discussing open source, right?

[00:25:31] **Adam:** So we say open source software is free as in speech not as in a puppy And so when something is free as in speech that comes with rights and sometimes it doesn't sometimes it doesn't come with some sort of like warranties of Suitability, right? It depends on the licensing in the case of open source So when you you know speech is free, but there are limitations on that, right?

[00:25:54] **Adam:** You can't yell fire in a crowded movie theater, for example, that's, that's not within your free speech rights. And so I think the, the, the crux of the, the statement is like it's saying, yes, this is something I've given you. That doesn't mean I promise to continue to upkeep it for your benefit if I'm, if I'm no longer interested.

[00:26:11] **Adam:** It doesn't mean that it, depending on the license, it doesn't mean that you can sell it, right? Maybe it's GPL and, and you can't include it in something that you go to sell or whatever. So it's, it's free, you're, you're, you can access it, you can read the source code, but that doesn't tell the whole story, I think is, is kind of what the, the phrase is implying, right?

[00:26:32] **Adam:** There's more to it. You have to read the license and know what the, the restrictions and limitations are.

[00:26:40] **Tim:** Yeah, I see, like, so free business speech is, users have the freedom to use it, they can modify it, they can distribute it, they can study the software. It's kind of like, you know, how Linux is, right? So people, if they want to do a fork off of Linux and create their own version of it and support that, they're totally able to do that.

[00:27:01] **Tim:** But, you download Adobe Acrobat for free. You can't change it, you don't get the source code, you can't modify it, you can't redistribute it but you can use it for free. So, so it's more like free as in beers refers to the cost only, whereas free in speech returns to the freedom more so than the cost.

[00:27:21] **Tim:** It's not really about the cost and freedom of speech, it's, it's the freedom that you have with the thing that is being granted to you.

[00:27:28] **Ben:** Oh, okay. That makes a lot more sense than I've ever had in my head. I've, I was one of the people who said that I've heard this phrase, but I've never really understood what it meant. And I never quite understood if it was even a good thing or a bad

[00:27:41] **Tim:** They both cost nothing, right? They both cost nothing. But one, you have a little bit more freedom to do more things with. With the beer, it's like, it's a beer. That's all it does. You drink it or you don't. can't do anything else with it, right? Can't sell it. You know, can't modify it. A beer is a beer is a beer.

[00:27:59] **Ben:** So when open source companies have in recent years said that. That this code is available, but for example, Amazon can't just repackage it and sell it as a service. That's free as in beer, not as in speech.

[00:28:15] **Adam:** Not necessarily. Right. So Redis for a long time was open source. And they, I think they made some licensing changes. So like new versions are under a different license if I'm not mistaken. And that the new license basically takes away Amazon's freedom to sell it as a managed service. Oh yeah, not just Amazon.

[00:28:39] **Adam:** I wasn't directly targeted them, but you know,

[00:28:41] **Ben:** But

[00:28:41] **Tim:** they, but they switched, right? So they, they went from freedom of speech to free as in beer, which they, you know, people have the right to do. They can change. They're like, if you want, I've seen tons of products do that. They're initially, they're completely free. And they're like, Oh, wait, people are really starting to use this.

[00:28:56] **Tim:** Like we've deprecated that version. It's no longer supported. And now the new version, you know, that has all these attachments to it.

[00:29:04] **Adam:** I'm not sure. Yeah, I think now we're just muddying the water again.

[00:29:07] **Ben:** on, I know on the changelog podcast, they always refer to that as the rug pull rug pull, not cool.

[00:29:14] **Adam:** Yeah yeah, I mean, my understanding is so, okay, a free beer doesn't mean that it comes with the recipe for the beer, right? You, you can't actually see inside. I mean, you, if you're a molecular biologist, maybe you could take it apart and figure it out. But shy of that decompiling the beer you, you, you get the end result.

[00:29:37] **Adam:** You don't get the, the source code. Whereas phrase and speech, you get the source code as well. And depending on the license, you may or may not have the right to resell it or include it in a for sale product, or, you know, maybe like, again, going back to GPL, if you make modifications under GPL, you're supposed to publish those modifications as GPL source code, right?

[00:29:59] **Adam:** You just publish your fork or whatever.

[00:30:01] **Tim:** Okay. I see what you're saying. So, I mean, I think we're oversimplifying both cases, honestly. Yeah, chat GPT told me freeze in speech equals freedom to control the software, but I mean, they can't put limits on, on commercialization of it. If the person is sharing something free, many times they want you to whatever you do with it to be free and they can put those constrictions on the license.

[00:30:27] **Adam:** Yeah. What was the license that you used, Tim? That was like no, no uh,

[00:30:31] **Tim:** That was the Bob Saget, the no Bob Saget. Clause, yeah, which was basically you could use this thing for free and, you know, when Bob

[00:30:39] **Adam:** long as you're not,

[00:30:39] **Tim:** long as you're not Bob Saget, which, you know, the guy from the guy from the dad from Full House, which when he died, someone found my, my repo and like wrote an article about it.

[00:30:50] **Carol:** Oh, wow,

[00:30:51] **Tim:** So, yeah.

[00:30:52] **Ben:** Well, aren't there some AI models now where you can use it for free, but only if you're under a certain number of users or something, I feel like Facebook.

[00:31:04] **Adam:** haven't seen that.

[00:31:06] **Tim:** Yeah. I mean, I mean, Zoom's like that, right? So Zoom is free, but you can use it for like 45 minutes at a call, right? Or a total number of people on the call is as a max, right? So that's free as in beer, right? They're, they're controlling the use of it. You don't get the source code of Zoom. Can't, you can't modify Zoom, but yeah, you can use it for free.

## [00:31:28] Open Source Packages

[00:31:28] **Ben:** I always wish that. Not always, but sometimes, so as many people do, I will just install packages off of NPM, you know, and then those packages install their packages, but sometimes I use a package that is so robust that I would like to somehow pay for it. And, and like, you'll go to, I'll go to the GitHub and there's nothing, like there's no option to do anything.

[00:31:55] **Ben:** And I'm just like, please just take a couple of dollars somehow,

[00:31:59] **Tim:** GitHub. Yeah, I know we ran into this a couple weeks ago. So we were using an authentication package. So it was in NET Core. So it was a NuGet package. So it's kind of like npm for NET. And I guess that when they downloaded that was like, just turned out just for timing. It was completely free at the time, right?

[00:32:22] **Tim:** Open source free. You didn't have to pay for it. But that was like the last version of it. And so a couple years later, someone's like, Oh, we need to upgrade this thing. And like, we'll be having to try to figure out why, well, like immediately the very next version that they, they dropped it, they said, this thing is deprecated, there's no more support for this.

[00:32:41] **Tim:** And now you need to, you know, pay so much per user for this thing. So now we're like, Oh, do we really have to spend 20, 000 this year that we weren't expecting? Yeah. So sort of a gotcha with, with free as in free as in beer. Sometimes the prices of beer go up.

[00:33:00] **Ben:** right? Like Docker for Docker desktop. I remember what it was like two or three years ago, they did

[00:33:06] **Adam:** is the status of that?

[00:33:07] **Ben:** It went from free to like, if you have more than,

[00:33:11] **Carol:** a user or something. 1,

[00:33:13] **Ben:** but I think only after you hit a certain threshold of users in a company.

[00:33:16] **Carol:** 500 is what it was, I think,

[00:33:19] **Tim:** Wow.

[00:33:19] **Carol:** quote me,

[00:33:20] **Ben:** it was much lower than that for sure. Yeah.

[00:33:23] **Carol:** Maybe we have something different. I thought it was after 1500. Maybe that's a different tool. Don't quote me. I don't want to lose Docker. I didn't say that you guys.

[00:33:32] **Tim:** that's sort of the crazy thing about these things. When they make these changes, you're like, well, what do you mean by a user? What do you mean by a client? Right. Cause there's, there's always ways around that. We'll just proxy this. So it looks like there's only one client coming through, but really it's, we're, we're federating it at a different level.

[00:33:48] **Tim:** So it's like, yeah, it gets tricky.

[00:33:51] **Adam:** So it's organizations with fewer than 250 employees and less than 10 million in revenue or get it for free.

[00:33:57] **Ben:** Yeah. I think we ended up having to, it was, it was one of those things where it's like, we didn't have that many engineers, but we had that many employees. And so I think there was some question about whether or not we still fell under the free tier.

[00:34:11] **Adam:** Yeah. That's dumb to me. Like why, why make it employees? Because not all employees are going to use it, right? What if your engineering team is four people like that's,

[00:34:22] **Tim:** I think, so the thing for the authentication thing was like the number of developers working on it.

[00:34:28] **Carol:** Oh, see, that's that's very specific, though.

[00:34:30] **Tim:** yeah, but it's like, well, we'll just. Tell one person to do the work. I mean, like what's, I mean, there's, yeah. So it's, it's, it's kind of weird.

[00:34:40] **Carol:** Tim writes it, Carol commits it.

[00:34:42] **Tim:** There you go. There you go.

[00:34:43] **Carol:** Yeah. See, I'm hitting some of this now, like, I don't know if you guys have been following some of the trying to account for what. The taxpayer dollars are spending, right? So we have to account for our software agreements. So things that we use for things that we use for file transfer.

[00:35:02] **Carol:** So, all of our software that we use is being evaluated and some of it has definitely been kicked back down and said, there are open source options that will fulfill this need. Well, then I have to go. Okay. It's open source, but is it secure? Is it supported? What is the support on it? And once I started using it, how many other people are actually using it?

[00:35:26] **Carol:** Right? So there's lots that go into it. And I haven't really thought about the fact that other agencies pay to use my software. Like we are a, like SAS type system. So they pay to have a seat on it. So then I actually can't use some of the open source things because we profit from the software itself. So, oh my God.

[00:35:48] **Carol:** Why'd we do this show, you guys?

[00:35:50] **Tim:** Oh, or, or they find out the government is using it. They're like, oh, now we're going to change the terms and now you got to pay for it.

[00:35:56] **Carol:** Agree.

## [00:35:58] Supply Chain Security Concerns

[00:35:58] **Adam:** and on the, just on the concept of the security thing that you kind of touched on there, Carol, the other less obvious thing is like, what's the supply chain? Like, yeah, maybe the current version has been community vetted and is considered to be secure and safe and everything, but. You know, it doesn't depend on some random package maintained by,

[00:36:17] **Tim:** One guy,

[00:36:19] **Adam:** person.

[00:36:19] **Adam:** Yeah. And yeah, so

[00:36:23] **Carol:** Yeah. Tracking down dependencies has been my job for the past two weeks, just so you know.

[00:36:28] **Adam:** yeah.

[00:36:29] **Tim:** fun.

[00:36:30] **Carol:** Mm hmm.

[00:36:32] **Tim:** I think I'd rather do PCI compliance.

[00:36:35] **Carol:** I would, too. Oh, don't fire me! Don't fire me! Please don't fire me!

[00:36:41] **Adam:** I have a compliance officer opening on my team. Carol, come, please come take my job.

[00:36:48] **Carol:** Oh.

[00:36:49] **Adam:** Yeah. Okay. I think, have we, have we muddied the waters enough on this?

[00:36:53] **Tim:** Probably.

[00:36:54] **Carol:** Probably, yeah.

[00:36:56] **Adam:** We tried to help. Did we help?

[00:36:58] **Ben:** Oh, you helped me. I'll put it, I'll, I'll say that much. I feel like now I actually know what people are talking about, at least vaguely.

## [00:37:05] Open Source Beer

[00:37:05] **Adam:** So then what I wish I could remember the details of this better, but I do remember there was a time you know This was a phrase that has not been I guess in vogue if that is still a phrase about a phrase that is well used but uh the the nobody really says phrase in Speech not as in beard that much anymore.

[00:37:26] **Adam:** I think it's just not common lexicon

[00:37:28] **Tim:** Just Scott, Scott Strohs. Isn't

[00:37:31] **Adam:** Well, who's that? And

[00:37:33] **Carol:** Wired only posted on it in 2006, so I think it's still

[00:37:37] **Adam:** been a few years, well, but it's been a few years and somewhere along the line, somebody, I think being cheeky about this turn of phrase created a beer, like literally a beer and, and I believe if I'm, if I'm recalling correctly, it was called open source beer. And so now that beer is, it can potentially be, if somebody is giving it away, free as in beer and free as in speech, because you can have the recipe and it, I'm sure it has a license and stuff

[00:38:09] **Ben:** very

[00:38:09] **Adam:** it just, just serves to, to make things even more confusing because that's what we need in the open source community.

[00:38:15] **Carol:** there's

[00:38:16] **Ben:** Schrodinger's beard there.

[00:38:18] **Carol:** well, there's, there, there's definitely a website called open source beer project. com. So,

[00:38:24] **Adam:** great.

[00:38:25] **Carol:** you know, there's a recipe listed and I don't know if it's good or not. 2020

[00:38:31] **Adam:** What I had for breakfast two days ago, but I can tell you about a beard that I heard about and have never had years ago. So yeah, okay. Well, then I guess we should just say you're welcome.

[00:38:46] **Carol:** for whatever this is. Yeah.

[00:38:49] **Adam:** Yeah

## [00:38:50] Patreon

[00:38:50] **Adam:** Alright. Well then this episode of working code is brought to you by svelting all over the place

[00:38:53] **Tim:** ha, ha.

[00:38:55] **Adam:** And listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[00:39:02] **Adam:** Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo, you guys rock.

## [00:39:10] Thanks For Listening!

[00:39:10] **Adam:** We are going to go record the after show, that is for the patrons of the show. If you would like to become a patron of the show, get access to the after show, listen to us, keep talking after the outro, then it's really easy to do.

[00:39:20] **Adam:** You go to patreon.com/workingcodepod and throw a few dollars our way. It can be as, it can be less than four dollars a month. So that's a pretty inexpensive and We hope that some people do it because it's good. It's good stuff. We like making it anyway, That's gonna do it for us this week.

[00:39:38] **Adam:** We'll catch you again next week and until then

[00:39:41] **Tim:** This is free as in speech, your heart matters.
