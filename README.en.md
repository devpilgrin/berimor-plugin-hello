<div align="center">

<img src="assets/logo.png" alt="Berimor" width="640">

[Русский](README.md) · **[English](README.en.md)** · [Deutsch](README.de.md) · [Français](README.fr.md) · [Español](README.es.md) · [简体中文](README.zh-CN.md) · [日本語](README.ja.md) · [한국어](README.ko.md)

</div>
# hello-tool — reference berimor plugin

A minimal plugin implementing the [berimor-plugins](https://github.com/devpilgrin/berimor-plugins) contract:
a process with a stdio protocol and an ACL manifest.

## Contract

- invocation: `./hello-tool <tool>` with JSON arguments on stdin;
- response: `{"content": ...}` or `{"error": ...}` on stdout;
- tool: `hello.greet` (mutates: false).

## Installation

```bash
berimor plugin install devpilgrin/berimor-plugin-hello \
  --signer-workflow "devpilgrin/berimor-plugin-hello/.github/workflows/release.yml" \
  --allowed-ref "v*.*.*" \
  --capability-ceiling "hello.greet"
```

The sigstore signature is verified before installation; on first install the
repository is pinned in the trust list (TOFU), and further updates are only
accepted with the same signer identity.

## License

Apache-2.0
