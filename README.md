# Whalebird
[![CircleCI](https://img.shields.io/circleci/project/github/h3poteto/whalebird-desktop.svg?style=flat-square)](https://circleci.com/gh/h3poteto/whalebird-desktop)
[![GitHub release](http://img.shields.io/github/release/h3poteto/whalebird-desktop.svg?style=flat-square)](https://github.com/h3poteto/whalebird-desktop/releases)
[![App Store](https://img.shields.io/itunes/v/1378283354.svg?style=flat-square)](https://itunes.apple.com/us/app/whalebird/id1378283354)


Whalebird is a mastodon client for desktop application.

![demo](screenshot.gif)

## Feature

- An interface like slack
- Notify to desktop
- Streaming
- Many keyboard shortcuts
- Manage multiple accounts

### Shortcuts

<table>
<thead>
<tr><th></th><th>Mac</th><th>Linux, Windows</th></tr>
</thead>
<tbody>
<tr><td> Toot, Reply                    </td><td>             <kbd>Cmd + Enter</kbd>         </td><td> <kbd>Ctrl + Enter</kbd>      </td></tr>
<tr><td> Change accounts                </td><td>             <kbd>Cmd + 1, 2, 3...</kbd>    </td><td> <kbd>Ctrl + 1, 2, 3...</kbd> </td></tr>
<tr><td> Jump to another timeline       </td><td>             <kbd>Cmd + k</kbd>             </td><td> <kbd>Ctrl + k</kbd>          </td></tr>
<tr><td> Open new toot window           </td><td>             <kbd>Cmd + n</kbd>             </td><td> <kbd>Ctrl + n</kbd>          </td></tr>
</tbody>
</table>

## Install
### Mac
[![App Store](app-store.svg)](https://itunes.apple.com/us/app/whalebird/id1378283354)

Or you can download `.dmg` from [release page](https://github.com/h3poteto/whalebird-desktop/releases).

So on, you can install from Homebrew:

```
$ brew update
$ brew install whalebird
```

:sparkles: Thanks to [@singingwolfboy](https://github.com/singingwolfboy) for adding it to [homebrew-cask](https://github.com/Homebrew/homebrew-cask/blob/cf568882b6e012956ca404a16be2db36ca873002/Casks/whalebird.rb).


### Linux

You can download `.deb` or `.rpm` from [release page](https://github.com/h3poteto/whalebird-desktop/releases).
If you do not want to use package manager, please download `.tar.bz2` file and docompress it.

Or please install the app from [snapcraft.io](https://snapcraft.io/whalebird).

```
$ sudo snap install whalebird
```

### Windows

You can download `.exe` from [release page](https://github.com/h3poteto/whalebird-desktop/releases).

## Development

``` bash
# clone this repository
$ git clone https://github.com/h3poteto/whalebird-desktop.git
$ cd whalebird-desktop

# install dependencies
$ npm install

# serve with hot reload at localhost:9080
$ npm run dev
```

## Release
### Binary
When you build release packages, please use `electron-builder`.

```bash
# for linux
$ npm run build:linux

# for mac
# This command automatically loads the Developer ID Application certificate from your keychain.
$ npm run build:mac
```

### AppStore

Please prepare certificates on your Apple developer console. The following keys are required:

- Mac App Distribution: `3rd Party Mac Developer Application: NAME (TEAM_ID)`
- Mac Installer Distribution: `3rd Party Mac Developer Installer: NAME (TEAM_ID)`

and register your KeyChain.

Then, create a Mac App ID like `org.whalebird.desktop`.

```bash
$ npm run build:mas

# This command automatically loads the certificates from you keychain.
$ ./appStore.sh
```

After that, the `.pkg` file is created under `./packages`.

Please upload the `.pkg` to App Store using Application Loader in Xcode.

### Snapcraft

First, please prepare snapcraft command.

```bash
$ brew install snapcraft
```

And prepare docker environment which is used in snapcraft building.

Build app for linux.

```bash
$ npm run build:linux
```

And upload.

```bash
$ snapcraft push build/whalebird_1.0.0_amd64.snap --release stable
```

# License
The software is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).
