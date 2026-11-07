<p align="center">
  <img src="assets/avatar-circle.png" alt="Stellisle Logo" width="105" />
</p>

<h1 align="center">Stellisle Releases</h1>

<p align="center">
  <strong>知屿星信 · macOS 官方发行版、安装包与安全验证中心</strong><br>
  <em>Official distribution hub, binary verification manifests, and changelog records for Stellisle.</em>
</p>

<p align="center">
  <a href="https://stellisle.pages.dev"><img src="https://img.shields.io/badge/Official_Site-stellisle.pages.dev-60243c?style=flat-square" alt="Website"></a> &nbsp;
  <a href="https://discord.gg/S7yy7Pxue"><img src="https://img.shields.io/badge/Discord-Join_Community-5865F2?style=flat-square&logo=discord&logoColor=white" alt="Discord"></a> &nbsp;
  <a href="https://x.com/stellisle_app"><img src="https://img.shields.io/badge/X-@stellisle__app-000000?style=flat-square&logo=x&logoColor=white" alt="X"></a> &nbsp;
  <a href="https://bsky.app/profile/stellisle.bsky.social"><img src="https://img.shields.io/badge/Bluesky-@stellisle.bsky.social-0285FF?style=flat-square&logo=bluesky&logoColor=white" alt="Bluesky"></a>
  <br>
  <a href="https://stellisle.itch.io/stellisle"><img src="https://img.shields.io/badge/itch.io-stellisle-FA5C5C?style=flat-square&logo=itchdotio&logoColor=white" alt="itch.io"></a> &nbsp;
  <a href="https://www.reddit.com/user/stellisle/"><img src="https://img.shields.io/badge/Reddit-u/stellisle-FF4500?style=flat-square&logo=reddit&logoColor=white" alt="Reddit"></a> &nbsp;
  <a href="https://github.com/stellisle-app/stellisle-releases/releases"><img src="https://img.shields.io/badge/Platform-macOS_14+_Sonoma_|_15+_Sequoia-2c3e50?style=flat-square" alt="Platform"></a> &nbsp;
  <a href="https://github.com/stellisle-app/stellisle-releases"><img src="https://img.shields.io/badge/Architecture-Apple_Silicon_(M1–M4)-34495e?style=flat-square" alt="Architecture"></a>
</p>

---

<p align="center">
  <img src="assets/app-preview.webp" alt="Stellisle Desktop Companion Interface" width="780" />
</p>

<p align="center">
  <em>Desktop Workspace: A calm conversational presence resting at the corner of your screen.</em>
</p>

---

## Overview

**Stellisle (知屿星信)** is a native desktop companion designed for macOS on Apple Silicon. It operates as a focused workspace presence, providing contextual conversational memory, nuanced vocal likeness, and tactile skeuomorphic interactions without sending personal telemetry to cloud servers.

This repository serves as the official distribution channel for verified disk images (`.dmg`), release notes, cryptographic checksums, and architecture compatibility requirements.

<p align="center">
  <img src="assets/starlight-symbol.png" alt="Starlight Symbol" width="120" />
</p>

---

## Architecture & System Capabilities

### 1. Local Neural Inference
Engineered specifically for Apple Silicon Unified Memory and the Apple Metal compute framework. Conversational generation processes on-device, preserving privacy and keeping spoken exchanges within local storage.

### 2. Encrypted Persistent Memory Graph
Conversations, preferences, and contextual milestones persist across sessions in an encrypted on-device SQLite database. Contextual retrieval reconstructs long-term familiarity over weeks and months of use.

### 3. Tactile Skeuomorphic Desk & Acoustics
Direct developer communication operates through an interactive simulated teleprinter desk. The interface integrates procedurally synthesized dot-matrix printer audio via the Web Audio API, pairing mechanical sound design with real-time ticket dispatch.

<p align="center">
  <img src="assets/starlight-card.webp" alt="Starlight Keepsake Polaroid Card" width="560" />
</p>

<p align="center">
  <em>Starlight Keepsakes: Procedural client-rendered memory keepsakes.</em>
</p>

---

## Hardware & Operating System Matrix

Stellisle utilizes Apple Metal 3 shaders and ARM64-specific neural kernels. Intel-based Mac configurations and Rosetta 2 emulation are not supported.

| Specification | Minimum Requirement | Recommended Specification |
| :--- | :--- | :--- |
| **Operating System** | macOS 14.0 Sonoma | macOS 15.0+ Sequoia |
| **Processor** | Apple Silicon M1 (8-core CPU / 7-core GPU) | Apple Silicon M2, M3, or M4 |
| **Unified Memory** | 8 GB Unified Memory | 16 GB or higher Unified Memory |
| **Storage Space** | 2.5 GB available APFS storage | 5 GB available APFS storage |
| **Display Support** | Built-in Retina or external 1080p display | Retina 4K / 5K with Wide Color (P3) |

