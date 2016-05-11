+++
Categories = ["IPFS"]
date = "2016-04-28T16:24:07+02:00"
title = "hugo and ipfs"
draft = false
+++

As some might have noticed in the tiny lettering on the bottom of this page: This page is built with [Hugo](http://gohugo.io). Hugo is a fast static website builder. Basicly, you take a theme, write some content, *compile* and it will generate one folder with you entire website. All well and done. 

There basically are two reasons I like Hugo. 

>	1: I can't do layout

I know my HTML, I can do CSS and JS. But don't let me design a page or pick a set of colors. It's the same reason I love using [LaTeX](https://www.latex-project.org/) for all my reports. 

>	2: IPFS. 

And one of it's main concepts: Content addressing. In IPFS, a file is known by the hash of it's content. That way, content in location A and in location B, will always have the same handle. This is usefull because someone that wants that content can receive it from anyone. And he will know it is the right content because the handle is cryptographically linked to the content. 

Because IPFS is content addressed, the content on this site needs to largely be the same. Content can not be generated dynamically, because changeing the content will change the handle. And any links with the handle, will therefore only link to a certain set of content. 

Because Hugo generates static sites, they are an ideal couple. 

Every time I generate a new site with Hugo, it needs to be added to IPFS. The IPNS hash needs to point to the newest version. And finally the old version should be added to the post with the old versions list. To do this for me consistently, I wrote this batch script:

	#! /bin/bash
	# hugo site generation and publishing to ipfs

	# check current directory
	curdir=$(pwd -P)
	if [ "$curdir" != "/path/to/hugo/project/" ]; then
	   	echo "not in proper directory"
   		exit
	fi

	# clean published version
	rm -r published/
	mkdir published

	# generate hugo site
	hugo --destination published/

	# add to ipfs
	hash=$(ipfs add -r -q published/ | tail -n 1)

	# pin new version
	pin=$(ipfs pin add $hash)

	# publish hash to ipns
	ipns=$(ipfs name publish $hash)

	# add new hash to old versions post
	date=$(date +"%Y-%m-%d")
	echo "$date: [/ipfs/$hash](http://ipfs.io/ipfs/$hash)\n\n" >> content/post/old-versions.md

	#return ipns output
	echo $ipns


