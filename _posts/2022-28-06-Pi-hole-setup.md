---
title: Pi-hole block list from firebug
date: 2022-06-28 18:55:00 -500
categories: [homelab,kubernetes]
tags: [pode,kubernetes,pihole,firebug] #tag is always lower case
---

# Pi Hole block list (firebug)
So I have now Rancher running and I have been spinning pode like crazy, one of it is Pi-Hole with his default state, you 'only' got 100k domain blocked



I've came accross the video from [TechnoTim](https://www.youtube.com/watch?v=0wpn3rXTe0g){:target="_blank"} on adding 3 millions blocklist url using a repo called: [The firebug](https://firebog.net/){:target="_blank"}

I have then now enable all of the green and blue link and have tweaked the list after a week of utilization, I will revisit this thread as needed since adding block link might required you to watch your Audit log!



so far after a week of utilization I do feel having a successful block list worth 800k+



### Removed list

Here is the removed list so far (date - 27/06/2022 )

| Category   |      Link      |                Note                       |
|----------  |:-------------: |------------------------------------------:|
| Advertising |  https://adaway.org/hosts.txt | Blocking Facebook/Twitter |
