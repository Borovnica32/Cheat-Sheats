# Basic Playwright Commands

## 1. Create a New Playwright Project
```cmd
npm init playwright@latest
```

## 2. Run Tests
```cmd
npx playwright test
```

## 3. Run Tests in UI Mode
```cmd
npx playwright test --ui
```

## 4. Run Tests in a Specific Browser
```cmd
npx playwright test --project=chromium
```

## 5. Generate Code
```cmd
npx playwright codegen
```

## 6. Show Playwright Report
```cmd
npx playwright show-report
```

---

# Basic Playwright Commands for Element Locators and UI Actions

## 1. Locating Elements
### By ID
```ts
await page.locator('#elementId').click();
```

### By class
```ts
await page.locator('.className').click();
```

### By text content
```ts
await page.locator('text=Click me').click();
```

### By CSS selector
```ts
await page.locator('button.submit-button').click();
```

### By XPath
```ts
await page.locator('//button[contains(text(), "Submit")]').click();
```


## 2. Additional Element Locators
### By text content
```ts
await page.getByText('Click me').click();
```

### By label
```ts
await page.getByLabel('Username').fill('myusername');
```

### By placeholder
```ts
await page.getByPlaceholder('Enter your email').fill('user@example.com');
```

### By role
```ts
await page.getByRole('button', { name: 'Submit' }).click();
```

### By test id
```ts
await page.getByTestId('submit-button').click();
```

### By title
```ts
await page.getByTitle('Help').click();
```

### By alt text (for images)
```ts
await page.getByAltText('Logo').click();
```

### Combining locators
```ts
await page.getByRole('button').filter({ hasText: 'Submit' }).click();
```


## 3. UI Actions
### Click an element
```ts
await page.click('button');
```

### Fill a form field
```ts
await page.fill('#username', 'myusername');
```

### Type text
```ts
await page.type('#search', 'Playwright');
```

### Select an option from a dropdown
```ts
await page.selectOption('select#colors', 'blue');
```

### Check/uncheck a checkbox
```ts
await page.check('input[type="checkbox"]');
await page.uncheck('input[type="checkbox"]');
```

### Hover over an element
```ts
await page.hover('a.dropdown-trigger');
```

### Drag and drop
```ts
await page.dragAndDrop('#draggable', '#droppable');
```

### Upload a file
```ts
await page.setInputFiles('input[type="file"]', 'path/to/file.jpg');
```

### Press a key
```ts
await page.press('#textarea', 'Enter');
```

---

# Debugging Playwright Tests

## 1. Using the Playwright Inspector
### Run tests with the inspector
```cmd
npx playwright test --debug
```

### Run a specific test file with the inspector
```cmd
npx playwright test example.spec.ts --debug
```

## 2. Adding Breakpoints in Your Code
```ts
// Add a debugger statement where you want to pause
test('my test', async ({ page }) => {
  await page.goto('<https://example.com>');
  debugger; // The test will pause here when running in debug mode
  await page.click('button');
});
```

## 3. Using VS Code for Debugging
* Install the Playwright Test for VS Code extension.
* Set breakpoints in your code by clicking on the gutter (the area to the left of the line numbers).
* Use the VS Code Debug view to run your tests and pause at the breakpoints.

## 4. Debugging Headless Browsers
```ts
// In your playwright.config.ts file
use: {
  headless: false,
  slowMo: 1000, // Slows down Playwright operations by 1 second
}
```

## 5. Using console.log for Quick Debugging
```ts
test('my test', async ({ page }) => {
  await page.goto('<https://example.com>');
  const title = await page.title();
  console.log('Page title:', title); // This will be printed in the console
  expect(title).toBe('Expected Title');
});
```

---

# Assertions in Playwright

## 1. Expect Library
```ts
const { expect } = require('@playwright/test');
test('assertion example', async ({ page }) => {
  await page.goto('<https://example.com>');
  
  // Equality
  expect(await page.title()).toBe('Example Domain');
  
  // Contains
  expect(await page.textContent('body')).toContain('Example');
  
  // Visibility
  await expect(page.locator('h1')).toBeVisible();
  
  // Element state
  await expect(page.locator('button')).toBeEnabled();
  
  // Attribute
  await expect(page.locator('a')).toHaveAttribute('href', '<https://www.iana.org/domains/example>');
});
```

