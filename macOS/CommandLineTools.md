# CommandLineTools

Set of software development tools (e.g `clang`, `git`, `python3`, `swift`) and SDKs.

## How-to

Install:
```bash
xcode-select --install
```

Check active installation path:
```bash
xcode-select --print-path
```

Show SDKs:
```bash
ls -la /Library/Developer/CommandLineTools/SDKs
```

Reinstall:
```bash
sudo rm -rf /Library/Developer/CommandLineTools
xcode-select --install
```

Check version after installation:
```bash
pkgutil --pkg-info com.apple.pkg.CLTools_Executables
```
or
```bash
softwareupdate --history | grep "Tools"
```

Find installed packages:
```bash
pkgutil --pkgs | grep -i tools
```

Find installed executables:
```bash
pkgutil --files com.apple.pkg.CLTools_Executables | grep /usr/bin
```

https://apple.stackexchange.com/questions/93573/how-to-reinstall-xcode-command-line-tools

https://apple.stackexchange.com/questions/180957/determine-xcode-command-line-tools-version

https://stackoverflow.com/questions/65397218/is-xcodes-sdks-macosx-sdk-symlink-a-documented-feature

https://stackoverflow.com/questions/33419301/is-it-okay-to-delete-the-macos-xcode-coresimulator-devices-folder

https://apple.stackexchange.com/questions/328034/removing-uninstalled-command-line-tools-from-appstore-updates

## Problem: xcode-select installs 2 versions at the same time

Getting errors running `swift` code:
```
error: redefinition of module 'SwiftBridging'

error: failed to build module 'Foundation'; this SDK is not supported by the compiler
```

`softwareupdate` shows two versions installed at the same time:
```bash
softwareupdate --history | grep "Tools"
```

```
Command Line Tools for Xcode       15.3       03.05.2025, 21:31:34
Command Line Tools for Xcode       16.2       03.05.2025, 21:31:34
```
#### Solution

First remove it all:
```bash
sudo rm -rf /Library/Developer/CommandLineTools/
```

Install one version with `softwareupdate` trick:
```bash
touch /tmp/.com.apple.dt.CommandLineTools.installondemand.in-progress
# copy label from softwareupdate --list
softwareupdate --install "Command Line Tools for Xcode-16.2"
rm /tmp/.com.apple.dt.CommandLineTools.installondemand.in-progress
```

https://github.com/orgs/Homebrew/discussions/5723

https://apple.stackexchange.com/questions/107307/how-can-i-install-the-command-line-tools-completely-from-the-command-line