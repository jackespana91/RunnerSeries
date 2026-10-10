# Runnerz city art finish brief

Status: production brief, 10 October 2026. The current game contains animated
geometry and city decoration, but the primitive models and authored surfaces
still need a substantial visual finish. The new surface and lighting foundation
below is an applied step toward this brief. Compilation and model boards do not
establish that the game looks finished through its gameplay camera.

## Applied foundation and prepared work

Five city material sheets have been generated with OpenAI image generation.
Unchanged native PNG masters are `art/masters/<city>-materials.png` for London,
New York, Rio, Buenos Aires and The Hood. Each 1536 × 1024 sheet contains six
512 × 512 material cells. Runtime copies are
`web/assets/<city>/materials.webp`, encoded at quality 90 without cropping,
resizing or redrawing. `tools/encode_city_materials.py` performs encoding with
ffmpeg; ordinary builds use the included WebP files without that dependency.

The integration uses
city atlases and merged panels on solid facades, selected roofs and paving;
obstacles retain their 3D geometry. Menu-cover wall substitutions in New York,
Rio and The Hood have been removed in favour of authored wall-art slots.

The rendering foundation now includes nearby soft sun shadows, city lighting,
exposure and outline settings, and lit atlas surfaces. Padded UVs and oriented
panels support the material placement. Build status is in
[VALIDATION.md](VALIDATION.md); no browser review or tests have been run for this
pass. Model form, character anatomy, textured hero hazards and convincing motion
still need the finishing work described below. No city is marked finished.

The separate `releases/Runnerz-Art-Finish-Pack.zip` is a handoff of **18 prepared,
unsubmitted enhancement jobs and 25 unchanged source/reference images** plus
this brief. `tools/package_art_finish.py` produces that pack. It contains no
completed Magnific enhancement. The generated material sheets and the prepared
source jobs are distinct work products; all 72 supplied originals remain
unchanged.

## Shared quality target

Use the supplied London art as the painted comic reference: confident contours,
painted shading, convincing fabric and worn surfaces, expressive adult
characters, and a clear runner silhouette. Keep the runner's face, proportions
and city hoodie colours. Give each city its own architecture, materials and
light while keeping a consistent level of finish.

Every obstacle remains a solid model with an appropriate animation. Better
images can guide modelling and supply textures; Magnific image enhancement
does not create geometry, a skeleton, skin weights or a dance animation.
Finish the visible shapes, UVs, painted materials, contact shadows and motion
together. Preserve lane rules, clearances, encounter timing and payouts.

## Sources and access

- The uploaded archives supplied **72 original visual files**, preserved in
  `web/assets`. Reuse those and suitable existing Higgsfield originals first.
- `newyork/cover.png`, `rio/cover.png`, `buenosaires/cover.png` and
  `hood/cover.png` were generated with OpenAI during this work. They are menu
  illustrations and colour references; they have not been enhanced by Magnific.
- The five city material sheets were generated with OpenAI during the current
  foundation pass. PNG masters are preserved in `art/masters/`; WebP runtime
  copies keep the same pixel dimensions and cell layout. They have not been
  enhanced by Magnific.
- The additional Higgsfield account library has **not been inspected**. A
  missing local source is an unresolved library search, not proof that new art
  needs generating. Prefer original downloads, alternate views, animation
  frames and any existing model or texture sources over browser thumbnails.
- Magnific is registered and enabled in the CLI, but no Magnific tool is
  callable in this chat and its authentication status is unknown. An unauthenticated
  endpoint returning HTTP 401 does not establish the CLI's login state. No
  Magnific enhancement has been performed.

Paths below are relative to `web/assets`. See [ASSET-SOURCES.md](ASSET-SOURCES.md)
for the received-file audit and provenance limits.

## Distinct city briefs

