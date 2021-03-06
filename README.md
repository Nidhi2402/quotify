# Quotlify

Quotlify is a quote browser and manager that allows one to search famous quotes and save them to a data store. The application is built using React, Redux for application state, and React Router for pages and navigation, and Firebase for a datastore.

Features:

* Display quote of the day (QOD)
* Search for quotes
* Save quotes as favorites
* Remove favorite quotes

## See Demo: https://qoutify-heroku-node.herokuapp.com/

## Overview

At a high level, Quotlify is a Single Page Application (SPA) built using notable libraries like React, React Router, and Redux. The application gets quote data from a third party API ([FavQs]). It allows one to add/remove a quote as a favorite to/from a database ([Firebase]). All API and database interaction is managed through domain services. The following diagram illustrates the general design of the application.

**Application Design**

![quotlify-app-design](https://user-images.githubusercontent.com/33935506/35609333-8c2348bc-0665-11e8-9eb4-8efc4e9a43dd.png)

## Primary Components

The root application component (App), is composed of 4 primary components:

* Header
  * A heading that displays application title
* Quote Of The Day (QOD) Page
  * The "landing page" or the first view that the application opens on. It displays a random quote of the day that it retrieves from a third party API ([FavQs])
* Quotes Page
  * A search page and is used to search for famous quotes by querying the [FavQs] API
* Favorite Quotes Page
  * Displays a list of all favorite quotes that were added via the application. The favorite quote data is managed via a [Firebase] database

The "page" components are configured to use [React Router] for display and navigation.

**Primary Component Design**

![primary-component-design](https://user-images.githubusercontent.com/33935506/35668601-c2d14352-073a-11e8-9588-963b8353ae61.png)

### Quote Of The Day Page

This is the first view that is displayed upon loading the application. It displays a random quote of the day. There is a button to favorite a quote. There is also a button to refresh and retrieve a new random quote of the day.

**Quote Of The Day Page Design**

![quotlify-qod-component](https://user-images.githubusercontent.com/33935506/35643325-a1e18150-06ce-11e8-8563-f6b9f81dffb2.png)

### Quotes Page

This view is responsible for providing quote search capability. The search functionality is provided through a SearchBar component. The results of a search are displayed as a list of cards containing, each containing a single quote and a 'favorite' button.

**Quotes Design**

![quotlify-quotes-component](https://user-images.githubusercontent.com/33935506/35643481-1a374cb6-06cf-11e8-937e-64db9b813558.png)

### Favorite Quotes Page

Displays a list of favorite quotes . Each quote is displayed in a _card_ with a 'remove quote' button.

**Favorite Quotes Design**

![quotlify-favquotes-component](https://user-images.githubusercontent.com/33935506/35643601-80c2dcca-06cf-11e8-8f09-8575f69fa7f8.png)

---

## Screenshots

![quotlify-screenshot-2](https://user-images.githubusercontent.com/33935506/35666236-e520ef2e-0731-11e8-9107-6503274ba2d5.png)

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

The following software is required to be installed on your system:

* Node 8.x
* Npm 3.x

Type the following commands in the terminal to verify your node and npm versions

```bash
node -v
npm -v
```

### Install

Follow the following steps to get development environment running.

* Clone _'quotify'_ repository from GitHub

  ```bash
  git clone https://github.com/Nidhi2402/quotify.git
  ```

   _OR USING SSH_

  ```bash
  git clone git@github.com:Nidhi2402/quotify.git
  ```

* Install node modules

   ```bash
   quotify
   npm install
   ```

### ENV Setup

**Before continuing, the following steps are required:**

1. Get API keys for FavQs

   * Have a look at [FavQs](https://favqs.com)
   * Get an API key [here](https://favqs.com/api/)

2. Setup Firebase

   * Visit the [Firebase] website to get started
   * See this [guide](https://firebase.google.com/docs/web/setup) to get started with setting up a web project to use Firebase

3. Setup environment variables

   * Add _'.env'_ file
     Create a file called _'.env'_ at the root of the application
   * Add environment variables to _'.env'_ file

     FAVQS_API_KEY=##########

     FIREBASE_API_KEY=##########

     FIREBASE_AUTH_DOMAIN=##########

     FIREBASE_DATABASE_URL=##########

     FIREBASE_PROJECT_ID=##########

     FIREBASE_STORAGE_BUCKET=##########

     FIREBASE_MESSAGING_SENDER_ID=##########

   For more information about _'.env'_, please visit [dotenv-webpack](https://www.npmjs.com/package/dotenv-webpack)

### Build

* Build application

  This command will also run ESLint as part of build process.

  ```bash
  npm run build
  ```

* Build application and start watching for changes

  This command will also run ESLint as part of build process.

  ```bash
  npm run build:watch
  ```

### Run ESlint

* Lint project using ESLint

  ```bash
  npm run lint
  ```

* Lint project using ESLint, and autofix

  ```bash
  npm run lint:fix
  ```

### Run

* Run start

  This will run the _'serve'_ npm task

  ```bash
  npm start
  ```

* Run webpack dev server

  ```bash
  npm run serve:dev
  ```

* Alternatively run live-server (simple development http server with live reload capability)

  ```bash
  npm run serve
  ```


#Nidhi
