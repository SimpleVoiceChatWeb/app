# SimpleVoiceChatWeb – Web Client

Built browser client for **SimpleVoiceChatWeb**. This repository is a deploy
target: it contains only the Vite build output, no source code.

- **Live:** <https://SimpleVoiceChatWeb.github.io/app/>
- **Short domain:** <https://SimpleVCWeb.github.io/app/>
- **Source:** [`SimpleVoiceChatWeb/webend`](https://github.com/SimpleVoiceChatWeb/webend)
- **Docs:** <https://SimpleVCWeb.github.io/docs/>

## Do not edit by hand

Every file here is generated. The `Deploy Webend to GitHub Pages` workflow in
[`webend`](https://github.com/SimpleVoiceChatWeb/webend) builds the Vue app and
pushes `dist/` into the root of `main` with `rsync --delete`. Changes made here
are overwritten on the next deploy.

`README.md` is excluded from that sync and is the only maintained file.

## Contents

| Path | Purpose |
|---|---|
| `index.html` | Entry point, assets referenced under `/app/` |
| `assets/` | Hashed JS/CSS bundles |
| `audio-processor.worklet.js` | AudioWorklet for capture processing |
| `favicon.svg` | Icon |
| `.nojekyll` | Disables Jekyll on GitHub Pages |

## URL structure

Routing is hash-based, so every view is served by the same `index.html`:

```text
/app/#/login      enter or confirm an invite code
/app/#/call       the voice call
/app/#/settings   devices, push-to-talk, audio
```

`/app/?code=ABC123` opens the login view with the code pre-filled.
Old links to `/voice` are redirected to `/call` by the router.

## GitHub Pages

- Source: **Deploy from a branch**, branch `main`, folder `/ (root)`
- Builds on every push to `main`
- Deploy key access is limited to the `webend` repository (`APP_DEPLOY_KEY`)
