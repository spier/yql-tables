# Tables for Berlin Open Data

Experiment to map the APIs from [Berlin Open Data][] to YQL tables to create a more uniform access.

# Some of the Available APIs
- [http://www.berlin.de/sen/finanzen/haushalt/zuwendungen/index.php]
- [http://www.berlin.de/ba-charlottenburg-wilmersdorf/org/umwelt/umwelt/altglascontainer/]
- ...

[Documentation of SimpleSearch](http://support.berlin.de/wiki/index.php/SimpleSearch)

# Examples

	SELECT * FROM bod.zuwendungen WHERE query="berlin"
	
	SELECT * FROM bod.altglascontainer WHERE plz="10585"

# TODO

- should the query parameters be translated to English? the input and return values will be German anyways
- some more examples of how to use this
- handle caching on YQL side


[Berlin Open Data]: http://daten.berlin.de