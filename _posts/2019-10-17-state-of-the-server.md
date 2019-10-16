---
layout: post
title: Production Server Security Manifesto
published: true
tags:
  - cloud
  - infra
  - security
---

World has changed, mobile phones now have most secure environment, not server in a datacenter.
Take a look at [iOS](https://www.apple.com/business/docs/site/iOS_Security_Guide.pdf) and [Android](https://source.android.com/security/reports/Google_Android_Enterprise_Security_Whitepaper_2018.pdf) security, it's far beyond what's server looks like.

Mobile phones have "secure enclave"/"temper resistant env" in contrast, on servers there is ring-2/3 firmware, which is [a form of malware](https://lwn.net/Articles/738649/).

## Manifesto

### Secure hardware
We need analog of "secure enclave"/"temper resistent env" on server too. This should not be exposed to ring-2/-3 firmware. This has to be in hardware (with [CoreBoot](https://www.coreboot.org/) and [OpenBMC](https://www.openbmc.org/)).

But we should acknowledge, there's always going to be a [0-day](https://googleprojectzero.blogspot.com/2019/08/a-very-deep-dive-into-ios-exploit.html).

### Use ALL isolation OS can provide
Dismiss "container" vs "VM" mindset, it's a poor one.
Clearly, modern servers need both (e.g. [GC](https://gvisor.dev/docs/architecture_guide/), [AWS](https://firecracker-microvm.github.io/)) plus [sandboxes](https://chromium.googlesource.com/chromium/src/+/master/docs/design/sandbox.md).

### Software quality and reliability
[Privilege separation](https://en.wikipedia.org/wiki/Privilege_separation) is an [old](https://cr.yp.to/qmail/qmailsec-20071101.pdf) idea. Prioritize [quality](https://en.wikipedia.org/wiki/The_Power_of_10:_Rules_for_Developing_Safety-Critical_Code) and [reliability](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing) in distributed systems software over features.

