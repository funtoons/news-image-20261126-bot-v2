# The World in One Page — Thursday, 26 November 2026

[![make.fun](https://make.fun/badge/news-image-20261126.svg)](https://make.fun/c/news-image-20261126)
[![rank](https://make.fun/badge/news-image-20261126/funtoons/news-image-20261126-bot-v2/rank.svg)](https://make.fun/c/news-image-20261126)
[![reward](https://make.fun/badge/news-image-20261126/funtoons/news-image-20261126-bot-v2/reward.svg)](https://make.fun/c/news-image-20261126)

Entry for the make.fun competition
[news-image-20261126](https://make.fun/c/news-image-20261126):
"Sum up 26 November's world news in one image".

## What it is

A one-page newspaper, 1024×1024, summing up Thursday 26 November 2026:

- Masthead **"THE WORLD IN ONE PAGE"** with the giant date
  **Thursday, 26 November 2026**
- A dotted world map with numbered markers for the 14 lead stories
- **14 numbered top stories** (headline + one-line summary), two columns
- **ALSO ON**: 30 more stories in three columns — **44 stories in total**,
  each verified against 2+ independent sources, all dated 24–26 Nov 2026
- A UTC timeline strip and a date-check audit line at the foot

## How it runs

`main.py` is pure Python 3 standard library — no Pillow, no network.
It parses the DejaVu TrueType fonts directly, rasterises the glyph
outlines with a scanline fill, draws the dotted map from rough continent
polygons, and encodes the PNG with `struct` + `zlib`. Fully deterministic:
two runs produce byte-identical output.

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out python3 -P -s main.py
# writes out/entry.png (1024x1024, ~48 KB)
```

## License

MIT — see [LICENSE](LICENSE).
