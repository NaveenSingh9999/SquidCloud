<div align="center">
  <h1>SquidCloud</h1>
  <p><strong>Secure, Unlimited Cloud Storage Platform — <i>v11.1.0 (Feijoa Update)</i></strong></p>

  [![Version](https://img.shields.io/badge/version-11.1.0-blue.svg)](https://squidcloud.vercel.app)
  [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
  [![TypeScript](https://img.shields.io/badge/TypeScript-Ready-blue?logo=typescript)](https://www.typescriptlang.org/)
  [![React](https://img.shields.io/badge/React-18-61DAFB?logo=react)](https://reactjs.org/)
  [![Android](https://img.shields.io/badge/Android-11.1.0-3DDC84?logo=android)](https://squidcloud.vercel.app)
  [![PWA](https://img.shields.io/badge/PWA-Ready-5A0FC8?logo=pwa)](https://squidcloud.vercel.app)
</div>

<br />

> **SquidCloud** is a next-generation, privacy-first cloud storage solution powered by the **Res54 Distributed Architecture**. Uncapped storage capacity, military-grade end-to-end encryption, and unparalleled performance — all seamlessly integrated into a modern web, desktop, and mobile ecosystem.

---

## 📸 Platform Preview

> *SquidCloud v11 Dashboard interface with the new Feijoa design language and the integrated cbCode IDE.*

<p align="center">
  <img src="./cx/Screenshot%202026-04-03%20at%2010-48-58%20SquidCloud%20-%20Secure%20Unlimited%20Cloud%20Storage.png" alt="SquidCloud v11 Dashboard Preview" width="100%">
</p>

---

## Table of Contents

- [What's New in v11.1.0](#whats-new-in-v1110-feijoa-update)
- [Key Features](#key-features)
- [Storage Options](#storage-options)
- [How It Works](#how-it-works)
- [Architecture](#architecture)
- [Security](#security)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Mobile & Desktop](#mobile--desktop)
- [Legal](#legal)

---

## 🌟 What's New in v11.1.0 (Feijoa Update)

- **Bring Your Own Storage (BYOS):** Attach your own external storage provider — Tebi.io, Cloudflare R2, or Amazon S3 — and use SquidCloud as your interface. Your files go directly to your infrastructure.
- **Bring Your Own Key (BYOK):** Supply your own encryption key. SquidCloud never sees or stores it. Full zero-knowledge encryption on your terms.
- **Signed Android APK:** Native Android app with a signed APK build pipeline via GitHub Actions, favicon-based launcher icons, and full mobile feature parity.
- **Rebuilt Legal Pages:** Privacy Policy and Terms of Service rebuilt as first-class UI — fully coded, styled, and compliant with India's DPDP Act 2023.
- **Mobile OAuth Hardening:** HTTPS redirects and PKCE flow for secure mobile OAuth state validation.
- **File Sharing Enhancements:** Backend PIN authorization enforced on all share and delete flows.
- **BYOK Setup Hardening:** Strengthened BYOK setup flow with auto-close bug fix and improved PIN authorization.
- **Upload Worker:** Background upload worker with notification support and improved file handling.

---

## What is SquidCloud?

SquidCloud is a next-generation cloud storage platform that combines the convenience of traditional cloud storage with advanced security features and unlimited capacity. Unlike conventional cloud providers, SquidCloud uses a unique distributed storage system called **Res54** that fragments, encrypts, and distributes your files across multiple secure repositories.

SquidCloud is free to use, independently operated, and built with a privacy-first philosophy. We do not sell your data, run ads, or train AI on your files.

---

## Key Features

### 🔐 Security & Encryption
- **AES-256-GCM encryption** via the Res54 engine on all stored files
- **End-to-end encryption** — file content is encrypted before it leaves your session
- **Bring Your Own Key (BYOK)** — supply your own encryption key; SquidCloud never stores or sees it
- **Passkey & Biometric Authentication** — true passwordless sign-in via WebAuthn
- **Secondary PIN Auth layer** — enforced on share and delete operations
- **HTTPS enforced globally** — no plaintext transmission anywhere
- **No plaintext storage** — encrypted chunks stored as opaque JSON blobs

### ☁️ Storage
- **Uncapped storage capacity** via the Res54 distributed architecture
- **Native GitHub Storage** — files stored as encrypted chunked JSON blobs across GitHub repositories
- **Bring Your Own Storage (BYOS)** — connect Tebi.io, Cloudflare R2, or Amazon S3
- **Block-split chunking** — files split into encrypted chunks before storage; no chunk reveals file identity
- **Optional entropy layer** for additional encryption complexity
- **Metadata-only Supabase storage** — file content never touches the database

### 🛠️ Developer Tools
- **Full REST API** with per-account API keys
- **CLI support** for automation and workflow integration
- **SquidLab SDK** (v1.1.0) — build on top of SquidCloud's ecosystem
- **cbCode IDE** — Monaco-powered browser coding environment embedded in your workspace
- **API usage logs** retained 90 days for audit and abuse prevention

### 📱 Platform
- **Progressive Web App (PWA)** — installable on any device
- **Native Android App** (v11.1.0) — signed APK with full mobile feature parity
- **Responsive design** — optimized for desktop, tablet, and mobile
- **Background upload worker** with notification support
- **Service worker caching** for offline resilience

---

## Storage Options

SquidCloud gives you full control over where your data lives. Choose the option that fits your needs.

### 🐙 Native GitHub Storage (Default)
Your files are chunked, encrypted with AES-256-GCM, serialized as JSON blobs, and stored in GitHub repositories managed by SquidCloud. The stored blobs are completely opaque — no filename, file type, or content can be identified from them by any party, including GitHub and SquidCloud. Only your account with the correct decryption credentials can reassemble and decrypt the original files.

**Best for:** Users who want a simple, zero-configuration setup with no external accounts required.

### 🗄️ Bring Your Own Storage (BYOS)
Connect your own external storage provider. SquidCloud acts as your interface — your files go directly to your infrastructure, not ours.

**Supported providers:**
- **Tebi.io** — S3-compatible object storage
- **Cloudflare R2** — zero egress fee object storage
- **Amazon S3** — industry-standard cloud object storage

SquidCloud stores only your encrypted provider credentials and file metadata. Your file content goes directly to your provider. Any costs from your provider are your own responsibility.

**Best for:** Users who want full infrastructure ownership, compliance control, or are already paying for cloud storage.

### 🔑 Bring Your Own Key (BYOK)
Supply your own encryption key for complete zero-knowledge encryption. Your key is never transmitted to or stored by SquidCloud. All encryption and decryption occurs entirely on your side.

> ⚠️ If you lose your BYOK encryption key, SquidCloud cannot recover your data. Keep a secure independent backup of your key at all times.

**Best for:** Users with strict security requirements, developers, and enterprise use cases.

---

## How It Works

```
Your File
    │
    ▼
Client-side chunking
    │
    ▼
AES-256-GCM Encryption (Res54 Engine)
    │
    ▼
Serialized as JSON blobs
    │
    ├──► Native: GitHub Repositories (opaque blobs)
    ├──► BYOS: Your S3 / R2 / Tebi bucket
    └──► BYOK: Encrypted with your own key before any of the above
```

Metadata (filename, size, type, timestamps) is stored separately in Supabase. File content and metadata are never stored together.

---

## Architecture

SquidCloud is built on the **Res54 Distributed Architecture** — a proprietary system designed around three principles: opacity, redundancy, and client-side sovereignty.

| Layer | Technology |
|---|---|
| Frontend | React 18 + TypeScript + Vite |
| UI Components | Shadcn/ui + Tailwind CSS |
| Backend / Auth | Supabase |
| Native Storage | GitHub API (encrypted blobs) |
| External Storage | Tebi.io / Cloudflare R2 / Amazon S3 (BYOS) |
| Encryption Engine | Res54 (AES-256-GCM, block-split, optional entropy) |
| Hosting | Vercel |
| Android | Capacitor + signed APK via GitHub Actions |
| SDK | SquidLab SDK v1.1.0 |

---

## Security

| Feature | Status |
|---|---|
| AES-256-GCM Encryption | ✅ Enabled |
| Client-side Encryption | ✅ Before upload |
| BYOK (Zero-knowledge) | ✅ Available |
| HTTPS Enforced | ✅ Global |
| Passkey / WebAuthn | ✅ Supported |
| PIN Authorization | ✅ On share and delete |
| OAuth PKCE Flow | ✅ Mobile hardened |
| No plaintext storage | ✅ Guaranteed |
| No AI training on files | ✅ Never |
| No data selling | ✅ Never |

We do not access, read, or analyze your file content under any circumstance. In BYOK mode, we are cryptographically incapable of doing so.

---

## Getting Started

### Web
Visit [https://squidcloud.vercel.app](https://squidcloud.vercel.app) and create a free account.

### Android
Download the latest signed APK from the releases section of this repository. Install it on any Android device running Android 7.0 or later.

### API
Generate an API key from your dashboard. Every key is scoped to your account and logged for security purposes.

```bash
# Example: List files via API
curl -H "Authorization: Bearer YOUR_API_KEY" \
  https://squidcloud.vercel.app/api/files
```

Full API documentation is available in your dashboard after signing in.

### CLI
The SquidCloud CLI supports automation and scripting via your API key. See the CLI documentation in your dashboard for setup instructions.

---

## Usage

### Connecting a BYOS Provider

1. Go to **Settings → Storage** in your dashboard
2. Select your provider (Tebi.io, Cloudflare R2, or Amazon S3)
3. Enter your provider credentials — these are encrypted and stored securely
4. Save and set as active storage backend

To disconnect, go to **Settings → Storage** and remove the provider. Note: disconnecting does not delete files already stored on your provider.

### Enabling BYOK

1. Go to **Settings → Encryption**
2. Select **Bring Your Own Key**
3. Enter or generate your encryption key
4. Save your key securely — SquidCloud does not store it

### Using cbCode IDE

Open any code file in your SquidCloud workspace and select **Open in cbCode**. The Monaco-powered editor launches directly in your browser with no setup required.

---

## Mobile & Desktop

| Platform | Version | Status |
|---|---|---|
| Web (PWA) | 11.0.37 | ✅ Live |
| Android (APK) | 11.1.0 | ✅ Available |
| iOS | — | 🔜 Planned |
| Desktop (Electron) | — | 🔜 Planned |

The Android app is built with Capacitor and distributed as a signed APK. It supports full feature parity with the web platform including BYOS, BYOK, file upload with background worker, and OAuth sign-in.

---

## Legal

SquidCloud is an independent project operated by its founders. All services are free to use.

- [Privacy Policy](https://squidcloud.vercel.app/privacy)
- [Terms of Service](https://squidcloud.vercel.app/terms)

Governed by the laws of India. Compliant with the Digital Personal Data Protection Act, 2023 (DPDP Act).

For support or legal inquiries: **hellosquidcloud@gmail.com**

---

## SquidLab SDK

Build on top of SquidCloud with the SquidLab SDK (v1.1.0). The SDK provides programmatic access to storage, file management, and authentication flows.

```bash
npm install squidlab-sdk
```

See the SDK repository for full documentation and examples.

---

<div align="center">
  <p>Built and maintained with 💙 by Lamgerr</p>
  <p>
    <a href="https://squidcloud.vercel.app">Platform</a> ·
    <a href="https://squidcloud.vercel.app/privacy">Privacy</a> ·
    <a href="https://squidcloud.vercel.app/terms">Terms</a> ·
    <a href="mailto:hellosquidcloud@gmail.com">Contact</a>
  </p>
  <p><i>SquidCloud v11.1.0 — One year of building. 🦑☁️</i></p>
</div>
