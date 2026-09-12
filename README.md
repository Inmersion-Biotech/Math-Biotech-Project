# Math & Biotech Lab

Interactive mathematics and biotechnology learning laboratory built as a web app, installable PWA, and Capacitor-based Android project from one shared codebase.

The project combines mathematical learning, biotechnology-oriented examples, deterministic calculations, three-dimensional visualization, study tracking, and AI-assisted explanations.

## Project status

**Active development — public source repository.**

A final open-source license has not yet been selected. Until a `LICENSE` file is added, public visibility does not grant general reuse rights.

**Live site:** https://inmersion-biotech.github.io/Math-Biotech-Project/

## Current capabilities

- Biotechnology-oriented mathematical lessons and examples
- Matrix addition, multiplication, determinant, and inverse workflows
- Exam-performance tracking and statistics
- Formula rendering with KaTeX
- Interactive 3D content with Three.js
- AI-assisted explanations
- Installable PWA support
- Android packaging through Capacitor
- REST API for calculations and study integrations

## Technology

### Client

React 19 · TypeScript · Vite · Tailwind CSS · Math.js · KaTeX · Three.js · React Three Fiber · Framer Motion · Vite PWA · Capacitor · Vitest

### Backend

Node.js · Express · TypeScript

## Architecture

```text
Web / PWA / Android client
             │
             ▼
      Versioned REST API
             │
     ┌───────┴────────┐
     ▼                ▼
Deterministic      Study records and
math operations    controlled AI gateway
```

The web, PWA, and mobile builds are intended to share course logic. Platform-specific behavior should stay behind explicit adapters rather than separate copies of the application.

## Development

### Web

```bash
npm install
npm run dev
npm run verify
```

### Backend

```bash
cd server
npm install
npm run dev
```

The development API uses `http://localhost:5000` by default. Backend details are documented in [`server/README.md`](server/README.md).

### Android

```bash
npm run build
npx cap sync android
npx cap open android
```

## AI security

The current AI interface includes a bring-your-own-key browser flow. Browser-persisted provider credentials are not suitable for an official hosted release.

The intended production direction is an authenticated backend gateway with no provider key in the web/mobile bundle, per-user authorization, input and rate limits, usage monitoring, timeout handling, explicit response schemas, safe Markdown rendering, and minimal logs that exclude private learning content.

AI-generated explanations should remain secondary to deterministic mathematical verification.

## Testing priorities

- Matrix and numerical calculations
- Invalid and boundary inputs
- Formula parsing and rendering
- Exam scoring and progress calculations
- API request validation
- AI response-schema handling
- Consistency between web and mobile builds

Client verification:

```bash
npm run verify
```

Backend API check:

```bash
cd server
npm test
```

## Before an open-source release

- [ ] Select and add an open-source license.
- [ ] Audit the current tree and Git history for credentials and private files.
- [ ] Remove browser-persisted provider-key handling from production flows.
- [ ] Route production AI calls through the backend.
- [ ] Add CI for tests, builds, dependency review, and secret scanning.
- [ ] Add contribution, security, and code-of-conduct documentation.
- [ ] Document the license and source of course content and visual assets.
- [ ] Publish reproducible web and Android release procedures.
- [ ] Add privacy, export, and account-deletion documentation where user data is stored.

## Scientific and educational responsibility

Mathematical results and AI-generated explanations should be independently checked before academic, laboratory, clinical, or professional use. Simplified models should be identified as models rather than complete representations of living systems.

## Author

Developed by [Halil Ibrahim Ozturk](https://github.com/Inmerson).
