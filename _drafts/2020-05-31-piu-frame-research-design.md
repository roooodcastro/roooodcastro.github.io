---
layout:        post
title:         "PIU Dance Pad - Research, Frame Design and Build"
thumbnail:     /images/posts/piu-frame-research-design/first_wood_frame.jpg
thumbnail_alt: "Full wood frame, assembled but not screwed"
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
  Details about how I initially researched and designed the wooden frame. From finding official manuals to look for
  dimensions, to designing the whole frame in Fusion 360.
</p>

<!--more-->

<em>This is the first post in a four part series detailing my process of building a DIY Pump it Up pad. If you don't
know what this is about, check my [project summary here](/).</em>

---

My initial idea for this project was to build a sturdy wood and metal frame, identical to the arcade ones, both in size
and in looks. I then started to google the exact dimensions and specifications for the pads, how the sensors worked,
etc. With that in hand, I started to design a wooden frame in Fusion 360. At first I had only a rough idea of the size
of the timber I was going to build, so I made sure to parameterise everything so that I could adjust in the future.
I designed it in a way that it would only use cuts from 15mm plywood board and 2x1 softwood timber, to make it as
simple and cheap as possible. I also didn't have any decent power tools to cut wood, and wanted to buy the fewest tools
I could to get it done, so the wood cuts had to be as few as simple as possible.

The following images are from the Fusion 360 design I initially drew. All the dimensions are correct in the finished
pad, but the pad frames (bottom left picture) were designed as 3D printed parts instead of wood ones.

{% include
  image.html
  name="base_frame_project.png"
  description="Frame project without any top plates"
%}

{% include
  image.html
  name="frame_timber_project.png|frame_mid_supports_project.png"
  description="Pad frames dimensions|Pad middle top plates supports dimensions"
%}


I then ended up with a finished project for the pad, and from there I could start looking into local suppliers for
wood, steel and acrylic. After getting a few quotes, I quickly realised that the metal plates would be by far the most
expensive part of the project, as I'd need to get them already cut and bent, as I don't have a press brake to do so.
The cheapest quote I got was around €120, and that didn't even include the bending, so I simply gave up on using steel.

I managed to find a place that sold the plywood sheet already cut to size (at a premium), which saved me *a lot* of
work, since I would need to handle and cut the 1550x1550x15mm sheet by myself with manual tools inside an apartment,
not fun. To cut the 2x1 (actually 42x20mm) timber, I used a mitre saw and a 3D printed mitre block. Throughout this
project, I used quite a lot of 3D printed tools and jigs, making a lot of the work easier and more precise.

{% include
  image.html
  name="mitre_saw_and_block.jpg"
  description="Mitre saw and block guide I used to cut the timber to size"
%}

After cutting everyting to size, I ended up with the first version of the frame. As mentioned before, this would not be
the final version of it, as I replaced most of the wood inside, keeping only mostly the outer shell made out of wood,
with 3D printed plastic parts. This might be confusing as wood is regarded as being much stronger than plastic,
especially for this kind of application that needs good mechanical strength, but the sensor design was ultimately the
decisive factor in this. I'll talk more about that in a later post.

To actually construct and secure the frame, I used 4x30mm wood screws. I only used wood glue on the frame's outer
shell, as it was the only part I knew for sure I wouldn't need to disassemble or change later. I'm glad I did that,
otherwise I wouldn't be able to swap the pad frame for plastic later on.

{% include
  image.html
  name="first_wood_frame.jpg|first_wood_frame.jpg"
  description="Assembled (but not fixed) wood frame|Hybrid wood+plastic frame"
%}

Lastly, I decided to incorporate a USB socket to facilitate plugging the pad into a computer, and avoid having a
dangling cable while the pad was not in use, and also add a 3D printed handle to more easily lift the pad up to store
it while not in use. The photo below also shows a second socket, for a generic DC power socket. This was to be used as
input for the power source of the LEDs, but ultimately I scaled down on the number of LEDs and the current draw fell
to whithin the limits of a USB 3.0 connection, so that's not needed anymore.

{% include
  image.html
  name="usb_socket.jpg|frame_handle.jpg"
  description="USB and DC sockets|Handle to carry the pad"
%}

---

### Bill of Materials for the pad

These are the materials I used to build the whole pad, along with approximate costs for each. These estimates are for
the finished, wood/plastic hybrid pad, but in reality I spent a lot more on prototype stuff and parts that were
eventually scraped. The 3D printed parts were mostly printed with 3 perimeters and 15% infill. The number of screws
used in the whole pad is 179, quite a lot, and most of these were used in each pad's support assembly together with the
3D printed parts.

##### Tools:

I'm not including the cost of the tools, as I already owned some of them, but these are most of the tools I used in
the project:

