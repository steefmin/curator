+++
categories = ["IPFS","cjdns"]
date = "2016-04-26T13:49:32+02:00"
title = "a distributed world"
description = "Distributed networks"
+++

Distributed networks fascinate me. The way that the network is truely supported and held up by the nodes, in stead of the backbone. In retrospect it should have been the way that systems were designed in the first place. The resilience: fails one of the nodes, then it's only the problem of that failing node. Other traffic will route around the problem and still arrive at the destination. There are many projects trying to achieve this. The one I'm most interested in is [cjdns](https://github.com/cjdelisle/cjdns). 

cjdns is a 'friend of a friend' network that cryptographically verifies nodes and routes traffic among them. It works over all kind of connections, being ethernet, wireless, Ad-hoc, UDP links on the internet or any other transmission that supports packet routing. 

But this only fixes the transmission of data over a network. The second step has to make sure information is stored and accessible freely and quickly. Bring in IPFS.  

>	IPFS is a distributed file system that seeks to connect all computing devices with the same system of files. In some ways, this is similar to the original aims of the Web, but IPFS is actually more similar to a single bittorrent swarm exchanging git objects. You can read more about its origins in the paper IPFS - Content Addressed, Versioned, P2P File System.	
>	IPFS is becoming a new major subsystem of the internet. If built right, it could complement or replace HTTP. It could complement or replace even more. It sounds crazy. It _is_ crazy.

From the IPFS [Readme](https://github.com/ipfs/ipfs).

But both these systems currently consist of a lot of sites spread all over this new web. Finding them is [hard](https://github.com/ipfs/faq/issues/30#issuecomment-172756566). So I'll make it my goal to regularly post some new interesting site here, to keep you informed on the most usefull and fun things to do on this new web. 

If you have any tips, please let me know. 
