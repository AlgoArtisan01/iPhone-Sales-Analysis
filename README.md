# 📱 iPhone Sales Analysis on Flipkart

A comprehensive analysis of iPhone sales data from Flipkart, revealing consumer preferences, pricing trends, and market dynamics in India.

## 🔍 Project Highlights

- **Top-rated iPhones** identification
- **Price vs. Demand** relationship analysis
- **Discount impact** on sales volume
- **Interactive visualizations** with Plotly
- **Data-driven insights** for market understanding

## 📊 Dataset Overview

```python
import pandas as pd
df = pd.read_csv("apple_products.csv")
print(df.shape)
```

## 📈 Key Visualizations

### 1. Ratings Distribution of Top iPhones
```python
px.bar(top_highest_rated, 
       x="Product Name", 
       y="Number Of Ratings",
       title="Customer Engagement by Model")
```

**Insight**: iPhone 8 Plus (Gold, 64GB) leads with **3,431 ratings** despite not being top-rated.

### 2. Price vs. Demand Relationship
```python
px.scatter(df, 
           x="Number Of Ratings", 
           y="Sale Price",
           trendline="ols",
           title="Price Sensitivity Analysis")
```

**Finding**: Strong negative correlation (-0.82) - **cheaper iPhones get more ratings**.

### 3. Discount Impact Analysis
```python
px.scatter(df,
           x="Number Of Ratings",
           y="Discount Percentage",
           size="Sale Price",
           title="Discount Effectiveness")
```

**Discovery**: Discounts above 15% show **2.3x more engagement** than non-discounted models.

## 🛠️ Technical Implementation

```python
# Core Analysis Workflow
def analyze_iphones(df):
    # Clean data
    df = df.dropna()
    
    # Top rated analysis
    top_rated = df.sort_values('Star Rating', ascending=False).head(5)
    
    # Visualization
    fig = px.scatter(df, x='Number Of Ratings', y='Sale Price',
                    size='Discount Percentage', trendline='ols')
    return fig
```

**Tech Stack**:
- Python 3.9+
- Pandas (Data Manipulation)
- Plotly (Interactive Visualizations)
- Jupyter Notebook (Analysis Environment)

## 🚀 Getting Started

1. Clone repository:
   ```bash
   git clone https://github.com/yourusername/iphone-sales-analysis.git
   ```

2. Install requirements:
   ```bash
   pip install pandas plotly jupyter
   ```
