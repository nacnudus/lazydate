# lazydate

An R package for handling incomplete dates and times like years with months but no days, operations like December + 1 month = January, subsetting certain times of day on all dates, and arbitrary date/time specifications like financial years and the French Republican Calendar.

## Ideas

* Check out zoo, quantmod, xts, etc. (see lubridate README)
* Interface with actual dates
* Parameter to specify rounding to start/end of a lazy unit
* Arithmetic to go around a list back to the beginning and compute both distances between two points (backwards, forwards)
* Subsetting lazily, e.g. get all March regardless of year
* Tally missing-date objects with ordinary date objects (e.g. tally weekdays-only with complete weeks)
* Fit models taking irregular periodicity (e.g. Easter) into account.
* Where there isn't enough information for exact arithmetic, return a vector c(min, max)
* If using angles of circles to represent periods, why not use angles of elipses too, to represent nominal periods that change actual duration predictably through one cycle, e.g. daytime through the year.

## Clock Formulae

```
between <- function(earlier, later) {
  Mod(24 + (2 - 23), 24) = 3
  Mod(24 + (23 - 2), 24) = 21
  Mod(24 + (2 - 1), 24) = 1
  Mod(24 + (2 - 0), 24) = 2
  Mod(24 + (2 - 2), 24) = 0 # or 24---special case
  Mod(24 + (2 - 3), 24) = 23
}
```

When including minutes, convert all figures to minutes first, do the sum, then convert back to HH:MM, e.g. 02:20 - 01:50 = 140 - 110 = 30 = 00:30.

