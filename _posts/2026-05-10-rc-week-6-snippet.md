---
layout: post
title: "[RC] Week #6: Half-batch checkin"
published: true
date: 2026-05-10 09:00:00
tags:
  - rc
  - coding-retreat
  - snippets
---

## Context about what "Recursers" do day-to-day
See my [Week #2 snippet]({% link _posts/2026-04-08-rc-week-2-snippet.md %}) for details.
Here's a [LinkedIn short video](https://www.linkedin.com/posts/nicholasbs_15-years-in-and-theres-still-no-place-else-ugcPost-7450566979393933312-9NzQ) where Nicholas (RC CEO) explains it really clearly.

## Week 6 Progress (official Half Batch)
Last week I pivoted my project from re-implemeting Android calculator in Zig to re-implementing UNIX dc calculator in Zig.

I started learning `dc` syntax and functionality, the syntax is definitely something not from this generation.
It's humbling to see and understand the design of a tool that's being around for more than half of centrury.
In university, I practiced some [code-golf](https://en.wikipedia.org/wiki/Code_golf), back then I used Perl mostly for that purpose.
Dc is a great language for code-golf - the shortest version of a program to print itself is: `dc -e '6581840dnP'` (as provides to me by a fellow RC person).
How it works in amazing!:
```text

Breaking it into parts, we have:

6581840 <-- put this number onto stack, in 256-based-encoding this number reads as "dnP"
d       <-- copy top of the stack, so we have that number twice
n       <-- this will pop the top of the stack and return it (as regular decimal)
6581840 --> first part of the output that you see
P       <-- prints top of the stack as encoded into 256-base number, this is beautiful hack to add string manipulations into a calculator
dnP     --> second part of output
```

Most of my week I spent on the ["AI Pro Fisco" project](#ai-pro-fiasco).
Which is to organized personal finances from multiple US and EU accounts into a sigle pivot table in Google Sheet.

## Challenges
Not much focus time last week, as we continue to settle in our place in Portugal.

:point_right: An actual data-point from doing that -- when planning a career break and estimating monthly expenses -- **mutiply your eastimate by two and add 20%** =/

## AI Pro Fiasco :poop: {#ai-pro-fiasco}
:point_right: Key observation I got is -- sticking to plain-text/git managed/agent-cli interface is best way to consume tokens and be productive with it.

Google provides an option to have an "AI Cool Aid" in the Google apps (Docs, Sheets, GMail, Drive) --
called ["AI Pro"](https://support.google.com/googleone/answer/14534406?hl=en&ref_topic=16477118&sjid=15664429330118666705-EU).

I use Drive, Docs and Sheets mostly. For each I summarized the current UX when "AI Pro" is ON,
and a common task for me that Gemini failed with bright colors.

### Google Drive
* Task it failed miserably - move all CSV docs from directory A to B and create subdirectories for every month. Turns out AI for google drive can't create directories or move files between directories ... sigh
* Side note: None of those "AI" features are integrated into Desktop Mac app for Gdrive. It's not even possible to get a link to Google doc from the desktop app(!)

![Google drive UI](/static/google-drive-gemini.png)

### Google Docs
* 4 ways to get to same "Gemini" side bar, not clear what's the difference between entry points
* Task it failed miserably at:
  - _"Reverse the order of entries in the document, make it from neweset to oldest and grouping by month and collapse those"_
  - The reply was half truncated document with semi-randomly shuffled text
  - I think at some point context window got truncated / compacted?

![Google docs UI](/static/google-docs-gemini.png)

### Google Sheets
* At least 4 different ways(!) to get to Gemini side bar, and different from Google Docs, to get to Gemini side bar
* My fav one is the `AI()` formula, which never work for me. But it's amusing as a source of nonsence-generation
* Task it failed miserably at:
  * Take all sheets in directory A and merge them into a single sheet them generate a pivot table.
  * The esult was either that it can't create a spreadhseet/can't read a spreadheet or generate a sheet with 10 record and some gardage data at the end.

![Google sheets UI](/static/google-sheet-gemini.png)

