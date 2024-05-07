---
title: "177: Infinite Invisibility Timeout"
description: "Adam uses the new CSS color functions for HSL (Hue, Saturation, Lightness). Ben dives into the Algolia search service. Carol is trying to alleviate performance concerns around an N+1 SQL problem. Tim is getting some great feedback regarding his AI-powered call system."
date: 2024-05-08
---

<script async defer onload="redcircleIframe();" src="https://api.podcache.net/embedded-player/sh/30227421-bc27-45c2-bfb4-861def7dd4cc/ep/37f8d3ba-90e8-4ad3-8125-5d7fda3fef9f"></script><div class="redcirclePlayer-37f8d3ba-90e8-4ad3-8125-5d7fda3fef9f"></div>

Adam uses the new CSS color functions for HSL (Hue, Saturation, Lightness) in order to [create a heatmap][hsl-so] for the number of dollars raised by his platform. Ben dives into the [Algolia search service][algolia] as a way to provide a search feature on his blog. Carol is trying to alleviate performance concerns around an N+1 SQL problem using an ORM (Object-Relational Mapper) that has decided to use an N+1 selection strategy as "the way" with no escape hatch. And, Tim is getting some great feedback regarding his AI-powered call system that will alert customers to upcoming renewal dates.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[algolia]: https://www.algolia.com/
[hsl-so]: https://stackoverflow.com/a/27263918/751
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/177-infinite-invisibility-timeout.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** The day after we had that discussion here on the podcast about like, you know, we had done certain things and I, I decided not to disclose what we were doing, right?

[00:00:07] **Adam:** And by 11 o'clock that night, we were being attacked. And so part of me was like, right, is my computer compromised or is somebody listening in? They're trying to figure stuff out. Right.

## [00:00:38] Intro

[00:00:38] **Adam:** Okay. Here we go. It is show number 177 and on today's show, I don't even know what we're going to talk about. We're going to figure it out live. Doing it live, just like Bill O'Reilly. but first as usual, we'll start with our triumphs and fails. Tim, it looks like it's your turn to go first. What do you got, man?

[00:00:53] **Tim:** Man, I went first last week and Carol wasn't here.

[00:00:57] **Adam:** Fine. Well, let's, let's, we're fixing it live too. All right.

## [00:01:00] Adam's Triumph

[00:01:00] **Adam:** Adam, it's your turn to go first. What do you got? I'm going to start us off with a triumph. I got to write some code, which, you know, I like shouldn't, shouldn't be that mind blowing, but

[00:01:09] **Tim:** do you do for a living?

[00:01:11] **Adam:** Right, between all the compliance crap that I have to deal with and now, you know, we hired a junior dev and I've been mentoring him and, you know, just trying to kind of be like his personal project manager, I guess is kind of how I'm thinking about it.

[00:01:27] **Adam:** that's been eating up quite a lot of my time. And then,

[00:01:30] **Ben:** And didn't you say last week that you were the only senior developer in the office this week?

[00:01:35] **Adam:** it might've been similar to that. Yeah. not, not for the whole week. one, one of my coworkers was out for a week, in Amsterdam and then the other was out for a day. So there was a day where I was the only one.but, yeah, so I got to write some code today and I, I, look. I'm not this smart, but I found some really smart code on Stack Overflow that I was able to copy and paste, and I really impressed somebody.

[00:01:56] **Adam:** so basically, you know, you guys know what a heat map is, right? You know, like, you look at the, the radar for where it's gonna rain, and like, the, the more red and angry the color is, the more, like, crazy the thunderstorms are gonna be, right?

[00:02:07] **Ben:** It's kind of what the predator sees.

[00:02:12] **Adam:** very similar. well, so I was, I just like Googled, you know, like, I don't know, CSS colors, heat map or something like that.

[00:02:18] **Adam:** And I landed on this Stack Overflow question. I will leave the link in the show notes, but, and it just had this like super terse, elegant, like smart way to implement heat map coloring based on like a percentage of a, of a number range. and, basically it's just, you use instead of RGB, right? You can do CSS colors with RGB.

[00:02:37] **Adam:** You can do them with hex, which is. Base 16 RGB, you can do lots of different, I dunno if it's technically color spaces or, or just for different syntaxes, right? So another one of them is HSL Hue, saturation, and luminance, I believe is what that stands for. and as it turns out, hue is basically a range from, I think it's zero to 2 55 or two 40, something like that.

[00:03:00] **Adam:** that goes from like, blue to red or red to blue, something like that. and, and it just goes like through all of the colors. in, in order or whatever, you know, like, like gradually moving from blue through, whatever, green to, to pink and red. and so basically all you have to do is like know your max and min values and you just like,scale that, right?

[00:03:21] **Adam:** That, you just have to change the hue value and you just pick like a saturation and a luminance. So like 100 percent saturation, 50 percent luminance. You scale the, the hue according to their dataset, right? So if your minimum value is a hundred and your maximum value is 500, then, you know, like a 500 would be a one, in terms of percentages, right?

[00:03:40] **Adam:** Zero to one.

[00:03:41] **Ben:** is it hue typically what we think of as a color? Like this is a blue hue, this is a red hue. And then you're kind of going saturations and luminances within that sort of ballpark.

[00:03:52] **Adam:** I think, look, I'm no pro at this. I'm not a botanist, but, but

[00:03:55] **Tim:** you do know how to copy and paste.

[00:03:57] **Adam:** That's up there with the best of them.and, yeah, so like basically you just, you just, you know, determine your minimum maximum values and you, so, and you scale that so, so that it matches up with zero and one, right?

[00:04:10] **Adam:** And so that's like a percentage basically, right? 0. 1 is 10%. and then you pass it into this function and it's very basic math. It's like one minus that percentage. You take that number, multiply it by 240, and that's your hue value. and

[00:04:25] **Ben:** you actually heat mapping though?

[00:04:27] **Adam:** that's a good question. so in this particular case, it is a grid of cells.

[00:04:33] **Adam:** So, think of it as a multi year calendar, right? So it's a, it's 12 cells across, and then however many years you want to look at vertically. So a row is a year, January through December.

[00:04:46] **Ben:** Okay.

[00:04:47] **Adam:** and then for each of those months, there's a value, right? And in this case, I was doing, number of dollars donated and also number of donors.

[00:04:55] **Adam:** And, and I was allowing them to flip flop between heat mapping based on donor count and on dollars.and so it's like, this is for recurring giving, right? So somebody might have it set up to do. you know, make a gift that's 10 a month every month for the next three years. Right. And so it's like, they want to be able to visualize money coming in and like, where does it dry up sort of thing.

[00:05:19] **Adam:** And like, Just

[00:05:21] **Ben:** So as, as an analogy, not an analogy, it's not the right word, but as, as a prior art that people might be familiar with, this sounds a little bit like the GitHub so like commit streak where instead of weeks and days, but you know, they have intensities based on the number of commits you're, you're doing that, but for donations, essentially.

[00:05:39] **Adam:** Yeah. Very similar, right? So that one is, a single year and they show you like every day in that year, but it's the same basic idea. It's a grid of squares and there's a single color and it's just, they're changing the intensity based on the number of commits. I'm changing color to be a heat map. and, and yeah, it's scaled based on either dollars or donors.

[00:05:59] **Adam:** and it was, it's, it was super easy, right? You just, I just like embedded. The minimum and maximum, dollar and donor amounts in JavaScript variables on the page. And then there's just like,set them as data attributes, right? So if this hell,

[00:06:12] **Ben:** So just to pull it back to the HSL calculations, essentially you have, let's, let's call it the, a green H for donations, green hue, and then you're, you're kind of fading in between the min donation and the max donation for the saturations kind of a strategy. You're like, no, not at all.

[00:06:31] **Adam:** for, for what I

[00:06:32] **Ben:** dumb question.

[00:06:34] **Adam:** and you should feel bad. no, the, the code that I used was almost a direct port from the stack overflow post, but, basically the hue is the only thing that changes and it

