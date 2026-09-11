# Japanese Demoscene — Design Document

This document translates the vision in `README.md` and the ideas in `brainstorm.md`
into a working narrative and scene structure. It is a living document — scenes here
can be cut, merged, reordered, or expanded as prototyping reveals what's actually
achievable and what looks good.

Nothing here is final. This is the current best guess at a shape for the demo.

---

## Creative Thesis

The demo is a compressed visual history of Japan, told without dialogue, moving
from myth to memory to the present — ending on a personal, emotional beat rather
than a technical one.

It is aimed at a Japanese audience roughly in their 40s–50s: someone who did not
live through the Edo period or the creation myths, but who *did* grow up with
Yakult delivery bicycles, matsuri lanterns, City Pop on the radio, and a Tokyo
skyline that kept climbing. The mythic and historical scenes exist to give the
demo weight and context; the Shōwa-era nostalgia section is the emotional core;
the night drive is the payoff.

**Structural spine:**

```
Myth (creation) → Myth (light returns) → Edo Japan → Shōwa nostalgia
   → Meiji/modernization → Neo-Tokyo peak → Night drive → Fade
```

**Recurring visual anchor:** Mount Fuji appears in every era, rendered in a style
appropriate to that era (ink silhouette → woodblock → flat cel-shade → wireframe
→ glitching neon hologram → distant glow). It is the one constant thread tying
the whole demo together, and it should be treated as a first-class recurring
asset in the codebase, not a one-off background element.

---

## Mythological Foundation

Japan's creation mythology (Kojiki / Nihon Shoki) gives the demo a natural cold
open. Two episodes are used here; both are visually well-suited to procedural
techniques already in scope for this project (fluid/ink simulation, raymarching,
particle systems, lighting).

### Episode 1 — Creation (Izanagi and Izanami)

The primordial deities Izanagi and Izanami stand on the floating bridge of
heaven and stir the primeval ocean with a jeweled spear (Ame-no-Nuboko). Brine
drips from the spear tip as it is withdrawn and congeals into the first island,
Onogoro.

- Visually: darkness, a single point of light/geometry (the spear tip),
  concentric ripples in a fluid-like surface, droplets that don't just fall but
  *accumulate* into landmass.
- Technique fit: SDF-based fluid/ripple simulation, or a simpler raymarched
  water surface with noise-based displacement. A single droplet forming solid
  ground is a compact, readable effect — good candidate for an early prototype.
- This is the literal birth of "Japan" as a place, so it earns being scene one.

*(Optional, likely cut for scope: Izanami's death, the underworld visit, and
Izanagi's purification ritual that produces Amaterasu, Tsukuyomi, and Susanoo.
Worth keeping in mind as a bridge if the demo runs long and needs a connective
scene between creation and the cave sequence — but not required.)*

### Episode 2 — Amaterasu and the Cave (Ama-no-Iwato)

After Susanoo's destructive rampage terrifies her, the sun goddess Amaterasu
hides in a cave, plunging the world into darkness. The assembled gods, guided
by Omoikane's plan, gather outside. Ame-no-Uzume dances wildly on an overturned
tub; the gods laugh; Amaterasu, curious, opens the cave enough to peer out and
catches her own reflected light in a mirror (Yata no Kagami) placed for her —
she is drawn out, and light returns to the world.

- Visually: total darkness → a single dancing figure (silhouette, minimal
  geometry) → firelight building around a gathering crowd → a mirror catching
  and amplifying light → sudden flood of brightness across the frame.
- Technique fit: this is naturally your first "peak" moment — many small
  elements (dancer, firelight, gathered figures, mirror flare) converging into
  one release. Good candidate for an early test of multi-system synchronization
  (light + geometry + camera) since it's a self-contained, low-geometry scene.
- Functions as the transition out of pure myth and into the "map of Japan"
  sequence — light returning to the world doubles as light returning to reveal
  the physical land.

---

## Historical Arc

### Edo Japan

- Procedural map of the four main islands (Hokkaido, Honshu, Shikoku, Kyushu),
  generated mathematically rather than traced from a bitmap.
- Regional kamon (family crests) appear over their historical domains as the
  camera glides across the map.
- Visual language: ink wash, woodblock-print texture, restrained motion, quiet
  pacing — a deliberate contrast to what follows.
- Mount Fuji appears here in a Hokusai-influenced woodblock silhouette style —
  the first "era skin" for the recurring Fuji motif.
- Possible additions: torii silhouettes, castle silhouettes, procedural roofline
  shapes, all kept flat and graphic rather than dimensional at this stage.

### Shōwa Nostalgia Interlude

This is the emotional heart of the demo and the section most directly aimed at
the target audience's own memory rather than history-book Japan. It should feel
warmer and more intimate than the scenes around it — a pause before the
technological escalation resumes.

