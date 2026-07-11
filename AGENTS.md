## Development

When starting the dev server, use background mode:

```
astro dev --background
```

Manage the background server with `astro dev stop`, `astro dev status`, and `astro dev logs`.

## Documentation

Full documentation: https://docs.astro.build

Consult these guides before working on related tasks:

- [Adding pages, dynamic routes, or middleware](https://docs.astro.build/en/guides/routing/)
- [Working with Astro components](https://docs.astro.build/en/basics/astro-components/)
- [Using React, Vue, Svelte, or other framework components](https://docs.astro.build/en/guides/framework-components/)
- [Adding or managing content](https://docs.astro.build/en/guides/content-collections/)
- [Adding styles or using Tailwind](https://docs.astro.build/en/guides/styling/)
- [Supporting multiple languages](https://docs.astro.build/en/guides/internationalization/)


## Site Logs And Security

Keep operational site logs inside `docs/logs/`, not in `Second Cerveau/`, unless the user explicitly asks to document a business, strategy, identity, or personal organization decision.

Use this structure:

- `docs/logs/global.md` for site-wide conventions, public identity rules, and non-sensitive infrastructure choices.
- `docs/logs/pages/` for page-specific decisions.
- `docs/logs/categories/` for cross-page topics such as video, SEO, design, or content.

Never store secrets or sensitive infrastructure details in `docs/logs/` or any committed documentation file.

Allowed examples:

- Site uses Astro and Cloudflare Pages.
- Videos are hosted on Bunny Stream.
- Large videos should not be stored directly in the repo.
- Public first name spelling is `Vero`.

Forbidden examples:

- Cloudflare login email.
- Cloudflare API token, Account ID, Zone ID, or detailed Access/Tunnel configuration.
- Bunny API keys or library API keys.
- Private dashboard URLs, upload tokens, billing details, or screenshots exposing admin data.
- Any `.env` value, secret, credential, token, or private infrastructure detail.

Document the what and why of a decision, not private admin access details.
