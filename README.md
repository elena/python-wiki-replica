# Replica of Python (official) Wiki

OriginaL: https://wiki.python.org/

2025-02-15:

**It seems to be the year of the python wiki!** Independently it seems as though several people/groups have got an interest in this wiki. I am one of those people, though it is only now it's coming to light how many people were interested.

For myself, I wanted to get an understanding of what the wiki "looked Like" to do some analysis on.

Additionally it seemed like fun to see if it was replicable here, using the default wiki available with this tooling, so here we are.

--

**TODO:**

* Add a list of "active-pages". Criteria:
  * not User pages (don't feel authority on these, though these are hard to identify -> perhaps seperate list of user pages, this is easy and should be done, adding now)
  * arbitrary, I reckon maybe last ~400-or-so pages this is back to end of 2016
  * all pages linked from https://wiki.python.org/moin/LocalUserGroups ✨
* Add list of "user-pages" (easily defined as they will be represented after `last edited by`)

**Completed:**

* Small django project that contains the whole db (last updated 2025-02-09)
* Basic overview: contains 2,636 pages and 849 unique contributors
* Converted all content to markdown
