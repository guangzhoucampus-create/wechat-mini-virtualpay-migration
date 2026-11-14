# 微信小程序虚拟支付迁移 Skill

帮助 Codex 等支持 SKILL.md 的编程助手，将存量小程序数字商品的普通微信支付迁移至虚拟支付。

覆盖开通核验、商品映射、取消重付、pending超时、迟到到账、幂等发货、灰度发布及真机验收。适用于会员、数字内容和课程等场景；具体资格与政策以微信最新官方文档为准。

## 安装

将本仓库放入 Codex 的技能目录：

```sh
git clone https://github.com/guangzhoucampus-create/wechat-mini-virtualpay-migration.git ~/.codex/skills/wechat-mini-virtualpay-migration
```

如果目标目录已存在，请先比较内容，避免覆盖自定义版本。安装后可新开会话发现技能。

## 使用

```text
$wechat-mini-virtualpay-migration
请先只读检查当前小程序支付链路，制定普通支付迁移到虚拟支付的方案。
```

技能不会自动授予生产部署、数据库修改、密钥重置或实际付款权限。按项目授权执行。

## 文件

- SKILL.md：入口与关键约束
- references/implementation.md：实施、验收与发布
- references/lessons.md：通用故障排查

本仓库是工作流程指导，不包含支付SDK、生产凭据或可直接上线的服务端实现。新订单号唯一不等于不会发生两笔独立扣款，必须保留旧单查账和重复到账处理。

## 许可

MIT License。欢迎通过 Issue 或 Pull Request 改进。
