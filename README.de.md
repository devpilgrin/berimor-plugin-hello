<div align="center">

<img src="assets/logo.png" alt="Berimor" width="640">

[Русский](README.md) · [English](README.en.md) · **[Deutsch](README.de.md)** · [Français](README.fr.md) · [Español](README.es.md) · [简体中文](README.zh-CN.md) · [日本語](README.ja.md) · [한국어](README.ko.md)

</div>
# hello-tool — Referenz-Plugin für berimor

Ein minimales Plugin nach dem Kontrakt von [berimor-plugins](https://github.com/devpilgrin/berimor-plugins):
ein Prozess mit stdio-Protokoll und ACL-Manifest.

## Kontrakt

- Aufruf: `./hello-tool <tool>` mit JSON-Argumenten auf stdin;
- Antwort: `{"content": ...}` oder `{"error": ...}` auf stdout;
- Werkzeug: `hello.greet` (mutates: false).

## Installation

```bash
berimor plugin install devpilgrin/berimor-plugin-hello \
  --signer-workflow "devpilgrin/berimor-plugin-hello/.github/workflows/release.yml" \
  --allowed-ref "v*.*.*" \
  --capability-ceiling "hello.greet"
```

Die sigstore-Signatur wird vor der Installation geprüft; bei der ersten
Installation wird das Repository in der Trust-Liste gepinnt (TOFU), weitere
Updates werden nur mit derselben Signer-Identität akzeptiert.

## Lizenz

Apache-2.0
