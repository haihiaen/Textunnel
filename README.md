# TexTunnel ⚡️ 
**Blazing Fast, Serverless P2P File & Text Sharing in Your Browser**

[![Website](https://img.shields.io/badge/Live_Demo-Visit_Website-000000?style=for-the-badge&logo=vercel)](https://textunnel.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

> TexTunnel is a modern, privacy-first web application that allows you to instantly share files, text, and clipboards between devices. No installation, no size limits, and no files ever touch our servers.

🌐 **Try the live tool here**: [Free P2P File Sharing App](https://textunnel.com/)

---

## ✨ Why TexTunnel?

Traditional cloud storage routes your sensitive data through centralized servers, throttling your speed and exposing your privacy. TexTunnel changes the game by utilizing **WebRTC Data Channels** to establish a direct Peer-to-Peer connection.

Whether you are sending a quick text snippet, looking to [transfer large files directly](https://textunnel.com/) (like a 10GB 4K video), or trying to sync clipboards across your phone and laptop — the bytes travel strictly over your local Wi-Fi.

## 🚀 Key Features

- 🔒 **Absolute Privacy**: Zero-knowledge architecture. All [local network file transfers](https://textunnel.com/) are encrypted end-to-end between peers. Servers are only used for the initial WebRTC signaling.
- ⚡️ **Uncapped Speeds**: Transfer files as fast as your local Wi-Fi router allows.
- 🗂 **Infinite File Sizes**: Streaming architecture allows for massive file transfers without exhausting browser memory.
- 📱 **Cross-Platform**: Works instantly on iOS, Android, macOS, Windows, and Linux. 
- 📋 **Universal Clipboard**: Seamlessly [sync clipboard across devices](https://textunnel.com/) without installing any native apps.

## 🛠 Tech Stack

TexTunnel is built with modern web technologies focused on performance and security:

- **Frontend**: React, TypeScript, Tailwind CSS
- **Networking**: WebRTC (RTCDataChannel) for P2P transfers
- **Signaling**: MQTT (over WebSockets) for real-time device discovery
- **Storage**: File System Access API for streaming massive files to disk

## 💡 How It Works

1. **Discovery**: When you open our [WebRTC file transfer tool](https://textunnel.com/), your device securely connects to our signaling broker.
2. **Handshake**: It automatically discovers other devices on the same network (or via manual Room ID).
3. **P2P Tunnel**: A secure WebRTC connection is negotiated.
4. **Direct Transfer**: Once connected, the signaling server steps out of the way. All data flows directly via DTLS/SCTP encryption between your devices.

## 🤝 Support & Feedback

If you find this tool useful, please consider giving this repository a ⭐️ to help others discover it!
For feature requests or bug reports, please feel free to open an issue.

Start sharing seamlessly today at **[TexTunnel Official](https://textunnel.com/)**
