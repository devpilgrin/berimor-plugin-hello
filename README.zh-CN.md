<div align="center">

<img src="assets/logo.png" alt="Berimor" width="640">

[Русский](README.md) · [English](README.en.md) · [Deutsch](README.de.md) · [Français](README.fr.md) · [Español](README.es.md) · **[简体中文](README.zh-CN.md)** · [日本語](README.ja.md) · [한국어](README.ko.md)

</div>
# hello-tool — berimor 参考插件

遵循 [berimor-plugins](https://github.com/devpilgrin/berimor-plugins) 契约的最小插件：
一个使用 stdio 协议和 ACL 清单的进程。

## 契约

- 调用：`./hello-tool <tool>`，通过 stdin 传入 JSON 参数；
- 响应：stdout 输出 `{"content": ...}` 或 `{"error": ...}`；
- 工具：`hello.greet`（mutates: false）。

## 安装

```bash
berimor plugin install devpilgrin/berimor-plugin-hello \
  --signer-workflow "devpilgrin/berimor-plugin-hello/.github/workflows/release.yml" \
  --allowed-ref "v*.*.*" \
  --capability-ceiling "hello.greet"
```

安装前会验证 sigstore 签名；首次安装时仓库会被固定到信任列表（TOFU），
后续更新只接受相同签名者身份的版本。

## 许可证

Apache-2.0
