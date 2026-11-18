# Architecture

## System Overview
kzshav.com is a fast, lightweight, static personal website and portfolio for Keshav Varshney. Built as a single-page HTML application with inline styles, custom SVG illustrations, responsive widgets, and client-side JavaScript interactions (including interactive tree-shaking, flying birds, and dynamic local IST clock).

## Architecture Diagram
```
[User Browser]
       │
       ▼
[kzshav.com / DNS]
       │
       ▼
[Vercel Global Edge CDN]
       │
       ▼
[Static Files: index.html]
```

## Layers & Responsibilities
| Layer         | Technology            | Responsibility                                      |
|---------------|-----------------------|-----------------------------------------------------|
| Frontend      | HTML5 / CSS3 / Vanilla JS | Interactive portfolio UI, widgets, animations, SVG |
| Backend/API   | None (Static)         | N/A (Static delivery)                               |
| Database      | None                  | N/A                                                 |
| Auth          | None                  | N/A                                                 |
| Queue/Jobs    | None                  | N/A                                                 |
| Storage       | Git repository        | Source version control                              |
| CDN/Hosting   | Vercel                | Global CDN, HTTPS termination, custom domain        |

## Data Flow
Client loads `kzshav.com` via Vercel Edge Network. The single-page `index.html` loads all styling and assets directly. Client-side JS runs locally in the browser to compute real-time IST clock and interactive canvas/DOM animations. External links navigate out to GitHub, Instagram, LinkedIn, and X.

## Key Design Patterns
- Single-page static bundle: Zero build dependencies, zero compile step, instant cold-starts, high reliability.
- Self-contained SVG illustrations and inline animations for optimal performance and zero asset-loading lag.

## External Dependencies
- Google Fonts: Instrument Serif, Inter, DM Mono
- Vercel: Hosting and DNS routing

## Scalability & Limits
Static edge-cached HTML scales virtually without limits on Vercel's Edge Network.

## What NOT to Do
- Do not introduce heavy frontend frameworks (React, Next.js, Vue) unless complex multi-page routing or server-side data fetching is explicitly requested.