Candidate imagery (procedurally stylized, not photoreal — think flat cel-shaded
or limited-palette illustration rendered in shader):

- A Yakult delivery lady cycling past a danchi (Shōwa-era apartment block),
  laundry lines and crisscrossing power cables overhead
- A dagashiya (retro candy shop) storefront, or a tofu-seller's horn implied
  through the scene's stillness
- A natsumatsuri (summer festival) street: paper lanterns, yukata silhouettes,
  a distant firework bloom, kingyo-sukui (goldfish scooping) stall
- An old CRT television with rabbit-ear antenna, briefly showing static or
  color bars — a possible literal frame-within-frame transition device
- Mount Fuji visible in the distance, rendered flat and cel-shaded — same
  mountain, new era, new style

This section is intentionally list-heavy right now because it's the richest
area for further brainstorming. Not everything here needs to make the final
cut — a small number of well-chosen, well-executed vignettes will read better
than a crowded montage.

### Meiji / Modernization Transition

- The map and architectural silhouettes from the Edo section begin to
  mechanize: lines straighten, curves give way to grids, ink texture gives way
  to harder edges.
- Fuji transitions here from cel-shaded to wireframe — the mountain becoming
  "structural" rather than pictorial.
- This scene is explicitly transitional and should be short — its job is to
  bridge nostalgia and hypermodernity, not to be a destination in itself.

### Neo-Tokyo Peak

- Full procedural cyberpunk Tokyo: dense skyline, neon signage, volumetric fog,
  reflections, the Yamanote line rendered as a visible light-loop or data path.
- Fuji appears here as a distant glitching, semi-holographic silhouette on the
  horizon — visible but no longer solid, echoing how the mountain has receded
  from daily experience into skyline backdrop.
- This is the visual and technical peak of the demo: multiple systems
  (particles, geometry, lighting, camera, music) should be synchronized and at
  maximum density here, per the README's Phase 5 goals.
- Digital rain, holographic kanji, and glitch effects belong here rather than
  earlier — they're the "fully digital" endpoint of the ink → pixel journey
  that starts in the Edo section.

### Night Drive Finale

- First-person or low third-person camera along a Tokyo elevated expressway at
  night: skyscrapers, neon reflections, motion blur, a strong sense of speed.
- Audio: 80s City Pop mood, deliberately realized in 8-bit/MIDI-style synthesis
  rather than sampled instruments, both for size reasons and for demoscene
  authenticity.
- Fuji makes its final appearance here — small, distant, glowing on the horizon
  through the car window — before the drive continues and the frame fades to
  black.
- This scene is the emotional payoff and should be given real time rather than
  rushed; it's the "reminiscence" beat the whole demo has been building toward.

---

## Design Principles Specific to This Arc

1. **Fuji is infrastructure, not decoration.** Plan its rendering as a reusable
   component early (parametrized silhouette/height-field that can be re-skinned
   per era) rather than redrawing it from scratch in every scene.
2. **The nostalgia section should feel handmade, not epic.** Resist the pull to
   make every scene bigger than the last — the Shōwa interlude earns its place
   by being quiet and specific, not by being technically impressive.
3. **Myth-to-history is a texture transition, not a hard cut.** Ink and
   woodblock textures should visibly persist a little into the Edo section
   before fully giving way to flatter graphic shapes, and again into Meiji.
4. **Digital elements (glitch, data rain, holographic kanji) are earned, not
   default.** They belong to the Meiji→Neo-Tokyo half of the demo. Introducing
   them too early undercuts the ink→pixel arc that's core to the concept.
5. **Scope discipline:** the candidate list above (especially in the Shōwa
   section) is intentionally larger than what the final demo needs. Before
   Phase 4 (scene sequencing) locks in, this list should be triaged into
   "must-have," "if time allows," and "cut" categories.

---

## Open Questions / Next Steps

- Which 3–5 items from the Shōwa nostalgia list are the true must-haves?
- Should the Izanagi/Izanami underworld/purification bridge scene be included,
  or is Creation → Cave a clean enough jump on its own?
- How literally should the CRT/television imagery be used as a transition
  device between sections (e.g., "changing the channel" from myth to Edo)?
- Rough time budget per section, once Phase 2 prototypes give a sense of how
  long each effect takes to read well on screen.
- Should regional kamon in the Edo map section be historically accurate to
  specific domains, or stylized/invented for visual variety?

---

## Relationship to README.md

This document expands the "Demo Structure" section of `README.md` with specific
narrative content. The six-stage structure in the README (Opening → Pattern
Awakening → Cybernetic Transition → Cyberpunk City → Peak → Resolution) still
holds as the *technical* shape of the demo; this document fills in *what
actually happens* within that shape. As the arc here solidifies, the README's
structure section should be revisited to stay in sync.
