# The Relationship Between Chinese Gold Jewelry Company Stock Prices and Gold Futures: A Comprehensive Empirical Analysis

## Executive Summary

This research examines the relationship between Chinese gold jewelry company stock prices and gold futures prices using data from 2010-2025 across multiple time frequencies. A market-cap-weighted Gold Jewelry Index was constructed from three major Hong Kong-listed companies. Analysis reveals a consistently positive and statistically significant relationship that strengthens dramatically across time horizons: daily (R² = 0.003, β = 0.05), monthly (R² = 0.115, β = 0.35), quarterly (R² = 0.131, β = 0.38), and yearly (R² = 0.290, β = 0.54). After controlling for broader market movements via the Hang Seng Index in multiple regression models, gold price movements retain independent predictive power (p < 0.05) for jewelry stock returns at monthly, quarterly, and yearly frequencies, validating the fundamental economic linkage between raw material costs/demand dynamics and corporate valuations.

## 1. Research Methodology

### 1.1 Data Collection and Filtering

**Gold Price Data:**
- COMEX Gold Futures (GC=F) - selected as primary gold price proxy
- Gold ETF GLD and IAU - excluded due to near-perfect correlation with COMEX Futures (ρ ≈ 0.99-1.00), avoiding multicollinearity in regression models
- Silver Futures (SI=F) - excluded as non-core to gold jewelry analysis

**Chinese Jewelry Company Stocks:**

*Included Companies:*
- Chow Tai Fook Jewellery Group (1929.HK) - Largest player, substantial fixed-price gold jewelry by weight
- Luk Fook Holdings (0590.HK) - Major competitor, similar business model
- Chow Sang Sang Holdings (0116.HK) - Established brand, significant fixed-price exposure

*Excluded Companies and Rationale:*
- China National Gold (600916.SS) - Limited data history (post-2015), significantly shortens analysis period
- Laopu Gold (6181.HK) - Different business model emphasizing high-craftsmanship artisanal pieces where gold price by weight is less dominant in final pricing compared to design/craftsmanship premiums

**Market Index:**
- Hang Seng Index (^HSI) - Control variable for Hong Kong market movements

**Data Period:** January 2010 - October 2025 (constrained by Chow Tai Fook IPO date in December 2011; actual analysis begins when all three companies have complete data)

### 1.2 Gold Jewelry Index Construction

A market capitalization-weighted index ("Gold Jewelry Index China") was constructed following established index methodology:

**Formula:** 
Index_t = 100 × (Σ(Market Cap_i,t) / Σ(Market Cap_i,0))

Where i represents each constituent company, t is current time, and 0 is the base period.

**Rationale for Market-Cap Weighting:**
1. Reflects true economic significance - larger companies have proportionally larger impact
2. Mirrors widely-recognized indices (S&P 500, MSCI indices) 
3. Self-rebalancing as market capitalizations naturally adjust
4. Reduces noise from company-specific events
5. Provides sector-level benchmark for investment analysis

**Base Value:** Normalized to 100 at earliest date with complete data for all three constituents

**Selection Criteria:**
Companies were selected based on:
1. Significant exposure to fixed-price gold jewelry (pricing directly linked to gold weight × prevailing gold price + markup)
2. Consistent trading history from 2010-2011 onwards
3. Hong Kong listing for market consistency
4. Complete, reliable data availability

This filtering ensures the analysis focuses on companies whose stock performance is most directly linked to gold price fluctuations through their business models.

## 2. Descriptive Statistics and Distribution Analysis

### 2.1 Daily Return Characteristics

**Mean Daily Returns:**
- COMEX Gold Futures: 0.035%
- Gold ETF GLD: 0.044%
- Gold ETF IAU: 0.037%
- Silver Futures: 0.038%
- Chow Tai Fook: 0.078%
- Luk Fook Holdings: 0.063%
- Chow Sang Sang: 0.050%
- Laopu Gold: 0.850% (limited data period)
- China National Gold: 0.057%
- Hang Seng Index: 0.014%

**Standard Deviation (Volatility):**
- COMEX Gold Futures: 0.98%
- Gold ETF GLD: 1.01%
- Gold ETF IAU: 0.98%
- Silver Futures: 1.92% (notably higher)
- Chow Tai Fook: 2.21%
- Luk Fook Holdings: 2.48%
- Chow Sang Sang: 2.50%
- Laopu Gold: 4.83% (limited data)
- China National Gold: 2.44%
- Hang Seng Index: 1.32%

