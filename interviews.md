---
title: "Super secret tale of interview woes 🤫  "
date: 2019-06-24
layout: single
author_profile: true
read_time: true
comments: true
---

Good news! I like you enough to let you read my NSFW railings

I'm finally done with interviewing, at least for the time being (read crossing my fingers till they're blue that I wont be doing this again for at least 3 years). I'm starting at Square in mid July 2019. It was probably the hardest interview I've ever done from an endurance perspective, but the technical aspects of the process were no slouch either

To give you an idea, I started this journey in late 2017, taking a 6 month break from it mid last year (2018) to do a remote contract, and ended it in June of 2019. In this 1.5 year span, I did probably upwards of 300 interviews. That's individual interview stages not counting HR or external recruiter screens/calls to be specific, not 300 companies, though that number is probably around 100. These stages ranged from:
* answering open-ended "trivia" style questions over the phone like "what is the difference between a process and a thread" or "Explain what a Scala case class is desugared to by the compiler"
* online coding assessments
* homeworks
* onsites, which are themselves typically comprised of:
  * a system design session
  * coding sessions with at least one developer
  * behaviorial sessions

### Technical Progression

I started from being shaky just even at introduction calls/screens where I explain my background and the interviewer tells me about their background, what the company is working on, and what the position entails, to being reasonably strong at technical onsite sessions, which for coding involve the interviewer giving you a question, typically multipart and you implementing a compiling, running, and semantically correct solution in, on average, no more than 30 minutes, running it against their test cases and test cases of your own to ensure correctness, all the while verbally communicating how you're thinking about the problem, what possible approaches may be to solving it, and explaining, assertion-by-assertion, the logic you are implementing to solve it as you are writing the code, followed by a 10 minute or so open-ended Q/A with your interviewer, and for system design involves typically 2 or more developers giving you an open-ended system design question like design Facebook messenger or design twitter and you asking questions in order to gather requirements for the system like features, API, and load (queries per second), and then implementing an architecture for it on a white board. And being strong at behavioral onsites as well


### Progression of my Attitude

TODO


### The most egregious questions I was asked:

In the case of larger companies, I've chosen to de-anonimize these as I believe that the power dynamics there are skewed towards the company. Unless the interviewee has done their research on the types of questions that could be asked (usually by trolling Glassdoor interview reviews or, for big players like Google, Facebook, etc, trying questions tagged as having been asked at the given company on interview prep sites like Leetcode), they're going into the interview largely in the dark. And really, this is true even if they have. This is because these company's have a very specific interview format that an incredibly minute portion of developers, even if they're virtuosos, would really excel at out of the box without doing mock interviews and solving a shit ton of practice problems beforehand. Also consider that big, sought-after brands like Google and Facebook can afford to be as arbitrarily picky as they'd like in their process which essentially directly translates to an interview difficulty level that is equivalently arbitrary.
In the case of smaller companies, I'm not sure, at a higher level, this is the case despite the fact that they usually simply co-opt the same processes as the big players. Therefore at least as far as the interview process goes, the effect is the same

### Banks

* Morgan Stanley: "What's your favorite data structure?"
* Bank of America: "How would you design a service that talks to a SQL database?"

