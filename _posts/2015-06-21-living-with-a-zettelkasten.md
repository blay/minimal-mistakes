---
layout: post
title: Living with a Zettelkasten
tags: meta
summary: Explains how to work with a Zettelkasten note system
image:
  feature: zettel_narrow.png
---

{% include _toc.html %}

This summer I have taken my time to re-think my note-taking system. I believe it was three years ago that I got serious with systematizing my note-taking by adopting a system based on plain text files inspired some writing that is not collected at zettelkasten.de.

The term Zettelkasten comes from Luhmann's note-taking system. Luhmann used a filing archive of index cards that he put in slip boxes -- or in German, Zettelkasten. [This video shows his system](https://www.youtube.com/watch?v=mCFP5i_0ibE).

<iframe width="560" height="315" src="https://www.youtube.com/embed/mCFP5i_0ibE" frameborder="0" allowfullscreen></iframe>

The core of the system is a collection of shorter notes with links between them. This can be implemented on [index cards](https://unclutterer.com/2014/06/17/the-pile-of-index-cards-poic-system/) or on a computer, preferably in a software-agnostic way, such as with plain text and customizable programming text editors. The for a computer implementation is to take the basis of an index card Zettelkasten and make it both human- *and* machine-readable. The philosophy is related to Markdown with its simple markup and emphasis on being readable by both humans and machines.

While being inspired by a paper-based index card system, a Zettelkasten is very different from a note book. Index cards and its filing system is a typically modern phenomenon, while books are medieval and pre-modern. Books --- including note books --- are based on text that *stick together*, page after page. This text can't be moved, processed, separated and concatenated. They are meant to be read from beginning to end and a page is not autonomous from its neighbors. While index cards and filing systems are predessessors to the computer, books, on the other hand, have nothing to do with computers.

Unlike its name implies, a computers primary task is not to compute in the sense of doing calculations of mathematics, but it is to be a data handler. In this sense a computer, down to its very core, is nothing but a dumb but extremely fast file handling clerk. This comparison goes all the way up to the operating system that works with files -- pieces of data -- that has a name -- or an address -- and can contain content, and that are later placed in folders. [See this video where Richard Feynman explains computer heuristics](https://www.youtube.com/watch?v=EKWGGDXe5MA).

<iframe width="560" height="315" src="https://www.youtube.com/embed/EKWGGDXe5MA" frameborder="0" allowfullscreen></iframe>

Now this is not a historical lesson, although the story of how the filing cabinet became the computer is an incredibly fascinating one[^1]. Instead, I will go through how I use a Zettelkasten, or rather, how I *live* with a Zettelkasten.

# How to Read a Book

When using a Zettelkasten, you have to read books differently. Instead of reading a book from cover to cover, you iterate over the book and each time drills down to the parts of the book that you will eventually read with a purpose -- the purpose of careful reading while taking notes and integrating these into your Zettelkasten.

The four stages of reading a book for your Zettelkasten are:[^2]

1)  Get a feel for the book by looking at the headlines.
2)  Decide what you want to learn from the book.
3)  Skim the paragraphs to find out the interesting ones.
4)  Take note of interesting passages.

With this overview you can start the practice of reading and making notes. Notes written in the practice of reading can sometimes be insufficient to stand on their own and when processing them into a Zettel you have to go back and read a few paragraphs from where the note was taken. Reading notes can also often be clustered together into one longer Zettel.[^3] Keep in mind what you decided that you wanted to learn from the book. Be wary of clustering notes based on the texts structure. Cluster in a way that makes sense to your intention and your Zettelkasten.

# Making a Zettel

In order for a reading note to be turned into a Zettel it must un-stick from the text. It must be able to stand on its own with only a *reference* to the source text. You need to untangle a note from the web of text it was immersed in. This often involves rephrasing of the arguments in the source text and turning a part of this argument into its own *concept*.

Rephrasing key arguments is a great way to integrate the knowledge and to have notes that you can rely on so you don't have to go back to the source text again. Using examples is also a way of getting the text to work for you creatively.

A typical Zettel can contain the following elements:

1)  A compact key statement.
2)  An elaboration of the concept.
3)  An example you came up with.

Zettelns based on concepts gleened from a text, rather than being to dependent on the structure of the source text makes for easy connections to your existing knowledge base. Making connections from the concepts you make note of too your existing knowledge is the only way to make the Zettelns work for the greater purpose of the Zettelkasten.

