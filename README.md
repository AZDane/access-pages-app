# Access Pages for Home Assistant

This is the public Home Assistant App Store repository for **Access Pages 0.1.126 owner-only acceptance prerelease**. Access Pages shares selected Home Assistant controls through expiring, revocable guest links using LayerV qURL/NHP. A LayerV account and dedicated management API key are required.

**0.1.126 is approved only for owner testing on HA-Nova. It is not approved for general or external beta.** External-beta promotion requires the owner's live results and a separate readiness decision. The historical September 22 timeout remains unresolved and is not claimed fixed.

Start with Diagnostic logging Off. After the normal backup and update, verify existing invitations and sessions, then run approximately ten minutes with one visible guest and ten minutes with two. Healthy polling should produce zero persistent request diagnostics and zero routine Admin callback access-log lines. Temporary diagnostics use native App Logs and Download Log; verify capture expiration and unchanged-selection restart staying off. See the [owner prerelease notes](https://github.com/AZDane/access-pages/releases/tag/v0.1.126) for the acceptance procedure.

**Known inherited limitation:** stderr already full before process startup can block the Gateway's synchronous startup message. This also existed in 0.1.125 and remains open for post-acceptance review and external-beta readiness. It is not fixed by this release.

Add `https://github.com/AZDane/access-pages-app` under **Settings → Apps → App store → Repositories** in Home Assistant, then install **Access Pages**. The App supports Home Assistant OS and Supervised installations.

- [Installation and operating documentation](access_pages/DOCS.md)
- [App changelog](access_pages/CHANGELOG.md)
- [Application source](https://github.com/AZDane/access-pages)
- [Private vulnerability reporting](https://github.com/AZDane/access-pages/security/advisories/new)

The App uses the versioned prerelease image `ghcr.io/azdane/access-pages-app:0.1.126`. This public repository's owner-only designation is an acceptance restriction, not private distribution.
