# Changelog

## [v0.1.2] - 2026-10-8

- **TLS in PSRAM**: An HTTPS memory bug is solved by moving mbedTLS's certificates from smaller internal memory to the much larger PSRAM.
- **OTA**: Device now checks the version number of the latest release and compares it to its own before OTA-ing. Also pulls from `mondi-radio/OTA` repo now.
- **Boot Screen**: Now shows the current firmware version number, and the user can reach the Wifi setup menu from there by pressing the rotary encoder button.
- **New Partition Table**: Used to store Wifi credentials outside of the default NVS partition, so it can be erased as units move from assembly and testing to field use.
- **Device ID**: Every device now computes a globally-unique ID hash which it can report to the backend along with telematics and crash logs.
- **'Boot Hunt'**: After boot, if the first station to play has a broken URL or provides no audio bytes, the firmware moves on to the next until a healthy station is found.
- **Station Switching**: When switching stations from A to B, the connection with A will be kept active for a time until B starts streaming audio bytes, or until a timer runs out. This will reduce how much static people have to hear.
- **Station Name**: The now_playing screen now shows the station's name alongside the other data.

## [v0.1.1] - 2026-09-27

Now with OTA for automatic updates, and the user can enter wifi credentials through the menu screen.

## [v0.1.0] — 2026-09-14

Initial public release. Snapshot of the firmware used in the New Interfaces demo on 9/12/2026.