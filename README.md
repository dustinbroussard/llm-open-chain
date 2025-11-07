# Code Maniac LLM Chain Processor

A single-page, multi-stage prompt orchestration tool powered by OpenRouter. This UI lets you chain prompts where each stage can consume the previous stage’s output.

## Features

- Multi-stage chaining with previous-output context
- OpenRouter model selection and API key entry
- Streaming responses with live updates and a Stop control
- Clear status messages, copy-to-clipboard, and responsive layout

## Quick Start

1. Open `index.html` in a modern browser.
2. Enter your OpenRouter API key in the Configuration panel.
3. Pick a model, type your prompt, and click “Send to LLM”.
4. Add more stages using “Add Next Stage” to chain outputs.
5. Optional: Install as a PWA via the banner, or from your browser menu.

## Notes on API Key

- Your key is read from the input field and optionally stored in `localStorage` if you change the field after initial load.
- Consider clearing storage or using a private browser window if sharing your machine.

## Development

- Lint HTML: `npm run lint:html`
- Lint JS (including inline JS in HTML): `npm run lint:js`
- Check formatting: `npm run format:check` (auto-fix with `npm run format`)
- CI runs lint and format checks on pushes/PRs.

## PWA

- Manifest: `manifest.webmanifest` with icons and theme configuration.
- Service Worker: `sw.js` implements CacheFirst (assets) and NetworkFirst (HTML) with a SWR fallback.
- Install Banner: Custom banner using `beforeinstallprompt` with session-level suppression.
- Icons: SVG icons at `assets/icons/`. Replace with branded PNGs (192px, 512px) for store-quality assets.

### APK via Bubblewrap (optional)

1. Ensure the site is served over HTTPS at your final origin and `start_url` points to it.
2. Install Bubblewrap: `npm i -g @bubblewrap/cli`.
3. Initialize: `bubblewrap init --manifest=https://your-domain/manifest.webmanifest`.
4. Build: `bubblewrap build` then sign and `bubblewrap install` to test on a device/emulator.
5. See Bubblewrap docs for Play Store requirements (screenshots, categories, assets).

## Roadmap / Ideas

- Streaming responses for better UX
- Export/import of chains to JSON
- Model-specific presets and temperature controls per stage

## License

Not specified. If you plan to open source, consider adding a suitable license.
# llm-open-chain
