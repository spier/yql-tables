# Tables for Berlin Open Data

Experiment to map many APIs from [Berlin Open Data][] to YQL tables to create a more uniform access



http://support.berlin.de/wiki/index.php/SimpleSearch

# Examples

To query some data from http://www.berlin.de/sen/finanzen/haushalt/zuwendungen/index.php one would write a YQL query like this:

	SELECT * FROM bod.simplesearch.finance WHERE query="berlin"


# TODO

- should the query parameters be translated to English? the input and return values will be German anyways
- some more examples of how to use this
- handle caching on YQL side





[Berlin Open Data]: http://daten.berlin.de