**Key Finding:** Jewelry stocks exhibit 2-2.5× higher volatility than gold assets and 1.7-1.9× higher than Hang Seng Index, indicating elevated risk but potentially higher return opportunities.

**Extreme Movements (Min/Max Daily Returns):**
- Silver Futures: -17.75% to +9.29% (widest range)
- Chow Sang Sang: -12.88% to +27.51%
- Chow Tai Fook: -18.50% to +11.34%
- COMEX Gold Futures: -9.29% to +5.97%
- Hang Seng Index: -8.65% to +5.87%

### 2.2 Distribution Properties: Jarque-Bera Test Results

**Daily Returns:**
All assets reject normality (p-value = 0.0000 for all assets with sufficient data)

**Skewness:**
- Gold assets (COMEX, GLD, IAU): Negative skewness (-0.21 to -0.30), indicating more frequent small losses or fewer large gains
- Jewelry stocks: Positive skewness (+0.09 to +1.21), suggesting more frequent small gains or fewer large losses
- Hang Seng Index: Negative skewness (-0.35)

**Kurtosis (Excess Kurtosis):**
All assets show significant leptokurtosis:
- COMEX Gold Futures: 4.63
- Chow Tai Fook: 6.08
- Chow Sang Sang: 10.07 (highest)
- Luk Fook Holdings: 6.26
- Hang Seng Index: 4.71

**Interpretation:** Kurtosis values >> 3 indicate "fat tails" - extreme price movements occur more frequently than normal distribution predicts. This has critical implications for risk modeling, VaR calculations, and portfolio construction. Traditional mean-variance optimization may underestimate tail risk.

**Monthly/Quarterly Returns:**
- Monthly: Continue to reject normality (p < 0.05) for most assets
- Quarterly: Mixed results - some assets fail to reject normality, suggesting Central Limit Theorem effects as returns aggregate over longer periods smooth out extreme daily movements

**Central Limit Theorem Manifestation:**
While daily returns strongly deviate from normality, quarterly/yearly aggregations approach normality for several assets. This occurs because quarterly returns represent sums of approximately 60-65 daily returns. Despite daily returns not being strictly independent or identically distributed, the CLT effect reduces skewness and kurtosis, making distributions closer to normal. This has important modeling implications - quarterly/yearly data may be more suitable for traditional parametric statistical methods.

## 3. Correlation Analysis Across Time Frequencies

### 3.1 Daily Correlations

**Gold Assets Intercorrelations:**
- COMEX-GLD: 0.998
- COMEX-IAU: 0.997
- GLD-IAU: 0.999

*Implication:* Near-perfect correlation confirms these are essentially interchangeable gold price proxies. Using all three would create severe multicollinearity in regression models (VIF >> 10).

**Gold Assets to Jewelry Stocks:**
- COMEX to Gold Jewelry Index: ~0.05 (very weak)
- COMEX to Chow Tai Fook: ~0.08
- COMEX to Luk Fook: ~0.06
- COMEX to Chow Sang Sang: ~0.05

*Interpretation:* Daily gold price movements have minimal immediate impact on jewelry stock returns. Short-term noise dominates: company-specific news, intraday trading dynamics, general market sentiment overwhelm the fundamental gold price relationship.

**Jewelry Stocks to Hang Seng Index:**
- Chow Tai Fook to HSI: 0.42
- Luk Fook to HSI: 0.48
- Chow Sang Sang to HSI: 0.47
- Gold Jewelry Index to HSI: 0.52

*Interpretation:* Moderate-to-strong correlation demonstrates these stocks are significantly driven by broader Hong Kong market movements independent of gold prices.

### 3.2 Monthly Correlations

**Gold to Jewelry Stocks (Progressive Strengthening):**
- COMEX to Gold Jewelry Index: 0.34 (moderate, 7× increase from daily)
- COMEX to Chow Tai Fook: 0.36
- COMEX to Luk Fook: 0.30
- COMEX to Chow Sang Sang: 0.32

*Interpretation:* Sustained monthly gold price movements begin showing clear relationship with jewelry stocks. Market has time to process implications of persistent gold price trends for company costs, revenues, and margins.

**Jewelry to Hang Seng Index:**
- Chow Tai Fook to HSI: 0.44
- Luk Fook to HSI: 0.51
- Chow Sang Sang to HSI: 0.47
- Gold Jewelry Index to HSI: 0.50

*Interpretation:* Hong Kong market influence remains strong and consistent.

**Gold to Hang Seng Index:**
- COMEX to HSI: 0.25

*Interpretation:* Gold prices show weak-moderate correlation with broader market, suggesting some shared macroeconomic drivers (inflation expectations, currency movements, risk sentiment) but largely independent dynamics.

