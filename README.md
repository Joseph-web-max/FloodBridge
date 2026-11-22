# FloodBridge — GitHub Release

**FloodBridge is a flood-impact and safe-access evidence platform for organisations.** It connects community observations and local water-level readings to monitored crossing sites and manually mapped essential-service dependencies.

## Download / run
1. Upload the contents of this folder to a new GitHub repository.
2. Enable GitHub Pages in **Settings → Pages** (deploy from the main branch and repository root).
3. Open the published HTTPS website.
4. Run `supabase/schema.sql` in your Supabase project, put the project URL and anon key in `config.js`, then sign in, create your organisation and add monitored sites. See `docs/DEPLOYMENT.md`.

## Included
- `index.html` — single-file web application.
- OpenStreetMap map tiles through Leaflet (internet required for basemap).
- `supabase/schema.sql`, `config.js`, GitHub Pages workflow.
- Open-Meteo forecast API integration for forecast rainfall (not a flood-stage forecast).
- Browser geolocation (permission required).
- Supabase sign-in, organisations and roles (admin / editor / viewer), realtime shared records, offline-safe sync queue, CSV/JSON export and backup restore.
- Web Bluetooth Nordic UART Service and optional Web Serial telemetry receivers.
- ESP32 JSN-SR04T demonstration firmware.
- Hardware wiring, deployment safety, data protocol and validation documentation.

## What it does
- Register crossing / gauge / drainage locations.
- Submit time-stamped observations with coordinates and condition.
- Separate fresh, aging and expired reports.
- Show multiple matching reports as corroborated submissions and conflicting reports separately.
- Record stage telemetry and link crossing sites to critical facilities.
- Fetch hourly precipitation forecasts for selected coordinates.
- Export locally stored evidence.

## What it does not do
- It is not an official warning service and does not notify emergency agencies.
- It does not certify that roads, bridges or crossings are safe.
- It does not infer flood depths or river stages from rainfall forecasts.
- It does not provide an authoritative road-closure feed or a road-network route planner.
- It does not replace Kenya Meteorological Department, Water Resources Authority, county authorities or other official sources.
- It has no audit-grade logging, SSO, public (anonymous) report submission or SMS/emergency-dispatch integration. Access control is organisation-level roles enforced by Supabase Row Level Security.

## Distinctiveness and prior work
Community flood reporting and official flood early-warning systems already exist. FloodNavigator is a community-driven flood information project for Accra. UNESCO and partners launched a flood early-warning system for the Tana River Basin in Kenya in 2026. FloodBridge therefore makes no claim that flood alerts or crowdsourced maps are new. Its research hypothesis is the operational evidence-to-access layer: freshness/conflict handling, sensor provenance and manually mapped lifeline dependencies in a lightweight workflow.

## Sensor node
The ESP32 sketch is a water-level sensor node for an ultrasonic water-level sensor. It emits JSONL over USB serial and BLE NUS. It measures distance to the water surface; stage is calculated only when a surveyed sensor-to-gauge-datum height is configured. It is not a certified hydrological gauge. Compare against a staff gauge and calibrate on-site before any operational use.

## Safety
Never enter floodwater or approach a hazardous crossing to collect data. Never install equipment from a bridge edge or within a flood channel without a competent installation team, safe-work plan and engineered mounting. Thresholds must be site-specific and set by qualified local authorities. The application intentionally does not translate rainfall or raw stage readings into an automatic crossing-safe status.

## Data and privacy
Records are kept in this browser and, when signed in to an organisation, synced to your Supabase project. Export JSON backups. Avoid storing names, phone numbers, exact household locations or sensitive personal information unless there is a lawful, approved operational need.

## Suggested validation partners (prospects only)
JKUAT, Kenya Meteorological Department, Water Resources Authority, KeNHA, KURA, county disaster-management teams, Kenya Red Cross, humanitarian mapping communities and qualified hydrologists. No partnership or endorsement is implied.

## Status
Production web client (V1.1). The sensor firmware has not been field-calibrated; calibrate against a staff gauge before operational use. No agency data feed, SMS gateway, emergency dispatch connection or institutional partnership is configured.

## What changed in V1.1
- Demo mode removed; legacy demo records are purged on load.
- Sign-in, organisations, roles and realtime shared data; read-only viewers.
- Edit and delete for sites and assets; verify / reject / delete for observations.
- Sensor readings now link to the selected site. Previously the firmware's placeholder `site_id` overrode the chosen site, so threshold status never updated.
- Device readings create an observation only on a status change or every 15 minutes (no flooding), with range checks and a device registry showing online/offline.
- Forecast rainfall for every site in one request; map shows lifeline assets; browser alerts; USB/BLE auto-reconnect.
