# YQL tables for Zugmonitor

This is an incomplete set of YQL tables for the [Zugmonitor API](http://www.opendatacity.de/zugmonitor-api/). This is the API that provides the data for the application [Zugmonitor](http://zugmonitor.sueddeutsche.de).

Unfortunately the information about the status of the trains cannot be retrieved with YQL. Reason:

>	Results may be truncated because the run exceeded the allowed max response timeout of 30000ms.

You can try out the working samples below by opening the [YQL console][] and pasting them there.

# Examples

## All stations

	SELECT * FROM zugmonitor.stations

## All cities

	SELECT * FROM zugmonitor.cities
	
## Get stations in Berlin
		SELECT * FROM zugmonitor.stations WHERE name LIKE "Berlin%"

## Get stations in Berlin and Hamburg
		SELECT * FROM zugmonitor.stations WHERE name LIKE "%Berlin%" OR name LIKE "%Hamburg%"
	
## All trains on a given day

Warning: This data cannot be retrieved with YQL!

	SELECT * FROM zugmonitor.trains WHERE date="2012-03-09"


[YQL console]: http://developer.yahoo.com/yql/console/?env=https://raw.github.com/spier/yql-tables/zugmonitor/alltables_forked.env
	