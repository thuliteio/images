# Hyas images

Image render hook, shortcode + partial for Hyas sites.

## Status

[![npm (scoped)](https://img.shields.io/npm/v/@hyas/images?style=flat-square)](https://www.npmjs.com/package/@hyas/images) [![GitHub Workflow Status](https://img.shields.io/github/workflow/status/h-enk/hyas-images/CodeQL?style=flat-square)]((https://github.com/h-enk/hyas-images/actions/workflows/codeql.yml))

## Installation

```bash
npm i @hyas/images -D
```

## Setup

Add to `./config/_default/module.toml`:

```toml
[[mounts]]
  source = "node_modules/@hyas/images/layouts"
  target = "layouts"

[[mounts]]
  source = "layouts"
  target = "layouts"
```

Add to `./config/_default/params.toml`:

```bash
# lazyimg
[lazyimg]
  resizer = "auto"
  renderer = "lqip-webp"

  # Resizer options:
  lqipSize = "120x Gaussian"
  maxSize = "1920x"
  responsiveSizes = [ "320x", "640x", "768x", "1024x", "1366x", "1600x", "1920x" ]
  resizeOptions = "Lanczos q95"

  # Renderer options:
  class = "img-fluid"
  # alt = ""
  noscript = true

  errorHandler = "warning"
```

## Usage

See the Hyas docs: [Images](https://gethyas.com/docs/recipes/images/)


## Credits

Based on [lazyimg](https://github.com/hugo-mods/lazyimg)
