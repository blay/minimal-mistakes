---
layout: post
title: On the Coming Golden Age of Open Hardware
tags: english notswedish
summary: Some trends that have up until now favored large, closed manufacturing could shift in the coming years and tilt the balance of power in favor of small scale open hardware. 
---

Andrew “bunnie” Huang has written a very insightful blog post called [Why the Best Days of Open Hardware are Yet to Come](http://www.bunniestudios.com/blog/?p=1863). A lot of people has commented on the post and [elsewhere](http://boingboing.net/2011/09/27/bunnie-huang-the-best-days-of-open-hardware-are-yet-to-come.html) and I want to recap it and expand on it here. The basic premise is that while open hardware is a niche industry at the moment, some trends that have up until now favored large, closed manufacturing could shift in the coming years and tilt the balance of power in favor of small scale innovation. 

## Moore's law is the enemy of open hardware.

In the early days of consumer electronics, hardware was open. They shipped with "full schematics, a list of replacement parts and instructions for service". Even computers in the early 80's came with full schematics of the main board. This is no longer the case. "Did electronics just get too hard and complex?" bunnie asks himself. "On the contrary", he says, "improving electronics got to easy: the pace of Moore’s Law has been too much for small-scale innovators to keep up". 

If we consider moore's law, that performance double every 18 months, it is an exponential growth. Consider then than a small scale innovator working to improve a given platform increases performance of it linearly at 75% per year (bunnie's estimation). As a consequence, when a platform is launched, the small scale innovator has only a small window of time to work on improvements on that platform before moore's law makes it more profitable to just get a new platform. This is bad for craft, it is bad for code (more beneficial to upgrade hardware than to write better, more efficient code) and it is bad for open hardware that does not have the investment opportunity to get new platforms all the time. It is more rewarding to sit and wait for the new platform than to improve on the existing. This all favor economies of scale. Being able to develop several generations of hardware and ship them globally fast.


## We do not need moore's law anymore

There are two things to consider here. One is that moore's law might not work forever. Certain physical limits have been hit when it comes to increasing CPU power[^cpu], which is the reason we are going for more processor cores today.  The problems of computing today is also not so much about fast calculations as being able to do many smaller calculations at the same time. Considering a deceleration of the increase according to moore's law will expand the window of opportunity for the linear small scale development.

[^cpu]: Such that signals don't have time to get from one end of the processor to the other before one clock cycle has run. That seriously messes up calculations...

The other thing is that we don't need moore's law anymore. Increase in performance does not lead to qualitative leaps in user experience. Even adding more processor cores, which is easy to do as much as cost allows, does not necessarily make that qualitative leap for most users. I don't think I am the only one that for the first time in my life felt that the computer i got now is "good enough". Only poorly coded programs make my computer stall for a few seconds, but that's it. I also do not feel that increase in performance would open up the space for better software. I'm just not hitting those limits. For special use cases, certainly, but someone like me who work with text, code and use the internet, the response time is perceived as immediate and we have no use for moore's law anymore.

It's not only that increase in performance has seized to lead to increase in user experience, the development on miniaturization that followed on that (same processing power, less energy use and size) is also coming to a halt in many areas. A the size of a mobile phone today is not determined by the absolute miniaturization of the components but by optimal screen size and most suitable tangible interactions [^nokia]. This means that today there is no ongoing linear acceleration that automatically enhances user experiences or opens up for more software opportunities, which opens the door for design in the broadest sense to be the determining factor --- that is choices based on intended use --- and these choices are up to anyone to be able to make. It won't be the same but smaller or faster. Now it's time to start making novel use of the computing resources that is here.

[^nokia]: See [this article](http://www.domusweb.it/en/design/portable-cathedrals/) about the interaction design of the Nokia N9 for how the space for tangible interactions in mobiles phones is not yet fully explored.

Also worth noting is what's called [koomey's law](http://www.koomey.com/post/2678649528) as a complement to moore's law. Koomey's law states that the energy efficiency of computational devices tend to double every 1.6 years. This means that the commodore 64 had the same energy-per-computation efficiency as a super computer of its age. Another way to state this law is that the need for battery capacity for a fixed amount of computational power halves every 1.6 years. This really opens up for a design-led future of computation since energy capacity also could become a non-issue.[^transfer]

[^transfer]: Or does this only shift energy use from consumption to manufacturing?

## Freedom ends at 100 mbits 

Effort to try to reintroduce that kind of linear acceleration again will have harder times to claim legitimacy. Perhaps it is only possible within gaming to push for more computational power, but even there interaction design and game play is starting to take over from pure improvement of number of polygons. As a commentator to bunnie's article said, the color race is already finished; no one sees more colors than 32bit TrueColor can produce (let's not get started on 3D). The key point is hit when increase in a parameter only enables better quality and not new kinds of interactions [^100mbit]. The media industries tries to continue to equate increased cultural value with increased use of computational resources in order to keep their advantage with economies of scale over the rest, but it becomes more and more difficult to sustain.

