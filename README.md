# Mobile Phone Price Analysis 📱

A data analysis project that explores how mobile phone prices vary by brand and hardware specifications using Python, Pandas, and Matplotlib. The project includes raw and cleaned datasets, exploratory analysis, and visualizations to help identify patterns in mobile phone pricing.

> **Dataset note:** The datasets used in this project are synthetic and intended for educational and demonstration purposes. They do not represent verified current market prices.

## Project Objectives

- Compare average mobile phone prices across brands.
- Explore the relationship between RAM and price.
- Analyze storage capacity and average price.
- Visualize the distribution of phone prices.
- Examine battery capacity and camera resolution in relation to price.
- Demonstrate a basic data-cleaning workflow.

## Repository Structure

```text
mobile-phone-price-analysis/
├── mobile_phone_price_raw.csv
├── mobile_phone_price_cleaned.csv
├── mobile_phone_price_analysis.py
├── brand_price_analysis.csv
└── README.md
```

*The filenames above are suggested. Include only files that you upload to your repository.*

## Dataset Description

| Column | Description |
|---|---|
| `phone_id` | Unique identifier for each phone record |
| `brand` | Mobile phone brand |
| `model` | Phone model name |
| `ram_gb` | RAM capacity in gigabytes |
| `storage_gb` | Internal storage capacity in gigabytes |
| `battery_mah` | Battery capacity in milliampere-hours (mAh) |
| `camera_mp` | Camera resolution in megapixels |
| `release_year` | Phone release year |
| `price_inr` | Phone price in Indian rupees (INR) |

### Raw and Cleaned Data

- **Raw dataset:** Contains intentionally introduced data-quality issues such as missing values, inconsistent text formatting, a duplicate row, and an extreme price value.
- **Cleaned dataset:** Standardizes text, converts numeric fields, fills missing values, removes duplicate rows, and caps extreme prices using the interquartile range (IQR) method.

## Tools and Technologies

- **Python** — programming language
- **Pandas** — data loading, cleaning, and grouping
- **Matplotlib** — data visualization
- **Google Colab / Jupyter Notebook** — code execution

## Visualizations

The analysis generates these charts:

1. **Average Price by Brand** — compares mean phone prices across brands.
2. **RAM vs. Price** — scatter plot exploring RAM and price.
3. **Storage vs. Average Price** — line chart comparing storage capacity with average price.
4. **Price Distribution** — histogram showing the distribution of prices.
5. **Battery Capacity vs. Price** — scatter plot exploring battery capacity and price.
6. **Camera Resolution vs. Average Price** — bar chart comparing average prices across camera resolutions.

## Getting Started

### 1. Clone the repository

Replace `<your-username>` with your GitHub username:

```bash
git clone https://github.com/<your-username>/mobile-phone-price-analysis.git
cd mobile-phone-price-analysis
```

### 2. Install dependencies

```bash
pip install pandas matplotlib
```

### 3. Run the analysis

If your Python script is named `mobile_phone_price_analysis.py` and reads the CSV from the current directory:

```bash
python mobile_phone_price_analysis.py
```

Alternatively, open your notebook in Google Colab, upload `mobile_phone_price_cleaned.csv`, and run the analysis cells.

## Example Python Workflow

```python
import pandas as pd
import matplotlib.pyplot as plt

df = pd.read_csv("mobile_phone_price_cleaned.csv")

brand_prices = df.groupby("brand")["price_inr"].mean().sort_values(ascending=False)
print(brand_prices)

brand_prices.plot(kind="bar", figsize=(10, 5))
plt.title("Average Mobile Phone Price by Brand")
plt.xlabel("Brand")
plt.ylabel("Average Price (INR)")
plt.xticks(rotation=45)
plt.tight_layout()
plt.show()
```

## Key Questions

- Which brand has the highest average price in this dataset?
- How does price vary across RAM and storage capacities?
- Which price ranges contain the most phones?
- Do battery capacity or camera resolution show a clear relationship with price?
- What data-quality issues were corrected during cleaning?

## Data Cleaning Steps

1. Trim whitespace and standardize brand/model text.
2. Convert price strings (including rupee symbols and commas) to numeric values.
3. Convert specification columns to numeric data types.
4. Remove duplicate records.
5. Fill missing numeric values using the median and categorical values using the mode.
6. Cap extreme price values using IQR-based bounds.

## Limitations

- The data is synthetic, not collected from a live retailer or verified market source.
- Relationships observed in this dataset should not be treated as universal market trends.
- Average price comparisons do not account for every factor, such as condition, discounts, region, or seller.

## Future Improvements

- Add more records from a verified, properly cited source.
- Add a correlation heatmap.
- Create an interactive dashboard using Plotly or Power BI.
- Train and evaluate a regression model to predict phone prices.
- Add automated data validation and tests.

## Author

**Your Name**

## License

Choose a license before distributing this project publicly. For example, the MIT License is commonly used for open-source projects; only add it if you intend to license your work under those terms.
