# YQL tables for ZEIT ONLINE Content API

These are inofficial YQL tables for the [ZEIT ONLINE Content API](http://developer.zeit.de/index/).
If you don't know what YQL is, I reccomend to start with the documentation of the [Yahoo! Query Language](http://developer.yahoo.com/yql/).

Some advantages of using YQL in the context of this API:

- mashup ZEIT API with other APIs easily
- parallelize multiple calls to the ZEIT API with one YQL call (warning: be aware that this does not increase the rate limit that the ZEIT API gives you. no backdoors here!)
- convert JSON response to XML automatically - sorry for the ones who actually need that :)

# TODO

- fix "get content by URI" call
- mention that one YQL call may lead to multiple API calls (wrapper functionality)
- add sorting to /content
- add faceting to /content
- add field selection
- add calls like department/<id> etc
- explain YQL vs API field selection


# General

## Testing YQL calls

All YQL queries below can be tested in the [YQL Console](http://developer.yahoo.com/yql/console/?env=https://raw.github.com/spier/yql-tables/zeit/alltables_forked.env), by loading the environment file alltables_forked.env from this repository.

## Authentication

Each of the YQL tables expects that you pass your API Key as parameter *api_key*.
This key is then passed along to the ZEIT API as the *X-Authorization* header.

You need an API Key in order to use the ZEIT API.
You can set the API Key for all YQL examples below like this:

    SET api_key="<API KEY HERE>" ON zeit;
    <YQL COMMAND HERE>




# Simple Queries

## Show client details

    SELECT * FROM zeit.client 

## Search for author

    SELECT * FROM zeit.author
    WHERE q="Hans*";

## Search for product

    SELECT * FROM zeit.product 
    WHERE q="*CAMPUS*";   

## Search for series

*Could not get the search for series to work*

    SELECT * FROM zeit.series 
    WHERE q="*";

## Search for keyword

    SELECT * FROM zeit.keyword
    WHERE q="Union*";

## Search for department

    SELECT * FROM zeit.department
    WHERE q="U*";

## Search for content

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

## Retrieve all content metadata for one article

Get one article by its ID:

    SELECT * FROM zeit.content 
    WHERE id="6mpIkLngjOxBoMnwoauBoh";

Get only the categories of one article:

    SELECT categories FROM zeit.content 
    WHERE id="6mpIkLngjOxBoMnwoauBoh";

Get one article its URL:

  TBD



# Advances Examples

These YQL examples represent extensions to the normal ZEIT API functionality.


## Get only the categories of one article that are associated with an department:

    SELECT categories FROM zeit.content 
    WHERE id="6mpIkLngjOxBoMnwoauBoh" AND categories.rel="department";

## Get all detailed metadata for a bunch of articles (joining multiple calls)

    SELECT * FROM zeit.content WHERE id IN (
      SELECT matches.uuid FROM zeit.content WHERE q="test"
    )

## Field selection

Select only uuid, title, and relations

    SELECT uuid, title, relations FROM zeit.content WHERE id IN (
      SELECT matches.uuid FROM zeit.content WHERE q="test"
    )

