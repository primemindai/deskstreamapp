# 🧠 DeskStream

**The local-first memory engine for your personal AI.**

[![License: Free](https://img.shields.io/badge/License-100%25%20Free-success.svg)](#license)
[![Platform: macOS](https://img.shields.io/badge/Platform-macOS%20(Apple%20Silicon)-lightgrey.svg)](#installation)
[![Platform: Windows](https://img.shields.io/badge/Platform-Windows-blue.svg?style=flat&labelColor=555555&color=0078D4&logo=windows&logoColor=white)](#installation) *(Coming Soon)*
[![Privacy: Local](https://img.shields.io/badge/Privacy-Local_First-blue.svg)](#privacy-architecture)
[![Status: Active](https://img.shields.io/badge/Status-Active-brightgreen.svg)](#status)

DeskStream silently maps your desktop activity entirely locally, giving your AI the perfect context to understand your workflows, report on your productivity, and automate the mundane. 

Created by **PrimeMind AI**.

---

## 🌎 The Mission

> **You shouldn't have to work like a machine.**

We built DeskStream because generic AI is blind to your daily context. By tracking your keystrokes, clicks, window switches, and natural breaks, DeskStream creates a flawless, localized map of your digital day. 

We don't track you to micromanage you. We track you to build a foundation for true **agentic engineering**—empowering you to do less so your AI systems can operate intelligently on your behalf. 

---

## ✨ Core Capabilities

### ⚡️ Radical Performance Insights
Understand your true capacity. DeskStream automatically reports on your peak productivity hours, tracks your natural breaks, and measures time spent across every application. Find your flow state, and protect it.

### 🤖 AI That Actually Understands You
DeskStream acts as a local API bridge, allowing your trusted desktop LLMs and automated workflows (like n8n) to read your activity history. 
* Generate highly specific, custom productivity reports.
* Let your AI build automation scripts based on repeated actions.
* Never lose your train of thought after a distraction or context switch.

### 🔒 Absolute Privacy (Local-First)
Your data never touches the cloud. Everything is stored in a local SQLite database on your machine. No telemetry. No hidden uploads. Your raw data is yours alone.

### 🎛️ Granular Capture Control
Control exactly what the AI sees. Easily toggle specific data streams on or off:
* Foreground app usage & Window titles
* Session durations & Idle time
* Key counts, mouse clicks, & scrolls
* Typed-text context (Optional, for deep memory)

---

## 🚀 Getting Started

### Installation
*(Instructions for downloading the latest `.dmg` or installing via Homebrew will be updated upon final stable release).*

Download the latest verified macOS build from the [PrimeMind AI Release Page](https://primemindai.com/).

### System Requirements
* **macOS:** macOS 12.0 or later (Optimized for Apple Silicon M-Series for seamless background operation alongside local model inference).
* **Windows:** *In active development. Coming soon.*

---

## 🔌 The Local API 

DeskStream includes a token-protected local API. This is the bridge between your raw activity data and your headless operations. Trusted local tools, custom scripts, or local LLMs can query this API to reconstruct your day.

### Authentication
All requests require a Bearer token, which can be generated and rotated directly within the DeskStream UI.

### Example Request

Retrieve the last 4 hours of active window context to feed into a local model for summary generation:

```bash
curl -X GET "http://localhost:8765/api/v1/activity?hours=4&include_text=true" \
  -H "Authorization: Bearer YOUR_LOCAL_TOKEN"
