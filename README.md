# Google Play Reviews Scraper

[<img width="950" height="300" alt="Google Play Store Reviews scraper" src="https://github.com/user-attachments/assets/1e8617f2-1909-47f1-8e22-6404ccc39482" />](https://serpapi.com/google-play-product-reviews?utm_source=github_google_play_reviews_scraper)

Google Play Reviews Scraper - A tool to scrape user reviews from the Google Play Store with a simple API. Get review details like rating, text content, date, user info, and engagement metrics.

We provide the results in a structured JSON format, eliminating the need for parsing, coding, proxies, or any other web scraping headaches for developers.

## How to scrape Google Play Reviews?

Using a simple GET request, you can retrieve Google Play product reviews:

```
https://serpapi.com/search.json?engine=google_play_product&product_id=com.google.android.apps.maps&store=apps&all_reviews=true&api_key=YOUR_API_KEY
```

- Register for free at [SerpApi to get your API Key](https://serpapi.com?utm_source=github_google_play_reviews_scraper)
- `product_id` parameter: defines the product ID to look up reviews for.
- `store` parameter: defines the type of Google Play store (e.g., `apps`).
- `all_reviews` parameter: must be set to `true` to enable review retrieval with filtering.

## Code examples
Here are some code examples based on your favorite programming languages.

### cURL Integration

``` bash
curl --get https://serpapi.com/search \
 -d engine="google_play_product" \
 -d product_id="com.google.android.apps.maps" \
 -d store="apps" \
 -d all_reviews="true" \
 -d sort_by="2" \
 -d api_key="secret_api_key"
```

### Python Integration

Step 1:
Create a new `main.py` file.

Step 2:
Install [requests package](https://pypi.org/project/requests/) with:
```
pip install requests
```

Step 3:
Add this code to your file:
``` py
import requests
SERPAPI_API_KEY = "YOUR_SERPAPI_API_KEY"

params = {
    "api_key": SERPAPI_API_KEY,
    "engine": "google_play_product",
    "product_id": "com.google.android.apps.maps",
    "store": "apps",
    "all_reviews": "true",
    "sort_by": "2"
}

search = requests.get("https://serpapi.com/search", params=params)
response = search.json()
print(response)
```

If you're only interested in the `reviews`, you can print them from the response directly:

``` py
print(response["reviews"])
```

### JavaScript Integration

Step 1:
Install the [SerpApi JavaScript package](https://github.com/serpapi/serpapi-javascript):
```
npm install serpapi
```

Step 2:
Create a new `index.js` file.

Step 3:
Add this to your file:
``` js
const { getJson } = require("serpapi");
getJson({
  api_key: API_KEY,
  engine: "google_play_product",
  product_id: "com.google.android.apps.maps",
  store: "apps",
  all_reviews: "true",
  sort_by: "2"
}, (json) => {
  console.log(json["reviews"]);
});
```

### Other Programming Languages
While you can use our APIs using a simple GET request with any programming language, you can also see our ready-to-use libraries here: [SerpApi Integrations](https://serpapi.com/integrations?utm_source=github_google_play_reviews_scraper).

## Google Play Reviews Scraper Parameters
Please find the parameters for the Google Play Product Reviews API below:

| Name               | Description                                                                                                  | Requirement |
|--------------------|--------------------------------------------------------------------------------------------------------------|-------------|
| product_id         | Parameter defines the product ID to look up reviews for                                                      | Required    |
| store              | Parameter defines the store type (e.g., `apps`)                                                              | Required    |
| all_reviews        | Parameter to enable review retrieval: `true` or `false` (default)                                           | Required    |
| **Filters**        |                                                                                                              |             |
| platform           | Parameter to filter reviews by device: `phone` (default), `tablet`, `watch`, `chromebook`, or `tv`          | Optional    |
| rating             | Parameter to filter reviews by star rating (1-5)                                                             | Optional    |
| **Sorting**        |                                                                                                              |             |
| sort_by            | Parameter to sort reviews: `1` (most relevant, default), `2` (newest), `3` (rating)                         | Optional    |
| **Pagination**     |                                                                                                              |             |
| num                | Parameter defines the maximum number of reviews per request (default: 40, max: 199)                         | Optional    |
| next_page_token    | Parameter to retrieve subsequent page results                                                                | Optional    |
| **Localization**   |                                                                                                              |             |
| gl                 | Parameter defines the two-letter country code (default: `us`)                                                | Optional    |
| hl                 | Parameter defines the two-letter language code (default: `en`)                                               | Optional    |

Visit [our documentation](https://serpapi.com/google-play-product-reviews) for more information on all available parameters.


## Available data on Google Play Reviews (JSON Response)
Google Play Reviews API returns review data in the `reviews` array. Here is what each review object may contain:

``` json
"reviews": [
  {
    "id": "String - Unique review identifier",
    "title": "String - Reviewer name",
    "avatar": "String - URL to the reviewer's profile image",
    "rating": "Integer - Star rating (1-5)",
    "snippet": "String - Review text content",
    "likes": "Integer - Number of likes on the review",
    "date": "String - Human-readable date (e.g., 'Jan 15, 2025')",
    "iso_date": "String - ISO 8601 timestamp"
  }
]
```

The API response also includes:
- `serpapi_pagination`: Contains `next_page_token` for retrieving additional reviews

## Tutorial
- [Video on scraping Google Play Store App Reviews](https://www.youtube.com/watch?v=V-uc-Fi9SpI)
- [Blog - Scrape All Google Play App Reviews in Python](https://serpapi.com/blog/scrape-all-google-play-app-reviews-in-python/)

## Use cases
Here are some use cases for the Google Play Reviews API:

- Monitor user sentiment by scraping and analyzing app reviews over time.
- Filter reviews by star rating to identify common complaints or praise.
- Track reviews by device platform to find device-specific issues.
- Build review aggregation dashboards for app portfolio management.
- Perform NLP and sentiment analysis on review text for product insights.
- Compare review trends across competitor apps.

## Related scraper
- [Google Play Store Scraper](https://github.com/serpapi/google-play-scraper/)

## Contacts
Feel free to reach out via `contact@serpapi.com`.

Check other [Google Scrapers](https://github.com/serpapi/google-scraper) from SerpApi.
