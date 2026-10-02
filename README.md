# gimme-shares

The public page for a shared gimme wishlist, published with GitHub Pages at
https://list.gimme-wish.com.

A link looks like `https://list.gimme-wish.com/?l=<token>`. The page is static: it reads the
token from the URL and asks the gimme backend (`shared-list` Edge Function) for that list each
time it is opened, so it always shows the current wishlist. `Report this list` posts to
`report-list`. There are no secrets in this repo and no build step.

- `index.html`: the whole page (markup, styles, script).
- `404.html`: sends `/<token>` links to `/?l=<token>`.
- `CNAME`: the custom domain. DNS needs a `CNAME` record `list` → `dayo-adebanjo.github.io`.

To change the page, edit `index.html` and push to `main`; GitHub republishes in about a minute.
The functions live in the app repo under `supabase/functions/` (SPEC §16, §17).
