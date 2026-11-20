# HinataTV

A fast, black-and-white anime streaming DUB and SUB site built with **Next.js 15 (App Router)**, **React 19**, **Tailwind CSS v4** and the **AniList GraphQL API**.

## Features

- Full-screen hero with hand-picked slides (`src/lib/featured.ts`, images in `public/hero/`) + trending fill
- Latest aired episodes, Top 10 (Now / Season / All-time), "Airing next" countdowns
- Browse with filter pills, quick genres, streaming skeletons and numbered pagination
- Anime pages: HD backdrop, seasons switcher, episodes, cast, community stats, related & recommendations
- Watch page shell with episode list, ranges and history (player source not connected yet)
- Ctrl/⌘ K search palette, watchlist + continue-watching (local, no account needed)
- Transparent floating navbar, scroll-driven 3D effects (respects reduced motion)

## Getting started


Open https://hinatatv.site

## Scaling notes

- Pages use ISR (home 10 min, schedule 30 min, titles 1 h); AniList calls are cached per query + variables, so traffic spikes are served from cache.
- Put a CDN in front (e.g. Vercel / Cloudflare) so cached HTML and static assets never hit the origin.
- Search API responses send `s-maxage` headers for CDN caching.

Anime metadata provided by [AniList](https://anilist.co).
