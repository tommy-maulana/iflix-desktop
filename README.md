# iflix Desktop App

This is a iflix desktop application to create a webview.

<p align="center">
    <a href="https://s.id/iflixMac">
      <img src="./img/download.png" alt="Download" width="150"/>
    </a>
</p>


<p align="center">
    <a href="https://s.id/iflixWindows">
      <img src="./img/download-win.png" alt="Download" width="150"/>
    </a>
</p>

![iflix Desktop App](screenshot.png)

## Usage

To run this repository you'll need [Node.js](https://nodejs.org/en/download/) (which comes with [npm](http://npmjs.com)) installed on your computer. From your command line:

```bash
# Install dependencies
$ npm install
# Run the app
$ npm start
```

### Electron packager

"[Electron Packager](https://github.com/electron-userland/electron-packager) is a command line tool and Node.js library that bundles Electron-based application source code with a renamed Electron executable and supporting files into folders ready for distribution."

#### Install Electron packager

```bash
# for use in npm scripts
$ npm install electron-packager --save-dev

# for use from cli
$ npm install electron-packager -g
```

#### Build MacOS, Windows and Linux package from the terminal

MacOS

```bash
$ electron-packager . --overwrite --platform=darwin --arch=x64 --icon=assets/icons/mac/icon.icns --prune=true --out=release-builds
```

Windows

```bash
$ electron-packager . --overwrite --asar=true --platform=win32 --arch=ia32 --icon=assets/icons/win/icon.ico --prune=true --out=release-builds --version-string.CompanyName=CE --version-string.FileDescription=CE --version-string.ProductName="iflix"
```

Linux (Ubuntu)

```bash
$ electron-packager . --overwrite --platform=linux --arch=x64 --icon=assets/icons/png/1024x1024.png --prune=true --out=release-builds
```

#### Shortcuts

To make it easier to create new builds, scripts are added in `package.json`.

Now you can run:

```bash
$ npm run package-mac
```

```bash
$ npm run package-win
```

```bash
$ npm run package-linux
```

## Mac installer

To create a DMG installer for our Electron app we can use the [electron-installer-dmg](https://github.com/mongodb-js/electron-installer-dmg) package.

To create a DMG installer you first need to package the app as we saw in the Application chapter above.

### Install

```bash
# For use in npm scripts
$ npm install electron-installer-dmg --save-dev

# For use from cli
$ npm install electron-installer-dmg -g
```

### Create the DMG

```bash
$ electron-installer-dmg ./release-builds/iFlix-darwin-x64/iFlix.app iflix --out=release-builds --overwrite --icon=assets/icons/mac/icon.icns
```

An `iflix.dmg` file is now created in the `release-builds` folder.

### Shortcuts

To make it easier to create new DMG installer, a script is added in `package.json`.

Now you can run:

```bash
$ npm run create-installer-mac
```

## Source

Based on:

- [Electron Packager tutorial](https://www.christianengvall.se/electron-packager-tutorial/)
- [Browser](https://github.com/hokein/electron-sample-apps/tree/master/webview/browser)
- [Electron Webview](https://github.com/cba85/electron-webview)

## License

[MIT](LICENSE.md)
