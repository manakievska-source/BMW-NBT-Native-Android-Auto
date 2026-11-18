# Notices

The installer releases of BMW NBT Native Android Auto contain the following third-party components. Their license
texts are in [licenses/](licenses/).

## NBT-AAD (Android Auto protocol core)

The Android Auto session, encryption, audio mixer and parts of the iDrive controller / MOST client code are taken from
or based on **NBT-AAD** by nanaisu, <https://github.com/Sq00ky/Supra-iDrive6-Android-Auto>, licensed under the
PolyForm Noncommercial License 1.0.0 ([licenses/NBT-AAD-PolyForm-Noncommercial-1.0.0.md](licenses/NBT-AAD-PolyForm-Noncommercial-1.0.0.md)).
These parts are contained in `oneplus_native`, `nbt_knob`, `nbt_cluster`, `nbt_hwvideo`, `audioconn` and
`accessory_window`.

Required Notice: Copyright (c) 2026 nanaisu - NBT-AAD (https://github.com/Sq00ky/Supra-iDrive6-Android-Auto)

## NBT Android Auto package

The installer, the iDrive entry plugin and the service scripts started from an earlier NBT Android Auto package
published under the PolyForm Noncommercial License 1.0.0
([licenses/PolyForm-Noncommercial-1.0.0.md](licenses/PolyForm-Noncommercial-1.0.0.md)).

Required Notice: Copyright (c) 2026 the NBT Android Auto contributors

## FFmpeg (libavcodec, libavutil)

The video program uses FFmpeg 2.8.22 (H.264 decoder only), <https://ffmpeg.org>, licensed under the GNU Lesser General
Public License 2.1 or later ([licenses/FFmpeg-LGPL-2.1.txt](licenses/FFmpeg-LGPL-2.1.txt)). FFmpeg is shipped as
separate shared libraries that can be replaced by the user. Source code: <https://ffmpeg.org/releases/ffmpeg-2.8.22.tar.xz>;
the build configuration used is published with each release.

## h264bsd

Software H.264 decoder (fallback), <https://github.com/oneam/h264bsd>
([licenses/h264bsd-Apache-2.0.md](licenses/h264bsd-Apache-2.0.md)).

## Mbed TLS

Mbed TLS 3.6.7, Copyright The Mbed TLS Contributors, Apache License 2.0
([licenses/MbedTLS-Apache-2.0.txt](licenses/MbedTLS-Apache-2.0.txt)).

## speexdsp

speexdsp 1.2.1 resampler, BSD license ([licenses/speexdsp-BSD.txt](licenses/speexdsp-BSD.txt)).

## Trademarks

BMW, iDrive, Android and Android Auto are trademarks of their respective owners. This project is not affiliated with
or endorsed by them. No BMW software or data is included in the releases.
