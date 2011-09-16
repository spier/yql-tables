# Tables for Berlin Open Data

Experiment to map the APIs from [Berlin Open Data][] to YQL tables to create a more uniform access.

If you consider this an interesting idea and want to chat about it, contact me on [Twitter](http://twitter.com/#!/sebastianspier/).

# Some of the Available APIs
- http://www.berlin.de/sen/finanzen/haushalt/zuwendungen/
- http://www.berlin.de/ba-charlottenburg-wilmersdorf/org/umwelt/umwelt/altglascontainer/
- ...

[Documentation of SimpleSearch](http://support.berlin.de/wiki/index.php/SimpleSearch)

# Examples

	SELECT * FROM bod.zuwendungen WHERE query="berlin" - [Try it!](http://yhoo.it/p076Uw)
	
	SELECT * FROM bod.altglascontainer WHERE plz="10585" - [Try it!](http://yhoo.it/phPho6)

# Open Items

- should the query parameters be translated to English? the input and return values will be German anyways
- test with some more APIs
- add more examples of how to use this
- handle caching on YQL side

[Berlin Open Data]: http://daten.berlin.de