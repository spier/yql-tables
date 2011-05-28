# My Personal Fork of the YQL Datatables

## Disclaimer

This is my personal fork of the original [YQL Community tables][yql_community]. If you want to find the latest version of the YQL tables, please go to the original.  

## What is YQL? 

From the [Yahoo's YQL website][yql]:
> The Yahoo! Query Language is an expressive SQL-like language that lets you query, filter, and join data across Web services. With YQL, apps run faster with fewer lines of code and a smaller network footprint.

## Why do you have a personal fork?

I am a YQL enthusiast. I love the general idea and also the current implementation (for the most parts). The [YQL Community tables][yql_community] are great but also fairly slow when it comes to incorporating recent updates. Therefore I am using this repository as my personal playground when it comes to YQL. In pull the latest changes from the [YQL Community tables][yql_community] as I need them but at the same time I can always do random experiments here without being depended on the original repository.

## YQL issues

As I said, YQL is great. As any piece of software it also has some flaws (as in bugs) and some other things that I just don't like that much, which is more a matter of personal taste. Also there are some areas of YQL that I just don't understand.

Therefore I am sometimes collecting some thoughts about YQL on [Twitter][seb_twitter]. See some examples below. I am happy to learn more about them or discuss with anybody who is interested in YQL.

@yql #issues no. 1: How to keep a given API and the corresponding datatable in sync as API gets updated?
@yql #issues no. 2: How to measure the "coverage" of a datatable, meaning how many calls of an API are implemented by the datatable? #in
@yql #issues no. 3: How to introduce and maintain naming conventions for the naming of "keys" across different datatables?
@yql #issues no. 4: Would be great to access usage stats for datatables that I did, to see how people use them. #optimization #motivation
@yql #issues no. 5: How to search for existing community datatables? The console is fine but could be better.
@yql #issues no. 6: Why can I not access/use values from a Sub-Select besides using the IN-syntax? Would allow for richer queries.
@yql #issues no. 7: How to test datatables, e.g. to be notified when the underlying API changes or gets deprecated like
@yql #issues no. 8: The error messages are just not clear :( Except this one of course "Yahoo! - 999 Unable to process request at this time"

## YQL Resources

* [Yahoo's YQL website][yql]
* [YQL Blog][yql_blog]
* [YQL Community tables][yql_community]
* [YQL Console][yql_console] - try out YQL commands yourself


[yql]: http://developer.yahoo.com/yql/
[yql_community]: https://github.com/yql/yql-tables
[yql_blog]: http://www.yqlblog.net/blog/
[yql_console]: http://developer.yahoo.com/yql/console/
[seb_twitter]: https://twitter.com/#!/sebastianspier

