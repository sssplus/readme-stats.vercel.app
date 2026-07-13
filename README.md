# readme-stats

Your own self-hosted instance of [github-readme-stats](https://github.com/anuraghazra/github-readme-stats) — generates live SVG cards (stats, top languages, pinned repos) to embed in a GitHub profile README. Running your own instance avoids the public rate limit and lets you show private-repo stats.

## Deploy

[![Deploy to Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/sssplus/readme-stats.vercel.app)

1. Click the button above (or **Add New → Project → Import** this repo from your [Vercel dashboard](https://vercel.com/pbipl)).
2. Accept the defaults and deploy once — it'll work, but every request will fail until step 3 (no token yet).
3. Create a GitHub PAT: [Settings → Developer settings → Personal access tokens → Tokens (classic)](https://github.com/settings/tokens/new) → **Generate new token (classic)** → no scopes needed for public data (add `repo` + `read:user` if you want private stats) → copy it.
4. In the Vercel project → **Settings → Environment Variables**, add `PAT_1` = `<the token>`.
5. Go to **Deployments** → "..." on the latest one → **Redeploy**.
6. Your API is now live at `https://<your-project>.vercel.app/api`.

## Use it on your GitHub profile

Create/edit the README in your [profile repo](https://github.com/sssplus/sssplus) (a repo named exactly `sssplus`) and drop in cards pointed at your own deployment — swap `<your-domain>` for the URL from step 6:

```md
![Soumedhik's GitHub stats](https://<your-domain>/api?username=sssplus&show_icons=true&theme=radical)

![Top Langs](https://<your-domain>/api/top-langs?username=sssplus&layout=compact&theme=radical)

[![Repo](https://<your-domain>/api/pin/?username=sssplus&repo=readme-stats.vercel.app&theme=radical)](https://github.com/sssplus/readme-stats.vercel.app)
```

Full option reference (themes, layouts, hide flags, wakatime cards, etc.) is documented in the upstream project: https://github.com/anuraghazra/github-readme-stats#table-of-contents

## Local development

```sh
npm install
cp .env.example .env   # fill in PAT_1
npm start               # serves the api/ routes at http://localhost:9000/api
```

## Credits

Fork of [anuraghazra/github-readme-stats](https://github.com/anuraghazra/github-readme-stats), MIT licensed.
