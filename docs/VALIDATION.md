# Validation of the polished demo

## City surface and lighting foundation — 10 October 2026

Current source work adds five OpenAI-generated material sheets. Native
1536 × 1024 PNG masters remain unchanged at
`art/masters/<city>-materials.png` and in the original generated-image outputs.
Runtime files are `web/assets/<city>/materials.webp`, format-encoded at quality
90 with the same dimensions and six 512 × 512 cells; no cropping, resizing or
redrawing was performed. `tools/encode_city_materials.py` uses ffmpeg for this
optional source-preparation step. Ordinary npm builds use the included WebP
files and do not require ffmpeg.

`city-surfaces.js` places those cells into city atlases for
solid building surfaces, roofs and paving. New York, Rio and The Hood no longer
substitute menu covers for their street murals. All 72 supplied images remain
unchanged.

The rendering foundation enables a 1024² PCF soft sun-shadow map, limits shadow
casting to nearby geometry around the first 60 metres, applies city-specific
lighting/exposure/outline settings and uses Lambert lighting for atlas panels.
Padded atlas UVs and panel rotation support the new surface placements.

**Final WebP `npm run build` passed.** The public classic-script IIFE also
compiled. Final artifacts for this pass are:

| Artifact | Build size |
|---|---:|
| Offline game (`Runnerz-Demo.html`) | 27.60 MB |
| Game with Three.js from CDN | 26.89 MB |
| Offline model viewer (`Runnerz-Art-Preview.html`) | 0.87 MB |

The five unchanged PNG masters total 17.68 MB. Their five runtime WebP copies
total 2.93 MB before base64 embedding. Master files remain in `art/masters/`;
ordinary builds consume the included WebP assets. Interim PNG delivery sizes
are superseded by the final sizes above.

Static review found no severe blockers and covered atlas capacity, inset UVs,
ground-panel rotation and unchanged role IDs. Atlas usage is London 22/32 cells,
Buenos Aires 29/32, and New York/Rio/The Hood 21/32 each.

No tests, browser review, screenshots or performance checks were run for this
pass. Compilation and source review do not establish finished model quality,
rendered appearance or frame rate through the game camera. Earlier successful
build sizes and runtime results below belong to the named earlier changes.

The separate `Runnerz-Art-Finish-Pack.zip` contains 18 prepared, unsubmitted
jobs and 25 unchanged source/reference images, not enhanced output. No Magnific
job ran and the additional Higgsfield library was not inspected. Magnific's CLI
entry is registered/enabled with authentication unknown; an unauthenticated
initialization returning HTTP 401 does not diagnose saved OAuth state.

## Direct tango obstacle preview — 10 October 2026

`npm run build` succeeded after adding the demo-only `artPreview=tango` scene:
23.69 MB offline game, 22.98 MB CDN game and 0.86 MB model viewer. The
classic-script public game also compiled. Static review confirmed the existing
tango definition/rig, view fields, preview controls and demo/round guards.
The scene loops the crossing cue without selecting or settling a game round.
No tests, browser playthrough or screenshots were run for this change.

## Buenos Aires environment and prop pass — 10 October 2026

`npm run build` succeeded with the new Buenos Aires environment, 24-slot
surface-art atlas, animated street ambience and five local prop factories:

| Artifact | Build size |
|---|---:|
| Offline game (`Runnerz-Demo.html`) | 23.68 MB |
| Offline model viewer (`Runnerz-Art-Preview.html`) | 0.86 MB |
| Game with Three.js from CDN | 22.98 MB |

The classic-script `Runnerz-In-Game.html` also compiled. Preview URLs can start
in any Buenos Aires district. The changes retain the existing obstacle IDs,
rules, pools, traffic positions and movement values; payouts are unchanged.
Static review covered atlas capacity, model APIs, slide clearance and ambience
cleanup. It prompted a district-boundary fix so upcoming flags and petals are
visible alongside the incoming district geometry; the final build passed.
No tests, browser playthrough or phone performance checks were run for this
pass. The visual upgrade is implemented, not browser-verified.

