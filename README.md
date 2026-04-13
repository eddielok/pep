# PEP — IT Consulting & Services Website

Rebuilt from Wix to a modern static site using [Astro](https://astro.build), hosted on [Cloudflare Pages](https://pages.cloudflare.com).

## Pages

| Route | Description |
|---|---|
| `/` | Homepage — hero, services overview, contact form |
| `/about` | About Us — company history, values |
| `/d-biz` | D-Biz Programme — HK Government Distance Business Programme |
| `/services` | Services index |
| `/services/system-management` | System Management |
| `/services/network-solutions` | Network Solutions |
| `/services/web-solutions` | Web Solutions |
| `/services/technical-support` | Technical Support |
| `/services/anti-money-laundering` | Anti-Money Laundering (AML) |

## Project Structure

```
pep/
├── public/
│   └── images/          # All image assets
├── src/
│   ├── components/
│   │   ├── Header.astro         # Sticky nav with mobile hamburger + dropdown
│   │   ├── Footer.astro         # 4-column footer
│   │   ├── ContactForm.astro    # Web3Forms contact form
│   │   └── ServiceLayout.astro  # Shared layout for service detail pages
│   ├── layouts/
│   │   └── Layout.astro         # Base HTML layout with global styles
│   └── pages/
│       ├── index.astro
│       ├── about.astro
│       ├── d-biz.astro
│       └── services/
│           ├── index.astro
│           ├── system-management.astro
│           ├── network-solutions.astro
│           ├── web-solutions.astro
│           ├── technical-support.astro
│           └── anti-money-laundering.astro
├── astro.config.mjs
└── package.json
```

## Local Development

```bash
npm install
npm run dev       # http://localhost:4321
```

## Build

```bash
npm run build     # outputs to dist/
npm run preview   # preview the built site locally
```

## Deploy to Cloudflare Pages

1. Push this repo to GitHub
2. In [Cloudflare Pages](https://pages.cloudflare.com), create a new project and connect the repo
3. Set the build settings:
   - **Build command:** `npm run build`
   - **Build output directory:** `dist`
4. Deploy

## Contact Form

The contact form uses [Web3Forms](https://web3forms.com) to deliver submissions to `info@pep.com.hk`.

The access key is configured in `src/components/ContactForm.astro`. To change the destination email, generate a new key at web3forms.com.

## Tech Stack

- [Astro 4](https://astro.build) — static site generator
- Vanilla CSS with CSS custom properties — no framework
- [Web3Forms](https://web3forms.com) — contact form delivery
- [Cloudflare Pages](https://pages.cloudflare.com) — hosting
