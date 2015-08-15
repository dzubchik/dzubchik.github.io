---
title:  "How to configure vrack at OVH"
date:   2015-08-15 22:23:00
categories: ruby, vagrant
---
[OVH](http://www.ovh.ie/) is one of the leading dedicated servers providers in the world.  Before the very beginning, I consider that you have successfully registered at OVH and have already confirmed your account (it was not easy for me). Let's see how to setup [Proxmox](https://www.proxmox.com/en/) cluster using such nice thing as [vrack](https://www.ovh.co.uk/solutions/vrack/) (virtual rack). 


First of all you should have ar least 2 servers. I tried to configure vrack using only one and then buy another and add it, but I failed because of many reasons (see comments to [this](http://borisguery.com/blog/2014/01/09/proxmox-3-plus-vrack-1-dot-5-with-both-public-and-private-networks-on-containers/) article). So, to have a success I advise beginning from 2 servers (yep, captain). Then, you should install Proxmox through ovh-panel or using KVM on all your servers. Than [add](https://www.ovh.com/us/solutions/vrack/configuration.xml) your servers to vrack. You can do with RIPE block of IPs and it variant is better than failover IPs because you can move them between all vrack servers. But, ovh takes off some of your IPs for internal using (ex. from /30 only 2 IPs is usable, from /28 - 12). After this, it is time to configure networks at our servers (consider we have only 2 servers: ovh-node-1 and ovh-node-2).

##Notes
* At this moment vrack available in 1.5 version only
* Proxmox used at version 3.4