# Hyas images

Official images integration for Hyas.

## Status

[![npm (scoped)](https://img.shields.io/npm/v/@hyas/images?style=flat-square)](https://www.npmjs.com/package/@hyas/images)

## Installation

```bash
npm i -D @hyas/images
```

## Setup

Add mounts to `./config/_default/module.toml`:

```toml
[[mounts]]
  source = "node_modules/@hyas/images/assets"
  target = "assets"
  excludeFiles = "/scss/**.scss"

[[mounts]]
  source = "node_modules/@hyas/images/layouts"
  target = "layouts"

[[mounts]]
  source = "assets"
  target = "assets"

[[mounts]]
  source = "layouts"
  target = "layouts"
```

Set the `image` parameters in `./config/_default/params.yml`:

```bash
image:
  ## General
  type: page # page (default) or global
  widths: [480, 640, 768, 1024, 1366] # [600, 900, 1300] (default)
  densities: [1,2] # [1,2] (default)
  formats: [original, webp] # [original, webp] (default)
  provider: null # null (default) or netlify
  loading: lazysizes # auto (default), lazy, or lazysizes
  class: "img-fluid blur-up" # img-fluid (default)
  output: picture # picture (default), figure, or img
  noscript: false # false (default) or true

  ## Placeholder
  placeholder: lqip # null (default), lqip, dominant, or [black, [gray-100..gray-900], white]
  lqip_div_factor: 5 # 5 (default)
  lqip_blur_amount: 5 # 5 (default)
  gif_div_factor: 10 # 10 (default)

  ## Figure
  target: "_blank" # _blank (default)
  rel: "noopener, noreferrer" # noopener, noreferrer (default)
  figure_class: "figure" # figure (default)
  figure_image_class: "figure-img img-fluid blur-up" # "figure-img img-fluid" (default)
  figcaption_class: figure-caption # figure-caption (default)
  figcaption_title_h: 4 # 4 (default)
  attr_link_target: "_blank" # _blank (default)
  attr_link_rel: "noopener, noreferrer" # noopener, noreferrer (default)

  ## Render hook
  render_hook: true # false (default) or true
  render_hook_wrapper_class: img-wrapper # img-wrapper (default)

  ## Shortcode
  shortcode_wrapper_class: img-wrapper # img-wrapper (default)

  ## Debugging
  suppress_width_warning: false # false (default) or true
  debug: false # false (default) or true
```

Add to `./assets/scss/components/_images.scss`:

```scss
img[data-sizes="auto"] {
  display: block;
  width: 100%;
}

.figure {
  display: block;
}

.blur-up {
  filter: blur(5px);
  transition: filter 400ms;
}

.blur-up.lazyloaded {
  filter: unset;
}
```

## How to use

See the Hyas documentation:

- [Images](https://docs.gethyas.com/guides/integrations-guide/images/)

## Credits

This npm package is based on the Hugo modules:

- [future-wd/hugo-responsive-images](https://github.com/future-wd/hugo-responsive-images)
- [future-wd/hugo-imaging-common](https://github.com/future-wd/hugo-imaging-common)
