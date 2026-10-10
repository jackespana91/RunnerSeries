# Runnerz asset sources and reuse

## Working preference

Reuse the user's existing Runnerz artwork, particularly the Higgsfield library,
before creating replacement art. The user's newer direction (10 October 2026)
requires animated 3D lane obstacles; the earlier flat obstacle-image plan is
superseded. Supplied images remain valuable model, palette and material
references, plus environment and character art.

The user confirmed that they are logged in to Higgsfield in the browser. This
session has no callable Higgsfield account or browser-control tool, so the
account library has not been inspected or downloaded. Continue to match accessible
Higgsfield originals before commissioning replacements for specific supplied
subjects. The five new material sheets below establish a surface foundation;
they do not establish that comparable Higgsfield originals are absent.

The [production plan](ART-PRODUCTION-PLAN.md) and
[asset manifest](art-manifest.json) describe runtime roles and source references.
Their earlier file counts are historical planning choices. A suitable Higgsfield
original can fill an image-based environment role directly or inform a 3D
model/material. The former 25 obstacle cutout targets and six traffic sheets are
retained as superseded reference records.

## Current material sources and prepared finishing pack — 10 October 2026

Five new material sheets were generated with **OpenAI image generation**, one
for each city. Each native PNG master is 1536 × 1024, arranged as six
512 × 512 cells. Masters stay unchanged in `art/masters/` and the original
`/workspace/generated_images` outputs; runtime copies are WebP:

| City | Unchanged generated master | Runtime file |
|---|---|---|
| London | `art/masters/london-materials.png` | `web/assets/london/materials.webp` |
| New York | `art/masters/newyork-materials.png` | `web/assets/newyork/materials.webp` |
| Rio | `art/masters/rio-materials.png` | `web/assets/rio/materials.webp` |
| Buenos Aires | `art/masters/buenosaires-materials.png` | `web/assets/buenosaires/materials.webp` |
| Westside / The Hood | `art/masters/hood-materials.png` | `web/assets/hood/materials.webp` |

`tools/encode_city_materials.py` uses ffmpeg to encode the runtime sheets as
WebP at quality 90, preserving the 1536 × 1024 dimensions and six-cell layout.
This is format encoding without cropping, resizing or redrawing. The included
WebP files keep download size lower; ordinary `npm run build` uses those files
and does not require ffmpeg.

These five generated sources are separate from the 72 unchanged supplied
originals and the four earlier generated covers. They have not been enhanced by Magnific. Their
cells feed `web/src/world/cities/city-surfaces.js` and city atlas panels for solid
building surfaces, roofs and paving. They do not replace obstacle volumes with
flat images. New York, Rio and The Hood now use their authored wall-art slots
instead of placing menu covers on street walls; Buenos Aires already has its
dedicated mural set. Surface integration and rendering changes compiled;
see [VALIDATION.md](VALIDATION.md). No browser review or tests were run.

`releases/Runnerz-Art-Finish-Pack.zip`, produced by
`tools/package_art_finish.py`, is a separate **prepared source handoff**: 18
unsubmitted enhancement jobs, 18 unchanged input images, seven unchanged
reference images and the finishing brief. The 25 images are copies of existing
sources; four of the cover references were generated during the earlier OpenAI
cover pass. This pack contains no completed Magnific output. The five new
material sheets are game assets, separate from those prepared enhancement jobs.

Magnific is registered and enabled in the Codex CLI, with authentication status
unknown and no callable Magnific tools in this session. An unauthenticated MCP
initialization returned HTTP 401; that does not diagnose saved OAuth credentials
or the user's browser login. No Magnific job has run, and the additional
Higgsfield account library remains uninspected.

## What has actually been supplied

File audit: 10 October 2026. Both source archives contain the same **72 visual files**, with identical SHA-256 hashes for every matching asset. All 72 are present, unchanged, in `web/assets`. The two publishing archives contain no visual files. This audit inspected the received files and selected images; it did not inspect the Higgsfield account.

| Source | Visual files | Provenance and status |
|---|---:|---|
| `Runnerz-Part1-Game-and-Source.zip` | 72 | Supplied by the user; imported into `web/assets` |
| `Runnerz-Source.zip` | 72 | Duplicate asset set; no additional illustrations |
| `Runnerz-Part2-Publish-Runs.zip` | 0 | Run publishing data |
| `Runnerz-Part3-Publish-Buys.zip` | 0 | Buy publishing data |
| Four current non-London `cover.png` files | 4 | Generated with OpenAI image generation during the earlier cover pass; separate from supplied art |
| Five generated city material sheets | 5 | OpenAI PNG masters in `art/masters/`; format-encoded quality-90 WebP runtime copies in `web/assets/<city>/materials.webp`; no Magnific enhancement |
| Additional Higgsfield projects/library | Unknown | User reports existing artwork; export or supported account access still required |

