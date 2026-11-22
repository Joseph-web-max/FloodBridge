# Known limitations — FloodBridge 1.0

1. Local browser storage only. No hosted backend, multi-user sync, institutional accounts or durable audit log.
2. OpenStreetMap base tiles require connectivity; no offline map bundle is included. Respect provider tile policies and use an approved tile provider for production.
3. Open-Meteo supplies weather forecast variables. Rainfall forecast is not a river-stage forecast, flood inundation map or passability decision.
4. Browser geolocation requires permission and may be inaccurate, especially indoors or on low-end devices.
5. Community observations are self-reported. The prototype does not verify identity or independent corroboration.
6. “Corroborated” is a count-based display hint only. Multiple accounts can be controlled by one person.
7. The dependency model is manually configured. The software does not calculate road-network reachability or alternate routes.
8. No official agency warning feed, closure feed, SMS, WhatsApp, USSD, emergency dispatch or rescue integration is configured.
9. ESP32 + JSN-SR04T sketch is a hobby demonstrator, not a calibrated or certified gauge.
10. Sensor distance requires a stable surface, unobstructed beam and correct sensor configuration. Waves, foam, debris, rain, condensation and mounting movement can cause erroneous results.
11. Stage calculation requires surveyed sensor-to-datum height. It is intentionally disabled by default.
12. Local thresholds are not preloaded and must be supplied by competent site authorities. Raw stage is not automatically converted into crossing safety.
13. Serial/BLE data are unauthenticated. No cryptographic device identity.
14. No hardware has been assembled, compiled, calibrated or field-tested by this package.
15. This platform is not an official alert system, engineering safety certification or substitute for emergency instructions.

## V1.1 additions
- Sensor ingestion depends on a browser tab connected to the device; there is no headless gateway.
- Notifications work only while a tab is open; there is no SMS or push service.
- Public/anonymous community submission is not included (reports require an account in the organisation).
- Freshness windows are per device settings, not organisation-wide.
- Users belonging to several organisations are attached to the first (or last used) one.