[00:06:45] **Ben:** okay. Okay.

[00:06:46] **Adam:** Scaled based on that, that percentage that you're passing in, right? So like this particular cell should be shaded as if it is at the 75 percent mark.

[00:06:54] **Adam:** So it'll be maybe sort of yellowish pinkish, not quite red. and then, the saturation and the luminance, I just hard coded.

[00:07:04] **Ben:** Gotcha.

[00:07:04] **Adam:** I, I've realized like after the fact, So initially those colors are very like vibrant, right? If you just do, cause so mine, I scaled the hue and then the saturation I set to a hundred percent and luminance at 50%.

[00:07:17] **Adam:** And that's just what I copied and pasted it out of the stack overflow thing. And I was doing that like scatterbrained thing where you're just like, okay, well, here's the thing it works, but I want to change it. What do I know about how I could change this? I'm like, well, I'm using HSL and these colors are just too, like, too, too much like 1995 GeoCities, right?

[00:07:35] **Adam:** Like just too caustic. and so I was like, I need to, I just need to tone it down a little bit, especially cause there's text on top of these colors, right? It's a, it's a grid cell. And I want you to get a sense of color, but I also want you to be able to read the data that's in there. And I don't want to have to like, okay, well, if the number is above this color, then I want the text color to be white.

[00:07:53] **Adam:** But if it's below this color, then I want it to be black. And in this range, it needs to be something else. You don't have to do that. Right? I just wanted all the colors to be muted enough that black text looks good on all of them. And so what I ended up doing is I happen to remember, yes, there's HSL, but you can also use HSLA, which just adds another component for alpha for transparency.

[00:08:16] **Adam:** So then I just, I just changed the HSL to HSLA and I added another, like I said, it's like 40 percent or something, 0. 4. and. That way it just mutes all the color. It will, so it makes them partially transparent. So what the background color of the page shows through, which is this like sort of grungy gray color that we have, almost looks like off white eggshell y, but whatever.so that's how I fixed it. But you know, in hindsight, I'm looking at this going, you know, I bet you I could have played with the luminance or the saturation to get those where I wanted them, it would have been same effect. I mean, ultimately the browser is going

[00:08:49] **Tim:** at a hundred, right?

[00:08:51] **Adam:** I'm sorry.

[00:08:52] **Tim:** You had the saturation at a hundred.

[00:08:53] **Adam:** Yeah. Saturation's at a hundred and luminance is at 50%. And ultimately, you know, the browser is just looking at this input and it's just doing some math and saying, okay, well, based on these layers of things that I'm displaying, because it's got to account for alpha, and the colors that I'm getting as inputs, here's the color that I'm going to make that the background of that div, right?

[00:09:13] **Adam:** And so, I probably could have figured it out with the HSL instead of HSLA, but I did it with HSLA and it worked and it was great. It's beautiful. And everybody loved it.

[00:09:23] **Ben:** the new color functions give me, I don't want to say anxiety, but it definitely feels like one of those technologies that I'm going to be very late to, I feel like it's almost going to take a designer telling me that I have to use a particular HSL color before I actually care. Because when I hear it described, it's all about this brilliance and this vibrance.

[00:09:51] **Ben:** And especially in terms of these radical gradients, you know, like gradient from hot pink over to deep purple. And I'm like, I, I don't build apps that have gradients like that, you know, full transparency.so I feel like I'm going to be very late to trying to learn these and pull these in and make them muscle memory.

[00:10:10] **Ben:** And

[00:10:12] **Carol:** Ben. Like, we have people that handle most of it, and I don't want to touch it.

[00:10:18] **Ben:** it's a complicated, you know, I, I don't know anything about color theory. You know, if you said, what's, what's the opposite What's the complementary color to orange? I don't know. I'd have to look on some sort of a wheel, I assume. And, I don't understand any of that stuff and, and I barely understand RGB and how those colors interplay.

[00:10:37] **Ben:** I mostly just little color

[00:10:38] **Tim:** men, most men have hard time naming more than seven colors. Anyway, right?

[00:10:43] **Adam:** Mm-Hmm.

[00:10:44] **Carol:** I think that's most software engineers, like us. This is us. Cause I, I get the eyeshadow palettes that go, you should match this if your eye color's this, but if your hair color's this, you should do this. And I'm like, where's the one for the blue eyes and red head? That's like, not a thing in palettes. It doesn't, it never works.

[00:11:02] **Carol:** So I'm like, I give up. I give up.

[00:11:05] **Ben:** So I'm going to have to be led. I'm not going to lead in terms of this stuff.

[00:11:09] **Tim:** might be a good thing.

[00:11:11] **Ben:** I do love that the Chrome DevTools. They, they seem to default to HSL whenever you're looking at a color in the web inspector, and then they have, you can switch between the different modes, so you can look at it. Pretty much, normally what I want to do is grab a color from the page and then tweak it, so I have to, it, I open it up and it's in HSL, and then I, Flip it over to RGB, and then I can start to play around with the little hexes, which I understand.

[00:11:37] **Ben:** But for the most part, when I'm picking a color, I have that giant gradient map. I don't know what the term for that is. And I'm just like clicking around until something looks right. That's, that's my color theory right there.

[00:11:49] **Adam:** Yeah. So, you were talking about like the new color functions and stuff, and I'm starting to get a little worried that we're headed for, you know, how like a few years ago we talked a lot about like JavaScript fatigue. I feel like we're kind of heading for CSS fatigue. I feel like there's so much stuff coming.

[00:12:03] **Ben:** that too. I feel that. And I also feel very much like I don't know what is safe to target. So I was just reading up that Google, I think it's Google, came out with this concept of a. of a baseline and they have a CSS and JavaScript baseline and anything that has been introduced within the last, I think it's like 36 months, is considered newly available.

[00:12:29] **Ben:** And then once all of the modern browsers have supported it for 36 months, it's considered broadly available. Yeah. And the idea being that things that are broadly available are safe to quote unquote, just use, I don't know. You know, I look in my error logs and freaking someone made a request to my site the other day with an IE9, which clearly I don't care about that. But, but

[00:12:55] **Adam:** Ben, I used to on my personal blog, I don't think it's still there, but. I used to do browser detection, and for any version of IE, I would like, force the font to Comic Sans, and like, Giant, and, and there was a message that would show up on the page like, You are being punished for using Internet Explorer.

[00:13:12] **Adam:** Here are some real good

[00:13:14] **Carol:** Oh my goodness.

[00:13:16] **Ben:** but it's so interesting. So for my error logging, and this is, this would actually be an interesting topic as well for another time, but just how to remove some of the noise from error logging. I've been using something called a Bugsnag, which has actually been a pretty solid product. And one of the features that they offer.

[00:13:32] **Ben:** Is that they will automatically ignore browsers that were released after a certain version, or I guess they'll automatically ignore earlier versions. But the defaults are really old. Like they start ignoring, it's like Chrome 36 and Chrome 36 came out in like 2014.

[00:13:50] **Tim:** What version of Netscape

[00:13:51] **Ben:** Yeah.

[00:13:51] **Tim:** use?

[00:13:53] **Ben:** Anyway, that's, I forget even how I got onto this just now.

[00:13:56] **Ben:** Oh, the CSS fatigue. Yeah, it's, it's, just generally speaking, I'm, I'm starting to at least lean into this idea of this newly available for versus broadly available. Cause I go to caniuse. com, which is a fantastic site. I'm sure we all use it all the time and it'll show you what browsers support, what features, but one of the cool things is that it has a date based rendering and it'll actually show you over the years when browsers actually started to support different feature.

[00:14:24] **Ben:** So I can kind of take that. You know, general cutoff date and say, okay, if, if, if every browser supported this since 2021, which is three years ago, three and a half years ago, you know, I'm going to, I'm just going to go for it.

[00:14:38] **Adam:** Not me, man. Once it hits evergreen browsers, like, once all the evergreen browsers have it, that's good enough for me. YOLO.

