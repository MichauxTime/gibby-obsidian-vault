---
type: requirement-hub
domain: commissary
status: living
created: 2026-06-16
tags: [streetlegal, requirements, commissary, kitchens]
---

# Commissary Kitchen Requirements

Cross-jurisdiction hub for the commissary / commercial-kitchen rule — the single biggest tie-in to our kitchen marketplace.

## Universal layer (true almost everywhere)
- Most jurisdictions **prohibit operating a food truck out of a home kitchen** and require the truck to be based out of an approved **commissary / commercial kitchen** for food prep, water/waste servicing, and overnight storage.
- The health permit application commonly requires a **signed commissary agreement / letter of agreement** naming the approved facility before the permit is issued.
- The commissary itself must typically be a **health-department-permitted** facility.

## Variation layer (what differs by jurisdiction)
- Some cities require a commissary **by name on the application**; some accept a self-certified arrangement; a few have no formal requirement.
- Servicing-frequency and waste-disposal rules vary.
- "Commissary" definitions differ — some accept shared/commercial kitchens, some require a dedicated mobile-unit servicing area.
- → Specifics live in the city/state guides; link them here as we confirm each (e.g. [[Austin TX Guide]], [[Houston TX Guide]]).

## Why this is strategic
- **No competitor connects permits → commissary kitchens.** This requirement is precisely where StreetLegal's marketplace becomes the moat: the city guide says "you need a commissary," and we hand them the list.
- Feeds: [[StreetLegal Kitchen & Truck Marketplace]] (claim/upsell), kitchen profiles, "send my kitchen to every new truck" trigger.

## Source of truth
- Per-city specifics: city guides + auto-fill mappings + permit-grades.
- Live kitchen data: EC2 Postgres `kitchens` table.

## Related
- [[Permit Requirements (MOC)]] · [[00 Canon]] · [[StreetLegal Kitchen & Truck Marketplace]] · [[Insurance Requirements]]
