# mkeutgen.github.io

Personal site built with Hugo and the [Archie](https://themes.gohugo.io/themes/archie/) theme.

## Local development
- Install Hugo Extended v0.128+ and Go (for Hugo modules).
- Clone the repo and run `hugo server -D`.
- Open the printed localhost URL to preview changes.

## Deployment
- GitHub Actions workflow `.github/workflows/deploy.yml` builds the site and deploys to GitHub Pages on pushes to `main`.
- Site settings (title, menus, socials) live in `config.toml`.

## Licensing
- Repo keeps the original `LICENSE`. Archie theme assets are under their upstream license (`themes/archie/LICENSE`).
