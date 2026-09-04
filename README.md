# Jukebox Site

The public page for [My Jukebox](https://github.com/strange-labs-uk/jukebox) at
**jukebox.strangelabs.io**. Currently a coming-soon page; the app is still in development.

Plain HTML and CSS, no build step. Palette and typography are lifted from the app's own
theme (`client/src/styles/theme.css` in the jukebox repo) so the two read as one product.
If the app's colours change, these are a copy and will not follow.

## Structure

```
index.html       # the whole page
css/main.css     # styles
CNAME            # custom domain for GitHub Pages
```

## Development

Open `index.html` in a browser. That is the whole workflow.

For the absolute paths in `index.html` to resolve, serve it rather than opening the file
directly:

```sh
python3 -m http.server 8000
```

## Deployment

GitHub Pages, deploying from the default branch. Pushing to `main` publishes.

## When the app takes this domain

`jukebox.strangelabs.io` is the intended home of the production app, not just this page.
The handover has an order that matters:

1. Remove the custom domain from this repo's **Settings → Pages**
2. Repoint the `jukebox` DNS record from `strange-labs-uk.github.io` to the Railway target
3. Add the domain in Railway and wait for the certificate to issue

Doing 2 or 3 before 1 leaves GitHub holding the domain while Railway tries to validate it,
which stalls certificate issuance.
