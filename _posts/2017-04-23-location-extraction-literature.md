---
title:  "Extracting and Mapping Location Mentions From Texts To The Ground"
date:   2016-05-23 19:38:00
description: In this post, I write about the importance of location name extraction and the common techniques to extract them from texts.
---

[This post was original shared in Kno.e.sis Research Blog](http://blog.knoesis.org/2016/05/extracting-and-mapping-locations.html)

The meaning of a social media post can be a function of location. For example, the meaning of "The Main Street bridge is closed" is ambiguous without establishing exactly which bridge is in question (The one in Danville, VA or in Columbus, OH). At the same time, location information metadata is sparse, forcing analysis of social media content and context to disambiguate alternative mappings. This article uncovers some of the persisting challenges in the recovery of location information from content and context: Text normalization, implicit location information, Geoparsing, and the future steps of our research.

Consider the Tweet in Figure 1. It contains valuable, but implicit information for Disaster Response and Flood Modeling. Here the user provides the level of water during a  storm surge. Knowledge-based inference supports the enrichment of this claim to determine that the water level is around 3 meters (to the height of a first floor)1. If we knew the location of Ganapathi colony, this quantitative data can inform a storm surge model to predict the direction of the surge and the danger it might pose.

<blockquote class="twitter-tweet" data-cards="hidden" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/hashtag/ChennaiRainsHelp?src=hash">#ChennaiRainsHelp</a> water hitting first floor. need to evacuate Ganapathi colony. <a href="https://twitter.com/ChennaiRains">@ChennaiRains</a> <a href="https://twitter.com/ndtv">@ndtv</a> <a href="https://t.co/rNvx4i4JVH">pic.twitter.com/rNvx4i4JVH</a></p>&mdash; Balaji (@blaji) <a href="https://twitter.com/blaji/status/671942649570398208">December 2, 2015</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>
Fig. 1: An example tweet from Twitris campaign of Chennai Flood 2015.

At Kno.e.sis center, one of the goals of our NSF-funded project ([Social and Physical Sensing Enabled Decision Support](http://wiki.knoesis.org/index.php/Social_and_Physical_Sensing_Enabled_Decision_Support) is to make information available in social media accessible to first-responders to prioritize relief efforts. Mapping events to locations in order to attach ground-based information to locations on the map will allow us to achieve the desired goal. In contrast to physical sensors, the resolution of social media data is a function of population rather than specialized infrastructure. In the case of lack of sensor/IoT coverage or malfunctioning of sensors, citizen sensing can provide information about ground status to compensate for missing data.

Using [Twitris](http://twitris.knoesis.org/), Kno.e.sis' robust semantic social web platform that has been used in a [number of real-world scenarios](http://knoesis.org/amit/media), we collect real-time, event-centric twitter data to understand social perceptions. During the 2015 Chennai floods, we created a [Twitris campaign](http://j.mp/Kchennai) that  collected  around 508K relevant tweets. Determining location is an important part of making these tweets informative. Location extraction and mapping is performed in two steps: Toponym extraction and Geoparsing.
