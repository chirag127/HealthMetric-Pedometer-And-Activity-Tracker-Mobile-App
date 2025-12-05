# HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App 
## 🏃 Real-Time Biometric Data & Activity Visualization Platform

<!-- VISUAL AUTHORITY (Above the Fold) -->

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://user-images.githubusercontent.com/66981880/209149957-3f3f5a2b-8a8b-4b2a-8c8c-1e2e7c3b2d1d.png">
    <img src="https://user-images.githubusercontent.com/66981880/209149957-3f3f5a2b-8a8b-4b2a-8c8c-1e2e7c3b2d1d.png" alt="HealthMetric Logo - Abstract Data Flow" width="600">
  </picture>
  <br/>
  
  [![Stars](https://img.shields.io/github/stars/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App?style=flat-square&color=FFC72C&label=STARS&logo=github)](https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/stargazers)
  [![Build Status](https://img.shields.io/github/actions/workflow/status/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/ci.yml?branch=main&style=flat-square&label=CI%2FCD&logo=githubactions)](https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/actions/workflows/ci.yml)
  [![Coverage](https://img.shields.io/codecov/c/github/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App?style=flat-square&token=YOUR_CODECOV_TOKEN&label=CODE%20COVERAGE&logo=codecov)](https://codecov.io/gh/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App)
  [![Language](https://img.shields.io/badge/Language-TypeScript-blue.svg?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
  [![Framework](https://img.shields.io/badge/Framework-React%20Native%20%2F%20Expo-61DAFB.svg?style=flat-square&logo=react)](https://reactnative.dev/)
  [![Linter](https://img.shields.io/badge/Linter%20%2F%20Formatter-Biome-3f3f3f.svg?style=flat-square&logo=biome)](https://biomejs.dev/)
  [![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-brightgreen.svg?style=flat-square)](LICENSE)
</div>

---

## 🚀 Overview (Zero-Defect Mobile Health Tracking)

HealthMetric is a high-performance, cross-platform mobile application built with **React Native** and **Expo**, engineered for seamless, real-time biometric data capture, rigorous activity tracking, and comprehensive health visualization. Utilizing native modules for high-fidelity sensor data access (HealthKit/Google Fit), this platform delivers professional-grade reliability and modularity via the **Feature-Sliced Design (FSD)** architecture.

This solution provides users with immediate feedback loops on physical activity (pedometer, distance, calorie burn) and securely manages biometric history, adhering to the highest standards of mobile performance and data privacy.

## 🗺️ System Architecture: Feature-Sliced Design (FSD)

This project strictly adheres to the Feature-Sliced Design (FSD) methodology, promoting scalable, maintainable, and decoupled components suitable for large, evolving mobile applications.

### Folder Structure (Conceptual Tree)

mermaid
graph TD
    A[src: Source Root] --> B[app: Global Config & Context];
    A --> C[pages: Screen/Route Definitions];
    A --> D[widgets: Complex UI Blocks];
    A --> E[features: User Interaction Logic];
    A --> F[entities: Business Objects & Data Handling];
    A --> G[shared: Reusable Primitives (UI, Hooks, Utils)];

    E --> H[features/Pedometer: Sensor Logic];
    E --> I[features/Auth: Biometric/Account];
    F --> J[entities/User: Profile Management];
    F --> K[entities/Metric: Step/Activity Data Schema];
    G --> L[shared/ui: Base Components];
    G --> M[shared/api: Data Access Layers];


## 📜 Table of Contents
1.  [Overview](#🚀-overview-zero-defect-mobile-health-tracking)
2.  [System Architecture: FSD](#🗺️-system-architecture-feature-sliced-design-fsd)
3.  [Apex AI Agent Directives](#🤖-apex-ai-agent-directives-ssot)
4.  [Technology Stack](#⚙️-technology-stack)
5.  [Getting Started](#🛠️-getting-started)
6.  [Development Scripts](#🔬-development-scripts)
7.  [Core Architectural Principles](#💎-core-architectural-principles)
8.  [License](#©️-license)

---

## 🤖 Apex AI Agent Directives (SSOT)

<details>
<summary>⚡ View Mandatory Configuration & Architectural Constraints for AI Agents</summary>
<br>

### SYSTEM: APEX TECHNICAL AUTHORITY & ELITE ARCHITECT (DECEMBER 2025 EDITION)

**1. ARCHITECTURAL MANDATES**
*   **Architecture Pattern:** Feature-Sliced Design (FSD). Components must be strictly confined to their respective layers (`shared` cannot access `features`, etc.).
*   **Data Flow:** Unidirectional data flow (e.g., Redux Toolkit or Zustand) must be utilized for state management, particularly for real-time sensor streams.
*   **Mobile Framework:** React Native / Expo. Must prioritize the utilization of the Expo SDK for non-ejected workflow, unless native performance requires a highly optimized C++/Kotlin module wrapper.

**2. TECHNOLOGY STACK DEFINITION**
| Area | Tool/Library | Purpose | Mandate |
| :--- | :--- | :--- | :--- |
| **Language** | TypeScript (Strict) | Type safety and scalability | All new files must be `.ts`/`.tsx`. |
| **Framework** | React Native / Expo | Cross-platform mobile development | Utilize Expo modules for Pedometer/HealthKit interaction. |
| **Linter/Formatter**| Biome | Ultra-fast code quality enforcement | Must pass all `biome check` and `biome format` rules. |
| **Testing** | Jest/React Native Testing Library | Unit and component testing | Require 90%+ component test coverage (using `shared/ui`). |
| **Styling** | Tailwind CSS v4 (Native) | Utility-first CSS framework | Use native extension for zero-runtime styling. |

**3. VERIFICATION & QUALITY ASSURANCE PROTOCOL**
All code modifications or feature additions MUST be verified using the following commands:
1.  **Dependency Synchronization:** `npm install` (Ensuring parity between `package.json` and `node_modules`).
2.  **Linting & Formatting Check:** `npm run lint` (Executes Biome checks).
3.  **Unit & Integration Test Execution:** `npm run test:ci` (Runs Jest/Vitest in CI mode).
4.  **Local Dev Server Startup:** `npm start` (Runs the Expo development server).
5.  **Native Module Integrity:** `npx expo prebuild` (Used only when modifying native dependencies).

</details>

---

## ⚙️ Technology Stack

This application is built using the following Apex Standard toolset for mobile development:

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| **Core Framework** | React Native | Cross-platform mobile UI construction. |
| **Build System** | Expo SDK | Simplified native development and Over-The-Air (OTA) updates. |
| **Language** | TypeScript (Strict) | Enhanced code integrity and type enforcement. |
| **State Management**| Zustand | Lightweight, efficient, and scalable state container. |
| **Styling** | Tailwind CSS (Native) | Utility-first styling for rapid UI development. |
| **Data Access** | React Query | Asynchronous data fetching, caching, and synchronization. |
| **Code Quality** | Biome | Linter and formatter for enforced standardization. |

---

## 🛠️ Getting Started

To set up and run the HealthMetric application locally, ensure you have Node.js (LTS), npm, and the Expo CLI installed.

### Prerequisites

bash
# Install Node.js/npm globally if not present
# Install the Expo CLI
npm install -g expo-cli


### 1. Installation

Clone the repository and install the dependencies:

bash
git clone https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App.git
cd HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App
npm install


### 2. Running Locally

Start the development server:

bash
npm start


This will launch the Expo Metro bundler. You can then:
*   Scan the QR code with the Expo Go app (iOS/Android).
*   Press `i` to launch on an iOS Simulator.
*   Press `a` to launch on an Android Emulator.

### 3. Native Prebuild (If modifying native modules)

If you modify `app.json` or add libraries requiring native linking, run:

bash
npx expo prebuild --clean


---

## 🔬 Development Scripts

| Script | Command | Description |
| :--- | :--- | :--- |
| `start` | `expo start` | Starts the Expo development server. |
| `android` | `expo run:android` | Builds and runs the app on an Android device/emulator. |
| `ios` | `expo run:ios` | Builds and runs the app on an iOS device/simulator. |
| `build:prod` | `expo build --platform all` | Builds production artifacts (APK/AAB/IPA). |
| `test` | `jest` | Runs unit and integration tests. |
| `test:ci` | `jest --ci` | Runs tests suitable for continuous integration environments. |
| `lint` | `npx biome check --apply .` | Runs the Biome linter and applies fixes. |
| `format` | `npx biome format --write .` | Formats all source files using Biome rules. |

---

## 💎 Core Architectural Principles

All contributions and feature implementations must adhere to the following principles enforced by the Apex Technical Authority:

*   **S.O.L.I.D. Principles:** Strict adherence, especially Dependency Inversion (avoiding direct concrete class dependencies) and Single Responsibility Principle (enforced via FSD structure).
*   **DRY (Don't Repeat Yourself):** Abstract shared logic (utility functions, hooks, base UI components) into the `shared` layer of the FSD structure.
*   **YAGNI (You Ain't Gonna Need It):** Minimize complexity; implement only the necessary functionality for the current sprint goal.
*   **Immutability:** State updates must always be immutable, leveraging modern state management patterns to prevent side effects and simplify debugging.
*   **Performance First:** Prioritize rendering performance, especially in high-frequency update loops (like pedometer data streaming). Memoization (`React.memo`, `useMemo`, `useCallback`) is mandatory for complex or frequently re-rendered components.

---

## ©️ License

This project is released under the **Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)** license.

> You are free to share and adapt the material for non-commercial purposes, provided appropriate credit is given. For commercial use, please contact the author.