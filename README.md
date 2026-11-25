<!--
  Published verbatim to shaked-nachum/vecton-ide by .github/workflows/release.yml.
  Everything in release/vecton-ide/ mirrors that repo's root; edits here ship with
  the next tagged release, never on their own.
-->

# Vecton

Run a team of AI coding agents without losing control.

## Quick install

Paste one line. Vecton downloads from GitHub and the installer opens.

**macOS** (Terminal):

```bash
curl -fL https://github.com/shaked-nachum/vecton-ide/releases/latest/download/Vecton-macos-arm64.dmg -o /tmp/Vecton.dmg && xattr -c /tmp/Vecton.dmg && open /tmp/Vecton.dmg
```

**Windows** (PowerShell):

```powershell
$setup="$env:TEMP\Vecton-setup.exe"; curl.exe -fL# https://github.com/shaked-nachum/vecton-ide/releases/latest/download/Vecton-windows-x64-setup.exe -o $setup; if($?){Start-Process $setup}
```

<details>
<summary><strong>Install latest pre-release (Alpha)</strong></summary>

> Pre-release builds contain experimental features and rapid changes that may be less stable.

**macOS** (Terminal):

```bash
TAG=$(curl -s https://api.github.com/repos/shaked-nachum/vecton-ide/releases | grep -m1 '"tag_name":' | sed -E 's/.*"([^"]+)".*/\1/') && curl -fL "https://github.com/shaked-nachum/vecton-ide/releases/download/$TAG/Vecton-macos-arm64.dmg" -o /tmp/Vecton.dmg && xattr -c /tmp/Vecton.dmg && open /tmp/Vecton.dmg
```

**Windows** (PowerShell):

```powershell
$tag=(irm https://api.github.com/repos/shaked-nachum/vecton-ide/releases)[0].tag_name; $setup="$env:TEMP\Vecton-setup.exe"; curl.exe -fL# "https://github.com/shaked-nachum/vecton-ide/releases/download/$tag/Vecton-windows-x64-setup.exe" -o $setup; if($?){Start-Process $setup}
```

</details>

Prefer clicking? Use the links below; the [First launch](#first-launch) steps
get you past the warning.

## Download

| Platform | |
| --- | --- |
| Windows 10/11 (x64) | [Download installer](https://github.com/shaked-nachum/vecton-ide/releases/latest/download/Vecton-windows-x64-setup.exe) |
| macOS (Apple Silicon) | [Download DMG](https://github.com/shaked-nachum/vecton-ide/releases/latest/download/Vecton-macos-arm64.dmg) |

Intel Macs are not supported yet. Every release also ships `checksums.txt` if
you want to verify the download.

## Before you install

You need [Git](https://git-scm.com/downloads) and
[Node.js](https://nodejs.org/) 18+. Vecton installs the coding agent itself on
first run.

## First launch

Skip this if you used the one-liner. These builds are not code-signed yet, so a
downloaded-by-hand installer gets one OS warning:

* **Windows** — SmartScreen shows "Windows protected your PC". Choose
  **More info → Run anyway**.
* **macOS** — Gatekeeper refuses to open the app. Drag Vecton to Applications,
  then **right-click it → Open → Open**. Only needed the first time.

## Feedback

Found a bug? Use **Report a bug** in the top bar of the app -- it sends us what
we need to reproduce it.
