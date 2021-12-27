+++
title = "Insecam"
date = "2021-12-27T04:28:34+09:00"
author = ""
authorTwitter = "" #do not include @
cover = ""
tags = ["", ""]
keywords = ["", ""]
description = ""
showFullContent = false
readingTime = false
+++

# Insecam and Korea

[Insecam](http://insecam.org) is a website which crawls the insecure network cameras connected to the Internet without any authentication throughout the world.
According to the [website's FAQ](http://insecam.org/en/faq/), they are collecting the network cameras without password protection and listing the live video feed of them.
They also claims that the cameras are not hacked, but the vulnerable software may enable the remote access without any authentication.
The website provides a grouped view by camera manufacturers, installed countries and cities, places.
Unless the network camera is supposed to broadcast a public video stream, the owner of the network camera is supposed to apply at least a proper password authentication to protect their video stream.

The installation and usage of video surveillance devices are regulated by Personal Information Protection Act[^pipa], Article 25.
According to the law, the owner of the video surveilance device must secure their device in order to protect the personal information.
In addition, the device must not record any voice and record places outside of its intended purpose.
Regardless of the legal code, the number of video surveilance devices installed by public institutions are in constant rise[^public-cctv-stats], and about 1.3 million devices are installed as of 2020.
There is no accurate number of video surveilance devices installed by private person, but one report estimates the number as 13 million devices in 2017[^cctvnews].
In addition, about 89 percent of Korean cars have dashcams installed in 2019[^dashcam].

At least the legal code seems to be good, but how come the picture below became the reality?

![South Korea is in 2nd place of Insecam](../images/insecam_korea.png)

As of the time of the writing, South Korea is ranked 2nd in the [Insecam](http://insecam.org)'s country list.
To make things even more ironical, Insecam website is blocked in Korea by Korea Communications Standards Commission (KCSC).
The block was decided around early 2016[^incheonilbo], to "protect" the privacy of Korean people.
This block is not effective against those who outside of Korea, and as everyone knows, cybercriminals these days do not know the national border.
The root cause of this problem -- unprotected network camera -- remains unsolved, as Korean police decided that there is no way to inform the individuals on the problem of their network camera[^incheonilbo].
To make things more worse, rebadged cheap camera by Korean companies often do not get adequate support from the original manufacturer, leaving the users vulnerable.
This was demonstrated in Petzview incident around 2018.

## The Petzview Incident

There was a network camera named Petzview, which was marketed towards companion animal owners to monitor their loved ones from outside of their home.
The device was sold for several years, and was used by not only individual peoples but also by veterinary clinics too.
The hardware itself was not that special as seen in the image below.

![Petzview hardware](../images/petzview.jpg)

In October 2018, Petzview announced that they will shut down their web service[^news1] to share the live footage of Petzview devices[^archive] and discontinue the mobile app to control the network camera.
According to the news report, an owner of Petzview network camera found that their camera had been compromised in **2012**, and found the security vulnerability in **2014**, which he exploited to illegally record the other Petzview users for at least 4 years.
The attack was only discovered in 2018, and the hacker was arrested for privacy invasions by illegal recording.
Well, if you look into the source code of the web archive, you may find interesting thing there which tells about the security mindset of the Petzview designers :(

As long as these kind of insecure network cameras are connected to the Internet without software updates, and Korean authorities are burying their head in the sand like just blocking the Insecam website instead of regulating the market tightly, we don't believe that the number of network cameras listed in the Insecam will decrease.

[^pipa]: [개인정보보호법 (in Korean)](https://www.law.go.kr/%EB%B2%95%EB%A0%B9/%EA%B0%9C%EC%9D%B8%EC%A0%95%EB%B3%B4%EB%B3%B4%ED%98%B8%EB%B2%95), [Non-binding translation in English](https://elaw.klri.re.kr/kor_service/lawView.do?hseq=53044&lang=ENG)
[^public-cctv-stats]: [공공기관 CCTV 설치 및 운영 (in Korean)](https://www.index.go.kr/potal/main/EachDtlPageDetail.do?idx_cd=2855)
[^cctvnews]: [공공안전 책임지는 CCTV, 보급의 역사와 현황 (in Korean)](https://www.cctvnews.co.kr/news/articleView.html?idxno=120089)
[^dashcam]: [점점 더 강조되는 ‘차량용 블랙박스’의 중요성, 이제 운전자의 ‘필수품’으로 자리잡아 (in Korean)](https://www.trendmonitor.co.kr/tmweb/trend/allTrend/detail.do?bIdx=1780&code=0304&trendType=CKOREA)
[^incheonilbo]: [공기관·유치원·학교 CCTV 해외노출 '무방비' (in Korean)](http://www.incheonilbo.com/news/articleView.html?idxno=704639)
[^news1]: [해킹됐던 반려동물 전문 IP카메라 사이트 '펫츠뷰' 내달말 폐쇄 (in Korean)](https://www.news1.kr/articles/?3467060)
[^archive]: [Archived copy of Petzview](http://web.archive.org/web/20180831090559/http://petstory.co/bsbbs/list?tn=petview)
