# NeuralTube Pilot Testing Environment

This repository hosts the deterministic offline testing protocol for the NeuralTube engine infrastructure.

## Protocol Objective

We are conducting isolated stress tests of the localized Node.js/SQLite architecture. The goal is to identify deterministic failure points related to SQLite persistence locks, concurrent port handling, and zero-dependency environment setups.

There is no cloud dependency, no account creation, and no external tracking. The entire system executes entirely on local hardware.

## Download Pilot Pack

- **Release Version:** `v1.0.0-pilot`
- **Size:** ~250MB
- **Direct Download:** [NeuralTube_Pilot_Protocol_Pack.zip](https://github.com/Z3r0DayZion-install/neuraltube-pilot/releases/download/v1.0.0-pilot/NeuralTube_Pilot_Protocol_Pack.zip)

## Technical Constraints

- **Backend:** Node 20.x
- **DB:** SQLite (file-based)
- **Frontend:** Vite dev server (port 5173)
- No external API calls out to third-party services
- No outbound network traffic for telemetry
- Lockfile-enforced install (`npm ci --omit=dev`)
- Generated Bug Reports export only local, deterministic artifacts

## Testing Instructions

1. Download the Pilot Pack ZIP release.
2. Extract the contents to a new local directory.
3. Read the `PILOT_QUICKSTART.md` file included in the root of the pack.
4. Execute the required testing steps (run `npm ci`, verify startup logs, hit constraints).
5. Generate the `EXPORT_BUGREPORT` payload using the provided script and return the generated ZIP structure to your maintainer hook.

> **Note:** Issues and Pull Requests are not actively monitored on this repository. All communication and crash dump submissions must happen via the direct Bug Report ZIP payload system.
