+++
title = "Kve"
date = "2021-12-27T04:26:47+09:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["", ""]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

# What is KVE?

South Korea is always actively insisting on the "platform sovereignty".
After a boom caused by Squid Game on Netflix, some Koreans thought that Netflix is not giving a fair share to Korean studios[^koreatimes] and complained why there is no local equivalent of Netflix which can attract users like what Squid Game did.
Even an ISP sued Netflix[^dtve] citing that they are not paying enough for the traffic caused by Netflix services.
Well, we don't want to discuss on the Squid Game or why some of Google and Apple services are not available in Korea in this article, but that kind of mentality is prevalent in various places of Korean society.

As a security researcher, everyone should know [CVE (Common Vulnerabilities and Exposures)](https://www.cve.org/).
MITRE Corporation maintains a nice public database of disclosed computer security flaws.
It benefits many system administrators and security researchers by sharing the known vulnerability and helping them to fix those holes.
Also, the software vendors also include CVE numbers for their security patches in order to announce what security problem they fixed.
The CVE is used globally and the vulnerability database also contains region-specific products and their vulnerabilities too.

Then here comes the "platform sovereignty" mind of Korean institution.
Having a local equivalent of CVE could be beneficial for overcoming language barrier, since CVE is only available in English.
Small-sized companies may cite the language problem as the reason of not-observing best practice and fixing their security vulnerabilities, which could be mitigated by publicly funded institution giving some CVE translation[^krcert-infos].
Now meet KVE, which is designed "local equivalent" of CVE.

We do not deny that a localized vulnerability device can help the local software vendors and users.
However, the biggest difference between CVE and KVE is that the latter database is only available internally within KrCERT.
If you search with the keyword such as "KVE vulnerability", what you will get is mostly the notice in Korean and a line in changelog mentioning that the vulnerability had been fixed.
Hmm, now what? Why there is no information of the vulnerability itself publicly available at all, even its abstract information such as severity, impact, type of vulnerability?
Is it to covering the mistakes made by local (small) companies and not to ruin their reputation?
We really don't know and want to know why we can't see the whole database, not the fragment.

Following examples are how the KVE ID is used:

 * An IP camera company "disabled" ONVIF access due to the missing access control on ONVIF interface allowing anyone to see the stream[^sjnetworks]. Note that "disable the feature because we can't secure that" mindset is quite prevalent among small Korean companies.
 * An archiver software patched NSIS and TAR file handling, citing the KVE ID[^bandizip]. No one knows what is the exact problem.
 * A web CMS software patched a security hole citing the KVE ID[^gnuboard]. Details could only be guessed from the patch.


As a security researcher, we find that the non-public vulnerability database targetting the public produces make little or no sense at all.
Security researchers waste time writing reports about duplicated vulnerabilities because they do not have access to the database.
End-users and system administrators are unable to know what threat they are currently exposed because the information is kept secret, and have to rely on the mercy of software vendors.
The KVE ID's existence is only known to researchers through the KISA bug bounty program, which replies to the researcher's mail with their useless database reference ID.
We believe that opening up the KVE database will bring more positive effect in the future.

[^koreatimes]: [Book reveals uncomfortable truth about 'Squid Game's global success ](https://www.koreatimes.co.kr/www/culture/2021/12/142_319104.html)
[^dtve]: [Netflix says paying SK Broadband over Squid Game surge creates ‘anti-competitive environment’](https://www.digitaltveurope.com/2021/10/25/netflix-says-paying-sk-broadband-over-squid-game-surge-creates-anti-competitive-environment/)
[^krcert-infos]: [취약점 정보 - KrCERT (in Korean)](https://www.krcert.or.kr/data/secInfoList.do)
[^sjnetworks]: [QCAM-K1 보안취약점 발견에 따른 패치 안내](http://www.sjnetwork.co.kr/sjnetworks/bbs/board.php?bo_table=notice&wr_id=295)
[^bandizip]: [반디집 업데이트 정보](https://www.bandisoft.com/bandizip/updateinfo/?kr)
[^gnuboard]: [gnuboard/gnuboard5](https://github.com/gnuboard/gnuboard5/commit/c2922aaa13fe5d9ffabd5370d67125209d5bb5a8)
