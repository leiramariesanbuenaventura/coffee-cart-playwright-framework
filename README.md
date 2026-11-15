# Coffee Cart – Playwright Automation Framework

A TypeScript-based Playwright automation framework for end-to-end testing of the [Coffee Cart](https://coffee-cart.app/) web application. This project demonstrates maintainable test architecture using the Page Object Model (POM), reusable Playwright fixtures, resilient locators, and continuous integration through GitHub Actions.

## Project Overview

This project was developed as part of a Quality Assurance (QA) automation testing activity. Its primary objective is to build a foundational test automation framework that prioritizes maintainability, scalability, and reliability rather than simply automating a single successful test flow.

The framework automates the coffee purchasing process, from selecting products to completing checkout and verifying successful payment submission.

**Target Application:** [https://coffee-cart.app/](https://coffee-cart.app/)

## Objectives

- Build a reusable and maintainable Playwright automation framework.
- Implement the Page Object Model (POM) to separate test logic from page interactions.
- Utilize Playwright fixtures for test setup, teardown, and state management.
- Apply resilient locators and Playwright's built-in auto-waiting capabilities.
- Separate test data from test logic.
- Integrate automated test execution into a CI pipeline using GitHub Actions.
- Explore additional UI interactions and application-specific features.

## Tech Stack

| Technology | Purpose |
|---|---|
| TypeScript | Primary programming language |
| Playwright | End-to-end browser automation |
| Node.js | JavaScript runtime |
| Page Object Model | Test architecture and abstraction |
| GitHub Actions | Continuous Integration |
| npm | Package management |

## Automated Test Scenarios

### Core Workflow

The primary automated scenario covers the complete coffee purchasing journey.

1. **Add Product** – Select and add coffee products to the shopping cart.
2. **Handle Promotional Popup** – Detect and handle promotional coffee popups when applicable.
3. **Checkout** – Proceed to the checkout process.
4. **Submit Payment Details** – Enter the required customer and payment information.
5. **Verify Success** – Validate that the checkout process completes successfully.

### Additional Test Scenarios

The framework also explores the application's interactive features:

| Feature | Test Scenario |
|---|---|
| Coffee Title Translation | Double-click a coffee title and verify that it translates into Chinese. |
| Add-to-Cart Dialog | Right-click a coffee icon and verify that the add-to-cart dialog appears. |
| Promotional Popup | Verify that a promotional coffee popup appears when adding every third item to the cart (3rd, 6th, 9th, etc.). |

*Note: These scenarios describe the intended test coverage. Update this section as individual tests are implemented and verified.*

## Framework Architecture

The framework follows the Page Object Model (POM) to promote code reusability, separation of concerns, and easier maintenance.

### Design Principles

- **Page Object Model:** Encapsulates page elements and interactions into reusable page classes.
- **Playwright Fixtures:** Manages browser-related setup, teardown, and shared test dependencies.
- **Test Data Separation:** Keeps test data independent from test implementation.
- **Resilient Locators:** Uses reliable selectors and Playwright auto-waiting instead of arbitrary sleep durations.
- **Reusable Components:** Encourages consistent implementation and easier collaboration among developers.

### Suggested Project Structure

```text
coffee-cart-playwright-framework/
│
├── .github/
│   └── workflows/
│       └── playwright.yml
│
├── src/
│   ├── pages/
│   │   ├── BasePage.ts
│   │   ├── HomePage.ts
│   │   ├── CartPage.ts
│   │   └── CheckoutPage.ts
│   │
│   ├── fixtures/
│   │   └── test-fixtures.ts
│   │
│   └── test-data/
│       └── checkout-data.ts
│
├── tests/
│   ├── checkout.spec.ts
│   └── special-features.spec.ts
│
├── playwright-report/
├── test-results/
│
├── playwright.config.ts
├── package.json
├── package-lock.json
├── tsconfig.json
└── README.md
```

*The structure above is a suggested organization. Adjust it to match the actual repository.*

## Getting Started

### Prerequisites

Make sure the following are installed:

- [Node.js](https://nodejs.org/)
- npm (included with Node.js)
- [Git](https://git-scm.com/)
- [Visual Studio Code](https://code.visualstudio.com/) (recommended)

### Installation

1. Clone the repository:

   ```bash
   git clone <repository-url>
   ```

2. Navigate to the project directory:

   ```bash
   cd coffee-cart-playwright-framework
   ```

3. Install dependencies:

   ```bash
   npm install
   ```

4. Install Playwright browsers:

   ```bash
   npx playwright install --with-deps
   ```

### Running Tests

Run all automated tests:

```bash
npx playwright test
```

Run tests in headed mode:

```bash
npx playwright test --headed
```

Run a specific test file:

```bash
npx playwright test tests/checkout.spec.ts
```

Run tests with the Playwright UI:

```bash
npx playwright test --ui
```

View the HTML test report:

```bash
npx playwright show-report
```

## Continuous Integration

This project includes a GitHub Actions workflow to demonstrate automated test execution within a CI pipeline.

The workflow is designed to:

1. Trigger when code is pushed or a pull request is created.
2. Set up the Node.js environment.
3. Install project dependencies.
4. Install the required Playwright browsers.
5. Execute the automated test suite.
6. Generate and retain test reports and results as CI artifacts.

Workflow configuration:

`.github/workflows/playwright.yml`

## Quality Assurance Considerations

The framework follows several practices to improve test reliability:

- Avoids hardcoded sleep functions and arbitrary wait times.
- Uses Playwright auto-waiting and web-first assertions.
- Prioritizes accessible and stable locators.
- Separates test data, page interactions, and test assertions.
- Uses reusable fixtures to manage test dependencies.
- Supports continuous testing through GitHub Actions.

## References

- [Coffee Cart Application](https://coffee-cart.app/)
- [Playwright Documentation](https://playwright.dev/docs/intro)
- [Playwright Test Fixtures](https://playwright.dev/docs/test-fixtures)
- [Page Object Model](https://playwright.dev/docs/pom)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)

---

**Disclaimer:** This repository is intended for educational and Quality Assurance testing purposes. All automated tests target the publicly available Coffee Cart demo application.
