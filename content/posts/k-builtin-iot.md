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

# Security of Korean Built-in Home Automation System

Apartments are the most wanted form of housing in South Korea, and the prices of apartments are one of the delicate theme of politics too.
One of the important factor affecting the apartment pricing is available network infrastructure and availability of home automation system.
Even there is a certification on the high-speed telecommunication[^bica] in the aparements, which mandates optical fibre and/or ethernet link to the house and inside the house.
If an apartment does not have an infrastructure for even medium-speed Internet, this actually negatively affects the price of the property.

To make things more interesting, there is even home network certification[^bica-hnet] which defines the minimal required home networking facilities in the apartment.
To get the certification, at least these type of installation is required:

 * Direct fibre-optic connection to the home
 * Home automation system
 * Built-in Wi-Fi access point
 * and more things that are not so much important in this context

Because this is considered as a premium in housing market, newer apartments (especially built after 2010s) applies for this certification.
There is a security requirement in the Class AAA Home IoT certification[^ksecurity], which sounds okay in the first glance.
The security requirement itself is reasonable enough, and there are some "certified" devices in the market[^ksecurity-list].
Sounds good up to this moment, but...

## Hacked Wallpads on Raidforums

On 15th October 2021, a Raidforums user opened a thread claiming that they are selling the video footage from hacked home automation systems in Korea[^rf].
This also became sensational in Korean news reports.
The person also posted a list of hacked apartments (original images deleted in RF), spanning around the whole nation.
The video footage contains internals of private houses, and could even contain explicit images and videos too.
Because most of affected people are not tech-savvy, and it is usually not possible to replace the home automation system by the home owners themselves, only a mitigation such as covering the camera is proposed as a solution.
The ultimate solution is proper security of the home automation system, though not all affected vendors are able and willing to do that (especially for older discontinued models).

How this things could happen even though there is "certification"?
In reality, the devices get very poor maintenance after its initial installation and small-sized vendors also discontinue their home automation products quickly.
The lifetime of home automation devices are shorter than the lifetime of the building in reality, and older discontinued devices eventually ends up in a dead end without any security patches and updates.
They also charge quite a lot of amount to home owners especially for discontinued devices[^twocpu].

We have investigated some of home automation systems in Korea, and found interesting bugs and vulnerabilities here and there.

## Bugs and Problems of Home Automation System

### Blinkenlights!
The built-in home automation system fully trusts the internal network. The control server sends the command without any authentication or encryption and, the home automation controller accepts the connection if it has a "valid" IP address. They do not care it is spoofed or not.

As a result, every room can send a spoofed packet to control someone else's home automation system.

### No one is listening to the ISM band. Right?
Lots of Korean built-in home automation system has integrated RF transmitter which opens the entrance door. So it must be designed with security in mind. Right?

However, lots of them just send RF signals without any anti-replay mechanism and can be replayed without much effort. Grab the SDR and replay the signal. Door unlocks.

### Let the telnet listen
[TODO]

[^bica]: [심사기준-공동주택, 초고속정보통신건물인증 (in Korean)](https://www.bica.or.kr/standard/house.do)
[^bica-hnet]: [심사기준-홈네트워크건물, 홈네트워크건물인증 (in Korean)](https://www.bica.or.kr/standard/building.do)
[^ksecurity]: [홈네트워크건물인증 보안점검 소개 (in Korean)](https://www.ksecurity.or.kr/kisis/subIndex/268.do)
[^ksecurity-list]: [홈네트워크건물인증 보안점검 결과 (in Korean)](http://222.239.254.182/user/extra/kisis/358/iot/iotList/jsp/LayOutPage.do?setIdx=&column=&search=&spage=1), [IoT 보안인증 현황 (in Korean)](https://www.ksecurity.or.kr/user/extra/kisis/356/iot/iotList/jsp/LayOutPage.do)
[^rf]: [Condominiums Automated Home System Hacked in South Korea?](https://raidforums.com/Thread-Condominiums-Automated-Home-System-Hacked-in-South-Korea)
[^twocpu]: [홈 오토메이션 고장 및 교체 문의 (in Korean)](https://www.2cpu.co.kr/QnA/395000)
