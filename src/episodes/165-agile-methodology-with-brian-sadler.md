---
title: "165: Agile Methodology with Brian Sadler"
description: "Today, we talk to Brian Sadler; a seasoned software developer and Agile coach - about what Agile is, what parts of it work the best, and where teams often go wrong in their interpretation of best practices."
date: 2024-02-07
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *; clipboard-write" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;border-radius:10px;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/165-agile-methodology-with-brian-sadler/id1544142288?i=1000644473306"></iframe>

For the most part, software engineers like the concept of Agile methodology; and, they have a sense that agile development practices are the best way of getting work done. But, that doesn't mean we know how to put these agile practices in place (especially at scale). Today, we talk to [Brian Sadler][brian-sadler] ([@brian_sadler][brian-sadler-twitter]) - a seasoned software developer and Agile coach - about what Agile is, what parts of it work the best, and where teams often go wrong in their interpretation of best practices.

Follow the show and be sure to [join the discussion on Discord][working-code-discord]! Our website is [workingcode.dev][working-code] and we're [@workingcode.dev on Bluesky][bsky]. New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

[brian-sadler]: https://www.linkedin.com/in/wbsadler/
[brian-sadler-twitter]: https://twitter.com/brian_sadler
[working-code]: https://workingcode.dev/
[working-code-discord]: https://workingcode.dev/discord/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[bsky]: https://bsky.app/profile/workingcode.dev
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/165-agile-methodology-with-brian-sadler.md

