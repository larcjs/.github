# LARC — Lightweight Asynchronous Relay Core

[![Version](https://img.shields.io/badge/version-1.1.1-blue.svg)](https://github.com/larcjs/core)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](https://github.com/larcjs/core/blob/main/LICENSE)
[![Status](https://img.shields.io/badge/status-production--ready-brightgreen.svg)](https://github.com/larcjs/core)
[![Tests](https://img.shields.io/badge/tests-261%20passing-brightgreen.svg)](https://github.com/larcjs/core)

> **Build serious web applications with just a `<script>` tag and Web Components.**

LARC is a message bus architecture for the browser inspired by automotive CAN bus systems. Components communicate through a shared PAN (Page Area Network) without knowing about each other — no tight coupling, no props drilling, no global state management complexity. Drop one script include into an HTML file and start building with native Web Components, ES modules, and browser standards. No build process required.

---

## 💡 What Makes LARC Different

### It's an architecture, not a framework

Most web tools give you components or state management or routing. LARC gives you a **communication pattern** — a message bus inspired by the CAN bus in cars. Components broadcast what they're doing. Other components listen if they care. Nobody needs to know who else exists.

This single pattern solves coordination problems across your entire application:

- **Component communication** — Publish/subscribe instead of props drilling
- **State management** — Distributed state without centralized stores
- **Cross-context messaging** — Sync tabs, workers, and iframes automatically
- **Framework interop** — React, Vue, and vanilla components all speak PAN
- **Loose coupling** — Change, add, or remove components without cascade effects

### The Browser is the Platform

Modern browsers have everything needed for serious app development: Custom Elements, Shadow DOM, ES Modules, async/await, IndexedDB, WebSockets, Service Workers. These aren't experimental — they're standardized, fast, and universal.

LARC embraces this reality. Instead of abstracting the platform away, it **amplifies what's already there**:

```html
<!-- This is a complete LARC application -->
<!DOCTYPE html>
<html>
<head>
  <script type="module" src="https://unpkg.com/@larcjs/core@1.1.1/src/pan.mjs"></script>
</head>
<body>
  <pan-bus></pan-bus>
  <pan-router></pan-router>
  <pan-auth></pan-auth>
  <my-app></my-app>
</body>
</html>
```

No build step. No package.json. No node_modules. Just an HTML file and browser standards.

### When to Use LARC

**You'll love LARC if:**
- You want to escape build pipeline complexity
- You're building component libraries that work everywhere
- You need micro-frontends without framework conflicts
- You value simplicity and web standards
- You want apps that load instantly without massive bundles

**You might want something else if:**
- You need React's ecosystem for a specific use case (you can still mix them!)
- Your team is deeply invested in Vue/Angular workflows
- You're building a traditional server-rendered app
- You prefer opinionated, all-in-one frameworks

LARC complements your existing tools. Use it to reduce overhead, or go all-in and build framework-free. Either way works.

---

## 🌟 Key Features

- 🚀 **Zero Build Required** — Drop-in `<pan-bus>` element, no bundler needed
- 🎯 **Lightweight** — 5KB core, components load on demand
- 🔌 **Framework Complement** — Reduce React/Vue overhead by 60%+
- ⚡ **High Performance** — 300k+ messages/second* (tested on MacBook Pro 16" M4, YMMV), 261 tests passing
- 🔒 **Production Ready** — TypeScript support, comprehensive testing, developed with security in mind (self-audited)
- 🛠️ **DevTools** — Chrome extension for debugging message flows

---

## 📦 Packages

| Package | Description | Version | Links |
|---------|-------------|---------|-------|
| **[@larcjs/core](https://github.com/larcjs/core)** | Core PAN messaging bus | 1.1.1 | [NPM](https://npmjs.com/package/@larcjs/core) · [Docs](https://larcjs.github.io/site/) |
| **[@larcjs/core-types](https://github.com/larcjs/core-types)** | TypeScript types for core | 1.1.1 | [NPM](https://npmjs.com/package/@larcjs/core-types) |
| **[@larcjs/components](https://github.com/larcjs/components)** | UI components library (57 components) | 1.1.0 | [NPM](https://npmjs.com/package/@larcjs/components) · [Gallery](https://larcjs.github.io/site/gallery.html) |
| **[@larcjs/components-types](https://github.com/larcjs/components-types)** | TypeScript types for components | 1.0.2 | [NPM](https://npmjs.com/package/@larcjs/components-types) |
| **[@larcjs/examples](https://github.com/larcjs/examples)** | Examples & demo apps | - | [Examples](https://larcjs.github.io/examples/) |
| **[@larcjs/site](https://github.com/larcjs/site)** | Documentation website | - | [Live Site](https://larcjs.github.io/site/) |
| **[@larcjs/devtools](https://github.com/larcjs/devtools)** | Chrome DevTools extension | - | [Docs](https://github.com/larcjs/devtools) |

---

## ⚡ Quick Start

### CDN (No Installation)

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <script type="module" src="https://unpkg.com/@larcjs/core@1.1.1/src/pan.mjs"></script>
</head>
<body>
  <!-- Components load automatically -->
  <pan-bus></pan-bus>
  <pan-card title="Hello World">
    <p>Components communicate via PAN messages</p>
  </pan-card>
  <pan-inspector></pan-inspector>
</body>
</html>
```

### NPM Installation

```bash
npm install @larcjs/core @larcjs/components

# TypeScript support (optional)
npm install -D @larcjs/core-types @larcjs/components-types
```

```javascript
import '@larcjs/core';
import '@larcjs/components/pan-card';

// TypeScript
import type { PanClient, PanMessage } from '@larcjs/core-types';
```

---

## 🎯 Use Cases

### Design Systems
Build once, use across React, Vue, Angular, and vanilla JS projects. Components work everywhere.

### Reduce Bundle Size
Replace heavy component libraries with lightweight LARC components. Reduce overhead by 60%+.

### Micro-frontends
Different teams/frameworks coordinating via PAN messages without tight coupling.

### Progressive Enhancement
Add interactive features to existing pages without full rewrites.

### Real-Time Collaboration
Sync state across tabs, iframes, and WebSockets with built-in cross-context messaging.

---

## 📚 Documentation

- **[Getting Started](https://larcjs.github.io/site/)** — Quick introduction
- **[API Reference](https://larcjs.github.io/site/docs/API_REFERENCE.html)** — Complete API docs
- **[Interactive Playground](https://larcjs.github.io/larc/playground/)** — Try 57+ components live
- **[Examples](https://larcjs.github.io/examples/)** — Real-world demos
- **[Component Gallery](https://larcjs.github.io/site/gallery.html)** — Visual showcase
- **[Production Guide](https://github.com/larcjs/larc/blob/main/docs/PRODUCTION-DEPLOYMENT.md)** — Deployment best practices

---

## 🔍 Example: Components Communicating

```html
<!DOCTYPE html>
<html>
<head>
  <script type="module" src="https://unpkg.com/@larcjs/core@1.1.1/src/pan.mjs"></script>
</head>
<body>
  <pan-bus></pan-bus>

  <!-- This publishes theme changes -->
  <pan-theme-toggle></pan-theme-toggle>

  <!-- These subscribe and react automatically -->
  <pan-card title="Card 1">I change themes!</pan-card>
  <pan-card title="Card 2">Me too!</pan-card>
  <pan-data-table>And me!</pan-data-table>

  <!-- No JavaScript needed! Components coordinate via PAN messages -->
</body>
</html>
```

**Zero coupling, pure coordination.**

---

## 🏗️ Hybrid Architecture Example

Mix React, Vue, and LARC on the same page:

```html
<!-- React component for complex chart -->
<div id="react-chart"></div>

<!-- Vue component for filters -->
<div id="vue-filters"></div>

<!-- LARC components for everything else -->
<pan-bus></pan-bus>
<pan-header></pan-header>
<pan-sidebar></pan-sidebar>
<pan-data-table></pan-data-table>

<!-- All coordinate via PAN messages -->
<script>
  // React chart publishes: { topic: 'chart.clicked', data: {...} }
  // Vue filters publish: { topic: 'filters.changed', data: {...} }
  // LARC table subscribes and updates automatically
</script>
```

**Result:** 837 KB → 322 KB (61% smaller bundle)

---

## 🌐 Architecture

```
┌─────────────────────────────────────────┐
│            Application                  │
├──────────┬──────────┬──────────────────┤
│  React   │   Vue    │      LARC        │
│Component │Component │    Components    │
└────┬─────┴────┬─────┴────┬────────────┘
     │          │          │
     └──────────┼──────────┘
                │
         ┌──────▼──────┐
         │  <pan-bus>  │  ← Message Hub
         └──────┬──────┘
                │
     ┌──────────┼──────────┐
     │          │          │
┌────▼───┐  ┌──▼───┐  ┌───▼────┐
│ Worker │  │iframe│  │ Tabs   │
└────────┘  └──────┘  └────────┘
```

**No tight coupling. Just messages.**

---

## 🛠️ Development

### Clone and Set Up

```bash
# Clone meta-repository with all submodules
git clone --recurse-submodules https://github.com/larcjs/larc.git
cd larc

# Run setup
./setup.sh         # Mac/Linux
# OR
setup.bat          # Windows

# Start server
python3 -m http.server 8000
```

### Develop a Package

```bash
# Work on core
cd core
npm install
npm test          # 261 tests across 5 browsers

# Work on components
cd ui
npm install
npm test
```

---

## 🤝 Contributing

We welcome contributions! Please see:
- [Contributing Guide](https://github.com/larcjs/larc/blob/main/CONTRIBUTING.md)
- [Code of Conduct](https://github.com/larcjs/larc/blob/main/CODE_OF_CONDUCT.md)
- [Security Policy](https://github.com/larcjs/larc/blob/main/SECURITY.md)

---

## 📊 Status

| Package | Build | Tests | Coverage | Security |
|---------|-------|-------|----------|----------|
| **core** | ✅ | ✅ 261 passing | 85%+ | ✅ 0 critical |
| **components** | ✅ | ✅ passing | 80%+ | ✅ 0 critical |
| **core-types** | ✅ | - | - | ✅ |
| **components-types** | ✅ | - | - | ✅ |
| **devtools** | ✅ | ✅ | - | ✅ |
| **examples** | ✅ | - | - | ✅ |

**CI/CD:** All packages use GitHub Actions for automated testing and publishing

---

## 📄 License

MIT © LARC Contributors

All packages are licensed under the MIT License. See individual repositories for details.

---

## 🆘 Support

- 📖 [Documentation](https://larcjs.github.io/site/)
- 🎮 [Interactive Playground](https://larcjs.github.io/larc/playground/)
- 💬 [Discussions](https://github.com/larcjs/core/discussions)
- 🐛 [Issue Tracker](https://github.com/larcjs/core/issues)

---

## 🎉 Featured Examples

Check out real applications built with LARC:

- **[Hybrid Dashboard](https://github.com/larcjs/examples/tree/main/hybrid-dashboard)** — React + Vue + LARC (61% smaller)
- **[Offline Todo App](https://larcjs.github.io/examples/offline-todo-app.html)** — State management showcase
- **[Interactive Playground](https://larcjs.github.io/larc/playground/)** — Browse 57+ components
- **[Invoice Studio](https://github.com/larcjs/examples/tree/main/apps/invoice-studio)** — Professional invoicing
- **[Data Browser](https://github.com/larcjs/examples/tree/main/apps/data-browser)** — Generic data exploration

---

## 🚀 Quick Facts

- **5KB** core (gzipped)
- **261** tests passing across 5 browsers
- **57** UI components ready to use
- **Zero** dependencies in core
- **100%** framework agnostic
- **60%+** bundle size reduction vs full React/Vue

---

**Build better web apps with LARC!** 🚀

*Reduce framework overhead. Increase interoperability. Keep it simple.*
