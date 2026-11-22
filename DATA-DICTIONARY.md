# FloodBridge data dictionary

| Entity / field | Meaning |
|---|---|
| Site `id` | Local unique monitored-site ID |
| Site `name`, `type` | Site label and category |
| Site `lat`, `lon` | WGS84 location |
| Site `datum` | Optional surveyed local gauge datum reference |
| `watchLevel`, `alertLevel`, `actionLevel` | Optional site thresholds; must be supplied by competent authority |
| Observation `id` | Unique observation ID |
| Observation `type` | Crossing, water level, flood extent, drainage or damage |
| `siteId` | Linked monitored site, if known |
| `passability` | Reported clear / caution / blocked / unknown; not an official status |
| `depthCm` | Road water depth only when safely and validly measured |
| `stageM` | Water level relative to a documented local datum |
| `source` | Community, trained field team, device, manually attributed official bulletin |
| `lat`, `lon` | WGS84 observation coordinates |
| `observedAt` | Time the observation was made |
| `observer` | Optional pseudonymous observer code |
| `notes` | User's observations and limitations |
| Asset `dependency` | Manually configured crossing site linked to an essential-service asset |
| Telemetry `distance_cm` | Sensor-to-water surface distance, if valid |
| Telemetry `stage_m` | Gauge-relative stage, only if sensor mounting height was surveyed |
| `receivedAt` | Browser receipt time; not necessarily sensor creation time |

## Status interpretation
- Fresh: within 120 minutes in this prototype.
- Aging: over 120 and up to 360 minutes old.
- Expired: over 360 minutes old.
These are interface defaults, not universal flood-report validity periods. Pilot teams must configure periods by hazard, site and operational context.
