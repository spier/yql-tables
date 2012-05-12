# YQL tables for Klout API v2 (BETA)

[Klout API v2](http://klout.com/s/developers/v2) is currently in beta and is subject to change. Thar be dragons.

## Examples

Get Klout ID for a Twitter screenname

	SELECT * FROM klout2.identity WHERE twitter_screenname='sebastianspier' AND api_key='yourKeyGoesHere'

Get Klout ID for a Twitter ID

	SELECT * FROM klout2.identity WHERE twitter_id='96320763' AND api_key='yourKeyGoesHere'

Get the score of a Klout User	
	
  SELECT * FROM {table} WHERE klout_id='653149' AND data="score" AND api_key='yourKeyGoesHere'

Get the influencers and influencees of a Klout User	

	SELECT * FROM {table} WHERE klout_id='653149' AND data="influence" AND api_key='yourKeyGoesHere'

Get the topics of a Klout User	
	
	SELECT * FROM {table} WHERE klout_id='653149' AND data="topics" AND api_key='yourKeyGoesHere'