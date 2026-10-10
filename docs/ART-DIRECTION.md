# Runnerz artwork handoff

The supplied London art establishes the visual direction: bold ink contours,
painted comic shading, warm light, a readable runner silhouette, and distinctive
street architecture. The new city covers preserve the same adult runner and
use each city's existing hoodie colour.

| City | Cover | Direction |
|---|---|---|
| London | `web/assets/london/cover.webp` | Supplied original; orange hoodie, estates, murals, red bus |
| New York | `web/assets/newyork/cover.png` | Yellow hoodie, brownstones, Brooklyn Bridge, warm city light |
| Rio | `web/assets/rio/cover.png` | Green hoodie, colourful hillside streets, palms, bay and mountains |
| Buenos Aires | `web/assets/buenosaires/cover.png` | Blue hoodie, La Boca colour, jacarandas, avenue landmarks |
| The Hood | `web/assets/hood/cover.png` | Purple hoodie, Westside palms, lowrider, sunset skyline |

The four new covers are 1672 × 941 PNGs. They were generated with OpenAI image
generation using the supplied London cover and runner pose as references.
No Magnific processing has been applied to these images.
Existing character poses, voice, music, and London art were supplied by the user.

All five covers are integrated into city selection and Golden Hour introductions.
New York, Rio and The Hood now use their authored wall-art slots instead of
menu covers on street walls. Buenos Aires uses dedicated Caminito, tango and
jacaranda murals from its earlier city pass. The supplied originals remain preserved. The earlier use of flat obstacle
sprites is superseded by the animated 3D direction below; supplied
images remain reference sources for the hazard geometry.

## Current surface and lighting foundation — 10 October 2026

Five OpenAI-generated material sheets supply a new surface source for London,
New York, Rio, Buenos Aires and The Hood. Native 1536 × 1024 PNG masters remain
unchanged at `art/masters/<city>-materials.png`; each contains six 512 × 512
cells. Runtime files are `web/assets/<city>/materials.webp`, encoded at quality
90 without cropping, resizing or redrawing. `tools/encode_city_materials.py`
performs that optional encoding step; normal builds use the included WebP files
without needing ffmpeg. The runtime materials are mapped through
`city-surfaces.js` and the city atlases onto solid building sides, selected roofs
and paving. Atlas padding and panel orientation support this integration while
keeping the city geometry and articulated obstacles.

The rendering foundation adds a 1024² soft sun-shadow map for nearby geometry,
city-specific sun/hemisphere light, exposure and outline settings, and Lambert
lighting on atlas surfaces. These changes provide a foundation for material
and model finishing. They do not establish finished character anatomy,
sculpted vehicle quality, believable motion or a finished city. Current
integration/build status is recorded in [VALIDATION.md](VALIDATION.md); no
browser review or tests have been run for this pass.

All 72 supplied images remain unchanged. The new sheets were generated with
OpenAI; no Magnific job has run and the Higgsfield account library remains
uninspected. `Runnerz-Art-Finish-Pack.zip` is a separate prepared handoff of 18
unsubmitted jobs and 25 unchanged source/reference images. Its preparation
must not be described as enhanced or integrated Magnific artwork. Follow
[CITY-ART-FINISH.md](CITY-ART-FINISH.md) for the remaining model, material,
animation and game-camera finish.

## Earlier Buenos Aires city artwork pass

Buenos Aires now has three more detailed streetscapes: colourful corrugated
La Boca buildings and balconies, San Telmo arches and café corners, and the
broad avenue with stone facades, domes and jacarandas. A 24-slot authored Canvas
atlas supplies six signs, three fileteado panels, three murals, six materials,
three posters, two ceramic patterns and a café menu. The tango mural directly
reuses the supplied `web/assets/buenosaires/tango.webp` original.

Overhead pennants and sidewalk petals animate the environment. Five local 3D
factories add a café table with mate and medialunas, a working parrilla, a stocked
kiosco, a cloth awning and a decorated colectivo in both obstacle and traffic
colours. Solid model details and independently moving parts retain the current
3D obstacle direction.

