# Serenity Skills

Codex skills for translating market information into testable investment research frameworks.

## Skills

- `serenity-alpha`: translates market news into alpha hypotheses using a `news -> demand -> financial statements -> small-cap elasticity -> validation path` framework.
- `bayesian-intrinsic-growth-valuation`: estimates a company's intrinsic 3-5 year growth rate with Bayesian hypothesis updates, then compares it with market-implied growth and FOMO.
- `gf-dma-health-index`: scores whether a stock's current valuation/trend health is supported by fundamental growth speed, DMA trend speed, divergence, escape ratio, and estimate revisions.
- `tam-adj-peg`: evaluates growth-stock valuation by adjusting traditional PEG with TAM runway and business quality.
- `buy-side-equity-research-memo`: generates source-backed buy-side equity research memos from a ticker, with investment view, SEC/IR-backed financial analysis, valuation scenarios, catalysts, risks, and Serenity framework cross-checks.

## 直接使用托管版

如果你觉得本地安装、配置 Codex skill 或维护环境不方便，也可以订阅 [@iamai_omni](https://x.com/iamai_omni/creator-subscriptions/subscribe)，然后访问 [app.k2ai.dev](https://app.k2ai.dev) 直接使用托管版。订阅版不需要你自己搭建，并且会附赠许多其他功能，适合想快速上手、持续使用 Serenity 体系的用户。也可以扫码直接打开订阅页：
 是一套面向投资研究的 Codex 技能集合，把市场信息转化为可验证的投研框架。

它包含 serenity-alpha、bayesian-intrinsic-growth-valuation、gf-dma-health-index、tam-adj-peg 和 buy-side-equity-research-memo 五项独立技能，分别覆盖新闻到 alpha 假设的转化、贝叶斯内在增长估值、估值与趋势健康度打分、TAM 调整 PEG 估值，以及完整买方研究备忘录生成。

主要功能：
- serenity-alpha：将市场新闻映射为需求变化，再延伸至财务报表和小盘股弹性，形成可验证的 alpha 假设；
- bayesian-intrinsic-growth-valuation：用贝叶斯方法更新公司 3-5 年内在增长率，并与市场隐含增长及 FOMO 进行对比；
- gf-dma-health-index：综合基本面增速、DMA 趋势、背离、逃逸比率与预期修正，对个股健康度进行评分；
- tam-adj-peg：结合 TAM 跑道与业务质量，调整传统 PEG 估值，区分成长速度与持续性；
- buy-side-equity-research-memo：从 ticker 生成带投资观点、财务分析、估值情景、催化剂与风险的买方研究备忘录。

支持直接复制 skills 文件夹到 Codex 目录，或通过托管服务 app.k2ai.dev 快速使用，适合需要系统化投研框架的投资者与研究者。
<img src="docs/assets/iamai-omni-subscribe-qr.png" alt="Subscribe to @iamai_omni QR code" width="220">

## Repository Layout

```text
skills/
├── serenity-alpha/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/original-framework.md
├── bayesian-intrinsic-growth-valuation/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/original-framework.md
├── gf-dma-health-index/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/original-framework.md
├── tam-adj-peg/
│   ├── SKILL.md
│   ├── agents/openai.yaml
│   └── references/original-framework.md
└── buy-side-equity-research-memo/
    ├── SKILL.md
    ├── agents/openai.yaml
    └── references/original-framework.md
```

Each subdirectory under `skills/` is an independent Codex skill. Codex discovers a skill from its `SKILL.md`; files under `references/` are supporting material loaded only when needed.

## Install

Copy all skills into your Codex skills folder:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R skills/* "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Or install only one skill:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R skills/serenity-alpha "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -R skills/bayesian-intrinsic-growth-valuation "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -R skills/gf-dma-health-index "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -R skills/tam-adj-peg "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -R skills/buy-side-equity-research-memo "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Then invoke `$serenity-alpha` for news-to-alpha analysis, `$bayesian-intrinsic-growth-valuation` for Bayesian intrinsic-growth valuation, `$gf-dma-health-index` for trend/valuation health scoring, `$tam-adj-peg` for TAM-adjusted PEG valuation, or `$buy-side-equity-research-memo` for a full buy-side stock memo. If a newly copied skill does not appear, restart Codex.

## What They Do

`serenity-alpha`:

- Separates narrative news from already-observable demand changes.
- Maps demand into revenue, margin, cash-flow, and balance-sheet impact.
- Searches for small, pure, potentially misclassified beneficiaries.
- Builds 1-4 quarter verification chains and falsification points.
- Frames position posture conditionally as research, not personalized investment advice.

`bayesian-intrinsic-growth-valuation`:

- Converts fundamentals, industry cycle, TAM, valuation, and new information into H0-H5 growth-hypothesis probabilities.
- Updates 3-5 year revenue CAGR assumptions with Bayesian reasoning instead of surface bullish/bearish labels.
- Separates intrinsic growth updates from FOMO, narrative heat, and valuation multiple expansion.
- Compares weighted intrinsic growth with market-implied growth.
- Classifies valuation as undervalued, fair, expensive but tradable, or bubble-like.

`gf-dma-health-index`:

- Combines revenue growth, profit growth, estimate revisions, and 20/50/100/200DMA structure.
- Scores fundamental-DMA match, price-DMA divergence, trend parallelism, and revision confirmation.
- Classifies the current state from healthy momentum to broken/escaping.

`tam-adj-peg`:

- Adjusts traditional PEG with TAM Runway Factor and Quality Factor.
- Separates growth speed from growth duration, TAM capture, pricing power, cyclicality, dilution, and execution risk.
- Classifies valuation from very cheap to very expensive and maps it to core, high-beta, turnaround, option-like, or cyclical position framing.

`buy-side-equity-research-memo`:

- Starts with rating bias, target-price range, upside/downside, key debate, and thesis breakpoint.
- Uses SEC filings, company IR, earnings calls, presentations, and other current sources to anchor key facts.
- Builds industry-chain, competitive-position, financial-statement, value-driver, SOTP/valuation, and Bull/Base/Bear scenario sections.
- Integrates Serenity Alpha, Bayesian Intrinsic Growth, TAM-Adj-PEG, and GF-DMA lenses only when they improve the investment decision.
- Lists catalysts, risks, variant perception, monitoring dashboard, and source list for follow-up research.

## License

MIT
