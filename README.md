# 0xsubrosa

Source of the 0xSubRosa website, served by GitHub Pages at https://wamimi.github.io/0xsubrosa/.

The site is a single self-contained file, `index.html`. It loads nothing from other hosts, sets no cookies and runs no analytics.

## Verifying the served page

`index.html.sha256` holds the SHA-256 of `index.html`. The page hashes itself in the browser and compares the result with this file. To check by hand:

```sh
curl -s https://wamimi.github.io/0xsubrosa/ | sha256sum
curl -s https://wamimi.github.io/0xsubrosa/index.html.sha256
```

After every deployment, the `verify-live` workflow fetches the live page and fails if its hash differs from the published one.

## Updating the page

Any change to `index.html` needs a new hash in the same commit:

```sh
sha256sum index.html > index.html.sha256      # Linux
shasum -a 256 index.html > index.html.sha256  # macOS
```
