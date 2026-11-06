# dima.vaschuk.com

Dima's capybara game: **Capybara Rush**, an endless runner in a single `public/index.html` (canvas + WebAudio, no dependencies). Collect oranges that stack on the capybara's head as a shield; jump logs/rocks/croc ponds, duck bees, grab power-ups.

Also `public/taekwondo/`: a sub-page with Dima's taekwondo testing video (H.264 MP4 + poster), linked from tabs at the top of both pages.

Static site in `public/`, no build step. Deployed to a separate Firebase Hosting site, `dima-vaschuk`, in the `vaschuk-com` Firebase project.
DNS: CNAME `dima` → `dima-vaschuk.web.app` at GoDaddy.

## Deploy

```sh
firebase deploy --only hosting --project vaschuk-com
```

Firebase CLI is installed globally (`npm i -g firebase-tools`) and needs Node 20+ first on PATH. Without it: `npx -p node@22 -p firebase-tools firebase deploy --only hosting --project vaschuk-com`.

## Local preview

```sh
python3 -m http.server 8000 --directory public
```

## Auto-deploy

Every push to `main` deploys via [.github/workflows/firebase-hosting.yml](.github/workflows/firebase-hosting.yml) (keyless, Workload Identity Federation). One-time GCP setup: `bash scripts/setup-github-deploy.sh`.
