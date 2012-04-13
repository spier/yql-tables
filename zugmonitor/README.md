# YQL tables for Zugmonitor

This is an **incomplete** set of YQL tables for the [Zugmonitor API](http://www.opendatacity.de/zugmonitor-api/). This is the API that provides the data for the application [Zugmonitor](http://zugmonitor.sueddeutsche.de).

You can try out the working samples in the [YQL console][].

# Examples

## All stations

	SELECT * FROM zugmonitor.stations

## All cities

	SELECT * FROM zugmonitor.cities
	
## Get stations in Berlin
		SELECT * FROM zugmonitor.stations WHERE name LIKE "Berlin%"

		SELECT * FROM zugmonitor.cities WHERE name="Berlin"

## Get stations in Berlin and Hamburg
		SELECT * FROM zugmonitor.stations WHERE name LIKE "%Berlin%" OR name LIKE "%Hamburg%"
	
## All trains on a given day

	SELECT * FROM zugmonitor.trains WHERE day="2012-03-09"
	
## Only a specific train on a given day

	SELECT * FROM zugmonitor.trains WHERE day="2012-04-09" AND train_nr="ICE 721"

[YQL console]: http://developer.yahoo.com/yql/console/?env=https://raw.github.com/spier/yql-tables/zugmonitor/alltables_forked.env
	