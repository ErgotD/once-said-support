# once-said-site

Public-facing static site for the Once Said iPhone app. Hosts the landing page, support FAQ, Privacy Notice, and Terms of Use. Served via GitHub Pages.

## What is hosted

- `index.html` — landing page, brief description, links to the other pages.
- `support.html` — six-FAQ support page with a `mailto:` contact line.
- `privacy.html` — Privacy Notice. Must stay in sync with the app's bundled `assets/legal/privacy.md`.
- `terms.html` — Terms of Use. Must stay in sync with the app's bundled `assets/legal/terms.md`.
- `styles.css` — single stylesheet using the app's brand tokens. Light and dark mode via `prefers-color-scheme`.
- No JavaScript, no third-party requests, no fonts loaded from a CDN, no analytics.

## URLs

After GitHub Pages is enabled, the public URLs are:

- Landing: `https://<your-username>.github.io/once-said-site/`
- Support: `https://<your-username>.github.io/once-said-site/support.html`
- Privacy: `https://<your-username>.github.io/once-said-site/privacy.html`
- Terms: `https://<your-username>.github.io/once-said-site/terms.html`

The Support URL and the Privacy URL above are what the App Store Connect listing should reference. The Marketing URL field can use the landing URL or be left blank.

## Enabling GitHub Pages

1. Create this repo on GitHub. Public visibility is required for GitHub Pages on a free plan.
2. Upload these six files to the repo's root, either via the web UI or by cloning and pushing.
3. In the repo on GitHub: Settings → Pages.
4. Source: "Deploy from a branch".
5. Branch: `main`, Folder: `/ (root)`.
6. Save.
7. Wait one to two minutes for the first publish. GitHub will show the live URL once published.

## Updating the legal text

The Privacy Notice and Terms of Use are duplicated between the app repo's bundled markdown and this site's HTML. When either set is updated, the other must follow.

The `[insert date]` placeholders in `privacy.html` and `terms.html` should be stamped with the same date that lands in the bundled markdown when the legal text is finalised.

There is no automated sync between the app repo and this site repo. A future option is a small build step that converts the markdown to HTML on every push, but for v1 the manual cross-check is enough.

## Custom domain (optional, later)

GitHub Pages supports custom domains. Once a domain is registered (for example `oncesaid.app` or `oncesaid.co.uk`):

1. Settings → Pages → Custom domain.
2. Add the domain.
3. Follow GitHub's DNS instructions on the domain registrar (an `A` record set pointing at GitHub's IPs, plus a `CNAME` for the `www` subdomain).
4. Once the domain is live, the URLs migrate from `<username>.github.io/once-said-site/...` to `https://oncesaid.app/support` and so on.
5. Update the App Store Connect listing with the new URLs. App Store Connect lets you change URLs without resubmitting the binary.

## Brand and design

The visual style mirrors the in-app brand:

- Warm paper background, deep ink primary text, warm grey secondary text, soft warm grey hairlines, persimmon accent on link underlines.
- Serif body type (system fallbacks: Newsreader, Source Serif Pro, Charter, Iowan Old Style, Georgia).
- Sans-serif navigation (system fallbacks: SF Pro via `-apple-system`, then Inter, then platform defaults).
- Light and dark colour schemes via `prefers-color-scheme`, both honoured by mobile browsers.

No JavaScript is used. The site is intentionally static, simple, and small.
</content>
</invoke>