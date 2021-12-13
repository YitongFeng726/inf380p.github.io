---
layout: post
author: acreese
title: "Alex's Final Project and Reflection"
---

## Final Project 

<iframe src="https://trinket.io/embed/python/6d36e19dd7" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>


I chose a data analysis program because (in addition to librarianship) I have chosen a data-focused concentration at the iSchool, and I simply enjoy working with and visualizing data.  When attempting to find datasets to work with, I set out with botanic data at the front of my mind because I studied botany and plant science as an undergraduate and remain very interested in plant taxonomy and ecology. So, I turned to the U.S. Department of Agriculture’s PLANTS Database – a resource that “provides standardized information about the vascular plants, mosses, liverworts, hornworts, and lichens of the U.S. and its territories," and one I have referred to before to satisfy my own curiosity – and I found their NRCS State Plants Lists. These are structured and fairly clean comm-separated lists of native plants species, one for each of the 50 American states and the territories Puerto Rico and the Virgin Islands. They contain information for plant "symbol" (an agency-specific alphanumeric code for the scientific name), "synonym symbol", scientific name (genus, species, and any additional subordinate taxa) with author (the first valid publisher of the botanical name), the state common name, and the taxonomic family name. For example, this is the entry for the common sunflower:

`"HEAN3","","Helianthus annuus L.","common sunflower","Asteraceae"`

It might not look like much at first glance, but I knew it provided plenty of information for analysis and visualization. I realized that for each state I could process the data and return metrics like the total number of native plant species, genera, and families – which would tell us not necessarily the most common/abundant plant species (not knowing their populations) but rather information about the state’s level of plant biodiversity. In this way I could also extract a top N number of biodiverse genera and families for display as well. If I could figure out how to meaningfully represent and display the data, I could also compare and contrast these metrics between states. 

I realized I could even go beyond scientific botanical information and reflect some cultural/sociological information as well. If I were able to compare and contrast state common names – highlighting plants that were called different common names in each state – I could point to cultural differences between states. Highlighting plants without common names could even give a rough indicator of historical botanical interactions within a state – what number (and what percent) of species are so rare or unfamiliar to European settlers that they did not acquire common names. (Sadly, common names in native languages are very rarely recorded and cataloged and are increasingly difficult to find.)

This felt initially like a big and daunting task, and I staked out some of these metrics as stretch goals. But as I began coding my data processing, things started getting easier and easier faster and faster. I think this was mainly because I was simply getting more and more comfortable and familiar with Python, learning techniques that I could apply to later processes and developing code snippets that I could easily rework. So things that started out as stretch goals like 2-state comparison became achievable to me! 


My process began, as instructed, with creating the user-interface of my program. I based this interface off of the one that Dr. Hauser mocked up as an example but, understandably, expanded upon it much further.  I created a main menu with two secondary menus based on my two main functions – single state analysis and 2-state comparison (even before I knew if whether I would be able to meet my stretch goal of 2-state comparison). We had worked with the `input()` function early on in the class, but this was the first time I had created user interfaces in Python, defining and calling functions to display text and capture variables extensively with `input()`. I still think it is the messiest and least elegant part of my code. I Perhaps this is because of the extensive and somewhat confusing `while` loops and `if` statements I created to account for invalid inputs, communicate that error, and prompt for new inputs – all in order to make my program as robust and graceful as possible. I have also tried to make my program case insensitive, which I felt was much easier to do and lead to less additional complexity. 

Initially, I was relying on a single main `while` loop to navigate between these three menus though different inputs that called specific functions, but it was getting difficult to manage the state of the menus this way and ask for conditional inputs in the secondary menus. As I started developing new input functions for users to select specific states, I realized that creating while loops within each menu/function would improve the program’s usability and gracefulness…but at the expense of simplicity.

Because my data was hosted on individual web pages in plaintext, I really hoped I would be able use Python to scrape this data on demand from the web, eliminating the need to copy and paste the text from each into my trinket. By referring to the Runestone chapters 13 and 14 on Network Programming and Web Scraping, I was successfully able to retrieve the web pages with the `urllib` module, but it gathered very sparse source code without the expected data. I eventually realized that the data was inserted with javascript, which is only supported by modules not available on Trinket.  So, understandably, I chose not to add .txt files all 50 states to my trinket, and, instead, my program only allows the user to analyze the small handful of state text files I have manually uploaded to my trinket.

I had some significant struggles using additional taxonomic text files to classify my plant species/families into major taxonomic groups (flowering plants, conifers, mosses, ferns). I kept getting key errors because some of the families in my USDA data weren’t present/represented in my taxonomy files – mostly due to the constantly shifting nature of taxonomic description – plant families are combined and reclassified and renamed and made defunct. So there is room for lots of discrepancies because it was secondary analysis. I spent too much time looking for really clean, comprehensive, exhaustive data, but I eventually realized that I my data did not really need to be clean at all – because all plant families all end with the latin suffice “-aceae”, I could pick them out of even chunks of text. I used this strategy pull them out of a big chunk of technical writing on taxonomic changes in flowering plant classification and was able to resolve a lot of these key errors in one swoop. However, in analyzing other names that came up missing, I noticed a fungus family (which should not have been included on a list of plants), and I considered looking for some fungal plant family data, but it just felt too far out of my purview and my expertise, which helped me realized I could create an ‘unknown’ category to capture this relatively small minority of problem species/families.

I also struggled with all the data I had on my hands. I saw some classmates create interfaces with more options, to let users select very specific types of the data to present, but I ended up opting for a kind of data dump. I don’t think it’s an unappealing dump, but I ran out of time to make my interface very granular. 

I played around with the `pygal` module and learned how to create some cool looking graphs – bar, stacked bar, pie – which was another stretch goal of mine. However, I didn’t end up using them in my final program. I did not like the way that the graphics were displayed separately above the text, and, again, I didn’t have enough time to refine my interface enough to allow users to select individual graphics, and so I worried that a dump of graphs might be confusing. I also did not like that I could not change the graph style from the default ‘Dark’ style – again because the module wasn’t supported by trinket. But I am happy that I can still walk away from this project having learned some `pygal`. 

By the end of the project, I realized I was starting to feel surprisingly comfortable with Python. Of course, I have so much still to learn – in terms of both functionality and producing elegant code – and I still make lots of mistakes along the way, but I have noticed that I am much more confident while coding and can produce functions and blocks of code much more quickly than I thought possible. And that all feels really exciting. I’ve also noticed I enjoy coding. My data analysis of native plants doesn’t feel super important (though some ecologiests might enjoy it), but it was still very fun to do, and I had moments of genuine excitement when I got my analysis functions to work and started building outputs. 


I of course had to debug throughout the process. I made simple mistakes that I learned to avoid and ran into larger problems that pushed my knowledge of Python, but I’m happy to say nothing hung me up for very long. I noticed I struggled more conceptually about how to structure my functions (should I do all the file processing up front, or on demand? Should I cram all the data analysis in a single function or break it down into smaller chunks?) than I did in actually building them. Again and again, I found that if I dove into the coding, the answers would become clearer and more evident. And while I had to do some restructuring throughout, it wasn’t exactly a waste of time. 