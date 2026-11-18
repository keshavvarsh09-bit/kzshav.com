# Architectural & Technical Decisions

## ADR-001: Pure Static Single-File Architecture
- **Date**: 2026-11-18
- **Context**: The portfolio consists of a beautifully styled, responsive personal homepage with custom SVGs and animations.
- **Decision**: Keep `index.html` self-contained without npm dependencies or bundlers (Webpack/Vite).
- **Consequences**: Super fast deployment, zero maintenance, instant deployment to Vercel.

## ADR-002: Hosting on Vercel with Custom Domain kzshav.com
- **Date**: 2026-11-18
- **Context**: The user requested deploying to Vercel and connecting custom domain `kzshav.com`.
- **Decision**: Deploy directly to Vercel Edge hosting using Vercel CLI / Git integration, with automated HTTPS and edge caching.
