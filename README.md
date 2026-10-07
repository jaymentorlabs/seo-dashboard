# seo-dashboard
dashboard for website

## Data model (draft)

### Daily (one row per site per day)
Every Daily row also has: site, date.

- Question 3: "How many clicks does my website receive from Google?"
  Column: clicks (count of visits from Google results)
  Why Daily: Search Console reports it once per day.

- Question 1: "Does my website rank on Google, and where?"
  Columns: impressions (times the site appeared in results), avg_position (e.g. 7.3, so page 1 is roughly 1-10 and page 2 is 11-20)
  Why Daily: Search Console reports both once per day.

- Question 2: "Do visitors arrive from AI tools like ChatGPT?"
  Column: ai_visits (count of visits whose referrer is an AI tool)
  Why Daily: the analytics tool reports visits by referrer once per day. Search Console doesn't see this. Some AI visits arrive with no referrer, so this is a minimum count.

### Events (one row each time something happens)
Every Events row also has: site.

- Question 4: "How many appointments were booked through the website?"
  Columns: booked_at (when it happened), source_page (the page the booking came from), campaign (the UTM campaign, if any)
  Why Event: GHL sends one webhook per booking. The dashboard gets the count by counting rows, so there is no count column.
  Store no names or phone numbers.