* DeWalt 650W corded impact drill (used as a drill and as a power screwdriver)
* 3D printer (Prusa i3 clone)
* Foldable workbench
* Mitre saw
* 3D printed mitre block
* 3D jigs for cuts and holes
* Wood adhesive
* Dremel

#### Materials:

<table class="table table-striped table-bordered">
<thead>
  <tr class="text-secondary">
    <th>Material</th>
    <th class="text-right">Quantity</th>
    <th class="text-right">Unit price</th>
    <th class="text-right">Total price</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td>15mm plywood sheet, 1550x1500mm cut to size</td>
    <td class="text-right">1</td>
    <td class="text-right">€39.50</td>
    <td class="text-right">€39.50</td>
  </tr>
  <tr>
    <td>42x20mm treated timber, 2400mm long</td>
    <td class="text-right">3</td>
    <td class="text-right">€2.93</td>
    <td class="text-right">€8.79</td>
  </tr>
  <tr>
    <td><a href="https://www.spax.com/en/products/universal/flat-countersunk-head/universal-screw-4-x-30-mm-200-pieces-full-thread-flat-countersunk-head-cross-recess-z2-4cut-wirox-1081010400303/pid-1137/">
      Spax wood screws 4x30mm box of 200
    </a></td>
    <td class="text-right">1</td>
    <td class="text-right">€4.99</td>
    <td class="text-right">€4.99</td>
  </tr>
  <tr>
    <td><a href="https://www.amazon.co.uk/gp/product/B07JD19BL4/">"Furniture" M6x30mm wide head screws</a></td>
    <td class="text-right">20</td>
    <td class="text-right">€0.30</td>
    <td class="text-right">€6.00</td>
  </tr>
  <tr>
    <td><a href="https://www.amazon.co.uk/s?k=black+pla+filament">Black PLA filament 1kg</a></td>
    <td class="text-right">2</td>
    <td class="text-right">€20</td>
    <td class="text-right">€40</td>
  </tr>
  <tr>
    <td><a href="https://www.aliexpress.com/item/32851664724.html">Metal USB socket female to female</a></td>
    <td class="text-right">1</td>
    <td class="text-right">€2.35</td>
    <td class="text-right">€2.35</td>
  </tr>
  <tr>
    <td>10mm clear polycarbonate pads cut to size</td>
    <td class="text-right">5</td>
    <td class="text-right">€15.00</td>
    <td class="text-right">€75.00</td>
  </tr>
  <tr>
    <td><a href="https://www.amazon.co.uk/s?k=ws2812b+led+strip">WS2812B LED strip (min. of 40 LEDs needed)</a></td>
    <td class="text-right">1</td>
    <td class="text-right">€15.00</td>
    <td class="text-right">€15.00</td>
  </tr>
  <tr>
    <td><a href="https://www.amazon.co.uk/gp/product/B07CHF21TB/">Arduino Leonardo</a></td>
    <td class="text-right">1</td>
    <td class="text-right">€8.75</td>
    <td class="text-right">€8.75</td>
  </tr>
  <tr>
    <td><a href="https://www.amazon.co.uk/gp/product/B00LOG8M68/">Wago Connectors (5 conductors)</a></td>
    <td class="text-right">12</td>
    <td class="text-right">€0.54</td>
    <td class="text-right">€6.48</td>
  </tr>
  <tr>
    <td>Electrical wires (between 18-22AWG)</td>
    <td class="text-right">~5m</td>
    <td class="text-right">€1.00</td>
    <td class="text-right">€5.00</td>
  </tr>
  <tr>
    <td><a href="https://www.aliexpress.com/item/32854540905.html">JST RCY connector pair</a></td>
    <td class="text-right">20</td>
    <td class="text-right">€0.10</td>
    <td class="text-right">€2.00</td>
  </tr>
  <tr>
    <td><a href="https://www.amazon.co.uk/gp/product/B000QVPIQ4/">Conductive copper tape (slug tape)</a></td>
    <td class="text-right">1</td>
    <td class="text-right">€4.99</td>
    <td class="text-right">€4.99</td>
  </tr>
  <tr>
    <td colspan="3" class="font-weight-bold">Total cost</td>
    <td class="font-weight-bold text-right">€218.85</td>
  </tr>
</tbody>
</table>

#### Plywood and timber cuts:

These are the sizes in which the plywood and timber need to be cut, for a hybrid wood/plastic pad using 42x20mm timber:

Plywood:

* 1x 877x877mm
* 2x 277x159mm
* 2x 277x279mm

Timber:

* 2x 877mm
* 2x 837mm
* 8x 277mm (these need to be cut along its length so it ends up being almost square at 27x20mm instead of 42x20mm)