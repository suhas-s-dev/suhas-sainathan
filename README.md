# Suhas Sainathan — personal website

A fast, single-page personal website built with Hugo. Its structure follows the compact, value-first approach of [srigovindnayak.com](https://srigovindnayak.com), adapted for Suhas's work in security architecture.

## Local development

Prerequisite: Hugo Extended 0.146 or newer.

```bash
hugo server --buildDrafts
```

Open `http://localhost:1313`.

## Edit profile content

Most copy and links live in [`data/profile.yaml`](data/profile.yaml). Layout is in [`layouts/index.html`](layouts/index.html), and styling is in [`assets/css/main.css`](assets/css/main.css).

## Production build

```bash
hugo --minify
```

The deployable site is generated in `public/`.

## Cloudflare Pages

```bash
hugo --minify
npx wrangler pages deploy public --project-name suhas-sainathan --branch main
```

The repository includes a GitHub Actions build check so pull requests and pushes to `main` verify the Hugo build.

## Content provenance

The initial draft uses public professional information from Suhas's LinkedIn and GitHub profiles. Suhas should review the wording, links, portrait, and selected credentials before adopting the site as his canonical personal website.
