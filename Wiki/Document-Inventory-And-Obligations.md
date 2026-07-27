# Document Inventory and Obligations

## Purpose
A single cross-document view of what Buoy's legal documents collectively commit to — data collected, retained, shared, and user rights/obligations — that neither the privacy policy nor the terms of service gives on its own.

## Key understanding

### Data collected and stored

**Fact** (source: `privacy-policy/index.html` §1): The following are stored in Supabase:
- Email address (from Apple/Google sign-in; may be Apple's private relay address)
- Account UUID
- Dog name (free text, 1–24 chars; shown to other users at the same park)
- Avatar selection (one of a fixed set of in-app silhouettes; no photos)
- Check-in records: `(account_id, park_id, status, created_time, expiry_time)` — no coordinate column
- Measurement records: `(account_id, park_id, time, status, count_of_others_present)` — no coordinate column; retained up to 180 days; never shown in-app
- Invite records: `(two account IDs, park, time)` — visible only to the two parties
- Block records: one-directional; blocked party not notified
- Report records: reason (preset or free text) and any user-written text
- Push notification tokens

**Fact** (source: `privacy-policy/index.html` §1, "What we do not collect"): Not collected or stored — photos, human name, phone number, contacts/address book, analytics identifiers, advertising identifiers, background location, coordinates at any point in the stack, payment information.

**Fact** (source: `privacy-policy/index.html` §1, "Precise location"): GPS coordinates leave the device only for a geofence check ("I'm here") or a nearby-park query; they are used to compute a result and then discarded — never written to any database.

### Data retention schedule

**Fact** (source: `privacy-policy/index.html` §4):
- *here* check-ins auto-expire after **90 minutes**; *heading* after **30 minutes** (cleanup job every 5 minutes)
- Measurement records (visit-level, no coordinates): retained up to **180 days**, then auto-deleted
- Profile, invites, blocks, reports, push tokens: persist until user deletion or account deletion
- Account deletion: immediate, permanent, cascades to profile + presences + invites + blocks + reports + push tokens; no grace period

### Third-party processors and data shared

**Fact** (source: `privacy-policy/index.html` §3):
| Provider | What they receive |
|---|---|
| Supabase (US East) | Everything stored in §1 |
| Apple (Sign in with Apple) | Sign-in flow |
| Google (Google Sign-In) | Sign-in flow |
| Expo Push / APNs / FCM | Push token + invite notification content (dog name + park name) |
| OpenStreetMap | Approximate map view + device IP address (no account identity) |

**Fact** (source: `privacy-policy/index.html` §3): Invite push notifications carry sender dog name and park name and pass through Expo's and Apple's/Google's systems; the sender's account ID is deliberately excluded.

**Fact** (source: `privacy-policy/index.html` §2): Data is not sold and is not used for advertising or cross-app tracking.

### User rights and controls

**Fact** (source: `privacy-policy/index.html` §5):
- Ghost mode: go invisible, create no presence
- Block: removes another user from your views immediately
- Delete account: in-app, immediate and permanent
- Export data: in-app JSON export of profile, check-in history (including expired), invites, blocks created, reports filed, push tokens. The sign-in email held by the auth provider is NOT included in this export; must be requested directly.
- Notifications and location: controllable in device settings

**Fact** (source: `privacy-policy/index.html` §5): Users in EEA/UK or California may have additional statutory rights; the in-app delete + export are stated to cover most of these.

### User obligations under Terms of Service

**Fact** (source: `terms-of-service/index.html` §2): Users must be at least **18** years old and legally capable of forming a contract.

**Fact** (source: `terms-of-service/index.html` §4): Prohibited uses include harassment/stalking/threatening, using presence information to track someone against their wishes, evading a block, impersonation, commercial solicitation or spam, probing/scraping/reverse-engineering the service or circumventing the server-side geofence.

**Fact** (source: `terms-of-service/index.html` §5): Buoy does not vet or background-check users. Any decision to meet or share space with another user is the user's own responsibility and risk.

**Fact** (source: `terms-of-service/index.html` §8): User retains ownership of their minimal content (dog name, avatar choice) and grants Buoy a limited license to host and display it for service operation.

**Fact** (source: `terms-of-service/index.html` §10): Liability cap is the greater of USD 100 or amounts paid in the prior 12 months — effectively $0 during v0 (Buoy is free).

**Fact** (source: `terms-of-service/index.html` §13): Governing law is Illinois; disputes go to Cook County state or federal courts.

### Cross-document observations

**Inference** (rests on reading both documents together): The privacy policy and terms of service are cross-linked via footer navigation in the rendered HTML and via in-text links (e.g., ToS §3 and §7 link to the privacy policy). They are designed to be read together; the ToS defers to the privacy policy on data handling specifics.

**Inference** (rests on `terms-of-service/index.html` §12 and `privacy-policy/index.html` §8): Both documents use the same update mechanism: change the "Effective date" and notify in-app for material changes. Neither document specifies a minimum notice period.

**Unresolved** (flagged in HANDOFF.md): The upstream source docs in `DogHood/docs/legal/` carry `status: draft` in their front matter (last_updated 2026-07-11) while the rendered copies here are live with effective date 2026-07-11. Whether the published copies match the final upstream text is unconfirmed.

## Sources
- [privacy-policy/index.html](../privacy-policy/index.html)
- [terms-of-service/index.html](../terms-of-service/index.html)

## Uncertainties & contradictions
- **Unresolved:** Upstream source documents (`DogHood/docs/legal/privacy-policy.md`, `terms-of-service.md`) carry `status: draft` while the rendered copies are live. Parity between source and rendered is unconfirmed.
- **Unresolved:** Neither document specifies a minimum advance-notice period before changes take effect — only that the effective date will be updated and in-app notification will be given for material changes.

## Related pages
- [History](History.md)
- [Publishing-Model](Publishing-Model.md)

## Relevance to current work
This repo is in maintenance mode; the next real work is a re-render when upstream legal docs change. This page serves as a reference to verify that re-rendered content remains consistent with the obligations documented here — particularly the data-not-collected list, the 90/30-minute expiry windows, and the 180-day measurement record retention, all of which must stay in sync with any upstream edit.

_Last reviewed: 2026-07-26_
