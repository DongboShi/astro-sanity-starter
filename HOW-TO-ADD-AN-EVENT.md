# Adding a new event (GitHub-only workflow)

Everything about events now lives in the repo. To add a talk:

1. **Photo** — save a landscape (3:2) JPEG, e.g. 1200×800, as
   `public/images/events/<slug>.jpg`   (slug = `lastname-year`, e.g. `smith-2026`)

2. **Data** — open `src/data/events.json` and add a new object at the **top**
   of the list (top = newest). Copy an existing entry and change the fields:

   ```json
   {
     "slug": "smith-2026",
     "year": "2026",
     "tag": "Robotics",
     "title": "Talk title",
     "time": "Friday Mar. 6th, 9:00am, Beijing/HK Time",
     "speaker": "Jane Smith",
     "speakerUrl": "https://university.edu/jane-smith",
     "affiliation": "University of Somewhere",
     "image": "/images/events/smith-2026.jpg",
     "abstract": "…",
     "bio": "…"
   }
   ```

3. **Commit and push to `main`.** Netlify rebuilds automatically (~20 s).

What updates automatically:
- Homepage "Recent Events" shows the first 6 entries in the file
- Each card's "Learn more" links to `/events#<slug>`
- The Events page lists everything, grouped by year

Tips
- `time`, `abstract` and `bio` may be left as `""` and filled in later.
- Keep the file valid JSON: every entry except the last needs a trailing comma.
  GitHub's web editor will show a red mark if something is off.
- The Michelle Rogan (rogan-2026) entry currently has `"time": "TBD"` and an
  empty abstract/bio — fill these in when you have them.
