---
layout: post
title: "Eurorack power kit: power distribution board design"
description: "Designing a power bus board for Eurorack synth case"
date: 2017-09-01
tags: [eurorack, power-kit]
comments: true
image: /images/power-kit/EurorackBus.jpg
---
![power bus render](/images/power-kit/EurorackBus.jpg)
This power bus (part of my "eurorack power kit") was designed to be used in a
single row case. I'm planning to
build a small Eurorack synth system, and decided to make my own power supply and
distribution.

Most Chinese PCB fabrication services are very inexpensive if your board's
longest dimension fits within 100mm.[^1]
This is the reason the power kit bus only fits 5
module connectors: the PCB fab will produce 10 boards anyway,
so I can just install 2 or 3 of them in a single row case.
With parallel connection to the power
supply, it will even have lower electrical resistance (and hence, lower voltage
drop).

Bus board is completely flat on the back side, so it can be installed in the
case without drilling: just stick it with a
[3M VHB](http://www.3m.com/3M/en_US/company-us/all-3m-products/~/All-3M-Products/Adhesives-Tapes/Industrial-Adhesives-and-Tapes/Double-Sided-Bonding-Tapes/3M-VHB-Tapes/?N=5002385+8710676+8710815+8710960+8711017+8713604+3294857497&rt=r3)
adhesive tape or any appropriate glue.
To achieve this, I've selected surface mounted connectors:
the obvious
[Molex C-Grid](http://www.molex.com/molex/products/datasheet.jsp?part=active/0015910160_PCB_HEADERS.xml)
0.1" headers for connecting modules; and
[Phoenix PTSM](https://www.phoenixcontact.com/online/portal/us?uri=pxc-oc-itemdetail:pid=1814676&library=usen&tab=1&requestType=product&productId=1814676)
terminal block for power input.

Meng Qi [Flat Back Busboard](https://www.mengqimusic.com/#/flat-back-busboard/)
inspired this project.

![power bus render front view](/images/power-kit/EurorackBusFrontView.jpg)

Four 3mm mounting holes are also provided, so it can be mounted with screws.
It's easy to use the board itself as a drilling template when making holes in
the case back panel. The bolt holes are copper plated and electrically
connected to GND wire. It is safe to install the bus board into metal Eurorack
case because the chassis is supposed to be connected to GND.

Wires connecting this bus to the power supply should be solid copper with
cross-section of 0.5mm² max (⌀ 0.8mm, 20 AWG), as required by PTSM terminal spec.
It may be possible to use tinned stranded wire, but I wasn't able to test it yet.
Phoenix PTSM connector is push-in spring connection, so wire must be stiff
enough to be pushed in without bending itself.

The C-Grid header is non-shrouded, in accordance to
[recommendation of mr. Doepfer](http://www.doepfer.de/a100_man/a100t_e.htm)
to not use polarized headers on bus
boards and modules. Silkscreen line across the bottom row of contacts marks
the -12V power line. Remember: Red Stripe Down!

All images in this post were created in CAD, I wasn't yet able to actually
build this board and test it. Look for my future posts to see it built.

[KiCAD source files](https://github.com/smotesko/eurorack-power-bus)
are published in git repo.

[^1]: It can be just $5 for 10 boards!