If a Zettel has too many dependencies to stand on its own, write the Zettel and create links to the necessary prerequisite notes.[^4] This is one way that a Zettelkasten can perform operations on itself. The Zettelns that form the prerequisites must now be researched and written. A part of a Zetteln is a dependency of both the Zettel and the dependency can stand on their own and be used in different note sequences. In computer science, this is called "Separation of concerns" [1507211921]. Such separations can be an empirical fact, and argument, and its conclusion.

A connection can be made by linking between two Zettelns, but it can be made stronger by merging Zettels or by writing a third Zettel that explains the connections between the two Zettels. Connection Zettels can also explain the connection between other connection Zettelns and if this process is expanded you soon end up at the level of the abstract, or outline.

Only you can make the connections between two Zetteln. As your personal knowledge system, you are the one deciding how your Zettelkasten will grow. You make these connections sensible to other people by writing texts about them.

The time it takes to integrate a Zettel into the Zettelkasten grows with the size of the arcive.[^5] This is the only task whose time consumption is dependent on the size of the Zettelkasten but its reward also grows with the amount of connections made. To add a new Zettel you have to both think about and find other Zettelns to link to that exands the arguments in your Zettel. You also need to find other Zetteln and sequences that would benefit from a link to the new Zettel. There is no straightforward way of doing this since connections are *created* by you. The Zettelkasten and its associated scripts are there to help, nudge and inspire you in this process.

# Titel Your Zettel

A title, or filename, of a Zettel should contain the unique identifier and any other semi-structured indicators such as tags and topics. The titel itself should be the content of the Zettel in a condensed form that can be read on its own.[^6] If the Zettel is an argument, the title should be the conclusion in a few words. Just saying what topic the note is about is not enough. By making the title into a statement, you indicate how it can be *used*. Similarly, the first sentence or short paragraph should summarize the Zettel. If you ever read a Zettel that is not summarized, add it! It is also important to consider that particularities of search. What title or summary would contain saerch terms that you are likely to use in the future. A likely search term is neither too obscure and unique, nor too common. Do not title a note the way you would title a paper; intriguing.

# The Knowledge Cycle

You should aim at making each writing session go through some variation of the knowledge cycle: *research, read, note, write*. Each knowledge cycle can be fractally embedded in larger knowledge cycles, which translates to stages in your writing process. Short knowledge cycles forces productive breaks, as opposed to interruptions or exhaustion. The short knowledge cycle works well with pomodoro breaks where each break marks a jump to the next phase of the cycle. A short knowledge cycle also work well with todo tasks since there can be a completion in one session, although the task continues the next day. A task can be "complete one cycle of research on article X", instead of "work on article X".

Quote from [Zettelkasten.de](http://zettelkasten.de/posts/knowledge-cycle-efficiently-organize-writing-projects/):

1.  Research for new material, where we have to scan and select what’s useful and what isn’t,
2.  Reading the findings, thus increasing our temporary understanding based on the capacity of our short-term memory,
3.  Taking lasting notes to feed the Zettelkasten and thus permanently increase our knowledge.
4.  Compose a new section or add notes to the outline of an existing draft.

# Building blocks of a Zettelkasten

1.  The Inbox; The gateway to your zettelkasten
2.  The Archive; The core of your Zettelkasten
3.  The Reference Database; The representation of the world outside your Zettelkasten

These are parts of a process, not different tools.[^7] Your own finished writing is part of the reference database.

The main purpose of the Zettelkasten is to provide you with information -- a difference that makes a difference -- that sparks new ideas. It *recalls* the ideas that you previously put into it by way of association, pointers, links and search. Your task is to turn this into *writing*.

The Zettelkasten need interfaces to the external world. Without input, the archive remains static, without output the archive is not released. A Zettelkasten becomes *uninteresting* when 1) It does not grow, 2) it grows only with isolated notes, 3) it never produces an output. A Zettel does not want to live alone in the Zettelkasten, it wants to find connections, but it also wants to be released from the archive and become part of a directional work.

The operations of the Zettelkasten also include recursive heuristic operations on the Zettelns in the archive where they are linked, commented on or expanded upon.[^8] These operations make gaps in the information in the Zettelkasten apparent which also directs the input function of the Zettelkasten, leading to the active search of pieces of information.

References, highlights, pinboard, RSS; all these are outside of the Zettelkasten system but could be considered a part of the outside with reduced complexity for the Zettelkasten compared to the internet as a whole or for that matter the world outside of it.

