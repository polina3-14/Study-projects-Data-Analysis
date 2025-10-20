# Real Estate Market Analysis in St. Petersburg

A comprehensive data analysis project exploring the real estate market in St. Petersburg and surrounding areas using historical property listing data from Yandex Real Estate.

## 📋 Project Overview

This project analyzes property listings from Yandex Real Estate to understand market trends, identify key factors influencing property prices, and build insights for automated property valuation systems and fraud detection.

## 🎯 Business Objectives

- **Market Understanding**: Analyze property market trends in St. Petersburg and Leningrad region
- **Price Determinants**: Identify key factors affecting property prices
- **Automated Systems**: Provide insights for building automated valuation models
- **Anomaly Detection**: Help identify suspicious listings and potential fraud

## 📊 Data Sources

### Yandex Real Estate Dataset
- **Source**: `real_estate_data.csv`
- **Records**: 23,699 property listings
- **Time Period**: Multiple years of historical data
- **Features**: 22 attributes including property characteristics, location data, and pricing information

### Data Categories
- **User-Provided Data**: Property specifications, photos, pricing
- **Automated Data**: Geographic data from mapping services (distances to key locations)

## 🛠️ Technical Implementation

### Data Preprocessing & Cleaning

#### Missing Value Treatment
- **Living Area**: Filled with median values by room count
- **Kitchen Area**: Filled with median values by room count (0 for studios)
- **Balcony**: Missing values replaced with 0 (assuming no balcony)
- **Location Names**: Standardized and deduplicated locality names
- **Distance Data**: Filled with median distances by locality
- **Park/Pond Counts**: Missing values replaced with 0

#### Data Quality Improvements
- **Data Type Conversion**: Converted `is_apartment` to boolean, date fields to datetime
- **Duplicate Removal**: Standardized 365 locality names to 302 unique locations
- **Anomaly Detection**: Removed properties with living area > total area
- **Outlier Treatment**: Addressed unrealistic ceiling heights and property areas

### Feature Engineering

#### New Features Created
- `price_per_meter`: Price per square meter
- `weekday_publish`: Day of week when listing was published (0=Monday)
- `month_publish`: Month when listing was published
- `year_publish`: Year when listing was published
- `floor_type`: Categorized as "первый", "последний", "другой" (first, last, other)
- `city_center_km`: Distance to city center in kilometers

## 📈 Key Findings

### Property Characteristics

#### Price Distribution
- **Average Price**: 6.55 million RUB
- **Median Price**: 4.65 million RUB
- **Price Range**: 430,000 RUB to 763 million RUB
- **Price per m²**: 99,380 RUB (average)

#### Property Size Analysis
- **Total Area**: Average 60.4 m², Median 52 m²
- **Living Area**: Average 34.4 m², Median 30.4 m²
- **Kitchen Area**: Average 10.4 m², Median 9.0 m²
- **Room Count**: Average 2.1 rooms, Mostly 2-room apartments

#### Location Insights
- **Center Distance**: Properties within 10km of center command premium prices
- **Popular Areas**: St. Petersburg, Murino, Kudrovo, Shushary
- **Price Gradient**: Clear inverse relationship between distance from center and price

### Market Dynamics

#### Sales Timeline
- **Median Time to Sell**: 95.5 days
- **Sales Distribution**: Most properties sell within 6 months
- **Quick Sales**: Some properties sell in 1 day
- **Long Listings**: Some properties remain listed for over 4 years

#### Seasonal Patterns
- **High-Price Listings**: More common in September
- **Low-Price Listings**: More common in October
- **Weekend Listings**: Higher-priced properties listed on Saturdays

## 🔍 Correlation Analysis

### Strongest Price Correlations
1. **Total Area**: 0.65 correlation with price
2. **Living Area**: 0.56 correlation with price  
3. **Kitchen Area**: 0.45 correlation with price
4. **Room Count**: 0.36 correlation with price
5. **Ceiling Height**: 0.38 correlation with price

### Location Impact
- **Center Proximity**: -0.21 correlation (closer = higher price)
- **Airport Distance**: Minimal direct correlation (-0.04)

## 🎯 Top 10 Locations by Listing Count

| Location | Average Price/m² (RUB) | Listings |
|----------|------------------------|----------|
| St. Petersburg | 104,694 | 15,721 |
| Murino | 86,111 | 522 |
| Kudrovo | 95,763 | - |
| Shushary | 76,923 | 440 |
| Vsevolozhsk | 65,789 | 398 |
| Pushkin | 99,994 | 369 |
| Kolpino | 74,724 | - |
| Pargolovo | 91,643 | - |
| Gatchina | 67,797 | - |
| Vyborg | 58,133 | - |

## 📊 Visualizations

### Key Charts Created
- Distribution histograms for all numerical features
- Scatter matrix for key price determinants
- Correlation heatmaps
- Time series analysis of listing patterns
- Geographic price distribution maps
- Categorical analysis of floor types and room counts

## 🚀 How to Use

### Prerequisites
```bash
pip install pandas numpy matplotlib seaborn missingno
```

### Running the Analysis
1. Ensure dataset `real_estate_data.csv` is available
2. Run the Jupyter notebook: `real_estate_evaluation.ipynb`
3. Follow the step-by-step analysis

### Key Functions
- `replace_with_median()`: Fills missing values with median by category
- `remove_words()`: Standardizes locality names
- `categorize_floor()`: Classifies floor types

## 📝 Conclusion

### What Makes Properties More Valuable?
- Size Matters: Larger total and living areas significantly increase value
- Location Premium: Properties within 10km of city center command highest prices
- Floor Position: First floors are cheapest, last floors (penthouses) most expensive
- Modern Features: Higher ceilings correlate with higher prices
- Room Configuration: More rooms generally increase value, with premium for larger configurations

### Market Recommendations
- Pricing Strategy: Use location-based pricing models with center proximity as key factor
- Investment Focus: Target properties with high ceiling heights and larger kitchen areas
- Sales Timing: List premium properties in September for better visibility
- Market Segmentation: Differentiate between central St. Petersburg and suburban markets

### Fraud Detection Indicators
- Price Anomalies: Extremely low prices per square meter
- Size Inconsistencies: Living area exceeding total area
- Unrealistic Features: Impossible ceiling heights or room configurations
- Location Mismatches: Claimed locations inconsistent with distance data

