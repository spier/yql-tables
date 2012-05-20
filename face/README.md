# YQL tables for face.com

This is an **incomplete** set of YQL tables for the [face.com](http://face.com) API!
The only currently implemented table is the one for the face.detect API call.

## Examples

Standard API call to perform face detection of a Twitter profile image

	SELECT * FROM faces.detect 
	WHERE
	api_key="YOUR_KEY"
	AND api_secret="YOUR_SECRET"
	AND urls="https://si0.twimg.com/profile_images/1735360254/icon_normal.jpg"

Next up a little bit more interesting use case that showcases the power of YQL.
Searches for Twitter users that have written about "food", takes their profile images, and then performs face detection on all of them in batch.

	SELECT * FROM faces.detect 
	WHERE
	api_key="YOUR_KEY"
	AND api_secret="YOUR_SECRET"
	AND urls IN (
		SELECT profile_image_url FROM twitter.search WHERE q='food' LIMIT 10
	)