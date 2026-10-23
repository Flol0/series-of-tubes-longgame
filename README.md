# Series of Tubes · Long Game
Experimental extension of https://github.com/fjaeckel/seriesoftubes (upstream 1.9.0). Original game and assets by fjaeckel; original source attribution retained in the game. This is an independent test build.

Run `npm ci`, `npm test`, `npm run build`. `site/` is editable source; `dist/` is the hosted static build.

The pink Unternehmen button opens seven new German-language management views. The original map, routing and UI remain available. Saves use browser-local storage; original JSON export/import remains available. Opening a management dialog pauses simulation.

Implemented: three simulated competing providers with expansion, topology and bidding; contract terms, delivery deadlines, SLA credits, growth and renewal; city demand profiles and advance market news; staged wave-upgrade and diversity projects; shared-risk failure drills; teams, repair automation and six strategies with annual goals. Existing wave-upgrade actions now create projects. Invalid no-subsea contracts are repaired without reducing the agreed customer rate.

Experimental abstractions: rivals have simplified economics and networks, rather than the full player routing engine. Traffic profiles aggregate time periods into game days. Shared-risk projects model route independence at group level; building and power failures use upstream mechanics. Physical route feasibility follows the game's land model and does not claim real-world carrier availability. Balance requires extended human playtesting. Real iPhone Safari testing is still needed; browser interaction and automated simulation tests are used here.

## Long Game 0.2
- Mobile bottom navigation, city search, route selection without dragging, expandable inspector sheets and 44px touch controls. Phone and landscape styles respect safe areas.
- Regional pricing affects customer growth and revenue; tariff changes have a 30-day lock.
- Bridge waves provide actual temporary capacity, pay higher rent and expire after 30 days unless extended. They share the parent's physical failure group.
- Scheduled maintenance takes only the selected line out for one day. Optical wave hardware older than 360 days has a small additional failure risk. Field service mitigates it.
- Projects can be cancelled after confirmation, refunding the unbuilt budget less a cancellation charge.
- Demand scenarios include signed starts and expected customer growth; financial scenarios explicitly hold current monthly profit constant.

## Original Unreleased coverage
All nine items from the inherited upstream CHANGELOG Unreleased section were already in the source used for this fork: split ports across sites, laptop HUD layout, corrected 800G/1.6T router tiers, North Sea cables and subsea dark fiber leases, own IX fabric upgrades, regional wave pricing, Cairo/Dubai and I-ME-WE-Us cables, Gulf cities/licences/incidents, and tablet layout. Existing upstream region tests verify the functional items.

## GitHub Pages
Production domain: https://tubes.krieger.pm/

In Settings → Pages select GitHub Actions, set the custom domain to `tubes.krieger.pm`, then enable HTTPS after certificate issuance. Pushes to main test, build and publish automatically. Restrict the Pages environment to main.

Cloudflare: CNAME `tubes` → `flol0.github.io`, DNS only (grey cloud), TTL Auto. No DNS API secrets required.

Pages is public. Saves are browser- and origin-local; export on the previous test host and import on the new domain to transfer progress.
