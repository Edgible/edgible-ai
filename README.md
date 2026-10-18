# www.edgible.ai

Edgible's marketing page: one static page, `index.html`. The copy comes from Edgible's Vision 2028 messaging. Images are in `images/`: the Edgible logo, symbol and favicon, and the icon set as one sprite, `icons.svg`.

Preview it locally:

```bash
python3 -m http.server 8787 --bind 127.0.0.1   # then open http://127.0.0.1:8787
```

It is served by the [static-site card](https://github.com/edgible-org/cards/tree/main/static-site) on an Edgible device, as www.edgible.ai: the card downloads this repo's `main` branch archive every few minutes, so a push to `main` goes live within minutes. `llms.txt` is the plain-facts summary for AI assistants.

The typeface is Nexa, Edgible's own, served from `fonts/` as www.edgible.com does. It is a licensed font, used here under Edgible's licence.
