<div align="center">

# Silicon Wheels

**High-traction cast silicone wheels for mini sumo (500 g) and 3 lb beetleweight combat robots**

![Robot Classes](https://img.shields.io/badge/robots-mini%20sumo%20%7C%203%20lb-blue)
![Tire Material](https://img.shields.io/badge/tire-cast%20silicone-success)
![Hub](https://img.shields.io/badge/hub-3D%20printed-orange)
![License](https://img.shields.io/badge/license-all%20rights%20reserved-red)
![Status](https://img.shields.io/badge/status-active-brightgreen)

**Anastasios Karaivazoglou · IRONBRICK | FIBRAN**

<p>
  <img src="docs/images/hero.png" alt="Silicon Wheels hero shot" width="480"/>
</p>

</div>

> [!NOTE]
> **Silicon vs. silicone:** the material used here is **silicone rubber** (a polymer), not the element silicon. "Silicon Wheels" is simply the project name — the tires are cast from platinum-cure silicone.

---

## Table of contents

- [About](#about)
- [Why silicone?](#why-silicone)
- [Features](#features)
- [Specifications](#specifications)
- [Repository layout](#repository-layout)
- [How they are made](#how-they-are-made)
  - [Bill of materials](#bill-of-materials)
  - [Print settings](#print-settings)
  - [Casting procedure](#casting-procedure)
  - [Assembly](#assembly)
- [Mounting to your robot](#mounting-to-your-robot)
- [Tuning & maintenance](#tuning--maintenance)
- [Measured performance](#measured-performance)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgments](#acknowledgments)
- [Gallery](#gallery)

## About

Silicon Wheels is a set of open-hardware, high-grip wheels designed from the ground up for two of the most traction-hungry weight classes in hobby robotics:

- **Mini sumo (500 g, 10 × 10 cm footprint)** — where the match is won or lost by static grip and pushing force.
- **3 lb beetleweight combat robots** — where wheels must survive hits, spin-outs, and arena grit while still hooking up under full throttle.

Each wheel is a two-part design: a lightweight **3D-printed hub** with a keyed outer profile, and a **cast silicone tire** poured directly around it. The silicone locks onto the serrated hub mechanically *and* chemically, so the tire can't spin, slip, or peel off — no adhesives required.

The whole thing is manufacturable on a desktop FDM printer and a workbench: no CNC, no lathe, no special tooling.

## Why silicone?

| Tire option | Grip | Weight | Tunability | Wear life | Cost |
| --- | --- | --- | --- | --- | --- |
| Printed TPU | Medium | Medium | Limited | Good | $ |
| Rubber (FR/Duratrax-style) | High | Medium | None | Medium | $$$ |
| **Cast silicone (this project)** | **Excellent** | **Low** | **Any durometer** | **Good** | **$$** |

- Silicone flows into a mold and cures at room temperature, so **any durometer, diameter, and width is one mold away**.
- Platinum-cure silicones span roughly **Shore 00-30 to 50A**, letting you dial in exactly how soft or durable your contact patch is.
- Cast silicone grips better than printed TPU because there are no layer lines on the tread and the surface stays tough and tacky instead of waxy.

## Features

-  **Zero-slip hub interface** — serrated/keyed hub profile locks the tire mechanically.
-  **Tunable durometer** — swap silicone hardness to match surface and strategy.
-  **Lightweight** — spoked hub keeps rotating mass low for faster acceleration.
-  **Rebuildable** — tires can be recast with minutes of labor; hubs reprint for pennies.
-  **Parameterized** — change a few variables to generate new diameters, widths, and bores.
-  **Drop-in mounting** — sized for common hobby gearmotor shafts (3 mm N20 and 4 mm options).
-  **Two weight classes covered** — geometry validated for mini sumo and 3 lb beetle builds.

## Specifications

<!-- EDIT: Add beetle hub bore, mounting method and both as-cast wheel masses — then delete this comment. -->

| Parameter | Mini sumo wheel | Beetleweight wheel |
| --- | --- | --- |
| Outer diameter | 26.5 mm | 44 mm |
| Tire width | 19 mm silicone (22 mm overall) | 12 mm |
| Hub bore | 3 mm, M4 setscrew tap | — |
| Hub material | Machined aluminum rim — [JSumo JS2622](https://jsumo.com/js2622-aluminum-silicone-wheel-pair) | TPU, printed rim/hub |
| Tire material | PL30 — 2-part platinum-cure RTV, 1:1 by weight | PL30 — 2-part platinum-cure RTV, 1:1 by weight |
| Tire durometer | ~30 Shore A | ~30 Shore A |
| Wheel mass | 12 g (as-sold JS2622) | — |

## Repository layout

```text
Silicon_Wheels/
├── cad/                 # Parametric source (OpenSCAD / Fusion 360 / FreeCAD)
├── stls/                # Printable hub files
│   ├── hub_26.5mm_minisumo.stl
│   └── hub_44mm_beetle_tpu-rim.stl
├── molds/               # Printable tire molds (two-piece, keyed)
│   ├── mold_26.5mm_top.stl
│   └── mold_26.5mm_bottom.stl
├── docs/
│   └── images/          # Photos used in this README
└── README.md
```

## How they are made

**Process at a glance:**

```text
print mold ──► clean & release ──► mix silicone ──► clamp & pour ──► cure ──► demold & trim ──► mount & test
```

### Bill of materials

| Item | Qty | Price | Notes |
| --- | --- | --- | --- |
| [PL30 platinum-cure silicone — 2×500 g kit](https://www.pacoartcenter.gr/en/platinum-cure-silicone-rubber-compound.html) (Paco Art Center) | 1 kit (1 kg) | €33.90 | Reference tire material — 2-part platinum RTV, mix 1:1 by weight; a wheel pair needs ~40 g, so one kit casts many sets. Bigger kits available up to 2×5 kg (€290). Smooth-On Rebound 25, Sorta-Clear, VytaFlex work as alternatives |
| [Silicone pigment — 25 g](https://www.pacoartcenter.gr/en/crafts/mold-making-casting/mold-making/silicone-pigments.html) (Paco Art Center) | 1 | €3.90 | Optional color. Super-concentrated, platinum-safe: ~10 drops per 100 ml (0.01–3% by weight). Overdosing can inhibit curing or soften the tire — test on a small batch first |
| [JSumo JS2622 aluminum wheel pair](https://jsumo.com/js2622-aluminum-silicone-wheel-pair) | 1 pair | $12.95 | Mini sumo variant — machined rim, 3 mm bore + M4 setscrew; cast PL30 into its 19 mm silicone groove |
| Filament | ~30 g | — | PETG for the mold, TPU 95A for the beetle rim/hub; PLA works for optional rigid hubs |
| [Mold securing screws](https://s.click.aliexpress.com/e/_c2QYYCJZ) + [nuts](https://s.click.aliexpress.com/e/_c2IxNp8B) | 4 + 4 | — | Bolt the two mold halves together — keeps the alignment pins seated and stops silicone leaking along the parting line |
| Mold release agent | 1 | — | Ease Release 200 or equivalent (platinum-safe) |
| [Plastic mixing cups](https://s.click.aliexpress.com/e/_c4EeuXZp) | 2 | — | One for mixing, one for topping off — mix slowly and thoroughly to avoid entrained air |
| [Wooden stir sticks](https://s.click.aliexpress.com/e/_c2xJT4WR) | a few | — | Scrape the walls and bottom of the cup while mixing parts A + B |
| [Digital scale (0.1 g)](https://s.click.aliexpress.com/e/_c34q1PFz) | 1 | — | Required for PL30's 1:1 by-weight mix |
| Nitrile gloves | 1 pair | — | Keep uncured silicone off skin; latex inhibits PL30 |
| Isopropyl alcohol | small bottle | — | Surface prep + cleanup |
| [Carving blades](https://s.click.aliexpress.com/e/_c3cynCwB) | 1 set | — | Trim flash and excess silicone after demolding |
| Vacuum chamber *(optional)* | 1 | — | Bubble-free tires; degassing is strongly recommended |

> [!WARNING]
> **Platinum-cure silicones are inhibition-sensitive.** Uncured SLA resin, sulfur-containing clay, some spray releases, and fresh paint can prevent curing — even latex gloves can poison the cure, so use nitrile or vinyl only. Only use platinum-safe release agents, and if you must mold against an SLA print, wash and post-cure it thoroughly first — FDM molds are the safe default.

### Print settings

**All printed parts are made on a Bambu Lab A1 mini.**

| Part | Material | Layer height | Walls | Infill | Notes |
| --- | --- | --- | --- | --- | --- |
| Hub (rigid) | PETG (PLA works) | 0.16–0.20 mm | 5–6 | 35–45% gyroid | Strong walls matter for grub-screw clamping |
| Hub (TPU rim) | TPU 95A | 0.20–0.25 mm | 4 | 15–20% | Flexible rim/hub bonds well to cast silicone; print slow |
| Mold | PETG | 0.20 mm | 4 | 20% | Keyed two-piece design prints support-free |

### Casting procedure

1. **Prepare the mold** — clean both halves of the 3D-printed mold thoroughly with isopropyl alcohol, then apply a thin layer of release agent to the inner surfaces (e.g., mold release spray or vaseline). Place the bottom half of the mold on a flat surface and insert the aluminum rim — wipe the rim with IPA first; clean surfaces bond better.
2. **Mix the silicone** — measure 7 g of part A and 7 g of part B into a cup (PL30 mixes 1:1 by weight), add one drop of silicone pigment for color, and mix slowly for 2–3 minutes to avoid bubbles.
3. **Cast the wheel** — carefully place the top mold half and clamp it firmly with the securing screws and nuts. Slowly pour the silicone into the mold until it is completely filled, then let it cure for the recommended time (usually 6–12 hours).
4. **Demold and finish** — once cured, gently open the mold and remove the wheel. Trim any excess silicone (flash) with a carving blade or small scissors.
5. **Mount and test** — mount the silicone wheel on the mini sumo axle (M4 setscrew against the shaft flat) and test grip on the arena surface.

> [!TIP]
> For perfectly bubble-free tires you can degas the mixed silicone in a vacuum chamber for 2–3 minutes before pouring (see the BOM) — slow, thorough mixing already gets you most of the way there.

### Assembly

Because the tire is cast *around* the hub, there is no separate assembly step — the wheel comes out of the mold ready to mount. If you ever need to re-tire a good hub, either:

- **Recast in place:** drop the used hub back into the mold and pour new silicone around it, or
- **Press-fit spare tires:** cast a tire-only puck and press in a freshly printed hub (light interference fit + keying).

## Mounting to your robot

- **3 mm N20-style shafts (mini sumo):** the JSumo JS2622 aluminum rim has a 3 mm bore with an M4 tapped setscrew — clamp on the shaft's flat with a drop of medium threadlocker.
- **4 mm shafts (20 mm+ gearmotors, beetleweight drivetrains):** use the 4 mm bore variant and clamp on the motor's shaft flat.
- Torque the grub screw against the flat, not the shaft diameter, and re-check tightness after your first few hits — impacts back screws out.

## Tuning & maintenance

### Durometer cheat sheet

| Silicone hardness | Character | Best for |
| --- | --- | --- |
| ~00-30 to 20A | Very soft, sticky | Maximum-grip mini sumo, slow pushers |
| ~25–35A | Balanced grip + wear | General mini sumo & beetle drive |
| ~40–50A | Firm, durable | Fast beetles, rough arenas, longer life |

### Care

- **Wipe tires with IPA before every match** — dust and arena grit are grip killers.
- Rotate wheels between matches to even out wear.
- If the tread glazes (shiny, low-grip), a couple of light passes with fine sandpaper restores the surface.
- Store away from UV and direct sunlight to prevent discoloration and slow hardening.

## Measured performance

<!-- EDIT: Fill in your own traction-test numbers here, or delete this section until you have data. -->

| Surface | Static friction coefficient (µs, measured) | Notes |
| --- | --- | --- |
| Corian-style sumo board | — | |
| Painted steel arena floor | — | |
| Aluminum weapon arena | — | |

*Method: robot weight × gravity vs. pull force at first slip, three-run average.*

## Troubleshooting

| Symptom | Likely cause | Fix |
| --- | --- | --- |
| Bubbles in tread | No degassing / poured too fast | Degas the mix; pour thin and high |
| Tire stayed tacky or never cured | Inhibition (resin, wrong release agent, off-ratio mix) | Use platinum-safe release; re-measure the ratio; avoid SLA molds |
| Tire spins on hub | Keying too shallow or oily hub | Wipe hub with IPA before casting; deepen serrations in CAD |
| Wheel wobbles | Mold halves misaligned | Assemble mold with alignment pins fully seated |
| Grip fades after minutes | Tread glazing or heat buildup | Lightly sand; step up one durometer |

## FAQ

**Silicon or silicone?**
Silicone. The name belongs to the project — the tire material is platinum-cure silicone rubber.

**How long do the tires last?**
With 25–35A silicone and IPA cleaning, expect many events in mini sumo. Beetles chew tires faster depending on spin-outs and arena grit. Recasting is cheap, so treat tires as consumables.

**Why not just print TPU?**
TPU is a great start, but layer lines, moisture sensitivity, and a limited durometer range cap its grip. Cast silicone gives a seamless tread and any hardness you want.

**Can I run these on brushless direct drive?**
Yes — generate a hub with your motor's bore and bolt pattern and cast as usual.

**Do they mark the arena?**
Very soft compounds can; 30A and firmer generally don't. Always test on the event's surface first.

## Roadmap

- [ ] Fully parametric OpenSCAD generator (diameter × width × bore, durometer embossed on the hub)
- [ ] 50 mm "max-legal" mini sumo variant
- [ ] Hex-bore hub for direct gearbox output mounting
- [ ] Colored silicone lineup (pigment tests)
- [ ] Traction test jig and published µs dataset

## Contributing

Issues, forks, and PRs are welcome — especially traction data from different arenas. If you build a variant, open an issue with photos plus your print and silicone settings so it can be added to a community builds section.

## License

**All rights reserved.** See [`LICENSE`](LICENSE) for the full notice. The documentation, hardware design files, and images may not be copied, redistributed, or used to create derivative works without prior written permission — reach out if you'd like to build on this project.

## Acknowledgments

- The mini sumo and combat robotics community, for decades of accumulated tire lore.
- Everyone who ever lost a match to a grippier wheel — this project exists because of you.

## Gallery

<!-- EDIT: Drop photos into docs/images/ and uncomment the table below. -->
<!--
| Mini sumo build | Beetleweight build | Mold & fresh casting |
| --- | --- | --- |
| ![](docs/images/minisumo.png) | ![](docs/images/beetle.png) | ![](docs/images/mold.png) |
-->

---

<div align="center">

**Built to hook up.** 

</div>