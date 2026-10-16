# jellyfin-tizen-builds

Main repo: https://github.com/jeppevinkel/jellyfin-tizen-builds

Installer: https://github.com/Georift/install-jellyfin-tizen

## How it work

### Install from main repository
```bash
docker run --rm ghcr.io/georift/install-jellyfin-tizen 192.168.0.10 Jellyfin-TrueHD "https://github.com/jeppevinkel/jellyfin-tizen-builds/releases/tag/2024-05-13-0139"
```

### Install from custom repository
From jellyfin-web fork:
1. Create new branch "custom-tag"

From a fork of main repository:
1. Actions → Enable workflow
2. Settings → Actions → General → Workflow permissions → Read and write
3. Remove get-latest-versions.yml
4. Update repository and tag values from matrix.json (see this [matrix.json](https://github.com/andreadegiovine/jellyfin-tizen-builds/blob/master/matrix.json))
5. Run build-new-release.yml workflow

From your pc:
```bash
docker run --rm -it --entrypoint bash ghcr.io/georift/install-jellyfin-tizen
# from container:
sdb connect 192.168.*.*
TV_NAME=$(sdb devices | grep -E 'device\s+\w+[-]?\w+' -o | sed 's/device//' - | xargs)
wget https://github.com/andreadegiovine/jellyfin-tizen-builds/releases/download/2026-10-15-1934/Jellyfin-TrailerFix.wgt
tizen install -n Jellyfin-TrailerFix.wgt -t "$TV_NAME"
```
