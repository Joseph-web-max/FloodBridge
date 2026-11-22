# FloodBridge deployment

1. Create a Supabase project. In the SQL Editor run `supabase/schema.sql`.
2. In Authentication settings choose your sign-up policy (invite-only is recommended for operational use).
3. Edit `config.js`: set `supabaseUrl` and `supabaseAnonKey` (public anon/publishable key only, never service_role).
4. Publish with GitHub Pages (Settings -> Pages -> Source: GitHub Actions) and open the HTTPS site.
5. First administrator: sign up, sign in, **Settings & team -> Create organisation**.
6. Share the join code privately. New members join as **viewer** (read-only); promote to **editor** to let them submit and verify reports.
7. Register sites with thresholds supplied by the competent authority, assign each sensor to a site in **Sensor connections**, and calibrate against a staff gauge.

## Roles
- admin: manage members and join code, read/write.
- editor: submit, verify, edit and delete records.
- viewer: read-only.

## Notes
- Records are stored as JSON in the `data` column of `fb_sites`, `fb_observations`, `fb_assets`, `fb_telemetry` (see DATA-DICTIONARY.md for fields).
- Sensor data enters via the browser (USB/BLE) of a signed-in editor; the bridge is not an authenticated device channel (see TELEMETRY-PROTOCOL.md).
- A browser tab must stay open for alerts and sensor ingestion.
