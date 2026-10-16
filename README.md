# jellyfin-tizen-builds

Main repo: https://github.com/jeppevinkel/jellyfin-tizen-builds

Installer: https://github.com/Georift/install-jellyfin-tizen

## How it work

### Install from main repository

```bash
docker run --rm ghcr.io/georift/install-jellyfin-tizen 192.168.0.10 Jellyfin-TrueHD "https://github.com/jeppevinkel/jellyfin-tizen-builds/releases/tag/2024-05-13-0139"
```

### Install from custom repository

From a new branch (ex: release-15.0.0) or master:

```bash
./bump_version 15.0.0
git commit -am "Bump version to 15.0.0"
```
```bash
git push origin v15.0.0
```
