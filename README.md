# Access Pages for Home Assistant

Access Pages gives temporary guests access to a small, explicitly approved part
of Home Assistant without making Home Assistant or the home network publicly
reachable. Guests receive a purpose-built page with only the devices,
information, and controls they need, without a Home Assistant account, password,
or VPN access. No inbound router port needs to be opened.

Home Assistant, its devices, and its administrative interface remain inside the
home, preserving its local-first model.

## The protected path and guest capabilities

Remote guest connectivity uses [LayerV](https://layerv.ai) and the
**Network-Infrastructure Hiding Protocol (NHP)**. NHP follows an
**authenticate-before-connect** model: the protected endpoint remains invisible
and unreachable until access has been cryptographically verified. A valid qURL
opens the protected NHP/FRP path.

NHP is the open-source network-hiding technology developed by OpenNHP. The
LayerV team are core builders of OpenNHP, and its founding team co-authored the
Cloud Security Alliance (CSA) NHP specification. LayerV provides the external
managed NHP/qURL connectivity service and developer tools currently used by
Access Pages. The protocol is also documented in an IETF Internet-Draft. See
[LayerV's OpenNHP standards page](https://layerv.ai/standards/) for this history.

Access Pages is independently developed open-source software. Its Gateway
independently determines and enforces the Home Assistant capabilities available
after admission. The browser cannot obtain more capabilities by changing its
requests. Guest pages do not expose the regular Home Assistant dashboard,
configuration, history, or unrelated entities.

Depending on the integrated devices and categories enabled by the owner, a
page can offer selected lights, temperature readings and thermostat controls,
music controls, or read-only camera stills. Additional supported actions, such
as unlocking a selected door, require the owner's deliberate selection.

Each guest has an independent grant with expiration and individual revocation.
Optional email-code verification, proximity requirements for actions, guest
activity records, security events, and administrator alerts provide additional
controls. Proximity is an accidental-action safeguard, not proof of physical
presence.

## What it looks like

The owner creates purpose-specific pages and selects the entities and actions
each guest can use.

![Access Pages administration showing purpose-specific Home Assistant access pages](https://raw.githubusercontent.com/AZDane/access-pages/30ad2605ce7f4f0f4cc536fd1f4fb705041a991d/docs/images/admin.png)

The guest sees only the controls approved for that page.

![Access Pages guest view showing limited vacation-rental controls](https://raw.githubusercontent.com/AZDane/access-pages/30ad2605ce7f4f0f4cc536fd1f4fb705041a991d/docs/images/guest.png)

## Owner responsibility

Home Assistant owners control what guests can access and are responsible
for deciding what is appropriate and safe for their installation. Home
Assistant is highly customizable: entities and actions can control
physical equipment, locks, doors, gates, appliances, security equipment,
or other systems where unintended operation has real-world consequences.
Access Pages cannot determine whether an entity or action is safe for
guest use. Owners must review what each entity actually controls, the
actions they expose, and whether the available protections are appropriate.

The App defaults to `include_domains: "light"`, enabling only the Light
category. The owner must explicitly enable additional supported categories
in this setting before selecting them for guest pages. This is a
conservative configuration default, not a guarantee that any entity is safe.
Entity categories are configuration aids, not safety classifications;
even a `light` entity is not inherently safe.

Treat qURLs as access credentials. Once a qURL is provided for sharing,
Access Pages cannot control how an owner or guest stores, transmits,
forwards, screenshots, publishes, or otherwise distributes it. Someone
who obtains a valid qURL may be able to reach the associated guest access,
subject to any additional protections configured by the owner.

The owner is responsible for deciding who receives a qURL, how it is
distributed, how long access remains valid, and whether protections such
as email verification, proximity requirements for actions, expiration,
or revocation are appropriate.

## Installation and current release

This is the public Home Assistant App Store repository for **Access Pages 0.1.132**. Access Pages shares selected Home Assistant controls through expiring, revocable guest links using [LayerV](https://layerv.ai) qURL/NHP. [A LayerV account and dedicated management API key](https://layerv.ai/qurl/dashboard/keys/) are required.

**0.1.132 starts with only the Light category enabled** (`include_domains: "light"`), including when a saved setting is empty. Explicitly add other Home Assistant domains before selecting their entities for guest pages. Area filters narrow the enabled domains and cannot enable other categories. Entity categories are configuration aids, not safety classifications; owners remain responsible for reviewing what each entity controls and how guest qURLs are shared.

Existing saved pages and guest access remain intact. Before saving an existing page again, enable its non-light domains or remove those controls. This release retains qURL CLI 3.0.0 with [LayerV](https://layerv.ai) Connector 0.14.1, saved Home Assistant settings, administrator configuration and Connector identity. No guest-link migration or automatic identity reset is introduced.

Back up the App and stop the old version completely before updating through Home Assistant. Existing guest links have no compatibility guarantee; revoke unwanted guests through the normal controls, allow durable remote cleanup to finish, and create new invitations as needed. Do not delete the ownership lock or reset the account/Connector merely to upgrade. Follow the [installation and recovery instructions](access_pages/DOCS.md#upgrading-to-qurl-300).

All required source checks and AMD64/ARM64 build and runtime probes passed. Live Home Assistant/[LayerV](https://layerv.ai) and phone acceptance remain unperformed; publication does not mean those checks have passed. With temporary diagnostic capture Off, verify fresh guest publication, a harmless action followed by fresh state, expiry, individual/bulk revocation, warm restart and mobile/network reconnect using disposable guests. Check the target appliance's AppArmor audit logs. The historical timeout is not claimed resolved.

The native **Temporary diagnostic capture request** option explains its one-shot behavior. To capture an issue, choose 30 minutes, save and restart. New `ap_diag` records include UTC timestamps. Use the App's Logs and Download logs controls. Capture expires automatically; the saved duration is not runtime status. Restarting a consumed selection must not restart capture. Re-arm by choosing Off, saving and restarting, then choosing a duration, saving and restarting again.

Diagnostic output remains bounded. An unsampled request that hangs without a detected failure may leave no useful early-boundary evidence. See the [0.1.128 acceptance notes](https://github.com/AZDane/access-pages/releases/tag/v0.1.128) and [operating documentation](access_pages/DOCS.md) for remaining acceptance checks and diagnostic limitations.

Add `https://github.com/AZDane/access-pages-app` under **Settings → Apps → App store → Repositories** in Home Assistant, then install or update **Access Pages**. The App supports Home Assistant OS and Supervised installations on amd64 and aarch64.

- [Installation and operating documentation](access_pages/DOCS.md)
- [App changelog](access_pages/CHANGELOG.md)
- [Application source](https://github.com/AZDane/access-pages)
- [Private vulnerability reporting](https://github.com/AZDane/access-pages/security/advisories/new)

The App uses the versioned image `ghcr.io/azdane/access-pages-app:0.1.132`. This normal release also updates the latest image tags; existing versioned images remain available. See the [0.1.132 release notes](https://github.com/AZDane/access-pages/releases/tag/v0.1.132).
