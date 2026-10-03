# hls.js

## Stack
- **Runtime**: Node.js 14+
- **Library**: HLS streaming client using MediaSourceExtension
- **Language**: TypeScript (types exported)
- **Build**: Rollup (ESM + CJS outputs)
- **Testing**: Karma + Jasmine
- **Documentation**: JSDoc + Markdown plugins

## Project Structure
```
src/
  controller/         # Main HLS controller
  loader/             # Network requests
  demux/              # Stream parsing
  utils/              # Utility functions
dist/                 # Compiled outputs (hls.js, hls.mjs, hls.light.mjs)
test/                 # Karma test suite
scripts/
  rollup.config.js    # Build configuration
  karma.conf.js       # Test runner config
```

## Key Patterns
- **MediaSourceExtension API**: Streams HLS into `<video>` element
- **Exports**: `hls.js` (CJS), `hls.mjs` (ESM), `hls.light.mjs` (minimal build)
- **TypeScript**: Full type definitions in `dist/hls.d.ts`
- **Live & VOD**: Supports both live HLS and video-on-demand
- **Adaptive Bitrate**: Quality switching based on bandwidth

## Common Commands
```bash
npm install                    # Install dependencies
npm run build                  # Full production build
npm run build-test             # Build with test bundle
npm run build-prod             # Production build (optimized)
npm run test                   # Lint + build + run tests
npm run lint                   # Check code style (vjsstandard)
npm run start                  # Dev server + file watcher
npm run docs                   # Generate API docs + images
```

## Important Files
- `src/hls.ts` — Main entry point & API surface
- `src/controller/` — HLS state management & control logic
- `scripts/rollup.config.js` — Build configuration
- `scripts/karma.conf.js` — Test runner setup
- `dist/hls.d.ts` — TypeScript type definitions (generated)

## Notes
- This is a fork of video-dev/hls.js; you're on the `MrAmazingFreelancer/issue4289` branch (issue fix)
- Before merging: run `npm run test` locally to catch regressions
- Build outputs multiple formats; always use full build for distribution
- MediaSourceExtension has browser compatibility limits; check can-i-use
