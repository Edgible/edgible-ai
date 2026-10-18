# www.edgible.ai

Edgible's marketing page: one static page, `index.html`, with the hero art in `images/`. The copy comes from the Vision 2028 doc's Messaging section; the hero and icons are in `images/` (the icon set is one sprite, `icons.svg`).

Preview it locally:

```bash
python3 -m http.server 8787 --bind 127.0.0.1   # then open http://127.0.0.1:8787
```

It is meant to be served by the static-site card on an Edgible device, under www.edgible.ai.

The typeface is Nexa, Edgible's own, served from `fonts/` as www.edgible.com does. It is a licensed font: keep `fonts/` out of any public copy of this repo unless the licence allows it.
