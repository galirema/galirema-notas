

|Property Name|Value|Description|Notes|
|-------------|-----|-----------|-----|
|kind|string|The fixed string "urlshortener#url".||
|id|string|Short URL, e.g. "http://goo.gl/l6MS".||
|longUrl|string|Long URL, e.g. "http://www.google.com/". Might not be present if the status is "REMOVED".||
|status|string|Status of the target URL. Possible values: "OK", "MALWARE", "PHISHING", or "REMOVED". A URL might be marked "REMOVED" if it was flagged as spam, for example.||
|created|string|Time the short URL was created; ISO 8601 representation using the yyyy-MM-dd'T'HH:mm:ss.SSSZZ format, e.g. "2010-10-14T19:01:24.944+00:00".||
|analytics|nested object|A summary of the click analytics for the short and long URL. Might not be present if not requested or currently unavailable.||
|analytics.allTime|nested object|Click analytics over all time.||
|analytics.allTime.shortUrlClicks|long|Number of clicks on this short URL.||
|analytics.allTime.longUrlClicks|long|Number of clicks on all goo.gl short URLs pointing to this long URL.||
|analytics.allTime.referrers[]|list|Top referring hosts, e.g. "www.google.com"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.allTime.referrers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.allTime.referrers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.allTime.countries[]|list|Top countries (expressed as country codes), e.g. "US" or "DE"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.allTime.countries[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.allTime.countries[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.allTime.browsers[]|list|Top browsers, e.g. "Chrome"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.allTime.browsers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.allTime.browsers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.allTime.platforms[]|list|Top platforms or OSes, e.g. "Windows"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.allTime.platforms[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.allTime.platforms[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".|
|analytics.month|nested object|Click analytics over the last month.||
|analytics.month.shortUrlClicks|long|Number of clicks on this short URL.||
|analytics.month.longUrlClicks|long|Number of clicks on all goo.gl short URLs pointing to this long URL.||
|analytics.month.referrers[]|list|Top referring hosts, e.g. "www.google.com"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.month.referrers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.month.referrers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.month.countries[]|list|Top countries (expressed as country codes), e.g. "US" or "DE"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.month.countries[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.month.countries[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.month.browsers[]|list|Top browsers, e.g. "Chrome"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.month.browsers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.month.browsers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.month.platforms[]|list|Top platforms or OSes, e.g. "Windows"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.month.platforms[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.month.platforms[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.week|nested object|Click analytics over the last week.||
|analytics.week.shortUrlClicks|long|Number of clicks on this short URL.||
|analytics.week.longUrlClicks|long|Number of clicks on all goo.gl short URLs pointing to this long URL.||
|analytics.week.referrers[]|list|Top referring hosts, e.g. "www.google.com"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.week.referrers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.week.referrers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.week.countries[]|list|Top countries (expressed as country codes), e.g. "US" or "DE"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.week.countries[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.week.countries[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.week.browsers[]|list|Top browsers, e.g. "Chrome"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.week.browsers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.week.browsers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.week.platforms[]|list|Top platforms or OSes, e.g. "Windows"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.week.platforms[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.week.platforms[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.day|nested object|Click analytics over the last day.||
|analytics.day.shortUrlClicks|long|Number of clicks on this short URL.||
|analytics.day.longUrlClicks|long|Number of clicks on all goo.gl short URLs pointing to this long URL.||
|analytics.day.referrers[]|list|Top referring hosts, e.g. "www.google.com"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.day.referrers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.day.referrers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.day.countries[]|list|Top countries (expressed as country codes), e.g. "US" or "DE"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.day.countries[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.day.countries[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.day.browsers[]|list|Top browsers, e.g. "Chrome"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.day.browsers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.day.browsers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.day.platforms[]|list|Top platforms or OSes, e.g. "Windows"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.day.platforms[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.day.platforms[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.twoHours|nested object|Click analytics over the last two hours.||
|analytics.twoHours.shortUrlClicks|long|Number of clicks on this short URL.||
|analytics.twoHours.longUrlClicks|long|Number of clicks on all goo.gl short URLs pointing to this long URL.||
|analytics.twoHours.referrers[]|list|Top referring hosts, e.g. "www.google.com"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.twoHours.referrers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.twoHours.referrers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.twoHours.countries[]|list|Top countries (expressed as country codes), e.g. "US" or "DE"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.twoHours.countries[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.twoHours.countries[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.twoHours.browsers[]|list|Top browsers, e.g. "Chrome"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.twoHours.browsers[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.twoHours.browsers[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||
|analytics.twoHours.platforms[]|list|Top platforms or OSes, e.g. "Windows"; sorted by (descending) click counts. Only present if this data is available.||
|analytics.twoHours.platforms[].count|long|Number of clicks for this top entry, e.g. for this particular country or browser.||
|analytics.twoHours.platforms[].id|string|Label assigned to this top entry, e.g. "US" or "Chrome".||

 [Volver a goo Galirema](gooGalirema.md)

