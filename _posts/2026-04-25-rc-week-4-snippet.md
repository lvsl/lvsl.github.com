---
layout: post
title: "[RC] Week #4: Ziglings are done, side-project that I procrastinated on"
published: true
date: 2026-04-25 20:00:00
tags:
  - rc
  - coding-retreat
  - snippets
---

## Context about what "Recursers" do day-to-day
See my [Week #2 snippet]({% link _posts/2026-04-08-rc-week-2-snippet.md %}) for details.
Here's a [LinkedIn Short video](https://www.linkedin.com/posts/nicholasbs_15-years-in-and-theres-still-no-place-else-ugcPost-7450566979393933312-9NzQ), where Nicholas (RC CEO) explains it really clearly.

## Week 4 Progress
Completed all [Ziglings](https://codeberg.org/leov/exercises/commits/branch/main/search?q=committer%3ALeonid&all=).
Was it worth it? Maybe; it was a good intro to different parts of the language and ecosystem,
but actual learning happened when I overcame some challenges:
* I've added a progress bar for my version of Ziglings (as part of that, I learned how to handle memory
  and string formatting).
* I got a new perspective on data structures; plan to read the ["Data Oriented Design"](https://www.dataorienteddesign.com/dodbook/) book.

I've collected some interesting "quirks" about the language below.

## Challenges
I had a day of firmware doom. I got a car with a fancy OS (based on AOSP) and managed to brick it
during the over-the-air upgrade. The same day, the laundry machine got corrupted firmware and locked my
clothes inside...

![MINI Firmware Upgrade](/static/car-software-upgrade.jpeg)
![Washing Machine Fail](/static/washing-machine-fail.jpeg)

That reminded me how integral software is to our day-to-day chores.

### Procrastination
I procrastinated on a personal finance tracker project. In the US, I used the Monarch app, and it was great.
Worked 95%. In the EU, it doesn't really work.

When I actually cornered myself to get it done, I had an idea to purchase a ["Google AI Pro"](https://support.google.com/googleone/answer/14534406)
subscription to get this task completed quickly, since with "AI Pro" all Google apps get those magic
"Gemini" buttons. Google Sheets, in particular, gets the magic formula, [`AI("your prompt")`](https://support.google.com/docs/answer/15820999).

| **Observation 1:** |
| :----------------- |
| :point_right: _Having a financial commitment forced me to start making progress._ |

When I actually began to work on this task, the "thinking" Gemini model built a plan with a series
of steps. At this point, I was able to make incremental progress.

| **Observation 2:** |
| :----------------- |
| :point_right: _This very specific type of procrastination—where a "task" is not an atomic simple task like taking out the trash or paying a bill, but a whole "project" with multi-step planning and readjustment..._ |

In the end, I was really frustrated with the "AI Pro" service; it's really poor quality. I ended up
using Gemini in the form of "Stack Overflow that knows my context." After a couple of evenings, I was
able to squeeze out the three formulas I needed to use—(`VLOOKUP`, `IMPORTRANGE`, and `QUERY`).

In particular, a task that should be "easy" for LLMs—_given a list of credit card transactions,
generate a regular expression to match them to categories in `@file-with-categories`. Use the web-search
tool to find details about transactions_—Gemini really struggled to produce output for this.


## Quirks in Zig that I found interesting / worth exploring more
(P.S. [KEXP music performance](https://youtu.be/Te1HkBx7rDw), I listened to this as a soundtrack while doing Ziglings).

* `!?[]const u8`
* `@typeInfo(Config).@"struct".fields`
* `&entry.*.?`
* `const my_letter: ?*[1]u8 = &letter;`
* `@TypeOf("foo") == *const [3:0]u8`
* `some_tuple.@"0"`

:eyes: :eyes: :eyes:
