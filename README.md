# Textunnel

**Share files and text between your devices in a browser. No installation or account required.**

[Open Textunnel](https://textunnel.com/) · [Transfer guide](https://textunnel.com/transfer-guide) · [Updates](https://textunnel.com/about#updates) · [Contact](https://textunnel.com/contact)

## Project status

Textunnel is a **closed-source browser service**, currently free to use. This repository provides public project information and a place to report issues. It does not distribute the current application source or offer a self-hosting package. No open-source license is granted for the application by this README.

## How to transfer

1. Create a room on one device and join the same room on the other. Match any room password.
2. Open the device panel and wait for **File channel ready**. Presence alone is not a ready file connection.
3. Send a file or text, accept the file if prompted, and wait for receiver verification. Save received files before closing or refreshing the page.

Keep both pages in the foreground. After an interruption, reconnect and use sender **Retry**; reconnection alone does not restart a failed transfer.

## Connection routes and privacy

- File and text content prefer a WebRTC data channel. Browsers encrypt that transport. **DIRECT** identifies a non-relay route; it does not prove traffic stayed on the same Wi-Fi. VPNs, firewalls and guest-network isolation affect connectivity.
- Online discovery and signaling use an internet service. Offline QR pairing requires loading the site first and a reachable local network.
- TURN and MQTT content relay require explicit permission in each tab. TURN forwards encrypted WebRTC transport. Public-room MQTT payloads require a **room password** for encryption against the broker. Share links use their own secret.
- History uses browser storage. Received file bytes normally remain in the open page. Optional temporary recovery stores incomplete file bytes locally, unencrypted at rest, within documented bounds. The website also runs third-party analytics and advertising scripts.

Read the [privacy policy](https://textunnel.com/privacy) before sharing sensitive information. Functional test results are not an independent security audit or an absolute-privacy guarantee.

## Current limits

| Route | Limit / condition |
| --- | --- |
| Text and clipboard | 64 KiB encoded message limit; clipboard permissions and focus apply |
| MQTT file fallback | 25 MiB per file, with explicit relay permission on both peers |
| Share links and folder packing | 256 MiB; keep the source page open |
| Room reception above 256 MiB | Supported disk-saving API required; browser/device limits still apply |
| Interrupted-file recovery | Eligible files up to 256 MiB, retained for up to 10 minutes; cross-refresh checkpoints require opting in before transfer |

There is no unlimited-file-size, fixed-speed or unattended background-clipboard guarantee. See the [maintained limits and recovery instructions](https://textunnel.com/transfer-guide).

## Published test evidence

The [dated physical-test table](https://textunnel.com/transfer-guide#tested-behavior) and [acceptance summary](https://textunnel.com/acceptance-summary.md) describe the actual devices, conditions, sizes, successes and failures tested. iPhone Safari ↔ Mac checks include 1 MiB and 64 MiB file round trips with matching SHA-256 hashes. Continuous lock-screen/background transfer failed; return-to-page and manual-retry recovery passed in the recorded cases.

A separate October 22, 2026 check on **Windows Server 2025 Datacenter / Chrome 155.0.8059.85** passed text delivery, 1 MiB and 64 MiB file round trips with matching download SHA-256 hashes, and 64 MiB refusal handling. It used two browser contexts on one GitHub-hosted Windows VM with controlled host candidates. See the [Windows environment and all six results](https://textunnel.com/transfer-guide#browser-tests) and [published JSON](https://textunnel.com/windows-browser-acceptance.json).

Physical Windows, iPhone-to-Windows and Android sessions remain unverified. Virtual machines, emulators, cloud devices and physical same-Wi-Fi sessions are labeled separately. Browser support is not a claim that every device configuration has been tested.

## Feedback

Report a problem using this repository's Issues or the [contact page](https://textunnel.com/contact). Include browser/OS versions, approximate file size, route label and the error shown. Do not post private files, room passwords, share secrets or TURN credentials. For security-sensitive reports, use the contact page rather than a public issue.