[00:14:46] **Ben:** man. Good times. So what is this, heat map built in? Are you, are you living the Svelte

[00:14:51] **Adam:** You know, I refuse to answer that question on the grounds that it may incriminate myself or others.

[00:15:00] **Ben:** I didn't, I didn't know if this was a client side thing or a server side thing.

[00:15:04] **Adam:** The, the heat map part of it is all JavaScript in the client. but it's, it's all based on data attributes in the divs, right? So like the server side stuff has the data and it just like, as it's rendering the view, it's like, okay, well,you know, it's looping over the data to, to drop these grid cells in.

[00:15:21] **Adam:** While it's doing that, it's just saying, okay, is the current value greater than the maximum or lower than the minimum? If so, then update the, the max min on the page, like the, the in memory available or variable on the page. And also for each cell setting like data donors equals the number and data dollars equals the number, right?

[00:15:42] **Adam:** So just setting data attributes. And then, and so initially the cells are all just like gray. There's no color. And then as when the page on load event hits, then it calls the function that looks at the data attributes and colors them all accordingly. Because now by the time that that has happened, I've also embedded a JavaScript variable that says, okay, the min is this, the max is that.

[00:16:03] **Adam:** and that way it can scale them accordingly.

[00:16:07] **Ben:** Very cool.

[00:16:08] **Adam:** That was super fun. I'll have to like, maybe I can post a screenshot of it in, in our discord, but I'll have to find a way to like blur out the numbers. Cause that would be. I mean,

[00:16:18] **Tim:** The money.

[00:16:19] **Adam:** Maybe not. I mean, it's, it's interesting numbers and it's kind of impressive for the school that I happen to be looking at at the moment.

[00:16:24] **Adam:** But, if I just don't tell you who it is, then that's, that's not breaking any privacy or anything, right?

[00:16:29] **Ben:** There you go.

[00:16:30] **Carol:** Well, good. If you're going to post it, why is the highest number red and the lowest number starts getting green and then blue?

[00:16:37] **Adam:** Yeah, so that's just because that's the way that, heat maps traditionally work. So if you look at the, you know, the radar, right, like red is the angriest, it's like the, the biggest, most attention grabbing portion of the, the radar, right? Yeah. So, and it's, it's honestly because, you know, that's what the, well, A, it's because that's what was in the stack overflow post that I copied, but I did like consider it and I was like, okay, well, you know, maybe I could multiply it by negative one or something to flip it around, who knows.

[00:17:09] **Adam:** or something like that and figure out the math, but I was like, you know, this is traditional enough.

[00:17:14] **Carol:** red on dollars makes me think bad. Green is good.

[00:17:18] **Adam:** True. And the other thing going through my head as I'm looking at this is like, it's not like, colorblind accessible, but I mean, the, the data is there, but I don't, I don't know how you could, I guess you could do like a, just a black and white version that, that, you know, like just change the color intensity of the black or whatever,

[00:17:39] **Tim:** And these, these gifts are tax deductible, right?

[00:17:42] **Adam:** I don't think so.

[00:17:44] **Tim:** No, because I was wondering why I'm just looking at the data. Why December is like the highest one is they, they try to get those donations in before

[00:17:51] **Adam:** Some of them, actually some of them could be. Yeah, I guess it depends, right? So if you are making a donation and you're not getting anything in return, I think that those are considered tax deductible. But like some of them, you know, you're, you're making a donation to a university and sometimes they'll give you like socks with the school logo on them or VIP

[00:18:09] **Tim:** I mean, you didn't donate to NPR. They give me a tote bag.

[00:18:11] **Ben:** right.

[00:18:13] **Adam:** I don't know what the exact rules are, but you know, like some of them get like special seats at sporting games and that sort of stuff. So. There are things that we have in the system that like, okay, I can, I can waive my, my, sport seats, benefit. And that makes my gift tax deductible sort of thing. I don't know.

[00:18:32] **Tim:** I was just curious.

[00:18:32] **Adam:** I just write the code, man. I don't understand the law.

[00:18:36] **Tim:** Looks good though.

[00:18:37] **Carol:** I like

[00:18:38] **Adam:** Yeah, so I'll post a screenshot in our discord in the, what'd you call it?not in the early access channel, but in the, in the, podcast adjacent. Yeah. Podcast adjacent. So I'll post it there. I guess I'll have to post it. I'll post it in early access when this show comes out of early access and I'll post it again in podcast adjacent when we, when that happens. So that's it for me. I got to write some code. Super excited about that. How about you, Ben? What do you got going on?

## [00:19:04] Ben's Triumph

[00:19:04] **Ben:** I will also go with a triumph and that is that this week I started looking into a search indexing service called Algolia. I've heard of Algolia. I think they've actually been around for a really long time. but I had only ever seen them in the context of static sites. Like, you know, here's a Jekyll or a Ghost blog and, and someone will wire up a, I know what I suggest using Algolia, but apparently it can work with anything, including dynamically driven applications.

[00:19:34] **Ben:** And, it's. It's pretty cool. It is, it is bonkers fast. Like I hit a key and I get search results in, in like 16 milliseconds or something insane. granted, I haven't really indexed all my data yet. I'm just kind of doing trial and error stuff, but just the round trip speed from my server. Plus I'm going through my server to then get to their server and then, and then back, which they don't recommend.

[00:19:59] **Ben:** They would rather have a client side. Search that goes directly to them for speed purposes, it's just, it's just fun and it's forcing me to think about how it has to be structured. So they have pricing plans, obviously, as any service does. And on the free plan, the documents that you post that can be indexed have a 10 K size limit.

[00:20:23] **Ben:** And most of my blog posts are under 10 K, but I have, you know, a couple of dozen that are larger than 10 K. Some, I think my biggest one is like 83 K in size about database index design. So what you have to do is you have to take these large documents and split them up into sub 10 K. Parts, but then you have to be able to group them internally to the document indexing to say that these are all actually the same document.

[00:20:49] **Ben:** So if you get back three of these, you should only return the most relevant one. And then you have to help it figure out which the most relevant one is. And that's just for the blog content. But I also want the comments to be searchable as well, because they're oftentimes quite relevant to the conversations.

[00:21:02] **Ben:** Then you have to index the individual comments and then like the splitting of the large blog posts and say, these are collectively, this is all the same document. And, and you should be able to search for it and find it. And I don't have all the answers here yet, but, I'm trying to figure it out. And then you have to maintain that over time.

[00:21:20] **Ben:** So it's not just a one time. Let me index this on, you know, Friday and I'm good forever. Every time a new comment gets added, I have to update the index. Anytime a comment gets edited or deleted, or I post a new blog post or I deactivate a blog post, I have to re index. Just portions of the document. And then that's just for blog posts, but like, what if I want to index other parts of my blog, like the list of people that I have photos with?

[00:21:46] **Ben:** Stuff of that nature. It's, it's,

[00:21:48] **Adam:** Sounds like a lot of work,

[00:21:49] **Ben:** it does sound like a lot of work and the only reason I'm doing it is because someone asked me why I don't have search and I sort of did like a challenge accepted kind of a thing.

[00:21:57] **Adam:** Yeah,

[00:21:58] **Ben:** cause when I search my site, I use Google. Like I literally, yeah, I have a, in Chrome, I have a, I don't know, it's like kind of like a macro where I can type Ben in the search bar and I hit space and then it'll force it to search just my site.

[00:22:11] **Ben:** So I basically just use Google as my own personal search engine. And that's been, you know, I have one for Mozilla developer network as well. I type in MDN space and it automatically limits it to all of Mozilla

[00:22:23] **Adam:** I can actually do you one better on that.

[00:22:25] **Ben:** Hit me.

[00:22:26] **Adam:** So if you go to mdn. io slash and then just type something, just like guess, right? So if you're, if you're talking about like array reduce, just do like array dash reduce. It will use whatever comes after the slash and it'll try to figure out what doc you're trying to pull up and it'll take you right to that doc.

