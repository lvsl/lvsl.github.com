---
layout: post
title: "[RC] Week #3: Journey through Ziglings and building up my coding routine"
published: true
date: 2026-04-16 16:20:00
tags:
  - rc
  - coding-retreat
  - snippets
---

## Context about what "Recursers" do day-to-day
See my [Week #2 snippet]({% link _posts/2026-04-08-rc-week-2-snippet.md %}) for details.

## Week 3 Progress
Completed "83.19%" of [Ziglings](https://codeberg.org/leov/exercises/commits/branch/main/search?q=committer%3ALeonid&all=) -
tiny coding problems to learn the basics of Zig.
How do I know the exact number? It's because I [added progress indicator](https://codeberg.org/leov/exercises/commit/02931bfccffae5be767ea3209e51bccdee04b2e3) to my fork of Ziglings to keep myself motivated.

This worked well for me, so [I proposed](https://codeberg.org/ziglings/exercises/issues/399) to add it to the Ziglings project, which was accepted and
[implemented](https://codeberg.org/ziglings/exercises/pulls/403/commits/d918dbae59346b75cccbe69c4820bcbd7b28e57c) right away!.
This was also a good learning excercise for me, see the section below on
how I implemented the progress indicator VS how project owner implemented it.

## Challenges
Social commitments: This part is still challenging, I missed "the impossible project" day
(I wanted to try booting OpenBSD kernel in the browser). Maybe next time.
I changed my expectations from on-site "recurses", my experience is ultimately different. Not worse.  
I adjusted my goal to build a healthy coding routing that works for me.
I realized that coding daily is something I enjoy and was definitely missing out in past years.

I also starting to notice a gap in social life. I don't speak Portugese, so RC helps me to have a
discussion in English once in a while (coffee chats are good for that!).

## Details on Ziglings progress bar implementation
While it might be a trivial feature, it was a good first example for me to actually read some Zig code.
It was even more interesting, since it's a change done via `build.zig` which is how Zig project
[builds itself](https://codeberg.org/ziglings/exercises/pulls/403/commits/d918dbae59346b75cccbe69c4820bcbd7b28e57c).
I really like that since I don't have to learn another DSL (e.g. Bazel, CMake, etc) to put a project together.

tl;dr:
* Math is different. I compute percents using floats, Chris computes size of the progress bar using
  unsigned integers
* Memory management: I'm using global mutable variable (boo!), while Chris allocates array on the
  stack inside a function.


Specifically I like this part:
```(zig)

fn printProgress(num: usize, max: usize) void {
	const bar_width: u32 = 60;

	const filled_len_u64 = (@as(u64, num) * bar_width) / max;
	const filled_len = @as(u32, @intCast(filled_len_u64));
```
There's a lot going on with integer types here. `usize` converted to `u64`, and then everything converted to `u32`.
I don't know why.

```
	 var bar_buf: [bar_width]u8 = undefined;

	 for (0..bar_width) |n| {
		const ord = std.math.order(n, filled_len);
		bar_buf[n] = switch (ord) {
			.lt => '#',
			.eq => '>',
			.gt => '-',
		};
	}
```
This is first time I see this [kind of function](https://ziglang.org/documentation/master/std/#std.math.order). But I like this patter.

```

	 std.debug.print("\rProgress: [{s}]  {d}/{d}\n\n", .{ &bar_buf, num, max });
}
```
