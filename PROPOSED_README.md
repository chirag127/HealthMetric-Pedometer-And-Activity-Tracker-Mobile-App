# HealthMetric: Pedometer and Activity Tracker Mobile App

[![Build Status](https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/actions/workflows/ci.yml/badge.svg)](https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/actions/workflows/ci.yml)
[![Tech Stack](https://img.shields.io/badge/Stack-React%20Native%20%7C%20Expo-blueviolet?style=flat-square)](https://expo.dev/)
[![Language](https://img.shields.io/badge/Language-TypeScript%20(Strict)-3178C6?style=flat-square)](https://www.typescriptlang.org/)
[![Lint/Format](https://img.shields.io/badge/Lint/Format-Biome-000000?style=flat-square)](https://biomejs.dev/)
[![License](https://img.shields.io/badge/License-CC%20BY--NC%204.0-yellow.svg?style=flat-square)](LICENSE)
[![GitHub Stars](https://img.shields.io/github/stars/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App?style=flat-square&color=FFC300)](https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/stargazers)

<p align="center">
  <a href="https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/stargazers"><img src="https://img.shields.io/badge/Star%20⭐%20this%20Repo-black?style=for-the-badge&logo=github" alt="Star this repository"></a>
</p>

> HealthMetric is a high-performance, cross-platform mobile application built with React Native and Expo, providing real-time activity tracking, detailed biometric visualization, and historical data analysis.

This project establishes a robust, FSD-compliant architecture for consumer-facing health apps, ensuring data privacy, reliability, and superior user experience on both iOS (HealthKit) and Android (Google Fit).

---

## 📋 Table of Contents

1.  [Core Features](#-core-features)
2.  [Architecture & Structure](#-architecture--structure)
3.  [AI Agent Directives](#-ai-agent-directives--technical-blueprint)
4.  [Quick Start & Setup](#-quick-start--setup)
5.  [Development Scripts](#-development-scripts)
6.  [Testing Strategy](#-testing-strategy)

---

## ✨ Core Features

*   **Real-Time Pedometer:** Accurate step counting utilizing native device sensors (`expo-sensors`) with minimal battery impact.
*   **Biometric Data Visualization:** Intuitive charts and dashboards built with Recharts/Victory Native for trend analysis (steps, distance, calories).
*   **Cross-Platform Health Integration:** Seamless synchronization with Apple HealthKit (iOS) and Google Fit (Android) for comprehensive data capture and sharing.
*   **Strict TypeScript Core:** Enterprise-grade type safety enforced across all data models and business logic.
*   **Modular Design (FSD):** Future-proof structure enabling rapid feature development and simplified maintenance.

## 📐 Architecture & Structure

HealthMetric utilizes the **Feature-Sliced Design (FSD)** pattern to ensure clear separation of concerns, strict dependency rules, and high scalability.

mermaid
C4Context

  Boundary(mobile_app, "Mobile Application Boundary") {
    Container(ui, "User Interface", "React Native / Tailwind CSS", "Visual Presentation Layer (Shared Components, Pages)")
    Container(features, "Features Layer", "TypeScript / Business Logic", "User interactions, forms, and complex use cases (e.g., Data Entry, Goal Management)")
    Container(entities, "Entities Layer", "TypeScript / API Models", "Core data models, API clients (HealthKit/Google Fit wrappers), and storage management")
    Container(shared, "Shared Utilities", "TypeScript", "Global constants, helpers, reusable UI components (Atomic Design principles applied)")
  }

  System(healthkit, "Apple HealthKit", "iOS Native Integration")
  System(googlefit, "Google Fit", "Android Native Integration")
  System_Boundary(ecosystem, "External Health Ecosystem")

  Rel(features, entities, "Accesses data via")
  Rel(ui, features, "Calls Feature Use Cases")
  Rel(entities, healthkit, "Connects to", "Bi-Directional Data Sync")
  Rel(entities, googlefit, "Connects to", "Bi-Directional Data Sync")
  Rel(ui, shared, "Uses generic components from")
  Rel(features, shared, "Uses utility functions from")


---

<details>
<summary><h2>🤖 AI AGENT DIRECTIVES & TECHNICAL BLUEPRINT</h2></summary>

# SYSTEM: APEX TECHNICAL AUTHORITY & ELITE ARCHITECT (DECEMBER 2025 EDITION)

## 1. IDENTITY & PRIME DIRECTIVE
**Role:** Senior Principal Software Architect.
**Context:** Current Date is **December 2025**. Building for the 2026 standard.
**Philosophy:** "Zero-Defect, High-Velocity, Future-Proof."

---

## 2. TECHNOLOGY STACK DEFINITION (HealthMetric Mobile App)

### A. PRIMARY SCENARIO: MOBILE / REACT NATIVE / HEALTH (TypeScript)
*   **Core Stack:** **React Native 0.73+**, leveraging the latest **Expo SDK (LTS)** for managed environments, and **TypeScript 5.x (Strict)**.
*   **Platform Integration:** **Expo-Sensors** for step counting (Pedometer API), **HealthKit (iOS)** and **Google Fit (Android)** integration via custom Expo modules or standard APIs.
*   **State Management:** **Zustand** or **Redux Toolkit** (for complex biometric history). Preference for lightweight, hook-based solutions.
*   **Styling:** **Tailwind CSS v4** via `nativewind` for high-velocity, consistent styling across platforms.
*   **Routing:** **React Navigation v6/v7**.
*   **Testing & Quality:** **Biome** (Lint/Format/Check) for absolute code quality adherence. **Jest/Vitest** for unit testing; **Detox** for robust E2E testing on simulators/devices.

### B. ARCHITECTURAL PATTERN: FEATURE-SLICED DESIGN (FSD)
The application structure must strictly follow the **Feature-Sliced Design (FSD)** methodology to ensure modularity, scalability, and predictable dependency flow.
*   **Layers (Top-to-Bottom):** `app` (entry), `pages` (routes), `features` (complex logic/forms), `entities` (data models/API interaction), `shared` (UI components/utils).
*   **Rule of FSD:** Dependencies flow inward (e.g., `features` can depend on `entities` and `shared`, but `entities` cannot depend on `features`).

---

## 3. DEVELOPMENT STANDARDS & VERIFICATION PROTOCOL

### A. APEX PRINCIPLES
*   **SOLID:** Applied strictly to component design and service layer classes.
*   **DRY (Don't Repeat Yourself):** Abstract shared logic into the `shared` layer.
*   **YAGNI (You Ain't Gonna Need It):** No pre-optimization. Prioritize performance optimization based on real-world profiling data, not assumption.

### B. MANDATORY VERIFICATION COMMANDS
The codebase must pass these checks before any release candidate is built:
bash
# 1. Dependency Integrity Check
npm install 
# 2. Strict Linting, Formatting, and Code Check (Biome is SSOT)
npm run check
# 3. Unit and Component Testing
npm run test:unit
# 4. End-to-End Mobile Simulation Testing (Detox Required)
npm run test:e2e
# 5. Native Module Prebuild Verification (Checks for environmental readiness)
npx expo prebuild


</details>

---

## 🚀 Quick Start & Setup

This project requires Node.js (LTS), `npm` (or `yarn`/`pnpm`), and Expo CLI installed globally.

1.  **Clone the Repository:**
    bash
    git clone https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App.git
    cd HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App
    

2.  **Install Dependencies (using `npm`):**
    bash
    npm install
    

3.  **Run Locally (Development Mode):**
    bash
    npm start
    # Scan the QR code with the Expo Go app on your mobile device.
    

4.  **Run Native Environment Checks (Mandatory for complex modules):**
    bash
    npx expo prebuild
    

## 💻 Development Scripts

| Script | Command | Description |
| :--- | :--- | :--- |
| `start` | `npx expo start` | Starts the Expo development server. |
| `android` | `npx expo run:android` | Builds and runs the app on a connected Android device/emulator. |
| `ios` | `npx expo run:ios` | Builds and runs the app on a connected iOS simulator. |
| `check` | `npm run biome check --apply` | Executes Biome for strict linting, formatting, and organization. |
| `test:unit` | `vitest run` | Runs unit tests (covering shared utilities and state entities). |
| `test:e2e` | `detox build && detox test` | Executes full end-to-end testing scenarios. |

## 🧪 Testing Strategy

We employ a robust, multi-tiered testing strategy based on the testing pyramid:

1.  **Unit Tests (Vitest):** Focus on pure functions, utility modules (`shared`), and state reducers (`entities`). Target 90%+ coverage here.
2.  **Component Tests (React Native Testing Library):** Ensure individual UI components (`shared` components, simple `features`) render correctly and respond to user events.
3.  **E2E Tests (Detox):** Verify critical user flows (e.g., onboarding, tracking session start/stop, data synchronization) across native platforms.