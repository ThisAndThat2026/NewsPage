# How to add a new day

Instructions for the daily agent. Use today's date in Pacific Time as `YYYY-MM-DD`.

## Step 1: Copy the template
Copy `briefing/template.html` to `briefing/YYYY-MM-DD/index.html`.
If that folder already exists, stop: never overwrite a past day.

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

## Step 3: Update index.html
1. Replace everything between `<!-- LATEST-START -->` and `<!-- LATEST-END -->` with:
   ```html
   <a class="latest" href="briefing/YYYY-MM-DD/"><span class="label">Latest briefing</span><span class="title">[DATE]</span></a>
   ```
2. Insert one new line directly after `<!-- DAY-LIST-START -->`, above the existing items:
   ```html
   <li><a href="briefing/YYYY-MM-DD/">[DATE]</a> - [ONE-LINE SUMMARY]</li>
   ```
Nothing else on the index changes.

## Step 4: Do not
- Edit or delete any past day folder.
- Change the CSS or page structure.
- Add external dependencies: no CSS/JS files, fonts, images or scripts.
- Use absolute links to this site. Internal links stay relative.
