---
layout: slides
title: "Uplift your Linux systems programming skills with systemd and D-Bus"
permalink: /fosdem-2020-go-dbus-systemd-presentation
---

<div class="slider">
  <div class="slides">
    <div class="slide" id="slide-0">
      <header>
        <h1>Slide Title</h1>
      </header>
      
      <section>
      Slide Content
      </section>
      
      <footer>
        <progress value="0" max="6"></progress>
      </footer>
    </div>
    
    <div class="slide" id="slide-1">
      <h1>Hello, FOSDEM &#x1F389;</h1>   
    </div>
    <div class="slide" id="slide-2">
      <h1>Agenda</h1>
    </div>
    <div class="slide" id="slide-3">
      <h1>D-Bus & systemd</h1>
    </div>
    <div class="slide" id="slide-4">
      <header><h1>D-Bus Daemon</h1></header>
      
      <section>
<p>Reference implementation of D-Bus message bus is <a href="https://dbus.freedesktop.org/doc/dbus-daemon.1.html" rel="nofollow">dbus-daemon</a>.</p>
<h4>Monitoring daemon</h4>
<p>Message bus provides a set on standard interaces which can be introspected with:</p>
<pre><code>$ dbus-daemon --introspect
</code></pre>
<p>To query these interfaces, use <a href="https://dbus.freedesktop.org/doc/dbus-send.1.html" rel="nofollow">dbus-send</a>.</p>
<p>To see who's on the system bus:</p>
<pre><code>$ dbus-send --system \
            --print-reply \
            --type=method_call \
            --dest=org.freedesktop.DBus / org.freedesktop.DBus.ListNames
</code></pre>
<p>Get some runtime stats from the daemon:</p>
<pre><code>$ dbus-send --session \
            --dest=org.freedesktop.DBus \
            --type=method_call \
            --print-reply \
            /org/freedesktop/DBus org.freedesktop.DBus.Debug.Stats.GetStats
</code></pre>
      </section>
      
      <footer><progress value="4" max="6"></progress></footer>
    </div>
    <div class="slide" id="slide-5">
      <h1>systemd overview</h1>
    </div>
  </div>
</div>
