# LPS Bill of Materials (NFPA 780 cross-referenced)

Exhaustive equipment list for a mast / overhead-ground-wire (catenary) lightning protection installation as modelled by this project (`masts.csv`, `catenaries.csv`, `rods.csv`), with the NFPA 780 section that governs each item.

## 0. Read this first

- **Edition.** Section numbers below are **NFPA 780-2026**. For **2020**, Chapter 4 sections from 4.5 onward are one number higher (2026 `4.12` grounding electrodes = 2020 `4.13`; 2026 `4.5.4` overhead ground wires = 2020 `4.6.4`; 2026 `4.15` bonding distance = 2020 `4.16`). Sections 4.1-4.4 and Chapters 1-3 are unchanged. The 2023 edition was not checked. Use the edition your AHJ / contract adopted.
- **Verification status.** The standard is paywalled and was not read directly. Numbers marked **(verify)** were not confirmed against a secondary source. Everything else was cross-checked against a published 2026 / 2020 clause summary. Check every row against your licensed copy before it goes in a submittal.
- **Listed parts.** Where listed or labeled parts exist, they must be used and installed within their listing (**§1.3.1, §1.3.2**). In practice this means UL 96 (components), UL 96A (installation), UL 467 (grounding/bonding equipment) and LPI 175 (installer practice).
- **Not in NFPA 780.** No earth-resistance target (NFPA 780 prescribes electrodes instead; this project's 25 ohm default comes from NEC 250.53(A)(2)). No structural, wind or ice design of masts, guys or catenary spans (use ASCE 7, TIA-222, NESC or a PE).
- **Excluded technologies.** Early streamer emission and charge dissipation devices are outside the standard (**§1.1.3**).

## 1. Design basis that drives the BOM

| Parameter | Value | NFPA 780 |
|---|---|---|
| Rolling-sphere radius, ordinary structures | <= 150 ft (45 m) | §4.7.3.1.4 |
| Rolling-sphere radius, flammable vapors / liquids | <= 100 ft (30 m) | §7.3.2 |
| Rolling-sphere radius, explosives (masts and catenaries inherit it) | 100 ft (30 m) | §8.2.1, §8.3.3-8.3.5 |
| Material class | Class I <= 75 ft; Class II > 75 ft | §4.1.1.1.1, §4.1.1.1.2, §4.1.1.2-4.1.1.4 |
| Masts / OHGW are strike termination devices | Yes | §4.5.1.1 |
| Isolated mast / wire standoff from structure | Sideflash separation calc | §4.5.5 (eq. 4.5.5.1, 4.5.5.2) |

If the structures hold explosives or flammables, Chapters 7 / 8 add to Chapter 4 and change the sphere radius, electrode list, test intervals and records (see section 14).

## 2. NFPA 780-2026 section map (Chapter 4)

| Section | Topic |
|---|---|
| 4.1 | Materials, Class I / II tables (Tables 4.1.1.1.1, 4.1.1.1.2) |
| 4.2 | Corrosion protection, aluminum keep-away (4.2.2.3.1), copper runoff (4.2.4) |
| 4.3 | Dissimilar metals, paint/masonry limit (4.3.3), bimetallic connectors (4.3.4.3) |
| 4.4 | Mechanical damage / displacement, metal sleeves (4.4.2.1, 4.4.2.2) |
| 4.5 | Strike termination devices: air terminals (4.5.2), masts (4.5.3), overhead ground wires (4.5.4), sideflash separation (4.5.5) |
| 4.6 | Roof placement of devices, rooftop objects (4.6.11, 4.6.12) |
| 4.7 | Zones of protection (angle, rolling sphere) |
| 4.8 | Conductors: roof, cross-run (4.8.8), down conductors (4.8.10) |
| 4.9-4.10 | Conductor fasteners / structural metal as conductors **(verify numbering)** |
| 4.11 | Connectors |
| 4.12 | Grounding electrodes |
| 4.13 | Common bonding of grounded systems |
| 4.14 | Potential equalization (ground, roof, intermediate levels) |
| 4.15 | Bonding of metal bodies, bonding distance, fences |
| 4.17 | Reinforcing steel interconnection (referenced by 4.14.3.2) **(verify title)** |
| 4.19 | Surge protection |

## 3. Strike termination - air terminals

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 3.1 | Air terminal (Franklin rod) | Class I: solid copper >= 3/8 in dia; Class II: solid copper >= 1/2 in dia (aluminum / tubular options per table). Tip >= 10 in above what it protects. Project default 0.61 m (2 ft). | 1 per mast (`masts.csv`), plus roof devices | §4.1.1.1.1/2, §4.5.2.1 |
| 3.2 | Terminal bracing kit | Required for terminals > 24 in; brace at or above mid-height. A terminal longer than the 0.61 m default needs this. | Per terminal > 24 in | §4.5.2.2.2 |
| 3.3 | Terminal-to-mast adapter / threaded base | Mechanically secures terminal so it cannot tip or shift | 1 per terminal | §4.5.2.2.1 |
| 3.4 | Ornaments (if any) | Free-standing, unbraced: <= 20 in² wind area; ball <= 5 in | As specified | §4.5.2.3 |
| 3.5 | Roof-mounted terminals, bases, adhesive / bolted / ridge / parapet supports | Only if buildings also use roof placement | Per roof layout | §4.6.2, §4.6.5, §4.6.11 |
| 3.6 | Terminals for rooftop equipment outside the zone | HVAC, vents, antennas outside the zone; thick metal >= 3/16 in is bonded instead | Per object | §4.6.11, §4.6.12 |

## 4. Masts (poles)

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 4.1 | Mast pole | Steel / galvanized steel, FRP or wood. Metal mast top >= 3/16 in or carries a terminal. **Nonmetallic mast always needs at least one terminal.** Structural design by others. | `masts.csv` rows; height = `height` | §4.5.3.3, §4.5.3.4 |
| 4.2 | Mast as down conductor (option) | Only if electrically continuous with wall >= 0.064 in; otherwise run a separate down conductor | Per design choice | §4.5.3.5 |
| 4.3 | Foundation (concrete pier / direct-embed) | Structural, not NFPA 780 | 1 per mast | Out of scope |
| 4.4 | Anchor bolts, base plate, leveling nuts, grout | Galvanized / stainless; if mast is the conductive path, base plate is part of the electrical path | 1 set per mast | §4.2, §4.3 (dissimilar metals) |
| 4.5 | Mast-base grounding lug / bonding pad | Main-size conductor termination to mast and foundation steel | 1+ per mast | §4.8, §4.11 |
| 4.6 | Standoff insulators / dielectric sections (isolated systems) | Only where isolated-system standoff cannot be met by distance | As designed | §4.5.5 |
| 4.7 | Aviation obstruction / marker lighting (if required) | By FAA / local code. Surge-protect every circuit. | Per mast | §4.19, Chapter 5 |

## 5. Overhead ground wire (catenary) and span hardware

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 5.1 | Overhead ground wire | Cross-section >= main conductor. Steel or stainless-steel cable: >= 1/2 in dia. Aluminum: as per class table. Typical: 7- or 19-strand copper (Class I >= 57,400 cir. mil, Class II >= 115,000 cir. mil) or galvanized / stainless / copper-clad steel strand (ASTM A363 or equivalent). | Chord length + sag + end wraps (`catenaries.csv`: `ax,ay,bx,by,sag_m`) | §4.5.4.5.1, §4.5.4.5.2 |
| 5.2 | Span tensioning hardware | Turnbuckles / in-line tensioners to hold the **calculated sag in every condition** (sag shrinks the zone of protection) | 1 per span end (min.) | §4.5.4.4 |
| 5.3 | Terminations: thimbles, wire-rope clips, preformed dead-ends, swaged or compression sleeves | Same metal family as the wire or bimetallic-rated; listed connector where one exists | 2 per span | §4.11, §4.3.4.3 |
| 5.4 | Attachment hardware at mast: clevis, shackle, eye bolt, saddle clamp, hot-dip galvanized or stainless | Must be electrically continuous to the mast / down conductor | 2 per span | §4.11 |
| 5.5 | Strain / dielectric insulators | Only if the wire is isolated from the mast and grounded elsewhere | As designed | §4.5.5 |
| 5.6 | Wire dampers / spacers / marker balls | Aeolian vibration, aviation visibility | Long spans | Out of scope |
| 5.7 | Down-conductor tap from wire (bond to ground at each end mast) | Main-size; each device needs two or more paths to ground | >= 2 per wire | §4.8, §4.8.10 |
| 5.8 | Sag chart / tension calc | Record in design file | 1 per span | §4.5.4.4 |

## 6. Guy wire system (guyed masts)

NFPA 780 has no dedicated "guy hardware" clause in Chapter 4. Treat every metallic guy as a metal body (§4.15) and check the guyed-structure rules in Chapter 5 **(verify subsection)**. Wind and ice loading is structural.

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 6.1 | Guy strand | Galvanized EHS steel (ASTM A475) or equivalent; 3 guys per level at 120 degrees typical | Per guy level | Ch. 5 **(verify)**, §4.15 |
| 6.2 | Guy anchors | Screw, plate, helical, or concrete deadman; rated to design load | 1 per guy | Out of scope |
| 6.3 | Anchor rod, thimble eye, hot-dip galvanized | Corrosion-compatible with strand | 1 per guy | §4.3 |
| 6.4 | Preformed guy grips or wire-rope clips with thimbles | Terminations at mast and anchor | 2 per guy | §4.11 |
| 6.5 | Turnbuckles (take-up) | Locked / jam-nutted | 1 per guy | - |
| 6.6 | Mid-guy fiberglass strain insulators (optional) | Break up resonant lengths; limits sideflash path to structure | Per design | §4.5.5 |
| 6.7 | Guy bonding jumpers + clamps | Bond guy at mast end and at anchor to the grounding system, or confirm it is exempt by the bonding-distance calc | 1-2 per guy | §4.15.2, §4.15.3 **(verify)** |
| 6.8 | Anchor-side ground rod / ring bond | Where guy is grounded at anchor | Per guy | §4.12.2, §4.12.4 |
| 6.9 | Guy guards / marker sleeves (PVC) | Personnel and equipment safety. Nonmetallic only, so they do not become a bonded metal body. | 1 per guy | §4.4 |

## 7. Conductors

Class I vs II sizing comes from Tables 4.1.1.1.1 / 4.1.1.1.2 (§4.1.1.1).

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 7.1 | Main-size conductor (roof, down, ring, loop) | Copper (Class I >= 57,400 cir. mil, Class II >= 115,000 cir. mil) or aluminum equivalent. Listed lightning conductor; bare AWG wire usually is **not** listed. | Down-conductor length + roof runs + ring | §4.1.1.1, §4.8, A.4.1.1.1 |
| 7.2 | Down conductors | >= 2 per structure; extra one per 100 ft of perimeter above 250 ft. Each strike device has >= 2 paths to ground. | Per structure | §4.8.10, §4.8.10.1 |
| 7.3 | Roof / cross-run conductors | Interior cross-runs tied to perimeter <= 150 ft apart | Per roof | §4.8.8.1, §4.8.8.2 |
| 7.4 | Bonding conductor (secondary-size) | Smaller than main; for bonding metal bodies per table | Per bond | §4.1.1.1, §4.15 |
| 7.5 | Loop conductors (equalization) | Main-size; roof level > 60 ft; intermediate loops at <= 200 ft (bonded rebar) or <= 60 ft (other) | Tall structures | §4.14.2-4.14.4 |
| 7.6 | Ground loop conductor | Main-size, within 12 ft vertically of base, > 60 ft structures | Per structure | §4.13.2 |
| 7.7 | Corrosion-resistant conductor (tinned / lead-covered / stainless) | Corrosive soil or atmosphere (stack tops, coastal) | Per site | §4.2, §4.12.1.6, §6.3 |
| 7.8 | Aluminum-specific keep-away | Aluminum not within 18 in of soil, vegetative roof soil, planters; not on copper roofing or in contact with masonry / paint | Where aluminum used | §4.2.2.3.1, §4.2.4, §4.3.3 |

## 8. Fastening, routing and mechanical protection

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 8.1 | Conductor fasteners / cable supports | Compatible metal; fixed per spacing rules (typical <= 3 ft) **(verify)** | Per conductor length | §4.9-4.10 **(verify)** |
| 8.2 | Conductor guards, nonmetallic (PVC / HDPE) | Down conductors where subject to damage (ground level, ~8 ft up) | Per exposed run | §4.4 |
| 8.3 | Metal sleeves / ferrous conduit around a conductor | Short sleeves: bond at one end or none; longer ferrous sleeves bonded at both ends **(verify)**. Metal conduit is a bonded path, not a replacement for the conductor. | Where used | §4.4.2.1, §4.4.2.2 |
| 8.4 | Bonding bushings, grounding bushings, lay-in lugs | Bond ends of a metal sleeve or conduit to the conductor | 2 per metal sleeve | §4.4.2, §4.11 |
| 8.5 | Expansion / flexible jumpers | Across building expansion joints and flexible couplings | Per joint | §4.8, §4.15 |
| 8.6 | Bend control | Radius / angle limits for conductors (no sharp bends; 8 in minimum radius, 90-degree maximum, **verify**) | - | §4.8 **(verify)** |
| 8.7 | Anti-oxidant compound, conductive adhesive, sealant (roof penetrations) | Dissimilar metals, bedrock-fixing every 3 ft | Per joint | §4.3, §4.12.8.1.3 |
| 8.8 | Through-roof / through-wall passthroughs | Sealed, corrosion-compatible | Per penetration | §4.4 |

## 9. Connectors and splices

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 9.1 | Bolted or clamp connectors (UL 96 listed, Class I / II rated) | Cable-to-cable, tap, splice, end-to-end; minimum contact area per listing | Per joint | §4.11, §1.3.1 |
| 9.2 | Compression / high-compression connectors | Permanent; allowed at ground connections | Per joint | §4.11, §4.12.1.4 |
| 9.3 | Exothermic weld kits (molds, powder cartridges, ignition) | Named connection type in 2026. Cable-to-rod, cable-to-steel, cable-to-cable. | Per weld | §4.11, §4.12.1.4 |
| 9.4 | Brazed joints (silver brazing kit) | Allowed permanent connection | If used | §4.12.1.4 |
| 9.5 | Bimetallic (Cu-Al) connectors | Required wherever copper meets aluminum | Per transition | §4.3.4.3 |
| 9.6 | Connector for rooftop thick metal | Main-size conductor, >= 2 paths, contact >= 3 in² (or 1 1/2 in along a round surface) | Per object | §4.6.11.1 |
| 9.7 | Equipotential bonding connectors | Minimum contact area per 4.15.6.2 | Per bond | §4.15.6.2 |
| 9.8 | Cable-to-structural-steel clamps / beam clamps / weld studs | Steel columns as down paths | Per tap | §4.10 **(verify)**, §4.11 |
| 9.9 | End caps / cable-end terminals, lugs, ferrules | Stranded cable terminations | As needed | §4.11 |

Only bolting, brazing, welding or a listed high-compression connector qualify for the down-conductor-to-electrode joint (§4.12.1.4).

## 10. Grounding electrodes

Every down conductor ends at an electrode (§4.12.1.1). Buried piping, the service rod or telecom rods **cannot** replace lightning electrodes (§4.12.1.3); they are bonded to the system (§4.13).

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 10.1 | Ground rod | Copper, copper-clad steel or stainless; >= 1/2 in dia x 8 ft; **driven >= 10 ft (3 m) into earth** (project uses 3.05 m). Zinc-coated rods are not covered. Listed (UL 467). | `rods.csv` rows | §4.12.2.1-4.12.2.4 |
| 10.2 | Rod sections + threaded couplers + drive stud / driving head | For sections joined to reach depth; keeps threads intact | As needed | §4.12.2.4.1 |
| 10.3 | Rod-to-conductor connection | Exothermic weld, brazed, bolted listed clamp or high-compression connector | 1 per rod | §4.12.1.4 |
| 10.4 | Multiple-rod spacing | >= sum of the two rods' driven depths where practicable | Layout | §4.12.2.5 |
| 10.5 | Ground ring electrode | Main-size conductor (or equal / larger grounding conductor); >= 18 in deep in earth, or in a qualifying footing. Explosives: bare copper >= 105,000 cir. mil. | Building perimeter + 2 ft offset | §4.12.4.1, §4.12.4.2, §8.4.2.4 |
| 10.6 | Radials | One or more main-size conductors, each >= 12 ft, each in its own trench, >= 18 in deep | Per down conductor | §4.12.5.1-4.12.5.3 |
| 10.7 | Ground plate | >= 0.032 in thick, >= 2 ft² surface (1 ft² with both faces in soil), >= 18 in deep | Where used | §4.12.6.1, §4.12.6.2 |
| 10.8 | Concrete-encased electrode (new construction) | >= 20 ft bare main-size copper, or >= 20 ft bonded rebar >= 1/2 in (no resistive coating), under >= 2 in concrete, **with test point** | New footings | §4.12.3.1-4.12.3.4 |
| 10.9 | Electrode combinations | Any combination of the five types | - | §4.12.7 |
| 10.10 | Soil / site relief hardware | Shallow topsoil < 18 in: bury at topsoil depth, 24 in from foundation; bedrock: radials >= 12 ft laid on rock, fixed every 3 ft with nails, conductive adhesive or cement; sand/gravel: multiple electrodes | Site specific | §4.12.8.1-4.12.8.3 |
| 10.11 | Ground-enhancing material, bentonite / conductive backfill, soil analysis | Optional; stainless electrodes need a soil analysis first | Poor soil | §4.12.1.6, A.4.12.1.6 |
| 10.12 | Inspection / test well (hand-hole) with cover, labeled | Access to each rod connection for testing; mandatory test point for concrete-encased | 1 per rod (or per group) | §4.12.3.4, A.4.12.1, D.1.2 |
| 10.13 | Below-frost-line installation | Where practicable | - | §4.12.1.5 |

## 11. Common bonding to other systems (the "ground it all together" items)

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 11.1 | Main-size bond to electrical service grounding electrode system | Interconnect lightning, service, comm and antenna electrodes; NEC 250.106 requires the same | >= 1 | §4.13.3, §4.13.5, NEC 250.106 |
| 11.2 | Common bonding point (ground bar / busbar) | If one accessible point exists, one main-size conductor to it | 1 | §4.13.5 |
| 11.3 | Underground metal piping bond (water service, well casing <= 25 ft, gas, underground conduits, buried LP gas) | Bond within 12 ft vertically of base; clamp listed for the pipe | Per service | §4.13.1, §4.13.4.1 |
| 11.4 | Bridging conductors across plastic pipe sections | Main-size | Per break | §4.13.4.2 |
| 11.5 | Gas line bond | Downstream of meter, customer side; CSST: short bonds near entrance and appliances, no clamp on tubing or jacket | 1 | §4.13.6.1, A.4.13.6.1 |
| 11.6 | Structural steel frame bond | Continuous frame; connect at base | Per column bond | §4.13.6.1 |
| 11.7 | Isolating spark gap (where direct bond is not allowed or galvanic issue) | Listed, rated for lightning | As permitted | §4.13.6.2 |
| 11.8 | Antenna / mast / comm mast grounding | Part of common bond | Per antenna | §4.13.3 |
| 11.9 | Roof-level and intermediate-level loops (tall structures) | See 7.5 | - | §4.14 |

## 12. Bonding of metal bodies - the alternate-path items (conduit, raceways, etc.)

The bonding distance `D` decides what must be bonded:

$$D = \frac{l}{6n}\,K_m$$

- `l` is conductor length from the bond to the nearest electrode (2020 used vertical height `h`).
- `n` is 1, 1.5 or 2.25 by number of down conductors >= 25 ft apart within 100 ft.
- `K_m` is 1.0 through air and 0.50 through dense material.

Metal inside `D` is bonded; metal beyond `D` is isolated (§4.15.2.4). No bond is needed where measured dc resistance to the nearest lightning component is < 200 milliohms (§4.15.2.3). Equations: §4.15.2.5.1 (> 40 ft), §4.15.2.6.1 (<= 40 ft).

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 12.1 | Bonds to grounded metal bodies in `D`: metal conduit / EMT / rigid, cable tray, ducts, handrails, ladders, gutters, roof drains, HVAC, railings, window frames that bridge the gap | Bonding conductor + listed connector; bond both ends where > 60 ft vertical (steel-framed / bonded rebar) | Per body | §4.15.1, §4.15.2.1, §4.15.2.2, §4.15.4 |
| 12.2 | Conduit bonding hardware: grounding bushings, bonding jumpers, conduit clamps, lay-in lugs, grounding locknuts | Bond each metal raceway where it enters or leaves the structure and at the lightning conductor crossing / parallel | Per raceway | §4.15, §4.4.2 |
| 12.3 | Metal roof bodies parallel to a main conductor within `D` | Bond at intervals averaging <= 100 ft | Per run | §4.15.3.2 |
| 12.4 | Metal bodies crossing a main conductor | Bond at crossing | Per crossing | §4.15.3.3 |
| 12.5 | Roof metal > 60 ft horizontal | Bond near both ends | Per run | §4.15.3.1 |
| 12.6 | Metal body bonded at one end only | Check the far end against `D` | Per body | §4.15.2.1 |
| 12.7 | Vertical branches > 12 ft | Check against `D` | Per branch | §4.15.2.2 |
| 12.8 | Metal fence within 6 ft (1.8 m) of protected structure | Ground to structure's system; gate posts get their own electrode | Per fence line + per gate | §4.15.5.1.1, §4.15.5.3.1 |
| 12.9 | Reinforcing steel interconnection | Bonded rebar interconnected | Per structure | §4.17.3 **(verify)** |
| 12.10 | Bonding test records (< 200 milliohm proof) | Low-resistance ohmmeter | Per bond group | §4.15.2.3, A.4.13.6.1 |

## 13. Surge protection

| # | Item | Specification / notes | Qty basis | NFPA 780 |
|---|---|---|---|---|
| 13.1 | SPD, <= 1,000 V, listed Type 1 or 2, at each power service | >= 20 kA nominal discharge per phase at service entrance; short-circuit rating marked; visible status indicator; accessible | Per service entrance | §4.19.2.1.1, §4.19.2.6, §4.19.2.8, §4.19.2.14, §4.19.2.15 |
| 13.2 | SPD grounding electrode / conductor | Per NFPA 70; leads short, no needless bends | Per SPD | §4.19.2.11.2, §4.19.2.12 |
| 13.3 | Surge arrester > 1,000 V | >= 125 % MCOV duty cycle; leads >= 6 AWG Cu / 4 AWG Al | Per MV service | §4.19.3.2, §4.19.3.7 |
| 13.4 | Signal / data / comm surge protectors | >= 10 kA Imax per line entering or leaving; never grounded through a down conductor | Per line | §4.19.4.1, §4.19.4.3, §4.19.4.7 |
| 13.5 | Mast-mounted equipment protection (lighting, cameras, antennas) | Protect every circuit to masts | Per circuit | §4.19 |

## 14. Special-structure add-ons (Chapters 7, 8)

| # | Item | Notes | NFPA 780 |
|---|---|---|---|
| 14.1 | 100 ft-sphere re-layout (masts / catenaries) | Re-run the solver at the smaller radius | §7.3.2, §8.2.1, §8.3.3-8.3.5 |
| 14.2 | Explosives: ground ring bare copper >= 105,000 cir. mil, specified electrode list | | §8.4.2 |
| 14.3 | Explosives: written maintenance / inspection plan | | §8.8 |
| 14.4 | Explosives: visual every 7 months; electrical tests every 14 months; any single bonded object <= 200 milliohm | | §8.9.6, §8.9.7, §8.9.7.1 |
| 14.5 | Explosives: three-point fall-of-potential test, instruments for earth testing, calibrated; clamp-on meter only if stakes impossible and AHJ allows | | §8.9.7.4-8.9.7.6 |
| 14.6 | Floating-roof tank bypass conductors <= 0.03 ohm | | §7.6.2.2.2 |

## 15. Test, inspection, documentation and consumables

| # | Item | Notes | NFPA 780 |
|---|---|---|---|
| 15.1 | Earth resistance tester (three-point fall of potential) + stakes + leads | Potential probe at ~62 % of current-probe distance; Annex E example: 120 ft / 75 ft | Annex E (E.1.3, E.1.4) |
| 15.2 | Low-resistance ohmmeter (bond continuity, 200 milliohm check) | | §4.15.2.3, D.1.3 |
| 15.3 | Clamp-on ground tester (secondary) | | §8.9.7.6.2 |
| 15.4 | Ground-test-well labels, tags, record forms | Keep baseline readings, test-point locations on as-builts | D.1.4, D.1.5, A.1.6 |
| 15.5 | As-built drawings with test points | Required baseline for future inspections | A.1.6 |
| 15.6 | Maintenance guidelines to owner | | §1.6 |
| 15.7 | Annual inspection / compliance test (unless AHJ sets another interval) | Annex D: visual yearly, complete 3-5 years | §1.7, D.1.1.2 |
| 15.8 | Installer certification / third-party inspection (AHJ) | | §1.5.2, §1.5.3 |
| 15.9 | Annex L risk assessment record | Informative; justifies the system | Annex L |
| 15.10 | Installation consumables and tools | Exothermic molds + cartridges, driving tools (rod driver, sledge hammer), trenching, compaction tool for backfill, cable cutters, crimp dies, torque wrench, PPE | §4.12.2.4 (compaction), §4.12.1.4 |

## 16. Quantity drivers from this project's outputs

| BOM line | Derived from |
|---|---|
| Masts, air terminals (3.1, 4.1) | Row count of `masts.csv` / `out_masts.csv`; `height`, `terminal_length_m`, `terminal_kind` |
| Terminal bracing (3.2) | Any `terminal_length_m` > 0.61 (24 in) |
| OHGW length (5.1) | Sum of chord `sqrt((bx-ax)^2+(by-ay)^2)` + sag allowance from `catenaries.csv` / `wires.csv` + end wraps |
| Span hardware (5.2-5.4) | 2 ends x row count of `catenaries.csv` |
| Down conductors (7.2) | >= 2 per structure; mast and wire end points from `masts.csv` / `catenaries.csv`; length = `tip_z` - `base_z` + horizontal run to the nearest electrode |
| Ground rods (10.1) | Row count of `rods.csv`; `length_m` of 3.05 m = 10 ft (meets §4.12.2.4.1 driven depth) |
| Ground ring (10.5) | Building footprint perimeter (`footprints.csv`) offset outward |
| Bonding (sections 11-12) | Per-building site survey; no CSV input yet (utilities, conduits, roof metal) |

## 17. Open items to resolve before procurement

1. Confirm the governing NFPA 780 edition and any AHJ / insurer amendments.
2. Confirm Class I vs Class II per structure height (75 ft).
3. Confirm Chapter 7 / 8 applicability (changes sphere radius to 100 ft).
4. Verify every row marked **(verify)** against the licensed text (fasteners and structural-metal section numbers, bend limits, guy-wire requirements, conduit sleeve bonding, rebar section).
5. Structural / wind / ice design of masts, guys and catenary spans by a qualified engineer.
6. Soil resistivity survey and, if the AHJ or specification sets a resistance target, record where it came from (NFPA 780 itself sets none).
7. Sideflash separation checks (§4.5.5) of each mast and OHGW to the structure, and §4.15.2 checks of each nearby metal body.
