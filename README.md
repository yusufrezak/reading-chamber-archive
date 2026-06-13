# The Reading Chamber Archive

An unofficial, browsable archive of books mentioned on
[The Reading Chamber](https://www.youtube.com/@TheReadingChamber-ID) YouTube channel.

The whole site is a single `index.html`. The data lives inline in a `<script>`
block near the bottom of that file, marked with a clear comment block.

## How to add a new episode

1. Open `index.html` in any editor.
2. Find the `window.READING_CHAMBER_DATA = [ … ]` block (search for `READING_CHAMBER_DATA`).
3. Paste a new object at the top of the array (newest first), matching the schema:

   ```js
   {
     episode: 44,
     title: "Episode title here",
     date: "2026-06-20",              // YYYY-MM-DD, or "" if unknown
     url: "https://www.youtube.com/watch?v=…",  // or ""
     guest: "Guest name",             // or ""
     books: [
       {
         title: "Book Title",
         author: "Author Name",
         year: 2024,
         link: "https://www.amazon.co.uk/s?k=…"   // any working link
       },
       // …
     ]
   },
   ```

4. Commit and push. Your site updates within a minute.

The page derives the episode dropdown, stats, and search index automatically
from `READING_CHAMBER_DATA` — no other code needs to change.

## Deploying to GitHub Pages

One-time setup:

1. Create a new public repo on GitHub (e.g. `reading-chamber-archive`).
2. Add `index.html` and `README.md` to the repo and push.
3. In the repo, go to **Settings → Pages**.
4. Under "Source," choose **Deploy from a branch**, branch `main`, folder `/ (root)`.
5. Wait ~1 minute. Your site is live at
   `https://<your-username>.github.io/reading-chamber-archive/`.

To use a custom domain, add a `CNAME` file with the domain name and configure
DNS per [GitHub's docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

## Working locally

Just open `index.html` in any browser. No build step, no server needed.

## What's included out of the box

Three episodes seeded as examples (Ep. 43, 39, 38) so you can see filtering and
search behave correctly. Replace, expand, or delete as you go.
