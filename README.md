# 微信小程序虚拟支付迁移 Skill

帮助 Codex 等支持 SKILL.md 的编程助手，将存量小程序数字商品的普通微信支付迁移至虚拟支付。

覆盖开通核验、商品映射、取消重付、pending超时、迟到到账、幂等发货、灰度发布及真机验收。适用于会员、数字内容和课程等场景；具体资格与政策以微信最新官方文档为准。

## 安装方法（Codex）

在终端执行：

```sh
git clone https://github.com/guangzhoucampus-create/wechat-mini-virtualpay-migration.git ~/.codex/skills/wechat-mini-virtualpay-migration
```

以上命令适用于 macOS、Linux 等使用该技能目录的环境。若设置了自定义 `CODEX_HOME`，请安装到该目录下的 `skills/wechat-mini-virtualpay-migration`。

如果目标目录已存在，请先比较内容，避免覆盖自定义版本。

## 使用方法

安装后新开一个 Codex 会话，打开你的小程序项目，输入：

```text
$wechat-mini-virtualpay-migration

请先只读检查当前项目的支付链路，制定迁移到虚拟支付的方案。
先不要修改线上服务。
```

确认方案后，再让 Codex 按计划实施、测试和部署。例如：

```text
按照已确认的方案实施，先完成本地修改与隔离测试。
不要影响其他项目，部署前汇报改动和验收结果。
```

## 使用前需要准备

- 小程序源码及现有支付、订单、会员或课程发放逻辑。
- 微信小程序后台权限；涉及服务端联调时，还需要对应服务器环境。
- 明确需要迁移的商品及客户端范围。

不要把 AppSecret、AppKey、服务器密码或支付凭据提交到公开仓库。

## 注意事项

这是指导 AI 开发的技能，不是一键开通支付工具，也不包含可直接上线的支付服务。支付资格、商品范围与政策以微信最新官方要求为准。

技能不会自动授予生产部署、数据库修改、密钥重置或实际付款权限，具体操作按项目授权执行。代码和自动测试通过，也不能代替真机收银台、真实到账及权益发放验收。

## 文件

- SKILL.md：入口与关键约束
- references/implementation.md：实施、验收与发布
- references/lessons.md：通用故障排查

本仓库是工作流程指导，不包含支付SDK、生产凭据或可直接上线的服务端实现。新订单号唯一不等于不会发生两笔独立扣款，必须保留旧单查账和重复到账处理。

## 许可

MIT License。欢迎通过 Issue 或 Pull Request 改进。
