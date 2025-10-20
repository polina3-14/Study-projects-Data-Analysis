# Scooter Rent Statistical Analysis

A comprehensive data analysis project exploring user behavior and revenue patterns in the GoFast scooter rental service using historical ride data and user subscription information.

## 📋 Project Overview

This project analyzes scooter rental data from GoFast to understand user behavior patterns, subscription model effectiveness, and revenue drivers. The analysis provides insights for optimizing pricing strategies and improving customer retention.

## 🎯 Business Objectives

- **User Behavior Analysis**: Understand how different user segments utilize scooter rentals
- **Subscription Impact**: Evaluate the financial impact of Ultra subscription model
- **Revenue Optimization**: Identify key factors driving revenue generation
- **Marketing Strategy**: Provide data-driven insights for promotional campaigns and user acquisition

## 📊 Data Sources

### Users Dataset
- **Source**: `users_go.csv`
- **Records**: 1,565 unique users (1,534 after deduplication)
- **Features**: User demographics, location, subscription type

### Rides Dataset  
- **Source**: `rides_go.csv`
- **Records**: 18,068 rides (17,973 after anomaly removal)
- **Features**: Ride distance, duration, timestamps

### Subscriptions Dataset
- **Source**: `subscriptions_go.csv`
- **Records**: 2 subscription types
- **Features**: Pricing structure for free and Ultra subscriptions

## 🛠️ Technical Implementation

### Data Preprocessing & Cleaning

#### Data Quality Improvements
- **Duplicate Removal**: Removed 31 duplicate user records
- **Date Conversion**: Converted ride dates to datetime format
- **Anomaly Detection**: Removed 95 rides with unrealistic durations (<0.5 minutes)
- **Data Integration**: Merged users, rides, and subscriptions into unified dataset

#### Feature Engineering
- **Month Extraction**: Created month column from ride dates
- **Revenue Calculation**: Implemented pricing logic for both subscription types
- **Duration Rounding**: Rounded ride durations up to nearest minute for billing

### Statistical Analysis Framework

#### Hypothesis Testing
- **T-tests**: Compared user behavior between subscription types
- **One-sample tests**: Validated against business thresholds
- **Normal Approximation**: Used for large-sample probability calculations

## 📈 Key Findings

### User Demographics

#### Geographic Distribution
- **Most Active**: Pyatigorsk (219 users)
- **Least Active**: Moscow (168 users)
- **City Coverage**: 8 major Russian cities

#### Subscription Patterns
- **Ultra Subscribers**: 45.5% of user base
- **Free Users**: 54.5% of user base
- **Adoption Rate**: Strong uptake of premium subscription

#### Age Distribution
- **Average Age**: 25 years
- **Age Range**: 12 to 43 years
- **Primary Demographic**: Young adults (22-28 years)

### Ride Behavior Analysis

#### Distance Patterns
- **Average Distance**: 3,059 meters per ride
- **Distance Range**: 0.86m to 7,066m
- **Subscription Difference**: Ultra users ride slightly longer distances (3,115m vs 3,045m)

#### Duration Patterns  
- **Average Duration**: 17.9 minutes per ride
- **Duration Range**: 2.04 to 40.82 minutes
- **Subscription Advantage**: Ultra users have longer rides (18.18 minutes vs free users)

### Revenue Insights

#### Pricing Structure
- **Free Subscription**: 50 RUB start fee + 8 RUB/minute
- **Ultra Subscription**: 199 RUB monthly fee + 6 RUB/minute (no start fee)

#### Revenue Performance
- **Ultra Superiority**: Higher monthly revenue per user compared to free users
- **Statistical Significance**: Confirmed through hypothesis testing (p-value: 2.5e-36%)

## 🔍 Hypothesis Testing Results

### Key Findings

1. **Ride Duration**: Ultra subscribers spend significantly more time riding (p-value: 5.68e-35%)
2. **Optimal Distance**: Ultra users average 3,130 meters - optimal for scooter wear-and-tear
3. **Revenue Superiority**: Ultra subscribers generate higher monthly revenue (statistically significant)

### Business Implications
- **Ultra subscribers are more valuable** across multiple dimensions
- **Subscription model protects scooter lifespan** through optimal usage patterns
- **Premium features drive engagement** and revenue

## 📊 Marketing & Promotional Analysis

### Promo Code Campaign

#### Scenario Analysis
- **Success Rate**: 10% conversion from trial to paid subscription
- **Target**: 100 successful conversions
- **Confidence Level**: 95% success probability

#### Results
- **Minimum Promo Codes**: 1,158 required to meet target
- **Risk Management**: 5% probability of missing target with calculated quantity

### Push Notification Campaign

#### Large-Scale Analysis
- **Campaign Size**: 1 million notifications
- **Expected Open Rate**: 40%
- **Performance Threshold**: 399,500 opens

#### Probability Assessment
- **Success Probability**: 85% chance of exceeding threshold
- **Underperformance Risk**: 15% probability of ≤399,500 opens

## 🚀 How to Use

### Prerequisites
```bash
pip install pandas matplotlib scipy numpy
```

### Running the Analysis
1. Clone the repository
2. Ensure datasets are in the `datasets/` directory
3. Run the Jupyter notebook: `scooter_rent_statistical_analysis.ipynb`
4. Follow the step-by-step analysis methodology

## 📝 Conclusion & Recommendations

### Strategic Insights
#### Subscription Model Success
- Ultra subscription is financially superior with higher revenue per user
- User behavior aligns with business goals - Ultra users ride optimal distances
- Strong market acceptance with nearly equal split between free and paid users
#### Growth Opportunities
- Increase Ultra adoption through targeted marketing to free users
- Geographic expansion in underpenetrated markets like Moscow
- Age-based marketing focusing on core 22-28 demographic
#### Operational Excellence
- Scooter maintenance benefits from optimal usage patterns of Ultra subscribers
- Pricing strategy validation confirms current model effectiveness
- Customer retention focus on converting trial users to paid subscriptions

### Marketing Recommendations
- Promo Code Strategy: Distribute 1,158+ codes for 95% success probability
- Push Notification: Expect 400k+ opens with 85% confidence
- Segmentation: Target young urban professionals in high-activity cities
- Upsell Strategy: Convert free users through demonstrated value proposition
