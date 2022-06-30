---
title: Pi-hole block list from firebog
date: 2022-06-28 00:18:00 -200
categories: [homelab,kubernetes]
tags: [pode,kubernetes,pihole,firebog] #tag is always lower case
---

I have now Rancher running and I have been spinning pode like crazy, one of it is Pi-Hole with his default state, you 'only' got 100k domain blocked

![Initial Pi-Hole stat](/assets/image/pihole-1.png)

I've came accross the video from [TechnoTim](https://www.youtube.com/watch?v=0wpn3rXTe0g){:target="_blank"} on adding 3 millions blocklist url using a repo called: [The firebog](https://firebog.net/){:target="_blank"}

I decided to do the same and have enable all of the green and blue links and have tweaked the list after a week of utilization, I will revisit this thread as needed since adding 'bulk links' might required you to watch your Audit log!

![Pi-Hole audit picture](/assets/image/pihole-2.png)

so far after a week of utilization I do feel having a successful url block list worth 800k+ and having a 47% block rate without noticing any issue visiting site

![Pi-Hole today](/assets/image/pihole-3.png)

### Removed list

Here is the removed list so far (date - 27/06/2022 )

| Category   |      Link      |                Note                       |
|----------  |:-------------: |------------------------------------------:|
| Advertising |  https://adaway.org/hosts.txt | Blocking Facebook/Twitter |
