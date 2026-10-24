# Meta

覆盖 Meta 官网与账号、Meta AI、Facebook、Instagram、Messenger、Threads、WhatsApp、Oculus 以及共用图片/CDN 域名，并补入 Muse 相关域名。当前共 59 条域名规则。子域名由 HOST-SUFFIX 自动覆盖，例如 www.meta.com、auth.meta.com、agent.meta.ai。

## 圈 X 订阅

在已有 `[filter_remote]` 段加入，将 PROXY 换为已有代理策略：

```ini
https://raw.githubusercontent.com/buding2008/routing-rules/main/QuantumultX/Meta/Meta.list, tag=Meta, force-policy=PROXY, update-interval=86400, enabled=true
```

如同时使用 Muse 独立规则，将 Muse 放在 Meta 前面；需要统一出口时，让两者选择同一节点。已有 Facebook 等资源可能重叠，检查规则顺序和实际命中策略。

## 来源与范围

主要数据选自 [v2fly/domain-list-community 的 Meta 分类](https://github.com/v2fly/domain-list-community/blob/master/data/meta)及其引用分类，筛选主要产品、账号与 CDN 域名；未收录全部拼写变体或开发工具网站。Muse 补充域名来自官网前端脚本。

不使用整个共享 CDN 域名或整个 ASN 的匹配。域名覆盖不代表地区资格或账号权限。未完成登录后的全功能客户端验证。

第三方声明见 [THIRD_PARTY_LICENSES.md](THIRD_PARTY_LICENSES.md)。
