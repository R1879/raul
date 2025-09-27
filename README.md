Playwright & Allure Test Automation Guide 
Project: Sauce Labs Demo App 
Version: 1.0.0 
1. Prerequisites 
Before starting, ensure the following are installed: 
• Node.js (v16+) – Download Node.js 
• npm (comes with Node.js) 
• Git – Download Git 
• Allure Commandline – Allure Installation 
• Playwright browsers (Chromium, Firefox, WebKit) 
2. Project Setup 
1. Clone the repository: 
git clone <your-repo-url> 
cd saucelab 
2. Install dependencies: 
npm install 
3. Install Playwright browsers: 
npx playwright install 
4. Configure environment variables in a .env file (if required). 
3. Project Structure 
saucelab/ 
│ 
├─ tests/ 
│   ├─ login.test.js 
│   ├─ checkout.test.js 
│   ├─ logout.test.js 
│   └─ e2e.spec.js 
│ 
├─ pages/ 
│   ├─ loginPage.js 
│   ├─ checkoutPage.js 
│ 
├─ playwright.config.js 
├─ package.json 
└─ .env 
• tests/ – Test cases. 
• pages/ – Page Object Model files. 
• playwright.config.js – Playwright configuration. 
• package.json – Project scripts and dependencies. 
4. Running Test Cases 
Use the scripts in your package.json: 
Script 
Run all tests 
Run login tests 
Command 
npm test 
npm run test:login 
Run checkout tests npm run test:checkout 
Run logout tests 
npm run test:logout 
Run end-to-end tests npm run test:e2e 
Optional Flags 
• Run in headed mode (UI visible): 
npx playwright test --headed 
• Run specific browser: 
npx playwright test --project=firefox 
• Run a single test for debugging: 
test.only('Login test', async ({ page }) => { ... }); 
• Skip a test temporarily: 
test.skip('Checkout test', async ({ page }) => { ... }); 
5. Generating Reports 
5.1 Playwright HTML Report 
Generate and view report: 
npm run report 
This opens the HTML report in your default browser showing passed, failed, and skipped 
tests. 
5.2 Allure Report 
Generate Allure report: 
npm run allure:generate 
Open Allure report: 
npm run allure:open 
Allure reports provide detailed visuals including graphs, steps, and screenshots. 
6. Tips & Best Practices 
• Keep credentials and sensitive data in .env file. 
• Use Page Object Model for maintainable test scripts. 
• Keep tests isolated to avoid dependencies between them. 
• Capture screenshots on failure for better debugging: 
await page.screenshot({ path: 'screenshot.png' }); 
• Use tags or annotations to categorize tests for selective execution. 
This guide covers installation, running tests, and generating reports for your Sauce 
Labs demo automation project.
