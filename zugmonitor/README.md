# YQL tables for Zugmonitor

This is an incomplete set of YQL tables for the [Zugmonitor API](http://www.opendatacity.de/zugmonitor-api/). This is the API that provides the data for the application [Zugmonitor](http://zugmonitor.sueddeutsche.de).

# Examples

## All stations

	SELECT * FROM zugmonitor.stations

## All cities

	SELECT * FROM zugmonitor.cities
	
## All trains on a given day

	SELECT * FROM zugmonitor.trains WHERE date="2012-03-09"