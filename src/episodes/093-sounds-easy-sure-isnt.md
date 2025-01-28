---
title: "093: Sounds Easy! Sure Isn't"
description: "Nothing is ever as simple as it seems, especially in the world of web development."
date: 2022-09-21
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/093-sounds-easy-sure-isnt/id1544142288?i=1000580175059"></iframe>

Sponsors

- [Audible](https://workingcode.dev/audible) - get a free audiobook from Audible with no strings attached at https://workingcode.dev/audible

On Adam's team, whenever anyone uses the phrase _"just"_ to describe a level-of-effort, everyone jumps in and echoes "just" using air-quotes. Because, as many of us have learned over the years, nothing is ever as simple as it seems, especially in the world of web development. On this week's show, we talk about some of those tasks that end up being way more complicated than they _should have been_. Topics include: vertically aligning content, using JavaScript in 2022, logging data with sufficient context, tracking who made changes to a database, and storing notification flags for users that _may never come back to your application_.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/093-sounds-easy-sure-isnt.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** It's like min height somehow flips it into some special mode of rendering or something. I, I don't know. It's really, some of it just makes no sense. It's like just some esoteric browser logic that. You just have to do cuz that's how it works.

[00:00:13] **Adam:** Yep.

[00:00:13] **Tim:** See sounds easy. Sure. Wasn't.

## [00:00:17] Intro

[00:00:17] **Adam:** Here we go. It is show number 93. and on today's show, we're gonna talk about things that sound like they should be easy, but actually aren't, like, you know, centering stuff vertically but, as usual, we'll start with our triumphs and fails. guess it's my turn to go first.

## [00:00:52] Adam's Fail

[00:00:52] **Adam:** So I'm gonna go with a continued fail from last week, and I'm just gonna say, brain is still mu. I don't have a whole lot of excuses because, I didn't actually do a ton of policy reading and writing since last week. I guess we, I would say we've had like one incident in the last week and then a bunch of like other, just sort of urgent and important work where it's like, okay, well I'll put aside my thing and work on that.

[00:01:14] **Adam:** but I, I did do some policy stuff this afternoon and it's like instantly return to, to mush

[00:01:22] **Tim:** This is for your sock too. Right?

[00:01:23] **Adam:** absolutely. Yeah. Re yeah, reading and writing policies like today, I did, our information security policy, which is separate from our incident response policy and like just a bunch of, you know, these things that sound like they should all be the same thing.

[00:01:38] **Adam:** And it, it sounds so easy to have a couple of policies, but oh my God, it's not.

[00:01:45] **Tim:** Are you finding anything wrong with them?

[00:01:48] **Adam:** With the policies or like with our business practices? No. mostly what it is is these policies, the templates that we're working from are meant to be sort of universal. Like they could apply to any company, but, you know, we don't have a chief information security officer and, you know, like there's like five or six positions that I'm just going, I'm think as I'm reading this, I'm like, okay, well we have an acting CISO, you know, that'll be somebody on the team.

[00:02:16] **Adam:** Right. Like we do all of these things, but it's, we don't have a formalized process around disaster recovery yet. And we don't have, uh, you know, formalized incident response plan. We just kind of like, okay, something's going on? So let's jump on video chat and figure it out. you know, we're a team of, technically still five people.

[00:02:34] **Adam:** We have our sixth starting in another week or two. so. Yeah, or just it's the, the language in these policies is just very enterprisey and it's hard to decide whether I need to like dumb down the language to fit our current business size, or if we just kind of accept it as is and go, yeah. You know, our CTO is also, our CSO is also this and is also that they're all the same person.

[00:02:57] **Adam:** and I don't know. And like, you know, we're still so small, we don't have a board of directors and there's like certain things, that it, like references, you know, reporting certain things to your board of directors. And I'm like, no, I'll just cut that sentence.

[00:03:09] **Carol:** Yeah,

[00:03:10] **Adam:** Yeah.

[00:03:10] **Carol:** but you gotta report to someone. So you really can't cut the

[00:03:14] **Adam:** I report to the mirror.

[00:03:15] **Carol:** Okay.

[00:03:16] **Adam:** No, no. I mean, it's, it's like, yeah, I mean, you're not wrong. Right? The, sentence that I was thinking about was like, the, I guess it's the CISO, the chief information security officer is supposed to report some information about how. like what the plan is and how well we're doing at, adhering to our security policies, and what the remediation plans would be if we found something that was out of, compliance.

[00:03:38] **Adam:** And so, you know, we just kind of absorbed that into

[00:03:43] **Carol:** Makes sense.

[00:03:44] **Adam:** like, yeah. I mean, the, I think the point of that sentence is about transparency, right? The plan isn't just we'll deal with it. There has to be an actual plan.

[00:03:52] **Carol:** Yeah. You need to communicate what's going on. Yeah.

[00:03:54] **Adam:** right. And, and so,

[00:03:57] **Tim:** every company, what the actual policy is, and actually what you do is there's always some divergence there.

[00:04:03] **Carol:** Mm-hmm

[00:04:04] **Adam:** So we just have to find language. That's gonna make sense for our business that, you know, we can, what, what's the word? plausible deniability, right. You

[00:04:13] **Ben:** There you go.

[00:04:13] **Adam:** we could theoretically make all of this work to the letter, even though we probably won't.

[00:04:20] **Adam:** So uh, unless you're the business, unless you're like the, you know, our auditor listening and then in which case we're going to

[00:04:28] **Ben:** I was on a call the other day at work. And I don't even remember what the context was, but someone started saying something that had like a sensitive nature to it. And I was like, I was like, don't what you're talking about. I don't know. I wanna be able to deny that I heard of this.

[00:04:46] **Adam:** yep.

[00:04:47] **Carol:** Steve does this thing where, when he talks about anything at work, no, no matter how silly it is, he takes his phone and turns it upside down and takes my phone and like sticks it in his pocket or something. And then whispers in my ear. Like it's some big, giant secret, but in reality, it's nothing at all.

[00:05:01] **Carol:** It's like, so, and so wasn't at work today and I'm like, you had to hide all of our phones to say that. And he's like, you never know who's listening.

[00:05:10] **Adam:** It he's right. unfortunately.

[00:05:14] **Adam:** And if anybody would know it would be the military. anyway, that's, enough gibber Jabber outta me. How about you, Ben?

## [00:05:20] Ben's Triumph

[00:05:20] **Ben:** I'm gonna go with a triumph. And that is that I wrote a data migration script today at work that has to delete about 22 million records from the database, which deleting data from the database is just a terrifying, terrifying thing, especially when it's not based on existing application code. It's something that, that you have to hand write.

[00:05:42] **Ben:** but I was looking at our application logic and there's this part of the application where a record gets generated. And then right after a very slightly different record gets generated. And there's a note that says, oh, by the way, we should probably not generate this in most cases.

[00:05:56] **Ben:** And I did a good blame on that. And that's, that was added seven years ago.

[00:06:01] **Carol:** Nice.

[00:06:02] **Ben:** I was like, oh, that doesn't seem right. So I looked at the data. And I ran a query to see roughly how many there were of that second type that, that didn't need to be there in most cases. And it was about 50% of the records in that table, which has about 50 million records in it.

[00:06:17] **Ben:** And, I just, I, I, I couldn't abide. I couldn't let it be there. So I, I, I wrote a migration script that essentially walks over the table and is looking for, cause there's certain conditions. I can't just like blanket delete 20 million records at a time. First of all, a database probably lock up in production.

[00:06:34] **Ben:** We don't want that. Yeah. So I'm, I, I wrote a migration script that, that gets stored like the place. It has a, a record in the database where it stores offset and it kind of loops over a thousand records at a time looking for specific conditions and then deletes them and it, and it's terrifying, but the triumph is that I did it and I pulled the trigger.

[00:06:52] **Ben:** And so far nothing's exploded. And so that's a bit of a relief. Yeah, yeah, exactly. No one's complained yet. I'm banking on the fact that, you know, there's always a database backup somewhere should something go afoul, but, I'll also throw in kind of a sub triumph, which is that I almost sort of wrote something that looked like a test, which is, yeah.

[00:07:11] **Ben:** I, uh, settle down, settle down. So I,

[00:07:14] **Tim:** baby steps.

[00:07:15] **Ben:** I, I had to delete this special type of record inside of this table. So I had a test file. I mean, I say test very liberal, liberal liberally basically I had a, a dot file that inserted a number of good records, quote, good records, a number of quote, unquote, bad records.

[00:07:33] **Ben:** And then I ran that and then I did the thing in the UI that, that like should have demonstrated whether or not that code was there and only the good records still exist. So, but then, you know, of course, once I was done, I deleted all of that. Mumo jumbo. You don't need to commit stuff like that, but, I felt good.

[00:07:50] **Ben:** I felt good. It was like, it was terrifying up until the moment I hit run in production then I just sort of felt better about it. So I feel good

[00:07:58] **Tim:** But is it moving the data to somewhere else before it deletes it? No, it's just deleting it.

[00:08:03] **Ben:** just deleting it.

[00:08:04] **Carol:** It's gone.

[00:08:05] **Adam:** Well, you got

[00:08:06] **Adam:** all your old backup.

[00:08:07] **Ben:** Yeah. That, that, so it's a very, edge Casey kind of a thing. And, we actually track how often this particular type of record gets accessed.

[00:08:16] **Ben:** Like when you render the view on the, on, in the app, we then store another record that says, Hey, this person viewed this thing. it's a very specific type of thing. It's not like we do that for everything. And so I spot checked the, the database and for like 2 million records of that type. Only something like 300 of them had ever been viewed.

[00:08:37] **Ben:** So it's, it's like literally we're, we're generating a bunch of data that that's not even accessible in the application. So it just, and we we're actually ending up, filtering that data out in a number of places. So once I actually clean this data up, I can go back and remove all the places where it's getting filtered out unnecessarily.

[00:08:55] **Ben:** So it's just gonna lead to faster access on that table. And just more peace of mind, I think on my end.

[00:09:02] **Tim:** Hm.

[00:09:03] **Ben:** So yeah. Triumph, Tim, what about you?

## [00:09:05] Tim's Triumph

[00:09:05] **Tim:** I also gotta triumph, So I simplified an existing feature that, and it's greatly reducing like resource usage. So of course, you know, in the financial world, we, we take a payment and then we're typically posting information about that, the success of that payment to, you know, some sort of system of record or accounting system or something.

[00:09:25] **Tim:** And the initial customer that I built this for in order to find out it was a whole bunch of steps, a bunch of lookups, it got really resource intensive to try to figure out, if that payment was applied. So I have an audit routine that, that does, that goes out and checks. And if it doesn't, you know, it either will automatically, post the payment or, contact a human, you know, put a note, note somewhere for a human being to take a look at it. And I don't know why I just sort had a brain fart. I was for some newer systems that I've been talking to, that it was so resource intensive, that it was like bogging their system down. And I kept trying to hack it and just, you know, take incremental approaches to fixing it.

[00:10:08] **Tim:** And then some reason today, like middle of the day, I, I was kind of done with most of my stuff and I was like, oh, what I gonna work on? And I goes, started thinking about that. I'm like, oh, you idiot these, the newer systems. They actually have. We have a, a token that we give to represent the payment this new one.

[00:10:23] **Tim:** They have the token and they store it. So all I gotta do is just go, I have a list of all my tokens for the customer. All I gotta do is. I created a, an API endpoint that says, give me the token and I'll go see if it's in this table. And so I went from, you know, taking two to three seconds per lookup to like, I can do, I did like 3000 in, you know, less than one second.

[00:10:47] **Tim:** so, and it's, it's, so it's much more resource intensive and doesn't, you know, block the, the system of record. so I'm like, and I'm just kicking myself. I'm like, why didn't I do this earlier? This is so much simpler. I've got the data I need. I just need to know. Did you take my token? Did you put it in your system if it's there, the payment's there so I can move on.

[00:11:04] **Tim:** So it was good to do that. And I only took probably an hour and a half today,

[00:11:09] **Tim:** so to get that, working tested, and then move to production.

[00:11:13] **Carol:** good job.

[00:11:14] **Tim:** yeah. How about you Carol?

## [00:11:16] Carol's Triumph

[00:11:16] **Carol:** I have neither. It's just it's okay. Things are going along. Things are working. I have nothing amazing to report. I have nothing terrible to throw in there either. Like everything's just going par. I don't know. Everything's okay. I guess that's a win in itself. It's just okay.

[00:11:34] **Adam:** Sure, I guess instead of a gold star, you'll get a green circle sticker.

[00:11:38] **Tim:** there you

[00:11:39] **Carol:** It's it's going good for go, I guess, green for go. Yeah. So that's me.

[00:11:47] **Ben:** All right. Hey, nothing to

[00:11:48] **Tim:** ain't no, ain't no shame in that,

[00:11:49] **Carol:** yeah.

## [00:11:50] Vertical Align

[00:11:50] **Adam:** All right. Well then, let's talk about things that are supposed to be easy. That sound like they should be easy, but in actuality just are not.

[00:11:58] **Tim:** but it sounds so easy.

[00:12:00] **Carol:** Yeah.

[00:12:01] **Adam:** I, I was kind of joking when I was talking about vertically centering stuff. you know, that's kind of the, the go-to joke, right. For, it sounds easy, but it's not,

[00:12:09]

[00:12:09] **Carol:**

[00:12:09] **Adam:** you know, there there's, I guess a line middle is, table. Is that a vertical centering? I guess it is. but that only works in tables,

[00:12:17] **Ben:** yeah. TDS have a vertical line.

[00:12:19] **Adam:** Yeah.but then, yeah, it's just been this thing. And I, I, I say this because I've had this trick that I've been using for the last several years or whatever, and, and has been working great for me, which is, so say you wanna align vertically align a div inside of its container.

[00:12:34] **Adam:** So you do, what is it position relative top, 50%. And then you do a transform translate Y minus 50% and that effectively vertically center stuff. And that, so that's just been how I've done things forever.

[00:12:48] **Tim:** So easily readable.

[00:12:50] **Adam:** Yeah.

[00:12:51] **Ben:** I I was gonna say, so there is, there is like one really small wall quirk that the last time I checked still exists, which is that if the content height of the element is an odd number of pixels,

[00:13:03] **Adam:** as an even odd.

[00:13:05] **Ben:** Yeah. Yeah. So let's say it's like 501 pixels high, the negative 50% actually like Mo shifts it to the half pixel and, and then certain things inside of that content become blurry.

[00:13:19] **Adam:** Oh, lovely.

[00:13:22] **Adam:** so that's not even the bug that I was gonna bring up. So, but I've been using this trick for years and years now. and I got a ticket today that something that I designed that's responsive, wasn't looking quite right. And, and the bug wasn't this, but I, while I was trying to figure out that bug, I was like, cool, let me open this up in every browser and take a look at it.

[00:13:39] **Adam:** And it was looking great. The vertical centering part at least was looking great everywhere except fricking safari. Uh, and somehow for some reason, the, the text was like basically bottom aligned, in, in safari, on this thing.

[00:13:55] **Carol:** Weird.

[00:13:56] **Adam:** Yeah. And at what it came down to, So I was using that trick to vertically align a diviv within a block uh, anchor tag, like a button, you know, that's a, a HF, whatever, but it's block styled and we're using it as a button.

[00:14:13] **Adam:** Um, because in some cases like, it's think of like a row of buttons. In some cases, one of those buttons might have multiple lines of text. And so they won't all automatically aligned. And that, that row of buttons is in a display grid. So the buttons themselves will all grow to fit the height of that row of buttons.

[00:14:31] **Adam:** So they'll all be identical height, but then the text of one will be centered because it's got multiple rows of text and it just it's setting the height for all of them. And then the rest are all not. And so I used my trick to vertically align the things and it looked great and I thought it was great for a week or two.

[00:14:47] **Adam:** And then I got this bug report and what I ended up having to do. And I don't think you're supposed to have to do this, but to fix it in safari, as I added a height equals a hundred percent to those grid items. Yeah. Which I think is like implied. And it must just be some weird safari bug, but that fixed it.

[00:15:05] **Adam:** I was like of all the things and there's, you know, there's other ways to do it too. Like we had somebody in Discord suggest, a different, it was MGO, a MGO give you credit, using a flex box, a similar flex box approach of, aligning things.

[00:15:18] **Carol:** Oh, there's a cool Flexbox demo. I love to do it's like the Frogger one. I don't know if you guys have done it or not, or basically you play Frogger. Oh, it's so much fun. I hate, I hate design. I hate CSS. I hate styling anything. I am not a pixel pusher. Everything you just rambled off at is something I would've expected to find when I'm searching, how do you vertically align something I'd be like in stack overflow, going someone, please tell me how to make this work. I can't make it work. I, I don't do those things very well.

[00:15:48] **Tim:** I don't do 'em often enough. I just

[00:15:50] **Carol:** and either

[00:15:50] **Tim:** the hack, the page until something moves, like, okay. It moved all I'm in the right spot. Let's play.

[00:15:56] **Carol:** the funniest part is I will have, like my developer console open and I'll like inspect the element and I'm over like changing pixels to see what it does, because I actually don't know what a lot of the tags do.

[00:16:09] **Carol:** So I'm like, what happens if this one is five more? Which way did it go? Because I'm like, this should go left. No, actually five more moved it. Right. And I'm like, I'm so confused, but, okay. So then I start plugging that back into my code. Refreshing. Let's just try it and see what it does.

[00:16:24] **Adam:** So the site you were talking about with the Frogger thing is Flexbox frog.com. It's basically a Flexbox tutorial that you learned by playing Frogger. Yeah.

[00:16:32] **Carol:** Yeah. It's, it's fun. And it's actually very educational.

[00:16:35] **Ben:** flex box has definitely become my go-to for a lot of things. I, well, so here's the thing is for the longest time we had to support I E 11. I 11 actually has Flexbox support with some vendor specific prefixes. I think we use at work, we use something called post CSS, which is basically a post compilation step for listeners here.

[00:17:00] **Ben:** So it'll do things like, you'll compile your less CSS into regular CSS and then post CSS will apply vendor prefixes to the, to the output. and you can get I E 11 to basically support flex box, but they, I don't think they have something like that for grid. So what I think a lot of people reach for grid.

[00:17:21] **Ben:** I have historically reached for flex box because grid was not available.

[00:17:26] **Adam:** Yeah. Yeah. Flex box came first and I tried really hard to learn it and I kind of it's like, I could make it work, but I, for every single time that I have to use it, I have to go dive back into the tutorials and oh, okay. Yeah. That's how you do that thing. Or that's what that property is called every single time.

[00:17:41] **Adam:** And it's for like everything that I wanna do every little feature, whereas grid just feels more natural to me. it's easier to remember the parts. And so I, that's what I tend to reach for if I can.

[00:17:50] **Ben:** Yeah, I gotta get into grid because it seems like it's really powerful. And, one of the things that's coming out soon is the sub, is it called subgrid where it's like different grids can then sort of share alignments. I don't quite know what the definition is, but.

[00:18:06] **Adam:** I, I forget the exact thing, but if, I'm gonna try and, and maybe we'll have to error correction, but, I believe it is so that like, you can have a grid of items and then all of the items can then be like display grid and have like grids within grids. but the thing is that they all adhere to each other.

[00:18:23] **Adam:** Right. They, they share the same vertical height of the rose and, and

[00:18:28] **Carol:** That's cool. It sounds cool. I hope you're right.

[00:18:32] **Adam:** I hope. Yeah,

[00:18:33] **Carol:** Yeah.

[00:18:33] **Adam:** me too.

[00:18:36] **Ben:** one issue that I've run into with vertically centering is, when you open a modal window in our application, you get a backdrop, you know? So, so like you have a grayish backdrop, that's like 90% opacity. So most of the application behind it is, not available. And then you have your mobile window above the backdrop and the motor window is vertically centered within the window.

[00:18:58] **Ben:** which is fine when the modal window is shorter than the browser window, but then when the browser, when, when you have a lot of content in your modal window and it has to go all the way to the top, aesthetically, I don't want the top of the modal window to butt against the actual top of the browser.

[00:19:14] **Ben:** So I want to build in like a 50 pixel margin on the top and the bottom. but with flex box and I don't, there's like weird things that you gotta do. So like in flex box, if you try to center that model within the window, and then the content of the model gets larger than the browser, the scroll bars don't work, and you have to do this weird thing where it's, it's like you don't center align it, but you, said like all the margins are auto and then one of them has like a min height.

[00:19:41] **Ben:** It's like min height somehow flips it into some special mode of rendering or something. I, I don't know. It's really, some of it just makes no sense. It's like just some esoteric browser logic that. You just have to do cuz that's how it works.

[00:19:54] **Adam:** Yep.

[00:19:55] **Tim:** See sounds easy. Sure. Wasn't.

## [00:19:59] Move This Left 50px

[00:19:59] **Carol:** whenever we're working on projects, we work with our design team and they send us over these like Figma designs of what they want the site to look like. And my very first project, I was like, yes, someone else is going to be designing this for me. This is gonna be amazing. And then I find out like three, No, not joking. Like three meetings into it. And three meetings into this. I found out. They don't design it. They just decide what it looks like. And I have to make it look that way. And I was like, do you guys know how much I don't like doing anything in the front? Like, this is not my thing. Right. So ultimately he sends me back a whip and is like, Hey, this really needs to move left.

[00:20:39] **Carol:** Like just a tad, like, and he zooms in. He's like, you can see that it, it's not exactly aligned with where our button is here. And I. This button literally has nothing around it. It's just in a diviv that has inherited everything else. Right? Like, I've done nothing to this other than just laid it out in our normal flow.

[00:20:57] **Carol:** So, because I got so frustrated with it cuz in the meeting I'm like, oh yeah, sure. That's fine. That's easy. No problem. Right. I go pull up the code, do everything I can to make it work. Didn't make it work. So ultimately I put like a negative 45 pixel on it and shipped it out and was like, it's there where you want it, but I'll figure out later why, why it won't move any like why it's not where it should be.

[00:21:21] **Carol:** So then I had to go back like two weeks later and fix it, but I'm like, I just, I don't get it. I don't do these things. So it sounds simple enough to just move something slightly left and I'm like, it doesn't move.

[00:21:34] **Tim:** What's worse is when you have, you know, it's the customer saying, Hey, could you just move this over? And it's like two days later, why haven't you moved? I mean, seriously, can't be that hard. Like, dude, you have no clue.

[00:21:43] **Carol:** Just get over it. Enjoy. Enjoy you have the button and it works. Okay. Yeah. Don't complain about his placement.

[00:21:50] **Tim:** Looks good on my machine.

[00:21:51] **Adam:** Yeah, just don't change your font size or

[00:21:54] **Carol:** yeah.

[00:21:54] **Adam:** zoom in or anything.

[00:21:57] **Ben:** I remember one time, years, and years and years ago at, basically my first job out of college, I was working on a website for this law firm and, it was literally new year's Eve and I'm sitting in the office with the clients right behind. And we're co-designing, their about page. And it was that same kind of thing where it's, they're like, oh no, can you move two pixels to the left?

[00:22:20] **Ben:** And like this partners face two pixels to the right. And they're like, oh no, that doesn't look right. Can we go try, go back the other direction? You're like, well, what if we put a border around it? And I'm like, yo, it's six. O'clock on new year's Eve. Why do you wanna be here doing this? Do.

[00:22:41] **Tim:** What's wrong with your marriage.

## [00:22:44] Builds, Bundling and JQuery

[00:22:44] **Adam:** well, you know what should be easy, but is just ridiculously frustrating. especially like if you're coming at it new, if, if you've never done it before using JavaScript in 2022, like on a website, right. You got like transpilers and bundling and you've got to choose between, ES modules, imports and, and common JS.

[00:23:09] **Adam:** And. Man. I like occasionally I entertain the idea of trying to teach my kids how to make websites. And like, I, I try, you know, I start with vanilla JS and all this stuff. Like I haven't, I haven't even brought them into like react or anything. It's just like, just here, let's make TT toe. And the it's just so frustrating.

[00:23:32] **Tim:** I mean, I don't do bundling and things like that. I, I don't, I mean, I just used old schools, like kind of, you know, import the library, you know, get it from a CDN or something. And then if you need to add some, put some custom Java script in there, just, you know, just put it on the page.

[00:23:48] **Tim:** I haven't really looked into I'm sure people are gonna tell me what is the advantage of, of, you know, doing these trans compilers and bundling and things like that.

[00:23:57] **Carol:** So, how do you update your.

[00:24:00] **Tim:** Hmm.

[00:24:00] **Carol:** update? 'em like when a new version comes out or, like a new release comes out for the library, how do you

[00:24:05] **Tim:** whatever the latest CDN number is, just update it.

[00:24:08] **Adam:** Tim's still

[00:24:08] **Carol:** You just manually go in and like, have to go like type it in, into all the files. Okay.

[00:24:13] **Adam:** You've got one shared layout file that you imported in, right?

[00:24:16] **Tim:** yeah, we don't, we don't update it till breaks.

[00:24:19] **Adam:** I'm sure that's PCI compliant.

[00:24:21] **Ben:** Quick side quest here on J query. Super interesting. so I was listening to, an episode, I think it was of code pen radio. And, they did this analysis of like the last, I don't know, however many years, think it was just the last year of pens that were created.

[00:24:35] **Ben:** So code pens for people who don't know what that is, it's basically like an online, playground where you can build JavaScript, HTML, and CSS kind of demos, and CodePen hosts them and they do all kinds of fancy stuff around bundling your JavaScript together, but making

[00:24:51] **Ben:** it

[00:24:51] **Ben:** so it's

[00:24:51] **Adam:** like a social network for, Web dev

[00:24:53] **Ben:** yeah.

[00:24:54] **Ben:** Yeah. Yeah. Good. That's great explanation. So they, when you create a pen, apparently you can choose what type of technologies get included. Like, do I wanna do a react demo or is it gonna use SVG? What kind of CSS? That kind of stuff. And they, analyze the most popular technologies that get concluded in their pens.

[00:25:12] **Ben:** And they say even to today, J query is the most popular technology that gets included in their pens. And that's people proactively saying, I wanna in pull this in. It's not like something that gets pulled in by default. And it was so fascinating cuz they were comparing it to say like the state of JavaScript, surveys that I think stack overflow does.

[00:25:31] **Ben:** they're saying like people talk about what they're really excited about and like what they wanna use in their side projects. but when it comes down to it, Jay is still super, super useful and powerful and it what a lot of people end up pulling in. It's just not the thing that they

[00:25:45] **Carol:** Yep.

[00:25:45] **Ben:** about.

[00:25:46] **Carol:** Yeah,

[00:25:47] **Adam:** jQuery is the it's like, it's like Batman's tool belt. If you're still working on the legacy app, right? Like you can't, you can't just start over and build everything from, with react and, and SELT and all these awesome things. I mean, you can, but it is much easier and thus more efficient and profitable to just do it with my favorite word is just right.

[00:26:07] **Adam:** Like I've got, I've kind of unintentionally, you know, without any effort trained my whole team to anytime anybody says just, we then repeat ourselves and we go just with air quotes, right. Just add an index, just, because it's such a, it's a trigger word, right? It's like when you say just, you are implying that it's an easy thing for somebody to do, and maybe it is easy for you, but it's not necessarily easy for everybody.

[00:26:30] **Ben:** Mm-hmm

[00:26:31] **Carol:** Anybody can do it.

[00:26:32] **Carol:** Like, just because it's easy for you doesn't mean it's easy for someone else. I mean, what sounds easy for you?

[00:26:38] **Carol:** Isn't easy for me.

[00:26:39] **Tim:** Yeah. So I never got an answer to my question. What, what does all that stuff buy you? Does that get you rather than just

[00:26:44] **Tim:** doing Java?

[00:26:45] **Adam:** A better developer experience once you get the build pipeline put together, like, so all these frameworks, the react, the views felt angular. They kind of all stem from. There's gonna be some, some, deviation from this, but in general rule of thumb, they all stem from the idea of declarative, state like view state, where you define the data and then you render the view based on what the data is.

[00:27:13] **Adam:** And If you wanna make a change to the view, you do that by changing the data on the page. And that causes the page to Reinder, which is a much easier to reason about, and, debug way to build complex user interfaces. And now I will get down off of my marketing soapbox.

[00:27:31] **Ben:** Well in bundling enables a bunch of other things that you don't necessarily think about. So like you can use features of a language that are somewhat advanced and then they get compiled away. So like fat Aero, syntax for functions, you know, it's supported everywhere now, but it wasn't supported everywhere.

[00:27:51] **Ben:** So you could write it like that. And then your compiler and your bundler would convert those to old school functions and, and this bindings and things like, async weight, I think still gets compiled down into generators. And, and then you can all of your applications in smaller files that they're easier to reason about, like Adam's talking about.

[00:28:12] **Ben:** And then the bundler puts those all into one giant file, or, or puts it into a giant file, but then splits that file up and, and does a code splitting, like based on the routes that you are on your application. So for example, you might eagerly load. The very early access parts of your application, but then lazy load, a whole administrative bundle and like, no human can do that reasonably on their own.

[00:28:36] **Ben:** So they rely on all these bundler technologies to figure out how to split up the code and how to extract parts of it and how to inject other parts of it into, into other things. It, I mean, it's all magic to me. I don't, I don't really

[00:28:48] **Adam:** Right. Yeah. Like, I guess another way of looking at it, just like, if you have, a million lines of JavaScript for your application, you don't want that to be manually split across 10 different files. Right. And even if you did that, you're still looking at 10 different, a hundred thousand line JavaScript files, which would suck.

[00:29:07] **Adam:** and so bundling allows you to organize that code well, right.

[00:29:13] **Ben:** I'm, I'm so used to the idea of bundling now that, when people talk about living in a world where bundling doesn't have to take place. So, so there was H D P one, which is what we've all been living on for the last 30 years. And then HTD P two came along. And the idea I think with that is that essentially you reuse connections.

[00:29:33] **Ben:** So it becomes theoretically much cheaper to send a lot of separate files. Because they don't have to do all the DNS hand shaking and HTP hand shaking and stuff again, I'm, it's not really my here.

[00:29:47] **Adam:** Close.

[00:29:47] **Ben:** And now that like, apparently didn't prove itself as well as people thought it would. So people continued to bundle.

[00:29:56] **Ben:** And now I think there's HTP three and, and browsers all support ES modules. I'm saying some words here that I don't fully understand. So forgive me. So, so I'll listen to podcasts. People are like, oh yeah, we're gonna be pretty soon living in a world where you just don't have to bundle. Like you can just build a site that has 200 separate files and it's all gonna be streamed through ES modules over HTB three.

[00:30:18] **Ben:** And I'm just, I'm like, I don't know. I feel like we tried that before. It doesn't feel like a, until I see it, it doesn't seem feasible.

[00:30:28] **Adam:** So, yeah, my, I don't know about everybody else. My introduction to bundling was a tool called browser AFI, which would. Allow you to use common JS require statements. So like no JS, if you're familiar with using require, you know, some other file or some node module, and it would pull in that code and it would, you could treat it like it was defined in the same file.

[00:30:47] **Adam:** and then browser file would allow you to that and many other things, but it would kind of combine all of that into one bundle based on a single entry point. and until, embarrassingly recent, that was how, our JavaScript bundles were built. And, yeah, I mean, like it, it worked and we had bigger, more important fish to fry.

[00:31:06] **Adam:** So we, we were living on browser fry and J until, probably at least 2020, if not later,

[00:31:13] **Ben:** Yo.

[00:31:13] **Tim:** What, what are you using now?

[00:31:15] **Adam:** so we switched out browser five for a tool called ES build, which I've talked to before about on the podcast. It's, it's built in. think it's built in go there's, there's sort of two that are competing there's ES build and there's WC.

[00:31:27] **Adam:** I believe WC is written in rust and ES build is written in go, and they are just much faster languages, right? So, tools like Babbel and Webpac and other prior bundlers were written in JavaScript because they were written by JavaScript developers who just needed to get something done. So they used what they knew.

[00:31:46] **Adam:** And this is actually, this is something that, SWX when we had 'em on the show was talking about, you know, how people are motivated enough now to learn other languages, to get better performance in the third age of JavaScript. and we're using ES build. there were a few features of Browserify Browserify had a good plugin for handlebars templates, which we were using, for doing some template stuff. and it turned out like when we went to switch to ES build that there was no way to do the same thing.

[00:32:14] **Adam:** And so I looked at what we were using templates for and there was like maybe 10 or 12 places we were doing this. And the templates were so simple. I was like, it would be so easy for me to just write a function that can strings together to do the same thing as the template. I'm just gonna do that.

[00:32:30] **Adam:** And so I did, and that made it possible for us to switch CS, build, and life has been so much better ever since.

[00:32:36] **Adam:** And we, I don't, I don't think we have a million lines of JavaScript, but we have quite a lot. And, and it's kind of built on, you know, legacy app style.

[00:32:43] **Ben:** bundlers are very magical and magical to the point where it's like, if, if you're swimming with the stream, they're amazing. And then it seems like the second you need to swim upstream a little bit. It's like, you really have to know what you're doing or it's just not possible. Sometimes I remember, I started playing around with a bundler called parcel parcel JS, which is really cool because the way it works is you, you sort of just build.

[00:33:09] **Ben:** The site, the way you'd wanna do it. If you didn't have a bundler, so you have your index file and your index file calls a main file. And then the main file imports, a bunch of other files, that kind of stuff. And then you just point parcel at the index file, like their index HTML and it parses it and it figures out all the references and then it pulls those things and bundles them together.

[00:33:28] **Ben:** And I'm like, oh, this is so amazing. And it's so fast, but it works with an HTML file. So I'm thinking to myself, can I use parcel to build a library that gets pulled into a CFML a ColdFusion template? And, I was posting on the issues and people are just like, no, that's just not how it works. You're like, it has, you have to point it index file, or you have to point it in a JavaScript file, but then you'd have to pull it in through like a whole different step where you, you create a hash file name and then you have to know where to pull that into your ColdFusion.

[00:33:55] **Ben:** It's like, you know, you just start swimming upstream and, and the, the training wheels come off really.

[00:34:00] **Tim:** yeah. It's a JavaScript. Sounds easy.

[00:34:04]

## [00:34:04] Logging

[00:34:04] **Ben:** So what.

[00:34:06] **Tim:** logging, logging sounds easy. Right? You just, you know, we gotta

[00:34:11] **Carol:** Just log it,

[00:34:12] **Adam:** Just

[00:34:12] **Adam:** use log

[00:34:12] **Adam:** for J

[00:34:14] **Tim:** yeah. Just CF log or

[00:34:15] **Carol:** now here. That's super safe.

[00:34:17] **Carol:** Don't use that if you're listening and you actually listen to Adam's recommendations, don't choose it.

[00:34:22] **Adam:** just

[00:34:23] **Adam:** just

[00:34:23] **Adam:** use the latest version. yeah.

[00:34:25] **Carol:** Make, make sure you've updated it.

[00:34:26] **Carol:** Yeah.

[00:34:28] **Tim:** That sounds easy. Right. You just, you know, automatically creates log file for you. You just dump some text to it or maybe some, you know, some JS on, but, yeah. But you know, you're running. You have multiple services on multiple instances and now they're all local.

[00:34:42] **Tim:** And so now you gotta get, now you gotta, you know, have a logging service that aggregates that across all your, all your services. So yeah, I just, I just find, and then if, if you don't do that, then it's like, well, now you gotta go physically log into the machine. go look at the file on the machine. it's easy to do that, that one little log statement, but you know, if you don't have a whole ecosystem to handle that across multiple machines and it's, it's not as easy as you think that data's being collected, but it's pretty, it's not even available to you.

[00:35:13] **Carol:** Yeah. Or if the data be collected, isn't helpful. Like just the error and maybe a point in time or a file, like where this is happening at. Isn't super helpful if you don't understand the context of it. So like, we're pretty good about making sure that all of ours have pretty healthy messages in it, so, you know, what's going on.

[00:35:29] **Carol:** So even though the user never sees those messages, when I'm looking to the logs, I actually can find what was going on. I'm not just guessing at what, what the user was doing when this happened or what the system was doing. Sometimes it's not user generat.

[00:35:42] **Tim:** Yeah. It's I find when I first create a new project, I tend to over log thinking, I'm gonna need all this stuff, and then it'll be about a year later. And I realize I haven't looked at most of these log files that I'm generating may, maybe there's one, that's been interesting. So I'm going through the code and just delete all those lines, get rid of the logs because I'm not having to debug as often as I think, and a lot of times the places that have been problems, there was no logging, cuz I didn't predict that there would be problems there.

[00:36:09] **Adam:** can tell you officially, I'm sure that you have a retention policy on all this data that you're creating and

[00:36:16] **Carol:** Fabulous.

[00:36:17] **Tim:** the policy is I keep it till I don't want it anymore.

[00:36:20] **Adam:** So speaking of logging, actually that reminded me of this thing that I wish all programming languages had, which is like just the idea of a debug context that like, so like, as you're writing the code, you can just kind of think in your head, okay. If an error were, were to be thrown while I'm trying to do this thing, just show me like these variables, right?

[00:36:40] **Adam:** Like you don't want every variable that's been set throughout the request, but you want, you know, this thing would be useful to know this thing would be useful to know, and it like automatically would reset with every request and, or you could tell it, okay, flush that. And, and I'm done with that operation and I'm getting ready to start another operation.

[00:36:55] **Adam:** So if that was all successful, then clean that out and start a new. and then anytime an error is thrown, you could have it automatically include that debug context with the error information that you're logging. Right. man, I've done that so many times now, as like a custom built solution, there's gotta be a better way.

[00:37:14] **Adam:** I feel like that feels like something that should belong to the.

[00:37:18] **Carol:** Agree. Completely agree.

[00:37:20] **Ben:** In, in our application, when a request comes into the framework, like one of the very first lines that I have is I take the user ID if it exists on the session and I stick it in the request scope and for people who aren't familiar with ColdFusion, Co has scopes. The request scope, I guess, is kind of like, like a thread context in Java, maybe where you can access that request scope anywhere in the request.

[00:37:44] **Ben:** So I stored the user ID at the very top and anytime I have to log something later, I check to see if it's in the request scope for exactly that reason to see if I can get as much contextual information as possible.

[00:37:55] **Carol:** Yep. We do the same thing. Exact same.

[00:37:58] **Adam:** Yeah. It's like a, it's a global scope, but it's specific to that particular request.

[00:38:02] **Ben:** Yeah.

[00:38:02] **Adam:** not shared.

[00:38:04] **Ben:** So at work, we are on Kubernetes and I'm about to say a bunch of stuff that I don't really understand, but prior to Kubernetes, we were logging everything to log files, like dot log files on the server. Like ColdFusion would do that automatically for you when you, when you do a CF log or a log. Right.

[00:38:22] **Ben:** but once we got into the world of Kubernetes, my understanding is that the way Kubernetes works is you just write to the standard output of the machine. And Kubernetes, essentially SLS all of that into a centralized location. And then there's some sort of log aggregator that pushes that data somewhere.

[00:38:39] **Ben:** And I was like, oh, this is so amazing. Like, it's so much easier to just write to the output instead of worrying about separate log files, cuz you never run outta space, you don't have to rotate anything. but then at some point you realize that everything writes to the standard out, including like when you start ColdFusion and Tom cat is starting up and it's loading everything and it's just like barfing, you know, line after line of not structured data, it's just like I loaded this property's filed.

[00:39:05] **Ben:** And then that property's filed and this property's spot doesn't exist. And I pulled this outta the environment and yada yada yada yada. And right now when we do a deployment at work, we generate over a gigabyte of log data. That's literally just

[00:39:18] **Ben:** Tom cat and engine X and Lucy starting up.

[00:39:22] **Ben:** And I have no idea how to get rid of that. It's like, you actually need someone who

[00:39:26] **Carol:** huge.

[00:39:27] **Ben:** Java. And I do not know about Java.

[00:39:30] **Adam:** I wish I,

[00:39:30] **Adam:** could help you buddy.

[00:39:31] **Ben:** yeah, if I didn't deploy the application produces very few logs, but the fact that I deploy fairly often, I'm producing like gigabytes and gigabytes of log data a day, which you're like, whatever, it's just text.

[00:39:44] **Ben:** But, where we log, we have a quota and we're always going over our quota for how much you can log per day. And essentially if you go over your quota, they just stop indexing your, your data. So all of a sudden like yours

[00:39:57] **Ben:** will just for like four hours, there'll be no data in your logs.

[00:40:01] **Adam:** So, along with that idea of everything writing to standard out, that's kind of the default, behavior for node JS. So if you write like console log and a node script, it goes to the standard out, you can do console dot error. And I believe it goes to the standard error either way. and, and so like, that's kind of the CF dump of the node world, right?

[00:40:18] **Adam:** You just console log stuff and it shows up there, or, I mean, even in the browser, right. You do console log and it shows up down in the. browser console. And that's great until it gets taken away from you there. So I love using next JS, but I get so angry when I'm trying to debug something. And I just it's like, just give me console log and they, it, it goes nowhere.

[00:40:41] **Adam:** You cannot console log. You can't do it in the browser. You can't do it on the server side. It just goes nowhere. And it's infuriating.

[00:40:49] **Carol:** be furious. I Don. Could use it. I'd be like new language. No, can't do.

[00:40:54] **Adam:** Yeah.

[00:40:54] **Ben:** I have such a love, hate relationship with react. Love. Hate's not the right. It's more like love indifference or no hate indifference, whatever.

[00:41:04] **Ben:** Uh,

[00:41:04] **Adam:** I was like, wait a minute. That's not, that's not the Ben. I know.

[00:41:07] **Ben:** So at work on the legacy platform, somebody added react years ago. I'm very unhappy about that, but whatever, and they built the whole compilation step for all the react. The JSX. So, you know, gets like we're talking about it all gets bundled down into a normal JavaScript file. And for, whatever type of configuration choices they made, I have no idea where these are.

[00:41:29] **Ben:** it will strip out any debugger statements and any console log statements. So I can't tell you how many hours I've wasted trying to put console log into the react code, to debug something, and then not having to compile it. And then having no idea why it's not outputting anything. Thinking like, oh, I must be in the wrong code.

[00:41:47] **Ben:** And then like, literally hours will go by and I'm pounding my head and I'm like, oh, you know what? Now I remember last time I went through this, I realized that they were all just getting stripped pain.

[00:41:57] **Tim:** Yeah, login sounds.

## [00:42:00] Receipts, Receipts, Receipts!

[00:42:00] **Adam:** So sort of, sort of along the same lines, we do a lot of data auditing. So we, we have a, a one word chant in our, in our sort of team back channel when, customers are being difficult and the, the chance is just receipts, receipts, receipts, receipts, because, you know, customers will say the system's not working or, or, you know, whatever.

[00:42:21] **Adam:** And we can, when we can go back and look through our audit logs and say, actually the data that you're looking for is not there because so, and so deleted it on such and such time and such and such update. And, and this was the browser they were using here was their IP address. And you know, all these things, you, it really has come in so useful for us that it's like everything.

[00:42:40] **Adam:** We, we need receipts and. I wish it was easier to log atomic changes to database records. Right. So it would be so nice if there was just some way to like automatically get, you know, you do an update statement and it sends you back like, okay, here are the columns that changed. And this was the before and after that would be so nice.

[00:43:01] **Adam:** It would create a ton of data, but like, that would be so useful. Why does no database do that?

[00:43:07] **Tim:** Yeah. If you wanna do stuff that you gotta create triggers for, for updates and all that

[00:43:12] **Carol:** And then you gotta keep it in line. Yeah. Every time you add a new column, you have to go update the trigger.

[00:43:18] **Ben:** at work they've been talking about, I don't know if it. Technology or just a concept. They, they talk about something called change data capture may it might be a Amazon feature with RDS where I think you can set up whatever change data capture is. And it will it's, it's like a callback and it will tell you here was the structure of the row before something happened.

[00:43:43] **Ben:** And here's the new structure of the row. I, you, I don't think it gives you information about like, which user did it. So that's sort of problematic for, for your particular situation, but

[00:43:53] **Adam:** It's a, okay, so I'm on the Wikipedia page. Yeah. I'm gonna, I'll save this and I'll read it later, but it says it's a software design pattern. So yeah, this is not specific to any one product.

[00:44:02] **Ben:** So I think Amazon has something that implements change data capture, but that's as that's

[00:44:08] **Adam:** Mm,

[00:44:09] **Ben:** cuz that's as

[00:44:10] **Adam:** well, we're on Amazon, sweet. I'll look into that. Thank you. Maybe you just made my life a little bit better.

[00:44:15] **Ben:** Who knows.

## [00:44:15] Seen and Notifications

[00:44:15] **Ben:** so I have another database related item, which is storing whether or not a user has seen a particular piece of information. and so you can imagine that, let's say that you're doing something online and you perform an action and you want everyone else to be notified. So the next person who logs in, maybe they see a little, bar at the top, says like, oh, Adam invited you to this thing, you know, and you can dismiss it kind of, kind of an in piece of information and storing whether or not I've seen Adam's notification seems like one of those things that should just be super simple.

[00:44:52] **Ben:** It's like a flag you just set somewhere. And then that flag either gets created when I see it or deleted when I see it. but what I have found maintaining the same application for the last decade is that, a lot of users just never come back to the application. And now you have these like hundreds of millions of notification flags, just sitting there forever. And you're like, can I delete these? Like, what happens if someone comes back in seven years, do they need to know about that notification that Adam made seven years ago? Like now, do I have to get

[00:45:25] **Ben:** legal

[00:45:26] **Adam:** a thumbs up emoji on your

[00:45:28] **Ben:** Yeah. It's like, you, you even just like, like, are there legal implications on, do I have to have a data retention policy?

[00:45:35] **Ben:** Can I delete a notification like this? If a user hasn't logged in after a certain period of time and, and the, the whatever data structure using to store this information just continues to grow and grow and grow over time. And it seems like in you're just like, oh, the user clicks something and I, and I just, you know, acknowledge it.

[00:45:55] **Ben:** But, but, I, I, to this day, I don't know what the right approach to that is.

[00:45:59] **Adam:** There's so many little things that could go like, and this and this and this all sort of in there too, have you seen this was years ago, but there, there was a diagram that went around, like on Twitter of the, like the logic workflow that slack uses for notifications.

[00:46:14] **Adam:** Cause you can get it in your, you can get it in the app on your desktop.

[00:46:18] **Adam:** You can get it on your phone. You can get email notifications. There's probably other things too. And they batch 'em too. Right. You can say, okay, email me once a day with my notifications. If I haven't already seen them. So how do they. And then I guess if you, if you get the email, then they take it out of your, the list of notifications.

[00:46:36] **Adam:** That'll show you the next time you log into the app. And it's so complicated. And if you, if you see it, if you are idle in the application, then it'll start sending notifications to your phone. But then they, I guess in those cases, they stop sending it to the application as well. And it's just like, ridiculous.

[00:46:59] **Tim:** Yeah.

[00:47:01] **Ben:** it's funny you say that. Cuz when I, so I'm on slack at work and if I have to get up and go do something, I make a note in my head to unfocus the slack app, like go back to my code editor specifically so that it'll start sending notifications to my phone when I step.

[00:47:16] **Carol:** I do the opposite. I make sure it's in focus, cuz I'm like, do not notify me. I'm walking the dog. If it can't wait eight minutes, then someone should probably call someone above me because I'm, I might not be able to help you anyways. So yeah. I'm like don't

[00:47:32] **Ben:** Have unhealthy boundaries.

[00:47:34] **Carol:** a little, a little, I mean, you're going to pee with your phone and you want slack messages in there.

[00:47:39] **Carol:** So

[00:47:40] **Carol:** might be a little unhealthy

[00:47:42] **Adam:** this is the same guy who won't answer his text messages.

[00:47:44] **Ben:** Oh yeah. Yeah. It's a weird balance. I actually, one time dropped my phone in the toilet because I was standing there peeing and I was, I was like, wonder if I have unread messages? So I tried to reach into my pocket while I was peeing and I didn't

[00:48:01] **Carol:** Oh man,

[00:48:02] **Tim:** Not for the

[00:48:03] **Carol:** should have learned your lesson. can wait. It's just a couple minutes.

[00:48:08] **Tim:** Yeah. So that sounds easy, but it's not.

[00:48:12] **Adam:** okay. So, before we, step away to do our after show, let's, tease what we're gonna talk about tonight. So anybody wanna take credit for these, bullet list items here

[00:48:22] **Tim:** Yeah, we're gonna talk about a dinosaur stamped

[00:48:25] **Carol:** Ooh,

[00:48:26] **Adam:** you know, as, as you do, as those things

[00:48:28] **Tim:** as you do, gotta watch out for those dinosaur

[00:48:32] **Adam:** Yeah. And, and so as we're recording this, it's a Thursday evening and night water jumps are in two days. I know I mentioned it last week too, but they're two days. And so yeah, my, my a little puckered right now. So we'll talk a

[00:48:45] **Carol:** as it will be in a, in a few weeks when you eat all those hot wings,

[00:48:49] **Adam:** Oh my God. Yeah.

## [00:48:50] Patreon

[00:48:50] **Carol:** mm-hmm

[00:48:51] **Adam:** right. All right. So this episode of Working Code was brought to you by reading your phone notifications while you. And listeners like you, if you're enjoying the show and you wanna make sure that we can keep putting more of whatever this is out into the university, you should consider supporting us on Patreon, Our patrons cover our recording and editing costs and we couldn't do this every week without them.

[00:49:11] **Adam:** So special. Thanks to our top patrons, Monte Gavin and Sean. You guys rock. if you wanna help us out, you can go to patreon.com/WorkingCodePod.

## [00:49:20] Thanks For Listening!

[00:49:20] **Adam:** again this week, and maybe we'll just do the same homework every week until we get there. your, your homework is to leave us a question for our 100th episode, AMA you can find the link at workingcode.dev there's a banner big ugly red and yellow banner at the top of the page there I'll take you right to it.

[00:49:36] **Tim:** A MySpace.

[00:49:39] **Adam:** It does looks, all too familiar on mind space there. As usual, you can send us your topics saying questions on Twitter or Instagram @WorkingCodePod. You can join our Discord at workingcode.dev/discord.

[00:49:51] **Adam:** Can send us an email with either text or your voice. A voice recording from your phone would be great. And we'll play it on the show. You can send that also to WorkingCodePod@gmail.com. That's gonna do it for us this week. We'll catch you next week and until then,

[00:50:04] **Tim:** Remember your heart matters, even if you can't sinner something to save your life.

[00:50:09]

## [00:50:09] Bloopers

[00:50:09] **Tim:** What's going on there, Carol.

[00:50:35] **Carol:** super hot in the office and I couldn't figure out why I'm like pouring sweat and. The nest thermostat and it's 79 degrees in here. Apparently I got cold one day and closed the vent. So there's no air circulating in here anymore. So I was like, Hey babe, can you come open the air vent for me?

[00:50:53] **Adam:** I need

[00:50:53] **Carol:** Okay. Sorry. He's six,

[00:50:56] **Carol:** three.

[00:50:56] **Adam:** okay.

[00:50:57] **Carol:** reach it.
