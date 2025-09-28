# App Maker Template

This is the template repository for the App Maker automated build system.

## Purpose

This repository contains a React Native WebView template that gets automatically customized and built into Android APKs when triggered by the App Maker system.

## How It Works

1. Firebase Functions trigger GitHub Actions workflow
2. GitHub Actions downloads this template
3. Template gets customized with order data (app name, website, icons, etc.)
4. Android APK gets built using Gradle
5. APK gets uploaded to Firebase Storage
6. Order status gets updated in Firestore

## Files Structure

- `App.js` - Main React Native WebView app
- `app.json` - Expo app configuration
- `package.json` - Node.js dependencies
- `android/` - Android build configuration
- `assets/` - App assets (icons, splash screens)

## Configuration

The template uses placeholders that get replaced during the build process:
- `APP_NAME_PLACEHOLDER` → App name
- `APP_URL_PLACEHOLDER` → Website URL
- `ORDER_ID_PLACEHOLDER` → Order ID

## GitHub Actions

The `.github/workflows/build.yml` file contains the automated build process that:
1. Sets up the build environment
2. Configures the app with order data
3. Builds the Android APK
4. Uploads to Firebase Storage
5. Updates order status

## Security

This repository should be public to allow GitHub Actions to work properly.
