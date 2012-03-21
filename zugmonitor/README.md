# YQL tables for Zugmonitor

This is an incomplete set of YQL tables for the [Zugmonitor API](http://www.opendatacity.de/zugmonitor-api/). This is the API that provides the data for the application [Zugmonitor](http://zugmonitor.sueddeutsche.de).

Unfortunately the train information cannot be retrieved with YQL. Reason:

>	Results may be truncated because the run exceeded the allowed max response timeout of 30000ms.

# Examples

## All stations

	SELECT * FROM zugmonitor.stations

## All cities

	SELECT * FROM zugmonitor.cities
	
## All trains on a given day

Warning: This data cannot be retrieved with YQL!

	SELECT * FROM zugmonitor.trains WHERE date="2012-03-09"
	
# Why use YQL for this?

Want to use XML instead of JSON? No problem, YQL got you covered.

## Get only the stations in Berlin
	SELECT * FROM zugmonitor.stations WHERE name LIKE "Berlin%"
	
## Get only the stations in Berlin, and select the *name* of the station only
	SELECT name FROM zugmonitor.stations WHERE name LIKE "%Berlin%" OR name LIKE "%Hamburg%"