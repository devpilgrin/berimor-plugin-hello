<div align="center">

<img src="assets/logo.png" alt="Berimor" width="640">

[Русский](README.md) · [English](README.en.md) · [Deutsch](README.de.md) · **[Français](README.fr.md)** · [Español](README.es.md) · [简体中文](README.zh-CN.md) · [日本語](README.ja.md) · [한국어](README.ko.md)

</div>
# hello-tool — plugin de référence pour berimor

Un plugin minimal selon le contrat [berimor-plugins](https://github.com/devpilgrin/berimor-plugins) :
un processus avec un protocole stdio et un manifeste ACL.

## Contrat

- invocation : `./hello-tool <tool>` avec des arguments JSON sur stdin ;
- réponse : `{"content": ...}` ou `{"error": ...}` sur stdout ;
- outil : `hello.greet` (mutates: false).

## Installation

```bash
berimor plugin install devpilgrin/berimor-plugin-hello \
  --signer-workflow "devpilgrin/berimor-plugin-hello/.github/workflows/release.yml" \
  --allowed-ref "v*.*.*" \
  --capability-ceiling "hello.greet"
```

La signature sigstore est vérifiée avant l'installation ; lors de la première
installation, le dépôt est épinglé dans la liste de confiance (TOFU) et les
mises à jour ultérieures ne sont acceptées qu'avec la même identité de signataire.

## Licence

Apache-2.0