[00:22:43] **Adam:** And you don't, like, it doesn't have to be array reduce. It could be like, you could probably do reduce dash array and it would figure it out and take you to the same place.

[00:22:50] **Ben:** That's pretty cool. It looks like it bounced in between DuckDuckGo. I think I

[00:22:54] **Adam:** Oh, I don't know. I've, I've never bothered to look at it. It just, I

[00:22:57] **Ben:** Well, it just like, they looked like the URL flash DuckDuckGo, but yeah. Yeah, I see actually an array reduce at the very top. They have that baseline widely available that I was talking about. anyway, so yeah, I've been, I've been having some fun.

[00:23:10] **Ben:** Looking into this and

[00:23:12] **Tim:** So, so Ben, I got a question for you. So I'm looking up. Algolia and they, you said it's been around a while, but it looks like they're positioning themselves as an AI company. Is it actually what you're using? Is it actually do an AI or they just slapping that

[00:23:26] **Ben:** I think that's just, I think that's what everybody's saying now. It's a, I'm, I, I guess they're using AI to help improve the search somehow, something. I

[00:23:41] **Adam:** to my head. It's like, Oh, look, it's the one startup that's not doing AI yet. And here we are.

[00:23:47] **Carol:** Yeah, it literally says the one stop shop for AI search.

[00:23:51] **Tim:** yeah. AI search, a better search, AI search. That's easy to use. Get a demo. Start now,

[00:23:56] **Adam:** I wonder if it's like, after you get your docs in here, if you're paying for the AI feature or something, then like you get an AI assistant to help you find what you need in the docs, right? Like, Oh, I need to figure out how to do reduce in arrays. Where do I look that up?

[00:24:11] **Ben:** have no idea. I mean, I, I would assume it's more about the search results than it docs, but. I'm completely just guessing

[00:24:19] **Adam:** What do we know? Yeah.

[00:24:21] **Ben:** The, the whole concept of indexing, I've never had to deal with it before. I know that for years

[00:24:27] **Adam:** Lucene or anything?

[00:24:28] **Ben:** no, Lucene and then Solar, which are Solar was the paid one and then Lucene was the open source one or vice versa.

[00:24:34] **Ben:** I can't remember.I never had to use any of those. I worked at a place where someone had some of that stuff already set up and it was, it was customer facing. So it was for a legal website where they had bios of all the, of all the lawyers and case studies. And when they went in and edited the data, they would then have to manually go in and hit re index site and it would, and it would do all that jazz.

[00:24:59] **Tim:** I've never actually had to build any of that myself. So that's why I felt like this would be a fun little, exploration. let us know how it goes. And if it's actually AI or just not. Oh

[00:25:10] **Ben:** the, I, I, you know, the. The hardest part is that it's, I'm going to use the free tier. I mean, I have no interest in paying for this only because I don't make money from any of this stuff. So I'm not about to start paying more money to not make money. but so there are quotas and there can only be a certain number of searches, which I don't think I'm going to have a run on searches, but.

[00:25:29] **Ben:** It is a public site, so you could, in theory, think that a crawler could accidentally start submitting searches or doing something, or like I accidentally have a link somewhere that triggers a search and then that gets searched constantly and then all of a sudden I look at my stats and, you know, in two days I've eaten up all of my search quota.

[00:25:47] **Ben:** I very much feel like that could happen accidentally.

[00:25:50] **Carol:** the quota by day, by month? Do you know how the quotas are?

[00:25:54] **Ben:** I believe it's by month.

## [00:25:55] S3 Exploit

[00:25:55] **Ben:** You know, quick side tangent. Someone posted this, at work. I think that, There was some, someone discovered that if you, if you make a request to someone's S3 bucket and it gets rejected, that the person who owns the bucket still has to pay for that as a, as a request.

[00:26:15] **Carol:** Oh no.

[00:26:16] **Ben:** I, I think there are security things that you can do to prevent this, but this one guy. Accidentally, he, he chose a bucket name apparently that coincided with an open source library that used that as the example bucket name.

[00:26:31] **Carol:** oh.

[00:26:31] **Ben:** And he woke up, the day after building this thing and he had a hundred million requests to his bucket. And, it was like, it was going to cost him like 16, 000 or something.

[00:26:42] **Ben:** I mean, Amazon ended up waiving it, but that seems pretty crazy. I don't know if that's true. I hope, I hope that's,

[00:26:48] **Tim:** I saw something similar to that as well. The other day I read an article that talked about that, that like check your buckets because of. If people, they can start hitting them and to charge you,

[00:26:58] **Ben:** Yeah, that's nuts. That's like a different kind of DDoS attack. Like

[00:27:02] **Adam:** Right, it's a

[00:27:03] **Ben:** consumer attack.

[00:27:05] **Adam:** DDoS your

[00:27:06] **Ben:** Yeah. But that's the scary thing with anything that is usage based and public facing. You know, people, like we talked about with the credit card stuffing attacks. all it takes is someone to be deciding that you're a target and now I'm going to screw you.

[00:27:25] **Ben:** And it feels like there's very little that you can do sometimes.

[00:27:29] **Tim:** Just use the AI to stop it.

[00:27:32] **Adam:** Since you brought up the carding stuff, Ben, we had It was funny, like the The day after we had that discussion here on the podcast about like, you know, we had done certain things and I, I decided not to disclose what we were doing, right? Like we had that conversation, just the recording, right? If the podcast wasn't even published at like seven o'clock, seven 30, something like that in the evening.

[00:27:54] **Adam:** And by 11 o'clock that night, we were being attacked. And so part of me was like, right, is my computer compromised or is somebody listening in? They're trying to figure stuff out. Right. And, As it turned out, no, in this case, the, the, so the gateway that one of our customers and this particular customer was using decided that the MID, the merchant ID, belonging to the school.

[00:28:23] **Adam:** was like somehow fraudulent or involved in fraudulent charges, whatever. They just decided to like shut that mid down. And they, they talked to some of the people that were using the mid, but not all of them, including us. And so we just like out of the blue kind of noticed like, okay, seems like there's been a lot of, unsuccessful transactions for this customer.

[00:28:44] **Adam:** I wonder what's going on. And we look into it and it's been like, 24, 36 hours with zero successful transactions. We're like, okay, something's not right. Especially like, okay, GIFs, you might expect that to, to fail sometimes, but like, especially when you're talking about event registrations that are like 5 or, you know, 15, like that's, those are a lot less likely to be declined, right?

[00:29:05] **Adam:** Most people have five or 15 left in their, their, credit. Balance. What's the word? Credit limit. and so, we, you know, we were like, something's not right here. We, we kind of ran it up the flagpole with the school and they were like, oh, oh, yeah, that's important. So, here's some new information we need.

[00:29:21] **Adam:** We, like, need new credentials in the mid and stuff and, so we got that sorted out, but that was just like a man, you know, like, just out of the blue and very

[00:29:28] **Tim:** cause you posted the snippet, snippet of that conversation that you're having. And I was like, Hmm, that's remarkably similar to what we were talking about last night. You're like, yeah, scarily so.

[00:29:38] **Adam:** yeah,

[00:29:38] **Ben:** So that's me, Algolia. I'm having fun. I'll report back more when I have some more things actually implemented. But, Carol, what do you got going on?

## [00:29:48] Carol's Failure

[00:29:48] **Carol:** I'm going to go with a failure. I, I demoed my project last week and everything went good. We demoed it early this week and I found that there are some queries that run slow, the more data that builds, which happens, you know, I get more data, then you find that things run slow. Well, what turned into like.

[00:30:09] **Carol:** A week early on delivery and I was going to start working on the next phase has been a week of me convincing myself I need to fix every slow query, which is not the truth because even though it takes a minute to process it right now in production, if they try doing the same process, it takes 45 minutes to process those.

