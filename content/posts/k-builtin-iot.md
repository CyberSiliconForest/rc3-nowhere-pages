+++
title = "K Builtin Iot"
date = "2021-12-27T02:37:01+09:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["", ""]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

# Security of Korean built-in home automation system

In South Korea, lots of new apartments are high-grade IT infrastructure certified. This certification requires the house has the following facilities by default:

Direct fibre-optic connection to the home
Home automation system
Built-in Wi-Fi access point
and more things that are not so much important in this context

As a result, lots of construction companies install those systems by default. The problem is, the devices' firmware security is not examined at all and, most of them are left unmaintained, unpatched for decades.

## Problems in the home automation system
### Always trusts internal network.
The built-in home automation system fully trusts the internal network. The control server sends the command without any authentication or encryption and, the home automation controller accepts the connection if it has a "valid" IP address. They do not care it is spoofed or not.

As a result, every room can send a spoofed packet to control someone else's home automation system.

### No one is listening to the ISM band. Right?
Lots of Korean built-in home automation system has integrated RF transmitter which opens the entrance door. So it must be designed with security in mind. Right?

However, lots of them just send RF signals without any anti-replay mechanism and can be replayed without much effort. Grab the SDR and replay the signal. Door unlocks.

### Let the telnet listen
[TODO]
