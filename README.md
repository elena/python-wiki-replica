# Replica of Python Wiki

OriginaL: https://wiki.python.org/

**It seems to be the year of the python wiki!** Independently it seems as though several people/groups have got an interest in this wiki. I am one of those people, though it is only now it's coming to light how many people were interested.

For myself, I wanted to get an understanding of what the wiki "looked Like" to do some analysis on.

Additionally it seemed like fun to see if it was replicable here, using the default wiki available with this tooling, so here we are.

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

This is still rough but care has been taken, the balance feels good and fair.

Some inspiration was taken from the existing "Category____" setup: https://wiki.python.org/moin/FrontPage?action=fullsearch&context=180&value=Category&titlesearch=Titles

A few "design decision" things are in my way currently:

* Today github wiki seem "flat", ie, it doesn't support wiki with directory/tree structure as moin does
  * -> this is fine I will fall back to using the main repo, but still thinking about this.
* Preserving history
  * Can see many approaches but developing the idea
* Links management
  * Some are broken
  * Internal linking is a pain if applying the tree I would like to. Links aren't necessarily preserved. Upon writing it occurs to me that I could step up my use of obsidian as the editor, which would be convenient in a range of ways and not too wild. It will just be a matter of making the commitment to dump out from the django project.
 
The final mopping up after the above are resolved is to upload the workings. These are:

* local django wip project including db.sqlite3 db
* full dump of md conversion
* original collected html files

Link management will be perenniel. Further down the track some kind of automation can by applied to assist in managing this.

---

2025-02-15:

**TODO:**

    
Next:

* New directory tree and commit here:
  * `users` directory which will contain all user pages irrespective of date
  * rest of pages, wip
    * grouping "organising" v "technical/reference" is challenging 
* Work on links
  * links back to original site
  * internal links are as expected
  * ?? broken links (can: remove, annotate, ??)
* Backfill revision history for active pages


**Completed:**

* Small django project that contains the all files collected using both linked-graph (this capture to 2025-02-09) and any further from `/moin/TitleIndex` (as recommended from mailing list).
* Basic overview: contains 2,636 pages and 849 unique contributors
* Converted all content to markdown
* List of `active-pages`. Criteria:
  * not User pages (don't feel authority on these, though these are hard to identify -> perhaps seperate list of user pages, this is easy and should be done, adding now)
  * arbitrary, I reckon maybe back to around 2016 as ordered by `last edited` date, this is ~400 pages including users, I think will come down to maybe ~250-300
* List of `user-pages` (easily defined as they will be represented after `last edited by`, with some nuances and likely imperfect)
* New django model for users (obviously not called users)
* List of `local-user-group-pages` (as linked per above)
  * all pages linked from https://wiki.python.org/moin/LocalUserGroups ✨ irrespective of date
* Fix white space in md
* Determinee most populated root-node pages, adjust and populate django models as necessary
* Experiment committing tree structure to github wiki


--

Icebox

* PSF wiki credits
* EuroPython2007/EuroPython2008
