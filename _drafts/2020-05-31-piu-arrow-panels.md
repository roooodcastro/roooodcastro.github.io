---
layout:        post
title:         "PIU Dance Pad (part 2) - Arrow Panels"
thumbnail:     /images/posts/piu-arrow-panels/finished_arrows.jpg
thumbnail_alt: "Acrylic pads with the arrow art printed on them"
date:          2020-05-15 00:00:00 +0000
author:        Rodrigo Azevedo
categories:    blog
tags:
  - DIY
  - Build
  - Arduino
  - PIU
  - DDR
  - Arcade
  - 3D Printing
  - Dance Pad
---

<p class="d-none">
  Design, construction and prototypes of the acrylic arrow panels for each pad.
</p>

<!--more-->

<em>This is the second post in a four part series detailing my process of building a DIY Pump it Up pad. If you don't
know what this is about, check out my [project summary here](/). You can also jump to any part of the series:</em>

* [Part 1 - Frame Build and BOM]()
* **Part 2 - Arrow Panels**
* *Part 3 - Pad Sensors (TODO)*
* *Part 4 - LEDs and Electronics (TODO)*
* *Part 5 - Arduino Programming (TODO)*

---

Talk about wood pads, 15mm x 10mm, bracket vs bracketless, and LEDs.

Another big decision, which was later changed, was to build the pad with brackets, as opposed to the new bracketless
pads. I chose that mostly for nostalgia, as that's how the pads were when I used to play it years ago. The brackets
are meant to hold the acrylic panels in place, otherwise when you step in the corner of a panel, the opposing corner
would lift up, potentially lifting the whole pad out of its place, ruining the song, and potentially hurting your feet.
They also need to be as thin as possible, so the only possible material for them was steel. The brackets themselves
need to be a bit bigger than their supports, so that the resulting lip can be used to hold the panel in place. I'm not
going into too many details on how I designed and built those, as they ultimately were scraped, and I also only made
and installed about 2 of them per panel, as that was the bare minimum needed to hold the panels (wood at the time) in
place. Here are some pictures of their design and build:

{% include
  image.html
  name="pad_corner_detail_project.png|wood_pad.jpg"
  description="Steel bracket and its support|Draft pad with 2 brackets installed"
%}

{% include
  image.html
  name="steel_bracket.jpg|rusty_bracket.jpg"
  description="Finished mild steel bracket|Developed a lot of rust after some use as it wasn't stainless"
%}

### Bill of Materials for the pads

These are the materials, parts and tools I used to make the frame, along with approximate costs for each. These
estimates are for the finished pad, in reality I spent a lot more on prototype stuff and parts that were eventually
scraped. The 3D printed parts, when printed with 3 perimeters and 15% infill sum up to between 1100-1200g, so 2 1kg
rolls are needed. The number of screws used in the frame alone was 43, but the total project used 179 screws in total.

TODO:

- Sensors
- Electronics and Arduino