With audio editing and engineering by [ZCross Media](https://www.zcross.media/).

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

## [00:00:00] Highlight

[00:00:00] **Adam:** manifesto for Agile software development. We are uncovering better ways of developing software by doing it. And helping others do it.

[00:00:07] **Adam:** Through this work, we have come to value individuals and interactions over processes and tools, working software over comprehensive documentation, customer collaboration over contract negotiation, responding to change over following a plan that is while there is value in the items on the right, we value the items on the left more. Period. That's it.

## [00:00:28] Intro

[00:00:28] **Adam:** Okay, here we go. IT is show number 165 and on today's show we are going to speaking with Brian Sadler.

[00:00:54] **Adam:** Brian, say hello.

[00:00:56] **Brian Sadler:** Hello.

[00:00:58] **Adam:** Brian, uh, is a friend of a friend of the show. And has some history, some work experience as an agile coach. And these days, I guess he's a bit of an agile Sherpa. So, this is a kind of a topic I've been wanting to bring onto the show for a while. We just had to find the right guest.

[00:01:15] **Adam:** So, we're going to dig into Agile and figure out what it's all about and why people hate it and why the people that love it, love it. And, you know, what are, what's true, what's good, what's bad, what's ugly. So that's the plan anyway. But first, as usual, we'll start with our triumphs and fails. And Ben, I'm going to come to you first.

## [00:01:33] Ben's Fail

[00:01:33] **Ben:** I'm going to go with a failure. This is a very light failure, but I'm, I'm working on some software. I've talked before about wanting to create a little site for writing and keeping poetry. And, I've started to break ground on that and I'm working on the access controls, meaning a user. Wants to edit a given poem or, delete a given poem.

[00:01:52] **Ben:** And as part of each one of those operations, they have to, the system has to verify that this user exists and this poem exists, and this user has access to do this thing with this poem. And I'm just having trouble finding a pattern in the code that feels elegant as far as verifying. Those access controls that this user can do this action on this object.

[00:02:12] **Ben:** I can, you know, replicate a bunch of logic in a different, in a bunch of places. I could pass some IDs around, I could pass some objects around and I'm sort of just. Keeping, moving code around, shuffling it around and, and nothing quite looks right. And, I don't know if I'm over estimating how elegant certain code can be.

[00:02:32] **Ben:** Like maybe it just has to be in all the places and it has to look the way it looks and it's, it's just going to be an unnecessary evil, maybe it just will never look, I'll never step away for a year and then come back and look at this code and be like, Oh yeah, that was a really clever, very clean approach.

[00:02:47] **Ben:** I think maybe I just have to bite the bullet and say. You just have to check that stuff all over the place and it doesn't look super great. But,

[00:02:55] **Adam:** Oh, I see. You're, you're looking for like a middleware almost to, to authorize access to stuff

[00:03:04] **Ben:** well,

[00:03:04] **Adam:** without having to write it into every crud

[00:03:07] **Ben:** It's, it's not that I don't want to write it into every CRUD operation. It's more like, as a quick aside, it's funny that you mentioned middleware because as, after I stared at the screen for like 45 minutes, kind of going over different, scenarios in my head, I said, you know, let me ask chat GPT.

[00:03:22] **Ben:** And I, I give it a couple of sentences about what I'm trying to do entities. People accessing entities, permissions, et cetera. And it suggested, Oh, just create middleware that you can put at the top of your request. or you could centralize it into an object. And that's sort of what I've been doing historically.

[00:03:39] **Ben:** I've had a central security service, I call it, and you basically just say. Get me this thing. And then as part of that, it's, it, it verifies that the thing you're getting can actually be accessed by the person you're saying is getting it. But the problem that I'm not liking there is that now I have this huge object and I get all of the different entities through this object and the names of these methods get really long because they have to be unique, right?

[00:04:05] **Ben:** Cause they're different methods on the class. And so now I'm thinking maybe I should make, instead of one giant security object, I make a security object. Kind of around a co located set of things. anyway, I'm just, I just want my code to look good. You know, I want to feel good about it. I want to feel like, oh yeah, clearly I knew what I was doing when I wrote this.

[00:04:24] **Ben:** That's, that's all I want, but I'll get there. So,

[00:04:28] **Adam:** Yeah, it does sound like there should be a pattern or, you know, some established, this is the way you do it sort of thing.

[00:04:36] **Ben:** and I get so hung up on stuff because imagine you want to delete a poem. So part of that is maybe I get a user from the record and I get a user from the database and I get the poem from the database. And then I have to call a method that says, can this user do this thing on this poem? And, and internally to that method, if let's just say I pass it IDs internally to that method, it could then also go to the database and get the poem and then make sure like poem.

[00:05:00] **Ben:** userId is the same user. And then I'm like, ah, but now I'm pulling the poem back twice in the same request. And that feels weird, but it's different concerns. So then maybe that's not weird. And I, and then that's where I get hung up.

[00:05:13] **Adam:** a typical approach to this problem in ORMs would be to be like, you would, you could go either way. I think the way that I would probably implement it is like a, on the user object, you would have like a hasPoem object where you would pass it the ID of the poem or something, or, or I guess you would have to pass it the poem entity.

[00:05:32] **Adam:** Right? And then it would run a query to say, okay, you know, check whatever table sets the permissions there, say, okay, does this user have access to this poem? Right? So user. hasPoem, poem, and then you're going to get true or false to continue. But

[00:05:49] **Ben:** Yeah. So I think I want to do that general approach. I just don't necessarily want that to be on the user or on the poem directly. I sort of want it to be a separate concept. I mean, referential integrity, you know, the poem has a user ID. I just don't want that to necessarily mean, I don't want that to have any inherent meaning to the poem.

[00:06:11] **Ben:** I want something kind of a layer above that to say, Oh, because you have this user ID and I know that I have this other user with this ID, then I know what you can do in the system. But I don't want that to be the responsibility of the thing I'm calling poem.

[00:06:23] **Adam:** I think you're,

[00:06:26] **Ben:** I'll

[00:06:26] **Adam:** I think you're overthinking it. I think you're overthinking it.

[00:06:28] **Carol:** Sounds very complicated.

[00:06:30] **Ben:** you know, it's like I have, I have a solution that'll work. I just don't like the way it looks. Anyway, all right, that's me, that's a light failure. It's a, it's like, you know, you figured after so many years of doing this thing, kind of variations on this thing for so many years, I'd have something that just, Oh, of course, this is how I'm going to do it because it's proven to work so well.

[00:06:49] **Ben:** But this is, this is one of the parts of an application that I've never felt confident about in terms of being done, quote unquote, the right way. I've never. Never been satisfied.

[00:06:59] **Carol:** This is where I would ask you to share your code with me, because I need to understand why it doesn't look good.

[00:07:04] **Ben:** All right. I'll, I'll get something on paper and, and maybe we can do a little powwow.

[00:07:08] **Carol:** well that would be fun.

[00:07:10] **Ben:** Awesome. All right. That's me. Carol, what do you got going on?

## [00:07:13] Carol's Triumph

[00:07:13] **Carol:** Well, I'm sorry, you're a loser, but I'm a winner. I'm going to go with the Triumph. Um,last week I mentioned that, you know, I was having some issues with something very simple, you know, a unit test, a search through, you know, types being checked. And I really wished I had a team that I could talk with about these things.

[00:07:32] **Carol:** Well, Today and yesterday, I got added to group chats with people that normally I don't chat with. And we got to tell jokes today. And later on, I even asked one of the engineers what they thought about something and it was just the best day ever. So I definitely got to tell my calendar joke and I have a new joke for you guys too.

[00:07:50] **Carol:** So do you want to hear the joke real quick?

[00:07:52] **Ben:** Of course.

[00:07:52] **Brian Sadler:** Yes, please.

[00:07:53] **Carol:** Do you think that, pencils poop?

[00:07:57] **Ben:** I don't know.

[00:07:58] **Adam:** everybody poops,

[00:08:00] **Carol:** Where do you think number two pencils Oh, wait, I said it wrong! Oh, man! I should have had, I should have had my meeting open. Do you think trees poop is the actual joke? And the answer is yes. Where do you think number two pencils come from? Oh, I ruined that one.

[00:08:20] **Ben:** we all enjoyed it. I think we all enjoyed it.

[00:08:25] **Carol:** Well, I'm just happy I have friends at work.

[00:08:29] **Adam:** congratulations on your triumph. I know working alone is extremely isolating and, and lonely. And, I think honestly, when we added a third person to my company and, you know, cause it was me and Steve for so long and. when we added a third person, it's like, finally, somebody who won't be so busy, they can't ever talk to me.

[00:08:49] **Adam:** I can have somebody to talk to in the company. It was a big deal for me.

[00:08:53] **Ben:** Yeah, absolutely.

[00:08:54] **Carol:** I mean, I told my product owner today, I was like, it's getting a tad bit tense for me because everybody's looking to me to make technical decisions about the way we're going with these projects, but I don't have anyone to lean on to talk through these technical concerns I have, so I'm feeling a lot of pressure and I'm not for sure how to get through this, so I definitely need someone on my team very soon to just pow wow with. But that's me. What about you, Adam?

## [00:09:22] Adam's Fail

[00:09:22] **Adam:** Oh, I'm gonna go with a fail. it's a, it's a little thing, but it's, you know, it's one of those things about my personality that drives me nuts. the fail is, you know, I, I did this really nice desk build. I built myself this beautiful, huge walnut desktop to put on my standing desk legs. And I love it.

[00:09:39] **Adam:** And it's gorgeous. And sitting on the floor to my left is a pile of cables. From all of the stuff that I took off of my last desk that I can't bring to bring myself to put on the new desk. It's like, it's clutter. I don't want that clutter on my desk, but it doesn't have anywhere else to go. So now it's just cluttering the floor and I've got things like I've got a laundry hamper full of like other stuff that was cluttered on my desk.

[00:10:04] **Adam:** and it's just now it's cluttering the other side of the room. And I hate that it's there, but. I'm protecting this space and, it's driving me nuts. So I got to figure out something.

[00:10:18] **Carol:** So I found a three drawer system that is tall enough to fit under my desk when it's all the way down. And that is where I am going to put my makeup and stuff because, you know, a few episodes back, I talked about my two desk situation going on, well, I've decided to get rid of one of them. So I'm going to put my makeup in there and I'm also going to put like my extra.

[00:10:38] **Carol:** Like phone charger, mixer, headphones, all in there. And it fits right under the edge, but doesn't interfere with the up and down. And it's out of sight, out of mind, but close enough that I can still get to it when I need it.

[00:10:50] **Adam:** And is it, it's, is it like nicer than the, those cheap like Walmart plastic, you know, shelf or, or drawer things like the, whatever.

[00:11:01] **Carol:** Yeah, I can let you know when it gets in, cause I haven't, it's not here yet. I just ordered it this weekend. Yeah. And I got it from Wayfair, but I was looking at one at West Elm too. So they're solid wood, nice, not metal, and they're not that cheap fake wood stuff.

[00:11:14] **Adam:** Right. Particle board. Okay. That might work for me. I am just. I think it's more my personality than, than a lack of a, a possible solution. It's just, that's my thing is I start things. I'm real good at starting things, not as good at finishing them.

[00:11:33] **Ben:** starting like a champ.

[00:11:34] **Adam:** Yeah. So along the same lines, I think I've mentioned this on the show before.

[00:11:39] **Adam:** I, I have these things around the house that are called DOOMpiles, D O O M. and that stands for didn't organize, only moved. you know, like I, I had good intentions. I'm trying to like move stuff to where it belongs. And I'm like, you know, it belongs in that room at least. Right. So I'll move it into that room.

[00:11:57] **Adam:** So there's a doom pile in the room. Like my, my nightstand and like my side of the bedroom are just like, it's clutter town, but it's all stuff that belongs either, either it belongs in the room and hasn't been put away in the room yet, or it belongs out of the room. And it's in a pile so that it can later be moved out of the room.

[00:12:11] **Ben:** I feel this. I got a whole set of doom shelves back here. It's just various piles of stuff that should be somewhere else.

[00:12:21] **Adam:** So I just got to get my brain in gear and make it a priority. I think one day it'll happen. Maybe. So, that's it for me. How about you, Brian? You got something for us?

## [00:12:32] Brian Sadler Triumph

[00:12:32] **Brian Sadler:** yeah, I'll, I'll go with the fact that we had a really good retrospective at work today. and obviously retrospective is a key, adjunct event. so we had a, you know, a really substantial conversation and discussion about things that were hindering us and where we want to make changes, don't want to go upset, which is always good.

[00:12:49] **Brian Sadler:** you know, it wasn't too emotional, but at the same time, I think that we, we kind of realized a few things that we want to make, changes as. Where we want to make improvements as a team. And that's, that's core to sort of Agile is, is taking charge of your own ways of working and looking to improve constantly.

[00:13:03] **Brian Sadler:** So, I think that was a win in terms of having a good discussion. Hopefully the action points get followed up on. only one of them is for me,

[00:13:13] **Adam:** Nice.

[00:13:13] **Brian Sadler:** so it was a win.

[00:13:15] **Adam:** Excellent. Yeah, I mean, I'm, I'm eager to dig into this Agile stuff, but you had something you wanted to add, Ben?

[00:13:21] **Ben:** no, it's cause I, and I definitely want to dig into retrospectives as well. Cause I, I have some conflicting thoughts about

## [00:13:28] Brian Sadler Introduction

[00:13:28] **Adam:** Okay. Well, before we dive into the deep end here, Brian, however deep you want to go, can you give us just like a little bit of, your, your history with Agile? What makes you more qualified than the three of us who have basically zero experience with Agile to, to defend and, or belittle it as appropriate?

[00:13:49] **Brian Sadler:** That might be a, might be a controversial statement, but, I think, my, my background has been,ColdFusion developer. So back in the late 90s, I, went through, you know, the fast track to ColdFusion and Ben Forter's whack books. And, I did that for about 15 years. and I eventually in the, in the pursuit of more responsibility in the workplace, I was, persuaded not to sort of become like a development manager or something like that, but, to try and, inculcate.

[00:14:16] **Brian Sadler:** An agile mindset into some of my colleagues. so I worked for a company in London that was bought out by a larger company in Dublin, and there was a kind of meeting of, of minds across the Irish sea. and the London organization had been doing scrum. And they were quite intrigued about, how we were doing it and it seemed to be quite successful from their perspective.

[00:14:36] **Brian Sadler:** So there was a much larger presence in Dublin and Ireland and I, that hot potato of, of kind of guiding the organization through an agile transformation landed in my lap. so for about, five of the last seven years, I've kind of self identified as an agile coach. And I've stood in front of people and, tried to talk and talk and, you know, observe and coach and guide and mentor people into being more agile.

[00:14:59] **Brian Sadler:** and I've taken a step back in the last couple of years. Just, I think you can't really be a good coach if you're not doing stuff and you're not staying current. And I think you, you spend too long on your goal face, then you start to start to miss out or feel you're missing out on a lot of the stuff that's going on around.

[00:15:13] **Brian Sadler:** around you in the industry and also I got my arm twisted by Adam Cameron to come and join him. His place of work, and yeah, he's quite persuasive. So, so yeah, I'm living the dream working with Adam and still being, trying to be true to my Agile philosophy and values. but yeah, I, I have tried to sell this Agile stuff to other people in a professional capacity.

[00:15:35] **Brian Sadler:** Maybe I'm slightly more qualified than you guys.

[00:15:39] **Carol:** When people say scrum and agile, is that the same thing or do they have different meanings?

[00:15:45] **Brian Sadler:** They definitely have different meanings. I think, you know, maybe it's, when we start talking about Agile, most people don't really have a handle on what Agile is, including Agile practitioners. I think it might be useful, you know, if you indulge me, just to talk about where it came from. It actually is now, you know, it's quite a means of doing Agile, one of the several means of doing Agile, the most popular, but Agile really is, I mean, it's very old.

[00:16:14] **Brian Sadler:** It's from 2001 is when, the guys got together in Snowbird in, Utah, the Ski Lodge. And these were, sort of industry leading figures in what could be. Termed lightweight project management methodologies or software, development methodologies. And, and, you know, that's 2001. That's a long time ago.

[00:16:32] **Brian Sadler:** And it was a reaction to the kind of dysfunctionality that was, was going along in the industry in the nineties, maybe the eighties as well. the, the problems were about large scale product projects, which were going catastrophically wrong. The ones that hit the headlines were the ones in the public sector.

[00:16:48] **Brian Sadler:** I think it was one for the federal aviation authority for. You know, air traffic control system that cost billions of dollars and delivered no working software. there's, there's, there's plenty of, plenty of examples across the pond, both in the public and private sectors. And, it was felt by, you know, the, the, the guy who read the Agile manifesto in 2001, you know, people like Bob Martin and Martin Fowler and a host of others, this was just a waste of time.

[00:17:12] **Brian Sadler:** It was, you know, the sellers of IT projects were just. Taking money under false pretenses. Nobody was winning, at least of all the people in the industry who were coders, who actually believed in what they were doing and wanted it to be a service to the customers and the users, but were hampered by all this bureaucracy and nonsense and, you know, spending years in big upfront design exercises and delivering nothing.

[00:17:36] **Brian Sadler:** So that's where the kind of agile came from. And back in 2001, It probably seemed a bit revolutionary and a bit fresh. I, my view now is like, who's, who's not doing Agile? 2024.

[00:17:52] **Ben:** Well, and who's, who thinks that they're doing Agile and, and aren't doing Agile at all? And, and maybe can I ask a question?

## [00:18:01] Agile Misconceptions

[00:18:01] **Ben:** Maybe this is an ill timed question. When you talk to people about doing Agile, and I'm sure a bunch of people will say, Oh yeah, our team is doing Agile. We do X, Y, Z. What, what would you say is, is the number one misconception or misunderstanding of what Agile is that you see?

[00:18:18] **Ben:** People putting into practice. Yeah.

[00:18:24] **Brian Sadler:** the, the, the common one is Agile equals Scrum. And, you know, it did, you know, that's, that's one of the most common misconceptions and that, that, that isn't true. so there's this idea of, you know, if we have standups, we have JIRA or stickies on a wall and, you know, that we're somehow doing Agile and that's not really the case.

[00:18:42] **Brian Sadler:** All that sort of paraphernalia, is, is, is really, you know, you know, sort of a sideshow. It's, I mean, one of the guys, Dan North, who invented behavioral, devised behavioral driven development, his definition of agile is you, you work in small chunks and you listen. Both to the way that you work and also to the results of what you deliver.

[00:19:02] **Brian Sadler:** And if you're close to the users and close to the customers and you're working in an incremental fashion and you're actively seeking out feedback and acting on it, then you're probably doing agile and all the rest is details.

[00:19:15] **Carol:** Ben, your heart is agile.

[00:19:20] **Brian Sadler:** Excellent. End of the podcast. Job done.

[00:19:22] **Carol:** yeah.

[00:19:27] **Brian Sadler:** But, but there are, you know, there are lots of different things and I think the thing is that, you know, that you can kind of follow the instructions and look up the guidance and you know, the usual thing, you get the scrum guide, you go through the scrum guide and, you know, we must have our stand ups at 9am and if you're five minutes late, you know, you're going to be in line for an admonishment and, you know, that's, that's not agile.

[00:19:47] **Brian Sadler:** That's, you know, just nonsense. So,

[00:19:49] **Ben:** one could argue that's process over people, which I think it's,

[00:19:53] **Brian Sadler:** Absolutely. But you really are agile,

[00:19:56] **Ben:** uh,

[00:19:56] **Carol:** Yeah.

## [00:19:58] The Agile Manifesto

[00:19:58] **Adam:** So maybe, it's worth pointing out for anybody who isn't already aware. I, I, I went, I don't know, six or eight months ago, I went and I read, the Agile Manifesto and the Scrum Guide and a book called, Learning Agile from O'Reilly. So I'm, I'm surface level familiar with a lot of the stuff here.

[00:20:16] **Adam:** The Agile Manifesto itself though, is, is interesting in that it's, it's extremely short, so short, I'm going to read the whole thing here in a couple of seconds.

[00:20:24] **Ben:** nice.

[00:20:25] **Adam:** And the thing that is. I think the most interesting about it is that it is not at all prescriptive in terms of processes or tools. It's just like a mindset.

[00:20:35] **Adam:** That's it. That is like, if you adhere to the mindset, then it's Agile. That's my surface level understanding. Here, let me read it real quick because I looked it up. manifesto for Agile software development. We are uncovering better ways of developing software by doing it. And helping others do it.

[00:20:50] **Adam:** Through this work, we have come to value individuals and interactions over processes and tools, working software over comprehensive documentation, customer collaboration over contract negotiation, responding to change over following a plan that is while there is value in the items on the right, we value the items on the left more. Period. That's it.

[00:21:13] **Ben:** Yeah, it's pretty, pretty simple.

[00:21:15] **Carol:** Yeah. Why can't people do it?

[00:21:21] **Brian Sadler:** I mean, it requires no interpretation whatsoever.

[00:21:24] **Carol:** Clearly? Yeah.

[00:21:27] **Ben:** I

[00:21:28] **Adam:** how do we get from that to Scrum and XP and all these other things?

[00:21:33] **Brian Sadler:** Yeah. I think that, I mean, there are a couple of other sections to the manifesto, but that's like kind of the, the. There's the, the 12 Agile principles as well, which, which come to support it. And I'd also, I'd prefer anybody who's listening and wants to dive into that, I'd also really recommend reading the about page or the history page on the manifesto, because that gives a commentary by Jim Highsmith, one of the guys who was there, and it gives some more background about the context.

[00:21:58] **Brian Sadler:** and, you know, he uses a bit of profanity for, Cameron's sake. also,you know, it really captures the spirit of what they were trying to do there. and I think that, you know, how do we go from, from the manifesto to things like, you know, Xtreme Programming, Scrum, Kanban, and they all claim to be manifestations or implementations of you know, frameworks, methodologies, whatever you want to call them, that adhere to the Agile values and principles.

[00:22:23] **Brian Sadler:** So, so you would say that if, if Scrum done properly, you know, it's about individuals and interactions over processes and tools, for example, Scrum doesn't mention the tool, it mentions the process and the framework and stuff, but, you know, at the same time, it should be that individuals and interactions are more important than the processes and tools.

[00:22:42] **Brian Sadler:** So,

[00:22:43] **Ben:** I, I was listening to a podcast the other day and someone talked about the concept of operationalizing something, and I think I might get this wrong, but I, I believe what they mean when they say operationalize is take a set of best practices. And codify it in a way so that the organization does it at scale in a way that you don't have to interpret it.

[00:23:05] **Ben:** It's, it's, it's kind of, it becomes more rigid so that best practices can be instilled everywhere. And, and I think maybe that's part of what happens here is people have the best intent to take the agile practices and put them into place. But when you're a software team of three people and you're all talking to each other and you've known each other for years and, and you can kind of complete each other's thoughts, it's easy to understand where the lines between best intentions and letter of the law and intent of the law happen, but then when now you have to scale up and you have an engineering organization, it's 300 people.

[00:23:40] **Ben:** We have to take those practices and operationalize them so that everybody can do Agile properly. And I think we, we maybe lose the, what's the expression? Lose the forest for the trees or the

[00:23:51] **Adam:** see the forest for the trees.

[00:23:53] **Ben:** Yeah. I think maybe that's a big part of what happened.

[00:23:58] **Brian Sadler:** I mean, in the kind of agile industry, there's this kind of, criticism of the, Scrum industrial complex, and, you know, that, You know, Scrum was the one that was best marketed, was the most mature as, as, as, as they went into snowboarding in 2001 and it kind of, it kind of snowballed from there.

[00:24:15] **Brian Sadler:** But the, you know, Scrums is probably on the more prescriptive end of, of ways of working within Agile. You know, we're talking about, you know, that there are set ceremonies or events they call them and the set roles and you've got to change your job title and all that type of stuff. And it's, it's, It's a little bit over the top, shall we say, to those who were just wanting to dip their toe into what Agile is all about. but at the same time, it's kind of like training wheels. If, if, if you're in an organization that's struggling and these are, these are, you know, why would any organization or team want to go into Agile?

[00:24:46] **Brian Sadler:** It's because they've got some problems. If everything's going fine, they just don't want to know. It's alone and we're. You know, we'll get on with the work. but if there's a, you know, the scene is a burning desire for change, or the burning need for change, then you're going to look around and say, well, why don't we try this scrum thing?

[00:25:00] **Brian Sadler:** And scrum is very prescriptive to start off with, but if you do it for a while, you start to outgrow it because I mean, and. You have to have some sort of rigor, otherwise it's a free for all. So Scrum imposes some rigor. There might be a bit too much rigor for lots of people. And then, you know, that's fair enough. If you're doing Scrum and you're kind of faithful to its intent, then you will, we're doing retrospective, which is at the. The heart of Agile is one of the principles, you know, at regular installs, you know, the team reflects on its ways of working and tunes its behavior, accordingly. you will then grow and you will maybe, you know, sort of, outgrow Scrum.

[00:25:37] **Brian Sadler:** And, you know, you will tweak your Agile process for yourself and say, we don't use Scrum anymore, we'll do Scrumban, we'll do Kanban, or we'll do our own hybrid of stuff that we find useful. For a few months at least, it's a very good idea to just Roll with the punches and be a bit uncomfortable and understand why do we have a daily stand up even though there's three people on the team.

[00:25:58] **Brian Sadler:** Because some days We might not talk to each other, even though we generally do. you know, some days we'll forget, at least if we've got one 15 minute, meeting in a calendar every day, we will just walk through our work in progress. We'll talk about what we did yesterday and what's blocking us. You know, and the key thing is what's blocking, because if you identify blockers and get them out of the way, you maintain a nice steady flow of work and you don't have this rollercoaster of emotions and.

[00:26:24] **Brian Sadler:** you know, demands and stuff placed on the team. So, and it's an empirical activity. You, you, you learn more by doing, you might learn it and you might do it and hate it, but at least if you hate it, if you do it and hate it, you're coming from a, a place of experience and you know, that was subjective on me and I've got nothing out of it and might hate it.

[00:26:42] **Brian Sadler:** Great. Don't do it. But, most people that I've worked with the most teams that I've worked with don't go back. you know, they find that they get some value out of this and they. Didn't really forget what they did before. They can't remember how they operated without some sort of heartbeat. Could be scrum, could be Kanban, could be XP, whatever.

[00:27:00] **Brian Sadler:** But, they find they got a lot out of it.

## [00:27:02] Agile Meetings

[00:27:02] **Adam:** Is there a certain like project structure or type of project or, so what I'm coming back to is like my organization, it's a very small team. You know, my team is three people. My company is seven people. We, for a long time, did a daily stand up and it, over time, it morphed into like, one person, the CEO, always has like a whole bunch of stuff to catch us up on because he's kind of off in his own silo doing sales work and business development and customer service and all kinds of other stuff where the rest of us get to be kind of heads down, moving the ball forward on project work, and so that stand up turned into a daily opportunity for him to like unload, this is what, you know, changed in our world.

[00:27:47] **Adam:** The new, he'd paint a new picture of the world every day. and the rest of us would be like, yeah, you know, I'm still working on my project, no blockers. And so clearly that's not, you know, that, that is not an agile standup meeting. And maybe the problem is just that like, the way that we work, where each person tends to be on a project that lasts anywhere from 2 weeks to 12, 20 weeks, and, and for the most part can just work by themselves, you know, like, if it, I think when we tend to need each other, it's less because I'm blocked by something and more because I have a really huge project We have a specific deadline for some, you know, functional need, and I just don't have enough time to get it done, so I need like, but it's not, it's not an unblock me, it's a, we need to spread out the workload situation.

[00:28:42] **Adam:** Is there some fundamental difference in the way that we're working that just Agile doesn't mesh with, or?

[00:28:48] **Brian Sadler:** well, I think your CEO, hogging your stand up is, you know, maybe, maybe an agile anti pattern. know, um, you know, maybe the CEO is part, part of the development team or not, maybe he's a key stakeholder and, but, but essentially, you know, the, the development team are the people doing the work and it's their meeting.

[00:29:06] **Brian Sadler:** So if the CEO wants to, to broadcast stuff, then fair enough, do it afterwards or let him do that and then hold the stand up afterwards. You know, the real stand up for yourself, for yourselves. and I think it's genuinely, genuinely, genuinely in small teams, you can get a situation where you don't need to stand up because you're talking, you genuinely are talking all the time and anybody who puts, who wants help will put their hand up.

[00:29:28] **Brian Sadler:** but those things are incredibly rare. You know, I mean, most

[00:29:32] **Adam:** I'm rare.

[00:29:33] **Brian Sadler:** yeah,

[00:29:35] **Ben:** Well, if

[00:29:35] **Ben:** I can,

[00:29:36] **Brian Sadler:** and unique.

[00:29:37] **Ben:** can interject for a second or Carol, did you have your hand up or did you already?

[00:29:42] **Carol:** No, go ahead. I, mine's a different topic.

[00:29:45] **Ben:** So if I reflect on how some of my meetings at work have sort of spun out of control in terms of their scope, I think to your point, we were not historically a team that was talking all the time. I've been working remotely for the last. 17 years or 15 years or something. And so you have to be very purpose driven in terms of your communication.

[00:30:09] **Ben:** It's very easy to just go heads down. So when we introduced the concept of a standup. It suddenly was this scheduled get together that we would have every day. And I think a lot of us would have the mentality throughout the work week, you'd have a problem kind of brewing in the back of your head and you think, Oh, I'll just talk about this tomorrow at standup.

[00:30:29] **Ben:** So standup became not just about the blockers. It became a. Brainstorming session. Hey, I've got this problem. Let's talk it out. And suddenly what probably could have been a 10 minute meeting is actually an hour long meeting because the five people involved are all kind of going deep on the problems that they're having.

[00:30:46] **Ben:** And I get the pushback against something like that, but at the same time, it was also, it was very revolutionary in a way to have this scheduled block of time where it was just kind of a. Not a free for all, right? That sounds too unstructured, but it was this open, open forum where people could start to talk.

[00:31:04] **Ben:** And I almost, it's like the pendulum has to swing too far in one direction before it kind of comes back to the center. But I think that's, that was kind of a usage pattern that we fell into a lot at work where we just kind of kept going, kept going in the conversation.

[00:31:20] **Brian Sadler:** Yeah. And I think that's, that's where the role of a, you know, a, a good, scrum master stroke agile coach at a team level can help with the facilitation of these meetings and make sure getting out of them what you want to get out of them. I mean, the, the main. The main reason why the standups, daily standups are short is because if you raise an issue or I want to have a brainstorming session, it doesn't affect all the team.

[00:31:42] **Brian Sadler:** You know, you've got a team of 10 and it's like, Oh, I've got a front end problem. And there's two front guys. It's like, well, just go off and talk about it. And so, you know, and that's where the, you know, a good, a good team level coach will be, will be saying, right. Okay, great. standups about raising issues, not necessarily solving them.

[00:31:56] **Brian Sadler:** And we can't. Have four to go down rabbit holes because you've got eight people out then sitting there looking at their feet saying, why am I losing the will to live? you guys, it's just these two people trying to solve their own problem. How selfish are they? I want to kill them. I hate this team when they hate scrum.

[00:32:13] **Brian Sadler:** so, so that's, that's, that's what, you know, experienced agile teams will straight away be jumping on that and, you know, taking offline. You know, that's, that's for the after party, if

[00:32:22] **Ben:** Yeah, yeah,

[00:32:22] **Brian Sadler:** And that's, that's, that's, you know, but I mean, if, if the, if you've got, you know, a small team and, issues are raised and it generally is of interest to everybody, then there's no harm in solving it right there.

[00:32:33] **Brian Sadler:** And then if, if that's what you think is the right thing to do and everyone genuinely gets used out of it, and you can tune, you know, and that's why I think the retrospectives are so important because you can tune, you know, Hopefully get the opportunity to tune your behavior as a team and say, well, either that's good or bad, or, you know, I want, I want a longer meeting every day, or I want a brainstorming session, or I, you know, can we just get in and out in five minutes, you know, or can we cancel it and tie it up to you guys?

[00:32:57] **Brian Sadler:** I mean,

[00:32:58] **Adam:** I'm glad you mentioned that. So, you know, as we were initially trying to introduce standups in our, our routine, I would say maybe three or more days a week, you know, we would head into this thing and it would be like, you know, the, the five or 10 minutes before the meeting, we would do a quick like straw poll in our team chat and just be like, does anybody have anything that you want to talk about?

[00:33:18] **Adam:** Should we just cancel it? And more often than not, we would end up canceling it. And. Is that an anti pattern? Does that mean that we're doing something wrong or is that a good thing? Because it means that all the necessary communication is already happening.

[00:33:31] **Brian Sadler:** time to get the cattle prods out, again, it's something you can see the temptation and I think the thing is, you know, if you would, if you had stuck with it for years and that's where you'd all ended up, then yeah, fair enough. But I think in initial phases, you know, if you were adopting, virtually every Agile, You know, kind of way of working mandates, a daily standup or it's, it's common practice is just do the standup because there's, there's lots of, the main purpose is to plan for the day ahead.

[00:33:58] **Brian Sadler:** but there's lots of other positive side effects in terms of socializing new work that comes in at a team level, rather than an individual level. So that the team themselves can own firefighting or crises if they crop up. and also that you can collaborate. Everyone on the team is there. So if something.

[00:34:14] **Brian Sadler:** If something comes up and it's like, I've got a, you know, backend stuff on a database issue, then it's like the guys are in the room and you don't have to go hunting for them. Whereas if you're doing it offline and asynchronously, yeah, it's not, not, not so great.

## [00:34:26] Time Estimations

[00:34:26] **Carol:** Well, I got two things. So, let's talk about story points and how they equal time, but they don't equal time and how you're supposed to put. Points on things based off of like an effort, but then they come back and say, how long is it going to take you? You put a three on that. Why is it taking a week to do it?

[00:34:44] **Carol:** I'm like, I thought points weren't time. Like, are they time? Do you want to know a time? Or do you want to know a point? Or a t shirt? What size t shirt do you wear?

[00:34:55] **Brian Sadler:** Yeah, the, the, the, the story points are actually, they, they came from xp, back in the day, and they, they were called nuts, and units of time. and, and you know, the, the whole point is that it's all, all agile estimation is about using yesterday's weather and relative estimation. So, you know, the best predict of our today's productivity is yesterday's and tomorrow's productivity is yesterday's.

[00:35:19] **Brian Sadler:** And what's the you know, we are absolutely terrible at absolute estimation. not too bad at relative estimation. So, you know, feature A is going to take twice as long as feature B, roughly. We think, you know, We're quite good at, you know, sort of sniffing out the easy jobs and, you know, avoiding the large ones, you know, if we, if we, you know, kind of need to bet our lives on it.

[00:35:42] **Brian Sadler:** So using those two things, we can just combine the story points and attempt to combine them basically to say, right, okay, well, it's story points and we've got relative sizing on the whole range of tasks that might be in our backlog. And then at the moment we're getting 10 story points down the sprint.

[00:35:57] **Brian Sadler:** Okay. So next, next sprint, we'll get 10 story points done. Oh, I've got five stories at two points each. Looks like we'll get those done. But when we're getting too deeply into estimates as a commitment signed in blood, then that's not Agile. it really isn't, you know, it's, I, I, I mean, one of the, one of the guys that I kind of got into in terms of reading way before Agile came around was Steve McConnell.

[00:36:20] **Brian Sadler:** And, one of the best books I've ever read on software development is his book on software estimation, demystifying the black art. and it's, you know, if you. Really bored one weekend,

[00:36:30] **Ben:** it's called demystifying the black art.

[00:36:33] **Brian Sadler:** of Software Estimation. Yes, it's, so Steve O'Connell wrote Code Complete, Rapid Development.

[00:36:38] **Brian Sadler:** And I just think he's a just fantastic author. He's one of the guys who wasn't in the Agile,manifesto writing session, but he probably could have been, but yeah, basically it's, estimation is not impossible, but it's not easy. and it takes an awful lot of effort. Therefore, there's no point in trying to put that effort into something that's almost certainly going to be wrong anyway.

[00:37:02] **Brian Sadler:** So, and then really why are we making an estimate? sometimes when, you know, Back in the day, an estimate was really about getting the development team to sign off in blood. And then, you know, the punishment beams would start as soon as that deadline was looked like it wasn't going to be met. and I remember reading Steve McConnell, I think it's in rapid development, he talks about, he talks about Microsoft Word, the first version, and that was a project that ran for five years and, for the last four years of the projects, they were nine months away from completion. So

[00:37:33] **Carol:** Mind

[00:37:34] **Ben:** You bring up some interesting points here, because as you're saying that the Agile Manifesto was written in what, 2001, is that what you said?

[00:37:41] **Brian Sadler:** yeah,

[00:37:42] **Ben:** And that was at the end of an era. The way we were building and delivering software was really on the cusp of fundamentally changing with, with web based software.

[00:37:53] **Ben:** And even in the last 23 years, I mean, to think about how software was developed and deployed in 2001 versus 2024, it's, it's, it's a world of difference. And it makes me think about, so many, many, many episodes ago, we read Clean Code by Robert Martin, Uncle Bob. And I remember watching a video presentation of his, and he was talking about how he used to have to write the software that they would burn onto chips that, that they would put in devices that they had to ship.

[00:38:26] **Ben:** And you're like, yeah, that's a very, very different mentality than I'm going to write some code this morning and I'm going to deploy it in two hours. And if it breaks, I'll write some more code and I'll redeploy it. And I, and I sometimes wonder if some of the practices aren't necessarily evolved to keep pace with the way we think about and approach software development.

[00:38:48] **Ben:** And, and, and maybe I'm, I'm needling here very specifically at all, at all the story points in the planning poker.

[00:38:54] **Brian Sadler:** Mm.

[00:38:55] **Ben:** And, and if I can share one more story and I'll change all the names to protect the innocent here, we, we used to have standups where we would have a little, a small backlog, you know, 20, 30, 40 tickets.

[00:39:07] **Ben:** And then at the beginning of the week, we would all get on a call together and we would look at this backlog and we would do planning poker. And I don't know if this is an official term, but essentially everyone on the call would give an estimate for what a ticket was. Someone says one, someone says three, and then we kind of pick the average. And then someone who shall remain nameless would spend 15 minutes trying to have us argue our case. If we said, oh, it should take a two, and this person said, I think it should take a one, why do you think it should take a two? And you have to dive into all these details about You know, this and that, and, and we're all looking around and you're like, the, what are you talking about?

[00:39:46] **Ben:** One versus two, who cares? If you finish the ticket ahead of time, then you just take the next ticket. This is not life or death.

[00:39:55] **Brian Sadler:** Absolutely. Yeah. And, and, and that's, that's the thing about, software estimation is, on a, on a task level even is, is, you know, not impossible, but like, what's the point?

[00:40:05] **Ben:** Right.

[00:40:06] **Brian Sadler:** You know? and you can, there's lots of techniques for averaging out the, you know, the, the differences in, in, you know, if you've got a hundred tasks and you know, you make an estimate and everything.

[00:40:17] **Brian Sadler:** To narrow a range of possible, estimates and, you know, the state of the art is kind of using probabilistic forecasting and Monte Carlo methods based on your cycle times, Kanban boards and stuff like that. So that's probably the easiest and lowest effort way of doing it, but, it's, it's more of a dysfunctionality of how.

[00:40:36] **Brian Sadler:** The regime is organized if people are being questioned around, well, you said it was a three story pointer and that's taken two days, you know, you're, you're, you're in the bad books. Come on, that's, that's just ridiculous. Uh, you know, the, the, the kind of, I wouldn't say it's standing up, but kind of modern thinking is, is around right sizing work.

[00:40:54] **Brian Sadler:** So you can, when you're, when you're bringing. Work into the team, the team say, right. And it came all out at cycle time or 80 percent of our work goes from left to right on our camera and board or JIRA board, whatever in, in a week, say, you know, it goes through all the phases of planning and development review.

[00:41:11] **Brian Sadler:** Testing, et cetera. so it's 80 percent of our work gets done in a week. That should be, or, you know, five working days. Then that should be the cutoff for accepting any new work because we don't want to increase our cycle. so if anything looks like it'll be longer than five days, it's too big to be done in one task.

[00:41:25] **Brian Sadler:** It needs to be split up. You keep doing that, your cycle time goes down, your flow should be maintained. And when you get together in the morning, you're looking for blockers and looking for work that's sort of going stale and taking a long time to do. You end up with a nice. Semi predictable flow of work.

[00:41:43] **Brian Sadler:** And from there you can start making projections about, well, we got, you know, our throughput is, you know, sort of 10 tickets a week. We've got a hundred tickets in the backlog to get this initiative finished. You know, that means we'll be done in 10 weeks ish. We can give, you know, dependent on the variation, you know, we can, run some simulations and, and give a tolerance either side. And then we get to the question of who wants the estimates and why typically. We, you know, we, we, we can't really escape that as development teams, as much as we want. I know there's a, there's a big, no estimates movement online, but, there's always a case stakeholders, people putting the money up, want to know. A, going to be take longer than feature B. Because that's an important decision to kind of get right if we can, because provided they've got the same value, you want to do the one that's going to take the shortest amount of time, clearly. So, so it's, it's to inform business decisions. So we do need to actually go through, you know, to, to be professional about it, I think.

[00:42:40] **Brian Sadler:** And to actually have some means of estimating and that makes sense. And it's got some rationality behind it, but, you know, that's all it should be made for is for forecasting. It shouldn't be about, you know, assessing performance or uses a stick to punish people ever in my view. Again, that's kind of in line with agile thinking.

[00:42:57] **Brian Sadler:** It's merely about forecasting and forget it, move on. you know, and the other side as well as that. So much of the work that we do in estimation and that we've been forced to do as developers in estimation, the flip side of the coin is that it's the value of the work that's actually way more important and very little work goes into estimating the value of the feature before we might start working on it.

[00:43:18] **Brian Sadler:** so, you know, on the right thing is around, trying to estimate how valuable something can be. And again, that is hard and it's, it requires you to predict and the old saying prediction is hard, especially about the future, but there are, there are means by which you can try to get a handle on the prospective value of something, and that's why, you know, your business analysts and your finance team in your companies, if you've got them.

[00:43:44] **Brian Sadler:** They should be able to help say, right, identify what's the most important thing in the backlog to work on. And typically if you look at a backlog, you know, there's, there's, sort of studies that say, you know, two, two thirds of, of, of functionality that, that, I mean, systems hardly ever get used. A third never gets used.

[00:44:00] **Brian Sadler:** One third gets used very rarely. It's only a third that people really care about and use frequently. So that's two thirds of the work we do is a waste of time anyway. So figure out the one third drop, the two thirds that's not of value and, you know, move on. you know, the, the analogy as well about sort of, you know, record companies financing the recording of albums by rock bands and stuff, and they kind of use the model of just throw enough money at the wall and one of them will be hit, pay for the rest.

[00:44:28] **Brian Sadler:** And they don't really know what's going to be a hit. So that's why they kind of, everyone thinks they've got ears, but I don't really care too much about controlling costs. I mean, they do to an extent, but not that much. So, you know, it's, it's not like they're going in and saying, well, you spent 15 minutes more in the studio today than you should have done and.

[00:44:46] **Brian Sadler:** And, you know, and, in, in, in, you know, in essence, mature software development firms have worked that out and just gone, yeah, we employed people, the money's going out every month in salaries anyway. you know, it's kind of a sunk cost. Our job is to make sure we give them valuable things to work.

[00:45:01] **Carol:** I love that. That sounds perfect.

[00:45:03] **Brian Sadler:** Good. Glad someone's happy.

## [00:45:07] Value and Prioritization

[00:45:07] **Ben:** I was going to say, one of the most frustrating patterns that we've fallen into at work from time to time is the product team will say, Hey, we've got this idea for. A big module, for lack of a better term, how long will this take to build? And we'll say, that looks like it'll take seven weeks.

[00:45:23] **Ben:** And they're like, okay, what if we take out feature A, how long will that take? And we're like, I don't know, nine weeks. And then they're like, what if we put feature A back in, but we take out features B and D, how long will that take? And it becomes this multi day conversation about how do we tweak this just so, so that the estimate perfectly lines up with the timeline and it all just seems so futile, because to your.

[00:45:47] **Ben:** You know, as you said earlier, we're not good at estimating to begin with.

[00:45:50] **Carol:** Right.

[00:45:52] **Brian Sadler:** it's interesting, Tyler, and the retort should be, how do you know this will make any money? And, and, and why should, why should I, why should I, why should I do that?

[00:46:07] **Ben:** Oh

[00:46:07] **Ben:** my God.

[00:46:08] **Brian Sadler:** divert our attention away from, from the valuable work that we're currently doing to talk about this nebulous idea that you've got, because the work I have, I'm doing right now, we think is valuable to the tune of, you know, X thousands a month.

[00:46:22] **Brian Sadler:** And you're asking us to stop working on that and go dive into planning and estimation on something that you've done no work on in terms of Because that they will have done no work on it. They, they'll have done no work on assessing whether that's got any value. So, you know, that's, that's kind of my retort usually expressed in more diplomatic terms than, than I just did now.

[00:46:41] **Brian Sadler:** But, you know, the, the, the effort should be at, be at least equivalent in terms of working out what the cost is and what the, the, the, the value or the return on that, that investment is gonna be, it's, it's, you know, as you say, the, the word futile, Ben, I think is, is absolutely right in these conversations.

[00:46:56] **Brian Sadler:** It's a waste of everyone's time.

[00:46:58] **Adam:** Is it naive to maybe try to respond to that question or that, those, those prompts in that situation by saying, tell me what timeline you want and put the tasks in priority order and we will work from most important to least, and we will stop when time is up. Is that too naive or is,

[00:47:19] **Brian Sadler:** No, it's the only, it's the only way that there is no alternative. I mean, one of the, the, the, the kind of the biggest thing in that sort of area about around looking for value is this thing called cost of delay, which, you know, I spend, I spent a while trying to convince executives that this is really important.

[00:47:34] **Brian Sadler:** You need to focus on this and this alone. but, the, the naivety is that, people are people and especially at the executive level, they're, you know, they have their own pet projects. Things that they want to do and they're not really interested in, you know, some agile person telling them they should go away and, and look at, you know, analyze the financial benefits.

[00:47:52] **Brian Sadler:** But cost of delay is a key term in terms of, you know, there's, in essence, it's if we, if for For every period of time that we're late delivering this, how much money do we lose? and if you work that out, then for each feature that's on your backlog, then you quickly come to a realization, which ones are the most important.

[00:48:09] **Brian Sadler:** And again, you're predicting the future. It's subjective. You've got to do some fuzzy logic and stuff to actually come up with a value. But, you know, that maybe in August, something that's. Aiming to hit the Christmas market that needs to be out in October before, you know, certainly, certainly before, you know, thanks just after Thanksgiving in order to get that, you know, hit that Christmas market.

[00:48:30] **Brian Sadler:** And if it doesn't, then it's worthless. No point putting out in January. So, you know, these questions around how much is it worth to the company or your employer? Generally, that's what we will work for, you know, how much is it worth? They're the things that should decide what's the most important thing and therefore.

[00:48:45] **Brian Sadler:** How your priorities are and limit the amount of things you work on in one, in one go. So as great at starting, but we should stop starting and start finishing, limit the work in progress, work on the most important things, get them done. As soon as you get them done, you realize the value. If you don't get them half, half finished work, you know, there's no value in that.

[00:49:02] **Brian Sadler:** It's just a factory. It's just stock piled up in a factory.

## [00:49:07] Team Priorities

[00:49:07] **Carol:** So talking about work, one thing I've struggled with at multiple companies is the concept of sprints. And, we can't get any more work in because we've committed to this in, in work. Work that's in the sprint. But yeah, customers come in with demands and things change and they have urgent, you know, priorities, they have compliance, they have things that have to be resolved.

[00:49:30] **Carol:** But then I've seen companies push back and go, no, we're agile. Our team has committed to this sprint. Your work will now go out in three months. You should have told us about this, you know, three months ago to get it in this sprint. And that's always frustrated me. Cause I feel like. The approach should be do what is the need for your customer and there has to be some give and take.

[00:49:52] **Carol:** So they have to agree to pull something out of the sprint and put something else in. Like there has to be some flexibility or your software loses reliability in the market. And that just, it doesn't add up to me.

[00:50:05] **Brian Sadler:** Yeah, it's a, a scrum isn't great at, you know, what do you do with urgent support requests or, or bug fixes or hop fixes when you've committed, to, delivering a bunch of work in the sprint. pragmatism, I think is the answer, you know, if you know, The recent history suggests that you will get urgent requests from customers and, and there is a commercial imperative for your company to, to meet the needs of those customers, you know, because if there isn't, then don't bother.

[00:50:33] **Brian Sadler:** But, if there is, then, you know, you, you know, one in one out, you know, alter the sprint goal, cancel the sprint, you know, and do whatever is needed to actually do the most important work. if. If support, urgent support is taking up a large proportion of the time as a team, then probably Scrum isn't for you and maybe Kanban is better.

[00:50:52] **Brian Sadler:** In fact, David Anderson, who was a guy who originally kind of worked with Kanban in Microsoft, he was working with a team who had, you know, kind of different, different streams of work coming in at them. Some of it was development, some of it was support. and having, using Kanban was a better solution because then there wasn't this expectation that, you know, in this.

[00:51:10] **Brian Sadler:** Say two weeks, sprint, we'll have accomplished this goal. Or we'll have delivered so many story points. And, you know, we we're committed to that and it's fixed forever. We're on two week death March. You know, the requirements ain't gonna change. that I think is, is, is one of the weaknesses of Scrum that, you know, we, we start to, we start to think about, oh, we should be good at Scrum rather than we should be good at, you know, software development and meeting the needs of our customers and stakeholders.

[00:51:36] **Carol:** There's a fine line we walk sometimes.

[00:51:38] **Brian Sadler:** Indeed.

[00:51:39] **Ben:** I have found that somewhat of an antidote for that kind of a mentality is to cut down on the distance between the support team and the product engineers. And I'm not saying that the product engineers should do rotations on the support team, although I know that some companies do that. I find that if you have a closer bond to the support people, they can give you That perspective, you know, you're locked into your agile scrum mindset and the support people say, Hey, we have this urgent ticket.

[00:52:09] **Ben:** This button's not working. And it's easy as, as an engineer or as a manager to be detached from that and say, well, we have this thing we have to deliver and the support people, if you can communicate with them, can turn around and say, yes, but this contract is worth 300, 000, so I don't really care what's on your Kanban board.

[00:52:27] **Ben:** You have to do this ticket. And I think that there's something very healthy about that. You can of course, push back, but I, I think. As companies grow, sometimes the, the, the boundaries between the customer facing teams and the non customer facing teams, it becomes too, too rigid. And I think we lose a lot of the nuance in how work has to be prioritized.

[00:52:50] **Brian Sadler:** Yeah, absolutely. You know, I think the, uh, you know, bringing development teams closer to the customer, the end user and stakeholders is, is really important because then they, they can start to make some of these trade off decisions themselves without being told. and, you know, one of the, one of the things that, kind of frustrates me as an attitude within the development community from time to time, you see, which is, Oh, just leave me alone.

[00:53:12] **Brian Sadler:** I want to play with the ones and zeros. And, you know, and it's like, we all work in a context. We all get paid. If you want to just work in ones and zeros, that's, that's your free team. You know, you do it in the summer holidays or your weekend or whatever, and you can do what the hell you like, you know, but if you're, if you're taking a paycheck, someone's paying you for a reason, we work and we develop code.

[00:53:33] **Brian Sadler:** To, in order to provide solutions for users for a reason, therefore I think we have a professional duty to be as close as possible to the, you know, it's the end user and the stakeholders so that we're meeting the needs, not to be sort of expect to be safeguarded from having to deal with, you know, the great unmoshed, if you like. It's, know, because essentially that's that, you know, what, there's a guy, Jeff Patton, he talks about user story mapping and he does this great talk about, you know, what is our job? Is it to write code or, and it's, and he says, no, it's to change the world. And it's to the corner of the world where our users live and use our software.

[00:54:10] **Brian Sadler:** You know, that's what we're here for. And, you know, If we've got users, stakeholders that, give us a lot of money, pay our wages, give us a nice, comfortable lifestyle for playing with computers all day long. If they've got a problem every now and again, we might just want to pay attention to see if they're all right.

## [00:54:26] Enthusiasm

[00:54:26] **Adam:** So as we, I kind of want to shift the focus of the conversation a little bit here. we've spent a lot of time talking about, I don't know, maybe how our various experiences are, are a poor excuse for Agile. what about somebody who has had these negative experiences and came away from it thinking all of Agile is wrong and bad and a waste of time?

[00:54:52] **Adam:** Do you have like a, a story in your back pocket that you typically will tell? Or, you know, something to Is there, is there worth in trying to convince somebody that Agile is worth the effort? Or, you know, is there, is it the opposite that's true? That it's like, well, if you've already made up your mind, then there's no point in trying to convince you.

[00:55:13] **Brian Sadler:** not, not, not so much. I mean, I think that the, the typical way that you, you try to bring about change is you work with the willing. so, you know, it's, it's. There's enough effort in that for people who are change agents, it's a horrible term,

[00:55:27] **Adam:** No, I love it.

[00:55:28] **Brian Sadler:** and stuff. you know, you, you, you're trying to convince people to do what they want to do for their own good anyway.

[00:55:32] **Brian Sadler:** But, you know, it's, it's hard enough for people who are enthusiastic and to keep them on track and to keep them motivated, nevermind working with people who don't, they just don't want to know, but the best, The best sort of way of promoting change is to, to have good exemplars nearby. So, you know, in a, in a large organization with multiple teams, then, you know, if you were bringing it about, you would, one, you'd look for, for, for, from buy in and support from above so that, you know, they, they're not going to kill the initiative.

[00:55:59] **Brian Sadler:** either deliberately or inadvertently. but you know, you look for a team that's enthusiastic and generally a team that's enthusiastic will start to make waves when, you know, they're happier, they feel they're being more productive, they get pats on the back. And then the naysayers sort of, or, you know, the.

[00:56:14] **Brian Sadler:** The second way people look around and go, Oh, I want to be on that team. Well, can we do what they're doing? and you know, you kind of divide and conquer and eventually the naysayers are in a corner by themselves. I suppose I have to try this. but it's, it's, it's not something. You know, the whole point of Agile is, I think as well, is that it's about, respect for the people doing the work.

[00:56:34] **Brian Sadler:** Some people don't want to know about Agile or change. you know, and that's perfectly fine. but there'll usually in any organization, there'll be plenty of people who do want it and, they should serve as exemplars of it. Ideally, as time goes on and they prove it's worthwhile and successful. I don't have a magic wand to wave to convert people,

[00:56:55] **Adam:** Oh, but if we did, converting people is out, but what about somebody who's like, okay, I'm willing to give it a chance, but the, the stuff I've heard of or the stuff I've seen is too prescriptive or, or if maybe it's the right amount of prescriptive, but it just doesn't fit my company. Like, is there a softer on ramp to, to try and like get people hooked?

[00:57:22] **Brian Sadler:** Yeah, I think I'd start with Kanban if you, if you're really resistant, because Kanban is, is, is just not at all prescriptive. You know, all it is, is, you know, I think there's, there's 12 things it says and they're, they're, You know, like, you know, start where we are, visualize your workflow, optimize the flow of work.

[00:57:41] **Brian Sadler:** there's a few others I can't remember off the top of my head, but it's,

[00:57:43] **Adam:** Limit work in progress. Yeah.

[00:57:45] **Brian Sadler:** yeah. you know, like Scrum says, you know, we have time boxes and that's how we limit work in progress. Kanban actually says, no, just don't work on too many things at once as a team. and, the people who've heard naysayers have been around a while and they, they kind of, you know, if they know their chops and they'll take kindly to Kanban and it's, it's absolutely fine.

[00:58:03] **Brian Sadler:** but you know, we're, we're kind of very neuro, neuro diverse industry. There's lots of different, viewpoints and that's okay. And some people will just. Do genuinely want to be left alone and they don't want interaction and they don't want to speak to the customer or the users and, you know, sometimes that's all right, you know, we can find a way to work around that.

[00:58:23] **Brian Sadler:** Valuable in producing the goods.

[00:58:25] **Adam:** Can I, can I delegate that interaction? Can I just like have an assistant that does all the agile stuff for me and I just do the programming?

[00:58:33] **Brian Sadler:** Be careful what you wish for. but yeah, I mean, like again, you know, some other people who've been involved in Agile might, might have different views on that, but for me, it's, it's people centric. If the people decide that they don't want to work in Agile, then that's. Okay, if they can still keep the stakeholders happy and informed and radiate information about the state of the work and progress, then that's great.

[00:58:54] **Brian Sadler:** but I think if they just reach into the Agile bag of tricks and tools, then it would be probably easier for them, really. You know, I think that people who don't use or actively, actively run away from the techniques and practices in Agile, I think there's almost certainly going to be some sort of dysfunction.

## [00:59:14] Retrospectives

[00:59:14] **Ben:** Let me ask, go off in a different direction for a second just cause I know we're, we're over an hour now, but, we, we started the conversation talking about retrospectives and I wanted to circle back to that for a moment because I have. Narrow feelings, and I'll, and I'll freely admit that these are possibly wrong, but when it comes to retrospectives, I find that a lot of people want to focus on the good things that we did.

[00:59:40] **Ben:** And for whatever reason, however, I'm wired, I have no interest in talking about all the things that went right. Like, I just want to spend the hour talking about all the things that went wrong and all the ways that the process is terrible and all the things that we should fix. And am I just, am I just a jerk or, or is like, I, you know, is there a value

[01:00:00] **Ben:** add in talking about the things that are good?

[01:00:03] **Ben:** Or is that just sort of patting each other on the back?

[01:00:06] **Carol:** Like, I feel like you need to praise the people on your team who've done great things, and this is a good open forum to praise those people who don't get enough, like, reward for what they're doing. So, go do the good things first. So, plus, you're in a good mood smiling at that point when you start tearing them apart in the next step.

[01:00:25] **Ben:** that's, that's fair. I think I just get so angsty because there's so much to complain about and such a little amount of time. Like get all that positive stuff out of the way so we can start,

[01:00:37] **Carol:** You need longer retros, man. Yeah.

[01:00:40] **Brian Sadler:** Longer retros, more

[01:00:41] **Ben:** yeah, I wish that was the problem, not, not the sheer amount of stuff to complain about.

[01:00:49] **Brian Sadler:** There's nothing, there's nothing wrong with, with,people mentioning positive things and praising each other in a retrospective. one, everyone likes praise and, and, you know, and I think it's nice that it, it, it, it's good for us to praise other people when they genuinely deserve it, I mean, one of the things I do is, I try to just keep a little notepad of retro items, as things go through the, the, you know, the.

[01:01:10] **Brian Sadler:** The cycle and, you know, if I have a couple of nice things to say about stuff, then stuff that's happened or, you know, people have made a contribution, then that's great. and it kind of primes us to be able to,you know, as Carol sort of hinted at, it's a bit of a head fake. So, you know, it's the old one, two of, you know, on the one hand, the Lord give us and the Lord take it away.

[01:01:29] **Brian Sadler:** It's a great job, but, you know, this stuff we've got to look at. but, but as well, there are, there are times with, about the ways of working that you might be doing something that needs to be called out because you want to retain it and reinforce it. and sometimes we, we gloss over the things that are working well, and we just have a glass half empty mentality and everything should be perfect, isn't perfect as, you know, horrendous and we go into criticism mode, but, it's good to balance the positive and the negative.

[01:01:54] **Ben:** All right. So I'm hearing that I'm a jerk and that's fine. I can take that criticism.

[01:01:59] **Brian Sadler:** No one, no one said that

[01:02:00] **Ben:** I, you know, I think

[01:02:01] **Carol:** all said that. We all said it. It's fine.

[01:02:06] **Ben:** you know, I think it's one of those things where you just. In the same way that I talked about how we started to treat the daily standup as the, I've had thoughts over the last 24 hours, and now this is my opportunity to brainstorm, I think the retrospective for me has always been, all of this stuff has been boiling below the surface for the last two weeks.

[01:02:25] **Ben:** And now this is my moment to just puke it all out. And so I think, I, I, I, I love to praise people. I certainly love to be praised. I don't want to. I always just felt like maybe the retro wasn't the right time for that. Maybe that should, there should be some other mechanism for that. but again, like I said, I have, I have very narrow view here and I'm, and I'm fully willing to admit that I am wrong.

[01:02:49] **Brian Sadler:** And I think the thing with the retro is that, that isn't the, you know, you said that there should be another mechanism. We'll make another mechanism. That's, that's all. Cool, like the retro isn't the exclusive

[01:02:59] **Ben:** Right. Right.

[01:03:00] **Brian Sadler:** time when you raise points or you praise or you deep dive into issues. You know, the retro is there in a calendar so it's guaranteed to happen because again for some teams it'll never happen unless you schedule it and put it in the calendar and that's what we're trying to safeguard is to have a deliberate attempt on a regular basis to deep dive into.

[01:03:20] **Brian Sadler:** You know, what's working well and what is, what needs to improve and make and take, appropriate steps. You know, before we did these retro stuff, you know, I could have been in an organization for years and no conversations about improvement would happen, nevermind any actions. And that's not a great place to be.

[01:03:38] **Ben:** Yeah. I mean, to be clear, I love retros. I, it, it is many times my favorite meeting of the, of the cycle, so.

[01:03:44] **Brian Sadler:** Great stuff.

[01:03:45] **Adam:** All right. Well, it sounds like a good place to wrap it. Brian, if people want to keep chatting with you, talk more about Agile, where can they find you?

[01:03:53] **Brian Sadler:** they can find me on Twitter. I'm, I think I'm Brian underscore Sadler. I'm on LinkedIn as Brian Sadler and Agile will probably bring me up in London. And, email, you can email me at brian. sadler at gmail. com.

[01:04:06] **Brian Sadler:** And we'll put, we'll make sure we get all that into our show notes as well. so thank you, of course, Brian, for coming on and having this chat with us. It was very, entertaining as well as informative and, and, just, it's been a pleasure. Likewise.

[01:04:21] **Adam:** Thank you. so we are going to go do the after show. Brian, are you able to stick around and hang out with us?

[01:04:26] **Adam:** I know it's kind of late there in London. Excellent.

[01:04:28] **Adam:** We'll get you tipsy and, and, spill the beans.

## [01:04:32] Patreon

[01:04:32] **Adam:** okay, well then, this episode of Working Code is brought to you by my new startup. I guess I got to have one every week. Adam's Agile Assistants and Associates, will go to your stand up for you. listeners like you, if you're enjoying the show and you want to make sure that we can keep putting more of whatever this is out into the universe, then you should consider supporting us on Patreon.

[01:04:51] **Adam:** Our patrons cover our recording, editing, and transcription costs. And we couldn't do this every week without them. Special thanks to our top patrons, Monte and Giancarlo.

## [01:04:59] Thanks For Listening!

[01:04:59] **Adam:** You guys rock. if you'd like to help us out, you can go to patreon.com/workingcodepod and benefits of that include early access.

[01:05:07] **Adam:** To new episodes and after show and, Oh, we have like some special discord stuff too, right? So we have like a patron only channels in our discord and it's been a while since we've done a game, game night. We should try to get one of those on the

[01:05:20] **Carol:** We should. That'd be fun. Yeah.

[01:05:24] **Adam:** All great reasons to hook us up and help us out and join the community.

[01:05:28] **Adam:** Speaking of join the community, if you want to just come hang out with us, no, no charge whatsoever. you can go to workingcode.dev/discord and join our discord community. It's like Slack, but better. and I think that's it. You know, honestly, it's been a while since I've asked, so I'm going to say it.

[01:05:42] **Adam:** we could really use, your re your ratings and your reviews on iTunes, wherever you go. You can go to workingcode.dev/review, and it'll take you to, the Apple Store or the iTunes podcasts thingamajiggy. in your local language and, and, region, and you can leave us a review. Five stars only, of course.

[01:06:00] **Adam:** It's still broken. You can only do five stars, sorry. But, you know. That's not on us to fix, it's on them to fix. So that's gonna do it for us this week, we'll catch you next week, and until then,

[01:06:09] **Ben:** remember folks, your heart matters, even if you follow Scrum.
