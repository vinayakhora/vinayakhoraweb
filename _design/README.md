# Design sources

Lossless masters for images used on the site. **Nothing in this folder is
published** — it sits outside `static/`, so Hugo never copies it into `public/`.
Keep it in git so the originals survive, but the deployed site stays lean.

## thumbnails/

The 1200×630 post thumbnails, as originally exported (PNG, ~1.2 MB each).

Each one is published as two derivatives in `static/images/`, because the two
uses have opposite requirements:

| Derivative | Used by | Why |
| --- | --- | --- |
| `<name>.webp` | `thumbnail:` in front matter | Rendered in the page and on the home-page card. Smallest file; Google/PageSpeed prefer it. |
| `<name>.jpg` | `ogImage:` in front matter | Social link previews. **WhatsApp will not render a WebP preview at all**, and Facebook is inconsistent with it, so social must be JPEG. |

Both must be 1200×630 (1.91:1) — that is the aspect ratio Facebook, LinkedIn
and WhatsApp use for the large preview card, and the ratio the home-page banner
card is sized to.

Keep the OG JPEG under ~300 KB; WhatsApp skips previews above roughly that size.

### Regenerating the derivatives

If a master changes, re-export both from the PNG — not from the existing WebP or
JPEG, which are lossy and would compound artefacts:

```python
from PIL import Image
im = Image.open('_design/thumbnails/NAME.png').convert('RGB')
im.save('static/images/NAME.webp', quality=88, method=6)   # page
im.save('static/images/NAME.jpg',  quality=90, optimize=True)  # social
```

Then check `thumbnail:` and `ogImage:` in **both** `content/en/post/…` and
`content/hi/post/…`, and set `thumbnailAside: false` so the post uses the
full-width banner card rather than the floated-aside layout.

After deploying, run the post URL through Facebook's Sharing Debugger and press
"Scrape Again" — it clears the cached preview for Facebook and WhatsApp both.