[00:30:30] **Carol:** So I've. Cut it down from 45 to 60 seconds. And I should say that that's a win, but in my head, I'm looking at these queries going, there's no way this is acceptable. Like this is, this is just data. It should not work like this. But the issue is that it's entity framework and the way it wants to link data, I don't have a lot of control over.

[00:30:49] **Carol:** So then it needs to pull back records to find if records exist in there. So I've been spending quite a bit of time playing with it and finally This afternoon convinced myself that I have to stop because I've killed my entire, you know, happy I'm way early on delivery and eaten it up just trying to take seconds off of something I've already taken, you know, almost an hour off of.

[00:31:13] **Ben:** And, entity framework, is that, like a, an ORM for NET?

[00:31:17] **Carol:** yeah, sort of. It is how we control our context and our data model.

[00:31:22] **Ben:** Gotcha. And I, and I ask it as a leading question, because I know with ORMs, Oftentimes you can say, Hey, get, I want to load data using this object model, but then for edge cases, I can dip down and actually sort of just write half SQL statements, half object statements. Does Entity Framework? It

[00:31:39] **Carol:** Yeah, no, so I can't write the half SQL statement. So everything is like, I want to know if this driver is associated to this vehicle. Well, because of how it's linked in some of the queries, the first thing I have to do is get every vehicle to then go see if the driver's on it, where really I just need to know.

[00:31:55] **Carol:** If I wrote in SQL, it'd be, is it tied together? Like just a join? Like do the, does the record exist, but you can't do it that way. It has to get the data first and then go look in it to see if it's there. So it's like 9, 000 records later. No, I don't have one. I'm like, Oh, I knew it already. I already knew I didn't have it.

[00:32:14] **Ben:** I'm, I'm, I'm chuckling because everyone always talks about. how do we avoid the N plus one problem, which is how do I, like, I do one query to get N records and then I have to do N more queries to get N more things. And it's like the entity frameworks solution there is what if everything is an N plus one problem?

[00:32:32] **Carol:** Yes, it's awful. It's so bad. So we're, we're getting rid of Entity Framework as we migrate off of, this older project that I'm working on right now. So the goal is to get rid of it, or as we upgrade to a newer version of NET Core to go to Entity Framework Core, which would then solve some of these problems, but we've started just adding procedures to do work and cut out the whole ability to use Entity Framework in some areas, but because this area is sovisible in the system.

[00:33:01] **Carol:** I can't do that yet. It's not like I can just say, and in this one spot, don't do it because the data is actually held in a transaction during this point. So I would have to then commit, figure it out, and then have a rollback option for if something happened later. So

[00:33:17] **Ben:** Bonkers.

[00:33:18] **Carol:** Yeah. But I'm stopping that.

[00:33:20] **Carol:** I guess that should be my triumph is I realized that I can't take more seconds off and it just needs to go to production cause my customer really wants it really bad.

[00:33:29] **Adam:** yeah. Well, I mean, there's always tomorrow, right? Yeah.

[00:33:32] **Carol:** Yeah. That's what my product owner said. Yeah.

[00:33:36] **Adam:** to a minute is a huge win. And then, you know, next week, next month, when you've got more time, squeeze a little bit more water from that stone.

[00:33:42] **Carol:** Yeah. And that's what she had said to you. She's like, well, what about if we just get it out and let's get it used and you start then getting your slow queries from the database and let's look at what we can do,

[00:33:53] **Tim:** Yeah. Incremental improvement. You might find out some of the things that are, were bad actors. They don't even ever run

[00:33:59] **Carol:** Yeah,

[00:33:59] **Tim:** run rarely.

[00:34:01] **Carol:** I would hope so, but the problem happens is when there's like 10, 000 plus associated records to another record. And that's exactly why my customer hired me was to fix, was to like fix that problem. Cause they, the IRS needs to hire 10, 000 people at a time. Like it's just what they do during tax season.

[00:34:18] **Carol:** So they have to be able to manage that kind of data. So I know my customer's going to run into it, but I think they may be the only agency that does. Like White House Fellows does. During the summer when they do their internship programs and stuff, you'll find that they do mass hiring and NASA does during, big like missions.

[00:34:37] **Carol:** But other than that, nobody does mass hiring like the IRS does. So other customers won't hit it, but mine will.

[00:34:45] **Tim:** Gotcha.

[00:34:47] **Ben:** Crazy. Could you, could you maybe, while this thing is running, Have some sort of, a little, like a little guy that pops up and tells dad jokes or something, you know, just to like pass the time.

[00:35:00] **Carol:** So actually what I guess I should tell you what it's doing, is everything was processing kind of like just in front of the user. So they would click submit and it would just sit and spin and they would have to wait for everything to save. And if one failed, then they had to still wait for everything to roll back.

[00:35:16] **Carol:** And it was just very messy. So now I have it writing to a message queue. So they basically just get told. Our process has kicked off. Go to lunch, go do some other work, go do something else. And then when you come back, you'll have a list of everything that's been created, saved, approved, like, and what happened with it all.

[00:35:33] **Carol:** And that's granted that they were doing thousands. If they're doing just a couple, like it's, you know, a second or two. So then they're able to just get the message back immediately.

[00:35:42] **Ben:** So what do you do? I, I, I'm so fascinated with the idea of message cues because as with all things, there is a happy path and a sad path,

[00:35:51] **Carol:** there is.

[00:35:52] **Ben:** What, what is the plan when you have this background query running? And then let's just, for sake of discussion, say that there's a transaction deadlock in the database and something times out, and now that query can't complete, what do you, how do you tell the user, Oh, by the way, that thing you requested has to be run again, or we requeued it automatically.

[00:36:13] **Ben:** What's the, what's the strategy there?

[00:36:15] **Carol:** Yeah. So, what we're doing right now is a requeue. So it will retry three or five times. Don't hold me to that. So it will do a retry. And, one of the things I added for my safeguard on it is I log when I start the process. So I go, Hey, I'm kicking it off. I need a thousand of these to be created. And then I have a service that runs.

[00:36:38] **Carol:** That's the one that goes and checks that table because every time the message processes, I didn't add like the, okay, it's processed, it's processed. So if in like an hour right now, that's a stupid number, but if in an hour it's not finished, then we go ahead and notify with an alert that says there was a problem in the process.

[00:36:55] **Carol:** Like, please submit a help desk ticket or go back and retry the process because I do some validation up front. So the error should only be if there is a glitch in the system. At which point the messages would still be on RabbitMQ waiting to be processed.

[00:37:11] **Ben:** So then, forgive me, I'm going to use the wrong words here, because I don't really know message queues, but I love to think about them. I, I, I believe there's a concept of, of like a, of like a, an acquisition timeout. Like a worker says, hey, I'm processing this message. But then the message queue has to assume that that worker could theoretically die without ever acting or knacking.

[00:37:33] **Ben:** So there, so the message queue says, if I don't get anything back in X number of seconds or minutes, then I'm going to assume that this has to be recued or something, what I assume

[00:37:42] **Tim:** dead letter.

[00:37:42] **Ben:** yeah. So I assume you, you have to pick a really high, like. It's like 90 minutes for a worker to respond or something.

[00:37:51] **Carol:** Yeah, for ours, it's not that long, only because each message is happening very quick. So by the time it gets sent over, it actually processes pretty fast. It, it's not keeping my time and count from like when I start to when I finish the entire process, it's per message. So I'm inserting one message for a request that I want to do.

[00:38:09] **Carol:** So they're half, like, You know, six are happening in a minute, 10 are happening in a minute when the data is huge. So I can't imagine it needing to be open for 90 minutes.

[00:38:18] **Ben:** I'm, I'm picturing one method call that's going off and taking an hour to run kind of a

[00:38:24] **Carol:** no, no. Imagine that I'm doing like a published batch of messages. So I'm sending out all of them. So it's writing like the, the test I showed a week ago was I wrote 10, 000 at one time. And I couldn't even test that the old way, but the new way, like an hour, all of them had been processed. Like everything was done. Yeah.

