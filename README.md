# Sharemefy
A simple social link sharing platform built with Svelte and Firebase. 

> This is a test project to learn Svelte and Firebase

## Features
### Firebase Related
* Storage bucket for storing images
* Firestore for storing user data
  * Strong rules for Firestore
* Authentication with Google
* Firebase JS SDK and Admin SDK

### Svelte Related
* Server Side Rendering
* Search Engine Optimization
* Data fetching and caching
* Cookie based authentication
* Routing
* Svelte Animations
* Svelte Actions
* Svelte Hooks
* Svelte Stores
* Form Validation

### UI Related
* Tailwind CSS
* DaisyUI

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm create svelte@latest

# create a new project in my-app
npm create svelte@latest my-app
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.

# Deployment

```bash
npm i -g firebase-tools

firebase login

firebase experiments:enable webframeworks

firebase init hosting

firebase deploy
```
