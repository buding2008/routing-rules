# 应用图标

为圈 X 的策略组提供 Manus、Muse、Grok 官方网站图标。图标与规则独立维护，规则不会自动绑定图标。

## 导入圈 X

长按节点或策略组 → 图标 → 右上角「+」→ 输入：

```text
https://raw.githubusercontent.com/buding2008/routing-rules/main/icons/filter-icon.json
```

导入后选择对应图标。也可在策略组配置使用 `img-url` 指向单张 PNG 的 raw 链接。

## 图标

| 名称 | 预览 | 尺寸 |
| --- | --- | --- |
| Manus | ![Manus](apps/Manus.png) | 512×512 |
| Muse | ![Muse](apps/Muse.png) | 128×128 |
| Grok | ![Grok](apps/Grok.png) | 512×512 |

## 维护

图片放在 `apps/应用名.png`；在 `filter-icon.json` 增加相同名称和图片直链；在 `sources.json` 记录官方来源、获取日期、处理方式和文件摘要。使用标准 JSON，最后一个条目不加逗号。已存在的图片路径保持稳定。

图片来自各应用官网，Muse 仅从 ICO 转换为 PNG；未重绘品牌标志。品牌图形权益属于各自权利人，此处不声明它们采用开源许可。

图标索引结构参考 [fanmingming/Rules](https://github.com/fanmingming/Rules) 和 [erdongchanyo/icon](https://github.com/erdongchanyo/icon)。尚未在用户的圈 X 客户端实际验证显示效果。