[00:38:45] **Adam:** So we've talked a little bit here about some of the vocabulary. I do have a good bit of experience with SQS, the Amazon, queuing service. And so I can give you sort of their version of the vocabulary. There was some wires across there and I want to make sure we at least try to present, truthful information

[00:39:01] **Ben:** educate me. I don't know

[00:39:03] **Adam:** it comes out.

[00:39:03] **Adam:** Yeah, so, yeah, you've got a bunch of stuff in the queue and when a worker comes by and picks up an item off of the queue, You're right that, you know, the, the queue has to assume that the worker might die in, in the middle of processing that and never ACK or NACK. So NACK would be like, reply back, like, Oh, I

[00:39:18] **Ben:** Acknowledge.

[00:39:19] **Carol:** something wrong.

[00:39:20] **Adam:** ACK would be success and NACK would be failure, like retry.

[00:39:25] **Adam:** and so in SQS, they call that the visibility timeout. So when you request the next item off the queue, it's still, I guess, technically in the queue, but it becomes invisible for a certain amount of time. So the next thing, like if you've got seven workers running. It's invisible to all of those guys because you don't want all the workers to pick up the same queue item, right?

[00:39:43] **Adam:** So it becomes invisible for a certain amount of time that you configure. And that way, if your worker dies without ever saying, I completed or I failed and you need to retry, then it'll automatically become revisible again. Now,

[00:39:57] **Ben:** Sorry. I didn't want to interrupt you, but I did want to interrupt you. Okay.

[00:40:00] **Adam:** Yeah, go ahead.

[00:40:01] **Ben:** I, I, so there's a concept of, in a message queue, something called a poison pill, which is essentially a message, which will continue to fail no matter how many times it's tried. and so I assume that in order to avoid that, there's some sort of a limit, how many times a thing can become invisible and then revisible.

[00:40:22] **Adam:** Yeah, so I think in SQS, if I remember right, it's just like a retry count, like number of times it'll automatically retry.

[00:40:28] **Ben:** know if that was different from someone knacking As opposed to just like going off into the ether.

[00:40:35] **Adam:** That is a good question. I don't know the answer off the top of my head, but then the, and the whole reason that I brought this up is that then there's the concept of the dead letter queue, which is if it fails a certain number of times, right? And it is again, configurable. So if it fails five times, then don't keep, there's your poison pill thing, right?

[00:40:51] **Adam:** Don't, don't keep doing it. Just move it over here to this other queue, the dead letter queue to say, okay, here's a message that I received, but I wasn't able to process it. And then you can do whatever you want with that. If you want to send it to your log aggregator or. Push a notification out to your on call alarms or to team chat or whatever. There you go. There's my, my, my segment of truth.

[00:41:13] **Ben:** I like it. I think we've mentioned this one time, but we had a weird edge case with message queues years ago where Kubernetes apparently will just occasionally lose track of a pod.

[00:41:25] **Adam:** You've mentioned that.

[00:41:26] **Ben:** yeah, yeah. So we had this pod just hanging out in the background for months, eating off of an existing message queue, but with code that was months old and it,

[00:41:34] **Carol:** Oh,

[00:41:34] **Ben:** kept failing in mysterious ways. Message queues. They're so fascinating.

[00:41:38] **Adam:** Microservices are great until they're not. Speaking

[00:41:41] **Carol:** Yeah. Yeah, I will say that's one thing that is exposed is the areas that we've written, application code that wasn't meant to, to be manipulated while it's being used elsewhere. So everything, like anything async, like you can forget it. Like there's so many places and like, oh, this is not going to work well.

[00:42:02] **Carol:** Is it? And sure enough. Yeah. I am looking at the database and there's just weights. It's just waiting and waiting because something else is holding that table data because the application wasn't written in a way to assume that I would never, that I would ever need to access it at the same time.

[00:42:17] **Ben:** We are

[00:42:18] **Adam:** of, microservices, hell.

## [00:42:20] Microservice Testing

[00:42:20] **Adam:** sorry, another tangent, but that's, that's what we do here. the, so we, we hired this, junior developer co op, and one of the things I've been having him do is go back and add tests to a bunch of, like, Lambda functions that don't currently have tests. And, you know, every now and then he'll ask me questions about, you know, like, why is this happening? What, how do I deal with this? And today I got to say like, welcome to the hell of, of testing with microservices because it's like to run one, you know, maybe 30, 40, 50 line long function, you have to like mock six different AWS services and database and this and that.

[00:42:55] **Adam:** It's like, yeah, sorry.

[00:42:58] **Ben:** yo, for real. I, I always loved the idea of a lambda function being about as stupid as you could possibly make it. Like have it, have it assume nothing that all of the messages that it pulls in should have all of the data that it needs, including like where it should send the data that it produces.I've never actually done that.

[00:43:19] **Ben:** But I've always been enamored with that idea so that it could just be as stupid as possible.

[00:43:25] **Adam:** Well, but something has to organize those messages and. Send them to the Lambda functions, right? So then you have to, you still have to write tests for the, the data lookup and, and

[00:43:34] **Ben:** Right, right. Like, like an integration kind of a

[00:43:37] **Adam:** Yeah.

[00:43:37] **Ben:** Oh, man.

[00:43:38] **Adam:** You're just, you're just kicking the can, unfortunately.

[00:43:42] **Ben:** is very

[00:43:49] **Adam:** he says under his breath.

[00:43:51] **Carol:** Under his, you know, what he whispered in his breath.All right. What about you, Tim? What you got going on?

## [00:43:57] Tim's Triumph

[00:43:57] **Tim:** so last week you weren't here, Carol, but I talked, talked a little bit. I was playing with the AI service. So basically what this AI service does is it bundles a large language model with a voice generation system and, a VoIP,

[00:44:12] **Adam:** Yeah. It's got a 1 900 number and it talks dirty to you. Mm hmm.

[00:44:17] **Tim:** it's a VoIP system. So basically you can, it's a, a call in or call out agent, AI agent that you can talk to.

[00:44:24] **Tim:** And so I took, some of, you know, our customers. I have an API that pulls customer's data and just kind of populated. So you basically send a JSON query, a JSON payload to the API and you got to give it a prompt and you can also give it a data dictionary. And it figures out from the data dictionary and the rules in your prompt, how to, how to interact with the customer.

[00:44:48] **Tim:** And I, I. So that's what we talked about last week. So I've been showing this off to a bunch of our existing customers and using their data and they're just, they've been blown away. So it's getting a lot of attention. it is pretty cool. Cause it's like, I will put in, you know, cancellation date of the policy, just data points, I'll just name them, cancel.

[00:45:08] **Tim:** Underscore date or, and it figures out, you know, I'll say, what's, you know, when does my policy cancel? Well, Tim, your policy will cancel on this and this date. If you don't make a payment and I don't write any of the responses, but it figures it out. So that's, that's pretty cool. And it's fast. That's the biggest thing.

[00:45:24] **Tim:** It's really, it's not, it responds rather, you know, very quickly for a lot of times you're sitting there and chat GPT and you watch the thing spin. Right. This one, you ask a question and it's almost immediate that the return, you're not going, did you hear me? Could you hear me? But one customer asked me, he said, well, you know, we got a lot of customers that speak Spanish.

[00:45:45] **Tim:** Can you, if they are speaking Spanish, can you have it switched to Spanish? So I played around with that and that wasn't quite as successful. They do have Spanish, do have Spanish language voices that you can choose from and they sound really good when you tell it, you have to. Tell it that this call is going to be in Spanish beforehand.

[00:46:06] **Tim:** You have to say this calls in Spanish and, this is the Spanish voice I want you to use. Use, you know, Lupe or, you know, Carlos was another one. I think it was. And, you do that. It sounds really good. That's the thing. You have to tell the call beforehand what language it's in. And I don't know if the person I'm calling is Spanish, right?