It is important to remember that there can never be too much information in a well managed Zettelkasten. In the worst case, unlinked information will not be of use, but it will never interfere in the operations of the Zettelkasten. Often it resides quitely until it shows up in a search function and can be linked and made useful with other Zettelns. Therefor, you should never be afraid of adding new material to the Zettelkasten as long as it is a proper Zettel, even if it is just summarizing and article you read with a short comment.

The Zettelkasten will grow to work together with your brain if you only let it. You need to educate your Zettelkasten because on day it will be *your* teacher. Emerging links, sequences, categories and keywords will integrate with your brain as it grows hardened together with your Zettelkasten. Familiar routines (in the everyday, the computer science and the theatre sense of the word) will form neural pathways in your brain and paths of note sequences in your Zettelkasten. Existing neural pathways will fire when you integrate new material and they will be extended by making new connections.[^9] The Zettelkasten adopt to your thinking but at the same time you start to think like your Zettelkasten. It is as if the Zettelkasten and your brain forms the same neural network and the Zetteln provide connections between your neurons that weren't there before. What is in your brain is not in your Zettel and vice versa, but they can use each other.

Remember that life in a Zettelkasten is supposed to be fun. It is a joyful experience to work with it when it works back with you. Life in Zettelkasten is more like dance than a factory. You can finish all Zettelns with this kind of dance where you come up with an idea, then search for a note that matches it. This new note will trigger a new idea and again you search for a new note. Eventually you will reach a well-connected base note, a super hub and it will lead you in all kinds of directions. Perhaps it is time to stop here. Let these connections rest and wait for another opportunity to revisit them in another playful dance that starts on another note. An example of this playful dance can be found in the end of a note I recently wrote:

> Mer om motivationen kring Electricity finns i anteckningar från ett gammalt möte §1402211136 Här finns en del tankar kring eldrivna tranporter §1405211242. Jag satte också det i kontext kring en "andra informations-revolution" i §1209270391. Det bekräftas också i intevjun med björn om den revolutionen i aktiv säkerhet som bygger på "cyberfysiska system" §1305060807. {\>\> REF: Link Björn interview transcription \<\<} Går också att länka till Beninger's Control Revolution §1305170840. Kan detta utvecklas till den övergripande temat i avhandlingen så som jag reflekterade över i §1404081206.

# The Question of Folgezetteln"

Folgezetteln are note sequencing created by follow up notes, such as the sequence created by ab01aa01aa in my Zettelkasten. The benefits with Folgezetteln is that it creates a clear sequence of notes that is visually apparent on listing or browsing notes. The downside is that it fixes links between notes in a hierarchical and linear manner that is the product of decisions in one particular time-space. It makes it hard to change these links or to create note-sequences on the fly based on the current topic of research. Folgezetteln is a hierarchical system based on trees and branches. Two note sequences can't share the same note.

Some alternatives to Folgezetteln are outlines and tags. An outline is an index of Zetteln that create a sequence. Tags reveal indexicality in a search.

A remaining controversy regards the historicity of Folgezetteln.[^10] Do they have a place in a digital Zettelkasten, or were they simply a by-product of the material constraints of index cards? A simple addition to a note that remains "sticky" is meaningless in a digital Zettelkasten, but serves a purpose in an index card based system. For a note to achieve the status of a Zettel it must be independent and be able to be a part of several sequences or relate to several notes. Likewise, a Zettel can become too sticky if other Zettelns would like to refer to *a part* of the Zettel. In this case, one can consider splitting the Zettel into two independent arguments with a link between them. This necessity of linking to a part of a Zettel could be used as the indicator that a Zettel has become too sticky instead of making Zettelns that are too loose by prematurely creating new ones. Another indicator that it is time to split a Zettel is that it keeps showing up in search results although you were only looking for a specific part of it.

A sequence of Folgezetteln links without explanation. They simple "belong together". This can provide a posivitve freedom of association but can also become a constraint, just like placing files in folders. A direct link on the other hand can also contain an explanation of how come the association arose in the first place. It is up to the author to choose what is a sufficient reason for a link.