---

## Installation Guide

### Option 1: Standard Disk Image (.dmg)

1. Open the [Releases](https://github.com/stellisle-app/stellisle-releases/releases) directory in this repository.
2. Download the latest release binary: `Stellisle-<version>-arm64.dmg`.
3. Double-click the downloaded `.dmg` file to mount the volume.
4. Drag the `Stellisle.app` bundle into your macOS `/Applications` folder.
5. Eject the disk image and launch Stellisle from Spotlight or Launchpad.

### First Launch & macOS Gatekeeper Notice / 首次打开安全提示

知屿星信采用纯本地推理架构，未配置云端遥测与外部开发者公证。在 macOS 14 (Sonoma) 或 macOS 15 (Sequoia) 首次打开时，系统可能会提示：“无法验证开发者”或“App 已损坏，无法打开”。这是 macOS Gatekeeper 对未签名开发版本的常规安全提示，软件本身完全正常，你可以通过以下任一方式解锁：

#### 方式一：系统设置解锁（推荐 · 无需终端）
1. 双击打开应用一次，系统弹出拦截窗口后点击“完成”或“好”。
2. 打开 Mac 的 **系统设置 (System Settings)** → **隐私与安全性 (Privacy & Security)**。
3. 向下滚动至 **安全性 (Security)** 区域，会看到提示：“已阻止使用「知屿星信」，因为来自身份不明的开发者”。
4. 点击右侧的 **仍要打开 (Open Anyway)**，输入开机密码确认即可。

#### 方式二：终端一行命令解除（最快捷）
打开 **终端 (Terminal)**，复制并粘贴以下命令后按回车：

```bash
xattr -cr /Applications/知屿星信.app
# 若安装包为英文名称：
xattr -cr /Applications/Stellisle.app
```
完成后即可正常双击启动。

### Option 2: Binary Integrity Verification

Every published `.dmg` file includes a corresponding SHA-256 checksum in its release assets. You can verify package integrity in Terminal:

```bash
shasum -a 256 Stellisle-*.dmg
```

Compare the resulting hash with the published value in the release notes to confirm the archive has not been modified.

---

## Release Channels & Cadence

| Channel | Identifier | Purpose | Distribution Target |
| :--- | :--- | :--- | :--- |
| **Stable** | `vX.Y.Z` | Recommended production releases tested across macOS 14 and 15. | GitHub Releases & [stellisle.pages.dev](https://stellisle.pages.dev) |
| **Preview** | `vX.Y.Z-rc.*` | Pre-release builds containing newly ported neural backends and audio models. | GitHub Releases (Tagged Pre-release) |

---

## Feedback, Support & Official Channels

| Channel | Identifier | Link | Description |
| :--- | :--- | :--- | :--- |
| **Official Web Portal** | `stellisle.pages.dev` | [Visit Portal](https://stellisle.pages.dev) | Interactive showcase, voice showroom, and web portal. |
| **Feedback Desk** | `/feedback.html` | [Open Postbox](https://stellisle.pages.dev/feedback.html) | Direct-to-developer feedback with printed ticket receipts. |
| **Updates & Field Notes** | `/updates.html` | [Read Notes](https://stellisle.pages.dev/updates.html) | Transparent development logs and release preparation. |
| **Discord Sanctuary** | `Stellisle Official` | [Join Server](https://discord.gg/S7yy7Pxue) | Bilingual community discussion, keepsakes, and voice model previews. |
| **X (Twitter)** | `@stellisle_app` | [Follow @stellisle_app](https://x.com/stellisle_app) | Official release announcements, product teasers, and changelog highlights. |
| **Bluesky** | `@stellisle.bsky.social` | [Follow Bluesky](https://bsky.app/profile/stellisle.bsky.social) | Open decentralized social updates and dev logs. |
| **itch.io** | `stellisle` | [View Project](https://stellisle.itch.io/stellisle) | Independent software showcase and community releases. |
| **Reddit** | `u/stellisle` | [View Profile](https://www.reddit.com/user/stellisle/) | Discussions across r/LocalLLaMA and r/macapps. |
| **Direct Contact** | `stellisle@proton.me` | [Email Us](mailto:stellisle@proton.me) | Inquiries regarding security disclosures, localization, or privacy. |

<sub>Upcoming channels in verification: 小红书 (`知屿星信 Stellisle`), 即刻 (`知屿星信`), Bilibili (`知屿星信_Official`).</sub>

---

<p align="center">
  <sub>Copyright © 2026 Stellisle. Built with care for quiet minds.</sub>
</p>