[00:46:24] **Tim:** I don't have, that's not a data point I have, if their primary preferred language is English or Spanish. So I did get it to do and, and I'll just, I was in, in English lady. It was the voice was in English, a female voice. And I said, can you repeat that in Spanish? And she did, but it sounded like an American tourist in Tijuana.

[00:46:48] **Carol:** Oh,

[00:46:48] **Tim:** donde esta su madre? You know, it wasn't, it wasn't that that you normally get from, from us. So it sounded very funny, but I don't think it's quite what the customer wants. So I still played around with it to see if I can get a convincing bilingual AI. But it was pretty impressive that it actually translated the English prompt into Spanish,

[00:47:11] **Carol:** so, but

[00:47:11] **Tim:** it was really slow.

[00:47:12] **Carol:** you had to ask for it in English though, right?

[00:47:15] **Tim:** for it in English. I did try, I did try in my Google Translate Spanish to ask it in, en Español, por favor. And no, it didn't. But when I said, could you repeat that in Spanish, please?

[00:47:28] **Ben:** It'd be really interesting to start doing some sort of a A B testing. Cause I, I'm this, so this, you said this is a bland AI, is that the service? And, and I feel like I remember you saying there's a whole bunch of different voices you can choose from. It'd be fascinating to say, okay, we're going to generally speaking, split our customer base into male and female, and then we're going to start testing whether male and female respond better to male and female voices and like which voices.

[00:47:57] **Ben:** I mean, you'd have to have some sort of metric that says this was a successful call versus a non successful call. But. It'd be really interesting to see that kind of data.

[00:48:06] **Tim:** If there's a good way to track that. Cause yeah, that changed. I switched it to a male named Tom and sent it to somebody. He's like, guy was like, it was a guy that I sent it to. I was like, Ooh, I don't like that. That guy sounds really stern. Like your policy will be canceled if you don't make a payment today.

[00:48:23] **Ben:** down, Tom.

[00:48:24] **Carol:** yeah, I know that sounds threatening. Yeah.

[00:48:26] **Tim:** Tom, get off my case, man. So we've, we've been knocking on AI, but actually it's, some of the stuff you can do in this, it's pretty cool, but I'm just trying to find those edge cases, right? Those edge cases is where they get you, because I think we talked about that last week, that there was, a court case where an AI for an airline, you know, quoted something wrong.

[00:48:46] **Tim:** I think it was about the cancellation policy or something. And promised them that they would get paid. And they, airlines like, no, you know, that's not our policy. The AI made it up and court made them, court made the airline pay it.

[00:48:58] **Adam:** hmm.

[00:48:59] **Tim:** So if they, I make something up, you know, you could be on the hook for it.

[00:49:04] **Carol:** So how would that work with you? like giving out wrong cancellation dates or something like that could be a bad thing, right?

[00:49:10] **Tim:** right. That could be a bad thing. I, you were here. I did say that I asked it. And I didn't program anything to do this. There's no hooks to do, send emails. I said, could you call me and remind me on the 5th that, that bills due? Certainly Tim, I'd be happy to do that. I'll send you an email on the 5th to let you know that your payment is due.

[00:49:27] **Tim:** If I'm like, Oh, she just lied.

[00:49:30] **Carol:** Uh

[00:49:30] **Carol:** oh.

[00:49:31] **Tim:** There is no way that's happening. So yeah, that's what I'm trying to catch is these, these kind of AI edge cases where they can get you in trouble, unless it's like you can do at the beginning or the end of the call. You know, this is AI, please confirm everything that it tells you with your agent, that this phone number or something.

[00:49:48] **Tim:** So I don't know.

[00:49:49] **Ben:** do you, I mean, you work at such a huge company and you have such a huge customer base. How do you, how would you roll out something like this? Could you say, for example, we're going to try this service, but only with people in Macon, Georgia to start with and to see what

[00:50:05] **Tim:** Oh, like the outgoing calls. Yeah. I would typically just start with a small, with one of our smaller customers first,

[00:50:11] **Ben:** gotcha. So it'd be a,

[00:50:12] **Tim:** that has a small, smaller user base than the others, right. And then monitor it really hard and you'll see what promises the AI made and start tweaking it from there.

[00:50:25] **Carol:** Could you throw it into your customer service line as just one of the agents? So you could still have five people answering the phone and one of them be the automated response.

[00:50:35] **Tim:** Yeah. And it can do a transfer too. You know, it can,

[00:50:37] **Adam:** Oh, nice.

[00:50:39] **Tim:** In fact, that's what I've been working on is trying to get the thing that if you're not a hundred percent sure of the fact you're about to give, that's not in the data dictionary, offer to transfer to customer service, but getting that tweaking, like, then she started like immediately, just like you asked her anything out of the ordinary.

[00:50:58] **Adam:** She's like,let me talk to customer service. You know, it's like, you did have the answer to that. That is in the data dictionary. So there's a lot of tweaking to this. really making me think that like, there's an opportunity here for an even better,Or, or, like, for these situations where it's important to be correct and to, like, not make promises that you can't keep, sort of thing, right? Like, quoting that price wrong. Right.

[00:51:20] **Adam:** There's an opportunity to build a product where a human is on the phone, but there's an AI listening to the conversation. And so when the customer says, How much is, do I owe on my next bill? It just like in front of the representative pops up, okay, here's their bill and it highlights like, this is the amount, right,

[00:51:37] **Tim:** so like an assistant for the, the

[00:51:40] **Carol:** Oh, I like that. I

[00:51:41] **Adam:** Right. So then the person is sitting there in the loop saying, Oh, you wanted an email? Sure. I can do that. And the human can schedule that or, or leave a note or whatever. But the AI is just there, like the person, the customer would never even know that there was an assistant listening in and helping the customer service rep.

[00:52:00] **Adam:** Get through their calls faster, right? Like saving them the time of having to look this up and, and all that stuff.

[00:52:06] **Tim:** Yeah. The devil's advocate on that is, is people are naturally lazy. So if the AI tells them something, it'd be like, well, that must be true. I mean, it told me that. And, and if they get in trouble, they're like, Hey, I was just, the AI you gave me told me that was the date. So yeah, that's what I did.

[00:52:20] **Ben:** I like, the graph, I think Tim, someone posted the graph about how often Delve comes up in, in the subject line of

[00:52:27] **Tim:** I, that was, that was Adam.

[00:52:29] **Ben:** just like skyrocket starting a year or two ago. Yeah. People are lazy.

[00:52:34] **Adam:** that, that was a Paul Graham tweet. We'll have to put it in the show notes now. Thanks, Ben. Paul Graham, who's a VC, put up some tweets. Not too long ago, saying, you know, A, he doesn't particularly love the word DELV, D E L V E, and, but he noticed that it, like, was starting to come in more frequently, in, in, like, letters he would receive, you know, proposals, that sort of thing, and so he, like, found some research and the, yeah, the usage of the word DELV, like, skyrocketed once AI, you know, this chat, ChatGPT and all these other LLMs became available.

[00:53:06] **Ben:** I'm still so on the fence. Not on the fence, but. You know, in a typical laggard fashion, I'm, I'm having trouble committing. I did. I was very happy with a little chat GPT interaction that I had the other day. And so going back to this idea that GitHub can host an NPM module, I mean, that's the wrong term cause it's not NPM, but you know, can host a, a, a JavaScript module and you can.

[00:53:31] **Ben:** Do it in package. json. Apparently in order for that to work, your system has to have git installed. And I didn't realize that that was the case. Like it uses git to pull it down. Maybe that was because I was using a git colon instead of an HTTPS colon or something.

[00:53:45] **Adam:** I believe so, yeah.

[00:53:46] **Ben:** anyway, so I took that error message out of the package.

[00:53:49] **Ben:** json log file, and I pasted in a chat GPT, and I said, I don't understand what's going wrong. And that's, it came right back right away and said, oh, you have to have git installed. And I was

[00:53:57] **Carol:** So

[00:53:57] **Ben:** father,