The supplied London source comments and accompanying README attribute the London artwork to Higgsfield. This is the provenance recorded in the supplied material, not an independent account-level verification. Do not assume the remaining supplied files have a particular generator, model, project ID or licensing record when those details are absent.

No Magnific enhancement has been applied to the supplied assets, generated covers or new material sheets.

### Received artwork inventory

| Folder | Count | Contents |
|---|---:|---|
| `london/` | 34 | Cover, skyline, six signs, four murals, eight pedestrians, ten obstacles, rider, bin lorry, chicken box and fox |
| `newyork/` | 2 | Hot-dog cart gag and bike messenger |
| `rio/` | 5 | Capoeira performer, coconut vendor/cart, monkey, moto-taxi and umbrella |
| `buenosaires/` | 3 | Dog walker, delivery scooter and tango pair |
| `hood/` | 3 | BMX rider, shopping cart and lowrider |
| `runner/` plus `runner.webp` | 10 | Nine reaction/action poses and the run sheet |
| `shared/` | 15 | Pickups, cash bag, snatchers, animals, balls and effects |

Preserve these source images. There is no unimported illustration set in the four received ZIPs.

## Earlier Buenos Aires authored art additions — 10 October 2026

This city pass adds runtime Canvas artwork and mesh geometry. It does not add a
new external illustration set, modify the supplied originals, access the
Higgsfield account or apply Magnific processing.

| Source | Added presentation | Provenance |
|---|---|---|
| `web/src/world/cities/buenosaires-art.js` | 24 atlas slots: six signs, three fileteado panels, three murals, six facade materials, three posters, two ceramics and one menu | Authored Canvas drawing; San Telmo mural composites the supplied `buenosaires_tango` image |
| `web/src/world/cities/buenosaires.js` | Detailed La Boca, San Telmo and avenue architecture, streetside furniture and Obelisco backdrop | Authored 3D geometry with atlas surfaces |
| `web/src/world/cities/buenosaires-ambience.js` | Fluttering pennants and drifting jacaranda petals | Authored instanced geometry and animation |
| `web/src/world/models/buenosaires-props.js` | Café, parrilla, kiosco, awning and colectivo rigs; five factories used by six roles including both bus colours | Authored articulated 3D geometry; colectivo extends the shared bus factory |

The reused tango file remains `web/assets/buenosaires/tango.webp`, unchanged.
Its use in a wall mural is separate from the animated 3D tango encounter. The
Buenos Aires cover remains menu/key art; its former street-mural use has been
replaced by the dedicated mural set. No new image-generation job, tests or
browser playthrough were run for this pass. The combined game/viewer build and
classic IIFE compilation passed; evidence is maintained in
[VALIDATION.md](VALIDATION.md).

## Historical reuse bindings before the animated 3D request

The following files served the earlier reuse pass. The four rider bindings and
three obstacle bindings below were implemented before the new direction. The
flat obstacle and rider bindings are superseded by the implemented animated 3D
rigs. The combined game/viewer build passed on 10 October 2026; no tests or
browser playthrough were run for this pass. Retain the original images as modelling and material
references. New York also uses
six shared pedestrian sprites: `london_ped1`, `london_ped2`, `london_ped4`, `london_ped5`, `london_ped6`
and `london_ped8`. Their generic adult clothing suits the current New York pass;
the additional Higgsfield city collection can supply further local characters.
This table records that historical binding pass, not completion of the current
animated obstacle work. Runtime review of the new models remains a separate task.

