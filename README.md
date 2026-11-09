# hypercuts FFmpeg source offer

This repository hosts the **corresponding source code** for the FFmpeg binary
shipped inside hypercuts (the desktop video app), as required by the
GNU General Public License v3 (GPLv3).

## What hypercuts ships

- `ffmpeg.exe` — gyan.dev **essentials build, FFmpeg 6.1.1**, Windows x64,
  static (bundled via the `ffmpeg-static` npm package).
- It runs as a **separate process** (subprocess call). It is never linked
  into hypercuts' own code.

## Corresponding source

| Item | Value |
|---|---|
| FFmpeg release | **6.1.1** |
| Source tarball | https://ffmpeg.org/releases/ffmpeg-6.1.1.tar.xz |
| Tarball SHA-256 | `8684f4b00f94b85461884c3719382f1261f0d9eb3d59640a1f4ac0873616f968` |
| Tarball size | 10,458,600 bytes |
| FFmpeg source tag | `n6.1.1` — https://github.com/FFmpeg/FFmpeg/tree/n6.1.1 |
| Build provider | Gyan Doshi / gyan.dev — `6.1.1-essentials_build-www.gyan.dev` |
| Shipped binary SHA-256 | `04e1307997530f9cf2fe35cba2ca7e8875ca91da02f89d6c7243df819c94ad00` |
| Shipped binary size | 82,797,568 bytes (~78.96 MB) |
| License | GPLv3 (see `COPYING`) — `--enable-gpl --enable-version3`, `--enable-nonfree` NOT present |
| H.264 encoder | libx264 |

The source tarball is attached to the **Releases** of this repository
(`ffmpeg-6.1.1.tar.xz`, same SHA-256 as above). `BUILD-INFO.md` records the
exact build configuration and the SHA-256 of the shipped `ffmpeg.exe`.

## How to verify

```sh
sha256sum ffmpeg-6.1.1.tar.xz
# must print: 8684f4b00f94b85461884c3719382f1261f0d9eb3d59640a1f4ac0873616f968
```

Or run `./verify.sh` in this folder.

## Correction note (2026-11-07)

An earlier draft of this package targeted FFmpeg **9.0.2**. That was wrong:
9.0.2-full_build is the *system* FFmpeg installed on the development PC,
not the binary the app ships. The shipped binary is the ffmpeg-static
**6.1.1-essentials** build (SHA-256 above), so the source offer covers
6.1.1.

## Rebuilding

The gyan.dev 6.1.1 essentials build is built from the FFmpeg 6.1.1 source
tree with the configure flags listed in `BUILD-INFO.md`. See the FFmpeg
documentation (https://ffmpeg.org/documentation.html) for build instructions.

## License

FFmpeg is licensed under the **GNU General Public License v3** (see `COPYING`).
hypercuts' own code is separate and is NOT covered by this license — only the
FFmpeg binary and its libraries are GPLv3.
