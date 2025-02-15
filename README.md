# Replica of Python (official) Wiki

OriginaL: https://wiki.python.org/

2025-02-15:

**It seems to be the year of the python wiki!** Independently it seems as though several people/groups have got an interest in this wiki. I am one of those people, though it is only now it's coming to light how many people were interested.

For myself, I wanted to get an understanding of what the wiki "looked Like" to do some analysis on.

Additionally it seemed like fun to see if it was replicable here, using the default wiki available with this tooling, so here we are.

--

**TODO:**

* Add a list of `active-pages`. Criteria:
  * not User pages (don't feel authority on these, though these are hard to identify -> perhaps seperate list of user pages, this is easy and should be done, adding now)
  * arbitrary, I reckon maybe back to around 2016 as ordered by `last edited` date, this is ~400 pages including users, I think will come down to maybe ~250-300
  * all pages linked from https://wiki.python.org/moin/LocalUserGroups ✨ irrespective of date
* Add list of `user-pages` (easily defined as they will be represented after `last edited by`, with some nuances and likely imperfect)
* Add list of `local-user-group-pages` (as linked per above)

Next:

* New directory tree and commit here:
  * `Historical`
  * `LocalUserGroups`
  * `User` directory which will contain all user pages irrespective of date
  * ?? rest of pages, don't want noise, maybe "`pages`" or "`active-pages`" or "`wiki`"? tbd
* Backfill revision history for active pages
* New django model for users (obviously not called users)

**Completed:**

* Small django project that contains the whole db (last updated 2025-02-09)
* Basic overview: contains 2,636 pages and 849 unique contributors
* Converted all content to markdown
