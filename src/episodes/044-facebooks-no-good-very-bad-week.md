---
title: "044: Facebook's No Good Very Bad Week"
description: ""
date: 2021-10-13
---

<iframe allow="autoplay *; encrypted-media *; fullscreen *" frameborder="0" height="175" style="width:100%;max-width:900px;overflow:hidden;background:transparent;" sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-storage-access-by-user-activation allow-top-navigation-by-user-activation" src="https://embed.podcasts.apple.com/us/podcast/044-facebooks-no-good-very-bad-week/id1544142288?i=1000538445325"></iframe>

Between Frances Haugen's testimony, a mega outage of Facebook properties including Facebook.com, Instagram, and What's App, and a $7 billion drop in Mark Zuckerberg's personal wealth in a matter of hours, it's safe to say that Facebook has been having a terrible, horrible, no good, very bad time of it. There have even been rumors that Facebook's "work from home" policy is being rescinded; though, such claims have been denied by the company. Today, the crew talks about everything that's going on in the Facebook universe. And, Tim shares his own harrowing experience with Border Gateway Protocol (BGP) catastrophes and why Facebook's networking woes were a little too triggering for his own comfort.

## Notes &amp; Links

-  [Gone in Minutes, Out for Hours: Outage Shakes Facebook](https://www.nytimes.com/2021/10/04/technology/facebook-down.html)
-  [Here are 4 key points from the Facebook whistleblower's testimony on Capitol Hill](https://www.npr.org/2021/10/05/1043377310/facebook-whistleblower-frances-haugen-congress)
-  [Zuckerberg loses $7 billion over Facebook outage; Telegram, Signal gain](https://www.business-standard.com/article/technology/zuckerberg-loses-7-billion-over-facebook-outage-telegram-signal-gain-121100501493_1.html)
-  [Facebook denies end to 'WFH forever' rule in wake of mega outage](https://www.techradar.com/uk/news/facebook-ends-wfh-forever-rule-after-mega-outage)
-  [DNS - Domain Name System](https://en.wikipedia.org/wiki/Domain_Name_System)
-  [BGP - Border Gateway Protocol](https://en.wikipedia.org/wiki/Border_Gateway_Protocol)
-  [DynDNS](https://account.dyn.com/)

Follow the show! Our website is [workingcode.dev][working-code] and we're [@WorkingCodePod on Twitter][working-code-twitter] and [Instagram][working-code-instagram]. Or, leave us a message at (512) 253-2633‬ (that's 512-253-**CODE**). New episodes drop weekly on Wednesday.

And, if you're **feeling the love**, [support us on Patreon][working-code-patreon].

With audio editing and engineering by [ZCross Media][editor].

[working-code]: https://workingcode.dev/
[working-code-instagram]: https://www.instagram.com/workingcodepod/
[working-code-patreon]: https://www.patreon.com/workingcodepod
[working-code-twitter]: https://twitter.com/WorkingCodePod
[editor]: https://www.zcross.media/
[github]: https://github.com/WorkingCodePod/workingcode/blob/main/src/episodes/044-facebooks-no-good-very-bad-week.md

---

# Transcript

[Spot an error? Send a pull request on GitHub.][github]

[00:00:00] **Ben:** do you think someone's getting fired over this or is this a teachable moment?

[00:00:06] **Ben:** I saw somebody say something that the downtime for Facebook ended up costing them, like in the billions of

[00:00:14] **Carol:** at least it happened during the day. People didn't get paged in the middle of the night.

[00:00:17] **Adam:** I mean,

[00:00:19] **Adam:** I'm sure you

[00:00:20] **Adam:** know what?

[00:00:20] **Ben:** I'm saying that the face it's not like the Facebook stuff got messed up, doing some sort of 2:00 AM shift and people had to be woken up. I mean,

[00:00:28] **Carol:** And I mean, it was somewhere

[00:00:30] **Adam:** It was absolutely. But I think that for,from the perspective of the management and the bookkeepers at Facebook, they will, I'm sure they would have rather had gone down at 2:00 AM. Right.

[00:00:41] **Tim:** I am north American time. Yeah.

[00:00:43] **Adam:** Yeah. Because they potentially lost billions from it being down.

[00:00:46] **Adam:** I wasn't like six hours, eight hours, something like that.

[00:00:48] **Ben:** I see, so you value $7 billion more than

[00:00:51] **Ben:** people's sleep, whatever.

[00:00:54] **Adam:** I'm saying there is somebody somewhere, whether it's Zuckerberg or whatever, his minions that are going, I wish that would have happened at 2:00 AM. Yeah. Okay. and I absolutely have sympathy for the people that have to get up at 2:00 AM to deal with something like that.

[00:01:08] **Tim:** but I mean, you know what? It makes me feel good when the big guys fall down because it's like, yeah. no one has a hundred percent of this stuff figured out it's a very massive complex system. And the fact that it works as well as it does is a miracle.

## [00:01:39] Intro

[00:01:39] **Adam:** Okay. Here we go. It is show number 44. And on today's episode, we're going to talk about Facebook's no good, very bad week. but first as usual, we're gonna start with our triumphs and fails. And Carol, you get to go for.

## [00:01:49] Carol's Recovery

[00:01:49] **Carol:** Yay. I don't have like a big triumph or a failure. I'm things are just going, okay. Things are going good. my kid got really sick a couple of weeks ago, gave it to me. I'm recovering from a, I was on my butt. Not going to lie. It kicked my butt again. I didn't have, COVID just like bronchitis, still all congested, lots of coughing, but the things are just really good.

[00:02:12] **Carol:** Like it's good that I can get sick and just recover and go back to work. And I don't have like this giant pile of work waiting on me when I get back. It's just, things are just good. My family is good. Work's good.

[00:02:27] **Adam:** check your baseline healthy privilege.

[00:02:29] **Carol:** know. I know it's I just don't know how to say it. I'm things are okay.

[00:02:35] **Carol:** And I'm okay with that.

[00:02:36] **Carol:** Yeah.

[00:02:36] **Adam:** That's really

[00:02:36] **Tim:** to hear.

[00:02:37] **Carol:** Yep. Nope. All right. That's all for me,

## [00:02:39] Adam's Triumph

[00:02:39] **Carol:** Adam.

[00:02:40] **Adam:** I'll go next. I am back on the testing horse, a while back, I put in this big effort to, get better at testing. And, or as I've been saying it lately, suck less at testing. And,I had some success, but I wasn't able to stay in it for long enough to really get my, my flywheel going as I like to say.

[00:03:00] **Adam:** and, I'm back in it. And, I feel like. The flywheel hadn't completely stopped. Right. I was sort of able to pick up, or I left off a little bit, put a little bit of energy back into it and keep it going again. I've learned more about mocking and that's going really well. I feel like in some ways maybe that break from it was beneficial, right?

[00:03:18] **Adam:** Like, how you work on a problem for long enough, it just becomes a thing where the problem is now sort of beating you and you need to walk away for a little while,and come back to it. And then you see it with fresh eyes and you'd do better. It's been kind of a similar situation with testing for me, especially mocking, I thought I understood the mocking tools ingest and, I was doing okay.

[00:03:38] **Adam:** But then every it's like every time things changed, even just the tiniest little amount in structure or whatever, I would have to sort of stop and relearn mocking all over again. It was really. A couple of weeks away and back on it for a couple of days now, and I'm really enjoying it and doing great.

[00:03:55] **Adam:** And in addition to that, you guys know how much I like new stuff and getting excited about new technology.

[00:04:00] **Adam:** last week I mentioned that I'd kind of been starting to play with spelt and it looks really interesting and really interested. It's still really early on the adoption curve. So I don't think it's something that I would recommend to my company or to yours, unless your risk tolerance is really high or you would prefer to put your innovation tokens there.

[00:04:20] **Adam:** We've talked about that a little bit before. but it's still really interesting. And I think my approach is going to be to play with that in personal stuff and then kind of keep it on my radar so that when it becomes really mature and a good option, I can be like, okay, now's the time let's do this in our company.

[00:04:34] **Ben:** and, in addition to spell, I've also started playing with tailwind. Now I think tailwind is way more mature and definitely recommendable. If you're not familiar with that, tailwind is a, oh, how do I describe it? I would say. class.

[00:04:45] **Adam:** yeah, well, so it's about utility classes, but the thing that really made it click for me and like, why is it awesome?

[00:04:52] **Adam:** It's not just like a CSS file that has a bunch of utility classes in it. It's really kind of a JavaScript library that allows you, or gives you tooling to create your own like CSS components, like style guides, sort of situations like build your own bootstrap. Right. And what it does is, you give it,your colors or whatever, and you can set like a baseline font size where everything and everything is sort of based on that.

[00:05:16] **Adam:** And so like your H one H two H three H five are all sort of relatively sized from that, so that you get good differentiation and you know what I mean? Like it's just, I don't know well enough to really try and like advocate for it here, but I was super, super impressed with it. and I'm definitely going to continue to learn about it.

[00:05:37] **Adam:** As you can tell from this last minute of me talking nonstop, I'm pretty hyped on it. And yeah, that's a triumphant thing for me.

[00:05:46] **Ben:** Yeah. People seem to really love tailwind. I have not tried it yet, but the people at work that I've talked to that have used, it was swear by it.

[00:05:55] **Adam:** Yeah. And it's funny because when somebody says to you, oh, it's a utility class thing. It sounds so dirty. Right. You're like, oh, you just add, like, instead of even just putting the style tag on your div to say, oh, add a margin, that's this much,you just add a class name that you have to go look up for the same amount of margin.

[00:06:11] **Adam:** Right? Like that sounds dirty, but that's not what it is really at all. I mean, it kind of is, but it also isn't. And I'm just gonna say you have to go look it up. There's a course for it on egghead that I found really good. A couple of courses for it on that good diode that I found really interesting and helpful in that regard.

[00:06:27] **Adam:** But.

[00:06:28] **Carol:** So you mentioned your jest and mocking, right? So, over this past week, I. And to my YouTube history to try to find something. And I got laughed at, because my researches are like,Jess mocking with Jess, because I like to just turn on videos in the background. Right. And I was just like watching random things and yeah, I totally got laughed at with my life history and YouTube.

[00:06:50] **Carol:** And I was

[00:06:51] **Adam:** By your children or by like

[00:06:52] **Carol:** no, by a friend. Yeah. I was like, you've nerd.

[00:06:55] **Adam:** Yeah. Okay.

[00:06:56] **Tim:** Is that really a friend,

[00:06:58] **Carol:** Probably not.

[00:07:00] **Adam:** That's how you can tell the acquaintances from the real friends, what your friends are. We'll make fun of you.

[00:07:05] **Tim:** right?

[00:07:07] **Adam:** At least. That's what I tell myself so that I feel like you guys are my friends.

[00:07:10] **Tim:** Yay. We are.

[00:07:12] **Carol:** We love you.

[00:07:13] **Tim:** That's why we pick on you so bad.

[00:07:15] **Adam:** Exactly. All right. That's enough of my babble. Ben, what do you got going on here?

## [00:07:20] Ben's Failure

[00:07:20] **Ben:** I'm going to go with a failure and I'm going to have trouble wording this, but essentially somebody says something to me at work that got under my skin way more than it should have. And it was something to the effect of, it was suggested that I look into something beyond what was my quote, unquote day-to-day. feel like the quoting of day job, the whole thing made me feel like what I do at work is not respected. And that somehow I'm one of these people who just shows up to work and punches their card. And that's it, which I don't think is necessarily a bad thing to begin with. There are people who work like that's fine, but that's, it's not how I work.

[00:08:05] **Ben:** Like at the end of my day, I stopped typing, but the work comes with me and I'm thinking about it all the time. And when I'm not thinking about work stuff specifically, I'm thinking about programming stuff. And it's just this constant process in my mind when I'm walking the dog, when I'm showering, when I'm laying down in bed, I'm going over problems.

[00:08:24] **Ben:** I'm thinking about picking things apart. And there's no reason that I should doubt the effort that I put into my. And the fact that somebody said something that made me feel angry, probably because it also made me feel guilty. It's just so disappointing in myself that

[00:08:44] **Adam:** Oh, because you let it get to you.

[00:08:45] **Ben:** it should be one of those things where I should just, whip my hair and,and,

[00:08:48] **Adam:** Emo kid whip your

[00:08:49] **Ben:** yeah, and it should just roll off my back, but I think I have so much insecurity.

[00:08:56] **Ben:** I have so much deep seated insecurity about how I'm perceived at work. I think that these little stupid comments get to me,

[00:09:04] **Adam:** What's this. So was this more about like technique and understanding of general concepts? Or was this more about choice of tooling?

[00:09:15] **Ben:** the intonation. Of the conversation was such that I am at work perceived as I'm. I am perceived as doing a lot of experimental R and D stuff, like I just research a lot of stuff and I'm playing constantly with Lucy, with CSS, with JavaScript, I'm just trying stuff. And the tone of the conversation was such that, Hey, maybe you should take some of that experimentation time and do something more useful for the company, which I do all that stuff in my free time. But all of that stuff ends up getting funneled back into the company anyway, because I'm experimenting with stuff that's been sparked by stuff I've been doing at work. And then the stuff that I do in my experimental time ends up influencing the way that I'm building stuff at work or changes the way that I want to put things together.

[00:10:06] **Ben:** So it's this just holistic exploration of code. All the time and the moment that anyone points at that and diminishes it by saying maybe I should be working on something more important. It just,

[00:10:22] **Adam:** that

[00:10:22] **Adam:** sucks. I mean, this is at its core. I think it's an interpersonal issue. And whether that's, on a larger scale or like a one-on-one sort of thing, I think so many problems work and outside of work, boiled down to communication issues, basically like being able to other people complexly, right. It's so easy to put somebody in a box, whether or not they actually fit in that box or whatever. and once you put somebody in a box, that's how you think of them

[00:10:54] **Ben:** Yeah,

[00:10:55] **Tim:** At a box.

[00:10:57] **Ben:** what's in the box.

[00:10:59] **Adam:** oh God. To do you move your references in a row without even like a sentence between them.

[00:11:03] **Tim:** I know, right? It's a portmanteau of memes.

[00:11:06] **Ben:** Carol got neither of them.

[00:11:07] **Carol:** I didn't even know they were movie references. I just thought y'all were making jokes.

[00:11:11] **Tim:** No is no one puts baby in a corner from dirty dancing. And what's the box from, was

[00:11:16] **Ben:** seven.

[00:11:17] **Ben:** Yeah.

[00:11:18] **Adam:** What's in the box.

[00:11:21] **Ben:** So anyway, that's my failure. I should just be more confident in my own abilities and not let people get under my

[00:11:27] **Adam:** I mean, you're absolutely right that you could, and that would be a total, totally valid approach to dealing with that. But at the same time, And there are other approaches that you could consider to,it's an indicator that at least one person outside of your team has that impression of how you spend your

[00:11:49] **Tim:** Perceived

[00:11:50] **Tim:** impression

[00:11:51] **Adam:** Right. Right.

[00:11:52] **Adam:** And.

[00:11:53] **Tim:** reading. So my take on it is I, been, you spoke on the show that you had this anxiety, that the legacy team going away. Right. And so this may have been a comment that exact same word. Two years ago, you've been like, man, whatever, day job is awesome.

[00:12:10] **Tim:** I'm good at it. Right. But now you feel a little anxiety And.

[00:12:13] **Tim:** the exact same words that, the past wouldn't have you because they didn't know the anxieties there, or maybe they

[00:12:19] **Ben:** possible.

[00:12:20] **Ben:** I have felt very stressed in running on empty lately, so I think that's,I'm a little bit of a frayed wire I think. And, and maybe stuff is cutting deeper than it should

[00:12:30] **Adam:** Oh, yeah. There's always context.

[00:12:31] **Ben:** Yeah.

[00:12:32] **Tim:** Yeah.

[00:12:32] **Ben:** Anyway, Tim, what do you got going on?

## [00:12:34] Tim's Triumph

[00:12:34] **Tim:** Well, after that emotional outpour, I feel really bad for saying I have a triumph. Wow.

[00:12:40] **Adam:** Okay.

[00:12:43] **Tim:** I mean, it's just good to be back on the road again. So you guys thank you for holding up the show and waiting for me. Cause I was literally getting off a plane driving home to get here, to hop on the show.

[00:12:56] **Adam:** Yeah, you didn't even put on pants.

[00:12:58] **Tim:** Oh, no, I haven't pants. speaking of pants.

[00:13:02] **Tim:** SoI went to a trade show. It's an insure tech conference, right? So it's all about insurance using emerging technologies and stuff. And there's some really cool stuff there, but the pants story is, so when I was packing, I realize it's been so long since I've gone on one of these things that I had nothing to wear.

[00:13:21] **Tim:** I had like one decent pair of khakis that had like a gravy stain. And so just basically packed one pair of clothes, one outfit of clothes. And then when I got there, it was in Las Vegas. We're staying at the, the Mandalay, down to TJ Maxx and bought like three new outfits, just so I could have something to. So, which by the way, the TJ max is in Vegas are amazing because they have all these high-end stores and they're constantly rotating product. And like, you can get Michael Kors outfits and just super high end stuff, like super cheap. So it's not a plug for teaching max, but. We'll take a sponsorship. now it's just, I mean, there was so much energy at the show.

[00:14:01] **Tim:** I think the past like year and a half, almost two years, we haven't been going to these like face-to-face conferences, everything's been over video and just been dying to get out there and like see people and talk to people and learn from people and hear presentations and, to booze and learn about what people are doing and tell people about what you're doing.

[00:14:20] **Tim:** And that's one of things I love about my job is that I can go from like, coding today and then hopping on a plane and going and talking to CEOs of CTOs of insurance companies and explaining what we do and how it can help them and then learning what their problems are and how we, how we can help solve it or where we need to like improve.

[00:14:37] **Tim:** And the best thing is, so our company has not ever been we're kind of an engineer led company that the founder was a mechanical engineer. Most of the people who. presidents or directors or software engineers, we'd been terrible at sales and marketing. And this year we spent a lot of money on sales and marketing.

[00:14:55] **Tim:** This thing had about 8,000 people show up and we hosted a giant beer garden.

[00:15:00] **Carol:** Dang.

[00:15:01] **Tim:** So free beer for everyone starting at 11:30 AM until 6:00 PM every

[00:15:07] **Tim:** day.

[00:15:08] **Adam:** Wow.

[00:15:08] **Ben:** 30 am.

[00:15:09] **Adam:** That's a lot of.

[00:15:10] **Tim:** That was a lot of beer. That was a lot of areas, as good as like German beers. It was very like, Fasten. And it was, I mean, it was brilliant.

[00:15:19] **Tim:** The hardest part about going out, any of.

[00:15:21] **Tim:** you who've been to a trade show is getting people to come to your booth. We had lines of people coming to our booth to just come get beer. Of course the hard part is like, half of them are like your competitors. So you like, you let them have the beer cause you have to.

[00:15:34] **Tim:** And you're like, salespeople, like stand here. Like you're the bouncer. Right. And you look at the tags and if it's an, if it's a customer, you talk to them. Right. So we have people kind of intercepting and getting their badge numbers and talking to him, but it was just really good.

[00:15:46] **Tim:** It just felt so good to be in an in-person conference. Again. I miss, I, I forgot how much I missed it. I was dreading going, cause I know how tiring it is. And I am absolutely can hear in my voice. I'm wrecked. Absolutely wrecked. I mean, late nights, 2, 3, 4 am every day, but man, it was so much.

[00:16:04] **Carol:** So we're going to need a follow-up on, how many referrals you got back from the beer garden? Like,

[00:16:09] **Tim:** that's

[00:16:09] **Carol:** it paid off? I mean, yeah. Cause I'm curious. Yeah.

[00:16:11] **Tim:** Yeah. I mean, what I was saying. It's like, you spend that much money on it. You have to prove that it was worth it.

[00:16:16] **Carol:** Yeah. He needed to make a sale.

[00:16:18] **Tim:** Yeah.

[00:16:18] **Tim:** Because that conference is going to be saying, Hey, so do you want to do that again next year? And you have to prove that the debt we got it, it was worth as well.

[00:16:25] **Tim:** So that was my triumph. Just going to be back on the road again.

[00:16:29] **Carol:** Yeah.

[00:16:30] **Ben:** exciting.

## [00:16:33] What Happened To Facebook?

[00:16:33] **Adam:** All right. Well, let's talk about Facebook, um, there's a lot to say, even if there wasn't, even if it wasn't this week, there's still always plenty to talk about with Facebook. so this of course is the week that Facebook sort of infamously went offline for several hours. and.

[00:16:49] **Carol:** Instagram, WhatsApp.

[00:16:51] **Adam:** And WhatsApp.

[00:16:51] **Adam:** Yeah. and so there's some stuff we're going to talk about there. and I think if I'm not mistaken that happened shortly after they had a whistleblower, I think her name was Francis Haugen or hugging, basically expose or leak that, they, that Facebook paid for some research to be done on their effects on people.

[00:17:10] **Adam:** And the research showed that they're just bad for everybody's mental health. And instead of doing the responsible thing and trying to improve the effects that they have on people, they were like, okay, but it's really profitable. So we're going to ignore

[00:17:25] **Carol:** under the rug.

[00:17:26] **Adam:** and maybe even explode it to our benefit and try to profit from it.

[00:17:30] **Adam:** so that's going on as well. And then also there's this whole of,

[00:17:38] **Carol:** to work thing,

[00:17:40] **Adam:** yeah.

[00:17:40] **Carol:** Yeah. That came out. So the, there was like this post on daily mail or something, been in mentioned a little earlier in the, before we started recording, and it basically came out and said that they were going to force everyone back into, an office and a few months, but Facebook came out and said that, that wasn't right.

[00:17:57] **Carol:** So they said that they haven't changed their policy, that nothing has been amended. And that whole article was completely crap. So

[00:18:05] **Adam:** Maybe they're just like trying to backpedal at immediately

[00:18:07] **Carol:** Yeah. Cause I mean, that just happened today. Yeah. I mean, as we're recording, like this was, today it came out, so yeah. They were like, no, we didn't say that.

[00:18:16] **Tim:** That was the other

[00:18:17] **Carol:** yeah. Yeah. We're we have not changed our remote work policy and we'll let you know if we do.

[00:18:23] **Adam:** hopefully that's accurate. I mean, I was just sitting here thinking, cause forcing everybody to go back into the office works so well for Yahoo.

[00:18:32] **Carol:** Hm.

[00:18:33] **Ben:** Yeah. What happened to that? I mean, Yahoo is still around or is

[00:18:37] **Tim:**

[00:18:37] **Adam:** I think

[00:18:38] **Carol:** I

[00:18:38] **Carol:** like Yahoo finance. That's the only thing I use Yahoo.

[00:18:42] **Adam:** I think a lot of their IP still exists, but it's like been bought by Verizon or something like that. I think that I'm almost positive that Yahoo had bought flicker and flicker one way or another, whether it's just as a wholesale part of Yahoo or individually was sold to I'm sure.

[00:18:59] **Adam:** I'm not sure. I'm pretty sure it was Verizon, which just seems like an odd thing for them to acquire, but, okay. Anyway, let's talk about this stuff. So where do you guys want to start?

[00:19:09] **Ben:** I don't really know anything about it. Other than what I saw people talking.

## [00:19:14] Companies Ending Work-From-Home

[00:19:14] **Adam:** Let's start with remote work because we all work remotely. Now we've talked about this stuff a little bit in the past. If you got a directive from your company that you are going to be expected to start showing up in the office again, would you consider it or would you start looking for new employment?

[00:19:32] **Carol:** personally, I'd start looking for new employment. I want, a company that values my health and puts that ahead of whatever goals they have and,

[00:19:43] **Adam:** So it is when you say your health, is that specifically because of the pandemic stuff is not over yet.

[00:19:49] **Carol:** It's not done. Yeah. And every time you keep having these mass gatherings of people, not vaccinated and then you keep having these big outbreaks of it. And I mean, we're seeing it now, my kids in public school, I'm not pulling them out of public school. And, you got COVID again, even though he's backstage.

[00:20:04] **Carol:** I mean, it just, it sucks, but I don't want to work where I'm going to constantly be exposed to it either. I mean, we don't know as long-term side effects.

[00:20:13] **Tim:** and I realize I probably should have said my getting back on the road. This show was a fully vaccinated show, supposedly, but it's like, they, it was just Scouts honor. Right. You just basically said I'm not sick. I've been vaccinated.

[00:20:25] **Tim:** So

[00:20:25] **Adam:** interesting. So this last weekend I was down at George Washington university for an event for my company and they had, it was a big event. They had two years worth of commencements to do because last year got

[00:20:38] **Ben:** Oh, right.

[00:20:38] **Adam:** and it was their bicentennial.

[00:20:41] **Carol:** Ah,

[00:20:42] **Adam:** and I think there was an, and I think there was another thing going on too.

[00:20:44] **Adam:** So between all of this stuff, they had something like, I want to say 26,000 registrations for this event,

[00:20:51] **Tim:** Wow.

[00:20:52] **Carol:** Crazy.

[00:20:53] **Adam:** was ridiculous. But something that made me feel really good about it all was that, they had, their lines stantion lines or whatever, but before they even got to the desk where they could check in for the.

[00:21:06] **Adam:** They had to go through COVID screening and they had to provide their vaccination card or whatever else. I don't know. But before they got to us, they were screened for being vaccine vaccinated. And it wasn't just a, oh yeah. I've did it. It was, showing them,

[00:21:19] **Adam:** show us the proof.

[00:21:20] **Tim:** I say that I did have to show my vaccination card. If you also had testing there and you had to wear a mask the entire

[00:21:26] **Tim:** time

[00:21:27] **Carol:** yeah. AWS is doing re-invent and person this year. So we just got the information at work and it is fully vaccinated. You have to prove, you have to show your card and even to even get registered. So I'm glad calm since we're coming back.

[00:21:40] **Adam:** Yeah.

[00:21:41] **Carol:** And I like the vac status.

[00:21:43] **Tim:** back to the employer thing,

[00:21:44] **Tim:** I mean,they just said everyone has to come back, I would think that would be, it just kind of shows a posture of, going to do what we say. Right.

[00:21:52] **Tim:** after they've shown, don't think any company has shown that there's been a huge negative impact to remote working.

[00:21:59] **Tim:** Right. If they were able to make it work, they still got stuff done. Right. It just in different ways. So that's, I would say maybe if you've company said, here's your option, And we're fine with you choosing it. And that's kind of what we're doing. Option is you can come back full time. If you want to the office.

[00:22:15] **Tim:** If you like to do a hybrid, you don't want to do three days, two days. can't have your own dedicated office, but we have these floating off, kind of floating off as you can come in, plug in, do whatever. And if you want to work remotely from home a hundred percent, that's fine too. So it's sort of a hybrid approach of what works for you.

[00:22:30] **Tim:** And you know what, sometimes I go in because it just makes more sense. And sometimes most of the time I stay home, cause it doesn't make any sense, none of my direct reports or even in the state. why should I go to an office? And if there's meetings we have to do or customers visiting, I'll go in, that's not a problem.

[00:22:50] **Tim:** So just, I think giving people options rather than mandates,is it shows more employee faith than it is to just be like, you guys all do what I say because mother knows best and.

[00:23:04] **Carol:** Well, I do. I mean,

[00:23:05] **Adam:** culture thing, right? Like, do you value the opinions and the desires of your workers versus you work for me? You're gonna do what I say. So Ben you're being kind of quiet and it's funny. I have, I can kind of picture you going either way on this, right? Like I know you guys had an office, have an office

[00:23:23] **Ben:** had, I mean, so at the previous company currently envisioned as a spinoff of a previous company and the previous company had an office where we started to dabble with remote work even then. And then Invision was entirely remote from day one.

[00:23:38] **Ben:** I don't think I can certainly, I couldn't go back to an office.

[00:23:41] **Ben:** Full-time it's just too darn comfortable being at home. And too many amenities,not to be, not to go blue here. but I have my own bathroom and like, that's a nice amount of privacy and, when it's hot, I sweat and it's nice not to be in an office sweating it's much better to be at home sweating.

[00:23:59] **Ben:** and I got my dog and I got the misses and I got my, I don't know, it's just really nice being

[00:24:06] **Adam:** You can wear shorts

[00:24:07] **Ben:** I wear shorts all year round, basically.

[00:24:10] **Adam:** Yeah.

[00:24:10] **Ben:** but I'll tell you, I was thinking about this maybe sometime earlier this year, and I think coming at it from an established adult in quotes, it feels probably very different than it would be if I were just coming into the workforce.

[00:24:28] **Ben:** And I wasn't in a relationship and didn't maybe have a lot of friends in the area that I lived. I feel like I want that workspace to be able to go to, to socialize with people. now I'm married, not having people to socialize with. It's like fine. It's now it's more time to spend with my family as far as I'm concerned.

[00:24:47] **Ben:** But you know, if this were 15 years ago,

[00:24:50] **Adam:** Yeah. I mean, that's where you

[00:24:51] **Adam:** make

[00:24:51] **Adam:** friends

[00:24:51] **Ben:** it probably it'd probably be a different story. Yeah, exactly.

[00:24:54] **Carol:** Yeah. Single during COVID sucks. Just going to put that out there. It is not, it's not a way to live.

[00:25:03] **Ben:** Yeah. So I think I could see myself going back into an office once or twice a week maybe, but I almost feel like I would use that once or twice a week to just remind myself about how great the other four days of the week are.

[00:25:16] **Adam:** Yup.

[00:25:17] **Ben:** if at the hybrid model who's to say that the people you want to see are also showing up to the office the same

[00:25:22] **Ben:** days that you

[00:25:23] **Ben:** go

[00:25:23] **Carol:** Right. You still have to coordinate everything. And I don't like Tim's way of having to share like a desk. Like, I want my own space. I want to leave my coffee. Got there overnight and not worry about it.

[00:25:37] **Ben:** Also, I mean, that's a great point about sharing the spaces. Do you bring your computer with you or do you have a computer at home

[00:25:45] **Ben:** and a

[00:25:45] **Carol:** a

[00:25:45] **Carol:** laptop. Yeah.

[00:25:47] **Tim:** usually.

[00:25:48] **Carol:** And I'm assuming most, most like places I've worked at, you have pretty much the same hardware for engineers, right? So we all have the same kind of doc ability. Like we use the same doc should work on almost all of our machines

[00:26:01] **Tim:** Yeah, that's how it works there. So we basically have like, every desk has, is, most of them are standing desks, three monitors, at least, and a doc. So you can just come in, your laptop on the table, plug into the dock and you're ready to go. And mouse keyboard everything's there.

[00:26:16] **Adam:** Oh, no,

[00:26:17] **Carol:** grow. So you've

[00:26:18] **Carol:** lost me. Nope. You lost me a mouse and keyboard. done.

[00:26:21] **Carol:** I'm staying

[00:26:22] **Carol:** home

[00:26:22] **Adam:** mouse and keyboard.

[00:26:23] **Tim:** but you can bring your own, you can bring your own.

[00:26:26] **Adam:** Yeah.

[00:26:26] **Ben:** go off on a tangent really quickly. I've been on a MacBook pro for the last, I don't know, 10 years almost, I think. And I'm so sick and tired of having a Mac book. I want a, what I mean is I would really love to have a nice iMac, something that's just has more Ram in it and more processing power.

[00:26:44] **Ben:** And the fan doesn't turn on the moment I started moving the mouse, but I'm so terrified of this idea that like once a year I'll have to go somewhere and have a computer and I'm going to be Sol if I have an iMac and I don't, I can't get over that emotional fear. And I don't know.

[00:27:03] **Adam:** Well, I mean, I did exactly that. I mean, I bought myself a hack and Taj rather than buying like an iMac, but, as far as the computer knows, it's an iMac, right. Cause you have to kind of fill in what kind of machine is it when you're installing it. and I did it for those reasons, right? I wanted, I needed a new machine to start and it was either going to be by myself, another MacBook pro or build something.

[00:27:24] **Adam:** And I, at this point it would be a huge deal for me to move off of Macko S just in terms of productivity, if nothing.

[00:27:32] **Ben:** Yeah.

[00:27:32] **Adam:** and so what I did, because I bought myself this machine and I bought, I think he's got 64 gigs of Ram and like the best process where I could get at a time decent motherboard. And it's got like integrated graphics because it's, I'm working, right.

[00:27:44] **Adam:** Like terminal is the sort of the most graphically demanding thing that I use or I guess the web browser, and, and SSDs and , is that what they're called them two SSDs or whatever? anyway, yeah, I spent a buttload of money on this, really fast hardware and it's great, except I can't move from this like two foot by four foot area right here because my computer doesn't move with me now.

[00:28:08] **Adam:** I have three monitors here in front of me, and it's wonderful until like, I just want to go work on a personal project on the couch while I watch TV with my wife or it's gorgeous weather outside. And I want to go sit on the deck and work something like.

[00:28:22] **Ben:** I'm not worried about the personal stuff. I'm so comfortable at my desk. I don't want to be anywhere else to work. I mean, it means just like, like I have my ergonomic keyboard. I have my vertical mouse. I have my, comfy desk, for me it's it is purely 100% work-related meaning, I'm afraid that I'm going to have an onsite work event

[00:28:42] **Ben:** and they're going to need me to bring a computer

[00:28:44] **Adam:** Yeah. And I mean, that's

[00:28:45] **Adam:** exactly my

[00:28:46] **Tim:** There'll be other computers there though. Ben, come on.

[00:28:49] **Adam:** I mean, I mean, that seems situation, right. Like I talked about, I was at that event last weekend, I had to take my ancient swelling, MacBook pro with me to that event. And I was like, okay,

[00:28:58] **Tim:** Why is it swole broke

[00:29:00] **Adam:** it's it

[00:29:02] **Adam:** former? Yeah. This battery. I was trying to make a joke about it being project huge with Ben, but, yeah.

[00:29:09] **Adam:** So, yeah. And so basically I was just like, okay, well I'll wear my flameproof pants and. I'll be right. And then, you can't catch COVID if you're on fire. Right. Like,

[00:29:18] **Tim:** and it burns all the germs.

[00:29:19] **Adam:** I set the laptop aside when it stopped, when it started being dangerous to use it. And in part, because it was dangerous, but also in part, because like I knew I wanted to replace it with something with top end. Hardware like my desktop and I knew I would need the laptop occasionally to go on the road.

[00:29:36] **Adam:** And fortunately, I think COVID kind of extended the useful life of that laptop by at least a year, if not longer, because I didn't have to go anywhere. And so it just sat cold on the shelf, not swelling anymore.

[00:29:49] **Tim:** When it gets cold, doesn't swell.

[00:29:51] **Adam:** so now we can take you out of context.

[00:29:54] **Tim:** I'm talking about the batteries.

[00:29:55] **Adam:** the, oh God, I can't even keep my thoughts straight with

[00:29:58] **Adam:** you right now.

[00:29:59] **Adam:** yeah, so anyway, all that to say, I completely agree with you, Ben and I am, even though I had this fantastic machine, which I am not at all outgrowing in terms of performance yet. I am sitting here like with a credit card in each hand waiting for the October apple event, like, come on announced the new MacBook pros and I'm going to buy at least one of them.

[00:30:22] **Tim:** that's funny.

## [00:30:23] Cause Of The Outage And Understanding BGP

[00:30:23] **Tim:** bringing it back to Facebook,

[00:30:25] **Carol:** Yeah.

[00:30:25] **Tim:** what was it?

[00:30:26] **Tim:** They said the bottom line. There's a root cause of the outage was

[00:30:29] **Carol:** Oh, yeah. To the outage. Right? So they were saying network related, right? Like someone changed some DNS, settings got updated and then nobody had access to go fix it.

[00:30:40] **Adam:** I wanted to ask you guys about this. So. I understand how DNS works. To some extent, I have managed my own domains for years and I understand the different types of records and that sort of thing. But then I, when there was, when I was reading up on what happened here, somebody mentioned BGP and that was the first time I had ever heard of BGP.

[00:31:01] **Adam:** And I'm like, I don't know, I don't know what to do. and I was wondering if any of you guys have any experience or any knowledge about this stuff. So we're like, okay, Tim, what's going on here?

[00:31:12] **Tim:** So what I read when I read BGP was the problem, it, I had a PTSD moment. I was totally triggered. So, border gateway protocols, what that stands for. It's kinda like the postal service of the internet. So sending messages to each of these routers, the routers basically use BGP to figure out, all right, where does this need to go the network chain to get closer to its destination?

[00:31:36] **Tim:** Right? So it's a BGP is constantly being announced. Cross network. I'm completely explaining this wrong. So anyone who really knows about it. Well correct me, but obviously Facebook engineers can't even do that because they obviously don't know how to BGP works either. So what w the PTSD that got me was, so when were, we had, our, we have a hosting facility here in Georgia, and it was only on one internet provider, which is bad.

[00:32:02] **Tim:** And, had actually had, had an occasion where, some construction going down the street and they hit the internet line and we were out, hosted customers were out for a good part of a day. So we rearranged everything. got multiple providers coming in. And so what the role that BGP plays is that whenever, running on like your main provider, And all of a sudden there's an outage.

[00:32:26] **Tim:** BGP is supposed to send out, you're supposed to do an, BGP update and it can be done automatically. It can be done manually. We were doing automatically that goes out to the world and says, Hey, I know that you think that this message should go to mailbox here, mailbox.

[00:32:40] **Carol:** server

[00:32:41] **Carol:** area

[00:32:41] **Adam:** And network switch or something.

[00:32:42] **Tim:** but actually it needs to go here.

[00:32:44] **Tim:** Now it's a forwarding address. so when we actually did have an outage, work. So we spent all this money all this time trying to, sure that network is multi-home, that we, so we wouldn't have downtime when there was construction going on. And so, with a ditch which accidentally hits your fiber line.

[00:32:59] **Tim:** that happened and it went down and, all just yelling, Leo, why did we spend all this money? Well, the word BGP just kept coming up and up. And again, obviously it seems very cryptic. It was one of those things that you never have to touch because it's normally not used. And if you misconfigure, gets really hard because this is propagated across the entire internet.

[00:33:19] **Tim:** And so you can fix it right now. Doesn't mean you fixed the

[00:33:22] **Tim:** problem

[00:33:22] **Tim:** across the entire range. worse than DNS Cause I don't know if it just doesn't update even more or I don't know what it was, but took we'd made the update. Cause there was a configuration change problem, probably similar to what Facebook had. It was not announcing the right address. It was trying, it was announcing the wrong address. And so even though technically we had,access coming into our servers, no one was being able to talk to us because it was going the wrong

[00:33:48] **Tim:** place.

[00:33:48] **Carol:** It was still pointing to the wrong route. Yeah.

[00:33:51] **Tim:** Right.

[00:33:51] **Tim:** We, I was point, well, it was pointing to not the original round, but a different round.

[00:33:55] **Tim:** Right. So, and it sounds to me like that's kind of what happened with Facebook. story though, I read today apocryphal. Cause I don't know if it's true or not. But saying that, said that a friend of theirs from Facebook, so, confirmed source basically said that they had to go to the server room cages that didn't have any,locks and just use an angle grinder to cut open the cage so they can get into the machines to manually, to mainly directly connect to them, to be able to change the settings so that they get back up

[00:34:26] **Tim:** and

[00:34:27] **Adam:** Yeah. I mean, that doesn't surprise me. We heard stories about like, nobody could get into conference rooms at Facebook because it was all IOT access

[00:34:37] **Tim:** yeah.

[00:34:37] **Tim:** So, that, that triggered me because I was sat in many, a meetings trying to understand, in end, the after action, why didn't this work? And the only thing I heard, like 5,000 times in that meeting was the word BGP to this day, hearing it makes me itch.

[00:34:53] **Adam:** So, let me maybe explain the, my understanding that I've gained from hearing your description. And let's see if I'm on the right page here. So it sounds like I can figure my DNS and I say, okay, or like with my name server. Right. and I say, this is the address for this domain, right? My, my blog or whatever.

[00:35:09] **Adam:** And then BGP sounds like it's the magic that the routers work between themselves so that they all know that when you request my blog domain, it should go over there. Like maybe not the direct final destination, but it's like, okay, I know that in order to get there, you have to go to this one. So you have to go to X, not Y.

[00:35:27] **Carol:** it controls the hops. Yeah.

[00:35:29] **Tim:** So how I imagine it is that each. Router each node in the internet is kind of play of the old fashioned media will gain where you're traveling down the road and there's a sign or maybe the signs out. And there's a guy, blood with all legends of Zelda is a guy standing in the corner and you're trying to get to the castle and you say, hello, sir, where's the castle.

[00:35:49] **Tim:** And he says, oh, there's like two roads going. It's that road to the north. And you take that road and you get to the next one. There's three in each hop. They tell you where to go. That is BGP. The DNS is like, is the castle right, that'swhat it's called, but how you get to it on each hop is the BGP.

[00:36:08] **Adam:** right. But it sounds like it's more, it's less of a on-demand evaluation and more of a push mapping

[00:36:15] **Tim:** Right. so, it continues to update across the internet, of the internet is telling you that the destination for the castle is up north and some of the internet is telling you the destination where the castle is down south. And so you get conflicting reports and some things get there.

[00:36:31] **Tim:** Some things don't, nothing gets there sometimes. So it's

[00:36:34] **Carol:** Yeah. And it can be a complete dead route at that point. Yeah.

[00:36:38] **Tim:** Yeah.

[00:36:39] **Carol:** Yeah.there was one point I wish I could remember when it was like, I'd have to go look it up, but like, I wanna say Pakistan Navy tried block try using it to block YouTube from being used inside their, like country. So like, okay. We're not gonna allow anybody here on our ISP is actually watching anything on YouTube.

[00:36:59] **Carol:** Well, they then propagated that path accidentally out to the other systems. So then it ends up taking YouTube down for hours because other people trying to access it ended up on those routes.

[00:37:10] **Ben:** Interesting.

[00:37:12] **Adam:** Kind of like a DNS poisoning attack

[00:37:14] **Adam:** sort of thing, unintentional, but yeah.

[00:37:16] **Ben:** When I was younger, there was something called dine DNS, which was some sort of dynamic

[00:37:22] **Ben:** DNS. Is

[00:37:23] **Ben:** that, what did that do? that was like, if you had a domain name, but the underlying IP address changed and you didn't want to have to change it. So

[00:37:31] **Ben:** dine

[00:37:31] **Ben:** DNS would automatically

[00:37:33] **Adam:** use that. so I have a NAS and I want that certain things on my NAS, like things running in Docker containers to be accessible to me, from my computer or from my phone when I'm outside of my home. And so I have something running on my router, which is exactly what dynamic DNS was doing.

[00:37:50] **Adam:** Dine DNS. There's a bunch of different services. and basically my ISP assigns me a new random IP address in their block. Every time I disconnect and reconnect and this app running on my router just goes out and updates the DNS record, anytime that IP address changes. So I can just access it my host name, and I don't have to worry that my IP address has changed.

[00:38:11] **Tim:** Yeah, I use the same thing for my, I have an old video security system, new ones that I'll take care of it, but yeah, this one, you have an external IP that constantly changes, but I have a little domain name and Dan DNS kind of updates it. He has a little program that runs on the computer and just constantly says, oh, my IP is this now.

[00:38:29] **Tim:** So

[00:38:29] **Tim:** that

[00:38:30] **Ben:** Gotcha.

[00:38:30] **Tim:** stays real.

[00:38:32] **Carol:** Hm.

[00:38:32] **Adam:** Okay.

## [00:38:33] Is Someone Getting Fired Over This?

[00:38:33] **Ben:** do you think someone's getting fired over this or is this a teachable moment?

[00:38:40] **Ben:** I saw somebody say something that the downtime for Facebook ended up costing them, like in the billions of

[00:38:48] **Carol:** oh, I last I saw was millions in revenue loss,

[00:38:51] **Carol:** billions with a B that's crazy.

[00:38:54] **Ben:** at least it happened during the day. People didn't get paged in the middle of the night.

[00:39:01] **Adam:** I mean,

[00:39:01] **Adam:** I'm sure you

[00:39:02] **Adam:** know what?

[00:39:02] **Ben:** I'm saying that the face it's not like the Facebook stuff got messed up, doing some sort of 2:00 AM shift and people had to be woken up. I mean,

[00:39:10] **Carol:** And I mean, it was somewhere

[00:39:12] **Adam:** It was absolutely. But I think that for,from the perspective of the management and the bookkeepers at Facebook, they will, I'm sure they would have rather had gone down at 2:00 AM. Right.

[00:39:23] **Tim:** I am north American time. Yeah.

[00:39:25] **Adam:** Yeah. Because they potentially lost billions from it being down.

[00:39:28] **Adam:** I wasn't like six hours, eight hours, something like that.

[00:39:30] **Ben:** I see, so you value $7 billion more than

[00:39:33] **Ben:** people's sleep, whatever.

[00:39:36] **Adam:** I'm saying there is somebody somewhere, whether it's Zuckerberg or whatever, his minions that are going, I wish that would have happened at 2:00 AM. Yeah. Okay. and I absolutely have sympathy for the people that have to get up at 2:00 AM to deal with something like that.

[00:39:50] **Adam:** Because like I'm had mentioned in the past, I'm on a very small team and we rotate a week on and two weeks off of a on-call and happens, man. I'm going to get quacked. Sorry about that. and yeah, I mean, it. It's a necessary evil.

[00:40:07] **Tim:** but I mean, you know what? It makes me feel good when the big guys fall down because it's like, yeah. no one has a hundred percent of this stuff figured out it's a very massive complex system. And the fact that it works as well as it does is a miracle.

## [00:40:23] Whistleblower On Facebook Research

[00:40:23] **Adam:** and it's hard to feel bad for them days after you find out that they're exploiting people's emotions for

[00:40:30] **Adam:** literal profit.

[00:40:33] **Carol:** The teenage girls. Oh

[00:40:35] **Adam:** Yeah. I mean, I feel like we've known this, right? Like that, that just Instagram is, I mean, obviously 99% of social media is bad for 99% of people baseline.

[00:40:46] **Adam:** Right.

[00:40:47] **Ben:** I tend to agree.

[00:40:48] **Adam:** but I think. I feel like I've seen this study, in recent years, like within the last five years that showed that Instagram in particular is bad for young girls in particular. just because of the social structures that they build up in their age groups, and how that involves Instagram and all that. And

[00:41:07] **Tim:** all about image.

[00:41:08] **Adam:** yeah, and about popularity and, yeah, and, but like, I'm struggling to separate that from what were we, what we've learned this week.

[00:41:18] **Adam:** And really, I think, for me, what does it is that what we learned this week is that Facebook has known for a long time and ignored it intentionally for a long time. It just continued to try and profit from it.

[00:41:29] **Adam:** And.

[00:41:30] **Tim:** And it makes me wonder why they did the study in the first place. Do they really think was going to come up with a different answer? That it was Facebook? Like social media was good for you?

[00:41:41] **Adam:** Well, I mean, there's a long history of companies that are bad for you funding research specifically to prove that they're not bad for you, or like, like tobacco and, led and yeah. so

[00:41:53] **Ben:** Now with more than

[00:41:57] **Adam:** led flavored cigarettes.

[00:42:01] **Tim:** in sugar.

[00:42:02] **Adam:**

[00:42:02] **Tim:** I think with the whistleblower thing, there's a broader story about dealing with, I don't want, I don't want to characterize it as disgruntled employee. Right? So they were former employee and they were telling stuff about Facebook that I don't know how they prove that the claims are true. I mean, his Facebook not.

[00:42:24] **Adam:** I don't know.

[00:42:26] **Tim:** Cause, I mean, we need to know that right. I mean, it's like you do have sometimes former employees who are angry and they're just going to do everything they can to like disparage their former employer. even perhaps even lying, maybe they're telling the truth. Maybe they're not, I mean, unless it's been confirmed, studies come out, we don't know.

[00:42:46] **Adam:** Yeah. I mean, I'm sure that they have lawyers that are saying it's not true.

[00:42:49] **Tim:** And gets into a legal battle. But I mean, what w I think what's interesting is that on its face, I mean, this sounds, so it sounds like a truism, even regardless of the fact that if it's true or not, everyone just goes, oh Yeah. that sounds about

[00:43:03] **Tim:** right.

[00:43:03] **Adam:** Yeah,

[00:43:04] **Ben:** they're going to checks out.

[00:43:06] **Tim:** Check the boxes. We all know that.

[00:43:08] **Tim:** I, yeah,that it's not good for folks then we see. So I, I don't know if I told you guys story went up. When we went to Hawaii a couple of years ago for our 20th anniversary, it's like saw this couple on the beach and she's on the beach there, Malibu and spending the entire time he, her boyfriend is like taking photos of her and could tell she's just trying to get the shots for the gram.

[00:43:32] **Tim:** And then she spends, so he takes all these photos. She he's gives her the phone back to her and there they are on beautiful wide. Sunset's going down. It's gorgeous. wife and I are swimming and having a good time and eating and enjoying the view. And I'm just looking over there.

[00:43:46] **Tim:** She didn't not once stop and enjoy the view. She sat there editing her photos the next 45 minutes. I'm trying to get the perfect pick to put up there. And I'm like, really. Your life is going by you lady,

[00:44:03] **Ben:** No, I have to admit this happened to me one time I was up in Vermont with the Mrs and the dog, and we went down near the water and it was sort of this beautiful sunset. So I took Lucy, the dog, and I put her up on this pedestal, like an

[00:44:19] **Ben:** actual literal pedestal.

[00:44:22] **Tim:** the two women in your life.

[00:44:24] **Ben:** So I have the dog there and in the background is this beautiful sunset, is pink and purple and yellow clouds. And I take this picture and I'm sitting there on the bench, in my, on my iPhone, editing the photo as best I can. And after like 10 minutes, my wife was like, you have to get off your phone immediately. I was like, no, but it's so close. She's like, no, you can do it later.

[00:44:46] **Adam:** Exactly

[00:44:47] **Tim:** You can edit it later that photo's not going anywhere.

[00:44:51] **Adam:** Yeah, no, I, I'm in the camp, like take a few photos and then enjoy your time there.

[00:44:56] **Carol:** Yeah. I don't like living with something between me and what's going on. Like Christmas. It always drove me nuts when my mom was like, record the kids and post it for me. I'm like, no, I just want to sit here and watch my kids. I don't want to have, something in between me and what's going on. Like, I want to enjoy the moment.

[00:45:14] **Tim:** It's funny. So the Bruno Mars was in concert in Vegas and he, took everybody's phones and they had, theyput them in this phone jail. So you still, you could hold onto it. They didn't like it in these cases and you weren't allowed to get them until after the show, which I think is brilliant because like, spend the whole concert, not enjoying the show yet with the camera in front of your face, looking. Image representation of that. And they're like, who's ever going to like, watch that and enjoy that. it. It's not a great quality photos and even started singing. We took all your phones. We took all your phones.

[00:45:50] **Carol:** We all move that the social media sides bad for kids. That's not

[00:45:55] **Tim:** Wow. it was a kids are just everybody.

[00:45:58] **Carol:** I mean, a lot of it's focused on like young females though. And the They do. I mean, when you look at, I mean, I hate filters, number one, like I hate filters on pictures. It gives you like this skewed view of what is reality and what is okay.

[00:46:15] **Carol:** And it makes you feel like you alone are not enough anymore. And you have to take out your imperfections to be okay. And for a 13 year old girl, who's figuring out her body and growing, that's not a good thing. I mean, to constantly feel that pressure of, you're not perfect. And the filters just proves that what you are as you are.

[00:46:34] **Carol:** Isn't perfect. So he filters alone is a bad thing. So then when you add the bullying and you add the people not liking your posts and the whole instant gratification, when you post something like it's just a giant mess. I hate social media.

## [00:46:48] Parenting And Social Media Usage

[00:46:48] **Tim:** Yeah, I don't let my, kid, I mean, my son's 18, we still in high school. I neither, one of my daughter's 16. I don't want them out there. There's no social media for them.

[00:46:57] **Carol:** Huh?

[00:46:58] **Tim:** just, it's too disruptive. Cause the, my son, he, we took him out of school last year because of COVID. So he had this big gross bird, so he comes back and he's like tall and he's like chiseled chin, and he's been working out, it's a good looking kid. And like, so the, like the freshmen girls he's playing basketball, the freshmen girls, like, like, sending the girl over to find out the two information they wanted to find out is what are you gay? That's the first question. And two, do you have Instagram? And he's like, no no

[00:47:27] **Carol:** So when James went off to college, he deleted all his social media. He was like, this is just stupid. And I don't want people knowing what's going on in my life. Number one, like I don't want my parents seeing if I screw up one night, so I don't want people tagging me in

[00:47:41] **Carol:** things. I mean, and then he's also like, if you want to know what's going on in my life to be in my life.

[00:47:46] **Adam:** Yep.

[00:47:47] **Tim:** yo

[00:47:48] **Carol:** yeah.

[00:47:49] **Tim:** of wisdom.

[00:47:49] **Carol:** smart smart kids.

[00:47:51] **Tim:** was very good.

[00:47:52] **Ben:** you remember when the check-in services like four square F first came out, someone had created this site called please break into my apartment or

[00:48:01] **Ben:** something.And it was basically every time people would check in somewhere else, it would tell you that they are not home and it would have their, where they checked in at home.

[00:48:12] **Ben:** I mean, just to show you how ridiculous it is, how much information people share.

[00:48:15] **Adam:** Yeah. Also you can be the mayor of Starbucks or whatever.

[00:48:20] **Carol:** Oh, yeah. forgot about that.

[00:48:23] **Adam:** So Tim actually, you mentioned neither of your kids has social media. Is that something that you decided for.

[00:48:29] **Tim:** oh yes.

[00:48:29] **Adam:** Okay. and, well, I meant that as a you and your wife, right? Like it's a parenting decision that you guys made. That's not a decision that your children made for themselves. So, but you do have some social media.

[00:48:40] **Adam:** I know you are less active on Twitter, less active on, Instagram. you have your moderately active on Facebook. I know. do you have, some cognitive dissonance there is, do you feel, I'm not trying to make you feel that I'm not judging you. I'm just asking your read here. Do you, are you, do you feel a little bit hypocritical

[00:49:00] **Tim:** no, no, because I'm a grown man who knows who he is. Right, right. And people can bully me if they want it. I'm not going to cry out to block them or, make them cry. They're not ready for it. Right. And plus they're under age and there's just that there are people that just will camp on, some young person's account, and try to figure out where they live and what they do, what they like.

[00:49:23] **Tim:** And, Put them in a compromising situation. So, when they leave the house, they can go do whatever they want. But as of now, no, no social media, I do live and use discord, which I don't really consider social media. They watch like gaming and stuff like that. And their friends can chat with them, but they're not posting stuff about themselves.

[00:49:42] **Tim:** And they do have my add, my son does have a blog with his, I bought his name as a domain name, but that you can control. Right. That's you only putting out what you want on there and it's not so super easy just to take a random pick and tag it, whatever it's, he's writing articles. I mean, he's, most of it's about blacksmithing. he's into.

[00:50:01] **Adam:** So, I mean, I know I'm kind of turning this into my personal parenting advice column here, but so did they, did your kids like beg you for social media and you just had to constantly turn them away? Or did they just

[00:50:13] **Tim:** No, I don't, I believe this is a parenting conference here, but, early on, I established that when we say no, it's for a good reason and that we don't ever back home that.

[00:50:26] **Adam:** okay.

[00:50:27] **Tim:** And so, and it's not no forever. Right. So when we say no, we're like, no, we don't think you're ready for that now, but we can reevaluate that.

[00:50:35] **Tim:** And they get that right? So they have never once said they did want discord. They said, can we do discord? Cause I like the, there's some good gaming stuff on there. And I saw, I was like, well, let's take a look at it together. How, we evaluated, how easy is it for people to find out who you are?

[00:50:50] **Tim:** It's actually not very easy. what will you be posting on it? Nothing, most of them just be consuming. So based on that criteria, yeah, we can do that. So I think we have a healthy relationship where we can say, no, not right now, you're not ready. And they respect that. And when they think they're ready, they'll come back and ask

[00:51:08] **Adam:** and we'll reevaluate it.

[00:51:10] **Adam:** Yeah. I mean, I'm very selfishly asking these things because my kids are 10 and 12 and they're knocking on the door of that, that age group right now. So.

[00:51:19] **Tim:** Yeah. Scary place to be a kid these days.

[00:51:21] **Adam:** Lots to think about. Yeah. I mean, I've explained that to my kids. Like they have challenges ahead of them that I didn't have right there. They have the opportunity to put things on the internet and that once they're on the internet, there's no taking it back.

[00:51:33] **Carol:** It doesn't go away.

[00:51:34] **Adam:** Yeah. And I've, I have, I mean, I have boys, I have stressed to them repeatedly and very clearly, and like I'm pointing out, like this is a big deal. Nudity of anybody of yourself or of anybody else is not to be put online because not only can that ruin your life, that can ruin somebody else's life

[00:51:54] **Carol:** Oh yeah, absolutely.

[00:51:56] **Tim:** Yeah. In most states that's distribution of child porn, even if it's just two miners sending it to themselves and they can get in legal trouble for

[00:52:01] **Adam:** Yup,

[00:52:02] **Carol:** Yep.

[00:52:02] **Adam:** yup. Yup. Yup. Yup. Yup.

[00:52:04] **Tim:** So, yeah. I mean, social media, it's, it has its benefits. I mean, we can, I can keep up with my family across the sea and do all that, but yeah, it's a tool that it has to be used wisely and unfortunately, big companies are profiting off our personal lives.

[00:52:19] **Adam:** Yeah. I mean, if you're not paying for it, you're the product.

## [00:52:22] Patreon

[00:52:22] **Adam:** Cool. All right. Well then this episode of Working Code is brought to you by the Instagram filter that makes you look like a dirty slob and listeners.

[00:52:30] **Adam:** Like

[00:52:30] **Adam:** you,

[00:52:30] **Tim:** That's really me.

[00:52:32] **Adam:** that's just the no

[00:52:33] **Carol:** no

[00:52:33] **Carol:** filter.

[00:52:34] **Tim:** filter.

[00:52:35] **Adam:** if you like what we're doing here, you might want to consider supporting us on Patreon at patreon.com/WorkingCodePod, to thank our patrons for their support. They'll get an invite to our Discord server, where we hang out and chat about the podcast and work stuff like. And we have other perks available, like early access to new episodes and the after show. And of course we need to thank our top patrons, Monte and Peter. Thank you guys so much for your support. As a matter of fact, Monte, just recently got a new job and he asked us to pass along that his company is hiring.

[00:53:02] **Adam:** They're looking for senior, CFML developers. So if that's you and you are looking for a new gig and they say they have pretty good work-life balance, he works at CF web tools. So that's CF web tools.com should be pretty easy to spell, I think. cool.

## [00:53:17] Thanks For Listening!

[00:53:17] **Adam:** So, if paying for podcasts is interesting. No worries.

[00:53:19] **Adam:** We appreciate you taking the time to listen and there are some free ways that you can help us out too. You can share this show with your friends and your coworkers, just not with an Instagram filter, or you can leave us a rating and a review on apple podcasts or wherever you get your. Please send us questions and show topic ideas on Twitter or Instagram @WorkingCodePod.

[00:53:37] **Adam:** Or you can leave us a message at 512-253-2633. That's 512-253-CODE. We'll catch you next week. And until then,

[00:53:45] **Tim:** your heart matters.

[00:53:46]

## [00:53:46] Bloopers

[00:53:46] **Carol:** I read it while you guys do try with all yours

[00:54:08] **Adam:** Okay. If you say so, if you think you can do that, multitasking.

[00:54:11] **Carol:** and the mom.

[00:54:12] **Carol:** Are you kidding me?

[00:54:13] **Adam:** Yeah. Well,

[00:54:14] **Carol:** can listen and talk at the same time.

[00:54:16] **Adam:** I can barely listen to myself.

[00:54:18] **Carol:** Sometimes I can chew gum doing. -

[00:54:19] **Adam:** and yeah, so, I mean, basically when it started to get swollen, I stopped using it. Cause I was like, okay, I might,

[00:54:26] **Tim:** Can we take,

[00:54:26] **Adam:** yeah, yeah, yeah,

[00:54:28] **Carol:** I just

[00:54:29] **Carol:** did.

[00:54:30] **Tim:** take that out of context, that needs to be to that needs to be a blooper reel right. there.

[00:54:36] **Adam:** when I stopped using my laptop, how do I even say this now? Whatever

[00:54:42] **Tim:** So, so bringing it back to Facebook,

[00:54:44] **Carol:** Hey is somebody making a zipper sound?

[00:54:47] **Tim:** Yeah.

[00:54:47] **Carol:** Oh, okay.

[00:54:49] **Tim:** That's me, I guess. Yeah, I guess I, so when I went

[00:54:54] **Tim:** to TJ, Mexico, I got these north face pants and they have all these zippers and I'm just enamored with

[00:54:58] **Carol:** Ah, oh, hands out to use zipper. Okay. Come on

[00:55:02] **Tim:** Oh, wow. All this show. Okay.
