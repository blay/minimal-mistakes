---
layout: post
title: Unique Identifiers
tags: meta
summary: Thought on using time-based Unique Identifiers as universal reference links
image:
  feature: uid_narrow.png
---

Zettelkasten.de uses a clever way of making unique identifiers by a YYMMDDHHMM timestamp. Since it is rare the one creates several notes the same minute, this works as a unique identifier. If notes are generated in bulk, a script can easily rename them to get unique identifiers.

The title can then be changed continuously because the link is just a reference to this identifier. Or it can be a reference to the whole note title, but a search for the note need only to use the unique identifier. They also simply use a §-sign to designate that it is a link so a search for § would only turn up links.

When viewing notes and outlines, a link can always be accompanied by an explaining reference, either the current title or the content that is referred to or the reason for the placement of the link. This gives a hint of what to find and what to do with that material.

Another benefit is that UIDs are simple a unique 12 digit number that can be attached anywhere. It can be includes as a comment in the middle of a file and then references from there. A markdown footnote can have a UID to ensure its global uniqueness (imagine linking to a footnote in another note seamlessly!). An image can have its unique id as long as nothing else in the file system was created that very same minute (in which case you need to fake it and add a minute). Anything that can be searched by the system can be referenced. It is also easy to add identifiers to unlisted old files or places by simply changing the name to include an identifier. The identifier signifies the time file became a unique target.

Even physical objects and index cards can have UIDs based on the same principle! You are not creating anything on your computer when you are writing index cards. This could be used to distinguish identical objects from each other, for example different routers of the same model. Since the system is time-based, you only need a watch to be able to place a correct UID.

A downside of the system is that scripts that visualize link relations would be hard to interpret since they would only contain the unique identifier and not a descriptive title. They could however be updated to search for the identifier and replace them with the full title as it currently stands. This can be done by "ls 201506222214*" or title=$(ls $link).

To make syntax highlighting possible in markdown, it would work to put the § link within [brackets] where at least vim puts a syntax color on it. A more long-term solution would be to code a highlighting for §word

§201506222204

With the right markdown preprocessor the possibilities are endless once the unique identifiers have made the connections. I imagine a preprocessor that would expand each §reference by looking up the first line of the corresponding file and typing it out in small and semi-transparent text just to give a hint of what lays behind it. Maybe a mouse-over would show the first paragraph summarizing the argument that the reference links to.

# Connections without Double-click

When I first started thinking about direct links between notes, I thought about clickable wiki-links. But not I have reconsidered this because the amount of time you would save clicking a link instead of searching for its UID is minimal in the context of a Zettelkasten where the majority of the time will be spend looking for the right notes to connect [^wiki]. It also invites a habit of fuzzy searching, for example searching for only the part of the UID that represents the day or the hour of the timestamp to find notes created around the same time. Even if you search for the full unique identifier, you would also find other notes linking to it, which allows you to jump across notes. Instead of a direct link that teleports you from one space to another the intermediate search space act as a quantum state of entanglement where the final state of linking is not yet completed and have a chance to go in other directions.

There is also something philosophical about a time-based UID system. As if time itself was natures own unidirectional UID system where the same time never occurs twice. The simplicity of being able to manage to place successive unique IDs even without a computer keeping track of the sequence by using nothing but a watch, or even just by looking at the sun is staggering! A time-based system should be future proof at least up until the time of invention of time-travel, at which points it's anyway going to be easy to go back and change.

# Pros and cons of the 20

In the beginning of my new UID system, I have opted for a shorter year date stamp in the form of '15', dropping the 20 in 2015. There are both pros and cons with this. The pros is that it makes it easier to distinguish between years in the listing of files at a glance. Having a long list of 20's does not provide any information. The downside (at least until year 2100) is that the likelihood of having duplicates of a search stem in the file system is greater. For example, the chance that '1506' occurs more than one times in a search is greater that for '201509'. I did try it out and it turns out that the differences are not so great after all. The 15-stem is also compatible with by previous way of writing dates in files, so it would allow me to still search for YYMMDD-stems and come up with results from outside of the note system.

# Footnotes

[^wiki]: http://zettelkasten.de/posts/you-dont-need-wiki/
