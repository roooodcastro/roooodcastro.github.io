---
layout:        post
title:         "Pump it Up Dance Pad build"
thumbnail:     /images/posts/piu-dance-pad/piu_prime2.jpg
thumbnail_alt: "Photo of completed pad"
date:          2020-05-15 15:52:00 +0000
author:        Rodrigo Azevedo
categories:    projects
tags:
  - DIY
  - Build
  - Arduino
  - 3D Printing
  - Woodworking
---

<p class="d-none">
  DIY dance pad for the game Pump it Up. Built using wood, full acrylic panels, 3D printed parts and LED lighting.
</p>

<!--more-->

Pump it Up is a dance arcade game, similar to DDR, except it's better ;). Back in my late teenage years I used to play
it all the time in a nearby shopping mall, sometimes multiple days a week. Building one of these pads myself was always
something I wanted, but I never quite had the expertise, time or money to pull it off. Of course I could buy or build
a "soft" foam pad, but I wanted the authentic arcade feel of a hard pad.

{% include image.html name="piu_prime2.jpg" description="Pump it Up arcade cabinet and pads, Prime 2 version" %}

A decade later I still had fond memories of the game and now I had more access to tools and had learnt a thing or two
about DIY, so I decided to take the plunge and give it a go at building this. I also have a 3D printer now, which I
knew I could use to print custom parts for it if needed, and with that I also learnt how to use CAD software like
Fusion 360 to model stuff.

Detailed posts on how I built this will be written, this is just a high level overview of what the pad is made of and
what it can do. This is what it looks like after months of work, and over a hundred of man-hours of designing,
prototyping, building, and most importantly, play testing the pad:

{photo of finished pad}

### Frame

The pad frame is built mainly out of wood, and has (should have) the same dimensions as the official pad. The only size
difference is at the front and back, where the official pads have an extended area in the front for the electronics,
and an extended area at the back for the metal bar. That bar is meant for the player to hold on so they can keep their
balance on harder songs and it's something I intend to integrate to my pad in the future. The final external dimensions
of the pad are 877x877x57mm, plus some 40mm at the front for the handles, and it weights 20.4kg.

Along with wood, each panel is supported by a 3D printed frame. 3D printing was chosen mainly because I'm a
developer/tech person, and I can create a more complex 3D design much more easily than I can make complex wood cuts
and joins :). And yes, even with full adults jumping up and down on those plastic parts, they seem to be holding the
impact very well, with no visible wear. Lastly, I added some handles so it's easy to pick it up and store it, as I live
in a compact apartment and optimising space is a must.

{photo of new naked structure with wood/3d printed pad frame}

### Panels

Each individual panel (also called a pad) is made of 10mm clear polycarbonate acrylic sheets, and the art on them was
printed in regular, office A4 paper, and glued on with regular white glue. It's far from ideal, and it clearly shows,
but it's easy to scrape it off in the future to upgrate to something more proper. 10mm seems quite thin to support the
weight of adults smashing the panels, but so far it has proven to be very apt for the job.

{photo of acrylic pads with glued art}

### Step sensors

Everyone that has tried to build one of these knows that the trickiest parts of the build are probably the sensors. The
sensors detect when the player is stepping on the panel, and send this input to the game. There are many ways to build
an effective sensors. Arguably the simplest option is to mount a conductive plate on the panel and another on the
frame, and find a way to keep them apart, allowing them to contact each other when pressure is applied to them. This
approach is electrically equivalent to a momentary push button, and is very easy to use with Arduino. I decided to
create a sensor out of 3D printed parts, so I iterated over many designs and reached this final form of the sensor,
which works beautifully and so far hasn't given me any issues, and me and my wife have been playing PIU at home for
months now. Each panel uses 4 sensors, one on each side, making it easy to trigger it by stepping anywhere on the
panel, center or not.

{% include
  image.html
  name="sensor_disassembled.jpg|four_sensors.jpg"
  description="The sensor flexes with pressure, creating electric contact|Four sensors aligned like they would on a panel"
%}

### Electronics

Underneath each panel there are 8 LEDs that light it up whenever a player steps on them, also to emulate the official
pads. The whole pad, including the LEDs, is controlled by an Arduino Leonardo. The Leonardo was chosen because it can
act natively as a USB keyboard/mouse/game controller. When the pad is connected to a PC, it shows up as a generic HID
game controller with 5 buttons, making it very easy to setup key mappings on games such as
[Stepmania](https://www.stepmania.com/) or [StepF2](http://stepf2.blogspot.com/) (which is what I use). One of the main
limitations of this pad is that it can't be used with the official game distribution (the official HDD), as that needs
a very specific hardware setup, and proprietary IO boards.

{side by side photos of lit up LEDs and Arduino wiring}

### Conclusion

It took me around 7 months, working on and off to finish this pad. I have only a slight idea of how much it cost me to
build it, as a lot of stuff I had to redo or buy parts for it again because the first iterations were crap. Designing
it from scratch is definitely not for everyone, it took a lot of patience and ingenuity to solve some of the issues I
had, but overall it was a very rewarding process, and I've learnt a lot doing this.

I already have plans to build a second pad so I can play doubles, which should be much easier as I already have some
material, and all of the tools and designs I used for the first one. Before that, though, I intend to integrate some
bars in the pad so I can play songs higher than S13, which are kind of hard without a bar, as one tends to lose either
balance or stamina too quickly.