This is code-authored art. No supplied image was changed; no new image
generation, Magnific processing or Higgsfield account access occurred for this
pass. The combined game/viewer build and classic IIFE compilation passed. No
tests or browser playthrough were run. See [VALIDATION.md](VALIDATION.md) for
build evidence. Other cities and remaining character/environment polish remain
separate work.

## Current in-game direction: animated 3D

The user's 10 October 2026 direction is that obstacles have volume and animation.
The earlier obstacle-cutout replacement plan is superseded. The current implementation
uses articulated toon geometry for all **35 lane-obstacle definitions across
five cities**, plus seven ambient vehicle prototypes. Model wheels, lids, fabric, plumes and lights
as independently animated parts where they suit the object. Keep solid supports,
road contact and slide openings readable from the gameplay camera.

Use London's supplied painted art to guide silhouettes, palette, material
contrast and outline weight. Keep the existing runner identity and city colours.
Retain perspective-correct street and building geometry, then improve its
materials, signs, murals and lighting to match the obstacle models. Preserve
obstacle rules, events, timing and payouts.

The 35 lane definitions and seven traffic prototypes have rig bindings.
Crossing, wipeout and robbery hazards also have model bindings, including
riders, performers, crooks, animals, gag props and plumes. The combined game and
viewer build passed on 10 October 2026.
Preserve the supplied images as modelling and material references.

No tests or browser playthrough were run for this pass. Environment art and
mobile performance review remain outstanding. The supplied runner sheet and background pedestrian
art remain in use; the obstacle/hazard pass does not make every character 3D.

A standalone `Runnerz-Art-Preview.html` model viewer is built for inclusion in
the playable ZIP, with city/category selection, orbit/zoom, pause and automatic
rotation. It compiled successfully and provides a direct way to inspect models
without waiting for a particular game encounter.

Follow [the production plan](ART-PRODUCTION-PLAN.md) for the work order. The
accompanying `art-manifest.json` marks the former 25 obstacle-image requests as
superseded and retains them as references for 3D models.

The user has additional assets in Higgsfield. Follow the reuse preference and
provenance record in [ASSET-SOURCES.md](ASSET-SOURCES.md): inventory accessible
originals before commissioning replacement artwork. Existing images can supply
model references, colour studies, surface textures, environment panels and
character-animation references. They do not need to become flat lane obstacles
to remain useful.

## Magnific enhancement pass

Magnific is registered and enabled in the CLI, but authentication is unknown
and this session has no callable Magnific tool. An unauthenticated initialization
response of HTTP 401 does not establish the saved OAuth state. No enhancement
job has been submitted; the source pack remains prepared work.

Use original art for a Magnific enhancement pass only where a specific texture
or reference-quality gap needs it. This is optional image work; it does not
produce 3D geometry, hinges or animation rigs. Select conservative
enhancement settings in the version of Magnific available to you. Review faces,
hands, banknotes, footwear and architectural lines at full size before accepting
an output. Preserve the character identity, hoodie colours, outline thickness,
landscape crop, and placement of the focal character. Avoid extra limbs, text,
logos, invented details on the face, and photographic skin texture.

Reference prompt:

> Polish this existing comic game illustration. Preserve the exact composition,
> adult character identity, expression, anatomy, clothing, perspective and colour
> palette. Clean ink contours and refine painted material detail. Keep the
> stylised shading and readable silhouette. No new text, logos or objects.

Keep the aspect ratio and filename/asset key stable, then run `npm run build`
from `web/`. If the output extension changes, remove the older file with the same
stem to avoid duplicate asset keys. Check the lobby at phone size as well as the
full artwork. The main character and skyline should remain readable behind the
interface.

## Fonts

Barlow Condensed and DM Sans are bundled from Fontsource 5.2.8 under the SIL Open
Font License. Font binaries and their licence texts are in `web/fonts/`. Both
HTML builds embed the fonts, so typography does not depend on Google Fonts.
