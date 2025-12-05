# 🚀 Contributing to HealthMetric: The Apex Standard

Thank you for considering contributing to `HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App`. We enforce rigorous development standards aligned with our "Zero-Defect, High-Velocity, Future-Proof" philosophy. All contributions are welcome, provided they meet the standards outlined below.

## 1. Code of Conduct

All contributors must adhere to the [Code of Conduct](https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/blob/main/CODE_OF_CONDUCT.md). Maintaining a respectful and professional environment is mandatory.

## 2. Getting Started: Setting Up the Local Development Environment

This project is built using React Native and Expo, leveraging TypeScript for strict type safety.

### Prerequisites
*   Node.js (LTS version)
*   Expo CLI (installed globally or via `npx`)
*   Git

### Installation
1.  **Clone the Repository:**
    bash
git clone https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App.git
cd HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App
    
2.  **Install Dependencies:**
    We utilize `npm` for dependency management.
    bash
npm install
    
3.  **Start the Development Server:**
    bash
npx expo start
    

## 3. Submission Flow & Branching Strategy

We utilize a robust Git branching strategy (`main`, `feature/*`, `hotfix/*`).

### 3.1. Reporting Issues
Before submitting an issue, please search the existing [Issues list](https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/issues) to prevent duplication.
*   For **Bug Reports**, use the detailed [Bug Report Template](https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/blob/main/.github/ISSUE_TEMPLATE/bug_report.md).
*   For **Feature Requests**, clearly articulate the value proposition and proposed solution.

### 3.2. Creating Pull Requests (PRs)
1.  Create a dedicated branch from the latest `main` branch: 
    `git checkout -b feature/my-new-feature-name`
2.  Ensure your code passes all linting, formatting, and tests (see Section 4).
3.  Use the provided [Pull Request Template](https://github.com/chirag127/HealthMetric-Pedometer-And-Activity-Tracker-Mobile-App/blob/main/.github/PULL_REQUEST_TEMPLATE.md) to provide comprehensive context, screenshots (if applicable), and testing evidence.
4.  Target the `main` branch for review.

## 4. Development Standards

### 4.1. Coding Principles & Architecture
*   **Architecture:** We strictly adhere to the **Feature-Sliced Design (FSD)** methodology for scalable mobile architecture. Components must reside in the correct layer (`shared`, `entities`, `features`, `widgets`, `pages`, `app`).
*   **TypeScript:** Type safety is paramount. All exported functions and complex object structures must be explicitly typed. Avoid implicit `any` usage.
*   **SOLID/DRY:** Follow architectural best practices: Single Responsibility Principle, Don't Repeat Yourself, and favor composition over inheritance.

### 4.2. Linting and Formatting (Biome)
We enforce code style and consistency using **Biome**. The CI pipeline will fail if checks are not passed.

bash
# Check for linting and formatting errors
npm run lint:check

# Automatically fix most formatting and linting issues
npm run lint:fix


### 4.3. Testing (Vitest & Playwright)
Robust testing is required for all new functionality. New features must include relevant tests.

*   **Unit Tests:** Use **Vitest** for testing business logic, utilities, and small components. Files should reside next to the component/module they test (`*.test.tsx`).
*   **E2E/Integration Tests:** Use **Playwright** for verifying critical user flows (e.g., successful activity tracking, dashboard loading).

bash
# Run all unit tests
npm run test:unit

# Run all integration/e2e tests (requires device/simulator setup)
npm run test:e2e


### 4.4. Conventional Commits
All commits must adhere to the [Conventional Commits Specification](https://www.conventionalcommits.org/en/v1.0.0/) to enable automated versioning and release notes generation.

**Format:** `<type>(<scope>): <description>`

| Type | Description | Example |
| :--- | :--- | :--- |
| `feat` | A new feature implementation. | `feat(pedometer): Integrate HealthKit step count API` |
| `fix` | A bug fix. | `fix(ui): Correct modal overflow on small screens` |
| `refactor` | Code change that neither fixes a bug nor adds a feature. | `refactor(shared): Consolidate theme definitions` |
| `chore` | Build process or dependency changes. | `chore(deps): Update expo to SDK 51` |
| `docs` | Documentation only changes. | `docs(readme): Clarify setup instructions` |

PRs will be automatically squashed and merged, preserving the primary conventional commit message.