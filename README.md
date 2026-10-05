# Last Nerve website

Static landing page for Last Nerve, a service of Gladly Rara. Hosted on GitHub Pages.

## Go live (about 20 minutes)

1. **Buy the domain.** First choice: `lastnerve.co`. Backups: `lastnerve.app`, `getlastnerve.com`. Cloudflare Registrar and Porkbun sell at cost.
2. **Make the repo.** In GitHub (gladlyrara account): New repository, name it `lastnerve`, set it to Public, then click "uploading an existing file" and drag in `index.html`, `CNAME`, and this README. Commit.
3. **Turn on Pages.** Repo Settings, then Pages. Source: Deploy from a branch, branch `main`, folder `/ (root)`. Save.
4. **Point the domain.** At your registrar, add DNS records:
   - Four `A` records for `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - One `CNAME` record for `www` pointing to `gladlyrara.github.io`
5. **Lock it down.** Back in Settings, then Pages: enter the custom domain, wait for the DNS check to pass, then tick "Enforce HTTPS." DNS can take up to an hour.

If you buy a different domain, change the one line in `CNAME` to match.

## Add the deposit and waitlist links

Near the bottom of `index.html`, find:

```js
const LINKS = {
  deposit: "",
  waitlist: ""
};
```

Paste the Stripe Payment Link between the first pair of quotes and the waitlist form link between the second. Until then, those buttons say "opens soon."

**Stripe:** create a $15 Payment Link and set its confirmation page to redirect to your domain. The statement descriptor (`NERVAL`) is an account setting: Settings, then Public details.
