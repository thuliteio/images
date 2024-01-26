# Hyas images

Official images integration for Hyas.

## Status

[![npm (scoped)](https://img.shields.io/npm/v/@hyas/images?style=flat-square)](https://www.npmjs.com/package/@hyas/images)

## Installation

```bash
npm i @hyas/images
```

## Setup

Add mounts to `./config/_default/module.toml`:

```toml
[[mounts]]
  source = "node_modules/@hyas/images/assets"
  target = "assets"

[[mounts]]
  source = "assets"
  target = "assets"

[[mounts]]
  source = "node_modules/@hyas/images/layouts"
  target = "layouts"

[[mounts]]
  source = "layouts"
  target = "layouts"
```

Set parameters in `./config/_default/params.toml`:

```bash
# Images (@hyas/images)
[hyas_images]
  [hyas_images.defaults]
    decoding = "async" # sync, async, or auto (default)
    fetchpriority = "auto" # high, low, or auto (default) 
    loading = "lazy" # eager or lazy (default)
    widths = [480, 576, 768, 1025, 1200, 1440] # [640, 768, 1024, 1366, 1600, 1920] for example
    sizes = "75vw" # 100vw (default), 75vw, or auto for example
    process = "" # "fill 1680x720" for example
```

Add CSS class selectors to `./assets/scss/components/_images.scss`:

```scss
img {
  height: auto;
  max-width: 100%;
}

img, picture {
  font-size: 0;
}

figcaption {
  font-size: 1rem;
  margin-top: 0.5rem;
  font-style: italic;
}
```

## How to use

See the Hyas documentation:

- [Images](https://images.gethyas.com/)


## Credits

This npm package is based on:

- [Image render hook](https://www.veriphor.com/articles/link-and-image-render-hooks/#image-render-hook)
- [Images with overlays](https://www.veriphor.com/articles/images-with-overlays/)
