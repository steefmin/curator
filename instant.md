+++
categories = ["p2p", "WebTorrent", "fileshare"]
date = "2016-05-24T10:20:36+02:00"
draft = false
title = "instant"
description = "Instant peer to peer fileshare"
+++

Last week I have been busy with a small side project. [Instant](http://instant.h.steefmin.xyz) is P2P file sharing over WebTorrent, a bittorrent over WebRTC implementation. This page allows you to drop a file in your browser and seed it while you have that browser tab open. Share the link that is generated and a friend can receive it. If your friend leaves the page open as well, he will also seed the file. 

Data is not stored on a server anywhere. This has advantages and disadvantages. If you close your browser, you stop sharing. But privacy is more in your own hands. 

Because it makes use of WebTorrent, it als works with other WebTorrent implementations as [instant.io](http://instant.io), [WebTorrent Desktop](https://webtorrent.io/desktop) and [many others](https://github.com/feross/webtorrent/blob/master/docs/faq.md#who-is-using-webtorrent-today).

You can test it out yourself with two browser windows. 
