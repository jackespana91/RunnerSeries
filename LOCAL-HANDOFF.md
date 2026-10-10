# Continue Runnerz locally

Handoff prepared 10 October 2026. The user has a local Codex project named
**runner**. Start a **local task** in that project.
Its files have not been inspected from cloud; do not assume it is empty or that
its Git remote matches the release repository. The cloud agent has no available
control to move this running task to the user's computer.

## Get the current source

Published branch: [codex/runnerz-art-preview](https://github.com/jackespana91/RunnerSeries/tree/codex/runnerz-art-preview).
The current game/art release is commit
`b3ac8f09508e8e0a82458f84d5ff58111ab32de6`.

That branch contains packaged releases; its repository root is not the expanded
application source. The local agent should inspect the existing project and
its Git status first, then download these files into a fresh subfolder without
replacing existing work. The user does not need to move ZIPs manually:

- `Runnerz-Polished-Source.zip` — all application source, original assets, five
  material masters and current rendering work; approximately 43.43 MB at the
  release above.
- `Runnerz-Art-Finish-Pack.zip` — 18 prepared enhancement jobs and 25 unchanged
  source/reference images, with prompts and a production brief.
- `SHA256SUMS.txt` and `ART-FINISH-SHA256.txt` — archive checksums.

Pinned download URLs:

```text
https://raw.githubusercontent.com/jackespana91/RunnerSeries/b3ac8f09508e8e0a82458f84d5ff58111ab32de6/Runnerz-Polished-Source.zip
https://raw.githubusercontent.com/jackespana91/RunnerSeries/b3ac8f09508e8e0a82458f84d5ff58111ab32de6/Runnerz-Art-Finish-Pack.zip
https://raw.githubusercontent.com/jackespana91/RunnerSeries/b3ac8f09508e8e0a82458f84d5ff58111ab32de6/SHA256SUMS.txt
https://raw.githubusercontent.com/jackespana91/RunnerSeries/b3ac8f09508e8e0a82458f84d5ff58111ab32de6/ART-FINISH-SHA256.txt
```

Expected SHA-256 values from the release artifacts:

```text
63416630113927c4d4ec1cb1c13130044c7130c33fe9369367345b57e49c9894  Runnerz-Polished-Source.zip
4a44a46769949301099c90de1c562257b6eb2d322faaaaf62be0f9b2d2eef76f  Runnerz-Art-Finish-Pack.zip
```

The local agent should verify the archive checksums, extract the source into
that new subfolder, and locate the `Runnerz` folder containing
`web/package.json`. Compare any existing Runnerz source separately before
combining it. Cloning the release branch alone does not unpack the application.

## Start the local game

Prerequisites: Node.js 18 or newer, npm and Python 3 available as `python3`.
The latest cloud build used Node 24. Dependencies are pinned in the lockfile.
The local agent can run these commands from the extracted `Runnerz` folder;
the user does not need to open a terminal:

```bash
cd web
npm ci
npm run dev
```

Keep that terminal running. Open:

- Game: <http://localhost:4173/>
- Buenos Aires street: <http://localhost:4173/?city=buenosaires&demoPreview=1&district=la-boca>
- Tango encounter: <http://localhost:4173/?city=buenosaires&artPreview=tango>

`npm run dev` builds once and serves `web/dist`; it is not a file watcher.
After edits, run `npm run build` in a second terminal inside `web`, then refresh
the browser. The existing dev script binds to all network interfaces. For
loopback-only serving, run `npm run build` followed by
`python3 -m http.server 4173 --bind 127.0.0.1 --directory dist` instead.
No new tests were requested or run for this handoff.

## Connect Magnific in the local task

First have the local agent inspect the tools actually available in that task.
The cloud conversation reported `Auth required`; successful local authorization
has not been verified. An open Magnific dashboard is not confirmation that
Codex has authorized MCP access.

If the server is absent from the local CLI configuration:

```bash
codex mcp add magnific --url https://mcp.magnific.com
```

If the local connection requires authorization:

```bash
codex mcp login magnific
```

Complete the browser consent and wait for the terminal's success result. Then
open a fresh local task if needed to load the connection. Have the agent make
an available read-only Magnific call before submitting jobs. Do not repeat the
cloud login loop or claim a connection works without a successful tool result.
Never paste tokens, cookies or OAuth callback URLs into the chat.

No Magnific job has run. The additional Higgsfield library has not been
inspected; inspect accessible originals there before generating replacements.

## Work already saved

- Five cities: London, New York, Rio, Buenos Aires and Westside / The Hood.
- Five OpenAI-generated material sheets provide 30 surface cells, integrated
  with city-specific lighting, lit atlas panels and nearby soft shadows.
- All 72 supplied original images are preserved unchanged. Material PNG
  masters are in `art/masters`; runtime WebP sheets are in `web/assets`.
- Obstacles and crossing hazards have animated geometry. Their model forms,
  anatomy, materials and coordinated motion still need substantial finishing.
- Buenos Aires includes district decoration and a dedicated tango preview.
- The latest build passed. The latest visual pass has no browser appearance,
  phone performance or gameplay capture review. No city is marked finished.

The source root in the cloud was an unborn `work` checkout with untracked
source. The public release branch was assembled separately. Do not assume its
Git history contains expanded source commits or reset an existing local
checkout to recreate that arrangement.

## Read first and continue

- `docs/CITY-ART-FINISH.md`: city identities, remaining work and
  first complete street/hero-hazard deliverables.
- `docs/ASSET-SOURCES.md`: supplied artwork and generated provenance.
- `docs/VALIDATION.md`: which results belong to which build; earlier
  runtime checks do not verify the latest art.
- Rendering: `web/src/world/engine.js`, `kit.js`, `obstacle-rig.js`.
- City work: `web/src/world/cities/`, especially `city-surfaces.js` and the
  Buenos Aires environment, art and ambience modules.
- Models: `web/src/world/models/`; crossing bindings:
  `web/src/world/hazard-models.js`.
- Actual tango preview: `web/src/game/hazard-preview.js`, used by `main.js`.
- Packaging: `tools/package_release.py` and `tools/package_art_finish.py`.

First finish a Buenos Aires street with the tango pair through the actual game
camera. Use Magnific for selected image references and texture improvement;
finish 3D form, UVs, animation and contact separately. Then carry the demonstrated
quality across every city's districts and obstacles. Preserve lane rules,
clearances, encounter timing and payouts. Show real in-game captures, labelled
with their build; offline model boards do not establish gameplay appearance.

## Paste into the new local task

> Continue Runnerz locally in the runner project. Read this LOCAL-HANDOFF.md,
> inspect existing files and Git changes, then download and verify the pinned
> source and art-pack archives into a fresh subfolder. Read the extracted
> docs/CITY-ART-FINISH.md, docs/ASSET-SOURCES.md and docs/VALIDATION.md.
> Start the game locally for me. Check Magnific tools and authorization first;
> avoid repeating the cloud login loop. Use Runnerz-Art-Finish-Pack.zip and
> accessible Higgsfield originals to finish all five cities with their own
> architecture, materials, lighting and signature animated hazards. Start with
> a complete Buenos Aires street and convincing tango pair. Keep every obstacle
> animated and three-dimensional, preserve game rules and payouts, and show
> actual in-game art progress. Preserve existing local changes and original
> assets. Do not call a city finished based only on compilation or model boards.