[^100mbit]: As a comparison I made the same argument in regards to bandwidth [here](2011-10-06-punks.html)

## The way we compute now is only one of many possible ways of computing

The idea of a legacy laptop passed on to the next generation might seem far fetched today but this is where things could be heading if these economics continue and design rather than performance becomes the key. Deceleration of technological performance increases creates the opportunities for more socially and ecologically sustainable practices.

Free software takes time to be good and to perfect. I'm writing this post on the 35+ year old Emacs text editor which has evolved to perfection due to a stable platform. Stable platforms makes it easier to get a chance to develop open standards. Imagine having a modular open hardware standard for a laptop or a mobile with interchangeable components. For a legacy laptop does require an extensive standardization, otherwise it would be very hard to find spare parts for a 30 year old laptop.

There can be some problems with creating a repair culture of modern electronics, which several people have pointed out in comments to bunnie's article. One is that the surface mounted components that are so small it is basically a one-way process of putting them on the circuit board and very hard to reverse that and repair manually with new ones. A solution to this as a commentator to the article says is to make technology modular, so instead of having to discard a whole device, small parts of it can be removes and replaced. This is similar to how Dominic Muren imagines modular design within his [SSG framework](http://www.humblefacture.com/2010/08/ssg-framework-for-more-sustainable.html).

One thing to remember is the major differences between hardware and software. It is not simply a "next step" but an entirely new thing. Only with very advanced robotics can you treat hardware as a software problem [^robotics]. Without them, you can't copy and share the way you do with software. Hardware often has a high initial cost (even though prices can go down per unit with mass manufacturing). This is especially true with CPU's. 

One promising breakthrough (although I'm not knowledgeable enough to completely determine if it works) is [Field-Programmable Gate Arrays](https://en.wikipedia.org/wiki/Field-programmable_gate_array) --- FPGAs. Unlike a regular CPU, whose structure and connections is determined at the point of manufacturing, an FPGA processor can change structure and connections with a new software. This has traditionally been reserved for low volume production where it is not profitable to develop a custom CPU. But the FPGAs are decreasing in cost and increasing in performance to make them suitable for a wider range of uses.

Another benefit of FPGAs is recyclability. If a FPGA has been used for a function that is no longer necessary, the same processor can be reprogrammed to perform some other task. [This article](http://www.i4donline.net/articles/current-article.asp?articleid=1276&typ=Features), about the state of telecommunications in India, suggests FPGA together with [software defined radio](http://gnuradio.org/redmine/projects/gnuradio/wiki) as a setup that could greatly improve rural telecommunications. The combination of FPGA and software radio enables devices that communicate with different protocols depending on fluctuating local needs. It could route GSM phones over the internet for free calls as well as function as a HAM radio or TV transmitter. No need for separate infrastructures to be built. The article ["It's time to bring FPGA design to the masses"](http://stop.zona-m.net/2011/09/its-time-to-bring-fpga-design-to-the-masses/) continues:

> Even if, after one year, the arrival of cheap smartphone made that device obsolete as a telephony gateway, it could continue to be useful to the community in many other ways, becoming solar panel and battery controller to an educational platform similar to the XO minicomputers of the One Laptop Per Child project. 


[^robotics]: The point with robotics is that they will perfectly repeat a physical process. Once it has been programmed it can be repeated eternally. See this ad for ABB for an example.




## The end of cheap electronics

Not only can it be possible to make long-lasting and repairable electronics. It can also become necessary. As rare earth metals, copper, gold and oil become more scarce and energy costs rise, it could mean the end of cheap electronics. It will become less profitable to make and buy trash that breaks and has to be replaced. Long lasting and repairable will be back again and perhaps once again bring back the schematics.

I would love for more technically knowledgeable people to comment on what you think about the plausibility of these scenarios. The overall point of the article is to suggest that the way we compute today and the what we think computing is and how its done is only a local manifestation of computing under specific circumstances. Were these conditions to chance, computing as an everyday practice could also look radically different. Already today there are traces of this on the margins in strange environments. 

The computer as we know it today must not only [be defended](http://www.reddit.com/r/freeculture/comments/nwzq6/the_coming_war_on_general_computing_cory_doctorow/) but our visions and practices must continuously be expanded, updated and transformed.
