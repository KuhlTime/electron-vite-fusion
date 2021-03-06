# NPM Actions Overview

This file provides additonal information to every available NPM action.

### Important:

- **`dev`**: Starts a development server that can be visited inside the local browser. Supports Hot Module Replacement *HMR*.
- **`electron:dev`**: Starts the electron application running in development mode. This runs the `vite` command in the background, so *HMR* is enabled.
- **`lint`**: Points out any errors or warnings with the code.
- **`test`**: Runs testing scripts to validate that the app is working properly.
- **`dist`**: Builds the complete electron application for production.
- **`dist:unsigned`**: Builds the application without automatically applying a certificate. [Code Signing - electron-builder Documentation](https://www.electron.build/code-signing)

### Operational:

- **`build`**: Compiles the frontend code and outputs it to the *dist* directory.
- **`build:electron`**: This sets some additional properties to optimize the build for the electron container.
- **`electron`**: Intermediate command that gets called by the `electron:dev` command.
- **`serve`**: Servers the content of the previously compiled *dist* directory. (When developing always use `dev` instead)
- **`electron:pack`**: Build Electron in an unpacked format, this is usefull for investigating and testing the output of *electron-builder*.
- **`electron:dist`**: This packages the electron application in a distributable format such as a `.dmg`, `.exe` or `.deb`. The configuration of which formats to generate can be checked out inside the `electron-builder.json` file. This is an intermediate call that is performed by the `dist` command.
- **`clean`**: Restores the default state without any installed packages.
- **`postinstall`**: Installs additional electron dependencies after `npm install` has finished. This ensures that the native dependencies always matched the electron version.

What is *HMR*? - TL;DR *HMR* boils down to no reloads of the page when the source code changes.
