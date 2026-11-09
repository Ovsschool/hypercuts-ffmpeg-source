# BUILD-INFO — hypercuts shipped FFmpeg binary

## Binary

- File: `ffmpeg.exe` (Windows x64, static)
- Provider: gyan.dev essentials build, bundled via npm `ffmpeg-static`
- FFmpeg version: **6.1.1** (`6.1.1-essentials_build-www.gyan.dev`)
- Built with: gcc 12.2.0 (Rev10, Built by MSYS2 project)
- Shipped `ffmpeg.exe` SHA-256: `04e1307997530f9cf2fe35cba2ca7e8875ca91da02f89d6c7243df819c94ad00`
- Shipped `ffmpeg.exe` size: 82,797,568 bytes (~78.96 MB)
- Location in the app: `node_modules/ffmpeg-static/ffmpeg.exe`
  (unpacked to `resources/app.asar.unpacked` by electron-builder)

## Build flags (from `ffmpeg -version`)

configuration: --enable-gpl --enable-version3 --enable-static --pkg-config=pkgconf --disable-w32threads --disable-autodetect --enable-fontconfig --enable-iconv --enable-gnutls --enable-libxml2 --enable-gmp --enable-bzlib --enable-lzma --enable-zlib --enable-libsrt --enable-libssh --enable-libzmq --enable-avisynth --enable-sdl2 --enable-libwebp --enable-libx264 --enable-libx265 --enable-libxvid --enable-libaom --enable-libopenjpeg --enable-libvpx --enable-mediafoundation --enable-libass --enable-libfreetype --enable-libfribidi --enable-libharfbuzz --enable-libvidstab --enable-libvmaf --enable-libzimg --enable-amf --enable-cuda-llvm --enable-cuvid --enable-ffnvcodec --enable-nvdec --enable-nvenc --enable-dxva2 --enable-d3d11va --enable-libvpl --enable-libgme --enable-libopenmpt --enable-libopencore-amrwb --enable-libmp3lame --enable-libtheora --enable-libvo-amrwbenc --enable-libgsm --enable-libopencore-amrnb --enable-libopus --enable-libspeex --enable-libvorbis --enable-librubberband

- `--enable-gpl` — PRESENT
- `--enable-version3` — PRESENT
- `--enable-nonfree` — NOT present
- H.264 encoder: **libx264**

## Corresponding source

- Tarball: https://ffmpeg.org/releases/ffmpeg-6.1.1.tar.xz
- SHA-256: `8684f4b00f94b85461884c3719382f1261f0d9eb3d59640a1f4ac0873616f968`
- Size: 10,458,600 bytes
- FFmpeg tag: `n6.1.1`

## Process separation

`ffmpeg.exe` runs as a **separate process** (child_process.spawnSync /
child_process.execFile). It is never linked into hypercuts' own code.
