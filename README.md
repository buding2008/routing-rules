# routing-rules

个人维护的 Quantumult X（圈 X）域名分流规则，仅包含规则和使用说明。

| 规则 | 基础覆盖 |
| --- | --- |
| [Manus](QuantumultX/Manus/Manus.list) | manus.im、manus.ai 及子域名 |
| [Muse](QuantumultX/Muse/Muse.list) | muse.ai 及子域名，包含 auth.muse.ai |
| [Grok](QuantumultX/Grok/Grok.list) | grok.com、x.ai 及子域名 |
| [Meta](QuantumultX/Meta/Meta.list) | Meta 官网、账号、AI、Facebook、Instagram、Messenger、Threads、WhatsApp、Oculus 与 CDN |

## 圈 X 订阅

在配置已有的 `[filter_remote]` 段加入以下规则。请将 `PROXY` 替换为你现有的代理节点或策略组名称：

```ini
https://raw.githubusercontent.com/buding2008/routing-rules/main/QuantumultX/Manus/Manus.list, tag=Manus, force-policy=PROXY, update-interval=86400, enabled=true
https://raw.githubusercontent.com/buding2008/routing-rules/main/QuantumultX/Muse/Muse.list, tag=Muse, force-policy=PROXY, update-interval=86400, enabled=true
https://raw.githubusercontent.com/buding2008/routing-rules/main/QuantumultX/Grok/Grok.list, tag=Grok, force-policy=PROXY, update-interval=86400, enabled=true
https://raw.githubusercontent.com/buding2008/routing-rules/main/QuantumultX/Meta/Meta.list, tag=Meta, force-policy=PROXY, update-interval=86400, enabled=true
```

也可以在圈 X 的「分流 → 规则资源」中添加对应 URL，并指定使用的策略。将这些资源放在可能匹配同一域名的宽泛规则前面。`force-policy` 会覆盖规则行末尾的策略名称，因此不需要额外创建 Manus、Muse、Grok 策略组。

## 覆盖范围与验证

这是基础版，语法已检查，尚未完成客户端实际流量验证。导入后测试登录、对话、上传、下载和视频播放等所需功能。若有异常，检查圈 X 请求记录，提供未命中的域名及错误现象，以便补充准确规则；请隐去 Cookie、Token 和账号数据。

第三方认证、CDN 等依赖尚未全面验证；不因某个产品使用共享服务而将整个共享域名加入分流。在 X 内使用 Grok 还需要独立的 X/Twitter 分流规则。

## 来源

- Manus：[官网](https://manus.im/)、[API](https://open.manus.ai/)
- Muse：[用户指定官网](https://muse.ai/)
- Grok：[官网](https://grok.com/)、[xAI](https://x.ai/)
- 格式：[Quantumult X 官方示例](https://github.com/crossutility/Quantumult-X/blob/master/sample.conf)

本仓库独立维护。不包含服务器资料、节点凭据或二维码。

## 应用图标

配套图标和分流规则放在同一个仓库，独立维护。现有 Manus、Muse、Grok 三个图标，来源和使用方式见 [图标说明](icons/README.md)。

圈 X 长按节点或策略组 → 图标 →「+」，导入：

```text
https://raw.githubusercontent.com/buding2008/routing-rules/main/icons/filter-icon.json
```

## Meta 与 Muse

Meta 规则覆盖主要产品、账号及 CDN，详见 [Meta 说明](QuantumultX/Meta/README.md)。Muse 独立规则应放在 Meta 之前；需要统一出口时，两者选择相同代理节点。添加规则不等于解除地区或账号限制。
