# Repo for sharp / libvips binaries

sharp downloads binaries from locations that are blocked by the proxy and that cannot be white-listed (since it can change).

fortunately, sharp allows to specify custom URLs for downloading prebuilt binaries from:
https://sharp.pixelplumbing.com/install#custom-prebuilt-binaries

the pre-built binaries are downloaded and commited to this github repo because github is white-listed.

## What to do when sharp releases a new version:

when sharp dependency is upgraded, usually 2 binaries have to be added.

## sharp

first, identify the version number in package.json of the project that depends on sharp:

```
...
"sharp": "^0.28.1"
...
```

go to:
https://github.com/lovell/sharp/releases/tag/{version} where version is the one in package.json prefixed by v "v0.28.1", ex:
https://github.com/lovell/sharp/releases/tag/v0.28.1

then download the Windows version, ex: sharp-v0.28.1-napi-v3-win32-x64.tar.gz
and add it to `$/sharp/{version}` (`$/sharp/v0.28.1` in this case)

## libvips

go to https://github.com/lovell/sharp/blob/main/package.json:

```
...
 "config": {
    "libvips": "8.10.6",
    "runtime": "napi",
    "target": 3
  },
...
```

go to:
https://github.com/lovell/sharp-libvips/releases/tag/{version} where version is the one in package.json prefixed by v "v8.10.6", ex:
https://github.com/lovell/sharp-libvips/releases/tag/v8.10.6

then download the Windows version, ex: `libvips-8.10.6-win32-x64.tar.br`
and add it to `$/libvips/{version}` (`$/libvips/v8.10.6` in this case)