### 3.3 Quarterly Correlations

**Gold to Jewelry Stocks (Continued Strengthening):**
- COMEX to Gold Jewelry Index: 0.36 (moderate-strong)
- Individual stocks: 0.28-0.41 range

*Interpretation:* Quarterly financial reporting cycle aligns with this frequency. Quarterly results reflect gold price environment's impact on COGS, gross margins, and inventory valuations. Market expectations adjust to fundamental implications.

**Jewelry to Hang Seng Index:**
- Gold Jewelry Index to HSI: 0.46
- Individual stocks: 0.42-0.47 range

**Gold to Hang Seng Index:**
- COMEX to HSI: 0.35

*Interpretation:* Longer-term shared macroeconomic influences become more apparent.

### 3.4 Yearly Correlations

**Gold to Jewelry Stocks (Strongest Relationship):**
- COMEX to Gold Jewelry Index: 0.54 (strong, 11× increase from daily)
- Individual stocks: 0.45-0.59 range

*Interpretation:* Annual financial results comprehensively reflect gold price environment. Revenue (for fixed-price items), COGS, inventory gains/losses, pricing strategies, and long-term consumer demand all align with yearly gold price trends. Fundamental relationship fully manifests.

**Jewelry to Hang Seng Index:**
- Gold Jewelry Index to HSI: 0.43
- Remains consistently moderate-strong

**Gold to Hang Seng Index:**
- COMEX to HSI: 0.53

*Interpretation:* Long-term shared macroeconomic drivers (economic growth, inflation, currency trends) create stronger correlation between gold and broad market over yearly horizons.

### 3.5 Cross-Frequency Summary

The progressive strengthening pattern validates the hypothesis that gold-jewelry relationships are fundamentally time-dependent:

| Frequency | Gold-Jewelry ρ | Percentage Increase from Daily |
|-----------|----------------|-------------------------------|
| Daily     | 0.05          | Baseline                      |
| Monthly   | 0.34          | +580%                         |
| Quarterly | 0.36          | +620%                         |
| Yearly    | 0.54          | +980%                         |

## 4. Simple Linear Regression Analysis

### 4.1 Model Specification

**Model:** Gold_Jewelry_Index_Returns = β₀ + β₁(COMEX_Gold_Futures_Returns) + ε

### 4.2 Results by Frequency

**Daily Regression:**
- R² = 0.003
- Adjusted R² = 0.003
- β₁ (Gold Coefficient) = 0.049
- P-value (β₁) = 0.0028 (statistically significant at α = 0.01)
- Interpretation: While statistically significant due to large sample size (n ≈ 3,500), gold futures explain only 0.3% of daily jewelry index variance. Economic significance is minimal.

**Monthly Regression:**
- R² = 0.115
- Adjusted R² = 0.109
- β₁ (Gold Coefficient) = 0.348
- P-value (β₁) < 0.0001 (highly significant)
- Interpretation: Gold futures explain 11.5% of monthly jewelry index variance. A 1% increase in monthly gold futures returns associates with 0.35% increase in jewelry index returns. Economically meaningful relationship emerges.

**Quarterly Regression:**
- R² = 0.131
- Adjusted R² = 0.115
- β₁ (Gold Coefficient) = 0.377
- P-value (β₁) < 0.0001 (highly significant)
- Interpretation: Gold futures explain 13.1% of quarterly variance. Relationship strengthens further; quarterly financial reporting alignment makes connection more apparent.

**Yearly Regression:**
- R² = 0.290
- Adjusted R² = 0.231
- β₁ (Gold Coefficient) = 0.538
- P-value (β₁) = 0.0091 (significant at α = 0.01)
- Interpretation: Gold futures explain 29% of yearly variance - strong fundamental relationship. A 1% yearly gold price increase associates with 0.54% jewelry index increase. Note: Yearly analysis has limited observations (n ≈ 12-14), reducing statistical power but still achieving significance.

### 4.3 Progressive R² Pattern

The dramatic R² increase from daily (0.003) to yearly (0.290) represents a 97-fold improvement in explanatory power, confirming that time horizon fundamentally determines the strength of the gold-jewelry relationship.

## 5. Multiple Regression Analysis: Controlling for Market Effects

### 5.1 Model Specification

**Model:** Gold_Jewelry_Index_Returns = β₀ + β₁(COMEX_Returns) + β₂(Hang_Seng_Returns) + ε

### 5.2 Results and Comparison to Simple Regression

