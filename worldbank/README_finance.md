# YQL tables for World Bank Finance API

The World Bank *Finance* API is provided by [Socrata](http://opendata.socrata.com/api/docs/).
Therefore the calls are a different than other calls to the World Bank API.

I tried to align them as much as possible.



## Examples

* Get the id and name of the first 20 Views.
	SELECT id, name FROM wb.finance.views(0,20)
	
* Get a specific view by ID
	SELECT * FROM wb.finance.views.details WHERE view_id="sfv5-tf7p"
	
* Get the names of two views (in one call)

	SELECT name FROM wb.finance.views.details WHERE view_id="rnku-kcby" OR view_id="wc6g-9zmq" 

* Get the id and name of the first 20 Views. Sort them by name. (Warning: This fetches the 20 Views first, and then sorts them. So this sorting is not over the full set of Views but just over the first 20!)

	SELECT id, name FROM  wb.finance(0,20) | sort(field="name")

* Get the id and name of the first 201 Views. (Normally the result limit is 200 for one call to the Socrata API. YQL does the pagination for you, so you can get more in one call if needed.)

        SELECT id, name FROM socrata.views(0,201)



## References

# 19 finance datasets of the World Bank [https://finances.worldbank.org/page/datasets](https://finances.worldbank.org/page/datasets)
# [Socrata API Documentation](http://opendata.socrata.com/api/docs/)

