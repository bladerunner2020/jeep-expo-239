# JSEP Issue 239

This repo was created to reproduce the issue described in [PR #239](https://github.com/EricSmekens/jsep/pull/239) of the **jsep** package.
This repo was created with [`create-expo-app`](https://www.npmjs.com/package/create-expo-app).

## How to reproduce issue

1. Install the app and run

   ```bash
   git clone https://github.com/bladerunner2020/jsep-expo-239
   cd jsep-expo-239
   npm install
   npm expo start
   ```

   You can start the React Native app in a web browser by pressing 'w'. In the browser, there is no issue.

2. Install [Android emulator](https://docs.expo.dev/workflow/android-studio-emulator/)

3. Try to launch the app in the emulator by pressing 'a'.

   You should get an error: `ERROR  TypeError: Restricted in strict mode, js engine: hermes`.

4. Comment out line 12 in explore.tsx: `const { Jsep } = require('jsep');` and the error is gone.

## Description

To reproduce this issue, you need to create an app with create-expo-app, install jsep, and add require('jsep'). Basically, this is what has been done in this repo.

