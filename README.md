<div align="center">

# 🔴 o11 NF Tool

### Your Windows desktop media workspace

**A focused black-and-red interface. Clear controls. Live activity.**

![Windows](https://img.shields.io/badge/Windows-x64-111827?style=for-the-badge)
![Runtime](https://img.shields.io/badge/Python-Bundled-111827?style=for-the-badge)
![Quality](https://img.shields.io/badge/Maximum-1080p-e11d48?style=for-the-badge)

[**Download the latest release**](https://github.com/drmforall/o11-nf-tool/releases/latest) · [Report an issue](https://github.com/drmforall/o11-nf-tool/issues)

</div>

---

## Welcome

o11 NF Tool is a Windows x64 desktop application with Movies / Shows controls, track inspection, audio and subtitle preferences, an Activity panel, stage progress, and local playback. This repository distributes the **final executable and user documentation**.

The application bundles Python and its application packages. Missing media utilities may be downloaded on first launch. Maximum video resolution is **1920 × 1080**; track availability and online operations depend on the source, account, device configuration, and service response.

## Download and launch

1. Open [Latest release](https://github.com/drmforall/o11-nf-tool/releases/latest).
2. Download **o11.NF.exe** (GitHub normalizes spaces in release asset names) to a writable folder on your Windows x64 PC.
3. Close any older running copy and open the downloaded executable.
4. Wait for startup setup to finish. Internet access is required for missing media utilities.
5. Follow the Activity panel. If setup fails, correct the reported problem and select **Retry setup**.

A separate Python installation is unnecessary. Device credentials and account sessions are not included; configure your own required local setup before using online operations.

## System requirements

| Requirement | Details |
| :--- | :--- |
| Platform | Windows x64 |
| Python | Included in the executable |
| Network | Required for first-time dependency downloads and online operations |
| Storage | Space for application files, media utilities, temporary files, and output |
| Local setup | Your own required account and device configuration |

No minimum RAM or exact disk-space benchmark is declared for this build.

## Interface guide

| Control | Purpose |
| :--- | :--- |
| Movies / Shows | Selects mode; Shows adds season and episode inputs |
| Title | Accepts a title ID or supported URL |
| Output filename | Sets the filename, separately from the destination folder |
| Quality | Requests a resolution up to Full HD; `best` remains capped at 1080p |
| Video profile | Chooses a codec/profile preference where available |
| Audio languages | Accepts comma-separated codes such as `en,pt-BR` |
| Original language | Selects original audio when identified in the manifest |
| Subtitle languages | Sets subtitle preferences |
| Convert subtitles | Chooses `srt`, `ass`, or `none` |
| Inspect tracks | Opens the available track list |
| Activity | Displays setup, progress, and error messages |
| Stop | Cancels the active operation |
| Output folder | Opens the configured destination |
| Play local file | Opens an existing local media file |

Original language cannot be combined with All tracks. Selecting a resolution or codec does not guarantee availability.

## Everyday workflow

1. Wait for setup to report readiness.
2. Select Movies or Shows and enter the title information.
3. Choose quality, audio, and subtitle preferences.
4. Inspect the available tracks. Select one video and multiple audio/subtitle tracks where needed.
5. Start your authorized operation and watch Activity.
6. Open Output folder after successful completion and check the result.

After changing device or session identity, inspect tracks again. Saved selections are checked against the inspected catalog and may need refreshing.

## Understand progress

- **Ready:** the application is idle.
- **Animated bar:** an active stage does not expose a numerical percentage.
- **Numerical percentage:** progress for the currently reported transfer or muxing stage.
- **Complete:** the process exited successfully; verify the expected files.
- **Stopped or failed:** review Activity for the result.

Progress can restart between stages and does not always represent overall completion. Click the progress bar to focus the latest activity. After Stop, wait for the process to exit before starting again; partial files may remain.

## Application data and updates

A standalone executable deploys its application files to:

```text
%LOCALAPPDATA%\o11NFTool
```

Paste that path into File Explorer to inspect local application data. When launched beside an existing source workspace, the executable can use that workspace instead.

The destination folder is controlled by `OUTPUT_FOLDER` in the local application configuration. Changing Output filename does not change that destination.

To update, close the application, download the newer executable, and run it. The launcher preserves an existing `nftool_cfg.py`. Keep local settings and account/device data private. The repository and release do not include those files.

## Troubleshooting

| Problem | Suggested action |
| :--- | :--- |
| Startup setup fails | Read the first Activity error, check connectivity and disk space, then Retry setup |
| An old icon or name appears | Confirm the EXE and shortcut path; File Explorer may cache icons |
| A Python installer error appears | Confirm you launched this bundled executable rather than an older bootstrap package |
| Progress moves without a number | Read Activity; some stages have no numerical progress |
| Output folder is empty | Confirm successful completion and the configured destination |
| Service rejects a session | Review the exact error and your own local account/device setup; successful installation does not establish authorization |
| A local file does not play | Confirm it exists and try a compatible installed player |

Live service acceptance and end-to-end online operation have not been verified as part of this release publication.

## Verify your download

Release: **v1.0.0** · Published: **6 October 2026**

File: `o11 NF.exe` · Size: **66,846,564 bytes**

SHA-256:

```text
F306CDF321EF9D829C2B7751192B8050E4D159DD83259B11C356DF7AFB754E38
```

Check a downloaded copy in PowerShell:

```powershell
Get-FileHash -LiteralPath '.\o11.NF.exe' -Algorithm SHA256
```

The hash verifies that your file matches this release artifact; it is not a claim of publisher signing or security certification.

## Support

Use [GitHub Issues](https://github.com/drmforall/o11-nf-tool/issues) and include your Windows version, release version, steps to reproduce, and sanitized error text. Access to this private repository and its releases requires permission from the owner.

Remove passwords, cookies, account tokens, private keys, device blobs, and session identifiers before sharing logs or screenshots.

## Distribution terms

No project-wide redistribution license is declared. Bundled components and downloaded utilities may have separate terms. Use the application only for content and systems you are authorized to access. This guide does not provide protection-bypass or credential-extraction instructions.