## 2. Page Assertions
```ts
test('page assertions', async ({ page }) => {
  await page.goto('<https://example.com>');
  
  // URL assertions
  await expect(page).toHaveURL('<https://example.com>');
  
  // Title assertions
  await expect(page).toHaveTitle(/Example Domain/);
});
```

## 3. Element Assertions
```ts
test('element assertions', async ({ page }) => {
  await page.goto('<https://example.com>');
  
  const heading = page.locator('h1');
  
  // Text content
  await expect(heading).toHaveText('Example Domain');
  
  // Class
  await expect(heading).toHaveClass('example-class');
  
  // Count
  await expect(page.locator('p')).toHaveCount(2);
});
```

## 4. Custom Assertions
```ts
test('custom assertion', async ({ page }) => {
  await page.goto('<https://example.com>');
  
  // Custom assertion function
  const assertColor = async (element, expectedColor) => {
    const color = await element.evaluate((el) => {
      return window.getComputedStyle(el).getPropertyValue('color');
    });
    expect(color).toBe(expectedColor);
  };
  
  await assertColor(page.locator('h1'), 'rgb(0, 0, 0)');
});
```

--- 

# API & JSON

## 1. Basic API Requests
### GET request
```ts
const response = await request.get('https://api.example.com/data');
```

### POST request
```ts
const response = await request.post('https://api.example.com/login', {
  form: {
    username: 'user',
    password: 'pass'
  }
});
```
**What gets sent:**
Content-Type: application/x-www-form-urlencoded

**Body:**
username=user&password=pass

### POST JSON
```ts
const response = await request.post('https://api.example.com/data', {
  data: {
    name: 'test',
    value: 123
  }
});
```
**What gets sent:**
Content-Type: application/json

**Body:**
```json
{
  "name": "test",
  "value": 123
}
```

## 2. Response Handling
### Status check
```ts
expect(response.ok()).toBeTruthy();
expect(response.status()).toBe(200);
```

### Convert to JSON
```ts
const body = await response.json();
```

### Get raw text
```ts
const text = await response.text();
```

## 3. JSON Assertions
### Check field value
```ts
expect(body.table).toBe('Samsonite');
```

### Check array
```ts
expect(Array.isArray(body.data)).toBeTruthy();
```

### Check length
```ts
expect(body.data.length).toBeGreaterThan(0);
```

### Check object property
```ts
expect(body.data[0]).toHaveProperty('set_id');
```

### API Assertion
```ts
await test.step('Assertion name', async() => {
  try{
    // Try logic
  } catch(e) {
    // Catch Logic
    throw e;
  }
});
```

## 4. Searching in JSON
### Find item
```ts
const item = body.data.find(x => x.set_id === '078-1');

expect(item).toBeTruthy();
```

### Filter items
```ts
const filtered = body.data.filter(x => x.theme === 'Star Wars');

expect(filtered.length).toBeGreaterThan(0);
```

## 5. Response Time Testing
```ts
const start = Date.now();

const response = await request.get(API_URL);

const duration = Date.now() - start;

console.log(`Response time: ${duration} ms`);

expect(duration).toBeLessThan(1000);
```

## 6. File Upload (API)
```ts
import fs from 'fs';

const response = await request.post(API_URL, {
  multipart: {
    file: {
      name: 'upload.7z',
      mimeType: 'application/x-7z-compressed',
      buffer: fs.readFileSync('upload.7z')
    }
  }
});
```

## 7. Headers & Auth
```ts
Add headers
const response = await request.get(API_URL, {
  headers: {
    Authorization: 'Bearer token'
  }
});
```

## 8. Query Parameters
```ts
const response = await request.get(
  `https://api.com/data?name=Star Wars`
);
```

## 9. Advanced Assertions
```ts
Check all items have field
for (const item of body.data) {
  expect(item).toHaveProperty('name');
}
Check values match condition
for (const item of body.data) {
  expect(Number(item.year)).toBeGreaterThan(1950);
}
```

## 10. Combine API + UI (power move)
```ts
const res = await request.get(API_URL);
const body = await res.json();

const firstItem = body.data[0];

await page.goto('http://your-ui');

await expect(page.getByText(firstItem.name)).toBeVisible();
```
