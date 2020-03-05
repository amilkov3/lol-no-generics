---
title: "What I'm Working On"
layout: single
permalink: /
---
2020

A lot has changed since last year. I realized I sort of pidgeon-holed myself into programming language theory the past (first) 3 years, which is good because I have a good idea when and why a programming language is appropriate and when and why not. But...at the expense of actual systems and engineering knowledge. So for now I don't care much what I'm programming in. I just care about problem solving. Though if anything I'm now even more curious about _all_ of them

* Super secret event planning platform for a start-up in Uber's [Fusion](https://fusionjs.com/) fullstack JS (using Typescript) framework
* Trying to introduce Rust to Square which entails porting their entire internal and a large chunk of their external ecosystem. What can I say...I miss functional programming and language features in general. Go makes programming way too straighforward...and boring (which is a good thing in my estimations at this point)

2019

* [Functional Data Structures & Algorithms](https://amilkov.gitbook.io/fp/) - This is a GitBook about implementing common algorithms and data structures, the kind you'd encounter in a mostly undergraduate/some graduate course on the subject and, more pertinently, a technical interviews...in the functional (+ statically typed) paradigm however. So if you want to confuse the shit out of your interviewer, check it out
* <img src="/assets/images/aws4cats.png" width="50" height="50" alt="Computer Hope"> [aws4cats](https://github.com/amilkov3/aws4cats) this is a `cats-effect`, `http4s-core`, `fs2` wrapper around the new 2.0 AWS Java SDK. So far I'm supporting SQS, S3, and DynamoDB. With longer term plans for SNS, RDB, etc **EDIT** project is still up but I'm no longer working on it

# Articles

{% for post in site.posts %}
  <p style="margin:50px 0 0 0;font-size:15px;"><i class="far fa-calendar-alt" aria-hidden="true"></i> {{ post.date | date: "%b %d %Y" }}</p>
  {% include archive-single.html %}
{% endfor %}
