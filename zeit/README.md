# YQL tables for ZEIT ONLINE Content API

These are inofficial YQL tables for the [ZEIT ONLINE Content API][zeit]. If you don't know YQL, I recommend to start with the documentation of the [Yahoo! Query Language][yql]. **Warning:** These YQL tables are only 90% finished, so they should be considered experimental.

## Benefits of using YQL

- prototype mashups of the ZEIT API with other APIs easily
- parallelize multiple calls to the ZEIT API with one YQL call (warning: be aware that this does not increase the rate limit that the ZEIT API gives you. no backdoors here!)
- convert JSON response to XML automatically - sorry for the ones who actually need that :)

## General

### Testing YQL calls

All YQL queries below can be tested in the [YQL Console][yql_console], by loading the environment file alltables_forked.env from this repository.

### Authentication

You need an API Key in order to use the ZEIT API. If you don't have one, you need to [register](http://developer.zeit.de/quickstart/). All YQL queries expects that you pass this API Key as parameter **api_key**. This key is then passed along to the ZEIT API as the **X-Authorization** header.

You can set the API Key for all YQL examples below like this:

    SET api_key="<YOUR API KEY HERE>" ON zeit;
    <YQL QUERY HERE>



## Simple Queries

### Search for author

    SELECT * FROM zeit.author
    WHERE q="Hans*";

### Show client details

    SELECT * FROM zeit.client     

### Search for content

See all matches, also including counts for *found*, *limit*, and *offset:

    SELECT * FROM zeit.content
    WHERE q="Umwelt";

See only the articles matching the search:

    SELECT matches FROM zeit.content
    WHERE q="Umwelt";

See the first 30 results (instead of the first 10, which is the default):

    SELECT matches FROM zeit.content(0,30)
    WHERE q="Umwelt";

Skip the first 100 results, and show results 101 to 123:

    SELECT matches FROM zeit.content(100,23)
    WHERE q="Umwelt";

### Retrieve all content metadata for one article

Get one article by its ID:

    SELECT * FROM zeit.content 
    WHERE id="6mpIkLngjOxBoMnwoauBoh";

Get only the categories of one article:

    SELECT categories FROM zeit.content 
    WHERE id="6mpIkLngjOxBoMnwoauBoh";

Get one article its URL:

  TBD

### Search for department

    SELECT * FROM zeit.department
    WHERE q="U*";  

### Search for keyword

    SELECT * FROM zeit.keyword
    WHERE q="Union*";

### Search for product

    SELECT * FROM zeit.product 
    WHERE q="*CAMPUS*";   

### Search for series

*Could not get the search for series to work*

    SELECT * FROM zeit.series 
    WHERE q="*";



## Advances Queries

These queries showcase some possibilities that YQL offers, which are extensions to the normal ZEIT API functionality.

### Get only the categories of one article that are associated with an department:

    SELECT categories FROM zeit.content 
    WHERE id="6mpIkLngjOxBoMnwoauBoh" AND categories.rel="department";

### Get all detailed metadata for a bunch of articles (joining multiple calls)

    SELECT * FROM zeit.content WHERE id IN (
      SELECT matches.uuid FROM zeit.content WHERE q="test"
    )




## TODO

Implementation tasks for these YQL tables.

- add sorting to /content
- add faceting to /content
- add field selection
- add calls like department/<id> etc
- explain YQL vs API field selection
- fix "get content by URI" call


[zeit]: http://developer.zeit.de/index/
[yql]: http://developer.yahoo.com/yql/
[yql_console]: http://developer.yahoo.com/yql/console/?env=https://raw.github.com/spier/yql-tables/zeit/alltables_forked.env