| City | Palette and light | Surfaces and architecture | Signature moving hazard | Available sources and unresolved gaps |
|---|---|---|---|---|
| **Buenos Aires — blue runner** | Warm cream and terracotta; La Boca red/blue/yellow; jacaranda violet in the avenue; warm sun with cool shaded streets | Painted corrugated metal and balconies in La Boca; aged plaster, stone, ironwork and café tiles in San Telmo; more formal stone fronts and trees on the avenue. Hand-painted fileteado accents with readable Spanish lettering | Tango couple: connected embrace, clear weight transfers, coordinated walk/pivot/turn, grounded shoes and a dress that follows the movement | `buenosaires/tango.webp`, `dogwalker.webp`, `moto.webp`; OpenAI `cover.png` for broad colour reference. Current Canvas atlas and meshes are working layout. Higgsfield façade originals, texture sources, dancer views and motion references remain uninspected |
| **London — orange runner** | Brick reds, charcoal, muted teal and bus red; soft cool daylight with warm shop interiors | East London brick, estate concrete, glazed tiles, patched tarmac, shop shutters and painted murals; preserve the existing local signage | Delivery cyclist: believable seated pose, hands on bars, pedalling and correctly rolling wheels, with clothing and delivery bag responding to movement | Strongest received set: `london/cover.webp`, `skyline.webp`, `rider.webp`, `bus.webp`, `cab.webp`, `sign_chicken.webp`, `sign_barber.webp`, `mural_e8.webp`, plus other supplied signs, props and people. Higher-resolution Higgsfield masters and extra model views remain uninspected |
| **New York — yellow runner** | Brownstone rust, deep steel blue and taxi yellow; warm angled sun against cool street shadows | Brownstone stoops, brick depth, fire escapes, deli storefronts, bridge steel, worn asphalt and street markings; paint material detail at gameplay scale | Runaway hot-dog cart: real cart volume, metal panels, wheel rotation, lid/umbrella response and a small food wobble that reads from the camera | `newyork/hotdog.webp`, `messenger.webp`; OpenAI `cover.png` for layout and palette. Supplied London bags/barrier/scaffold can inform shared objects. Local storefront, skyline and taxi originals in Higgsfield remain uninspected |
| **Rio — green runner** | Sunlit coral, turquoise and lime with warm white; strong daylight, cool shade and restrained distance haze | Painted hillside plaster, tiled thresholds, corrugated roofs and wires; palms, promenade mosaic and coastal depth where the district supports them | Capoeira performer: balanced ginga into a readable sweeping kick, planted support foot, coordinated hips/shoulders and cloth follow-through | `rio/capoeira.webp`, `coconut.webp`, `mototaxi.webp`, `umbrella.webp`, `monkey.webp`; OpenAI `cover.png` for palette. Local surface masters, architecture studies and movement views in Higgsfield remain uninspected |
| **Westside / The Hood — purple runner** | Peach sunset, dusty cream, mauve shade and selective saturated car paint; low warm sun | Stucco bungalows, porches, garages, chain-link fences, palms, corner shops and basketball-court surfaces; neighbourhood details with believable scale | Lowrider: sculpted body, painted chrome and upholstery, grounded rotating wheels and articulated suspension that moves the chassis convincingly | `hood/lowrider.webp`, `bmx.webp`, `cart.webp`; OpenAI `cover.png` for colour reference. Westside buildings, murals, car detail views and texture sources in Higgsfield remain uninspected |

## Bounded delivery per city

Each row has four concrete deliverables. Finish and review one playable street
section before expanding that city's full route.

| City | 1. Surface kit | 2. Street section | 3. Finished moving hazard | 4. In-game evidence |
|---|---|---|---|---|
| Buenos Aires | Corrugated metal, plaster, paving, café tile and fileteado material set | San Telmo café block with one La Boca façade variant; then carry the finish into the avenue | Textured, articulated tango pair with one coherent crossing dance sequence | Same-camera before/after stills and a short gameplay clip showing the runner approaching and passing the dancers |
| London | Brick/concrete/road set plus cleaned existing shop signs and mural panels | One East London shop-and-estate block using the original art | Textured delivery cyclist with a complete pedal loop and grounded crossing motion | Same-camera street comparison and cyclist encounter clip |
| New York | Brick/brownstone/asphalt/metal set and a small local storefront panel set | One stoop-and-deli block with a distinct bridge approach backdrop | Finished rolling hot-dog cart with coordinated wheel and secondary motion | Same-camera street comparison and cart encounter clip |
| Rio | Painted plaster, roof metal, paving/mosaic and shop panel set | One hillside street section with a clear coastal transition | Finished capoeira performer with a coherent approach, kick and recovery | Same-camera street comparison and capoeira encounter clip |
| Westside / The Hood | Stucco, sidewalk, fence and garage/storefront material set | One bungalow-and-corner-shop block with palms and court detail | Finished lowrider with textured interior, chrome and suspension motion | Same-camera street comparison and lowrider encounter clip |

These signature hazards establish the finish standard for the remaining
obstacles; they do not mark a city complete while its other hazards remain
primitive. Apply the accepted material, modelling and animation standard to
each city's existing obstacle set before calling that city finished.

## Production order

1. **Audit sources.** Match accessible Higgsfield originals and the supplied
   files to the first Buenos Aires street and tango pair. Record source name,
   dimensions, transparency, useful views and provenance. Keep originals
   unchanged. Request access/export only for the library assets that cannot be
   reached through the available connection.
2. **Enhance selected images in Magnific.** Select a specific surface or
   reference image with a visible quality gap. Preserve character identity,
   costume, composition, painted style and silhouette; keep variation low.
   Compare the output with its original before accepting it. Restore lettering
   from a clean authored layer and retain clean transparency where needed.
   Prepare texture crops, seams and UV layouts separately; a cover upscale is
   not a finished environment material.
3. **Finish the first Buenos Aires section.** Build or refine textured models
   from those references. Give the tango pair expressive anatomy, connected
   hands, believable foot placement and coordinated partner motion. Fit the
   sequence into the existing crossing duration and footprint. Finish the
   street materials, lighting and contact shadows around that encounter.
4. **Review through the actual game camera.** Show the runner, street and
   dancers together in motion at desktop and phone sizes. Capture genuine
   gameplay evidence and label its build. Check readability on approach,
   foot contact, silhouettes, clipping, lighting consistency and cost on the
   target device. Record observed results; a model viewer or offline render
   cannot stand in for this review.
5. **Transfer the demonstrated standard.** Apply the Buenos Aires finish to
   its remaining districts and obstacles, then deliver the four items above
   for London, New York, Rio and Westside. Reuse shared construction techniques
   while preserving the local materials, architecture and animation subjects.

This brief defines the remaining finish work. Five OpenAI material sheets and
the surface/lighting foundation are now recorded above, alongside the prepared
source pack. No Magnific jobs, finished cities, completed hero-model quality,
browser review or test results are claimed.
