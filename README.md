🧰 search_local Tool Documentation
The search_local tool is a wrapper for SerpApi that allows you to fetch local search results from Google Local. It is implemented as a FastMCP tool and can be easily integrated into agent or multi-modal systems.

🚀 Overview
This tool uses SerpApi’s google_local engine to simulate Google Local search from different locations, devices, and languages. It is useful for retrieving business listings, places, and services based on locality.

📦 Import
from mcp.server import FastMCP
from fastmcp import Context
🛠️ Usage Example
search_local(q="coffee shop", location="San Francisco, CA")
📌 Parameters
Parameter	Type	Required	Description
q	str	✅ Yes	The search query, just like you would enter in a regular Google Local search.
location	str or None	❌ No	Defines the location from which the search originates. Recommended to use city-level names. Cannot be used with uule.
uule	str or None	❌ No	Google’s encoded location string. Cannot be used with location.
google_domain	str or None	❌ No	Defines the Google domain (e.g. google.com, google.co.uk). Defaults to google.com.
gl	str or None	❌ No	Country code (e.g. us, uk, fr).
hl	str or None	❌ No	Language code (e.g. en, es, fr).
start	int or None	❌ No	Pagination offset. Desktop: multiples of 20, Mobile: multiples of 10.
device	str or None (desktop / tablet / mobile)	❌ No	Defines the type of device for the search. Defaults to desktop.
no_cache	bool or None	❌ No	Forces SerpApi to fetch fresh results. Set to True to disable cache. Cannot be used with aasync.
aasync	bool or None	❌ No	Enables asynchronous search. Use the SerpApi Archive API to fetch results later. Not compatible with no_cache.
🔐 Environment Setup
Make sure to set your SerpApi key in a .env file:

SERP_API_KEY=your_serp_api_key_here
🧪 Sample Response (JSON)
{
  "local_results": [
    {
      "title": "Blue Bottle Coffee",
      "rating": 4.5,
      "reviews": 832,
      "address": "66 Mint St, San Francisco, CA",
      "phone": "(415) 123-4567"
    },
    ...
  ]
}
⚠️ Notes
location and uule cannot be used together.
no_cache and aasync should not be used together.
Cached results are free and expire after 1 hour.
The response format may change depending on SerpApi updates.
Let me know if you need a version for a specific platform like GitHub README or API docs!
