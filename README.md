# dima.vaschuk.com

Dima's capybara game. For now, an "under construction" page.

Static site in `public/`, no build step. Deployed to a separate Firebase Hosting site, `dima-vaschuk`, in the `vaschuk-com` Firebase project.
DNS: CNAME `dima` → `dima-vaschuk.web.app` at GoDaddy.

## Deploy

```sh
firebase deploy --only hosting --project vaschuk-com
```

Firebase CLI needs Node 20+. With an older Node: `npx -p node@22 -p firebase-tools firebase deploy --only hosting --project vaschuk-com`.

## Local preview

```sh
python3 -m http.server 8000 --directory public
```
