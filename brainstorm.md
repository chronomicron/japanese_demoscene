# Japanese Demoscene — Brainstorm

This file is a living collection of ideas, possibilities, technical options, and half-formed thoughts.
Nothing here is committed to the final design until it is deliberately moved into the project definition (README) or into actual code.

Ideas can be expanded, refined, combined, or later pruned. Keep them even if they feel rough.

---

## Technology & Platform

### Target platforms
- Primary goal: standalone Windows `.exe`
- Strong preference for also running on Linux (native)
- Ideal: also compilable / runnable on macOS
- Question: pure C + lightweight cross-platform layer, or accept some platform-specific paths?

### Possible graphics approaches
- OpenGL (classic demoscene feel, good cross-platform story with care)
- Vulkan (more modern, heavier setup)
- Software framebuffer only (maximum control + tiny size, but limited)
- OpenGL + GLSL shaders for procedural effects
- Ray marching / SDF heavy approach
- Hybrid: CPU procedural generation feeding GPU

### Audio
- Procedural / synthesizer-based (keeps size small)
- Compact tracker-style or chiptune
- Traditional Japanese timbres mixed with cyberpunk / industrial
- Synchronization to visual events is important later

### Build / toolchain thoughts
- GCC / Clang
- Cross-compilation from Linux Mint to Windows
- Minimal dependencies
- Single binary preferred

---

## Visual & Narrative Ideas

### Map concepts (procedural / mathematical)
- Outline of the four main Japanese islands (Hokkaido, Honshu, Shikoku, Kyushu) generated mathematically, not from a bitmap.
- Alternative: stylized map of Tokyo with the Imperial Palace as the clear center point.
  - Yamanote line as a visible loop / circuit.
  - A few key districts or landmarks represented abstractly (Shinjuku, Shibuya, Akihabara, Tokyo Station, etc.).
  - Could serve as a transitional or "establishing" scene, or as a geometric structure that later breaks apart into particles / neon city.
- Possible uses:
  - Silent opening map that slowly fills with light / data
  - Map that folds, unfolds, or extrudes into 3D
  - Map that becomes the floor plan of a larger cyberpunk environment
  - Map lines that turn into data streams or particle paths

### Traditional → Cyberpunk transformation ideas
- Seigaiha (wave pattern) → ocean → digital waves → data ocean
- Asanoha lattice → 3D structure → neon scaffolding
- Kamon / family crest → particle system → final emblem
- Ink brush stroke that spreads, then digitizes
- Torii gates forming an infinite tunnel
- Rising sun that becomes a cyberpunk sun / holographic disk
- Cherry blossoms that turn into digital particles or kanji fragments
- Emakimono (scroll) camera movement that reveals changing eras

### Scene / structure seeds
- Opening: pure black → single ink drop or brush stroke
- Pattern awakening that gains depth and eventually fractures
- Transition moment where traditional geometry "glitches" into wireframe / neon
- Dense procedural city sequence
- Peak of synchronized complexity
- Return to a single pure symbol (kamon / seal / rising sun) then fade to black

### Atmosphere & contrast
- Silence vs noise
- Ink vs neon
- Flat pattern vs deep 3D space
- Organic curves vs hard geometric / digital forms
- Calm traditional motifs that slowly become overwhelming technological density

---

## Specific Effect Seeds

- Procedural seigaiha ocean that can be flown over or through
- Rotating kamon constructed purely from particles
- Hanko (seal) that stamps with an ink explosion / shockwave
- Infinite neon torii tunnel
- Digital rain made of Japanese characters / kana / kanji fragments
- Wireframe pagoda that can be orbited or entered
- Ray-marched Japanese architectural forms
- CRT / scanline presentation layer that can be turned on/off or intensified
- Glitch that affects only traditional patterns first, then the whole scene

---

## Open Questions

- How important is true cross-platform (Win + Linux + macOS) versus focusing on a polished Windows .exe first?
- Preferred minimum OpenGL version / feature set?
- How early should audio experiments begin?
- Should the map idea be a full scene, a transitional element, or a recurring motif?
- Any hard size target (even soft) we want to keep in mind from the beginning?

---

## Narrative / Script Seeds

### Historical arc: Edo → Meiji → Modern Tokyo → Night Drive
A possible overall visual story spine:

1. **Edo Japan opening**
   - Procedural map of Japan (four main islands) rendered in an Edo-period visual language.
   - Regional / domain family kamon (crests) appear over or near the areas they historically belong to.
   - Flying / gliding camera over the map.
   - Other Edo identifiers: ink, woodblock texture feel, calm composition, possible silhouettes of castles, torii, or traditional roofs generated procedurally.
   - Mood: quiet, historical, almost contemplative.

2. **Transformation through Meiji**
   - The map and traditional elements begin to modernize.
   - Geometry hardens, lines straighten, industrial / early-modern forms appear.
   - Visual language shifts from ink/woodblock toward early industrial / Western-influenced Meiji aesthetics while remaining Japanese.

3. **Arrival in modern / Neo-Tokyo**
   - Full procedural Tokyo.
   - Train network becomes visible (Yamanote loop and/or other major lines as geometric structures or light paths).
   - City density increases, neon appears, vertical scale grows.

4. **Climax / ending: Night drive**
   - Camera drops into a first-person or low third-person night drive along a Tokyo highway / elevated expressway.
   - Skyscrapers, neon signs, reflections, motion blur, speed.
   - Strong "Neo Tokyo / Akira / 80s cyberpunk night drive" atmosphere.
   - Audio direction: 80s Japanese City Pop / J-pop feeling, but realized as 8-bit / chiptune / compact MIDI-style synthesis rather than full sampled tracks (keeps size under control and stays demoscene-authentic).

This arc gives a clear beginning (historical Japan), middle (transformation + modern city), and ending (emotional night drive payoff). It also naturally incorporates the map + kamon ideas and the desire for an 80s Japanese night-drive mood.

Possible shorter versions or variations:
- Compress the historical part and spend more time in the night drive.
- Use the map primarily as an establishing / title sequence rather than a long scene.
- Let kamon dissolve into the neon city or reappear as final logo.

---

## Notes from conversations

- 2026-09-09: Project still in pure planning / technology selection stage. Only README existed. Brainstorm.md created to capture free-form ideas separately from the formal project definition.
- Map of Japan (four main islands) or Tokyo-centric map (Imperial Palace + Yamanote) suggested as mathematical/procedural element.
- 2026-09-10: Strong narrative interest in Edo-period Japan map with regional kamon → Meiji transformation → modern Tokyo train network → night highway drive in Neo-Tokyo atmosphere. Audio leaning toward 80s J-pop / City Pop feeling expressed through 8-bit / MIDI-style sound.
