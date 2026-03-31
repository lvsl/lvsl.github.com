---
layout: post
title: Introducing "rot" - an ultimate stdout/stderr redirector and rotator written in pure Python
published: true
tags:
  - python
  - epoll
  - asyncio
  - subprocess
  - linux
  - rotation
---

**Code tested on Ubuntu 11.10**

Let's start with an example.
{% highlight python %}
p = subprocess.Popen(["spam_program", "-a", "-b", "-c", "100500"],
                     stdout=open('spam_out.log', 'wb'))
{% endhighlight %}

Imagine you have a `spam_program` that emits 20GB to stdout/stderr...
This program is one of many (hundreds or even thousands) that your test framework will start.

How can we handle this?
The first thought is to redirect to `/dev/null`, which is nice!
Except that the author of `spam_program` may want to grep through this massive log file.

The other option might be to set up `logrotate` each time the program is started to rotate this huge file.
The disadvantage of this approach is that you have to provide a config file for `logrotate` and have permissions to restart the daemon—and yes, it's a daemon...


Or you can simply run the program using rot. :)
Rot is a zero-install tool written in Python that requires no configuration.

You can find it here:
[http://github.com/lvsl/rot][repo]

Here is an example of its usage:
{% highlight sh %}
$rot --stdout-limit 100M \
     --stdout-count 4    \
     --stdout-file spam.stdout.log \
 -- spammy_program -a -b -c 100500
{% endhighlight %}

[repo]: http://github.com/lvsl/rot
