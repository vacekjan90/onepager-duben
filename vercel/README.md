# Allwyn · Sport's Marketing Onepager — Duben 2026

Static HTML one-pager ready to deploy on Vercel.

## Folder contents
- `index.html` — the one-pager (single self-contained file, ~118 KB, all images base64-embedded)
- `vercel.json` — sets `noindex` (private link only), short HTML cache TTL, basic security headers
- `robots.txt` — also tells crawlers not to index

## Deploy in under 5 minutes

### Option A — drag & drop (easiest, no install)
1. Open <https://vercel.com> and sign in (free Hobby plan is enough).
2. Click **Add New… → Project**, then on the new screen pick **Deploy** under "Other".
   - If you don't see a drag area, go directly to <https://vercel.com/new>.
3. Zip this `vercel/` folder and drop it onto the upload area, **or** click "Browse" and select it.
4. Give the project a name (e.g. `allwyn-onepager-04-2026`) and click **Deploy**.
5. ~30 seconds later you'll get a URL like `https://allwyn-onepager-04-2026.vercel.app`. Done.

### Option B — Vercel CLI (best if you'll redeploy each month)
```bash
# one-time install
npm i -g vercel

# from inside this vercel/ folder
cd /Users/janvacek/Documents/Claude/Scheduled/sports-marketing-report/vercel
vercel login          # follow the email link
vercel                # first-time deploy → creates the project (preview URL)
vercel --prod         # promote to production URL
```
Subsequent monthly updates: replace `index.html`, run `vercel --prod` again.

### Option C — GitHub-connected (best if multiple people will edit)
1. Create a new GitHub repo (private), upload the contents of this `vercel/` folder.
2. In Vercel: **Add New… → Project → Import** the repo.
3. Vercel auto-deploys on every push to `main`.

## Custom domain (optional)
After the first deploy:
- Project → **Settings → Domains**
- Add e.g. `onepager.pragosport.cz` and follow the CNAME instructions Vercel shows.

## Privacy note
This deployment is configured with `X-Robots-Tag: noindex, nofollow` and `robots.txt: Disallow: /`, so the page won't appear in Google. The URL itself is still public — anyone with the link can open it. If you need real auth, turn on Vercel's **Password Protection** under Project → Settings → Deployment Protection.

## Updating the file each month
Just replace `index.html` with the new month's build (re-run `python3 build_html.py` to produce it, then copy the file here) and redeploy with whichever option you used above.
