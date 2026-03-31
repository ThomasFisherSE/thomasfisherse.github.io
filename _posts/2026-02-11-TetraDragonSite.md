---
layout: post
published: true
title: tetradragon.dev
subtitle: A portfolio website disguised as a desktop operating system.
gh-repo: ThomasFisherSE/tetra-dragon-site
gh-badge: [star, follow]
tags: [TypeScript,React,Web,Desktop,Development,Projects]
---

## Introduction

When I started [contracting as Tetra Dragon Software](https://thomasfisherse.github.io/2025-03-20-TetraDragonSoftware/), I wanted a portfolio site that was a bit more memorable than the standard template. I've always liked the idea of skeuomorphic interfaces, so I decided to build the whole thing as a fake desktop operating system - complete with draggable windows, a taskbar, desktop icons, and a boot sequence.

You can check it out at [tetradragon.dev](https://tetradragon.dev).

## The Desktop Experience

The site works like an OS. You're greeted with a boot screen and a lock screen, and then you land on a desktop with icons you can click to open windows. Each window is draggable and resizable, and supports minimize, maximize, and close, just like a real desktop environment. There's a taskbar along the bottom with a clock and buttons for each open window.

The portfolio content itself lives inside these windows: an About Me page, a Projects folder with detail pages for each project, a Services page, and a file explorer. But beyond the portfolio stuff, I had a lot of fun packing in extras.

## Easter Eggs

This is where I probably spent more time than I should have:

- **Aquarium** - a 3D screensaver with fish swimming around, built with React Three Fiber
- **Dragon Paint** - a basic drawing app
- **Dragon Powder** - a falling-sand physics simulation
- **Pong** - yes, there's Pong in the portfolio site
- **Terminal** - a terminal emulator with custom commands
- **3D Viewer** - a Three.js-powered model viewer
- **Achievements** - an achievement system that tracks things you discover on the site
- **Trash** - the bin has jokes in it

## Technical Details

- **React 19** with **TypeScript** (strict mode) and **Vite** for the build
- **Tailwind CSS v4** for styling, with a custom dark fantasy theme (deep navy blues, neon blue and red accents)
- **Zustand** for state management - separate stores handle window lifecycle, desktop state, mobile navigation, achievements, and session phases
- **react-rnd** for the window drag and resize behaviour
- **Motion** (Framer Motion) for animations, with spring physics. All animations respect `prefers-reduced-motion`.
- **Hash-based routing** with React Router so deep links like `#/about` and `#/project/unity-vr` work, including browser back/forward

The window system uses a central content registry that maps content type strings to lazily-loaded React components, so adding a new window type is just a matter of registering it. Window positions and states are persisted to localStorage.

On mobile, the site switches to a completely separate launcher-style UI rather than trying to cram draggable windows onto a small screen.

The site is deployed on Vercel with CI via GitHub Actions (lint, typecheck, tests, build). Feature branches get preview deployments before merging to production.
