# TestSprite Guidelines

1. **Selectors**: Always use `data-testid` instead of XPath. This is critical for stability.
2. **Login & Nav**: After login the app always redirects to `/`. If the test targets another page, call `page.goto('/target')` **after** successful login.
3. **PrimeVue Inputs**: For components like `Password` or `InputNumber` with `data-testid` on the wrapper, type into the inner input: `locator('[data-testid="..."] input').fill(...)`.
4. **PrimeVue Select**: For dropdowns (Select), first click the element with `data-testid`, then pick an option from `.p-select-overlay .p-select-option`.
5. **Assertions**: Assert on unique UI elements (headings, labels), not generic text like "Success".
6. **Headless**: Tests must run reliably in headless mode (wait for elements via `wait_for_selector`, not fixed timeouts).

## Available data-testid for filters

- `voice-filter` - voice selection filter. Options have `data-testid="voice-option-{VOICE_CODE}"` (e.g., `voice-option-RU_SYNODAL`).
- `book-filter` - book selection filter. Options have `data-testid="book-option-{BOOK_NUMBER}"`.
- `anomaly-type-filter` - anomaly type filter
- `status-filter` - status filter. Options have `data-testid="status-option-{STATUS}"`.
