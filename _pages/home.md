---
title: "What I'm Working On"
layout: single
permalink: /
---
2020

Moving away from programming language theory stuff to focus on distribute systems and engineering in general

* Introducing Rust at Square which entails porting the internal ecosystem necessary to run services here(I obviously miss functional programming and Go is about as far away as you get from scratching the itch). We are getting close to baseline support, have built a first (notifications) service during a hackweek that's running in our staging environment, and it will be really interesting to see what the reception will be like when we choose Rust to build something more critical and visible. Potential projects so far:
  * Envoy side cars: we want to push concerns like auth, which is currently implemented in every server supported language here (Go, Java, Kotlin, Python, Ruby) to our Envoy sidecars so we don't have to maintain code across all the aformentioned languages. Many (most) of these concerns have performance/throughput requirements so Rust seems like a good choice here.
* Doing a datastore rearchitecture of the service I work on, which manages merchant catalogs. We are currently on an EAV model in sharded MySQL which isn't very nice. Issues include:
  * It forces us to push up constraints to the application level since the model isn't relational so we can't take advantage of DB level constraints. This
* GraphQL for querying merchant catalogs: worked on a hackweek service to expose querying the service metnioned above via GraphQL's playground

2019

* [Functional Data Structures & Algorithms](https://amilkov.gitbook.io/fp/) - This is a GitBook about implementing common algorithms and data structures, the kind you'd encounter in a mostly undergraduate/some graduate course on the subject and, more pertinently, a technical interviews...in the functional (+ statically typed) paradigm however. So if you want to confuse the shit out of your interviewer, check it out
* <img src="/assets/images/aws4cats.png" width="50" height="50" alt="Computer Hope"> [aws4cats](https://github.com/amilkov3/aws4cats) this is a `cats-effect`, `http4s-core`, `fs2` wrapper around the new 2.0 AWS Java SDK. So far I'm supporting SQS, S3, and DynamoDB. With longer term plans for SNS, RDB, etc **EDIT** project is still up but I'm no longer working on it

# Articles

{% for post in site.posts %}
  <p style="margin:50px 0 0 0;font-size:15px;"><i class="far fa-calendar-alt" aria-hidden="true"></i> {{ post.date | date: "%b %d %Y" }}</p>
  {% include archive-single.html %}
{% endfor %}
