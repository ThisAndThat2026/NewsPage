# How to add a new day

Instructions for the daily agent. Use today's date in Pacific Time as `YYYY-MM-DD`.

IMPORTANT: The homepage (`index.html`) IS the full latest briefing. Opening it must show the full news immediately, with no click to a day page. Day folders are the archive only.

## Step 1: Copy the template
Copy `briefing/template.html` to `briefing/YYYY-MM-DD/index.html`.
If that folder already exists for a previous calendar day, stop: never overwrite a past day. If it already exists for today (a same-day refresh), replace today's day page with the fresh version.

## Step 2: Fill in all placeholders
Replace every placeholder in the new file. Keep the same sections, order and layout.

| Placeholder | What goes there |
|---|---|
| `[DATE]` | Full date, e.g. `Saturday, October 31, 2026` (appears in title, header, footer) |
| `[ONE-LINE SUMMARY]` | One sentence on the day (header and meta description) |
| `[HEADLINE]` | Story headline |
| `[SUMMARY]` | 1-2 sentences (2-3 for the lead story) |
| `[SOURCE]` | Outlet name, e.g. `The Seattle Times` |
| `[SOURCE URL]` | Full `https://` link to the article |
| `[TIME]` | Publish time, e.g. `Oct 31, 6:10 AM` |

Rules:
- Total page length: 450-550 words.
- Only real stories from the last 24 hours, each with a working source link.
- If a section has nothing significant, keep the section and use one item with headline `No major updates` and remove its link (`<div class="item">` instead of `<a>`).
- You may remove extra item rows inside a section, but never remove or reorder sections.
- When done, search the file: no `[` placeholder must remain.

## Step 3: Update index.html (the homepage = full latest briefing)
1. Copy today's day page to `index.html`.
2. Remove its back link (`&larr; All briefings`), which would point to itself on the homepage.
3. Replace its "Previous briefings" section with the correct past-days list, newest first, each as a link to `briefing/YYYY-MM-DD/` with that day's date and one-line summary. To build it: read the current homepage before overwriting it. If its date is a previous calendar day, add that day to the top of the Previous list, followed by its existing Previous list items. If its date is already today, keep its Previous list unchanged and do NOT add today to it. If there are no past days yet, keep the text "Previous briefings will appear here."
Nothing else in the briefing content changes.

## Step 4: Do not
- Edit or delete any past day folder.
- Change the CSS or page structure.
- Add external dependencies: no CSS/JS files, fonts, images or scripts.
- Use absolute links to this site. Internal links stay relative.