The primary argument for maintaining sequences of Folgezetteln so far seem to be that they provide a visual overview of links at the level of file browsing, search and listing of notes. This is a argument that is based upon lack of tools and methods to otherwise accomplish the same overview and is therefor a compromise of the Zettelkasten system. This constraint is partly a consequence of the interface of nvALT, but could also be considered a broader issue with file-system based data handlers (as opposed to database managers for example). The reason for this limitation is that the file system as a framework for data handling is itself a metaphor based on a paper based file handling system in which Folgezetteln makes sense. The idea that "in the end", a Zettelkasten consist of a folder where each Zettel is a file in a file system is a limiting metaphor compared to a dynamic database that can arbitrarily construct relations between data. The follow up question is if the paper based metaphor is a proper fit with a human cognitive processing system -- that is, the brain -- and should therefor be kept to provide easy organisation, or is it is a historical residue that can -- and should -- be replaced by a dynamic relational database.

If the latter case -- that a dynamic relational database is the proper way of representing a digital Zettelkasten -- holds true, then the file-system based listing and browsing of notes -- which also nvALT is based on -- should be replaced by a dynamic listing of indexical relations in the Zettelkasten. One way of doing that while still keeping with a plain text file based system is to use scripts that render outline files. These outline files could follow links in the Zettelkasten -- provided that links are unidirectional (which makes sense) -- and render indexes of note sequences. This could both be rendered as notes in themselves, or it could be dynamically rendered as STDOUT. A combination of both is preferable. The reason that unidirectional links make sense is that only one of the notes (the linking note) is written with the knowledge of the other note (the linked note). Instead of the linked note also containing a traceback to the linking note, a dynamic index should be possible to render as a list of several note sequences where this note is a part.

The discussion boils down to a conflict between a rendering of relations as a sequence or as a network. The sequence allows a note to only be part of one history (but several futures in the form of branches) while a network has no time-variant to the links, but on the other hand do not allow a tracing of a sequence in more that one step. In a network we can't visualize a sequence of more than one jump. If the relations are to come in the form of a database, that is as a network, then the sequencing need to happen with manually constructed outlines indexing sequences of jumps throughout the network. This is similar to how a wiki relies of indexes of links between files or parts of files. In a file-system based organisation on the other hand, a note can't be part of several histories unless there is a merge of these histories into one future. Once the two histories arrive at the point of merger, they can't have separate futures anymore, although it is possible that there are new branches created.

To continue the metaphor of "writing as software project", or rather Zettelkasteling as software project, there needs to be a decision of whether the Zettelkasten functions like a version controlled code repository, such as git branching, or as a code library of reusable code. The latter is a database, while the former is a tree sequence (excluding concepts such as forking). The great fear of moving to direct links is of course that the Zettelkasten turns into the dreaded Wiki.

# The Collectors Fallacy

To *know about* something is merely be aware of its existence. *Knowing something* is information integrated in a knowledge system.[^11] It is that information coming into contact with, transforming and being transformed by the encounter with other pieces of information, thoughts or knowledge. Collecting does not transform us and always postpones learning and transformation to the future. Collecting creates debt that we promise to pay back in some future that never arrives. The collection allow us to imagine ourselves in the near future as a person who has read and understood the collected material. This makes us feel good. We like that person.

If a collector collects more items than he or she can manage, the items turn into a pile. A pile will never be read.

Reading can also be subject to the collectors fallacy. Then we read unsystematically -- without taking notes or integrating what we understood into our knowledge system -- then reading is merely a short-term feeling of understanding. This understanding can't be kept in memory for long and we once again trade a pleasant feeling in the present for the increase in long-term learning. If we take proper notes, there should be no need to go back and read a text again *in the same way*. Taking proper notes on the other hand allows us to go back to a text and gain an even deeper understanding of it.

In genereal, you should never read anything without having an aim of it being integrated into your Zettelkasten. Anything else is a waste of time in the long run. Read everything like you read a book!

Not even reading *and* writing is immune to the collectors fallacy. If you go directly from reading a source text to pouring it in to your draft from your short-term memory without creating notes as scaffolding of that knowledge, it will also become shallow and the next time you continue your draft you have to go back to the source text again.

Bad notes is also not an excuse -- the worst example of a note being the highlight -- but this comes down more to practice and experience of knowing what is a workable note and what is an insufficient note that forces you back to the original text.

In the end, the collectors fallacy relies on a totalizing vision of knowledge that thinks one can collect everything on a topic, read everything on a topic and turn that complete knowledge into a draft. It does not consider the situatedness of a research project and that new knowledge is *created* when pieces of knowledge encounter each other, not when gaps in a totalizing knowledge system are filled by adding information.

The collector's fallacy should be channeled, not squashed. Cherish your inner "archive fever"[^12] --- it is your engine --- but channel it to productivity. Use *strategic procrastination*.

# Semi-random

