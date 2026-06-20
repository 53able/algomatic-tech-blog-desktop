# Algomatic Tech Blog Desktop

Pake/Tauri wrapper for <https://tech.algomatic.jp/>.

This repository contains:

- a reproducible Pake build command
- a GitHub Actions workflow for macOS / Windows / Linux builds
- the locally built macOS arm64 app archive

## Local macOS build

```bash
PAKE_CREATE_APP=1 npx pake-cli@3.11.10 https://tech.algomatic.jp/ \
  --name "Algomatic Tech Blog" \
  --title "Algomatic Tech Blog" \
  --width 1440 \
  --height 900 \
  --min-width 900 \
  --min-height 600 \
  --enable-find \
  --app-version 1.0.0
```

## Local artifact

```text
Algomatic Tech Blog-macOS-arm64.app.zip
```

Verified locally:

```text
Mach-O 64-bit executable arm64
CFBundleName => Algomatic Tech Blog
CFBundleShortVersionString => 1.0.0
codesign verify: ok
```

## Cross-platform builds

For Windows, Linux, and macOS release artifacts, run the GitHub Actions workflow:

```text
.github/workflows/build-pake.yml
```

The workflow uses Pake CLI and OS-specific GitHub-hosted runners.

## Source

- Website: <https://tech.algomatic.jp/>
- Pake: <https://github.com/tw93/Pake>

## License note

This repository contains a Pake-generated desktop wrapper for <https://tech.algomatic.jp/>.

Pake itself is licensed under GPL-3.0 with the Pake Output Exception:

- <https://github.com/tw93/Pake/blob/main/LICENSE>
- <https://github.com/tw93/Pake/blob/main/LICENSE-EXCEPTION>

The generated app artifact is distributed as a Pake Output. This repository does not redistribute a modified version of Pake itself.

Website content, logos, trademarks, icons, and brand assets remain owned by their respective owners. This repository is published as a generated app artifact and build recipe, not as a grant of rights to reuse the underlying website content or brand assets separately.
