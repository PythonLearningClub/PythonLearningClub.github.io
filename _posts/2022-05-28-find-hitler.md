---
layout: post
title:  "Find Hitler"
---
#### Team:  
* Idea: Olya S.
* Project Manager: Olya S.
* Project Developer: Sofia
### Description: 
Starting from a random Wikipedia page try to switch to page about Hitler in 5 or less steps.
Pay attention! we work with EN wiki version only (https://en.wikipedia.org/)

**Implementation idea:**

1. create script that takes as input link to wiki page - it is our entry point
2. parse the page and extract all existing links
3. exclude service links (like: change language, download page)
4. check one by one the rest of the links and verify:
    1. it is still wiki
    2. name of the page is equal to “Hitler”
5. in case of first success return the “win” chain and number of steps.
6. if it is impossible, i.e. no links lead to Hitler in 5 steps print some message to user

**Example:**

entry point: https://en.wikipedia.org/wiki/Diversity_index  
link_1 https://en.wikipedia.org/wiki/Norbert_Wiener  
link_2: https://en.wikipedia.org/wiki/World_War_II  
link_3: https://en.wikipedia.org/wiki/Adolf_Hitler  
print:  
"Hitler found!
Game finished in 3 steps:
Diversity_index -> Norbert_Wiener -> World_War_II -> Adolf_Hitler"