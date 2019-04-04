---
title: "What I'm Working On"
layout: single
permalink: /
---

(As of March 2019)

* [Functional Data Structures & Algorithms](https://amilkov.gitbook.io/fp/) - This is a GitBook about implementing common algorithms and data structures, the kind you'd see in your college textbook on the subjects if you were a C.S. major and the kind that pop up in technical interviews...at least the broken-tech-interview-industry kind, in the functional paradigm. You may think these are only for circus performers whose full time job it is to solve these kinds of teaser style questions on Leetcode and interview 5 times a year at each Big 10, but I have observed, like said performers will certainly contend, studying them has made me a better developer. So there's merit in this and regardless of what you think about a given company's interview process, they're not going to change it for you so you just gotta brave through. And this will help! So if you have a passion for FP or you have an interview coming up for a Scala dev spot, check it out
* <img src="/assets/images/aws4cats.png" width="50" height="50" alt="Computer Hope"> [aws4cats](https://aws4cats.milkov.ml) this is a `cats-effect`, `http4s-core`, `fs2` wrapepr around the new 2.0 AWS Java SDK. So far I'm supporting SQS, S3, and DynamoDB. With longer term plans for SNS, RDB, and...well if the case is made, whatever really

# Articles

{% for post in site.posts %}
  <p style="margin:50px 0 0 0;font-size:15px;"><i class="far fa-calendar-alt" aria-hidden="true"></i> {{ post.date | date: "%b %d %Y" }}</p>
  {% include archive-single.html %}
{% endfor %}
