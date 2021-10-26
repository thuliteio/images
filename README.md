# Hyas images

Image render hook + shortcodes for Hyas sites.

## Installation

```bash
npm i @hyas/images -D
```

## Setup

Add to `./config/_default/module.toml`:

```toml
[[mounts]]
  source = "layouts"
  target = "layouts"

[[mounts]]
  source = "node_modules/@hyas/images/layouts"
  target = "layouts"
```

Add to `./config/_default/params.toml`:

```bash
# Images
quality = 85
bgColor = "#fff"
landscapePhotoWidths = [900, 800, 700, 600, 500]
portraitPhotoWidths = [800, 700, 600, 500]
lqipWidth = "20x"
smallLimit = "300"
```

## Usage

See the Hyas docs: [Images](https://gethyas.com/docs/recipes/images/)
