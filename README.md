# Serenity Skills

Codex skills for translating market information into testable investment research frameworks.

- `serenity-alpha`: translates market news into alpha hypotheses using a "news -> demand -> financial statements -> small-cap elasticity -> validation path" framework.
- `bayesian-intrinsic-growth-valuation`: estimates a company's intrinsic 3-5 year growth rate with Bayesian hypothesis updates, then compares it with market-implied growth and FOMO.

## 直接使用托管版

如果你觉得本地安装、配置 Codex skill 或维护环境不方便，也可以订阅 [@iamai_omni](https://x.com/iamai_omni/creator-subscriptions/subscribe)，然后访问 [app.k2ai.dev](https://app.k2ai.dev) 直接使用托管版。订阅版不需要你自己搭建，并且会附赠许多其他功能，适合想快速上手、持续使用 Serenity 体系的用户。也可以扫码直接打开订阅页：

<img src="docs/assets/iamai-omni-subscribe-qr.png" alt="Subscribe to @iamai_omni QR code" width="220">

## Install

Copy or symlink the skill directories into your Codex skills folder:

```bash
mkdir -p "${CODEX_HOME:-$HOME/.codex}/skills"
cp -R serenity-alpha "${CODEX_HOME:-$HOME/.codex}/skills/"
cp -R skills/* "${CODEX_HOME:-$HOME/.codex}/skills/"
```

Then invoke `$serenity-alpha` for news-to-alpha analysis, or `$bayesian-intrinsic-growth-valuation` for Bayesian intrinsic-growth valuation.

## What It Does

- Separates narrative news from already-observable demand changes.
- Maps demand into revenue, margin, cash-flow, and balance-sheet impact.
- Searches for small, pure, potentially misclassified beneficiaries.
- Builds 1-4 quarter verification chains and falsification points.
- Frames position posture conditionally as research, not personalized investment advice.

## License

MIT
