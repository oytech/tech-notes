# MacPorts

Available packages - https://ports.macports.org/

## How-to

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


https://guide.macports.org/#using

https://apple.stackexchange.com/questions/10149/how-to-remove-unused-macports-packages