**Daily Multiple Regression:**
- R² = 0.291 (vs 0.003 simple) - massive improvement
- Adjusted R² = 0.290
- β₁ (Gold Coef) = 0.031, P-value = 0.051 (marginal significance)
- β₂ (HSI Coef) = 0.626, P-value < 0.0001 (highly significant)
- Interpretation: Hang Seng Index dominates daily movements, explaining 29.1% of variance. Gold effect becomes marginal when controlling for market. Short-term jewelry stock performance primarily driven by broad market dynamics.

**Monthly Multiple Regression:**
- R² = 0.393 (vs 0.115 simple)
- Adjusted R² = 0.385
- β₁ (Gold Coef) = 0.235, P-value = 0.0003 (highly significant)
- β₂ (HSI Coef) = 0.531, P-value < 0.0001 (highly significant)
- Interpretation: Both predictors significant. HSI explains much variance, but gold retains independent predictive power. After controlling for market, gold still explains additional variance. Combined model explains 39.3% of monthly variance.

**Quarterly Multiple Regression:**
- R² = 0.465 (vs 0.131 simple)
- Adjusted R² = 0.455
- β₁ (Gold Coef) = 0.267, P-value = 0.0012 (highly significant)
- β₂ (HSI Coef) = 0.538, P-value < 0.0001 (highly significant)
- Interpretation: Gold coefficient remains substantial and significant. Combined model explains 46.5% of quarterly variance - strongest model performance. Both gold and market effects independently important.

**Yearly Multiple Regression:**
- R² = 0.542 (vs 0.290 simple)
- Adjusted R² = 0.527
- β₁ (Gold Coef) = 0.349, P-value = 0.0234 (significant at α = 0.05)
- β₂ (HSI Coef) = 0.461, P-value = 0.0089 (significant at α = 0.01)
- Interpretation: Over yearly horizons, both gold and market movements significantly impact jewelry stocks. Combined model explains 54.2% of yearly variance. Gold effect persists even when controlling for market.

### 5.3 Critical Finding: Gold Price Independent Effect

**Key Observation:** When Hang Seng Index is added to the model, gold coefficient magnitude decreases across all frequencies (e.g., monthly: 0.348 → 0.235), indicating some shared variance between gold prices and broad market. However, gold coefficient remains statistically significant at monthly, quarterly, and yearly frequencies (p < 0.05).

**Implication:** Gold price movements have independent predictive power for jewelry stock returns beyond their correlation with broader market movements. This validates the fundamental economic channel: gold price changes affect jewelry companies through both cost structures and demand dynamics, not merely as a proxy for general market sentiment.

### 5.4 Hang Seng Index Dominance

Across all frequencies, Hang Seng Index coefficients are consistently larger than gold coefficients and highly significant (p < 0.0001). This reflects:
1. These are Hong Kong-listed equities subject to regional market dynamics
2. General market sentiment, liquidity conditions, and macroeconomic factors in Hong Kong significantly drive stock performance
3. Jewelry stocks have substantial systematic risk (market beta) beyond commodity exposure

## 6. Non-Linear Regression Analysis

### 6.1 Model Specification

**Model:** Gold_Jewelry_Index_Returns = β₀ + β₁(COMEX) + β₂(HSI) + β₃(COMEX²) + β₄(HSI²) + β₅(COMEX × HSI) + ε

Testing for:
- Quadratic effects (β₃, β₄): Do squared terms capture accelerating/decelerating relationships?
- Interaction effects (β₅): Does gold's impact vary with market conditions?

### 6.2 Results Summary

**Daily Non-Linear:**
- R² = 0.291 (vs 0.291 linear)
- Squared term p-values: 0.8672 (COMEX²), 0.9103 (HSI²)
- Interaction p-value: 0.9722
- Conclusion: No significant non-linear effects. Linear model sufficient.

**Monthly Non-Linear:**
- R² = 0.403 (vs 0.393 linear) - marginal 0.01 improvement
- Squared term p-values: 0.7566 (COMEX²), 0.6344 (HSI²)
- Interaction p-value: 0.4545
- Adjusted R² = 0.388 (vs 0.385 linear) - minimal improvement when penalizing complexity
- Conclusion: Non-linear terms not statistically significant. Marginal R² improvement does not justify added complexity.

**Quarterly Non-Linear:**
- R² = 0.467 (vs 0.465 linear) - negligible 0.002 improvement
- Squared term p-values: 0.7788 (COMEX²), 0.9730 (HSI²)
- Interaction p-value: 0.8084
- Adjusted R² = 0.426 (vs 0.455 linear) - **adjusted R² decreases** despite R² increase
- Conclusion: Added complexity not justified. Linear model superior.

