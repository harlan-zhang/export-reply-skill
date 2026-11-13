# trb-export-reply · 外贸客户回复 Skill

一个通用的 Agent Skill（不是平台专属的专家包）。把海外客户的原话变成一封能直接复制发送的回复，并附简短版、会话要点、下一步动作。

仓库：<https://github.com/harlan-zhang/export-reply-skill>

## 从 GitHub 安装

支持 Git 源安装的客户端（Cherry Studio、Claude Code 等）直接用仓库地址：

```
https://github.com/harlan-zhang/export-reply-skill
```

如果客户端支持填 `owner/repo`，用：

```
harlan-zhang/export-reply-skill
```

不支持 Git 源时，用归档包链接：

```
https://github.com/harlan-zhang/export-reply-skill/archive/refs/heads/main.zip
```

```
https://github.com/harlan-zhang/export-reply-skill/archive/refs/heads/main.tar.gz
```

> 注意：`SKILL.md` 位于仓库根目录，`references/` 与 `templates/` 是同级目录。
> 安装器需要能按路径读取原始文件（raw.githubusercontent.com），不要指向静态站点或带 SPA 回退的地址——那些会把任意路径都返回首页，导致 `references/`、`templates/` 读不到。

## 这个 Skill 做什么

业务员贴进客户邮件、WhatsApp / Instagram 消息、询盘表单、经销商询价，输出的不是"建议话术"，而是四段成品：

| 段落 | 内容 | 语言 |
|---|---|---|
| 一、成品回复 | 纯文本，整段复制即可发送 | 跟随客户语言 |
| 二、简短版 | 2—4 句，WhatsApp / DM 用 | 跟随客户语言 |
| 三、会话要点 | 客户身份 / 真实诉求 / 已确认 / 信息缺口 / 风险提示 | 中文 |
| 四、下一步动作建议 | 动作 + 可直接发的追问原句 + 跟进时机 | 中文 |

覆盖 B2C 零售（终端骑手、个人改装玩家）与 B2B 批发（经销商、改装工作室、车队、项目采购）两类场景，话术逻辑分开，不混写。

默认适配 **TRB POWER** 电动越野摩托车 / 轻型电摩动力系统（电池包、APEX FOC 控制器、中置电机、充电器、成套动力）与 **TRBEXA** 电动卡丁车业务。换成其他品类只需替换 `references/` 与 `templates/` 里的内容，四段式骨架可复用。

## 目录结构

```
trb-export-reply/
├── SKILL.md                        # 技能本体：触发条件、四段式铁律、B2C/B2B 分型、红线
├── README.md
├── LICENSE
├── references/
│   ├── company-facts.md            # 公司与品牌事实底稿（成立口径、主体信息、可适配平台）
│   ├── product-matrix.md           # 产品参数矩阵（电池 10 个 SKU / 控制器 / 电机 / 充电器 / 卡丁车）
│   ├── compatibility-checklist.md  # 适配核对清单（四品类必核项 + 分场景策略）
│   ├── price-and-trade.md          # 报价前 5 项、MOQ、运费、认证、付款、保修、OEM
│   └── tone-and-redlines.md        # 语气基线 + 禁止写法对照表 + 高危场景处理
└── templates/
    ├── output-blocks.md            # 四段式输出模板与变体处理
    ├── b2c-scenarios.md            # 终端客户 13 个高频场景
    └── b2b-scenarios.md            # 客户分级 + 经销商等 13 个场景
```

## 安装

Skill 是一个文件夹，放进对应客户端的 skill 目录即可，无需构建、无依赖。

**WorkBuddy**

```
%USERPROFILE%\.workbuddy\skills\trb-export-reply\
```

macOS / Linux：`~/.workbuddy/skills/trb-export-reply/`

**Claude Code**

```
~/.claude/skills/trb-export-reply/
```

项目级则放到 `<项目>/.claude/skills/trb-export-reply/`。

**其他 Agent Skills 兼容客户端**

放进该客户端约定的 skills 目录（通常为 `.skills/` 或 `skills/`，每层文件夹一个 skill，内含 `SKILL.md`）。

**校验安装是否生效**：确认客户端能读到 `trb-export-reply/SKILL.md`，且 frontmatter 的 `name` 与文件夹名一致。重启客户端或开启新会话后生效。

## 使用

装好后直接贴客户原话，例如：

```
客户发来这个，帮我回：

Hi, I have a 2022 Surron Light Bee. Will your 72V battery fit?
What's the price shipped to Sydney?
```

技能会自动判断 B2C/B2B、查适配核对项、输出四段成品。

也可以显式点名：

- "用 trb-export-reply 帮我回这封经销商邮件"
- "这单按 B2B 处理，先收资格信息再报价"

## 维护

参数、价格规则、红线有变化时，优先改 `references/` 下的对应文件，`SKILL.md` 正文不用动。

- 产品参数唯一依据：`references/product-matrix.md`
- 有新 SKU 或口径变更，先改这一份

## 许可证

版权所有 © 2026 惠州天润邦能源科技有限公司（TRB POWER），保留所有权利。详见 [LICENSE](./LICENSE)。

包内涉及 Sur-Ron、Talaria、E-Ride Pro、79 Bike 的名称仅用于说明适配关系，TRB POWER 与上述公司无隶属、授权或背书关系。

## 免责声明

包内的产品参数、价格规则与回复指引会随产品迭代变化。正式报价、合同、认证与交期必须以最新销售资料和团队确认为准。
