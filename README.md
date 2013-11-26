make-calendar-ics
=================

Take simple descriptions of calendar events and transform them into an ICS
file that can be imported by various calendar applications.

The simple descriptions look like this:

    date time duration reminder subject

Example:

    04/09/2011 11:30am 1hr 15min Jenna's soccer

One event per line.  In this example, 1hr is the duration and 15min is the
reminder.

The duration and reminder can be any of these forms:

    15min 15m 15mins
    1hr   1h  2hrs
    1day  1d  2days
    0

Use "-" for no reminder.

For all-day events, replace the time and duration fields with "-":

    4/9/2011 - - 15min No school

Dates are in the form mm/dd/yyyy.  If the year is specified it must be four
digits.  If the year is not specified, the year from the previous line is used
or the current year if there is no previous line.  If a given event recurs
over several days, you may specify only the dates for the 2nd and subsequent
occurrences.

Example:

    5/24/2012 9am 1hr 15min Status
    5/31
    6/7
    6/14

Times are in the form hh:mmap.  hh is one or two digits.  mm must be two
digits if present.  If ":mm" is missing it is assumed to be ":00".  "ap" can
be any of: AM, PM, A, P (caseless).