**Yearly Non-Linear:**
- R² = 0.583 (vs 0.542 linear) - 0.04 improvement
- Squared term p-values: 0.5678 (COMEX²), 0.9278 (HSI²)
- Interaction p-value: 0.6699
- Adjusted R² = 0.420 (vs 0.527 linear) - **substantial decrease**
- Conclusion: With limited yearly observations (n ≈ 12-14), adding 3 parameters severely penalized. Non-linear terms not significant. Linear model strongly preferred.

### 6.3 Overall Non-Linearity Assessment

Across all time frequencies, the polynomial regression model with squared terms and interaction effects provides no statistically significant improvement over linear models. All non-linear term p-values > 0.05. The relationships between gold jewelry returns, gold futures returns, and market returns are fundamentally linear within the tested framework and dataset.

**Possible Explanations:**
1. True relationship is linear within observed gold price ranges
2. Sample period may not include extreme gold price regimes where non-linearities emerge
3. Other functional forms (exponential, logarithmic) not tested may capture non-linearities
4. Company hedging strategies and pricing adjustments may linearize the transmission mechanism

**Modeling Recommendation:** Linear multiple regression (Gold Jewelry Returns ~ COMEX Returns + HSI Returns) provides parsimonious, statistically sound models across all frequencies.

## 7. Time Frequency Impact: Economic Interpretation

### 7.1 Daily Dynamics: Noise Dominates

**Why Weak Daily Relationship (R² = 0.003)?**

Multiple factors create daily noise:
1. **Intraday Trading Dynamics:** Momentum trading, technical signals, liquidity shocks unrelated to fundamentals
2. **Market Microstructure:** Bid-ask bounces, price discovery processes, order flow imbalances
3. **Information Asymmetry:** Company-specific news (management changes, store openings, competitive actions) affects individual stocks immediately
4. **Sentiment Volatility:** Short-term risk appetite fluctuations drive general equity volatility
5. **Gold Price Insignificance:** Minor daily gold fluctuations (±0.5-1%) don't immediately alter profitability expectations or warrant repricing

Gold price is one of many inputs, and daily changes are too small/transient to shift investment thesis.

### 7.2 Monthly/Quarterly Dynamics: Fundamentals Emerge

**Why Strengthening Relationship (R² = 0.115-0.131)?**

1. **Sustained Price Trends:** Persistent monthly movements (e.g., +5-10% over month) represent meaningful cost/revenue changes
2. **Financial Reporting Alignment:** Quarterly earnings reports capture gold price impact on:
   - Cost of Goods Sold (direct material costs)
   - Gross Margin trends
   - Inventory valuation (FIFO/weighted average accounting)
3. **Pricing Strategy Adjustments:** Companies have time to adjust retail prices for fixed-price items
4. **Consumer Behavior Response:** Sustained price increases trigger:
   - Accelerated purchasing before further increases (demand surge)
   - Investment buying (gold as store of value)
   - Brand switching based on relative pricing
5. **Analyst Coverage:** Monthly/quarterly updates from sell-side analysts incorporate gold price forecasts into earnings models, influencing institutional investor positioning

Market participants gain sufficient time horizon to assess and price fundamental impacts.

### 7.3 Yearly Dynamics: Fundamental Relationship Dominates

**Why Strongest Relationship (R² = 0.290)?**

1. **Annual Financial Statements:** Comprehensive reflection of gold price environment:
   - Full-year revenue heavily influenced by average gold price level (fixed-price sales)
   - Full-year COGS directly tied to gold procurement costs
   - Inventory gains/losses fully realized
   - Year-end valuation adjustments
2. **Strategic Adjustments Complete:** Companies implement:
   - Pricing strategy changes
   - Product mix optimization
   - Hedging program adjustments
   - Inventory management refinements
3. **Long-Term Investor Positioning:** Institutional investors with yearly rebalancing cycles incorporate gold price outlook into valuations
4. **Business Cycle Alignment:** Annual performance captures:
   - Seasonal variations (Chinese New Year, wedding seasons) fully integrated
   - Consumer spending patterns influenced by persistent gold price trends
   - Competitive dynamics and market share shifts
5. **Macroeconomic Integration:** Yearly gold price trends reflect and correlate with broader economic conditions (inflation, currency movements, growth expectations) that also fundamentally affect consumer discretionary spending and luxury goods demand

The yearly view captures the complete economic transmission mechanism from commodity prices → company fundamentals → stock valuations.

## 8. Understanding the Positive Correlation: Economic Mechanisms

### 8.1 The Counterintuitive Result

