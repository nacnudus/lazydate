lazydate
========

An R package for handling incomplete dates and times like years with months but no days, operations like December + 1 month = January, and arbitrary date/time specifications like financial years and the French Republican Calendar.

Ideas
-----

* Check out zoo, quantmod, xts, etc. (see lubridate README)
* Interface with actual dates
* Parameter to specify rounding to start/end of a lazy unit
* Arithmetic to go around a list back to the beginning and compute both distances between two points (backwards, forwards)
* Tally missing-date objects with ordinary date objects (e.g. tally weekdays-only with complete weeks)
* Fit models taking irregular periodicity (e.g. Easter) into account.
* Where there isn't enough information for exact arithmetic, return a vector c(min, max)
