# My Personal Fork of the YQL Datatables

## Disclaimer

This is my personal fork of the original [YQL open data tables][yql_open_data_tables_github]. If you want to find the latest version of the YQL tables, please go to the original.  

## What is YQL? 

From the [Yahoo's YQL website][yql]:

> The Yahoo! Query Language is an expressive SQL-like language that lets you query, filter, and join data across Web services. With YQL, apps run faster with fewer lines of code and a smaller network footprint.

## Why do you have a personal fork?

I am a YQL enthusiast. I love the general idea and also the current implementation (for the most parts). The [Open Data Tables][yql_open_data_tables] are great but sometimes a bit slow when it comes to incorporating recent updates. Therefore I am using this repository as my personal playground. I pull the latest changes from the [YQL Community tables][yql_open_data_tables_github] as I need them but at the same time I can always do random experiments here without being depended on the original repository.

## YQL issues

As I said, YQL is great. As any piece of software it also has some flaws (as in bugs) and some other things that I just don't like that much, which is more a matter of personal taste. Also there are some areas of YQL that I just don't understand.

Therefore I am sometimes collecting some thoughts about YQL on [Twitter][seb_twitter]. See some examples below. I am happy to learn more about them or discuss with anybody who is interested in YQL.

1. How to keep a given API and the corresponding datatable in sync as API gets updated?
1. How to measure the "coverage" of a datatable, meaning how many calls of an API are implemented by the datatable? #in
1. How to introduce and maintain naming conventions for the naming of "keys" across different datatables?
1. Would be great to access usage stats for datatables that I did, to see how people use them. #optimization #motivation
1. How to search for existing community datatables? The console is fine but could be better.
1. Why can I not access/use values from a Sub-Select besides using the IN-syntax? Would allow for richer queries.
1. How to test datatables, e.g. to be notified when the underlying API changes or gets deprecated like
1. The error messages are just not clear :( Except this one of course "Yahoo! - 999 Unable to process request at this time"

## YQL Resources

* General Information
	* [Yahoo's YQL website][yql]
	* [YQL Blog][yql_blog]
	* [YQL Forum][yql_forum]
* Hacking 
	* [YQL Guide][yql_documentation] - Documentation
	* YQL Open Data Tables [Website][yql_open_data_tables] and [github project][yql_open_data_tables_github]
	* [YQL Console][yql_console] - try out YQL commands yourself




[yql]: http://developer.yahoo.com/yql/
[yql_open_data_tables]: http://www.datatables.org
[yql_open_data_tables_github]: https://github.com/yql/yql-tables
[yql_blog]: http://www.yqlblog.net/blog
[yql_forum]: http://developer.yahoo.net/forum/index.php?showforum=41
[yql_documentation]: http://developer.yahoo.com/yql/guide/
[yql_console]: http://developer.yahoo.com/yql/console/?q=show%20tables&env=store://datatables.org/alltableswithkeys
[seb_twitter]: https://twitter.com/#!/sebastianspier

