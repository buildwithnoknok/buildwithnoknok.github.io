---
title: Display Planner
permalink: /display-planner-guide/
---

# noknok Display Planner

Design what your **noknok Display** shows — right in your browser. Lay the screen out as
named boxes, drop in text, icons or a picture, see exactly what the panel will draw, and
copy the Python code into your product. It also turns any image into a crisp 1-bit icon.

No account, no software to install, and **nothing is uploaded** — the whole tool runs on
your computer, offline once loaded.

<p style="margin:24px 0;">
  <a href="/display-planner/"
     style="display:inline-block;background:#59d3a4;color:#04150f;font-weight:700;
            padding:14px 26px;border-radius:10px;text-decoration:none;font-size:17px;">
    ▶ Launch the Display Planner
  </a>
</p>

**You'll need:** a desktop browser (Chrome, Edge, Firefox, or Safari), a noknok Display on a
Pico running `noknok.py` **1.9 or newer**, and a mouse or trackpad.

---

## The idea in one minute

The noknok Display has no frame buffer, so redrawing the whole screen for every little
change is slow and flickery. `noknok.py` solves that with **named regions**: you define a
box once —

```python
d.region("temp", 0, 40, 80, 32, size=32, color=YELLOW, align="center")
```

— and from then on you update it by name, and only that box is redrawn (about 15 ms):

```python
d.set("temp", text="22.5")
d.set("temp", icon="warning")
```

The planner is the visual front-end for that: you draw the boxes, it writes the
`d.region()` and `d.set()` lines, and the preview shows what the panel really renders —
same fonts, same wrapping, same clipping as the Pico and the module use.

---

## Layout tab

### 1. Pick your display

Top-left: choose **noknok Display 1.42″ (80 × 160)** and the **orientation**. Landscape
turns it into 160 × 80 and adds a `d.rotation(1)` line to the code. (Custom sizes are
there for displays that don't exist yet — up to 255 × 255.)

**Background** is the colour the screen is cleared to; every region wipes to it (or to its
own box background) before drawing.

### 2. Draw regions

**Drag a rectangle** on the enlarged display. That's a region. Give it a name in the panel
on the right — that's the name you'll use in `d.set("name", ...)`.

- **Move** by dragging it, **resize** with the corner and edge handles, **nudge** with the
  arrow keys (Shift = 8 px), **Del** removes it. Everything snaps to whole pixels.
- **Size** is the pixel height of text (and of icons) in this box.
  Sizes **8, 16, 24, 32, 40, 48, 56, 64** are drawn by the display module itself with its
  square 8 × 8 font — fastest, but wide: 16 px text is 16 px wide, so an 80 px panel fits
  5 characters. Any other size uses the Pico's narrower 8 × 16 font (16 px text → 8 px
  wide → 10 characters). The panel tells you the columns × lines your box gives.
- **Colour**, **box background** and **alignment** (left / center / right) are the
  region's defaults.

### 3. Give each region content

Under **Content**, pick one:

- **text** — type it. Enter starts a new line. The preview wraps and clips exactly like the
  Pico will, and the **Checks** list tells you when it doesn't fit.
- **icon** — choose one of noknok.py's built-ins (wifi, battery, check, cross, warning,
  play, pause, gear, arrows, heart, bell) or one of your own from the Icons tab. It is
  scaled to the region's size.
- **image** — drop a PNG / JPG / SVG / BMP. It is converted to 1-bit at the box size; tune
  it with the threshold, dither and invert controls. Small images go straight into the
  code; bigger ones are exported as a `.bmp` you copy into `/pics/` on the Pico.

### 4. Read the checks

The **Checks** box flags the things that bite on a tiny screen: text that needs more lines
than the box has, a line wider than the box, overlapping regions (each `d.set()` wipes its
whole box, so overlapping boxes erase each other), regions that stick out of the panel,
and — if you tick **I also use d.print()** — regions inside the band `print()` repaints.

### 5. Copy the code

The **Python code** box is always up to date. Click **copy code** and paste it into your
`product.py` right after you fetch the display:

```python
d = c.display[0]
# … paste here …
```

It contains the definitions of any icons you drew, `d.clear(...)`, one `d.region(...)` per
box, and a starter `d.set(...)` for each. From then on, call `d.set(name, text=...)` whenever
a value changes.

**Save .json** keeps the layout (with your icons) so you can reload or share it. The
planner also remembers your last layout in the browser.

---

## Icons tab

Two ways to make an icon:

- **Draw it.** Set a width and height, click **+ new icon**, and paint: left-drag draws,
  right-drag erases; there's a fill bucket, invert, flip, rotate and shift.
- **Import it.** Drop any image. Choose the target size (16 × 16 is the built-in size),
  **fit / stretch / crop**, whether to read **brightness** or **transparency** (auto picks
  transparency for PNGs with a see-through background), a **threshold**, optional
  **dither** for photos, and **invert**. Then touch it up with the pen.

The three previews show the icon at **1:1** — on a normal monitor that is about the real size
on the panel — 2:1 and 4:1, tinted in any noknok colour.

**Export:**

- **copy code** — an `ICONS["name"] = [...]` snippet. Paste it into your product and use
  the icon like a built-in: `d.icon("name", x=10, y=10)` or `d.set("box", icon="name")`.
  Any colour, any size — icons are masks, tinted when drawn.
- **.bmp** — a 1-bit file for `d.image("/pics/name.bmp")`.
- **save to my icons** — keeps it in the browser and lists it in the Layout tab.

---

## Good to know

- The preview isn't a mock-up: it is produced by a port of `noknok.py`'s own drawing code,
  and it is tested pixel-for-pixel against the real library on every change.
- Coordinates are single bytes on the wire (0–255), which is why the panel size is capped.
- `d.print()` and regions don't mix well: `print()` repaints full-width lines from the top.
  Use one or the other, or keep the regions below the print area.
- The planner is **open source** (MIT). The code lives in the
  [Ecosystem repo](https://github.com/buildwithnoknok/Ecosystem/tree/main/software/display-planner);
  the runtime it targets is
  [`noknok.py`](https://github.com/buildwithnoknok/brain-Pico/tree/main/software).
- This tool was built with the help of AI — see our
  [License, Safety &amp; Liability](/safety-and-license/) page.

Built something great, or hit a snag? **[Tell the noknok team](https://noknok.odoo.com/support#Contact-us)** — we want to see it.

---

📄 [License, Safety &amp; Liability](/safety-and-license/) · Made with ❤️ in Switzerland.