| Additional role | Existing asset key / file | Starting binding | Reason |
|---|---|---|---|
| New York crossing rider | `newyork_messenger` / `newyork/messenger.webp` | `crosser.sprite`, `w: 2.5` | Existing city messenger already has the side-view action needed for crossing |
| Rio crossing rider | `rio_mototaxi` / `rio/mototaxi.webp` | `crosser.sprite`, `w: 2.7` | Existing city moto-taxi gag supplies the same subject and motion direction |
| Buenos Aires crossing rider | `buenosaires_moto` / `buenosaires/moto.webp` | `crosser.sprite`, `w: 2.6` | Existing delivery rider can replace the geometric crossing figure |
| Westside crossing rider | `hood_bmx` / `hood/bmx.webp` | `crosser.sprite`, `w: 2.2` | Existing BMX rider can replace the geometric crossing figure |
| New York `trash` obstacle | `london_bags` / `london/bags.webp` | `sprite`, `h: 1`, `maxW: 2.2`; retain `rule: 'jump'` | Generic black bags and cartons; 512 × 341 RGBA; no city-specific lettering |
| New York `barricade` obstacle | `london_barrier` / `london/barrier.webp` | `sprite`, `h: 1.15`, `maxW: 2.3`; retain `rule: 'jump'` | Front-view orange/white barrier with amber lamps; 512 × 260 RGBA; matches the requested object |
| New York `shed` obstacle | `london_scaffold` / `london/scaffold.webp` | `sprite`, `h: 3.2`, `maxW: 2.6`; retain `rule: 'slide'` | Front-view green upper span and two scaffold uprights; 421 × 512 RGBA; fully transparent opening below |
| Shared New York pedestrians | `london_ped1`, `ped2`, `ped4`, `ped5`, `ped6`, `ped8` | `people.sprites` using the six existing keys | Generic adult streetwear characters; no new files needed; compare against incoming city-specific art before final selection |

The scaffold size above retains London's existing proportions. The current camera and encounter distance still determine final visual scale. Reuse must preserve obstacle rules, deterministic events and payouts.

### Reference roles and view limitations

- `newyork/hotdog.webp` is a moving, tilted cart with flying food. Use its colours, proportions and materials as references for the animated 3D runaway-cart hazard and stationary lane cart.
- `rio/coconut.webp` contains the vendor pushing a side-on cart. It is useful as a style/material reference, while the fixed stall obstacle needs a distinct silhouette.
- `hood/cart.webp` is a side/three-quarter shopping cart. Use this and appropriate Higgsfield cart views as model and material references for the 3D cart hazard.
- `hood/lowrider.webp` is a side-view bouncing convertible. The animated 3D lane obstacle and traffic need their own geometry and wheel/suspension articulation; the existing image remains a style and proportion reference.
- `shared/steam.webp` is a cloud effect. New York's `steam` lane obstacle is a solid orange/white steam stack and must retain a clearly readable obstacle body.
- London signs and murals demonstrate the art style and atlas format. Their city-specific lettering and imagery should not silently replace the other cities' intended panels.
- `london/skyline.webp` contains London landmarks. Keep each destination's skyline identity; covers are not substitutes for transparent panoramic backdrop strips.
- London pedestrians are useful for an interim New York pass. Review clothing against Rio's climate and the intended local character designs before using the same population everywhere.

## Higgsfield handoff

The next external input is a download/export of the existing Runnerz projects or a shared asset folder that this environment can actually read. Being logged in through the user's browser does not expose that library to the file tools.

For the first batch, collect the existing **New York** art, including alternative generations: hydrant, yellow taxi, stationary hot-dog cart, steam stack, skyline, signs, murals, pedestrians and vehicle rear views. Include available 3D source models, animation frames and material/texture sources. Obstacle images now support 3D modelling and materials rather than replacing volumes with flat cutouts. Include any better originals of the reusable bags, barrier and scaffold. Preserve original names and project groupings so duplicates and variants can be matched correctly. Then supply the equivalent Rio, Buenos Aires and Westside sets.

Prefer the original downloadable PNG/WebP assets, transparent cutouts, animation frames or source sheets over screenshots or gallery thumbnails. Where already available, retain the project ID, original filename, creation date, prompt/reference notes, frame layout and attribution/licensing notes beside the art. Do not include login credentials, browser profiles, cookies or API keys.

After receipt:

1. Inventory filenames, dimensions, alpha, hashes, camera views and character identity without changing the originals.
2. Match each usable original to a manifest role and mark duplicates or alternate views. Keep lossless masters outside `web/assets`, which is embedded in the playable build.
3. Use suitable supplied art as 3D model/material references, environment textures or character art according to its role. Animate model components in the runtime. Select Magnific enhancement only for an identified image-quality gap, preserving composition, outlines, alpha and gameplay silhouettes.
4. Create new art only for roles still missing after that comparison. Export one final file per asset stem to avoid duplicate runtime keys.

Current missing code bindings and geometric placeholders do not establish that the corresponding artwork is absent from Higgsfield. That distinction stays open until the export is available.
