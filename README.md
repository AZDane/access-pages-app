# Access Pages for Home Assistant

This is the public Home Assistant App Store repository for **Access Pages 0.1.125 owner-only diagnostic beta**. Access Pages shares selected Home Assistant controls through expiring, revocable guest links using LayerV qURL/NHP. A LayerV account and dedicated management API key are required.

**0.1.125 is approved for owner-only diagnostic testing. It is not approved for external beta users until [HA125-OBS-001](https://github.com/AZDane/access-pages/issues/12) is closed and real LayerV acceptance is complete.** The initial owner cycle is one hour with up to two continuously visible guests, followed by a review of actual HA journal/storage growth. The historical 0.1.124 guest timeout remains unresolved.

Add `https://github.com/AZDane/access-pages-app` under **Settings → Apps → App store → Repositories** in Home Assistant, then install **Access Pages**. The App supports Home Assistant OS and Supervised installations.

- [Installation and operating documentation](access_pages/DOCS.md)
- [App changelog](access_pages/CHANGELOG.md)
- [Application source](https://github.com/AZDane/access-pages)
- [Private vulnerability reporting](https://github.com/AZDane/access-pages/security/advisories/new)

The App uses the versioned beta image `ghcr.io/azdane/access-pages-app:0.1.125`.
