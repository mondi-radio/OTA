# Mondi Radio — Firmware Releases

This repo is a public over-the-air (OTA) release channel for Mondi Radio devices. Every tagged release on this page is a firmware image a Mondi can/should install automatically over Wi-Fi.

## For Mondi users

You do not need to do anything. Your device polls this repository on a schedule and installs new releases automatically once it has verified them. You can inspect the release notes on each version for what changed and why.

If your device seems stuck on an old version, there are a few things you can check:

- Confirm it is powered on and connected to Wi-Fi.
- Wait. The device checks periodically, not instantly.
- Power-cycle. The radio checks for new releases on each boot.
- If it still doesn't update, open an issue against this repository and include the version currently shown on the device, or contact the team in our [Discord](https://discord.gg/BGHwhwwvk).

## For developers and integrators

The URLs your device queries are stable and never change:

- Latest version metadata: `https://api.github.com/repos/OWNER/REPO/releases/latest`
- Latest firmware binary: `https://github.com/OWNER/REPO/releases/latest/download/firmware.bin`

Each release attaches, at minimum:

- `firmware.bin`
	- The OTA image itself.
- `firmware.bin.sha256`
	- Hex SHA-256 digest for verifying integrity, in a single line.
- `firmware.elf`
	- Symbol-carrying build. Useful for decoding a panic backtrace from `idf.py monitor` or `addr2line`. Contains no source, just symbols and addresses.

Releases are tagged `vX.Y.Z` following semantic versioning. The tag string is what the device compares against its own running version.

## Rolling back

To force devices back to an earlier version:

1. Go to Releases on this repository.
2. Edit an earlier release and mark it "Set as the latest release."
3. Devices will treat it as a newer version and install it on their next check.

## Security

If you have discovered a vulnerability, please read [SECURITY.md](SECURITY.md) before opening a public issue.

## License

Files committed to this repository and firmware binaries distributed as release assets on this repository are licensed under [PolyForm Noncommercial 1.0.0](LICENSE): free for personal, educational, research, and other non-commercial use. Commercial use requires a separate license. Contact <will@imbas.tech> for any commercial licensing agreement.
