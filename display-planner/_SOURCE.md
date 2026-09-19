<!-- Leading-underscore filename => Jekyll excludes this from the built site. Maintainer note only. -->

# Deploy copy — do not edit here

The files in this folder are a **deployed copy** of the noknok Display Planner. The source of
truth lives in the **Ecosystem** repo:

    Ecosystem/software/display-planner/   (index.html, app.js, layout.js, render.js, data.gen.js)

To update the live tool: edit there, run `node test/golden.mjs`, then copy those five files here
and commit. `data.gen.js` is generated from noknok.py + font8x8.h (`node data.gen.mjs`) —
never hand-edit it.

The how-to page is `/display-planner-guide.md` (permalink `/display-planner-guide/`).