The more I have developed my Zettelkasten, the more I have come to rely on opportunistic presentation of information instead of hierarchical, logical structure. The Zettelns have some structure and many connections, but it is really the scripts that bring it alive.

This might seem scary -- to rely on uncertain, opportunistic matching -- but remember that the idea is not the collecting and organizing; the idea is the writing, and the idea of the Zettelkasten is to support your writing. The Zettelkasten is there, so that when you decide to write, you don't need to only rely on the immediately accessible short-term memory. You are presented with traces of your past thoughts, each Zettel bringing something back to life within you, lighting up some parts of your brain that start to remember those trains of thoughts the memory had sorted away. Now you start to see the bigger picture, how things are connected, how the argument goes. But it is *your writing* that is the map, not the Zettelkasten, it can't do that for you, you have to put in the work.

# The Art of the Outline.

An outline in the context of a Zettelkasten system is an index of a sequence of Zettelns that create a story, or a narrative, or an argument. They may come with a simple list of a sequence of Zetteln, or with contextual information such as headlines. An outline can also be written as an abstract of a paper where each argument or statement in the abstract is supported by a link to a Zettel. This allows the author to make sure that the narrative is coherent and each argument is well supported. The final paper will simply be an expansion of the abstract into a concatenation of the listed Zettelns. A sequence of Folgezetteln notes in the filenames of the Zettelns can from this perspective be considered a hardcoded outline and should be avoided, however convenient it seems.

Optimally, outlines should both be able to be created manually by the author -- and then be considered in some form or another as an abstract -- or rendered dynamically by a search function and should then be considered to be indexes of links between Zettelns.

A way to test the strength of an outline or an abstract is to fill it with notes. Is every argument supported by well-written Zettelns? IS new research needed? Can you build a strong foundation for an argument by making connections between more notes?

# Writing a Draft

By utilizing the knowledge cycle, you should arrive at a first draft early in the process. By experimenting with turning outlines and note sequences into abstracts and furhter into drafts, gaps in the research process should become apparent. Once a proper Zettelkasten is constructed for a given paper, the process of writing and revising drafts is an easy, comfortable and well supported task. Making a draft is a stage within a writing process and as with all stages, it is best to separate them to different sessions; the cost of switching attention is too high. With a supportive Zettelkasten, you should be able to construct a draft without having to go back to the research stage.[^13]

The process of writing your first draft generally consists of making an outline from the overview of the knowledge of the field and populating each item in the outline with notes from your archive. A note might lead to new links that makes you add to your outline. If necessary, fill in the gaps in the outline with some more research that produces a few more Zettel notes (this research does not have to be complete). After this, you generate a complete text by expanding and concatenating the notes in the outline and re-write this piece of text into a first draft. In this process of re-writing, you will discover where the arguments and connections are weak and more research is required.

# Footnotes

<div class="references">

# References {#references .unnumbered}

Derrida, Jacques, and Eric Prenowitz. *Archive Fever: A Freudian Impression*. Chicago: University of Chicago Press, 1996.

Krajewski, Markus. *Paper Machines: About Cards & Catalogs, 1548-1929*. Cambridge, MA [etc.]: MIT Press, 2011.

Vismann, Cornelia. *Files: Law and Media Technology*. Stanford University Press, 2008.

</div>

[^1]: A glimpse of this can be seen in the documentary the machine that changed the world: https://www.youtube.com/watch?v=krlZf5H7Hp4. For interesting research on file systems, see Krajewski, *Paper Machines*. and Vismann, *Files*.

[^2]: http://zettelkasten.de/posts/learn-faster-by-writing-zettel-notes/

[^3]: http://zettelkasten.de/posts/create-zettel-from-reading-notes/

[^4]: http://zettelkasten.de/posts/create-zettel-from-reading-notes/

[^5]: http://zettelkasten.de/posts/reading-putting-it-all-together/

[^6]: http://zettelkasten.de/posts/how-to-write-notes-you-can-understand/

[^7]: http://zettelkasten.de/posts/zettelkasten-building-blocks/

[^8]: http://zettelkasten.de/posts/zettelkasten-building-blocks/\#comment-1391701606

[^9]: http://zettelkasten.de/posts/no-categories/

[^10]: http://zettelkasten.de/posts/zettelkasten-building-blocks/\#comment-1647837883

[^11]: http://zettelkasten.de/posts/collectors-fallacy

[^12]: Derrida and Prenowitz, *Archive Fever*.

[^13]: http://zettelkasten.de/posts/ease-into-writing/
