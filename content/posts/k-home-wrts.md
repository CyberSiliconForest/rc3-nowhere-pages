+++
title = "K Home Wrts"
date = "2021-12-27T02:35:38+09:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["", ""]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

# K-Home-WRTs

The concept of [router freedom](https://fsfe.org/activities/routers/routers.en.html) in South Korea is... well, not actively discussed in this moment.
The following figure is copied from BEREC report explaining the network termination point.
While using self-bought modem is "technically" possible, but this happens very seldom in reality and the modem is supplied by the ISP at a lower rate or even for free, regardless of the type of last mile (e.g. DOCSIS, FTTx, ethernet).
Most of the modems supplied by the ISP does not have an integrated router function, therefore either ISP-supplied router or a self-bought router could be used.
But wait a second... Ethernet as a last mile?
Most South Koreans lives in an apartment, and some apartment provide an ethernet connection directly to the each households, effectively eliminating any kind of modem and the router is freely choiceable.

![Illustration of network termination points](../images/ntp.png)

One of the most popular WRT in private households is [ipTIME](https://iptime.com/iptime/), followed by other Korean vendors such as WeVO.
There used be much more smaller Korean vendors selling home WRT, but they got consolidated in the market throughout the last decade.
Other global vendors such as Asus, Belkin, D-Link are usually bought by power users who is not satisfied by performance or software of what ipTIME or other Korean vendors provide, and have limited market presence.
This makes the situation hard in several aspects: local brand WRTs got OpenWrt support only in recent days, while the "stock" firmware of those WRTs have security holes and patched them in very clever way.

## ipTIME and GPL, OpenWrt

ipTIME in year 2007 claimed that "it is not fair that the GPL enforcement is harsh on small-sized enterprises", however, they slowly changed their mind and opened up some of their GPLed source codes around 2017.
In addition to this, they used Realtek -- infamous for their non-support status in OpenWrt -- in the past and changed their chipsets during mid-2010s.
As a result (and lack of general interest), not many devices of ipTIME is listed as supported device of OpenWrt[^openwrt-iptime].

(TODO)

## The Home Router (In)security

(TODO)

[^iptime-gpl]: [re: Firmware License 문제 문의 (in Korean)](https://iptime.com/iptime/?page_id=174&nType=UFFscUh5dURlaTNsU1BwZGlNV2czcWpRb3B1QldXK3Rad3IyazFGNUw5WHZXOHpneCtDN0gvZGpGNjMzQjNxelEzWXMwdEsyRmJuUTJoOU1BQmEwZVhEUFRneEV1bmlDY2hROUlMS2tVZCsrYnFEQVV6cmlnZjNVL3h1aG5HalhoQTlTU1hLRWsrSHJNSDFzVlYzbHhFWnVpUDliVzd1SGc2b3lRYVox)
[^openwrt-iptime]: [OpenWrt Wiki: Table of Hardware](https://openwrt.org/toh/start?dataflt%5BBrand*%7E%5D=iptime)
