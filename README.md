# Book2Invest

把银行螺丝钉的五本基金投资书整理成一个可安装的 Codex Skill，用同一套流程处理基金选择、估值、定投、组合配置与退休规划。

## 覆盖范围

| 模块 | 解决的问题 |
|---|---|
| 指数基金 | 品种分类、指数估值、盈利收益率法、博格公式、定投与家庭资产配置 |
| 定投与财务自由 | 4% 法则、定期不定额、估值定投、止盈、养老/教育/加薪计划 |
| 红利指数基金 | 红利指数分类、股息率、分红处理、持股收息与风格轮动 |
| 主动基金 | 基金经理风格、基金分析、基金池、组合构建与再平衡 |
| 个人养老金 | 税优测算、开户与领取、五类品种、养老 FOF 与指数基金策略 |

`book2invest` 是唯一入口。它会先识别问题涉及哪一本书，再按需读取对应总览和专题资料，因此安装后不需要分别加载五个 Skill。

## 安装

将仓库克隆到 Codex 的用户级 Skill 目录：

```bash
git clone https://github.com/KeepLjx/book2invest.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/book2invest"
```

确认目录结构如下，然后重新打开 Codex：

```text
~/.codex/skills/book2invest/
├── SKILL.md
├── agents/openai.yaml
└── references/
    ├── index-fund-investment/
    ├── dca-financial-freedom/
    ├── dividend-fund-investment/
    ├── active-fund-investment/
    └── personal-pension-investment/
```

## 使用

显式调用：

```text
Use $book2invest to help me design a long-term fund investment plan.
```

也可以直接用自然语言提问，例如：

- “我有 30 万闲钱，准备 10 年后使用，应该怎样配置？”
- “现在该不该继续定投沪深 300？”
- “这只主动基金值不值得留？”
- “个人养老金账户适合买什么？”
- “红利基金的分红和止盈应该怎么处理？”

## 设计原则

- 一个入口，五个知识模块，按问题渐进加载。
- 先确定目标、期限和账户，再选择品种与执行方式。
- 原则与历史数据分开；实时估值、利率、费率、政策与产品名单必须重新核验。
- 输出结论、假设、执行规则、风险和数据日期，避免“无脑买”和短期预测。
- 投资教育优先，不虚构实时数据，不承诺收益，不替代持牌投资顾问。

## 目录来源

本体系整理自以下五本书的方法论，书名和原作者权益归各自权利人所有：

1. 《指数基金投资指南》
2. 《定投十年财务自由》
3. 《红利指数基金投资指南》
4. 《主动基金投资指南》
5. 《个人养老金投资指南》

本仓库是学习型知识整理和软件封装，不包含原书全文。引用书籍数据时会保留其历史时点，并提示用最新数据校准。公开分发或商业使用前，请自行确认内容授权与所在地合规要求。

## 验证

使用 Codex `skill-creator` 自带的校验器：

```bash
python3 ~/.codex/skills/.system/skill-creator/scripts/quick_validate.py .
```