Interestingly enough (or not) these banks all have the same interview process for which my patience topped out at 2 calls with Morgan and half a call (no thats not a typo, will explain in a minute) with BoA (and that's as far as they wanted to take me as well :)). These calls consisted entirely of technical trivia, which was comprised of questions like how is Scala's HashMap type implemented under the hood, what are the `equals` and `hashCode` methods and what is their relationship, what is a case class, explain pattern matching, etc, etc. Pretty mind-numbing stuff but I suppose some of the questions I listed could be relatively effective in weeding out candidates unfamiliar with Scala as a language. Of course unless you're hiring for critical, crunch time Scala project(s), interviewing for competency for a specific programming language is silly in my opinion, but this is a whole nother discussion I'll get into in a bit. Also not interestingly enough, every person I talked to at both came across as passion-free and downright demoralized. I can only imagine what actually working with these people would be like, though I prefer not to

P.S. why only half a call with BoA? The interviewer started rattling off these questions and I obliged in answering them faithfully, through gritted teeth and substantial boredom. Here's the tail end of that which I paraphrased. Btw Morgan's calls pretty much went exactly the same way:

him: what do all types (sic. he was very vague here) inherit from in Scala?

me: *As with all of this crap I just proceed to rattle off what I know off the top of my head...* I'm pretty sure everything inherits from `Any`. Classes inherit `AnyRef` and then I can't remember where `AnyVal` fits into this. I just use it for zero runtime overhead value classes which extend it. I think because everything is boxed in Scala, boxed primitives inherit `AnyVal` but dont quote me on that

him: *silence* More generally what's at the top of the inheritance hieararchy?

me: *rolling my eyes* are you looking for `java.lang.Object`?

him: *silence* what are the methods on `java.lang.Object`?

me: yea I mean don't know all of them of the top off my head but `toString` is one and `equals` and `hashCode` I think are too?

him: are you aware of `hashCode` and can you tell me how you've implemented it before

me: Yea `hashCode` just denotes the implementation details of hashing a class which is represented as an int. An example that comes to mind would be `HashMap` in Java calls `hashCode` on the key to determine what bucket to then put it into but collisions are possible when 2 different keys hash to the same thing so then it calls `equals` to determine whether a collision did indeed occur or it didnt and the 2 keys are actually the same but I've never had to implement it before because in general all this stuff happens under the hood but in Scala in particular I can't really think of a use case where you'd need to override `hashCode`. I do remember recently I had to compare large strings to determine whether they had changed and I used SHA256 there to see if there was a diff but I just used a lightweight wrapper type with a constructor that did the hashing instead of doing anything with `hashCode`

him: *silence* how would you design a service that talks to a SQL database?

me: *eyes are now constantly rolling to where if someone was looking at me they'd think I'm having a seizure...but still completely politely:* I'm not sure what you mean here. You'll have to be more specific

him: ok I'm ending the call

me: *so confused but I just laughed at this point*

him: *hangs up*

So my takeaway as far as these big banks go would be to stay away. I just can't imagine that this inanity stops at the interview process. And unless it's a technology company that just so happens to do finance (think Jane Street and 2 Sigma and afaik even there the first class citizens are moreso the quants (for whom you could argue programming is a means to end rather than the main focus) rather than strictly software engineers) like this new outcrop of so-called fintech companies, it's probably not a good idea as a software dev. **Always prefer technology companies with some unrelated domain bolted on than some unrelated domain companies with technology bolted on**

### Pretentious (usually niche space) or simply silly (usually startups) companies

#### Pretentious
* _Haskell startup_: I was given a CSV file of school names and another CSV file of a list of filenames that are similar to the a given school name. ex: school name: Worcester Polytechnic Institute file name: Worcester_Polytechnic_Institute.jpg and was asked to write a program that matches a filename to the name of the school it most closely resembles. As I've mentioned and you would know if you've ever done a technical interview of any kind, the most time you're ever given to implement a solution is 45 min, but typically is more like 30 out the hr allocated for the interview due to the time spent at the beginning conveying the question and the Q/A at the end. I ended up having more like 30 min for this one, mostly because the interviewers were very inexplicit about the constraints on the problem and what I was allowed to use in terms of outside resources. Here's what happened: after they conveyed the question and I understood it enough to begin conceiving of a solution I proposed to approaches to solving the problem: TODO

#### Silly
* A Dell subsidiary: Couldn't rattle off the internals of Kafka and Cassandra, but I was familiar enough with both at the time to give a high level overview. Because of this I wasn't even given the chance to interview for real (next step would've been a homework). This annoyed me so much and well really I felt that being intimately familiar Kafka and Cassandra would actually be pretty damn useful and practical in my career, that I sat down to read some books and articles on both and play around with with them a bit. And guess how long this took? A few weeks. Which is really the root of my frustration with how this went down.
* An interview for a Spotify contract: Didn't have Hadoop experience or something oddly specific like that so wasn't even given the chance to interview. If this ridiculous approach is what we're taking taking to evaluate candidates then mind you this was for a Scala position, and lets just say I've seen Spotify's open source Scala and they could really use people that know their way around Scala and its ecosystem. Earlier this year (2019) I applied to two full time positions at Spotify: a data engineering role I was straight up rejected for and wasn't even given and interview and a vanilla backend role that, given it was again Scala and a bunch of other shit I'm very familiar with, I was probably maybe even over qualified for, that they didn't even get back to me on, at this point it's possible that they just don't like me or something haha. Lean hard on those referalls to get interviews at places if you have them.

 Takeaway: **Do not empasize rattling off random crap about specific tools, frameworks, or programming languages in an interview. The translatable core concepts that underpin these is what's actually important. And even then I'm not sure that not knowing what a monad and two phase commit are is a non-sequeter for an interviewee**

#### No words 🤦
* Small-to-mid-sized F# shop:
Ok...ready yourself...You have a bunch of IoT devices that are transmitting temperatures in Fahrenheit to 3 decimal places but you can just assume its an integer (i.e. given 50.001 F, multiply by 1000 to get the integer 50,001) to a central hub which groups them into time windows of 1 second (i.e. let say `Instant` -> `Array[Temperatures]`). If I have a function that takes an `Array[Temperature]` and a target temperature `T` how do I find a temperature in the array that equals `T`. And how can we take advantage of all cores on the machine that’s gonna be running this function.
The only valid reaction to this question is wtf. WTF for the interviewer using this over and over again and having the time and engery to convey all of this and then deal with the candidate's likely befuzzled reaction. And WTF to me for not doing us both a favor and politely ending the call short and then proceeding to try to put the damn thing into writing ^ lol.
Having said that, I appreciate the essence of what this question is evaluating. In fact if we could get rid of this completely superfluously lavish premise/concrete example and just asked: write a concurrent program that finds a given integer(s) in an array it wouldn't be a bad demonstration of whether the candidate posseses a basic understanding of concurrency/parrallelism and can write a simple `for` loop or is aware `find` or `filter`. But this was needlessly painful for all parties that were involved

