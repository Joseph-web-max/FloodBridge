# FloodBridge system architecture

## Proposed evidence flow

1. **Observe:** a person or water-level node records a time-stamped observation with coordinates and source metadata.
2. **Preserve:** local-first web client stores the report and source details.
3. **Quality-check:** the interface labels records as fresh, aging or expired. Multiple submissions can be shown as corroborated or conflicting; this is not proof of independent observers.
4. **Connect impact:** local teams manually link monitored crossing sites to critical facilities. The dashboard highlights potential dependency impacts, not computed road reachability.
5. **Contextualise:** Open-Meteo precipitation forecast may provide rainfall context. It does not forecast a specific river stage or establish passability.
6. **Respond:** authorised human decision-makers consult official bulletins and field teams before issuing closures, warnings or response actions.

## Data sources and interfaces
- Browser geolocation: device permission-based.
- OpenStreetMap: map tiles for display; see OSM tile usage policy before high-volume institutional deployment.
- Open-Meteo: forecast precipitation and precipitation probability.
- ESP32 prototype: BLE NUS notifications or newline-delimited JSON over USB Serial.
- Local storage: browser-local database for prototype only.

## Future production services
A production deployment would require authenticated API services, per-organisation access controls, encrypted transport, server-side event log, retention/deletion policies, backups, audit trails, abuse prevention, rate limits, role-based validation and monitoring. Use official data-sharing agreements for agency feeds and emergency notification channels.

## Failure handling
- No forecast response: retain observations; do not infer no flood risk.
- No sensor data: show last reading timestamp and stale state; do not reuse it as live.
- Conflicting reports: show conflict; never auto-resolve to safe.
- Missing coordinates / datum: retain as unlocated or unreferenced; do not create false geospatial precision.
- Connectivity loss: use local form records; basemap and live forecast may be unavailable.
