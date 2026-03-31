---
layout: post
title: Switching from Python+Django to Scala+Lift. Part 0
published: true
tags:
  - python
  - django
  - scala
  - lift
---

It's been the 4th year of my heavy usage of Python and Django.
I've been using Python since 2.4 and Django since 0.96.
Both Python and Django are great tools and are worth spending time mastering.

But the dynamic nature of Python has its own price.
If your application is heavily distributed and multithreaded,
well... the correctness and performance of your app will be hardly acceptable.

This is why using a language with static typing and a well-designed threading model might help a lot.

So I decided to perform an experiment:
Switch one of my apps to Scala+Lift and share my experience with you.

In the first place, as I don't know Scala, I'm going to learn it first.

These are some free books on Scala for newbies that I found:
* [Scala School, a book from Twitter developers](http://twitter.github.com/scala_school/)
* [Programming Scala, a book from ObjectMentor and again Twitter developers](http://ofps.oreilly.com/titles/9780596155957/)

And some books on the Lift framework:
* [Simply Lift](http://simply.liftweb.net/)
* [Exploring Lift: A book providing in-depth coverage of the Lift Web Framework](http://exploring.liftweb.net/)

So these are my goals for the first few weeks!

*P.S.*
*As a Python developer, I constantly type 'list' instead of 'lift'.*
