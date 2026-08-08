<div align="center">

<img src="assets/logo.png" alt="Berimor" width="640">

[Русский](README.md) · [English](README.en.md) · [Deutsch](README.de.md) · [Français](README.fr.md) · [Español](README.es.md) · [简体中文](README.zh-CN.md) · **[日本語](README.ja.md)** · [한국어](README.ko.md)

[![Socket](https://badge.socket.dev/npm/package/berimor)](https://socket.dev/npm/package/berimor)

</div>
# hello-tool — berimor リファレンスプラグイン

[berimor-plugins](https://github.com/devpilgrin/berimor-plugins) コントラクトに準拠した最小プラグイン：
stdio プロトコルと ACL マニフェストを持つプロセスです。

## コントラクト

- 呼び出し: `./hello-tool <tool>`（JSON 引数を stdin へ）;
- 応答: stdout に `{"content": ...}` または `{"error": ...}`;
- ツール: `hello.greet`（mutates: false）。

## インストール

```bash
berimor plugin install devpilgrin/berimor-plugin-hello \
  --signer-workflow "devpilgrin/berimor-plugin-hello/.github/workflows/release.yml" \
  --allowed-ref "v*.*.*" \
  --capability-ceiling "hello.greet"
```

インストール前に sigstore 署名が検証されます。初回インストール時に
リポジトリがトラストリストにピン留めされ（TOFU）、以降の更新は
同一の署名者アイデンティティでのみ受け付けられます。

## ライセンス

Apache-2.0
