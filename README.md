# Access Pages for Home Assistant

This is the public Home Assistant App Store repository for **Access Pages 0.1.127 owner-only acceptance prerelease**. Access Pages shares selected Home Assistant controls through expiring, revocable guest links using LayerV qURL/NHP. A LayerV account and dedicated management API key are required.

**0.1.127 is approved only for owner testing on HA-Nova. It is not approved for general or external beta.** Further promotion and the stable development baseline decision require the owner's live results and a separate readiness assessment. The historical September 22 timeout remains unresolved and is not claimed fixed. Version 0.1.126 remains available as the live diagnostic-policy reference.

After the normal backup, update from 0.1.126 with Diagnostic logging Off. Verify existing invitations/sessions, guest verification, harmless actions, and healthy single-guest polling with zero request diagnostics and zero routine callback access-log lines.

Then enable 30-minute Diagnostic logging and restart. Keep one guest continuously visible for at least five minutes and perform a harmless action. Expect approximately one complete final Gateway timing summary per request, occasional sampled pre-blocking records, and no systematic loss growth that routinely suppresses final summaries. Verify native App Logs and Download Log. Allow capture to expire while polling continues; verify healthy silence resumes and an unchanged selection does not reactivate after restart. See the [owner prerelease notes](https://github.com/AZDane/access-pages/releases/tag/v0.1.127).

**Accepted diagnostic limitation:** an unsampled request that hangs indefinitely without a detected failure may leave no useful early-boundary evidence. Reproduction may be necessary; no history, watchdog, collector, or tracing infrastructure is added.

**Separate inherited limitation:** stderr already full before process startup can block the Gateway's synchronous startup message. This also existed in 0.1.125 and remains open for a separate external-beta readiness assessment. It is not fixed by this release.

Add `https://github.com/AZDane/access-pages-app` under **Settings → Apps → App store → Repositories** in Home Assistant, then install **Access Pages**. The App supports Home Assistant OS and Supervised installations.

- [Installation and operating documentation](access_pages/DOCS.md)
- [App changelog](access_pages/CHANGELOG.md)
- [Application source](https://github.com/AZDane/access-pages)
- [Private vulnerability reporting](https://github.com/AZDane/access-pages/security/advisories/new)

The App uses the versioned prerelease image `ghcr.io/azdane/access-pages-app:0.1.127`. This public repository's owner-only designation is an acceptance restriction, not private distribution.
