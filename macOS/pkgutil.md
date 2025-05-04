# pkgutil

`pkgutil` reads and manipulates MacOS installer flat packages (single installer files with .pkg file extensions).

List installed packages:
```
pkgutil --pkgs
```

Check package version:
```bash
pkgutil --pkg-info $PKGID
```

List package files:
```bash
pkgutil --files $PKGID
```

Remove package metadata (after deleting installed files):
```bash
pkgutil --forget $PKGID
```

Remove system package metadata (requires disabled SIP):
```bash
sudo pkgutil --volume /Library/Apple/System/ --forget $PKGID
```