## Direct in-game preview — 10 October 2026

`npm run build` succeeded after adding a standalone classic-script game build
(`Runnerz-In-Game.html`) for public HTML preview services. The existing demo and
model viewer also compiled. The `city` and demo-only `demoPreview=1` URL options
open the street and start ordinary play-money rounds, respecting autoplay
restrictions. This preview path has not had a browser playthrough; public HTML
delivery does not establish rendering correctness or performance.

## Animated 3D artwork pass — 10 October 2026

`npm run build` succeeded for the updated game and standalone model viewer:

| Artifact | Build size |
|---|---:|
| Offline game (`Runnerz-Demo.html`) | 23.66 MB |
| Offline model viewer (`Runnerz-Art-Preview.html`) | 0.84 MB |
| Game with Three.js from CDN | 22.96 MB |

Source review covered all 35 lane-obstacle bindings, seven extra traffic
prototypes, every current crossing/wipeout/robbery hazard cue, pool resets,
geometry/material disposal, slide openings and model transforms. It prompted
fixes for wheel arches, vehicle culling, grounded lowrider suspension, model
scale, walking direction, rolling-prop ground clearance and shared textures.

No game tests, browser playthrough or phone performance checks were run for
this pass. Successful compilation and source review do not establish rendered
appearance or frame rate. Earlier runtime results below predate the 3D changes.

## Earlier supplied-art reuse pass

`npm run build` succeeded after adding four painted crossing-character bindings,
three shared New York obstacle sprites, six shared New York pedestrians, and
duplicate artwork-key detection in the build. The demo and source archives were
regenerated. No game tests or browser playthrough were run for this reuse pass;
the runtime results below describe the earlier build, not these latest changes.

## Earlier demo validation

Validated in the cloud workspace on 9 October 2026 using Node 24.19.0, Python
3.12.14, system Chromium and Playwright 1.62.0.

| Check | Result |
|---|---|
| `npm ci` and `npm run build` | Passed; standalone and CDN builds generated |
| `npm test` | 7 passed, 0 failed |
| `python tests/smoke.py` | All 10 browser check groups passed |
| `python tests/soak.py 10 base 0` | Exactly 10 normal London rounds; balances match; no errors |
| `python tests/soak.py 10 hype 2` | Exactly 10 Hype Rio rounds; balances match; no errors |
| Saved install script rerun | Passed |
| `npm run dev` and local HTTP request | Passed; current game served with HTTP 200 |

Browser checks cover all five cities, all four payout modes, the largest demo
bonus purchase, native keyboard behaviour, lobby focus isolation, loading
failure/retry, blocked new bets during failed settlement, retry of the same
result, UK speed/autoplay restrictions and minimum duration, and controls fitting
360×640, 812×375 and 1440×900 viewports. The standalone build made zero external
requests. No browser exceptions occurred.

The city-switch cleanup was also stressed across 20 switches in an isolated
renderer build. At the end of each five-city cycle, resources stayed at 63
geometries and 30 textures, instead of growing from 177/55 to 618/136. Shared
runner and cached textures remained intact. The final integrated browser checks
also rendered every city successfully.

## Supplied maths

The supplied verifier replayed every event/payout pair and checked the lookup
files. Independent stream counts also matched:

| Mode | Books | Weighted RTP |
|---|---:|---:|
| Base | 1,000,012 | 0.965000000 |
| Hype | 1,000,012 | 0.965000000 |
| Golden Hour | 200,030 | 0.965000000 |
| Super Golden Hour | 200,010 | 0.965000000 |

All 6,994 embedded demo books replayed correctly. Hash comparisons confirmed
the imported maths files and publishing books were unchanged by this work.
These checks do not establish independent certification or live RGS approval.

Physical phones, audio listening tests, real-money sessions and fresh-task
restoration after cloud publication were not tested. The cloud configuration
was saved as a draft; publication is performed in environment settings.
