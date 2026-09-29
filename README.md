# Access Pages for Home Assistant

This is the public Home Assistant App Store repository for **Access Pages 0.1.131**. Access Pages shares selected Home Assistant controls through expiring, revocable guest links using LayerV qURL/NHP. A LayerV account and dedicated management API key are required.

**0.1.131 upgrades to qURL CLI 3.0.0 with LayerV Connector 0.14.1.** It retains account-based onboarding, explicit Agent enrollment, sealed credentials, external supervision and per-share isolation. Daemon health checks now verify process ownership, startup/shutdown handle the new lifetime lock, and the packaged CA trust store is checked for verified tunnel TLS. Saved Access Pages, Home Assistant settings, administrator configuration and Connector identity are preserved. No guest-link migration or automatic identity reset is introduced.

Back up the App and stop the old version completely before updating through Home Assistant. Existing guest links have no compatibility guarantee; revoke unwanted guests through the normal controls, allow durable remote cleanup to finish, and create new invitations as needed. Do not delete the ownership lock or reset the account/Connector merely to upgrade. Follow the [installation and recovery instructions](access_pages/DOCS.md#upgrading-to-qurl-300).

All required source checks and AMD64/ARM64 build and runtime probes passed. Live Home Assistant/LayerV and phone acceptance remain unperformed; publication does not mean those checks have passed. With temporary diagnostic capture Off, verify fresh guest publication, a harmless action followed by fresh state, expiry, individual/bulk revocation, warm restart and mobile/network reconnect using disposable guests. Check the target appliance's AppArmor audit logs. The historical timeout is not claimed resolved.

The native **Temporary diagnostic capture request** option explains its one-shot behavior. To capture an issue, choose 30 minutes, save and restart. New `ap_diag` records include UTC timestamps. Use the App's Logs and Download logs controls. Capture expires automatically; the saved duration is not runtime status. Restarting a consumed selection must not restart capture. Re-arm by choosing Off, saving and restarting, then choosing a duration, saving and restarting again.

Diagnostic output remains bounded. An unsampled request that hangs without a detected failure may leave no useful early-boundary evidence. See the [0.1.128 acceptance notes](https://github.com/AZDane/access-pages/releases/tag/v0.1.128) and [operating documentation](access_pages/DOCS.md) for remaining acceptance checks and diagnostic limitations.

Add `https://github.com/AZDane/access-pages-app` under **Settings → Apps → App store → Repositories** in Home Assistant, then install or update **Access Pages**. The App supports Home Assistant OS and Supervised installations on amd64 and aarch64.

- [Installation and operating documentation](access_pages/DOCS.md)
- [App changelog](access_pages/CHANGELOG.md)
- [Application source](https://github.com/AZDane/access-pages)
- [Private vulnerability reporting](https://github.com/AZDane/access-pages/security/advisories/new)

The App uses the versioned image `ghcr.io/azdane/access-pages-app:0.1.131`. This normal release also updates the latest image tags; existing versioned images remain available. See the [0.1.131 release notes](https://github.com/AZDane/access-pages/releases/tag/v0.1.131).
