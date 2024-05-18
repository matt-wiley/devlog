# Hugo SSG

## Setup

1. Install Hugo
2. Create a new site
3. Add a theme
4. Create a new post
5. Start the server
6. Build the site
7. Deploy the site

### Install Hugo

```bash
brew install hugo
```

### Create a new site

```bash
hugo new site mysite
```

### Add a theme

> [!NOTE]
> Here we're creating a new basic theme. You can also use an existing theme by cloning it into the `themes` directory.  

```bash
hugo new theme hugo001theme
```

### Create a new post

```bash
hugo new posts/my-first-post.md
```



### Start the server

```bash
hugo server # Start the serverr
hugo server -D # Start the server with draft contentt
```

### Build the site

> [!NOTE]
> If deploying to GitHub Pages, be sure to set the update the `baseURL` in the `config.toml` file to the correct URL.
> 
> For example, if deploying to `https://username.github.io/repo-name/`, the `baseURL` should be set to `https://username.github.io/repo-name/`.

```bash
hugo # Build non-draft content to public directory
hugo -D # Build draft content to public directory
```

### Deploy the site

#### GitHub Pages

The following is a simple GitHub Actions workflow for deploying a Hugo site to GitHub Pages.

```yaml
# Simple workflow for deploying static content to GitHub Pages
name: Deploy to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ["main"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  # Single deploy job since we're just deploying
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Pages
        uses: actions/configure-pages@v5
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          # Upload the public directory to GitHub Pages
          path: 'public'
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

## Links

- [Hugo](https://gohugo.io/)
- [Hugo Themes](https://themes.gohugo.io/)
- [Hugo Docs](https://gohugo.io/documentation/)






