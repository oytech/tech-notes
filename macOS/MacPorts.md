# MacPorts

Guide - https://guide.macports.org/#using

Available packages (ports) - https://ports.macports.org/

## How-to

Install port, e.g `python`:
```bash
sudo port install python312
```

List different versions, e.g `python3`:
```bash
port select --list python3
```

Select default version:
```bash
sudo port select --set python3 python312
```

Show all installed packages with dependencies:
```bash
port installed
```

Show only directly installed (without dependencies):
```bash
port installed requested
```

Update ports tree, upgrade macports itself and then upgrade packages to newest versions:
```bash
sudo port selfupdate
sudo port upgrade outdated
```

Show old (inactive) packages and unused dependencies (leaves):
```bash
port echo inactive
port echo leaves
```

Remove old (inactive) packages and unused dependencies (leaves), this may mark more ports as leaves:
```bash
sudo port uninstall inactive
sudo port uninstall leaves
```

https://apple.stackexchange.com/questions/10149/how-to-remove-unused-macports-packages

https://stackoverflow.com/questions/6612009/macports-port-select-commands
