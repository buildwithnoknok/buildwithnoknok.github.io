<!-- Leading-underscore filename => Jekyll excludes this from the built site. Maintainer note only. -->

# Deploy copy — do not edit here

`index.html` and `app.js` in this folder are a **deployed build** of the noknok Housing
Configurator. The source of truth lives in the **Ecosystem** repo:

    Ecosystem/mechanical/housing-configurator/   (main.js = source, app.js = esbuild bundle)

To update the live tool: in the Ecosystem repo run `npm run build` (regenerates `app.js`),
then copy `index.html` + `app.js` here and commit. Never hand-edit `app.js` (minified bundle).

Frozen releases are tagged in Ecosystem (`housing-configurator-v6`, …). This deploy = V6.
The how-to page is `/housing-configurator.md` (permalink `/housing-configurator/`).
