# Working in this repository

## Before editing

- Check the current branch and working-tree status. Preserve existing user changes.
- Read `README.md` and the files you are changing. Keep edits limited to the requested work.
- Follow the parent [`../AGENTS.md`](../AGENTS.md) for work that crosses into the other sites.

## Page content and behavior

- Keep the page minimal: the portrait and, to its right, the menu: About Me, Resume, then a "My Interests" heading over four smaller links (Daily Diff, Cribsheets, Sightings, Writings, which is the blog). No visible name and no nav bar, by the owner's design.
- White background, Fraunces Light (300), black menu links with a thick orange underline on hover or focus. Keep the orange accent aligned with `blog/style.css`.
- The portrait is a fixed crop approved by the owner. Don't recrop, replace, or re-encode it unless asked, and strip metadata from any new image.
- `vercel.json` keeps every old `indrayam.com` blog URL working. Don't remove or narrow its redirects without checking what they forward. Put new files under `assets/` so the catch-all doesn't redirect them.
- No dependencies, frameworks, or build step.

## Verification

- For layout or styling changes, check the page in a browser at desktop and phone widths.
- For redirect changes, test on a Vercel deployment URL: `/`, a post URL, a legacy `.php` URL, and `/assets/` files. A local static server doesn't apply `vercel.json`.
- Report what you checked; don't claim redirect or deployment checks you didn't run.
