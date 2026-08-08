<div align="center">

<img src="assets/logo.png" alt="Berimor" width="640">

[Русский](README.md) · [English](README.en.md) · [Deutsch](README.de.md) · [Français](README.fr.md) · [Español](README.es.md) · [简体中文](README.zh-CN.md) · [日本語](README.ja.md) · **[한국어](README.ko.md)**

[![Socket](https://badge.socket.dev/npm/package/berimor)](https://socket.dev/npm/package/berimor)

</div>
# hello-tool — berimor 레퍼런스 플러그인

[berimor-plugins](https://github.com/devpilgrin/berimor-plugins) 계약을 따르는 최소 플러그인:
stdio 프로토콜과 ACL 매니페스트를 사용하는 프로세스입니다.

## 계약

- 호출: `./hello-tool <tool>` (stdin으로 JSON 인자 전달);
- 응답: stdout으로 `{"content": ...}` 또는 `{"error": ...}`;
- 도구: `hello.greet` (mutates: false).

## 설치

```bash
berimor plugin install devpilgrin/berimor-plugin-hello \
  --signer-workflow "devpilgrin/berimor-plugin-hello/.github/workflows/release.yml" \
  --allowed-ref "v*.*.*" \
  --capability-ceiling "hello.greet"
```

설치 전에 sigstore 서명이 검증됩니다. 첫 설치 시 저장소가 신뢰 목록에
고정되며(TOFU), 이후 업데이트는 동일한 서명자 아이덴티티로만 허용됩니다.

## 라이선스

Apache-2.0
