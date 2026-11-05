# PMFBY-CROP-INSURANCE-ANALYSIS
# PMFBY Crop Insurance Analysis (2018–2025)

District-level analysis of India's crop insurance scheme (PMFBY): data cleaning, an insurance performance score (AIIS), clustering, a policy simulation, and a Power BI dashboard.

## What I did
1. **Cleaned and validated the data**
   - 7,373 raw rows, minus 15 "Grand Total" summary rows = **7,358 records**
   - Standardised 6 inconsistent state names (33 → 27 distinct states)
   - Flagged 21 structural-zero records (no activity reported)
   - Checked gender-percentage consistency
2. **Built the AIIS score** (Agricultural Insurance Intelligence Score)
   - Screened 19 indicators with correlation and VIF checks, kept 14 (max VIF 3.43)
   - Weighted indicators with the entropy method; scored 7,355 rows (3 had missing values)
3. **Clustered districts** with K-means (k = 2): 5,876 high and 1,479 low scoring records
4. **Simulated a policy scenario** (premium +20%, coverage density +15%, claim per farmer +10%) using a Random Forest model
5. **Built a 3-page Power BI dashboard**: claims overview, AIIS by state and year, and the simulation

## Key results
| Result | Value |
| Average AIIS change in the simulation | +2.39% |
| Districts that improved | 5,067 (68.9%) |
| Districts that declined | 2,267 (30.8%) |
| Unchanged | 21 (0.3%) |

## Limitations
- The simulation changes the score on average, but about 31% of districts score lower, so the effect is not uniform.
- The Random Forest R² (0.9957) was measured on the same data used for training, so it does not show accuracy on new data.
- AIIS values are small (average 0.0186), so the dashboard shows them ×100.
- Some state-year combinations have very few districts.

## Files
- `notebooks/ANALYSIS_OF_PMFBY.ipynb`: full analysis
- `dashboard/PMFBY_Dashboard.pbix` and `dashboard/screenshots/`: Power BI report
- `data/aiis_scores.csv`, `data/digital_twin.csv`: exported results

## My contribution
* I have developed a insurance intellegence system for Pradhan Mantri Fasal Bima Yojana Scheme using perfomance indicators and participation indicators using weighted entropy method. also used k-mean clustering to and found high performing and low performing districts. also built a random forest model and simulated a digital twin model .*

## Data source
District-level PMFBY data compiled from official government reports (2018–2025).

## Tools
Python (pandas, NumPy, scikit-learn, statsmodels), Excel, Power BI
