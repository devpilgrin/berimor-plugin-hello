# hello-tool — эталонный плагин berimor

Минимальный плагин по контракту [berimor-plugins](https://github.com/devpilgrin/berimor-plugins):
процесс с stdio-протоколом и ACL-манифестом.

## Контракт

- вызов: `./hello-tool <tool>` с JSON-аргументами на stdin;
- ответ: `{"content": ...}` или `{"error": ...}` на stdout;
- инструмент: `hello.greet` (mutates: false).

## Установка

```bash
berimor plugin install devpilgrin/berimor-plugin-hello \
  --signer-workflow "devpilgrin/berimor-plugin-hello/.github/workflows/release.yml" \
  --allowed-ref "v*.*.*" \
  --capability-ceiling "hello.greet"
```

Подпись sigstore проверяется до установки; при первой установке репозиторий
пинится в trust-список (TOFU), дальнейшие обновления — только с той же
идентичностью подписанта.

## Лицензия

Apache-2.0
