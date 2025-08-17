# Hotel Booking Data Analysis - For Learning

This project explores the **Hotel Booking dataset**, a rich real-world dataset containing hotel reservation details, cancellations, customer behavior, and pricing(Antonio, Almeida & Nunes, 2019, Kaggle/UCI).  
The aim is to perform **end-to-end analysis** using Excel, Python, and Tableau — showcasing how different tools can complement one another for data cleaning, exploration, visualization, and insights.

---

## 📂 Project Structure

```
.
├── data/
│   ├── raw/                  # Original dataset (hotel_bookings.csv)
│   ├── processed/            # Processed datasets exported for BI tools
├── notebooks/
│   ├── hotel_analysis.ipynb  # Python data cleaning, exploration, and visuals + ML
├── reports/
│   ├── figs/                 # Plots and charts generated in Python
├── README.md                 # Project documentation
```

---

## 🔹 Excel Analysis

Excel was used for **pivot-table style exploration** of the dataset:

1. **Booking Volume by Hotel Type & Year**  
   - Clustered column chart comparing Resort vs City hotel demand.  
   - ![Booking Volume by Hotel Type & Year](./reports/figs/excel_bookingvolume_byhoteltype_year.png) 

2. **Cancellations by Market Segment**  
   - Pivot table showing which customer segments cancel most frequently.  
   - ![Cancellation by Market Segment](./reports/figs/excel_cancellation_bymarketsegments.png)  

3. **ADR (Average Daily Rate) Trends by Month**  
   - Line chart of average pricing patterns across hotels.  
   - ![Average Daily Rate (ADR) by Month & Hotel](./reports/figs/excel_adr_bymonth_andhoteltype.png)

4. **Average Stay Duration by Customer Type**  
   - Bar chart of stay behavior across different customer types.  
   - ![Average Stay Duration by Customer Type](./reports/figs/excel_averagestay_customertype.png)  

---

## 🔹 Python Analysis

Python provided deeper data cleaning, preparation, more visualizations, and Machine Learning Model for cancellation prediction.

### Data Preparation
- Cleaned inconsistent column names and data types.  
- Converted date fields into datetime format.  
- Handled missing values in `children`, `agent`, and `company`.  
- Created processed tables for BI tools.

### Key Visualizations
1. **Bookings by Hotel Type & Year**  
   - Clustered column plot plot.  
   - ![Booking Volume by Hotel Type & Year](./reports/figs/hb_vol_by_hotel_year.png)

2. **Cancellations by Market Segment**  
   - Cacellation frequency by customer type.  
   - ![Cancellation by Market Segment](./reports/figs/hb_cancel_rate_by_segment.png)

3. **ADR by Month & Hotel**  
   - Seasonal pricing trends.  
   - ![Average Daily Rate (ADR) by Month & Hotel](./reports/figs/hb_adr_by_month_hotel.png)  

4. **Stay Duration by Customer Type**  
   - Boxplot distribution to identify outliers.  
   - ![Average Stay Duration by Customer Type](./reports/figs/hb_avg_stay_by_customer.png)

5. **Cancellation Rate by Lead Time (deciles)**
   - cancellation probability vs lead-time bins (deciles = splitting the dataset into 10 equal-sized groups).
   - Insight: Bookings made far in advance tend to have higher cancellation rates.
   - ![Cancellation Rate by Lead Time](./reports/figs/hb_cancel_rate_by_leadtime.png)

6. **Numeric Feature Correlations**
   - Heatmap showing correlation between numeric variables (lead time, total stay, ADR, etc.) and cancellation outcome.
   - Helps identify strong relationships before modeling (e.g., lead time and cancellation are positively correlated).
   - ![Heatmap](./reports/figs/hb_corr_numeric.png)

### Machine Learning (Bonus)
- Built a **logistic regression model** to predict cancellation likelihood.  

1. **Top Drivers of Cancellation (Logistic Regression)**
   - Bar plot of the most influential features from the logistic regression model.
   - Shows which variables (e.g., lead time, ADR, special requests) are most predictive of cancellations.
   - ![Feature Relevance](./reports/figs/hb_top_features_logreg.png)

2. **ROC Curve — Cancellation Model (LogReg)**
   - Receiver Operating Characteristic curve for the logistic regression cancellation model.
   - Demonstrates the model’s ability to distinguish between cancelled vs non-cancelled bookings.
   - ![ROC Curve](./reports/figs/hb_roc_logreg.png)

---

## 🔹 Tableau Dashboards

Data was connected to Tableau Public for interactive dashboards.

### Sheets
- **Booking Volume by Hotel Type & Year**
   - ![](./reports/figs/tab_vol_year_type.png)  
- **Cancellation Rate by Market Segment**
   - ![](./reports/figs/tab_cancelation_market_segment.png)   
- **ADR Trends by Month & Hotel**
   - ![](./reports/figs/tab_adr_month_type.png)
- **Average Stay Duration by Customer Type**
   - ![](./reports/figs/tab_Avgstay_customertype.png)
- **Monthly KPIs (Bookings vs Cancels, ADR, Cancellation Rate)**
   - ![](./reports/figs/tab_KPI_Dashboard.png)

---

## 🔹 Insights & Recommendations

### Key Insights
- **City Hotels** receive more bookings overall, but also higher cancellation rates.  
- **Resort Hotels** show strong seasonality in ADR (higher prices in summer).  
- **Corporate & Offline Travel Agents** segments are more stable (fewer cancellations).  
- **Transient customers** cancel the most frequently.  
- Average stay duration is longer for **Resort Hotels** and **Group bookings**.

### Recommendations
- Adjust **pricing strategy** for resorts during off-peak months to smooth demand.  
- Implement **stricter cancellation policies** for high-cancel segments (e.g., transient).  
- Incentivize **longer stays** (e.g., discounts for 4+ nights).  
- Monitor ADR trends for revenue management optimization.

---

## 📊 Tools Used

- **Excel** → Pivot tables and quick exploration.  
- **Python (Pandas, Matplotlib, Seaborn, Plotly)** → Cleaning, advanced visualizations, ML.  
- **Tableau Public** → Dashboards & interactive storytelling.  

---

## 🚀 Next Steps

- Expand the machine learning model with Random Forest / XGBoost.  
- Add more BI dashboards combining customer and cancellation insights.  
- Automate monthly KPI reporting pipeline.

---

## 📌 Summary

This project demonstrates how to take a raw hotel booking dataset and transform it into **business insights** through a combination of:  
- Spreadsheet analysis (Excel)  
- Data science workflow (Python)  
- BI dashboards (Tableau)  

It provides a **full analytics workflow** from raw data to actionable recommendations.
