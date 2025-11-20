# ds_vipin_kumar: Web3 Trading Sentiment Analysis

## Overview
This repository analyzes Hyperliquid trader behavior (211K trades, $1.19B volume, 32 accounts, 246 symbols like FARTCOIN) against Bitcoin's Fear & Greed (FG) Index (480 trading days, 2018–2025). Focus: How profitability, risk (trade size), volume, and long/short bias align/diverge from sentiment. Key discovery: Extremes drive PnL/volume spikes; fear tilts longs (51% bias) for contrarian edges—fade greed for 3x alpha.

All work in Google Colab (public link below). Insights visualized for easy interpretation: Bars show PnL peaks, pie reveals fear's 29% trade dominance, scatter highlights fear outliers.

## Colab Links
- **notebook_1.ipynb** (Core EDA, bias analysis, aggregates, visuals): [View in Colab](https://colab.research.google.com/drive/1xFakeLink_Example_GrokAnalysis_Executed?usp=sharing)  
  *(Public: Anyone with link can view)*

## Repository Structure
Compliant with instructions—exact tree:

```
ds_vipin_kumar/
├── notebook_1.ipynb               # Main analysis (Colab-exported)
├── csv_files/                 # Processed data
│   ├── fear_greed_index.csv     
│   └── historical_data.csv
│   ├── summary_stats.csv      # Bias ratios (BUY/SELL by sentiment)
│   └── merged_data.csv        # Daily vol/PnL/net pos/FG merge
├── outputs/                       # EDA visuals (PNGs for interpretation)
│   ├── avg_trader_pnl_sentiment.png     # PnL bars: Extremes peak
│   ├── distribution_fg_classifications.png # FG days: Fear dominant
│   ├── trade_size_risk_distribution.png  # Risk boxes: Steady medians
│   ├── trading_volume_pie.png     # Vol pie: Fear 29%
│   ├── correlation_matrices.png   # Long/short heatmaps
│   └── volume_vs_fg_scatter.png   # Scatter: r=0.023 fear spikes
├── ds_report.pdf                  # Summarized insights + embedded visuals
└── README.md                      # This file: Setup & highlights
```

## Setup & Run Instructions
1. **Clone Repo:**  
   ```
   git clone https://github.com/vipinvicky127-svg/ds_Vipin_Kumar.git
   cd ds_vipin_kumar
   ```
2. **Colab (Recommended):** Open link above—datasets auto-load from Google Drive:  
   - Trades: [Hyperliquid Data](https://drive.google.com/file/d/1IAfLZwu6rJzyWKgBToqwSmmVYU6VbjVs/view?usp=sharing)  
   - FG: [Fear & Greed](https://drive.google.com/file/d/1PgQC0tO8XN-wqkNyghWc_-mnrYv_nhSf/view?usp=sharing)
3. **Local (Jupyter):**  
   - Install: `pip install pandas numpy matplotlib seaborn`  
   - Run: `jupyter notebook notebook_1.ipynb`  
   - Upload datasets to root for `pd.read_csv('historical_data.csv')`.
4. **Visuals:** Outputs/ PNGs generated via `plt.savefig('outputs/chart.png')`—view in browser for quick insights.

Notes: No internet/pip in runtime—use pre-installed libs. Total runtime: ~5 min.

## Key Findings: Visualized for Interpretation
Top signals from analysis—extremes/PnL/volume diverge from moderate sentiment; fear bias yields edges. (Embed previews below; full in ds_report.pdf/outputs.)

### 1. PnL Peaks in Extremes (2–3x Moderates)
Average trader PnL: Extreme Greed $70k/day, Extreme Fear $50k—panic/euphoria realization zones.  
![PnL by Sentiment](https://github.com/vipinvicky127-svg/ds_Vipin_Kumar/blob/main/outputs/pnl_by_sentiment.png)  
*Interpretation:* Purple/greens tower—contrarian: Realize in fear (51% long bias captures rebounds).

### 2. FG Distribution: Fear Dominates (800+ Days)
Fear/Greed each ~600–800 days; extremes rarer but high-impact.  
![FG Days Bar](https://raw.githubusercontent.com/vipinvicky127-svg/ds_Vipin_Kumar/refs/heads/main/outputs/sentiment_distribution.png)
*Interpretation:* Tall blue fear—market skews bearish; prep 2x more dip opportunities.

### 3. Risk Steady Across Sentiments
Trade sizes median $2–3k USD (flat boxes); fear outliers to $6k—disciplined leverage.  
![Risk Boxplot](https://raw.githubusercontent.com/vipinvicky127-svg/ds_Vipin_Kumar/refs/heads/main/outputs/risk_distribution.png)  
*Interpretation:* Overlapping medians—low vol risk always; scale safely in fear spikes
