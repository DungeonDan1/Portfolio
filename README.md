# Portfolio

Single-page portfolio site for Dan Rowe. Content manager, writer, and social media strategist.

Live: https://portfolio-three-sooty-84.vercel.app

## Stack

One `index.html` file. All styles are inline. Tailwind loads from CDN. There is no build step.

## Running it locally

```bash
npm install
node serve.mjs
```

Serves the project root at http://localhost:3000. Do not open `index.html` as a `file://` URL, because the video and PDF embeds will not load.

To screenshot a page:

```bash
node screenshot.mjs http://localhost:3000
```

Output lands in `temporary screenshots/`, numbered so nothing gets overwritten. Add a label as a second argument to suffix the filename.

## Layout

```
index.html          the whole site
assets/<client>/    per-client media
scratch/            one-off screenshot scripts, kept for reference
temporary screenshots/   screenshot output
```

Client folders: `bridgwater`, `purplex`, `starbubs`, `taunton`, `warwick`, `growthtechnology`.

## Assets

Two rules matter here.

**GitHub rejects any file over 100MB.** Video and PDF exports have to sit under that or the push fails. `Behind the Nest.mp4` and the full `Art of Marketing.pdf` both crossed it and are excluded, with a YouTube embed and a compressed `-web.pdf` used in their place.

**Source masters stay out of git.** The `.mov` files are the originals and run to roughly 3.7GB. They live on disk and are ignored. The `.mp4` exports are what the site serves. Same idea for the source PNGs, where the site uses smaller `-web.jpg` versions.

If you add a file to `assets/` and it does not appear on the live site, check `.gitignore` first. That is what caused the missing webinar video poster.

## Deploying

Vercel watches `main` and deploys on push. There is no config file and no manual step.
