# keystatic-astro-cloudflare-demo

I recently went through the process of setting up Keystatic on my Astro site deployed to Cloudflare Workers. I figured I'd document the process in a short tutorial to help anyone else looking to setup a similar stack

## Steps

- Follow the official guide to integrate Keystatic into your Astro project: [Adding Keystatic to an Astro project - Docs \| Keystatic](https://keystatic.com/docs/installation-astro)
- Follow the GitHub Mode instructions: [GitHub mode - Docs \| Keystatic](https://keystatic.com/docs/github-mode)
- Add the Cloudflare Adapter: [@astrojs/cloudflare \| Docs](https://docs.astro.build/en/guides/integrations-guide/cloudflare/)
- Add your secrets to the Cloudflare Workers environments (this will prompt you to login to Cloudflare if you haven't already)

```
npx wrangler secret bulk .env
```

- Build and deploy

```bash
npm run build
npx wrangler deploy
```

- Update your GitHub App's callback URL to `https://<app-name>.<account-name>.workers.dev/api/keystatic/github/oauth/callback`

Done! Now you should be able to access Keystatic at `https://<app-name>.<account-name>.workers.dev/keystatic`
