---
layout: post
published: true
title: Pin Tracker
subtitle: A cross-platform app for managing collectible pin collections, with AI-powered identification.
gh-repo: ThomasFisherSE/pin-tracker
gh-badge: [star, follow]
tags: [Rust,Svelte,TypeScript,Desktop,Android,iOS,AI,LLM,APIs,Development,Projects]
---

## Introduction

As I mentioned in my [Activity Planner](https://thomasfisherse.github.io/2024-12-10-ActivityPlanner/) post, my wife and I are big Disney fans, and a side effect of visiting the parks is that we've ended up with a growing collection of Disney trading pins. Keeping track of what we own, what we're looking for, and what we'd be willing to trade became enough of a chore that I figured I'd build something for it.

Pin Tracker is a cross-platform app for managing collectible pin collections. While it was built with Disney pins in mind, it's designed to work with any type of collectible pin.

## How It Works

The main hook is photo-based pin identification. You take a photo of a pin (or pick one from your gallery), and the app sends it to an LLM with vision capabilities to identify it. The LLM returns a set of ranked suggestions with details like the pin's name, series, estimated trade value, and reference images. You pick the best match, tweak any details if needed, and it gets added to your collection.

From there, you can:
- Mark pins as **Owned**, **Wishlist**, **Saved**, or **Former** (for pins you've traded away)
- Tag and flag pins for easy filtering (e.g. flagging trade candidates)
- Track sets and see your progress towards completing them
- Discover related pins in the same series via the LLM
- View collection stats - value over time, duplicates, edition breakdowns, tag frequency, and set completion

If you've got a group photo of multiple pins, there's a segmentation feature where you tap to mark individual pins in the image, and each one gets identified separately.

## Technical Details

The app is built with [Tauri](https://tauri.app/), which pairs a Rust backend with a web frontend. This gives you native performance and access to system APIs (file dialogs, SQLite, etc.) while keeping the UI in familiar web tech.

- **Backend:** Rust with SQLite (via rusqlite) for local-first data storage. All pin data, images, tags, and history live on-device.
- **Frontend:** Svelte 5 with SvelteKit and TypeScript. The UI includes grid/list views, bulk operations, and a carousel for multi-image pins.
- **LLM integration:** The app supports multiple LLM providers through a trait-based abstraction. Currently Google Gemini and Anthropic's Claude are implemented, and swapping in another provider is straightforward. The LLM handles pin identification, text-based search, related pin discovery, tag suggestions, and trade value estimation.
- **Platforms:** Desktop (Linux, macOS, Windows) and mobile (Android, iOS) from a single codebase.

The database schema has gone through 6 migrations so far, adding things like source attribution, original price tracking, status history (so you can see when a pin moved from Owned to Traded), and disposition notes.
