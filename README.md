# indrayam.com home

The landing page at [indrayam.com](https://indrayam.com/): a portrait and links to About Me, Resume, The Daily Diff, the blog, and Cribsheets. It is one of five static sites in the `indrayam.com` workspace; the parent [`AGENTS.md`](../AGENTS.md) describes how they fit together.

## Files

| File | Role |
| --- | --- |
| `index.html` | The whole page: the portrait with the menu to its right (stacked below it on phones). No visible name and no nav bar. |
| `assets/style.css` | White page, the blog's orange accent bar, Fraunces (Google Fonts): Light 300 for the menu, Regular 400 for the footer. Menu links are black; hovering or focusing one shows a thick orange underline. The photo's edges fade to white with a CSS mask (`--fade`), so the image file itself has no border baked in. |
| `assets/anand.webp`, `assets/anand.jpg` | Portrait, 640×800, metadata stripped. The JPEG is the fallback for browsers without WebP. |
| `favicon.ico`, `assets/apple-touch-icon.png` | A tight crop of the portrait (16, 32 and 48px in the `.ico`; 180px touch icon). Resume, The Daily Diff, and Cribsheets use the same icon; the blog keeps its own. |
| `robots.txt`, `sitemap.xml` | Crawler files for this host only. The blog has its own at `blog.indrayam.com`. |
| `vercel.json` | Redirects. See below. |

## Redirects

`indrayam.com` used to serve the blog, so old links still arrive here. `vercel.json` sends them to `blog.indrayam.com` with permanent (308) redirects:

1. The legacy `.php` post URLs, copied from `blog/vercel.json` and pointed straight at the final `.html` page so they take one hop.
2. A catch-all: every path except `/`, `/assets/`, `/robots.txt`, `/sitemap.xml`, and `/favicon.ico` goes to the same path on `blog.indrayam.com`.

Keep this site's own files under `assets/` (or add them to the catch-all's exclusions), or the catch-all will redirect them to the blog. When `blog/vercel.json` gains a legacy rule, copy it here too.

## Working on it

No build step. Preview locally with any static server (the workspace's `.claude/launch.json` has a `home` entry on port 8082). Redirects only run on Vercel, so test them on a deployment URL. Vercel serves the repository root.
