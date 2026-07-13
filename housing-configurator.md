---
title: Housing Configurator
permalink: /housing-configurator/
---

# noknok Housing Configurator

Design a custom 3D-printed housing for your noknok build — right in your browser.
Pick your modules, arrange them on a grid, and the configurator generates a single
snap-together box, ready to download as an STL and 3D print.

No account, no software to install, and **nothing is uploaded** — the whole tool runs
on your computer, offline once loaded.

<p style="margin:24px 0;">
  <a href="/configurator/"
     style="display:inline-block;background:#59d3a4;color:#04150f;font-weight:700;
            padding:14px 26px;border-radius:10px;text-decoration:none;font-size:17px;">
    ▶ Launch the Configurator
  </a>
</p>

**You'll need:** a desktop browser (Chrome, Edge, Firefox, or Safari) and access to a
3D printer — your own, a friend's, or an online printing service. A mouse or trackpad
makes placing modules easier.

---

## How it works

The configurator lays out your modules on a **10 mm grid** (every cell = 10 mm), then
builds one box with a **front cover** and a **back cover** of the same height. Inside,
each module is held by small **columns** that clamp its circuit board and line its
payload (buzzer grille, knob shaft, button, LED window…) up with an opening in the front.

You do it in five quick steps.

### 1. Add your modules

In the left panel under **Add a module**, click each module you want. It drops onto the
grid. The number next to each name (e.g. `20×20`) is its size in millimetres. Supported
modules today: **buzzer, knob, LED button, USB LEDs, and display**.

### 2. Arrange them

- **Click** a placed module to select it, then **drag** to move it.
- **⟳ rotate 90°** turns the selected module.
- **🗑 remove** deletes it.

Each module shows little markers you should keep an eye on:

| Marker | Meaning |
|--------|---------|
| ○ open circle | an **M2.5 screw hole** — a holding column will grow here |
| ▪ dark square | a **JST-SH connector** (the small I²C cable socket) |
| ▪ blue square | a **USB-C connector** |

Leave a bit of room next to the connector squares so cables can reach them, and try not
to let modules sit right on top of each other.

### Label a module (optional)

Select a module, type a label (e.g. "Volume"), pick an edge, and set the size — the text is
**engraved into the top cover** in the tiles next to that edge. Those tiles become part of the
box and no module can be placed on them, so leave room for the label when you arrange things.

### 3. Shape the box

The box starts as a rectangle hugging your modules (shaded green). To change its shape,
**click empty cells** to add or remove them — round off a corner, notch out a gap, or
bridge two separated modules into one enclosure. **↺ reset to rectangle** starts over.

> The status bar at the top warns you if a module is poking outside the box — just extend
> the box (or move the module) until everything is covered.

### 4. Add a power slot and latches

Your box needs two things on its walls, and the tool won't let you generate until both
are placed. **Click directly on a wall** of the box to add whichever is selected:

- 🔌 **Power slot** (blue) — a U-shaped notch, open at the top, that your USB-C power
  cable drops into. You plug the cable into the module first, then lay the cable into the
  notch before closing the covers — so only the thin cable needs to fit, not the whole plug.
  Add at least one, on the wall nearest where the cable should exit.
- 🔒 **Latch** (orange) — switch the toggle to *latch*, then click walls to add clips
  that hold the two covers shut. Add a couple around the box.

Keep power slots and latches on **separate walls** so they don't clash.

### 5. Generate and download

Click **Generate 3D box**. The tool switches to a 3D preview you can spin around
(drag to orbit, scroll to zoom). Use the toggle at the top to compare:

- **Assembled** — how the finished box looks.
- **Print layout** — the two covers laid flat and ready for the print bed.

Happy with it? Click **Download STL (both covers)** for the whole box, or grab each cover on
its own with **top cover** / **bottom cover** — handy for printing one at a time or in two
colours. (In the combined file the two covers are separate bodies, so your slicer's "Split to
objects/parts" also splits them.)

---

## Save your design

Not finished, or want to reuse a layout? Up in the left panel under **Design file**, click **💾 save** to
download your current 2D layout as a small `.json` file, and **📂 load** to open it again later — it
restores everything (modules, box shape, power slots, latches, joins, labels, cable mushrooms) so you can
keep editing. It's also an easy way to share a design with someone else. (Loading only accepts noknok
design files and quietly ignores anything it doesn't recognise.)

---

## Joining two boxes (optional)

Want to split a build across **two separate enclosures** — say a control box next to a lamp —
and still run a cable between them? The **Join to another box** tools add a tool-free dovetail
joint and a cable pass-through. You design and print each box on its own, then slide them together.

Like power slots and latches, you add these by **clicking a wall**:

| Tool | What it adds |
|------|--------------|
| ◤ **Male** | a dovetail *rail* on the outside of the wall |
| ◣ **Female** | a dovetail *groove* the rail slides into. It fills the tile just inside that wall, so no module can go there — add an empty cell with **Reshape box** if none is free |
| ▭ **Cable** | an opening in the wall for a cable to pass between the two boxes |

### Line them up

Because you design each box separately, *you* place the joint — and the two boxes have to match.
The 10 mm grid makes this easy: put a **male** rail on one box, and a **female** groove at the
**mirror position** on the wall of the other box that will face it. Do the same with a **cable
opening** on each box if you want to route wiring across.

> **Tip:** design both boxes at the same time and count grid cells from a shared corner, so the
> male on box A lands exactly opposite the female on box B.

Keep the joint tools on **different walls** from your power slots and latches.

### Put them together

Print both boxes, then **lower the second box straight down** so its rails slide into the first
box's grooves from the top. The dovetails lock the boxes together side-to-side; to take them apart
again, just **lift straight up** — no tools, nothing to break.

> This is a **brand-new feature**. The dovetail is a snug slide fit — if your first pair prints too
> tight or too loose, [tell us](https://noknok.odoo.com/support#Contact-us) and we'll fine-tune it.

---

## Printing and assembly

- **Orientation:** print from the **Print layout** — the front cover sits face-down and
  the back cover is placed beside it, mirrored, so it folds over and everything lines up.
- **Material:** PLA or PETG both work well. See the
  [3D Printing Guidelines](https://github.com/buildwithnoknok/Ecosystem/blob/main/mechanical/3D_printed.md)
  for layer height, infill, and material notes.
- **Assembly:** set each module onto the columns of the back cover, plug in the cables and
  lay the power cable into its slot, then press the front cover on until the latches click.
  To open it again later, push a latch in through its window from the outside — the box is
  fully repairable, nothing is glued or trapped.

---

## Good to know

- This is an **early tool** and we're improving it quickly. It currently covers the
  buzzer, knob, LED button, USB LEDs, and display modules.
- The configurator is **open source** (MIT). The code lives in the
  [Ecosystem repo](https://github.com/buildwithnoknok/Ecosystem/tree/main/mechanical/housing-configurator).
- Housings you export are yours to print, remix, and share — see our
  [License, Safety &amp; Liability](/safety-and-license/) page.

Built something great, or hit a snag? **[Tell the noknok team](https://noknok.odoo.com/support#Contact-us)** — we want to see it.

---

📄 [License, Safety &amp; Liability](/safety-and-license/) · Made with ❤️ in Switzerland.
