# SmartMarsh — Interactive Anti-Idling Port Truck Marshalling Simulation

A standalone browser application for an Industrial Engineering university demonstration.

## Open the simulation

If GitHub Pages is enabled for the repository's **main branch / (root)**, open:

https://aljurialsaiari.github.io/aljuri-portfolio/smartmarsh/

To enable Pages: repository **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: main → Folder: /(root) → Save**.

## Capabilities

- Six navigation sections: Simulation, Analytics Dashboard, Truck Data Table, Results & Conclusions, Settings, About.
- Animated port, check-in zone, engine-off staging, engine-on gate-side queue, reserved/available/busy gates, supervisor event log and driver notification preview.
- Deterministic discrete-event simulation: 5–100 trucks, 1–10 gates, FCFS assignment and exclusive gate reservations.
- Paired experimental workloads with matching arrivals, per-truck service times, gate counts and comparable gate travel assumptions.
- Start, pause, resume, reset, playback speed, simulation clock, user-editable assumptions and local browser persistence.
- All KPI numbers, charts, truck timestamps and conclusions are calculated from simulated events, not hardcoded performance.
- CSV export; XLSX export loads the client-side SheetJS library from a public CDN.

## Engineering scope

- Only time stationary with the engine running is counted as idling.
- Idling diesel consumption (L) = engine idling time (h) × configured diesel rate (L/h).
- Estimated idle CO₂ (kg) = idling diesel (L) × configured emission factor (kg/L).
- Gate utilization (%) = cumulative gate service-busy time ÷ (number of gates × simulation horizon) × 100.
- SmartMarsh may reduce idling while increasing turnaround and reducing gate utilization because gates are reserved during truck travel.

**Disclaimer:** This is simulated data under explicit assumptions, not measured port operations.

## Technical notes

This is the self-contained browser implementation, committed under `smartmarsh/index.html` without modifying the existing portfolio homepage. It does not automatically copy or sync the separate Figma Make file. The default engine scenario was checked after upload: 40 trucks processed in both modes, no overlapping gate reservations, and model-derived fuel/CO₂ figures. A live browser deployment has not been independently verified.