Traditional cost-based reasoning suggests: Rising gold prices → Higher raw material costs → Lower profit margins → Negative stock performance

However, empirical results show: Rising gold prices → **Positive** jewelry stock returns

This requires explanation through demand-side mechanisms specific to Chinese gold jewelry market.

### 8.2 Investment Demand and Price Expectations

**Cultural Context:** In Chinese culture, gold jewelry serves dual purposes:
1. Adornment and cultural significance (weddings, festivals)
2. Investment vehicle and wealth preservation

**Demand Channel:**
- Rising gold prices create positive feedback loop
- Consumers anticipate further increases
- "Buy now before prices rise more" mentality
- Gold jewelry as tangible inflation hedge
- Preference for physical assets over financial assets in certain demographics

**Evidence:** This behavior particularly strong in:
- Tier 2-3 Chinese cities with less developed financial markets
- Older demographics with traditional investment preferences
- Periods of currency depreciation or inflation concerns

### 8.3 Inventory Valuation Effects

**Mechanism:**
- Companies maintain significant gold inventory (both raw materials and finished goods)
- Rising gold prices increase balance sheet asset values
- FIFO or weighted-average accounting methods reflect gains
- Inventory gains boost reported profitability in rising price environments
- Enhanced balance sheet quality improves credit ratings and borrowing costs

**Magnitude:** Large retailers may hold several tons of gold inventory. A 10% gold price increase on 5,000 kg inventory at $60,000/kg = $30 million inventory gain.

### 8.4 Price Pass-Through Capability

**Fixed-Price Business Model:**
- Major Chinese jewelry chains prominently feature "fixed-price" gold items
- Selling price formula: (Current Gold Price per Gram × Item Weight) + Labor/Design Fee + Retail Markup
- Prices adjust automatically/daily based on current gold market rates
- Consumers accept pricing mechanism (transparently displayed in stores)

**Margin Protection:**
- Companies can immediately pass increased costs to consumers
- Labor/design fees and retail markups often calculated as percentages, amplifying in absolute terms when base gold price rises
- Gross margins on fixed-price items remain stable or improve
- Premium brand positioning allows for additional markup expansion during gold price rallies

### 8.5 Brand Value Enhancement

**Premium Positioning:**
- Rising gold prices enhance perceived value of jewelry
- "My necklace is worth more now" psychology
- Brand prestige associated with higher-value inventory
- Justifies and reinforces premium pricing on non-fixed-price (high craftsmanship) items
- Marketing benefits: "Investment-grade jewelry" positioning

### 8.6 Company Growth Trajectories

**Confounding Factor:**
All analyzed companies experienced substantial growth 2010-2025:
- Geographic expansion (new store openings in emerging markets)
- E-commerce channel development
- Brand maturation and market penetration increases
- Rising middle-class consumption in China
- Improved operational efficiency and supply chain management

**Implication:** Positive stock returns over the period partly reflect inherent company growth independent of gold prices. Gold price correlation may capture some of this if growth periods coincided with gold rallies, or if company expansions were strategically timed to gold market conditions.

### 8.7 Integrated Explanation

The **positive correlation** results from demand-side effects (investment demand, price expectations, cultural preferences) overwhelming supply-side cost increases, particularly in the Chinese market context where gold jewelry combines consumption and investment functions. This is amplified by companies' pricing power, inventory management capabilities, and inherent growth trends.

Over longer time horizons (yearly), these fundamental dynamics fully materialize in financial statements and market valuations, explaining the strengthening positive relationship.

## 9. Key Findings and Conclusions

### 9.1 Primary Findings

1. **Time-Dependent Relationship Strength:** The relationship between gold futures returns and Chinese gold jewelry stock returns is fundamentally time-dependent, with correlation and R² values increasing dramatically from daily to yearly horizons. This pattern is statistically robust and economically interpretable.

2. **Independent Gold Price Effect:** Gold futures returns maintain statistically significant predictive power for jewelry stock returns (p < 0.05) even after controlling for Hang Seng Index movements at monthly, quarterly, and yearly frequencies. This validates the fundamental economic linkage beyond simple market correlation.

3. **Market Dominance at Short Horizons:** The Hang Seng Index is the dominant driver of daily and monthly jewelry stock returns (larger coefficients, stronger significance), reflecting the substantial systematic risk (market beta) inherent in these equities.

4. **Fundamental Relationship at Long Horizons:** Over quarterly and especially yearly periods, gold prices become substantially more important (R² increases from 0.003 to 0.290 simple regression; 0.291 to 0.542 multiple regression), capturing their fundamental impact on business economics, financial performance, and investor valuations.

