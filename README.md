# Media Plan Generator

A free, single-page tool that turns a budget and a campaign goal into a first-draft paid media plan: channel split, estimated results and a weekly flowchart.

Built for the first 30 minutes of planning, when a client asks "what would 1.5 million rupees get us?" and you need a defensible starting point before the detailed plan. It covers markets most planning tools ignore: **Pakistan, the UAE and Saudi Arabia**, alongside the US and UK.

**Live demo:** `https://ghazanfar111212.github.io/media-plan-generator/`

![Media Plan Generator](docs/screenshot.png)

## What it does

- **Channel split by objective.** Pick awareness, traffic, leads, B2B leads or online sales, and it recommends a split across Meta, Google Search, YouTube, Display, TikTok, Snapchat and LinkedIn. Edit any share and the others rebalance to 100%.
- **Estimated results as ranges.** Impressions, reach, clicks and conversions per channel, with a low-to-high range rather than one falsely precise number.
- **Weekly flowchart.** Spend per channel per week in the style of an agency media flowchart, with three flighting patterns: always on, launch burst, and pulsing.
- **Local currency.** Budgets and costs in PKR, AED, SAR, USD or GBP, with editable exchange rates.
- **Editable benchmarks.** Every CPM, CTR, conversion rate and frequency assumption can be changed, so you can plug in your own account data.
- **Share and export.** Every plan lives in the URL, so "Copy share link" sends the exact plan to a colleague. Download as CSV for Excel or Google Sheets, or print.

## How the estimates work

For each channel:

```
impressions  = budget / CPM x 1000
clicks       = impressions x CTR
conversions  = clicks x conversion rate
reach        = impressions / frequency
```

Total reach is discounted by 20% when more than one channel runs, since the same people see ads on several platforms. Ranges apply plus or minus 15%, 25% or 40% to the central estimate.

The default benchmarks are **indicative starting points** for planning conversations. Real costs vary a lot by industry, season, audience size, creative quality and auction competition. Replace them with numbers from your own ad accounts whenever you have them. The tool says this in the interface too, because a plan built on someone else's averages is a conversation starter, not a forecast.

## Use it

Open `index.html` in any browser. There's nothing to install and no build step.

### Publish it free with GitHub Pages

1. Push this repo to GitHub.
2. Go to Settings > Pages.
3. Under "Build and deployment", choose **Deploy from a branch**, then select `main` and `/ (root)`.
4. After a minute your tool is live at `https://ghazanfar111212.github.io/media-plan-generator/`.

Update the GitHub link in the page footer to point at your repo.

## Customising

All the planning logic sits at the top of the `<script>` in `index.html`:

| Constant | What to change |
|---|---|
| `MARKETS` | Add a market, its currency, exchange rate and benchmarks |
| `CHANNELS` | Add or rename channels and their colours |
| `WEIGHTS` | How budget is split across channels for each objective |
| `DEFAULT_CHANNELS` | Which channels are ticked by default per objective |

## Roadmap

- Benchmarks by industry (real estate, FMCG, education, healthcare)
- Audience size check so plans don't exceed the available audience
- Export to a formatted Excel flowchart

## License

MIT
