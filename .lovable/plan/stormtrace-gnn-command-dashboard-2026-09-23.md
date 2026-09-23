# STORMTRACE-GNN Command Dashboard

## Goal
Build a functional, presentation-ready scientific command platform around the supplied FastAPI backend. Historical Replay will be the default demonstration path, while every API capability remains accessible.

## Product structure
- Create a compact collapsible application shell with Command Center, Live Analysis, Historical Replay, Anomaly Tracking, Downscaling Lab, Physics Validation, Alert Center, Model Verification, and System/API routes.
- Add a persistent dark/light scientific theme, responsive rearrangement, keyboard focus states, reduced-motion behavior, status toasts, and route-specific metadata.
- Make the current mode, synthetic/demo data status, backend health, active job, and replay event visible at all times.

## API and state
- Add strict backend models, a centralized environment-driven API client, response/error normalization, and adapters for transient pipeline results versus persisted alerts.
- Add TanStack Query hooks for health, replay events, alerts, alert detail, metrics, async job polling, cancellation, retries, terminal states, and post-completion cache refresh.
- Connect all endpoints: health, async run/status, sync run, replay events/run, alerts list/detail, and metrics.
- Preserve actual backend behavior: eight exact progress messages, only low/moderate/severe tiers, mesh coordinates rather than fabricated latitude/longitude, and no invented verification metrics.

## Core experience
- Build an eight-stage execution panel with queued/running/done/failed states, exact stage mapping, job ID, retry, safe user errors, and developer traceback disclosure.
- Build replay selection and judge demo autoplay that advances only after real backend stages/results become available.
- Build result provenance, actual JSON inspection/copying, GNN loss chart, forecast window, 4D bounding-box display, peak comparison, physics score, severity, runtime, seed, and tracked-point metrics.
- Persist only interface preferences and the latest in-session completed result; never synthesize backend results.

## Scientific visualizations
- Create a map-focused command view with MapLibre architecture and a geospatial adapter. Without backend latitude/longitude, the map will explicitly withhold geographic placement and pair the basemap with an abstract mesh-coordinate field; future coordinates will activate geographic centroid, track, radius, and severity layers without redesign.
- Build an animated spherical mesh, message-passing paths, EFI display, D+3–D+10 trajectory, synchronized raw/U-Net/diffusion comparison, amplitude-preservation chart, physics validation gauge, and interactive process flow.
- Label visual reconstructions that the API cannot supply as “DEMO VISUALIZATION”; numeric labels always come from API results.

## Alerts, verification, and system tools
- Build server-backed alert filters for severity/event/limit, frontend search/sort over loaded rows, load-more behavior within the backend’s limit-only contract, and authoritative detail fetching.
- Build verification charts only from `/metrics`, with honest empty states and no accuracy/recall claims.
- Build System/API status, endpoint catalog, recent in-session jobs, completed payload inspector, and guarded blocking sync execution warning.

## Technical details
- Use TanStack Start routes, TanStack Query, Motion for controlled animation, Recharts for numeric charts, MapLibre GL for the map layer, and semantic Tailwind v4 tokens.
- Keep browser-only map/chart code behind safe client boundaries and lazy-load heavy views.
- Use the backend URL from `VITE_API_BASE_URL`, defaulting to `http://localhost:8000` for local development without hardcoding a production address.
- Account for the backend’s in-memory job registry: a documented two-worker deployment can intermittently return job-not-found during polling. The UI will distinguish this from a failed pipeline and provide retry guidance.

## Verification
- Check current diagnostics, automated API-client/hook behavior, and production compilation.
- Drive the live interface at desktop and tablet widths, inspect screenshots, console, requests, theme, navigation, filters, dialogs, and reduced-motion behavior.
- Manually exercise health → replay events → replay → polling → result → alerts → alert detail → metrics → live pipeline → explicit sync pipeline when a backend is available at the configured URL. If it is unavailable, verify all unreachable/retry states and report the blocked end-to-end checks precisely.