5. **Linear Relationship Dominance:** Non-linear regression models (polynomial with squared terms and interactions) provide no statistically significant improvement across any time frequency. The relationships are well-described by linear models within the tested framework and sample period.

6. **Positive Correlation Mechanism:** The consistently positive correlation between gold prices and jewelry stock returns, while counterintuitive from a pure cost perspective, is explained by demand-side factors (investment demand, price expectations, inventory gains, pricing pass-through) that dominate cost pressures in the Chinese market context.

### 9.2 Statistical Robustness

- All key relationships achieve statistical significance at conventional levels (p < 0.05)
- Results consistent across multiple model specifications (simple, multiple, non-linear)
- Pattern replicates across individual stocks and composite index
- Findings align with economic theory and industry knowledge

### 9.3 Economic Significance

While statistical significance is achieved, economic significance varies:
- Daily models have weak economic significance (R² = 0.003 simple, β ≈ 0.05)
- Monthly/quarterly models show moderate economic significance (R² = 0.12-0.13 simple, β ≈ 0.35-0.38)
- Yearly models demonstrate strong economic significance (R² = 0.29 simple, 0.54 multiple)

For practical investment applications, monthly and longer horizons provide actionable relationships.

## 10. Limitations and Future Research Directions

### 10.1 Methodological Limitations

**Index Construction:**
- Basic market-cap weighting methodology; more sophisticated approaches (fundamental weighting, risk-parity) not explored
- Limited to three constituent companies; broader industry index would be more representative
- Corporate actions (splits, dividends, special distributions) handled with basic adjustments

**Model Specification:**
- Standard OLS regression assumptions not formally tested (homoskedasticity, no autocorrelation, normality of residuals)
- Potentially relevant control variables excluded: RMB/USD exchange rate, consumer price index, interest rates, consumer confidence indices, gold import regulations
- Alternative econometric specifications not explored: error correction models, GARCH models for time-varying volatility, VAR/VECM for dynamic relationships

**Data Constraints:**
- Analysis period limited by IPO dates (particularly Chow Tai Fook December 2011)
- Yearly analysis has limited observations (n ≈ 12-14), reducing statistical power
- No access to company-specific operational data (inventory levels, hedging positions, sales mix by product category)

### 10.2 Data Gaps

**Unavailable Micro-Level Data:**
- Detailed sales breakdown: fixed-price gold jewelry by weight vs. high-craftsmanship/design-premium items
- Real-time inventory levels, composition, and turnover rates
- Hedging strategies: futures positions, options contracts, effectiveness measurement
- Granular geographic sales data: tier-1 vs. tier-2/3 cities, regional variations
- Customer demographics and purchasing behavior (survey data)
- Pricing strategy details: markup structures, promotional activities, dynamic pricing algorithms

**External Factors Not Analyzed:**
- Chinese government gold market policies and regulations
- Import/export restrictions and tariffs
- Cultural events and seasonal patterns (Chinese New Year demand, wedding season timing)
- Competitive landscape dynamics and market share evolution
- E-commerce disruption and channel shift impact
- COVID-19 pandemic effects on store traffic and consumer behavior

### 10.3 Future Research Opportunities

1. **Expanded Geographic Scope:**
   - Include mainland China A-share listed jewelry companies (post-2015 data available)
   - Compare dynamics with Western markets (U.S. jewelry retailers, European luxury conglomerates)
   - Cross-country comparative analysis: Does Chinese positive correlation replicate elsewhere?

2. **Granular Company-Level Analysis:**
   - With access to detailed financial disclosures, decompose revenue/profit by product category
   - Analyze companies with different business model exposures (high-craftsmanship vs. fixed-price dominated)
   - Examine hedging strategy effectiveness using position-level data

3. **Advanced Econometric Models:**
   - Time-series models: ARIMA, VAR, VECM for dynamic relationships and lead-lag structures
   - Regime-switching models: Do relationships change in gold bull vs. bear markets?
   - GARCH family models: Capture time-varying volatility and conditional correlations
   - Machine learning approaches: Non-parametric methods (random forests, neural networks) may capture complex non-linearities

4. **Additional Control Variables:**
   - Macroeconomic variables: GDP growth, CPI, interest rates, exchange rates
   - Consumer sentiment indices: China Consumer Confidence Index
   - Commodity market variables: platinum, silver, diamond prices
   - Alternative investment returns: real estate, wealth management products
   - Gold-specific variables: gold import volumes, central bank purchases, mine production