[00:53:59] **Carol:** Yeah.

[00:54:00] **Ben:** you actually did something right for me. It does seem like my odds of getting a good outcome are when the, the facts are very constrained.

[00:54:12] **Ben:** Like there's no open to interpretation. It's, this is the right answer. This is the wrong answer. That seems to be where it can be best for me personally.

[00:54:20]

## [00:54:20] SuperMaven

[00:54:20] **Adam:** And so actually kind of while we're on the subject of AI stuff, I had another thing that I ran across today that I wanted to bring up and see if you guys have heard of it or, if you're interested in it, so it's like a competitor for CoPilot, it's called SuperMaven, like literally just heard about it today that it's actually, there's a free tier.

[00:54:38] **Adam:** Which is like, basically my understanding is the free tier is like the same thing as the pro tier, except the pro tier allows it to include more context with your requests, right? So like, it'll look at more of your project to, to understand, you know, what it to, to provide context for the, the, requests that it's making. And it's actually cheaper too. Like the, I think the pro thing was 10 a month instead of like 40.

[00:55:04] **Ben:** And does it work in sublime text?

[00:55:07] **Adam:** Does anything work in Sublime Text?

[00:55:10] **Ben:** I actually did try to see if I could get. Copilot working in Sublime Text, but apparently in order to do that, you have to install the Vim plugin for Sublime Text and then use it through Vim.

[00:55:21] **Adam:** Ugh.

[00:55:21] **Ben:** too much work.

[00:55:23] **Adam:** Yeah, no, not for me.

[00:55:25] **Carol:** No.

[00:55:25] **Adam:** No, I, I, so I know it works in VS Code. I, there was another one. I forget here. Let me, okay. Yeah.

[00:55:32] **Carol:** Yeah, it's Jet Brains.

[00:55:33] **Adam:** so there's that. it just, I, and I, you know what, honestly, so I, I did give it a try because the things that I saw about it, that I really liked, it was so much faster than Copilot.

[00:55:43] **Adam:** it's like almost instantly as you type each character, it's updating its suggestions instead of, you know, how like we've kind of trained ourselves to like. Start typing something and then you just kind of pause for three to five seconds while you're like, what's it going to suggest? Maybe I'll like that.

[00:55:57] **Adam:** this is like, it does it instantly while you're typing. And then, the other thing that I really liked about it was that it like, you know how if you start typing a function, you've got your open curly brace and then you decide to accept the copilot suggestion. It like messes up the closing curly braces.

[00:56:12] **Adam:** Like it might not have it or might add an extra one or something like that or parentheses. This one doesn't, in my experience so far, does not do that. Like it figures out, you know, it's got that, it knows which characters are there and it doesn't repeat them, which was cool.

[00:56:27] **Tim:** Is it related to Maven? The, the other program,

[00:56:30] **Adam:** The, you're thinking of like the Java, no, no.

[00:56:33] **Tim:** No, okay.

[00:56:35] **Adam:** Not, not to my knowledge. I wouldn't expect it to be, but.

[00:56:38] **Tim:** I wouldn't think that'd be expansive enough to have a Repository to pull from, unless you're just only doing Java.

[00:56:45] **Ben:** Carol, have you done your AI training at work yet?

[00:56:49] **Carol:** No, but interestingly enough, I don't know why, my computer refuses to let me keep Chrome as my default browser, so it always switches me back to Edge, and I've just given up on it, because I think it's some policy somewhere, however, all my code, like Visual Studio, is set to debug in Chrome, so my core things are okay, but I've learned to just work with Edge, so, I realized that I know, it's really sad.

[00:57:15] **Carol:** It's bad, but I realized about a week ago, whenever I'm searching for technical things, it is now giving me, AI suggestions and my respo and all the responses, so it will pull up co like code things from GitHub, so I'm thinking something happened with security where they're allowing some of it in the network now, so, cause Edge is able to use their stuff in the search engine to, to, to populate, but

[00:57:38] **Adam:** I mean, I imagine it's using the Bing search engine.

[00:57:42] **Carol:** probably.

[00:57:43] **Adam:** I don't, I wonder if that's something they could even disable.

[00:57:46] **Carol:** Oh, they can disable it. Yeah. Yeah. They can disable everything. I can't get to extensions. I can't unpack packages. There are so many things they can disable. Like, you have to be put in special groups in order to do things inside Edge, the browser itself. Like, you have to be in a special group to be able to do, like, developer tools.

[00:58:09] **Carol:** Otherwise, you can't have access to it. So, there's lots they can do. It's the government, Adam. Come on.

[00:58:17] **Tim:** Yeah. They're listening to us right

[00:58:19] **Adam:** there's good parts of the government and not so good parts. And then there's capable parts. And then there's the parts that the general public gets to interface with. The not so capable parts. It's funny how the, all the really capable parts of government and tend to be on the evil side of the, the good and evil meter, right? Like the CIA and, and all that.

[00:58:40] **Carol:** No

[00:58:40] **Adam:** Carol's like, no comment.

[00:58:42] **Carol:** comment. Don't want to lose my clearance.

[00:58:44] **Carol:** Yeah. No comments.

## [00:58:45] Boeing Conspiracy

[00:58:45] **Carol:** Oh, well, talking about weird little things like that. Did you guys see the Boeing guys? The two whistleblowers died suspiciously. like, yeah, the two people who were like the big whistleblowers for

[00:58:59] **Adam:** Yeah, so there was one that like, mysterious, like, he was sort of like, for lack of a better word, well known for being like, super health conscious and really healthy, and then he just sort of mysteriously gets like, super sick. And dies from it. And then the other one, you know, supposedly committed suicide.

[00:59:15] **Carol:** Yeah. Yeah. The one was like some very strong infection took him out quickly.

[00:59:22] **Adam:** Yeah. MRSA or something.

[00:59:24] **Carol:** God. Yes.

[00:59:25] **Ben:** sounds very shady.

[00:59:27] **Carol:** Yeah. It's so creepy. I'm like, no, no, no, no, no. All cause a door came off a plane. Ugh.

[00:59:33] **Adam:** Everything to maximize profit in this country. I hate it.

## [00:59:36] Patreon

[00:59:36] **Adam:** Anyway, this episode of Working Code is brought to you by setting your visibility timeout to infinity to maximize queue throughput

[00:59:41] **Carol:** huh. Yes, yes, yes. Woo hoo.

[00:59:44] **Adam:** listeners like you. If you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon. Our patrons cover our recording, editing, and transcription costs, and we couldn't do this every week without them.

[00:59:57] **Adam:** Special thanks to our top patrons, Monte and Giancarlo. You guys rock.

## [01:00:00] Thanks For Listening!

[01:00:00] **Adam:** And, you know, I know I didn't bring it up last week because I forgot, because that's what I do and who I am.double triumph this week because I can officially say I have sent out the order for the stickers. It did happen. It did happen as I said it would.

[01:00:17] **Adam:** So, you know, it's May. I admit that. You know, time, time is a strange thing. Sometimes it passes. faster than we wanted to, but I did it. Anyway, moving on, we're going to go record our after show.looks like on the list here, somebody thinks their mouse is hacking them. I don't know who that is, but we're gonna find out in the after show.

[01:00:38] **Adam:** And I, you know, occasionally we talk about books. I have been reading a new series of books I want to talk about briefly. So we'll see. And Carol is. Typing house hacked, question mark, question mark. So, we will get into that. If you want to know more about the after show, if you would like to hear conversations like those, you can go to patreon.com/workingcodepod. Support us, throw a few dollar bills our way, keep the lights on around here. We would greatly appreciate it.

[01:01:05] **Adam:** anyway, you can, join our discord, go to workingcode.dev/discord, and hang out with us and our listeners. It's a great place to be great community. Love to have you. that's gonna do it for us this week. We'll catch you next week. And until then,

[01:01:18] **Tim:** Don't let this message get sent to dead letters. Your heart matters.
