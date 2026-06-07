# Product logos — drop-in slots

Each product card in `Norditech.html` automatically shows a real logo if a matching
image exists in this folder. Until then, a styled fallback glyph is shown.

## How it works
The card renders both a fallback glyph **and**:

```html
<img class="logo-img" src="product-icons/<slug>.png" onerror="this.remove()" />
```

- If the file exists → the real logo covers the tile (object-fit: cover).
- If it 404s → the `<img>` removes itself and the glyph stays. No layout shift.

## Add the real app icons (from the original screenshots)
Save each as a square PNG (recommended 256×256 or larger) using these EXACT filenames:

| Product         | File                              |
|-----------------|-----------------------------------|
| ReelHome        | `product-icons/reelhome.png`      |
| AlgoMaster      | `product-icons/algomaster.png`    |
| SinglePicker    | `product-icons/singlepicker.png`  |
| BilDeal         | `product-icons/bildeal.png`       |
| CenterForge     | `product-icons/centerforge.png`   |
| SummonIt        | `product-icons/summonit.png`      |
| Reforhandle     | `product-icons/reforhandle.png`   |
| A-Pop Showdown  | `product-icons/apop-showdown.png` |
| Dr. Hanni       | `product-icons/drhanni.png`       |

The tile is 54×54 px with 15px rounded corners and `overflow:hidden`, so app-icon
artwork (already rounded squares) drops in cleanly. `.svg` also works if you change
the extension in the `src` (search `product-icons/${p.slug}` in Norditech.html).

The glyph fallback colors live in the `tile:` field of each entry in the `PRODUCTS`
array — adjust if a real logo needs a different glow color.
