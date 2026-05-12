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
Last week I pivoted my project from re-implementing the Android calculator in Zig to re-implementing the UNIX dc calculator in Zig.

I started learning `dc` syntax and functionality; the syntax is definitely not from this generation.
It's humbling to see and understand the design of a tool that's been around for more than half a century.
In university, I practiced some [code-golf](https://en.wikipedia.org/wiki/Code_golf); back then I used Perl mostly for that purpose.
Dc is a great language for code-golf - the shortest version of a program to print itself is: `dc -e '6581840dnP'` (as provided to me by a fellow RC person).
How it works is amazing:
```text

Breaking it into parts, we have:

6581840 <-- put this number onto stack, in 256-based encoding this number reads as "dnP"
d       <-- copy top of the stack, so we have that number twice
n       <-- this will pop the top of the stack and return it (as regular decimal)
6581840 --> first part of the output that you see
P       <-- prints top of the stack as encoded into 256-base number; this is a beautiful hack to add string manipulations to a calculator
dnP     --> second part of output
```

Most of my week I spent on the ["AI Pro Fiasco" project](#ai-pro-fiasco),
which is to organize personal finances from multiple US and EU accounts into a single pivot table in Google Sheets.

## Challenges
Not much focus time last week, as we continue to settle in our place in Portugal.

:point_right: An actual data point from doing that -- when planning a career break and estimating monthly expenses -- **multiply your estimate by two and add 20%** =/

## AI Pro Fiasco :poop: {#ai-pro-fiasco}
:point_right: Key observation I got is -- sticking to a plain-text/git managed/agent-cli interface is the best way to consume tokens and be productive with it.

Google provides an option to have "AI Kool-Aid" in the Google apps (Docs, Sheets, Gmail, Drive) --
called ["AI Pro"](https://support.google.com/googleone/answer/14534406?hl=en&ref_topic=16477118&sjid=15664429330118666705-EU).

I use Drive, Docs, and Sheets mostly. For each, I summarized the current UX when "AI Pro" is ON,
and a common task for me that Gemini failed with bright colors.

### Google Drive
* Task it failed miserably at - move all CSV docs from directory A to B and create subdirectories for every month. Turns out AI for Google Drive can't create directories or move files between directories ... sigh.
* Side note: None of those "AI" features are integrated into the Desktop Mac app for GDrive. It's not even possible to get a link to a Google doc from the desktop app(!)

![Google drive UI](/static/google-drive-gemini.png)

### Google Docs
* 4 ways to get to the same "Gemini" sidebar, not clear what's the difference between entry points.
* Task it failed miserably at:
  - _"Reverse the order of entries in the document, make it from newest to oldest and grouping by month and collapse those"_
  - The reply was a half-truncated document with semi-randomly shuffled text.
  - I think at some point the context window got truncated / compacted?

![Google docs UI](/static/google-docs-gemini.png)

### Google Sheets
* At least 4 different ways(!) to get to the Gemini sidebar, and different from Google Docs, to get to the Gemini sidebar.
* My favorite one is the `AI()` formula, which never worked for me. But it's amusing as a source of nonsense generation.
* Task it failed miserably at:
  * Take all sheets in directory A and merge them into a single sheet, then generate a pivot table.
  * The result was either that it can't create a spreadsheet/can't read a spreadsheet or it generated a sheet with 10 records and some garbage data at the end.

![Google sheets UI](/static/google-sheet-gemini.png)


In conclusion, this is not suprising -- as there multiple groups of people working on competing set of AI-related projects. Currently apprach is "throw some AI on the wall and see what sticks"... My next plan is to switch to plain text Markdown/CSV/git repo and work with Gemini CLI to implement those simple tasks.
