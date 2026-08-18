# umuzi-gig-list

The list of gigs that appears in the **gig name** drop-down on the Umuzi
gig-verification claim form.

The form fetches `gigs.json` from this repo at the moment a young person opens it.
Editing this file changes the drop-down — the form itself does not need to be
republished, and nothing needs to be re-signed on chain.

## How to add a gig

1. Open [`gigs.json`](gigs.json) and click the pencil icon.
2. Add an entry to the list:

   ```json
   {
     "value": "short-id-with-dashes",
     "text": "The name a young person will see"
   }
   ```

3. Commit the change.
4. Anyone who **opens the form after that point** sees the new gig. A form that is
   already open on screen keeps the old list until the page is refreshed.

### Rules

- `value` is what gets stored on the claim. Keep it short, lowercase, dashes instead
  of spaces, and **never change or reuse one once claims exist against it** — that
  would silently re-label past claims.
- `text` is what the young person reads. Write it the way they would say it, not the
  way it appears in internal paperwork.
- The file must stay a valid JSON array, and this repo must stay **public** — the
  form fetches it straight from the browser with no credentials.

## Fallback

The drop-down also offers *"My gig is not on this list"*, which opens a free-text box.
If claims start coming through on that option, it means a gig is missing here.

## Status

The four entries currently in `gigs.json` are a **starter list**, drawn from the gig
types agreed on the Umuzi design call of 18 August 2026. They are placeholders — they
should be replaced with the real gig names before youth start claiming.
