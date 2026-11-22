# Safety, privacy and governance safeguards

## Hazard communication
- FloodBridge is not an official alert issuer.
- A blank map or lack of recent reports never means a crossing is safe.
- An observation must display time, source and freshness.
- Conflicting reports should remain visible as a conflict until a competent person resolves them.
- User-generated reports must not be re-labelled as official warnings.
- Emergency numbers, evacuation orders and closure decisions must come from the relevant local authority.

## Physical safety
- Never enter floodwater to measure depth or test a crossing.
- Do not operate near fast-flowing water, unstable banks, bridge edges, culverts or lightning.
- Install sensors only with site permission, a safe-work plan and competent engineering oversight.
- Protect electronics in suitable enclosures and design for lightning, surge, corrosion and vandalism with qualified professionals.
- The included hobby ultrasonic module is for controlled demonstration, not unattended public-safety deployment.

## Privacy
- Prefer pseudonymous team codes to personal names.
- Do not collect phone numbers or precise home locations by default.
- Avoid publishing reporter identity, shelter occupancy, vulnerable household data or rescue locations.
- Define retention, deletion, access and lawful basis before institutional deployment.
- Browser localStorage is not encrypted institutional storage.

## Security
- Current prototype has no login, role management, tamper-proof records or server-side audit log.
- BLE/serial readings are unauthenticated and can be spoofed or corrupted.
- Treat incoming values as untrusted; validate units and source provenance.
- Production system requires signed device identity, transport encryption, access controls, monitoring and security review.
