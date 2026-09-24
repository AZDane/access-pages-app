# Access Pages for Home Assistant

This is the public Home Assistant App Store repository for **Access Pages 0.1.129**. Access Pages shares selected Home Assistant controls through expiring, revocable guest links using LayerV qURL/NHP. A LayerV account and dedicated management API key are required.

**0.1.129 is a normal patch update.** It keeps paired guest actions such as Turn on and Turn off side-by-side on narrow mobile screens while preserving text and touch-target sizes. The only product change from 0.1.128 is the approved responsive-layout fix. Live iPhone acceptance remains to be tested; publication does not mean those checks have passed. The historical timeout is not claimed resolved.

After the normal backup, update through Home Assistant with temporary diagnostic capture Off. Verify existing guest access, a harmless action followed by fresh state, verification recovery, page deletion across restart, mobile background/network recovery, and individual/bulk revocation using disposable guests. Healthy guest polling should remain quiet.

The native **Temporary diagnostic capture request** option explains its one-shot behavior. To capture an issue, choose 30 minutes, save and restart. New `ap_diag` records include UTC timestamps. Use the App's Logs and Download logs controls. Capture expires automatically; the saved duration is not runtime status. Restarting a consumed selection must not restart capture. Re-arm by choosing Off, saving and restarting, then choosing a duration, saving and restarting again.

Diagnostic output remains bounded. An unsampled request that hangs without a detected failure may leave no useful early-boundary evidence. See the [0.1.128 acceptance notes](https://github.com/AZDane/access-pages/releases/tag/v0.1.128) and [operating documentation](access_pages/DOCS.md) for remaining acceptance checks and diagnostic limitations.

Add `https://github.com/AZDane/access-pages-app` under **Settings → Apps → App store → Repositories** in Home Assistant, then install or update **Access Pages**. The App supports Home Assistant OS and Supervised installations on amd64 and aarch64.

- [Installation and operating documentation](access_pages/DOCS.md)
- [App changelog](access_pages/CHANGELOG.md)
- [Application source](https://github.com/AZDane/access-pages)
- [Private vulnerability reporting](https://github.com/AZDane/access-pages/security/advisories/new)

The App uses the versioned image `ghcr.io/azdane/access-pages-app:0.1.129`. This normal release also updates the latest image tags; existing versioned images remain available. See the [0.1.129 release notes](https://github.com/AZDane/access-pages/releases/tag/v0.1.129).