5. **Product Category Analysis:**
   - Separate analysis for companies with different product mix exposures
   - Time-series analysis of shifting product mix and its impact on gold price sensitivity
   - Consumer preference evolution: tracking fixed-price vs. design-premium demand

6. **International Comparison Study:**
   - Western market comparison: Tiffany & Co., Signet Jewelers, Pandora
   - Do Western jewelry stocks show same positive correlation or cost-driven negative correlation?
   - Cultural and institutional factors explaining cross-country differences

## 11. Practical Implications

### 11.1 For Investors

**Investment Strategy Considerations:**
- **Time Horizon Alignment:** Short-term traders should focus on Hang Seng Index movements; long-term investors should incorporate gold price forecasts
- **Diversification Benefits:** Chinese gold jewelry stocks provide blended exposure to both commodity prices and Hong Kong equities
- **Tactical Allocation:** Gold price trends may offer signals for 3-12 month positioning in jewelry stocks
- **Risk Management:** Higher volatility than gold or broad market requires appropriate position sizing; stop-loss disciplines important

**Portfolio Construction:**
- Jewelry stocks offer differentiated risk-return profile vs. pure gold exposure (mining stocks, ETFs) or pure equity exposure
- Positive correlation with gold provides partial inflation hedge within equity portfolio
- Consider jewelry stocks as satellite holding (5-15% allocation) in Asia-Pacific equity sleeves

### 11.2 For Company Management

**Strategic Planning:**
- **Pricing Strategy:** Dynamic pricing for fixed-price items should closely track gold spot prices with minimal lag
- **Inventory Management:** Optimize inventory levels considering gold price forecasts; strategic inventory build during anticipated rallies
- **Product Mix:** Balance fixed-price (gold-price-sensitive) vs. high-craftsmanship (design-premium) offerings based on gold market outlook
- **Hedging Decisions:** Cost-benefit analysis of futures/options hedging considering positive demand elasticity to gold prices
- **Investor Relations:** Clearly communicate gold price transmission mechanisms to equity analysts and investors

**Operational Implications:**
- Procurement timing: Centralized gold purchasing with market timing capabilities
- Working capital management: Rising gold prices increase working capital needs
- Expansion timing: Consider gold price environment when planning store network growth

### 11.3 For Policymakers

**Market Stability Monitoring:**
- Gold price volatility has amplified effects on jewelry retail sector through both cost and demand channels
- Sudden gold price spikes may create consumer panic buying and inventory speculation

**Consumer Protection:**
- Ensure pricing transparency for fixed-price gold jewelry
- Regulate misleading "investment value" marketing claims
- Monitor retailer markup practices during gold price volatility

**Economic Indicators:**
- Jewelry sales volumes may serve as indicators of:
  - Consumer discretionary spending and confidence
  - Inflation expectations (gold as inflation hedge)
  - Wealth effect from gold price changes

## 12. Conclusion

This comprehensive analysis provides robust empirical evidence of a positive, statistically significant, and time-frequency-dependent relationship between gold futures prices and Chinese gold jewelry company stock returns. The relationship strengthens dramatically from negligible daily correlation (ρ = 0.05, R² = 0.003) to strong yearly correlation (ρ = 0.54, R² = 0.290), reflecting the time required for fundamental economic transmission mechanisms to manifest in corporate financial performance and investor valuations.

Critically, gold price movements retain independent predictive power for jewelry stock returns even after controlling for broader Hong Kong market movements (Hang Seng Index), particularly at monthly, quarterly, and yearly frequencies. This validates the fundamental economic channel: gold price changes affect these companies through both raw material cost structures and consumer demand dynamics, with the latter appearing to dominate in the Chinese market context due to gold's dual role as consumption good and investment asset.

The analysis reveals that linear models adequately capture these relationships within the tested framework; non-linear specifications provide no statistically significant improvement. The consistently positive correlation, while initially counterintuitive from a pure cost perspective, is economically rationalized by demand-side factors (investment demand driven by price expectations, inventory valuation effects, pricing pass-through capabilities, and cultural preferences for gold as wealth storage) that overwhelm raw material cost pressures.

These findings have important implications for investors (time-horizon-appropriate strategies, diversification benefits), corporate managers (pricing strategy, inventory optimization, hedging decisions), and policymakers (market stability monitoring, consumer protection, economic indicator development).

This research establishes a foundational understanding of the complex interplay between commodity prices, consumer behavior, and stock market valuations in the Chinese gold jewelry sector, highlighting the critical importance of time frequency selection in financial analysis and the unique market dynamics created by gold's multifaceted role in Chinese consumer culture.

