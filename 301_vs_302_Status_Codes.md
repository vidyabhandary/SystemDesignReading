## 301 vs 302 Status Codes

### Overview

Both **301** and **302** are HTTP status codes used for URL redirection, but they serve different purposes and have important implications for browsers, users, and search engines.

### 301 Moved Permanently

- **Purpose:** Indicates that a resource has been permanently moved to a new URL.
- **Browser Behavior:** Browsers and clients should update bookmarks and always use the new URL for future requests.
- **Search Engine Impact:** Search engines transfer ranking (SEO value, PageRank) from the old URL to the new one. The old URL will eventually be replaced in their index with the new URL.
- **Use Case:** Website migrations, permanent URL changes, consolidating content.

**Example:**
`GET /old-page` → `301 Moved Permanently` with `Location: /new-page`

### 302 Found (Moved Temporarily)

- **Purpose:** Indicates that a resource is temporarily available at a different URL, but the client should continue to use the original URL for future requests.
- **Browser Behavior:** Browsers redirect users for the current request, but do not update bookmarks. The original URL is still considered valid.
- **Search Engine Impact:** Search engines generally do not transfer ranking or SEO value to the target URL. The old URL remains indexed, and SEO strength is preserved for the original page.
- **Use Case:** Temporary page changes, A/B testing, website maintenance, short-term promotions.

**Example:**
`GET /login` (unauthenticated user) → `302 Found` with `Location: /login-page`

### Comparison Table

| Status Code | Meaning | Permanency | SEO Transfer | Typical Use |
| :-- | :-- | :-- | :-- | :-- |
| 301 | Moved Permanently | Permanent | Passes SEO value | Domain moves, merges |
| 302 | Found/Temp Move | Temporary | Does not transfer | Maintenance, A/B testing |

### Key Considerations

- Use **301** for permanent redirects to preserve traffic and search rankings.
- Use **302** for temporary redirects when the original page will return soon and you want search engines to keep indexing the original URL.

**Summary:**
A 301 signals a permanent move and transfers SEO value, while a 302 is for temporary changes and does not pass SEO value to the new destination. Choosing the correct status code is crucial for both user experience and search engine optimization.


[1]: https://www.semrush.com/blog/301-vs-302-redirect/

[2]: https://world.siteground.com/kb/301-vs-302-redirect/

[3]: https://www.redirect-checker.org


