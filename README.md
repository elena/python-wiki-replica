# Replica of Python Wiki

OriginaL: https://wiki.python.org/

**It seems to be the year of the python wiki!** Independently it seems as though several people/groups have got an interest in this wiki. I am one of those people, though it is only now it's coming to light how many people were interested.

I have tremendous respect for the wiki and everyone who has worked on it. Some names appear again and again over many years, it's clear a great deal of effort and work has been put in to this resource. 

My motive here is that I want to have a community-driven "source of truth" for a bunch of the information in this resource, particularly the user-groups (where my magnificent Australian community has over-represented here) and I want to push this further. It's been on my mind for some time that the existing moin instance does seem to struggle with resiliance and simultaneously this here github seems to be growing as a tool that many people are familiar with, which also supports the "wiki" concept. 

This project is an attempt to do a swift port to a github repo. It has been about as much work expected and I'm exceptionally grateful for some fantastic tooling from the python ecosystem that has made this both quick and quite fun (nb no llms were used outside of editor-code-completion, which didn't necessarily make things faster). 

--

NEXT: To reach out to the owners of the moin instance and get their advice. Contact has already been made via discord and mailing list, but this project is well on track to be mature, with the hardest parts of the work done. For disclosure, I'm now feeling quite nervous about this, but yolo and also it'd be a shame to see this effort go to waste.

Ideally this version of the python wiki can be accepted at least informally and "real" work can be started to build upon it, there's still tons to do. I for one and now busting to update the details on my main UG.

I will be pursuing this follow-up during w/c 2025-02-17


---

2025-02-16:

First pass is complete. 

There are 1,751 "root" pages by default.

This are grouped to:

```
`beginner-tutorials` (15)
`reference-technical` (108)
`reference-international` (89)

`events-major` (82)
`events-local-groups` (31)

`lists-links-external` (14)
`lists-books-topical` (14)
`lists-books-international` (13)

`psf-wiki-internal` (25)
`users` (474)
`historical-pages` (rest)
```

This is still rough but care has been taken to select these root categories based on past decades of use. Some inspiration was taken from the existing "Category____" setup: https://wiki.python.org/moin/FrontPage?action=fullsearch&context=180&value=Category&titlesearch=Titles  -- the balance applied here feels good, fair and appropriate.

A few "design decision" things are in my way currently:

* Links management
  * Some are broken. Link management will be perenniel. Further down the track some kind of automation can by applied to assist in managing this. Maybe precommit-hook.
* ✅ github/wiki experiment (failed): github wiki appears to be "flat", ie, it doesn't support wiki with directory/tree structure as moin does. Fallen back to using the main repo.
* Preserving history
  * Can see many approaches but developing the idea
 
The final mopping up after the above are resolved is to upload the workings. These are:

* local django wip project including db.sqlite3 db (or data dumps?)
* full dump of md conversion
* original collected html files

**TODO:**

* Reach out to people who appear to be owners of existing 
* Process newly collected (no wait, another 99 have fallen out, love-a-spider)
  * keep recursing until done
  * apply groups (could document loose rules used? vaguely: pull out users/local-groups/events/books/i18n; arrange by date, eyeball most recent for annotation saying explicitly that historical; categorise remaining)
* Check for any changes since 2025-02-09 (and apply)
* Update links back to original site for generated pages (can't move)
* Write out all to repo and commit (to this repo here)
* Talk to https://github.com/python-organizers/ about maybe setting up shop there?
  * also reach out to people here, bit of a crossover, but this is scary! Quick looks suggests poor fit for this exact repo:https://github.com/python/docs-community
 
Next:

* Work on broken links (can: remove, annotate, ??), maybe pre-commit hook
* Backfill revision history for active pages

---

2025-02-15:

**It seems to be the year of the python wiki!** Independently it seems as though several people/groups have got an interest in this wiki. I am one of those people, though it is only now it's coming to light how many people were interested.

For myself, I wanted to get an understanding of what the wiki "looked Like" to do some analysis on.

Additionally it seemed like fun to see if it was replicable here, using the default wiki available with this tooling, so here we are.


**Completed:**

* ✅ Small django project that contains the all files collected using both linked-graph (this capture to 2025-02-09) and any further from `/moin/TitleIndex` (as recommended from mailing list).
* ✅ Basic overview: contains 2,636 pages and 849 unique contributors
* ✅ Converted all content to markdown
* ✅ List of `active-pages`.
  * Criteria:
    * -> not User pages (don't feel authority on these, though these are hard to identify -> perhaps seperate list of user pages, this is easy and should be done, adding now)
    * arbitrary, I reckon maybe back to around 2016 as ordered by `last edited` date, this is ~400 pages including users, I think will come down to maybe ~250-300
* ✅ List of `user-pages` (easily defined as they will be represented after `last edited by`, with some nuances and likely imperfect)
* ✅ New django model for users (obviously not called users)
* ✅ List of `local-user-group-pages` (as linked per above)
  * all pages linked from https://wiki.python.org/moin/LocalUserGroups ✨ irrespective of date
* ✅ Fix white space in md
* ✅ Determine most populated root-node pages, adjust and populate django models as necessary
* ✅ Experiment committing tree structure to github wiki
* ✅ Remove links to redundant wiki `Category__`
* ✅ Pushed up small set to review in github (`event-local-groups`)
* ✅ New directory tree:
  * ✅ `users` directory which will contain all user pages irrespective of date
  * ✅ rest of pages, wip
    * ✅ grouping "organising" v "technical/reference" is challenging
 * ✅ Linking: managed internal linking (`Page.clean_links()` method)
   *  Internal linking is a pain if applying the tree I would like to. Links aren't necessarily preserved. Upon writing it occurs to me that I could step up my use of obsidian as the editor, which would be convenient in a range of ways and not too wild. It will just be a matter of making the commitment to dump out from the django project.
* ✅ Fixed tree structure applying README as necessary
* ✅ Reliable way to move pages (`EuroPython2007` v `EuroPython/2007` problem)
* ✅ late update: upon cleaning up urls 437 previously untouched urls turned up which will need to be collected. I suspect that as I've pinged the channel about it that someone else is also working on this wiki replication effort, as it seems as though server has been down more frequently than I remember. It's handing about 2 requests per minute. Having said this, I don't think what ever comes out now will change anything substantially. -> a mere 7h32m later, we're done.


--

Icebox

* PSF wiki credits
