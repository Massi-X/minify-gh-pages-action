# Minify GitHub Pages
[![GitHub release](https://img.shields.io/github/release/Massi-X/minify-gh-pages-action.svg?color=orange)](https://github.com/marketplace/actions/minify-github-pages)
[![MIT license](https://img.shields.io/github/license/Massi-X/minify-gh-pages-action.svg?color=blue)](https://github.com/Massi-X/minify-gh-pages-action/blob/master/LICENSE)

Github Action to minify js, css, and html files for GitHub Pages, using the [node-minify](https://node-minify.2clics.net/introduction/) package.

### Why did I build this?
No action I found on the marketplace worked reliably (or at all) producing broken artifacts for GitHub pages. This pavkage aims to keep high compatibility and updated dependencies.

### Usage
Add `minify` step right `Build with Jekyll` in default [GitHub Pages build](https://docs.github.com/en/pages/getting-started-with-github-pages/using-custom-workflows-with-github-pages) action
```yaml
# ...

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Build with Jekyll
        uses: actions/jekyll-build-pages@v1
        with:
          source: ./
          destination: ./_site
      - name: Minify
        uses: Massi-X/minify-gh-pages-action@v2
# ...
```

### Options
The package currently support a few options:
|Option|Default|Required|Meaning|
| -------- | ------- | -------- | ------- |
|source|./_site/|false|Jekyll output directory. Should be the same as Jekyll 'destination'|
|compress|js,css,html|false|File types to compress, comma separated|
|js_options|'{"mangle": false}'|false|Options for js compressor from the ones available [here](https://github.com/mishoo/UglifyJS)|
|css_options|'{}'|false|Options for css compressor from the ones available [here](https://github.com/clean-css/clean-css)|
|html_options|'{"collapseInlineTagWhitespace": false}'|false|Options for html compressor from the ones available [here](https://github.com/kangax/html-minifier)|

### Donation
If you like to support me, you can donate. Any help is greatly appreciated. Thank you!

<a target="_blank" href="https://paypal.me/firemetris"><img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" alt="paypal"/></a>

**Bitcoin:** 1Pig6XJxXGBj1v3r6uLrFUSHwyX8GPopRs

**Monero:** 89qdmpDsMm9MUvpsG69hbRMcGWeG2D26BdATw1iXXZwi8DqSEstJGcWNkenrXtThCAAJTpjkUNtZuQvxK1N5xSyb18eXzPD
