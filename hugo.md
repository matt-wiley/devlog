# Hugo SSG

## Setup

1. Install Hugo
2. Create a new site
3. Add a theme
4. Create a new post
5. Start the server
6. Build the site
7. Deploy the site

## Install Hugo

```bash
brew install hugo
```

## Create a new site

```bash
hugo new site mysite
```

## Add a theme
<!-- TODO:  Complete this. Doesn't look right. -->

```bash
hugo new theme hugo001theme
```

## Create a new post

```bash
hugo new posts/my-first-post.md
```



## Start the server

```bash
hugo server -D
```

## Build the site

> [!NOTE]
> If deploying to GitHub Pages, be sure to set the update the `baseURL` in the `config.toml` file to the correct URL.
> 
> For example, if deploying to `https://username.github.io/repo-name/`, the `baseURL` should be set to `https://username.github.io/repo-name/`.

```bash
hugo
```

## Deploy the site
<!-- TODO: Setup github pages deployment-->

```bash
```

## Links

- [Hugo](https://gohugo.io/)
- [Hugo Themes](https://themes.gohugo.io/)
- [Hugo Docs](https://gohugo.io/documentation/)






