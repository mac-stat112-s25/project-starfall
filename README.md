# 📊 Stock Market Volatility: Patterns and Predictions
## STAT 112 - Spring 2025
### Macalester College

<p align="center">
  <img src="https://commons.wikimedia.org/wiki/File:Macalester_College_Logo.png" alt="Macalester College Logo" width="300">
  <br>
</p>

## 👥 Team Members

| Name | Role | Focus Area |
|------|------|------------|
| **Zhijun He** | Lead Data Analyst | Cross-Market Correlation, Volatility Regimes |
| **Phoebe Pan** | Statistical Modeler | Sector Analysis, Event Impact Quantification |

## 🎯 Project Overview

This project delivers a comprehensive analysis of stock market volatility patterns across major global markets from 2000 to 2025. Through rigorous statistical methodology and data visualization, we investigate the complex interplay between economic, political, and global events and their impact on market volatility across different sectors and geographic regions.

Unlike typical market studies that focus solely on price or return patterns, our analysis centers on volatility—the key barometer of market uncertainty and risk. By exploring the temporal evolution of volatility across different markets and sectors, we provide valuable insights for investors, risk managers, and policymakers navigating increasingly complex financial landscapes.

### Research Questions

Our analysis is guided by these central questions:

1. **Event Impact**: How do different types of global events (financial crises, geopolitical tensions, natural disasters, pandemics) affect market volatility magnitude, duration, and recovery patterns?

2. **Market Integration**: What patterns emerge in volatility transmission between global markets, and how has this transmission speed changed over time?

3. **Sector Vulnerability**: How do different market sectors respond to various crisis types, and which sectors offer the best defensive properties during market turbulence?

4. **Early Warning Systems**: Can specific volatility patterns or sector-specific movements serve as early warning signals for broader market disruptions?

5. **Volatility Regimes**: How have volatility regimes evolved over the 25-year study period, and what factors drive transitions between these regimes?

## 📊 Interactive Dashboard

