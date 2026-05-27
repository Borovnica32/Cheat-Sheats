# Basic Playwright Commands

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

---

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

---

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