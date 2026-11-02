# Poeng Ta Kho

A small visitor guide to **Poeng Ta Kho**, the "Amazing Cliff" on the road up to Phnom Kulen National Park, Siem Reap Province, Cambodia.

It is a one-page website with facts, how to get there, practical tips, nearby sights, and a short FAQ. The text is in English with Khmer captions under the main lines.

This site was made as a live demo at New Hope Cambodia, to show how to build and publish a website by talking to an AI. It started from the "Vibe Code Cambodia" workshop template.

> **Please check the Khmer.** The Khmer text was written by an AI. Ask a Khmer speaker to read it before you share the site widely.

## See it on your computer

```
nvm use
npm install
npm run dev
```

Then open the address it prints, usually http://localhost:4321. The page updates as you change files.

## Change the site

Just ask Claude, for example: *"Add a packing list section"*, *"Make the colors look like sunset"*, *"Add a Telegram contact button"*.

Or edit the files yourself:

- `src/pages/index.astro` — the whole page. The facts, steps, tips, and FAQ are lists at the top of the file.
- `src/site.ts` — site name, tagline, and description.
- `src/styles/global.css` — colors and fonts, in the `@theme` block.
- `src/components/Header.astro` and `Footer.astro` — the top bar and the bottom of the page, including the list of sources.
- `public/` — the favicon, and any images you add. A file at `public/photo.jpg` is used as `/photo.jpg`.

Khmer text goes in `<span class="km" lang="km">…</span>` under the English line.

## About the information

The facts come from public travel pages and Wikipedia, linked in the site footer. Sources disagree on some details, such as exactly where the cliff is on the road and whether tuk-tuks can make the trip, so the site says "reported" for those. Prices (the $20 park ticket for foreign visitors) can change. Check with a driver or guesthouse before you go.

Poeng Ta Kho is a viewpoint, not a national park on its own. It sits on the road to Phnom Kulen National Park.

## Put it on the internet

The site is static, so Cloudflare just serves the files from `npm run build`.

1. Log in to [Cloudflare](https://dash.cloudflare.com).
2. Go to **Workers & Pages** → **Create** → **Import a repository**.
3. Connect GitHub and choose this repository.
4. Keep the default settings (build command `npm run build`, deploy command `npx wrangler deploy`) and click **Deploy**.

After that:

- **Push to `main`** → the live site updates.
- **Push a branch or open a pull request** → you get a private preview link.

> **If the build fails:** the `name` in `wrangler.jsonc` (`poeng-ta-kho-demo`) must match the Worker name in Cloudflare.

## Commands

| Command | What it does |
| --- | --- |
| `npm run dev` | Preview the site on your computer |
| `npm run build` | Build the finished site into `dist/` |
| `npm run preview` | Build, then preview it the way Cloudflare will serve it |
| `npm run deploy` | Build and publish to Cloudflare by hand (usually not needed) |

## Make your own copy

Want a site like this for your own idea? Create a new repository from the workshop template on GitHub (use the **Use this template** button), open it in the Claude app, and type `/make-it-mine`. `docs/mac-setup.md` explains how to set up a Mac for this.

---

Built with [Astro](https://astro.build), [Tailwind CSS](https://tailwindcss.com), and [Cloudflare Workers](https://workers.cloudflare.com).