Explore our findings through our interactive Quarto-powered web dashboard:
[**Market Volatility Dashboard**](https://mac-stat112-s25.github.io/project-starfall/)

## 📚 Data Sources

Our analysis integrates data from multiple high-quality sources:

- **Yahoo Finance** (via tidyquant): 
  - Historical daily stock price data (2000-2025)
  - Six major global indices: S&P 500 (US), FTSE 100 (UK), Nikkei 225 (Japan), DAX (Germany), CAC 40 (France), and Hang Seng (Hong Kong/China)
  - Over 37,500 trading days analyzed across all markets
  - Data frequency: Daily OHLC (Open, High, Low, Close) with volume

- **Sector ETFs**:
  - XLF (Financial): 177 constituent companies
  - XLK (Technology): 149 constituent companies
  - XLE (Energy): 24 constituent companies
  - XLV (Healthcare): 65 constituent companies
  - XLY (Consumer): 52 constituent companies
  - Data includes price, volume, and constituent weights

- **Historical Events Dataset**: 
  - Self-compiled database of 78 major global events
  - Categories include: Financial crises, Geopolitical conflicts, Natural disasters, Policy changes, Technological disruptions, Health crises
  - Each event tagged with: Date, Type, Geographic origin, Initial impact region, Global significance rating

## 🔬 Analysis Methods

Our methodological approach combines traditional financial metrics with advanced statistical techniques:

### Volatility Quantification
- **Rolling Volatility Analysis**: Using 21-day (monthly) and 63-day (quarterly) rolling standard deviation of returns to quantify market turbulence at different time scales
- **Parkinson's High-Low Range**: Incorporating intraday price ranges for more accurate volatility estimation
- **Log-normalized returns**: Ensuring statistical properties appropriate for time-series analysis

### Regime Analysis
- **Volatility Regime Classification**: Employing hierarchical clustering to categorize markets into five distinct volatility states:
  - Very Low: < 10% annualized volatility
  - Low: 10-15% annualized volatility
  - Normal: 15-25% annualized volatility
  - High: 25-35% annualized volatility
  - Crisis: > 35% annualized volatility
- **Regime Transition Modeling**: Analyzing the probabilities and catalysts for shifts between volatility regimes

### Correlation & Relationship Analysis
- **Dynamic Conditional Correlation (DCC)**: Measuring time-varying correlations between global markets
- **Principal Component Analysis**: Identifying common volatility factors across regions
- **Event Studies**: Measuring abnormal volatility during key historical events using 30-day pre-event windows as baselines
- **Granger Causality Tests**: Examining lead-lag relationships in volatility transmission between markets

### Sector Behavior Analysis
- **Crisis Volatility Ratio**: Computing sector-specific ratios of crisis-period volatility to normal-period volatility
- **Sector Rotation Analysis**: Tracking volatility shifts between sectors as market conditions evolve
- **Defensive Score Calculation**: Creating a composite metric of sector performance during various crisis types

## 🔍 Key Findings

Our comprehensive analysis reveals several groundbreaking insights:

### Market Integration Evolution
- Global market integration has increased dramatically, with volatility transmission between markets accelerating from 3-4 weeks (in early 2000s) to just 1-3 days (by 2020s)
- European markets show the highest integration with correlation coefficients above 0.85, while Asian markets maintain more independence
- Correlation between developed and emerging markets peaks during crisis periods but diverges during recovery phases

### Crisis Type Signatures
- Different crisis types produce distinctive volatility "signatures" identifiable through:
  - **Shape**: Financial crises generate prolonged elevated volatility (3-6 months), while geopolitical events cause sharper but shorter disruptions (1-2 months)
  - **Magnitude**: Financial crises increase volatility by 2.8x on average, health crises by 2.4x, geopolitical events by a more modest 1.7x
  - **Recovery Pattern**: Technology-led crises show rapid recovery, while financial sector crises experience longer-duration volatility with frequent aftershocks

### Sector Stability Rankings
- Healthcare demonstrates remarkable stability across all crisis types (crisis-to-normal volatility ratio of just 1.6), making it the most defensive sector
- Financial stocks exhibit extreme sensitivity with volatility more than tripling during disruptions (average ratio: 3.2)
- Technology and Energy sectors show crisis-specific responses:
  - Technology volatility spikes during tech-specific bubbles
  - Energy volatility responds most dramatically to geopolitical events and supply shocks

### Regional Divergence Patterns
- Despite increased global integration, Chinese markets have shown increasingly independent volatility patterns since 2020
- European markets demonstrate the most synchronized volatility profiles (average correlation: 0.82)
- Japanese market volatility shows uniquely muted response to global events after 2010

### Early Warning Indicators
- Sector-specific volatility shifts, particularly in financial and energy sectors, demonstrate potential as early warning signals for broader market disruptions
- Financial sector volatility typically leads broad market volatility by 2-3 weeks
- The VIX/MOVE ratio (equity/bond volatility) provides predictive power for upcoming volatility regime shifts
- Correlation breakdowns between traditionally related assets often precede major market disruptions

## 📁 Repository Structure

```
project-starfall/
├── .github/              # GitHub configuration files
├── data/                 # Data files
│   └── msg.csv           # Market data CSV file
├── github/               # GitHub templates and configurations
│   └── workflows/        # GitHub Actions workflows
│   └── issue_template.md # Template for GitHub issues
├── src/                  # Source files
│   ├── appx/             # Appendix files
│   ├── EDA - Phoebe Pan.qmd     # Exploratory analysis by Phoebe
│   ├── EDA - Zhijun He.qmd      # Exploratory analysis by Zhijun
│   └── market_volatility_summary.csv  # Volatility data summary
├── style/                # Custom styling
│   └── custom.css        # Custom CSS for Quarto output
├── .gitignore            # Git ignore file
├── DS112 Final Pre_ Stock Market Volatility.pptx  # Final presentation slides
├── README.md             # This file
├── Zhijun:Phoebe- Presentation-Starfall.mp4  # Project presentation video
├── _quarto.yml           # Quarto configuration file
├── index.qmd             # Main report file
├── market_volatility_summary.csv  # Volatility summary data (root level)
└── qb.Rproj              # RStudio project file
```

## 🚀 How to Reproduce

To reproduce our analysis, follow these steps:

### Prerequisites
- R (version 4.2.0 or higher)
- RStudio (version 1.4 or higher) with Quarto support
- Git

### Setup Instructions
1. Clone this repository:
   ```bash
   git clone https://github.com/mac-stat112-s25/project-starfall.git
   cd project-starfall
   ```

2. Install required R packages:
   ```r
   # Core data manipulation and analysis
   install.packages(c("tidyverse", "tidyquant", "lubridate", "TTR", "xts", "zoo"))
   
   # Visualization packages
   install.packages(c("ggplot2", "patchwork", "scales", "ggthemes", "gridExtra"))
   
   # Statistical packages
   install.packages(c("corrplot", "knitr", "kableExtra"))
   ```

3. Quarto installation (if not already installed):
   ```bash
   # Install Quarto CLI from https://quarto.org/docs/get-started/
   ```

4. Run the complete analysis:
   ```r
   # Option 1: Use Quarto CLI
   quarto render
   
   # Option 2: From RStudio
   # Open qb.Rproj and click "Render" button in RStudio
   ```

5. Explore specific analyses:
   - Open individual .qmd files to run specific sections
   - View rendered output in the `docs/` directory
   - Use `source("R/specific_function.R")` to load custom functions

## 📈 Key Visualizations

Our analysis includes over 30 publication-quality visualizations. Highlights include:

- **Volatility Regime Heat Map**: A temporal visualization showing how markets transition between volatility states over 25 years
- **Crisis Signature Comparison**: Side-by-side visualization of volatility patterns during different crisis types
- **Sector Response Dashboard**: Interactive tool for exploring how different sectors respond to various market conditions
- **Correlation Network Graph**: Force-directed network visualization of market relationships
- **Volatility Transmission Animation**: Time-series animation showing how volatility propagates across global markets

## 🏆 Applications & Impact

Our findings have several practical applications:

- **For Investors**: Enhanced portfolio construction techniques that account for specific crisis types and sector responses
- **For Risk Managers**: Improved early warning systems for detecting upcoming market turbulence
- **For Policymakers**: Better understanding of market interconnectedness and potential financial contagion channels
- **For Academics**: Quantitative framework for classifying and comparing market events across time and regions

## 🔮 Future Research Directions

Building on our work, we identify these promising avenues for future research:

1. **Machine Learning Integration**: Applying deep learning techniques to identify complex non-linear relationships in volatility patterns
2. **Alternative Data Sources**: Incorporating sentiment analysis from news and social media to enhance volatility prediction models
3. **Regional Expansion**: Extending analysis to emerging markets and cryptocurrency volatility
4. **Causality Analysis**: Developing more sophisticated models of volatility transmission mechanisms
5. **Policy Response Effects**: Quantifying how central bank and regulatory responses impact volatility regimes

## 🙏 Acknowledgements

We express our sincere gratitude to:

- **Professor Amin Alhashim**, Department of Mathematics, Statistics, and Computer Science at Macalester College, for her exceptional guidance and thoughtful feedback throughout this project （We love you Amin!）
- **Yahoo Finance** for providing the historical financial data accessed through the tidyquant package
- **Macalester College DeWitt Wallace Library** for access to financial databases and research resources
- Fellow students in STAT 112 for their valuable peer reviews and suggestions

## 📧 Contact & Resources

For questions or collaboration opportunities:

- **Zhijun He**: zhe@macalester.edu

### Additional Resources
- **Interactive Dashboard**: [Market Volatility Dashboard](https://mac-stat112-s25.github.io/project-starfall/)
- **Presentation Video**: See `Zhijun:Phoebe- Presentation-Starfall.mp4` in the repository
- **Presentation Slides**: Available as `DS112 Final Pre_ Stock Market Volatility.pptx`
- **GitHub Classroom**: This project was completed as part of Macalester College's STAT 112 course

---

<p align="center">
  <br>
  <em>Team Starfall • Macalester College • STAT 112 Spring 2025</em>
</p>
