# Runnerz — city artwork preview

## New city materials and lighting

Five new painted material sheets now supply 30 surfaces for the solid street
geometry. Each city has its own lighting, exposure and outline treatment, with
soft nearby cast shadows and lit façade artwork. Buildings, windows, balconies
and animated obstacles retain their volume.

| City | Applied surface work | Open the game |
|---|---|---|
| Buenos Aires | Red/celeste/ochre corrugated metal, aged cream plaster, limestone and café tiles | [La Boca](https://raw.githack.com/jackespana91/RunnerSeries/codex/runnerz-art-preview/Runnerz-In-Game.html?city=buenosaires&demoPreview=1&district=la-boca) |
| London | Worn brick, glazed shop tiles, estate concrete, teal shutters and courtyard asphalt | [High Road](https://raw.githack.com/jackespana91/RunnerSeries/codex/runnerz-art-preview/Runnerz-In-Game.html?city=london&demoPreview=1&district=high-road) |
| New York | Brownstone, rust/oxblood brick, bridge steel and deli tile | [Brownstones](https://raw.githack.com/jackespana91/RunnerSeries/codex/runnerz-art-preview/Runnerz-In-Game.html?city=newyork&demoPreview=1&district=brownstones) |
| Rio | Coral/turquoise/lime plaster, terracotta roofs, mosaic paving and painted wood | [O Morro](https://raw.githack.com/jackespana91/RunnerSeries/codex/runnerz-art-preview/Runnerz-In-Game.html?city=rio&demoPreview=1&district=o-morro) |
| Westside / The Hood | Peach/cream/mauve stucco, tan brick, garage metal and court paint; open court fencing | [The Boulevard](https://raw.githack.com/jackespana91/RunnerSeries/codex/runnerz-art-preview/Runnerz-In-Game.html?city=hood&demoPreview=1&district=the-boulevard) |

**[See the tango pair directly on the Buenos Aires street →](https://raw.githack.com/jackespana91/RunnerSeries/codex/runnerz-art-preview/Runnerz-In-Game.html?city=buenosaires&artPreview=tango)**

The tango link repeats the existing crossing scene with pause and replay;
it places no bet. Other links start up to ten normal-speed play-money rounds
with sound muted; press **AUTO** to stop further rounds. The first load embeds
about **28 MB**, including art, voices, fonts, game code and Three.js.

This is a material and lighting pass. Character models, authored movement and
remaining city architecture still need finishing. The current tango model is
not a newly finished dancer asset. The build compiled on 10 October 2026;
no tests, browser playthrough, fresh gameplay screenshots or phone performance
review were performed for these changes.

## Artwork sources and finishing pack

The five material sheets and four earlier menu covers were generated with
**OpenAI image generation**. All 72 supplied original images are preserved.
No Magnific enhancement has run, and the additional Higgsfield account library
has not been inspected. New York, Rio and Westside no longer paste their menu
covers into the street mural slots.

- [City finishing brief](docs/CITY-ART-FINISH.md): distinct identity and remaining deliverables for each city.
- [Runnerz-Art-Finish-Pack.zip](Runnerz-Art-Finish-Pack.zip?raw=1): 18 prepared enhancement jobs, 25 unchanged input/reference images and the briefs. These are unsubmitted jobs, not Magnific output.
- [Asset provenance](docs/ASSET-SOURCES.md) and [build record](docs/VALIDATION.md).

Magnific is registered in the cloud CLI, but its tools are not exposed to the
active chat. Running those prepared jobs requires an authenticated, callable
Magnific connection in the active Codex session. A browser login alone does
not establish tool availability.

## Download and play offline

1. Download [Runnerz-Playable-Demo.zip](Runnerz-Playable-Demo.zip?raw=1).
2. Extract the ZIP and open **Runnerz-Demo.html** in a modern browser.
3. Select a city and press **RUN**.
4. Open **Runnerz-Art-Preview.html** for a separate rotatable obstacle-model viewer.

Both files work offline. The model viewer shows model geometry; use the game
to see city textures and lighting. All 35 lane obstacles and seven additional
traffic models use animated geometry; crossing hazards also have moving parts.
The supplied runner and background pedestrian images remain in use.

Download [Runnerz-Polished-Source.zip](Runnerz-Polished-Source.zip?raw=1) for
source, full-resolution generated texture masters, WebP delivery copies and
reusable build/packaging tools. Supplied payout maths are unchanged; original
Parts 2 and 3 still provide the publishing books. The demo awards no real money.

[SHA256SUMS.txt](SHA256SUMS.txt) covers the game/source archives;
[ART-FINISH-SHA256.txt](ART-FINISH-SHA256.txt) covers the finishing pack.
GitHub's code viewer does not run HTML: use the preview links or extracted demo.

## Earlier images

[Earlier model renders](ART-PREVIEWS.md) predate the latest material and lighting
work and are not gameplay screenshots. The existing city-selection image below
shows the menu covers only.

![Existing Runnerz city-selection screen](Runnerz-City-Selection.png)
