# Account Records Desktop — Full Source 1.0.4

This is the complete desktop project source folder, not an updater-only patch.

## Included
- Electron main process and local API proxy
- Secure preload bridge
- Packaged renderer UI
- Desktop Settings with manual update controls
- GitHub Releases updater configuration
- Windows NSIS build configuration
- Build helper and example desktop configuration

## Build a Windows installer
1. Install Node.js LTS on Windows.
2. Extract this ZIP.
3. Open the `desktop` folder.
4. Double-click `BUILD-INSTALLER-1.0.4.bat`.
   Alternatively, run `npm install`, then `npm run dist`.
5. The installer output is created in `desktop\dist`.

## GitHub update target
- Owner: `redlotus0615`
- Repository: `account-records-desktop-releases`
- Provider: GitHub Releases

The public release repository must exist and contain a valid release before
Check for Updates can succeed.

## Security and release requirements
- The existing web repository remains separate; this source can be committed
  under a `desktop/` folder in the private `account-records` repository.
- Do not commit `node_modules`, `dist`, `.env`, GitHub tokens, PFX files,
  private keys, or code-signing passwords.
- Configure a trusted Windows Authenticode certificate before distributing
  signed updates. `electron-updater` signature verification is enabled.
- GitHub publishing requires a token with permission to create releases in
  the desktop release repository. Set `GH_TOKEN` only in the build environment;
  never hard-code it or commit it.
- The generic GitHub updater target is configured, but no release has been
  published by this package.
- A failed-update automatic rollback mechanism is not implemented. Keep prior
  signed installers available for recovery; downgrade attempts are blocked.

## Production data
The desktop app continues to use the hosted Account Records backend.
This package does not modify Render, Lark Sheets, Supabase, or production data.
