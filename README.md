# Coffee Cart E2E (Playwright + TypeScript)

## Layout
- `src/data/`        test data only (no logic)
- `src/components/`  reusable UI pieces (promo popup, payment form, dialogs)
- `src/pages/`       page objects: locators + user actions, **no assertions about business rules**
- `src/fixtures/`    `test` extended with `menuPage`, `cartPage`, `seedCart`
- `tests/`           specs: read like user stories, never touch raw selectors

## Rules for contributors
1. Import `test`/`expect` from `@fixtures`, never from `@playwright/test`.
2. No `waitForTimeout`/`sleep`. Wait on state: `expect(locator).toBeVisible()`.
3. Locators: `getByTestId` > `getByRole` > `getByLabel`. No CSS/XPath in specs.
4. New selectors go in page objects only; test data goes in `src/data`.
5. Tests must be independent (each gets a fresh context/cart).

## Run
`npm ci && npx playwright install && npm test`
Note: selectors are centralised in `src/pages` and `src/components`; if the app's markup differs, fix them there only.
