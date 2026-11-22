# FloodBridge changelog

## Version 1.0
- Single-file offline-first web client.
- Monitored-site registry and geospatial map.
- Community / field / manual bulletin observation capture.
- Freshness and conflict display for observations.
- Essential-service assets with manually mapped dependencies.
- Open-Meteo precipitation forecast integration.
- OpenStreetMap basemap through Leaflet.
- Browser geolocation.
- CSV and JSON exports.
- Generic ESP32 BLE NUS / USB serial telemetry receiver.
- ESP32 JSN-SR04T demonstrator firmware and safety documentation.

## Version 1.1
- Removed demo data. Added Supabase auth, organisations, roles (admin/editor/viewer) and Row Level Security.
- Offline-safe sync queue with retry; realtime updates between users.
- Site/asset edit and delete; observation verify/reject/delete; filters; backup restore.
- Fixed device-to-site linking bug (firmware placeholder site_id overriding the selected site).
- Telemetry throttling, range validation, device registry, auto-reconnect.
- Multi-site rainfall forecast, asset map markers, in-app alert banner, browser notifications.
- Settings & team page with configurable freshness windows.
