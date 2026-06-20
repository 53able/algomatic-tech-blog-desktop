# Algomatic Tech Blog Desktop

<https://tech.algomatic.jp/> を Pake / Tauri でデスクトップアプリ化するためのリポジトリです。

このリポジトリには、次のものを置いています。

- 再現用の Pake ビルドコマンド
- macOS / Windows / Linux 向けの GitHub Actions ビルド workflow
- ローカルで作成した macOS arm64 アプリの zip アーカイブ

## ローカル macOS ビルド

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

## ローカル成果物

```text
Algomatic Tech Blog-macOS-arm64.app.zip
```

ローカルでは次を確認しています。

```text
Mach-O 64-bit executable arm64
CFBundleName => Algomatic Tech Blog
CFBundleShortVersionString => 1.0.0
codesign verify: ok
```

## クロスプラットフォームビルド

Windows、Linux、macOS 向けの成果物は、次の GitHub Actions workflow から生成できます。

```text
.github/workflows/build-pake.yml
```

この workflow は Pake CLI と OS 別の GitHub-hosted runner を使います。

## 参照元

- 対象サイト: <https://tech.algomatic.jp/>
- Pake: <https://github.com/tw93/Pake>

## ライセンス注記

ライセンスと権利関係の注記は [LICENSE-NOTE.md](./LICENSE-NOTE.md) を参照してください。
