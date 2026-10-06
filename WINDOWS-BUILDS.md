# Windows builds — v1.0.1

[Download release assets](https://github.com/drmforall/o11-nf-tool/releases/tag/v1.0.1)

Three distribution formats are available for the current **Windows x64** application. They package the same application functionality and bundled Python runtime; different formats do not add support for older operating systems or other CPU architectures.

## Choose a download

| Format | Download | Best for |
| :--- | :--- | :--- |
| Standalone EXE | [o11-NF-Tool-1.0.1-windows-x64.exe](https://github.com/drmforall/o11-nf-tool/releases/download/v1.0.1/o11-NF-Tool-1.0.1-windows-x64.exe) | A single file with no install wizard |
| Folder bundle / portable ZIP | [o11-NF-Tool-1.0.1-windows-x64-portable.zip](https://github.com/drmforall/o11-nf-tool/releases/download/v1.0.1/o11-NF-Tool-1.0.1-windows-x64-portable.zip) | An unpacked runtime; keep the whole extracted folder together |
| Per-user installer | [o11-NF-Tool-1.0.1-windows-x64-setup.exe](https://github.com/drmforall/o11-nf-tool/releases/download/v1.0.1/o11-NF-Tool-1.0.1-windows-x64-setup.exe) | Start menu integration, optional desktop shortcut, and an uninstaller |
| SHA-256 checksums | [SHA256SUMS.txt](https://github.com/drmforall/o11-nf-tool/releases/download/v1.0.1/SHA256SUMS.txt) | Checking that downloads match the published artifacts |

No administrator access or separate Python installation is required for these application packages. Internet access is still required for missing media utilities and online operations. Device files and account sessions are not included in the release assets.

## Windows compatibility

| System | Status | Details |
| :--- | :--- | :--- |
| Windows 11 x64 | Local packaging checks passed | Tested on the available Windows 11 build 26300 host. Checks cover UI startup, runtime dependencies, package payload, and CLI help with a synthetic fixture; live service behavior is not certified. |
| Windows 10 x64 | Compatibility candidate; not tested | The Python runtime supports Windows 10, but current Playwright upstream requirements start at Windows 11. Automatic browser activation is not supported upstream on Windows 10; overall application compatibility remains unverified. |
| Windows 11 ARM64 | x64-emulation candidate; not tested | Windows 11 can emulate x64 applications. These assets are x64, not native ARM64. The application and media utilities have not been tested on an ARM PC. |
| Windows Server with Desktop Experience | Not tested | Current browser automation lists Windows Server 2019+ upstream. GUI, runtime, utilities, and service behavior still need host-specific verification. |
| Windows 10/11 32-bit systems | Not supported by this build | Runtime and utility downloads require x64. No x86 build is provided. |
| Windows 8.1, 8, 7, Vista, XP, Windows RT | Not supported by this build | The bundled Python 3.14 runtime requires Windows 10 or newer. Older Python alone would not resolve the application's utility and browser dependencies. |
| Windows Server Core / Nano Server | Not supported by this desktop distribution | The application requires a desktop GUI. |

Runtime requirements: [Python's Windows support](https://docs.python.org/3/using/windows.html). Browser requirements: [Playwright Python system requirements](https://playwright.dev/python/docs/intro). Emulation capability: [Microsoft's Windows on ARM documentation](https://learn.microsoft.com/en-us/windows/arm/apps-on-arm-x86-emulation).

There is no verified universal build for every Windows version. Native x86/ARM64 and legacy Windows releases need additional dependency work and testing before publication.

## Installation methods

### Standalone EXE

Download the standalone file to a writable folder and open it. Its runtime payload is unpacked temporarily, while application files/settings normally deploy to `%LOCALAPPDATA%\o11NFTool`. Missing media utilities are downloaded on first use.

### Folder bundle / portable ZIP

Extract the complete archive, open the `o11 NF` folder, and run `o11 NF.exe`. Keep its `_internal` folder beside the EXE; moving the EXE alone breaks the folder bundle. This format needs no installation wizard, but application data still normally uses `%LOCALAPPDATA%\o11NFTool`; it is not a fully self-contained data directory.

### Installer

Run the setup EXE. It defaults to `%LOCALAPPDATA%\Programs\o11 NF Tool`, adds a Start menu entry, and offers an optional desktop shortcut. The wizard supports uninstalling the installed runtime. The separate `%LOCALAPPDATA%\o11NFTool` application-data folder is preserved on uninstall, so device/session settings are not deleted by the uninstaller.

Close the app before updating. Download a newer installer or replace the standalone/folder distribution as appropriate. Existing application configuration is preserved by the launcher.

## Verification

Run `Get-FileHash -LiteralPath '<downloaded file>' -Algorithm SHA256` in PowerShell and compare the result with `SHA256SUMS.txt`.

Validation for this release:

- Standalone executable packaged self-test.
- Folder-build packaged self-test.
- Extracted portable ZIP packaged self-test.
- Silent installer installation into an isolated test directory, installed executable self-test, and uninstallation.
- Build payload inspection excludes device credentials, cookies, saved keys, and session caches.

The binaries are not signed or notarized by this release process. Packaging checks do not establish live service acceptance or compatibility on every target machine.
