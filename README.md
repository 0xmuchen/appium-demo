# Introduction

This project demonstrates mobile test automation using WebDriverIO, focusing on the functionality and appearance of the [Google Translate](https://play.google.com/store/apps/details?id=com.google.android.apps.translate) Android app. It includes both functional and non-functional autotests, with UI regression tests that compare current views to predefined screenshots.

**Note:** This project does not aim to cover all functionality and views of Google Translate.

## Features

- **Test Suite Execution:** Run autotests by suite names: `main screen`, `select language screen`, and `all tests`.
- **UI Regression Tests:** Compare current views to predefined screenshots. Differences are highlighted in red.

  ![UI Comparison](https://github.com/0xmuchen/appium-demo/raw/master/demo/DifferenceInAllure.png)

- **Allure Reports:** Includes screenshots and links to issues marked with `ISSUE =>` in the test labels. Custom `@step()` decorator for ease of use.

  ![Allure Report](https://github.com/0xmuchen/appium-demo/raw/master/demo/AllureReport.png)

- **Modular WebDriverIO Configuration:** Separated settings to avoid conflicts in different pipeline environments.
- **Static Code Analysis:** Uses `ESLint` and `CodeQL` for code quality checks on push and pull requests.
- **Customizable Logging:** Set log levels (e.g., `debug`) via `.env` for improved readability and debugging.

  ![Logs](https://github.com/0xmuchen/appium-demo/raw/master/demo/Logs.png)


- **Easy-to-use Imports:** Simplify imports by using `ApplicationScreens` for screen functions.

  ```js
  import { ApplicationScreens } from '@screens/ApplicationScreens';
  
  await screens.mainScreen.function();
  await screens.selectLanguageScreen.function();
  ```

## Project Structure

- `.github/` - Static code analysis pipeline configuration.
- `config/` - WebDriverIO and reporter configurations.
- `demo/` - Screenshots for `README.md`.
- `docs/` - Instructions and guidelines.
- `google-translate-autotests/` - Functional and non-functional tests.
- `screens/` - Screen selectors and functions.
- `support/` - Utilities and test data.
- `package.json` - Scripts and dependencies.
- `tsconfig.json` - TypeScript import setup.

## Setup

### 1. Prerequisites
- Install [Node.js and NPM](https://radixweb.com/blog/installing-npm-and-nodejs-on-windows-and-mac).
- Install TypeScript if necessary.

### 2. Install Dependencies

```bash
npm install
```

### 3. Mobile Emulator Setup
- Install [Appium](https://github.com/appium/appium).
- Follow [Appium Inspector setup instructions](https://github.com/0xmuchen/appium-demo/blob/master/docs/APPIUM.md).
- Install [Android Studio](https://developer.android.com/studio) and create a device. Add device capabilities to `.env`.

Example `.env`:

```env
PLATFORM_NAME=Android
DEVICE_NAME=Pixel 6 API 30
PLATFORM_VERSION=11

RETRIES=1 #optional retries on fail number, 0 by default
MAX_INSTANCES=1 #optional parallel runs number, 1 by default
LOG_LVL=silent #optional log level, available 'trace' | 'debug' | 'info' | 'warn' | 'error' | 'silent'

```

### 4. Run Tests

1. Start the Android device in Android Studio.
2. Add the `.apk` file to the `app/` folder.
3. Run the desired suite:

```bash
npm run run-functional-autotests
```

## Tech stack

- [TypeScript](https://www.typescriptlang.org/) 
- [NPM](https://www.npmjs.com/) 
- [WebDriverIO](https://webdriver.io/uk/) 
- [Mocha](https://github.com/mochajs/mocha) 
- [Appium](https://github.com/appium/appium) 
- [Pixelmatch](https://github.com/mapbox/pixelmatch) 
- [Allure Report](https://webdriver.io/docs/allure-reporter/)
