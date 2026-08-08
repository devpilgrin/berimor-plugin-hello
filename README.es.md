<div align="center">

<img src="assets/logo.png" alt="Berimor" width="640">

[Русский](README.md) · [English](README.en.md) · [Deutsch](README.de.md) · [Français](README.fr.md) · **[Español](README.es.md)** · [简体中文](README.zh-CN.md) · [日本語](README.ja.md) · [한국어](README.ko.md)

[![Socket](https://badge.socket.dev/npm/package/berimor)](https://socket.dev/npm/package/berimor)

</div>
# hello-tool — plugin de referencia de berimor

Un plugin mínimo según el contrato de [berimor-plugins](https://github.com/devpilgrin/berimor-plugins):
un proceso con protocolo stdio y manifiesto ACL.

## Contrato

- invocación: `./hello-tool <tool>` con argumentos JSON en stdin;
- respuesta: `{"content": ...}` o `{"error": ...}` en stdout;
- herramienta: `hello.greet` (mutates: false).

## Instalación

```bash
berimor plugin install devpilgrin/berimor-plugin-hello \
  --signer-workflow "devpilgrin/berimor-plugin-hello/.github/workflows/release.yml" \
  --allowed-ref "v*.*.*" \
  --capability-ceiling "hello.greet"
```

La firma sigstore se verifica antes de la instalación; en la primera
instalación el repositorio se fija en la lista de confianza (TOFU) y las
actualizaciones posteriores solo se aceptan con la misma identidad de firmante.

## Licencia

Apache-2.0
