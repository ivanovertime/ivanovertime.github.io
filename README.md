<p align="center">
  <img width="100" height="100" src="./static/favicon.ico" alt="Ivan Over Time logo">
</p>

<h1 align="center">Ivan Over Time</h1>

<p align="center">
  <a href="https://app.netlify.com/sites/ivanovertime/deploys">
    <img src="https://api.netlify.com/api/v1/badges/b9595701-510e-411b-969e-6a0d348a2a5f/deploy-status" alt="Netlify Status">
  </a>
  <a href="/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="License">
  </a>
</p>

Personal site and digital garden by Iván Álvarez. The site is a multilingual Hugo build that collects long-form writing, quick notes, and curated resources around data, software, and language learning.

## About

- Static site generated with [Hugo](https://gohugo.io/) using a vendored copy of the [Bilberry theme](https://github.com/Lednerb/bilberry-hugo-theme).
- Content is published in English, Spanish, and Japanese via Hugo's multilingual features.
- Deployed automatically to Netlify at https://alvarezivan.net.ve/ after every push to `trunk`.

## Features

- Multilingual layout with language-specific titles and subtitles.
- Custom typography and styling via `static/custom.css` and Google Fonts.
- Post types for articles, project pages, galleries, and status updates.
- Built-in RSS, JSON index, and sitemap feeds produced during the Hugo build.

## Local Development

### Prerequisites

- Hugo **extended** `>= 0.126.0` (matches the Netlify build version).
- Git (for cloning and pulling the Bilberry theme submodule).
- Optional: `dart-sass` if you need to rebuild theme styles locally, mirroring the Netlify pipeline.

### Setup

```bash
git clone https://github.com/ivanovertime/ivanovertime.github.io.git
cd ivanovertime.github.io
git submodule update --init --recursive
```

Start the development server with drafts and future-dated entries enabled:

```bash
hugo server -D
```

Open `http://localhost:1313` in your browser. Hugo hot-reloads content, so saving Markdown files under `content/` will refresh the page immediately.

## Content Workflow

- Create a new article: `hugo new article/my-post/index.md`
- Create a new page: `hugo new page/uses/index.md`
- Drafts live alongside their translations; add `draft: true` to keep them local.
- Assets placed next to the Markdown file are bundled automatically thanks to Hugo Page Bundles.

Keep translations in language-specific sections (for example `content/article/my-post/index.md`, `content/article/my-post/index.es.md`). Hugo aligns them based on filename suffixes.

### Responsive images

- Place source images inside the same page bundle as the Markdown (`content/article/my-post/image.png`).
- Reference them with a shortcode or render hook that leverages Hugo image processing to create resized variants (`.Fit`, `.Resize`, or `.Fill`) and emits a `srcset`.
- `static/custom.css` already forces inline and featured images to stay fluid (`width:auto; max-width:100%; height:auto;`), so they shrink cleanly on mobile while the generated `srcset` keeps them sharp on high DPI screens.

## Project Structure

```
content/        # Markdown sources for posts, pages, galleries, and status updates
layouts/        # Hugo layout overrides layered on top of the Bilberry theme
static/         # Static assets copied verbatim (CSS, manifest, images)
themes/         # Bilberry theme as a Git submodule
netlify.toml    # Build settings and cache headers for Netlify
hugo.toml       # Global Hugo configuration (languages, params, theming)
```

## Deployment

- Netlify runs `hugo --gc --minify` using Hugo extended `0.126.0` on Ubuntu 24.04.
- The build script installs Dart Sass so theme SCSS customizations compile consistently.
- The generated site is published from the `public/` directory; push to `trunk` to trigger a deploy.

To test a production build locally run:

```bash
hugo --gc --minify
```

The output in `public/` can be served with any static file server.

## Contributing

Issues and pull requests are welcome. Please run `hugo server -D` locally to verify that content or layout changes render as expected, and share screenshots for visual updates.

## Thanks

- Grateful for the [Bilberry Hugo theme](https://github.com/Lednerb/bilberry-hugo-theme) and its maintainers, whose work powers the site's look and feel.

## License

Distributed under the [MIT License](LICENSE).
